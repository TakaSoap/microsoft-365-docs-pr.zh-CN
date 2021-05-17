---
title: 使用部署在 Linux 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何使用安装程序在 Linux 上部署 Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d54732134e91b87b2639634c365556beda5312b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934569"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a><span data-ttu-id="6e0fb-104">使用部署在 Linux 上的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6e0fb-104">Deploy Microsoft Defender for Endpoint on Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6e0fb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6e0fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="6e0fb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6e0fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6e0fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e0fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6e0fb-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6e0fb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6e0fb-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6e0fb-110">本文介绍如何使用部署在 Linux 上使用部署 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-110">This article describes how to deploy Defender for Endpoint on Linux using Puppet.</span></span> <span data-ttu-id="6e0fb-111">成功的部署需要完成以下所有任务：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="6e0fb-112">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="6e0fb-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="6e0fb-113">创建清单</span><span class="sxs-lookup"><span data-stu-id="6e0fb-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="6e0fb-114">部署</span><span class="sxs-lookup"><span data-stu-id="6e0fb-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="6e0fb-115">检查载入状态</span><span class="sxs-lookup"><span data-stu-id="6e0fb-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="6e0fb-116">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="6e0fb-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="6e0fb-117">有关当前软件版本的先决条件和系统要求的说明，请参阅 Linux 页面上的 [Defender for Endpoint 主页面](microsoft-defender-endpoint-linux.md)。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="6e0fb-118">此外，对于部署部署，你需要熟悉管理中心任务、配置了管理中心并知道如何部署程序包。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="6e0fb-119">安装工具有许多方法可以完成同一任务。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="6e0fb-120">这些说明假定受支持的"开发工具"模块可用， *例如，有助于* 部署程序包。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="6e0fb-121">您的组织可能使用不同的工作流。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="6e0fb-122">有关详细信息， [请参阅"百分百](https://puppet.com/docs) "文档。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="6e0fb-123">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="6e0fb-123">Download the onboarding package</span></span>

<span data-ttu-id="6e0fb-124">从以下网站下载载入Microsoft Defender 安全中心：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="6e0fb-125">In Microsoft Defender 安全中心， go to **设置 > Device Management > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="6e0fb-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="6e0fb-126">在"第一个"下拉菜单中，选择 **"Linux Server"** 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="6e0fb-127">In the second drop-down menu， select **Your preferred Linux configuration management tool** as the deployment method.</span><span class="sxs-lookup"><span data-stu-id="6e0fb-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="6e0fb-128">选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="6e0fb-129">将文件另存为WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 安全中心屏幕截图](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="6e0fb-131">在命令提示符下，验证您是否具有该文件。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="6e0fb-132">提取存档的内容。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="6e0fb-133">创建清单</span><span class="sxs-lookup"><span data-stu-id="6e0fb-133">Create a Puppet manifest</span></span>

<span data-ttu-id="6e0fb-134">你需要创建一个清单，用于将 Linux 上的 Defender for Endpoint 部署到由开发工具服务器管理的设备上。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-134">You need to create a Puppet manifest for deploying Defender for Endpoint on Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="6e0fb-135">此示例使用了从 *labs中* 提供的 apt 和 *yumrepo* 模块，并假定模块已安装在了您的开发工具服务器上。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="6e0fb-136">在安装 *Install_mdatp模块文件夹* 下 *install_mdatp/* 文件和清单文件夹。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="6e0fb-137">此文件夹通常位于安装服务器 */etc/moduleslabs/code/environments/production/modules* 中。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="6e0fb-138">将mdatp_onboard.js上的文件复制到 *"install_mdatp/files"* 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="6e0fb-139">创建 *init.pp*</span><span class="sxs-lookup"><span data-stu-id="6e0fb-139">Create an *init.pp*</span></span> <span data-ttu-id="6e0fb-140">包含部署说明的文件：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-140">file that contains the deployment instructions:</span></span>

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

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="6e0fb-141">`install_mdatp/manifests/init.pp` 的内容</span><span class="sxs-lookup"><span data-stu-id="6e0fb-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="6e0fb-142">Linux 上的 Defender for Endpoint 可以从以下频道之一进行部署 (下面表示为 *[channel]* *) ：insiders-fast、insiders-slow* 或 *prod*。 每个通道对应于 Linux 软件存储库。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-142">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="6e0fb-143">通道的选择决定了提供给你的设备的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="6e0fb-144">预览 *体验成员-快* 中的设备是首先接收更新和新功能的设备，随后是预览体验成员 - *慢* ，最后是 *受支持*。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="6e0fb-145">为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用预览体验成员 *-快* 或预览体验成员-*慢。*</span><span class="sxs-lookup"><span data-stu-id="6e0fb-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="6e0fb-146">在初始安装后切换通道需要重新安装产品。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="6e0fb-147">若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="6e0fb-148">记下分发和版本，并确定 其最接近的 `https://packages.microsoft.com/config/` 条目。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="6e0fb-149">在下面的命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="6e0fb-150">对于 RedHat、Oracle EL 和 CentOS 8，将 *[distro]* 替换为"rhel"。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
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

## <a name="deployment"></a><span data-ttu-id="6e0fb-151">部署</span><span class="sxs-lookup"><span data-stu-id="6e0fb-151">Deployment</span></span>

<span data-ttu-id="6e0fb-152">在 site.pp 中包括上述清单</span><span class="sxs-lookup"><span data-stu-id="6e0fb-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="6e0fb-153">文件：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="6e0fb-154">注册的代理设备定期轮询部署服务器，并一经检测到，立即安装新的配置文件和策略。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="6e0fb-155">监视部署部署</span><span class="sxs-lookup"><span data-stu-id="6e0fb-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="6e0fb-156">在代理设备上，还可以运行以下程序检查载入状态：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="6e0fb-157">**许可**：这可确认设备已绑定到你的组织。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="6e0fb-158">**orgId：** 这是适用于终结点的 Defender 组织标识符。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="6e0fb-159">检查载入状态</span><span class="sxs-lookup"><span data-stu-id="6e0fb-159">Check onboarding status</span></span>

<span data-ttu-id="6e0fb-160">可以通过创建脚本来检查设备是否正确载入。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="6e0fb-161">例如，以下脚本检查已注册设备是否载入状态：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="6e0fb-162">如果产品已载入并正常工作，则上述命令 `1` 将输出。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e0fb-163">当产品首次启动时，它将下载最新的反恶意软件定义。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="6e0fb-164">根据您的 Internet 连接，这最多可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="6e0fb-165">在此期间，上述命令将返回 的值 `0` 。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="6e0fb-166">如果产品运行不正常， (检查退出代码) `echo $?` 指示问题：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="6e0fb-167">1（如果设备尚未载入）。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="6e0fb-168">3（如果无法建立与守护程序的连接）。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="6e0fb-169">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="6e0fb-169">Log installation issues</span></span>

 <span data-ttu-id="6e0fb-170">若要详细了解如何在发生错误时查找安装程序创建的自动生成的日志，请参阅日志 [安装问题](linux-resources.md#log-installation-issues)。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="6e0fb-171">操作系统升级</span><span class="sxs-lookup"><span data-stu-id="6e0fb-171">Operating system upgrades</span></span>

<span data-ttu-id="6e0fb-172">将操作系统升级到新的主要版本时，必须先卸载 Linux 上的 Defender for Endpoint，安装升级，最后在设备上重新配置 Linux 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="6e0fb-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="6e0fb-173">卸载</span><span class="sxs-lookup"><span data-stu-id="6e0fb-173">Uninstallation</span></span>

<span data-ttu-id="6e0fb-174">创建一个 *remove_mdatp，install_mdatp*  *init.pp* 中的以下内容类似的模块</span><span class="sxs-lookup"><span data-stu-id="6e0fb-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="6e0fb-175">文件：</span><span class="sxs-lookup"><span data-stu-id="6e0fb-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
