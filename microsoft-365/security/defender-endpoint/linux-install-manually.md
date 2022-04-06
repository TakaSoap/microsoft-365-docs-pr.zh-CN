---
title: 手动在 Linux 上部署Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何从命令行手动在 Linux 上部署Microsoft Defender for Endpoint。
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
ms.openlocfilehash: a0f499a08288735d5f0d75e7111ec0b6360908a8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664515"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>手动在 Linux 上部署Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。


本文介绍如何在 Linux 上手动部署Microsoft Defender for Endpoint。 成功部署需要完成以下所有任务：

  - [先决条件和系统要求](#prerequisites-and-system-requirements)
  - [配置 Linux 软件存储库](#configure-the-linux-software-repository)
    - [CentOS、Fedora、Oracle Linux 和 Amazon Linux 2 (RHEL 和变体) ](#rhel-and-variants-centos-fedora-oracle-linux-and-amazon-linux-2)
    - [SLES 和变体](#sles-and-variants)
    - [Ubuntu 和 Debian 系统](#ubuntu-and-debian-systems)
  - [应用程序安装](#application-installation)
  - [下载载入包](#download-the-onboarding-package)
  - [客户端配置](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>先决条件和系统要求

在开始之前，请参阅 [Linux 上的Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)，了解当前软件版本的先决条件和系统要求。

> [!WARNING]
> 在产品安装后将操作系统升级到新的主要版本需要重新安装该产品。 需要 [卸载](linux-resources.md#uninstall) Linux 上的现有 Defender for Endpoint，升级操作系统，然后按照以下步骤在 Linux 上重新配置 Defender for Endpoint。

## <a name="configure-the-linux-software-repository"></a>配置 Linux 软件存储库

Linux 上的 Defender for Endpoint 可以从以下频道之一部署， (如下所示的 *[频道]*) ： *预览体验成员速度快*、 *预览体验成员速度缓慢* 或 *引发*。其中每个通道都对应于 Linux 软件存储库。 下面提供了有关将设备配置为使用这些存储库之一的说明。

通道的选择决定了提供给设备的更新的类型和频率。 以 *预览体验成员为快的* 设备是第一个接收更新和新功能的设备，其次是 *预览体验成员缓慢* 的设备，最后是 *促销*。

为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用 *预览体验成员快* 或 *预览体验成员慢*。

> [!WARNING]
> 在初始安装后切换通道需要重新安装产品。 若要切换产品通道：卸载现有包，重新配置设备以使用新通道，并按照本文档中的步骤从新位置安装包。

### <a name="rhel-and-variants-centos-fedora-oracle-linux-and-amazon-linux-2"></a>CentOS、Fedora、Oracle Linux 和 Amazon Linux 2 (RHEL 和变体) 

- `yum-utils`安装（如果尚未安装）：

    ```bash
    sudo yum install yum-utils
    ```

  > [!NOTE]
  > 你的分发和版本，并标识最接近的条目 (主要，然后次要) 下 `https://packages.microsoft.com/config/rhel/`。

    使用下表来帮助指导你查找包：

    <br>

    ****

    |发行版&版本|包|
    |---|---|
    |对于 RHEL/Centos/Oracle 8.0-8.5|<https://packages.microsoft.com/config/rhel/8/[channel].repo>|
    |对于 RHEL/Centos/Oracle 7.2-7.9 & Amazon Linux 2 |<https://packages.microsoft.com/config/rhel/7/[channel].repo>|
    |对于 RHEL/Centos 6.7-6.10|<https://packages.microsoft.com/config/rhel/6/[channel].repo>|
    |对于 Fedora 33|<https://packages.microsoft.com/config/fedora/33/prod.repo>|
    |对于 Fedora 34|<https://packages.microsoft.com/config/fedora/34/prod.repo>|

    在以下命令中，将 *[version]* 和 *[channel]* 替换为你已识别的信息：


    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/rhel/[version]/[channel].repo
    ```

    > [!TIP]
    > 使用 hostnamectl 命令标识系统相关信息，包括版本 *[version]*。

    例如，如果运行 CentOS 7 并希望从 *Prod* 通道在 Linux 上部署 Defender for Endpoint：

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/rhel/7/prod.repo
    ```

    或者，如果想要探索所选设备上的新功能，可能需要在 Linux 上将Microsoft Defender for Endpoint部署到 *预览体验成员快速* 频道：

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/rhel/7/insiders-fast.repo
    ```

- 安装 Microsoft GPG 公钥：

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="sles-and-variants"></a>SLES 和变体

> [!NOTE]
> 你的分发和版本，并标识最接近的条目 (主要，然后次要) 下 `https://packages.microsoft.com/config/sles/`。

   在以下命令中，将 *[distro]* 和 *[version]* 替换为你已识别的信息：

   ```bash
   sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
   ```

   > [!TIP]
   > 使用 SPident 命令标识系统相关信息，包括版本 *[version]*。

   例如，如果运行的是 SLES 12，并且希望从 *prod* 通道在 Linux 上部署Microsoft Defender for Endpoint：

   ```bash
   sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
   ```

- 安装 Microsoft GPG 公钥：

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Ubuntu 和 Debian 系统

- `curl`安装（如果尚未安装）：

    ```bash
    sudo apt-get install curl
    ```

- `libplist-utils`安装（如果尚未安装）：

    ```bash
    sudo apt-get install libplist-utils
    ```

> [!NOTE]
> 你的分发和版本，并标识最接近的条目 (主要，然后次要) 下 `https://packages.microsoft.com/config/[distro]/`。

   在以下命令中，将 *[distro]* 和 *[version]* 替换为你确定的信息：

   ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
   ```

   > [!TIP]
   > 使用 hostnamectl 命令标识系统相关信息，包括版本 *[version]*。

   例如，如果运行 Ubuntu 18.04，并希望从 *prod* 通道在 Linux 上部署Microsoft Defender for Endpoint：

   ```bash
   curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
   ```

- 安装存储库配置：

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```

    例如，如果选择了 *prod* 通道：

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- 如果尚未安装， `gpg` 请安装包：

    ```bash
    sudo apt-get install gpg
    ```

  如果 `gpg` 不可用，请安装 `gnupg`。

    ```bash
    sudo apt-get install gnupg
    ```

- 安装 Microsoft GPG 公钥：

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- 安装 https 驱动程序（如果尚未存在）：

    ```bash
    sudo apt-get install apt-transport-https
    ```

- 更新存储库元数据：

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>应用程序安装

- CentOS 和 Oracle Linux (RHEL 和变体) ：

    ```bash
    sudo yum install mdatp
    ```

    > [!NOTE]
    > 如果在设备上配置了多个 Microsoft 存储库，则可以具体说明要从哪个存储库安装包。 以下示例演示如何在此设备上配置存储库通道时从 `production` 通道 `insiders-fast` 安装包。 如果在设备上使用多个 Microsoft 产品，则可能会发生这种情况。 根据服务器的分布和版本，存储库别名可能与以下示例中的别名不同。

    ```bash
    # list all repositories
    yum repolist
    ```

    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```

    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- SLES 和变体：

    ```bash
    sudo zypper install mdatp
    ```

    > [!NOTE]
    > 如果在设备上配置了多个 Microsoft 存储库，则可以具体说明要从哪个存储库安装包。 以下示例演示如何在此设备上配置存储库通道时从 `production` 通道 `insiders-fast` 安装包。 如果在设备上使用多个 Microsoft 产品，则可能会发生这种情况。

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...

    ```

    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- Ubuntu 和 Debian 系统：

    ```bash
    sudo apt-get install mdatp
    ```

    > [!NOTE]
    > 如果在设备上配置了多个 Microsoft 存储库，则可以具体说明要从哪个存储库安装包。 以下示例演示如何在此设备上配置存储库通道时从 `production` 通道 `insiders-fast` 安装包。 如果在设备上使用多个 Microsoft 产品，则可能会发生这种情况。

    ```bash
    cat /etc/apt/sources.list.d/*
    ```

    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/config/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/config/ubuntu/18.04/prod bionic main
    ```

    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a>下载载入包

从Microsoft 365 Defender门户下载载入包。

> [!IMPORTANT]
> 如果错过此步骤，执行的任何命令都将显示一条警告消息，指示产品未经许可。 此外，该`mdatp health`命令返回值 。`false`

1. 在Microsoft 365 Defender门户中，转到 **设置 >终结点>设备管理>载入**。
2. 在第一个下拉菜单中，选择 **Linux Server** 作为操作系统。 在第二个下拉菜单中，选择 **"本地脚本** "作为部署方法。
3. 选择 **"下载载入"包**。 将文件另存为WindowsDefenderATPOnboardingPackage.zip。

   :::image type="content" source="images/portal-onboarding-linux.png" alt-text="在 Microsoft 365 Defender 门户中下载载入包" lightbox="images/portal-onboarding-linux.png":::

4. 在命令提示符下，验证你是否拥有该文件，并提取存档的内容：

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```

    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

## <a name="client-configuration"></a>客户端配置

1. 将 MicrosoftDefenderATPOnboardingLinuxServer.py 复制到目标设备。

    > [!NOTE]
    > 最初，客户端设备不与组织关联， *orgId* 属性为空白。

    ```bash
    mdatp health --field org_id
    ```

2. 运行 MicrosoftDefenderATPOnboardingLinuxServer.py。

    > [!NOTE]
    > 若要运行此命令，必须根据发行版和版本在设备上安装 `python`  或 `python3` 安装此命令。 如果需要，请参阅有关在 [Linux 上安装 Python 的分步说明](https://opensource.com/article/20/4/install-python-linux)。
    
    如果运行 RHEL 8.x 或 Ubuntu 20.04 或更高版本，则需要使用 `python3`。

    ```bash
    sudo python3 MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

    对于其余发行版和版本，需要使用 `python`。
    
    ```bash
    sudo python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```
    
3. 验证设备现在是否与组织关联，并报告有效的组织标识符：

    ```bash
    mdatp health --field org_id
    ```

4. 运行以下命令检查产品的运行状况。 返回值 `1` 表示产品按预期运行：

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > 当产品首次启动时，它会下载最新的反恶意软件定义。 这可能需要几分钟的时间，具体取决于网络连接。 在此期间，上述命令返回值 `false`。 可以使用以下命令检查定义更新的状态：
    >
    > ```bash
    > mdatp health --field definitions_status
    > ```
    >
    > 请注意，在完成初始安装后，可能还需要配置代理。 请参阅 [在 Linux 上配置 Defender for Endpoint 以进行静态代理发现：安装后配置](linux-static-proxy-configuration.md#post-installation-configuration)。

5. 运行 AV 检测测试以验证设备是否已正确载入并向服务报告。 在新加入的设备上执行以下步骤：

    - 确保通过运行以下命令) `1` 启用实时保护 (表示：

        ```bash
        mdatp health --field real_time_protection_enabled
        ```
        
      如果未启用，请执行以下命令：
      
       ```bash
        mdatp config real-time-protection --value enabled
        ```

    - 打开终端窗口并执行以下命令：

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - 该文件应已由 Linux 上的 Defender for Endpoint 隔离。 使用以下命令列出所有检测到的威胁：

        ```bash
        mdatp threat list
        ```

6. 运行EDR检测测试并模拟检测，以验证设备是否已正确载入并报告给服务。 在新加入的设备上执行以下步骤：

    - 验证载入的 Linux 服务器是否显示在Microsoft 365 Defender中。 如果这是计算机的第一次载入，则最多可能需要 20 分钟才能显示。

    - 下载 [脚本文件](https://aka.ms/LinuxDIY) 并将其提取到载入的 Linux 服务器，并运行以下命令： `./mde_linux_edr_diy.sh`

    - 几分钟后，应在Microsoft 365 Defender中引发检测。

    - 查看警报详细信息、计算机时间线，并执行典型的调查步骤。

## <a name="installer-script"></a>安装程序脚本

或者，可以使用[公共GitHub存储库](https://github.com/microsoft/mdatp-xplat/)中提供的自动[安装程序 bash 脚本](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh)。
该脚本标识分发和版本，简化正确存储库的选择，设置设备以拉取最新包，并合并产品安装和载入步骤。

```bash
> ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

在此处阅读详细 [信息](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)。

## <a name="log-installation-issues"></a>日志安装问题

有关如何查找安装程序在发生错误时创建的自动生成的日志的详细信息，请参阅 [日志安装问题](linux-resources.md#log-installation-issues) 。

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>如何从Insiders-Fast迁移到生产通道

1. 卸载 Linux 上 Defender for Endpoint 的"预览体验成员-快速通道"版本。

    ```bash
    sudo yum remove mdatp
    ```

1. 在 Linux Insiders-Fast 存储库中禁用 Defender for Endpoint

    ```bash
    sudo yum repolist
    ```

    > [!NOTE]
    > 输出应显示"packages-microsoft-com-fast-prod"。

    ```bash
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ```

1. 使用"生产通道"在 Linux 上重新部署Microsoft Defender for Endpoint。

## <a name="uninstallation"></a>卸载

有关如何从客户端设备中删除 Linux 上的 Defender for Endpoint 的详细信息，请参阅 [卸载](linux-resources.md#uninstall) 。

## <a name="see-also"></a>另请参阅

- [调查代理运行状况问题](health-status.md)
