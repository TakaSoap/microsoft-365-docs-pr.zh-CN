---
title: 在 Linux 上手动部署 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何从命令行手动在 Linux 上部署 Microsoft Defender for Endpoint。
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
ms.openlocfilehash: c13138f3d80a95dbda3a899507f662c081831d94
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259675"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="386fb-104">在 Linux 上手动部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="386fb-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="386fb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="386fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="386fb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="386fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="386fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="386fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="386fb-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="386fb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="386fb-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="386fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="386fb-110">本文介绍了如何在 Linux 上手动部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="386fb-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="386fb-111">成功的部署需要完成以下所有任务：</span><span class="sxs-lookup"><span data-stu-id="386fb-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="386fb-112">在 Linux 上手动部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="386fb-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="386fb-113">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="386fb-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="386fb-114">配置 Linux 软件存储库</span><span class="sxs-lookup"><span data-stu-id="386fb-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="386fb-115">CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="386fb-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="386fb-116">SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="386fb-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="386fb-117">Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="386fb-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="386fb-118">应用程序安装</span><span class="sxs-lookup"><span data-stu-id="386fb-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="386fb-119">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="386fb-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="386fb-120">客户端配置</span><span class="sxs-lookup"><span data-stu-id="386fb-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="386fb-121">安装程序脚本</span><span class="sxs-lookup"><span data-stu-id="386fb-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="386fb-122">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="386fb-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="386fb-123">操作系统升级</span><span class="sxs-lookup"><span data-stu-id="386fb-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="386fb-124">卸载</span><span class="sxs-lookup"><span data-stu-id="386fb-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="386fb-125">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="386fb-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="386fb-126">在开始使用之前，请参阅 Linux 上的 [Microsoft Defender for Endpoint，](microsoft-defender-endpoint-linux.md) 了解当前软件版本的先决条件和系统要求。</span><span class="sxs-lookup"><span data-stu-id="386fb-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="386fb-127">配置 Linux 软件存储库</span><span class="sxs-lookup"><span data-stu-id="386fb-127">Configure the Linux software repository</span></span>

