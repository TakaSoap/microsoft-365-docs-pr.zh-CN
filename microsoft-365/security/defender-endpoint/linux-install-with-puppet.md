---
title: 使用 Puppet 在 Linux 上部署Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何使用 Puppet 在 Linux 上部署Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 木偶， ansible， linux， redhat， ubuntu， debian， sles， suse， centos， fedora， amazon linux 2
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5ec3eb5d12933b33f4af7d5af96b4ab54fda4604
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663789"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a>使用 Puppet 在 Linux 上部署Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

本文介绍如何使用 Puppet 在 Linux 上部署 Defender for Endpoint。 成功部署需要完成以下所有任务：

- [下载载入包](#download-the-onboarding-package)
- [创建 Puppet 清单](#create-a-puppet-manifest)
- [部署](#deployment)
- [检查载入状态](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>先决条件和系统要求

 有关当前软件版本的先决条件和系统要求的说明，请参阅 [Linux 页面上的主 Defender for Endpoint](microsoft-defender-endpoint-linux.md)。

此外，对于 Puppet 部署，需要熟悉 Puppet 管理任务、已配置 Puppet 以及了解如何部署包。 Puppet 有许多方法可以完成同一任务。 这些说明假定支持 Puppet 模块的可用性，例如 *，可以* 帮助部署包。 组织可能使用其他工作流。 有关详细信息，请参阅 [Puppet 文档](https://puppet.com/docs) 。

## <a name="download-the-onboarding-package"></a>下载载入包

从Microsoft 365 Defender门户下载载入包：

1. 在Microsoft 365 Defender门户中，转到 **设置 >终结点>设备管理>载入**。
2. 在第一个下拉菜单中，选择 **Linux Server** 作为操作系统。 在第二个下拉菜单中，选择 **首选的 Linux 配置管理工具** 作为部署方法。
3. 选择 **"下载载入"包**。 将文件另存为WindowsDefenderATPOnboardingPackage.zip。

   :::image type="content" source="images/portal-onboarding-linux-2.png" alt-text="下载载入包的选项" lightbox="images/portal-onboarding-linux-2.png":::

4. 在命令提示符下，验证你是否拥有该文件。 

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

5. 提取存档的内容。

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```

    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>创建 Puppet 清单

需要创建 Puppet 清单，以便将 Linux 上的 Defender for Endpoint 部署到 Puppet 服务器管理的设备。 本示例使用 puppetlab 提供的 *apt* 和 *yumrepo* 模块，并假定模块已安装在 Puppet 服务器上。

在 Puppet 安装的模块文件夹下创建文件夹 *install_mdatp/文件* 和 *install_mdatp/清单* 。 此文件夹通常位于 Puppet 服务器上的 */etc/puppetlabs/code/environments/production/modules* 中。 将上面创建的mdatp_onboard.json 文件复制到 *install_mdatp/文件* 文件夹。 创建 *init.pp* 包含部署说明的文件：

```bash
pwd
```

```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```

```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>`install_mdatp/manifests/init.pp` 的内容

Linux 上的 Defender for Endpoint 可以从以下频道之一部署， (如下所示的 *[频道]*) ： *预览体验成员速度快*、 *预览体验成员速度缓慢* 或 *引发*。其中每个通道都对应于 Linux 软件存储库。

通道的选择决定了提供给设备的更新的类型和频率。 以 *预览体验成员为快的* 设备是第一个接收更新和新功能的设备，其次是 *预览体验成员缓慢* 的设备，最后是 *促销*。

为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用 *预览体验成员快* 或 *预览体验成员慢*。

> [!WARNING]
> 在初始安装后切换通道需要重新安装产品。 若要切换产品通道：卸载现有包，重新配置设备以使用新通道，并按照本文档中的步骤从新位置安装包。

记下你的分发和版本，并标识其下 `https://packages.microsoft.com/config/[distro]/`最接近的条目。

在以下命令中，将 *[distro]* 和 *[version]* 替换为你已识别的信息：

> [!NOTE]
> 对于 RedHat、Oracle Linux、Amazon Linux 2 和 CentOS 8，请将 *[distro]* 替换为"rhel"。

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle Linux, Amazon Linux 2, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>部署

在 site.pp 中包含上述清单 文件：

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```

```Output
node "default" {
    include install_mdatp
}
```

注册的代理设备会定期轮询 Puppet Server，并在检测到新配置文件和策略后立即安装它们。

## <a name="monitor-puppet-deployment"></a>监视 Puppet 部署

在代理设备上，还可以通过运行以下命令来检查载入状态：

```bash
mdatp health
```

```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **许可**：这可确认设备已绑定到组织。

- **orgId**：这是 Defender for Endpoint 组织标识符。

## <a name="check-onboarding-status"></a>检查载入状态

可以通过创建脚本来检查设备是否已正确载入。 例如，以下脚本检查已注册设备的载入状态：

```bash
mdatp health --field healthy
```

如果产品已载入并按预期运行，则会打印 `1` 上述命令。

> [!IMPORTANT]
> 当产品首次启动时，它会下载最新的反恶意软件定义。 这可能需要几分钟的时间，具体取决于 Internet 连接。 在此期间，上述命令返回值 `0`。

如果产品不正常，则可通过 `echo $?`) 检查的退出代码 (指示问题：

- 1 如果设备尚未载入。
- 3 如果无法建立与守护程序的连接。

## <a name="log-installation-issues"></a>日志安装问题

 有关如何查找安装程序在发生错误时创建的自动生成的日志的详细信息，请参阅 [日志安装问题](linux-resources.md#log-installation-issues)。

## <a name="operating-system-upgrades"></a>操作系统升级

将操作系统升级到新主版本时，必须先卸载 Linux 上的 Defender for Endpoint，安装升级，最后在设备上的 Linux 上重新配置 Defender for Endpoint。

## <a name="uninstallation"></a>卸载

在 *init.pp* 中使用以下内容 *创建类似于**install_mdatp* 的模块remove_mdatp 文件：

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