<span data-ttu-id="386fb-128">Linux 上的 Defender for Endpoint 可以从以下频道之一进行部署 (下面表示为 *[channel]* *) ：insiders-fast、insiders-slow* 或 *prod*。 每个通道对应于 Linux 软件存储库。</span><span class="sxs-lookup"><span data-stu-id="386fb-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="386fb-129">下面提供了配置设备以使用这些存储库之一的说明。</span><span class="sxs-lookup"><span data-stu-id="386fb-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="386fb-130">通道的选择决定了提供给你的设备的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="386fb-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="386fb-131">预览 *体验成员-快* 中的设备是首先接收更新和新功能的设备，随后是预览体验成员 - *慢* ，最后是 *受支持*。</span><span class="sxs-lookup"><span data-stu-id="386fb-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="386fb-132">为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用预览体验成员 *-快* 或预览体验成员-*慢。*</span><span class="sxs-lookup"><span data-stu-id="386fb-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="386fb-133">在初始安装后切换通道需要重新安装产品。</span><span class="sxs-lookup"><span data-stu-id="386fb-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="386fb-134">若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="386fb-135">CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="386fb-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="386fb-136">如果 `yum-utils` 尚未安装，请安装：</span><span class="sxs-lookup"><span data-stu-id="386fb-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="386fb-137">记下你的分发和版本，并确定最近的条目 (按主要版本，然后在 下) 次要条目 `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="386fb-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="386fb-138">例如，RHEL 7.9 比 8 更接近 7.4。</span><span class="sxs-lookup"><span data-stu-id="386fb-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="386fb-139">在下面的命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="386fb-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="386fb-140">对于 Oracle Linux，将 *[distro]* 替换为"rhel"。</span><span class="sxs-lookup"><span data-stu-id="386fb-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="386fb-141">例如，如果你运行的是 CentOS 7，并且想要从 *Prod* 渠道在 Linux 上部署 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="386fb-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="386fb-142">或者，如果你想要在所选设备上探索新功能，你可能希望将适用于 Linux 的 MDE 部署到 *预览体验成员-快频道* ：</span><span class="sxs-lookup"><span data-stu-id="386fb-142">Or if you wish to explore new features on selected devices, you might want to deploy MDE for Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="386fb-143">安装 Microsoft GPG 公钥：</span><span class="sxs-lookup"><span data-stu-id="386fb-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="386fb-144">下载并启用当前启用的 yum 存储库的所有元数据：</span><span class="sxs-lookup"><span data-stu-id="386fb-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="386fb-145">SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="386fb-145">SLES and variants</span></span>

- <span data-ttu-id="386fb-146">记下你的分发和版本，并按主要 (条目，然后在 下) 次要条目 `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="386fb-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="386fb-147">在下列命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="386fb-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="386fb-148">例如，如果你运行的是 SLES 12，并且想要从专业渠道部署适用于 Linux的 MDE：</span><span class="sxs-lookup"><span data-stu-id="386fb-148">For example, if you are running SLES 12 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="386fb-149">安装 Microsoft GPG 公钥：</span><span class="sxs-lookup"><span data-stu-id="386fb-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="386fb-150">Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="386fb-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="386fb-151">如果 `curl` 尚未安装，请安装：</span><span class="sxs-lookup"><span data-stu-id="386fb-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="386fb-152">如果 `libplist-utils` 尚未安装，请安装：</span><span class="sxs-lookup"><span data-stu-id="386fb-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="386fb-153">记下你的分发和版本，并确定最近的条目 (按主要版本，然后在 下) 次要条目 `https://packages.microsoft.com/config` 。</span><span class="sxs-lookup"><span data-stu-id="386fb-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="386fb-154">在下面的命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="386fb-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="386fb-155">例如，如果你运行的是 Ubuntu 18.04，并且想要从 *prod* 渠道部署适用于 Linux 的 MDE：</span><span class="sxs-lookup"><span data-stu-id="386fb-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="386fb-156">安装存储库配置：</span><span class="sxs-lookup"><span data-stu-id="386fb-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="386fb-157">例如，如果选择 *"专业频道* "：</span><span class="sxs-lookup"><span data-stu-id="386fb-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="386fb-158">安装 `gpg` 程序包（如果尚未安装）：</span><span class="sxs-lookup"><span data-stu-id="386fb-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="386fb-159">如果 `gpg` 不可用，则安装 `gnupg` 。</span><span class="sxs-lookup"><span data-stu-id="386fb-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="386fb-160">安装 Microsoft GPG 公钥：</span><span class="sxs-lookup"><span data-stu-id="386fb-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="386fb-161">如果 https 驱动程序不存在，请安装它：</span><span class="sxs-lookup"><span data-stu-id="386fb-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="386fb-162">更新存储库元数据：</span><span class="sxs-lookup"><span data-stu-id="386fb-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="386fb-163">应用程序安装</span><span class="sxs-lookup"><span data-stu-id="386fb-163">Application installation</span></span>

- <span data-ttu-id="386fb-164">CentOS 和 Oracle Linux (RHEL 和) ：</span><span class="sxs-lookup"><span data-stu-id="386fb-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="386fb-165">如果你在设备上配置了多个 Microsoft 存储库，你可以明确关于从哪个存储库安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="386fb-166">以下示例演示了如果在此设备上还配置了存储库通道，如何从该通道 `production` `insiders-fast` 安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="386fb-167">如果你正在设备上使用多个 Microsoft 产品，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="386fb-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="386fb-168">根据服务器的分发和版本，存储库别名可能不同于以下示例中的别名。</span><span class="sxs-lookup"><span data-stu-id="386fb-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

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

- <span data-ttu-id="386fb-169">SLES 和变量：</span><span class="sxs-lookup"><span data-stu-id="386fb-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="386fb-170">如果你在设备上配置了多个 Microsoft 存储库，你可以明确关于从哪个存储库安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="386fb-171">以下示例演示了如果在此设备上还配置了存储库通道，如何从该通道 `production` `insiders-fast` 安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="386fb-172">如果你正在设备上使用多个 Microsoft 产品，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="386fb-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

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

- <span data-ttu-id="386fb-173">Ubuntu 和 Debian 系统：</span><span class="sxs-lookup"><span data-stu-id="386fb-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="386fb-174">如果你在设备上配置了多个 Microsoft 存储库，你可以明确关于从哪个存储库安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="386fb-175">以下示例演示了如果在此设备上还配置了存储库通道，如何从该通道 `production` `insiders-fast` 安装程序包。</span><span class="sxs-lookup"><span data-stu-id="386fb-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="386fb-176">如果你正在设备上使用多个 Microsoft 产品，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="386fb-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="386fb-177">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="386fb-177">Download the onboarding package</span></span>

<span data-ttu-id="386fb-178">从以下网站下载载入Microsoft Defender 安全中心：</span><span class="sxs-lookup"><span data-stu-id="386fb-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="386fb-179">In Microsoft Defender 安全中心， go to **设置 > Device Management > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="386fb-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="386fb-180">在"第一个"下拉菜单中，选择 **"Linux Server"** 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="386fb-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="386fb-181">In the second drop-down menu， select **Local Script (for up to 10 devices)** as the deployment method.</span><span class="sxs-lookup"><span data-stu-id="386fb-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="386fb-182">选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="386fb-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="386fb-183">将文件另存为WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="386fb-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 安全中心屏幕截图](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="386fb-185">在命令提示符下，验证您是否具有该文件。</span><span class="sxs-lookup"><span data-stu-id="386fb-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="386fb-186">提取存档的内容：</span><span class="sxs-lookup"><span data-stu-id="386fb-186">Extract the contents of the archive:</span></span>

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


## <a name="client-configuration"></a><span data-ttu-id="386fb-187">客户端配置</span><span class="sxs-lookup"><span data-stu-id="386fb-187">Client configuration</span></span>

1. <span data-ttu-id="386fb-188">将 MicrosoftDefenderATPOnboardingLinuxServer.py 复制到目标设备。</span><span class="sxs-lookup"><span data-stu-id="386fb-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="386fb-189">最初，客户端设备不与组织关联。</span><span class="sxs-lookup"><span data-stu-id="386fb-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="386fb-190">请注意 *，orgId* 属性为空：</span><span class="sxs-lookup"><span data-stu-id="386fb-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="386fb-191">运行 MicrosoftDefenderATPOnboardingLinuxServer.py，请注意，为了运行此命令，你必须 `python` 已安装在设备上：</span><span class="sxs-lookup"><span data-stu-id="386fb-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py, and note that, in order to run this command, you must have `python` installed on the device:</span></span>

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="386fb-192">验证设备现在是否与组织关联，并报告有效的组织标识符：</span><span class="sxs-lookup"><span data-stu-id="386fb-192">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="386fb-193">完成安装后几分钟，可以通过运行以下命令来查看状态。</span><span class="sxs-lookup"><span data-stu-id="386fb-193">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="386fb-194">返回值 表示 `1` 产品正在正常运行：</span><span class="sxs-lookup"><span data-stu-id="386fb-194">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="386fb-195">当产品首次启动时，它将下载最新的反恶意软件定义。</span><span class="sxs-lookup"><span data-stu-id="386fb-195">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="386fb-196">根据您的 Internet 连接，这最多可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="386fb-196">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="386fb-197">在此期间，上述命令将返回 的值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="386fb-197">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="386fb-198">可以使用以下命令检查定义更新的状态：</span><span class="sxs-lookup"><span data-stu-id="386fb-198">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="386fb-199">请注意，完成初始安装后，可能还需要配置代理。</span><span class="sxs-lookup"><span data-stu-id="386fb-199">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="386fb-200">请参阅 [在 Linux 上为终结点配置静态代理发现：安装后配置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)。</span><span class="sxs-lookup"><span data-stu-id="386fb-200">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="386fb-201">运行检测测试，验证设备是否正确载入并报告给服务。</span><span class="sxs-lookup"><span data-stu-id="386fb-201">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="386fb-202">对新载入的设备执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="386fb-202">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="386fb-203">确保实时保护 (由运行以下命令或命令的结果 `1`) ：</span><span class="sxs-lookup"><span data-stu-id="386fb-203">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="386fb-204">打开"终端"窗口。</span><span class="sxs-lookup"><span data-stu-id="386fb-204">Open a Terminal window.</span></span> <span data-ttu-id="386fb-205">复制并执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="386fb-205">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="386fb-206">该文件应该已由 Linux 上的 Defender for Endpoint 隔离。</span><span class="sxs-lookup"><span data-stu-id="386fb-206">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="386fb-207">使用以下命令列出所有检测到的威胁：</span><span class="sxs-lookup"><span data-stu-id="386fb-207">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a><span data-ttu-id="386fb-208">安装程序脚本</span><span class="sxs-lookup"><span data-stu-id="386fb-208">Installer script</span></span>

<span data-ttu-id="386fb-209">或者，您可以使用公共数据库存储库中提供的自动安装程序[bash](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) [GitHub脚本](https://github.com/microsoft/mdatp-xplat/)。</span><span class="sxs-lookup"><span data-stu-id="386fb-209">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="386fb-210">该脚本标识分发和版本，并设置设备以拉取最新的程序包并安装它。</span><span class="sxs-lookup"><span data-stu-id="386fb-210">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="386fb-211">您还可以使用提供的脚本载入。</span><span class="sxs-lookup"><span data-stu-id="386fb-211">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
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

<span data-ttu-id="386fb-212">在此处阅读[更多。](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)</span><span class="sxs-lookup"><span data-stu-id="386fb-212">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="386fb-213">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="386fb-213">Log installation issues</span></span>

<span data-ttu-id="386fb-214">请参阅 [日志](linux-resources.md#log-installation-issues) 安装问题，详细了解如何在发生错误时查找安装程序创建的自动生成的日志。</span><span class="sxs-lookup"><span data-stu-id="386fb-214">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="386fb-215">操作系统升级</span><span class="sxs-lookup"><span data-stu-id="386fb-215">Operating system upgrades</span></span>

<span data-ttu-id="386fb-216">将操作系统升级到新的主要版本时，必须先卸载 Linux 上的 Defender for Endpoint，安装升级，最后在设备上重新配置 Linux 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="386fb-216">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="386fb-217">如何从生产Insiders-Fast迁移到生产渠道</span><span class="sxs-lookup"><span data-stu-id="386fb-217">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="386fb-218">卸载适用于 Linux 的 MDE 的"Insiders-Fast channel"版本。</span><span class="sxs-lookup"><span data-stu-id="386fb-218">Uninstall the “Insiders-Fast channel” version of MDE for Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="386fb-219">禁用适用于 Linux 的 MDE Insiders-Fast存储库  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="386fb-219">Disable the MDE for Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="386fb-220">输出应显示"packages-microsoft-com-fast-prod"。</span><span class="sxs-lookup"><span data-stu-id="386fb-220">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="386fb-221">使用"生产通道"重新部署适用于 Linux 的 MDE。</span><span class="sxs-lookup"><span data-stu-id="386fb-221">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="386fb-222">卸载</span><span class="sxs-lookup"><span data-stu-id="386fb-222">Uninstallation</span></span>

<span data-ttu-id="386fb-223">请参阅 [卸载](linux-resources.md#uninstall) ，了解有关如何在 Linux 上从客户端设备中删除 Defender for Endpoint 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="386fb-223">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>
