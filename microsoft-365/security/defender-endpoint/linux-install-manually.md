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
ms.openlocfilehash: 3579e9dab975d8776a53d400121d98fe119fe6cc
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438068"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="f0232-104">在 Linux 上手动部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0232-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f0232-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f0232-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0232-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0232-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f0232-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0232-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f0232-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="f0232-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f0232-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f0232-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f0232-110">本文介绍了如何在 Linux 上手动部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f0232-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="f0232-111">成功的部署需要完成以下所有任务：</span><span class="sxs-lookup"><span data-stu-id="f0232-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="f0232-112">在 Linux 上手动部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0232-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="f0232-113">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="f0232-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="f0232-114">配置 Linux 软件存储库</span><span class="sxs-lookup"><span data-stu-id="f0232-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="f0232-115">CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="f0232-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="f0232-116">SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="f0232-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="f0232-117">Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="f0232-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="f0232-118">应用程序安装</span><span class="sxs-lookup"><span data-stu-id="f0232-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="f0232-119">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="f0232-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="f0232-120">客户端配置</span><span class="sxs-lookup"><span data-stu-id="f0232-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="f0232-121">安装程序脚本</span><span class="sxs-lookup"><span data-stu-id="f0232-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="f0232-122">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="f0232-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="f0232-123">操作系统升级</span><span class="sxs-lookup"><span data-stu-id="f0232-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="f0232-124">卸载</span><span class="sxs-lookup"><span data-stu-id="f0232-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="f0232-125">先决条件和系统要求</span><span class="sxs-lookup"><span data-stu-id="f0232-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="f0232-126">在开始使用之前，请参阅 Linux 上的 [Microsoft Defender for Endpoint，](microsoft-defender-endpoint-linux.md) 了解当前软件版本的先决条件和系统要求。</span><span class="sxs-lookup"><span data-stu-id="f0232-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="f0232-127">配置 Linux 软件存储库</span><span class="sxs-lookup"><span data-stu-id="f0232-127">Configure the Linux software repository</span></span>

<span data-ttu-id="f0232-128">Linux 上的 Defender for Endpoint 可以从以下频道之一进行部署 (下面表示为 *[channel]* *) ：insiders-fast、insiders-slow* 或 *prod*。 每个通道对应于 Linux 软件存储库。</span><span class="sxs-lookup"><span data-stu-id="f0232-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="f0232-129">下面提供了配置设备以使用这些存储库之一的说明。</span><span class="sxs-lookup"><span data-stu-id="f0232-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="f0232-130">通道的选择决定了提供给你的设备的更新的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="f0232-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="f0232-131">预览 *体验成员-快* 中的设备是首先接收更新和新功能的设备，随后是预览体验成员 - *慢* ，最后是 *受支持*。</span><span class="sxs-lookup"><span data-stu-id="f0232-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="f0232-132">为了预览新功能并提供早期反馈，建议将企业中的某些设备配置为使用预览体验成员 *-快* 或预览体验成员-*慢。*</span><span class="sxs-lookup"><span data-stu-id="f0232-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="f0232-133">在初始安装后切换通道需要重新安装产品。</span><span class="sxs-lookup"><span data-stu-id="f0232-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="f0232-134">若要切换产品渠道：卸载现有程序包，将设备重新配置为使用新通道，然后按照本文档中的步骤从新位置安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="f0232-135">CentOS 和 Oracle Linux (RHEL 和) </span><span class="sxs-lookup"><span data-stu-id="f0232-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="f0232-136">如果 `yum-utils` 尚未安装，请安装：</span><span class="sxs-lookup"><span data-stu-id="f0232-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="f0232-137">记下你的分发和版本，并确定最近的条目 (按主要版本，然后在 下) 次要条目 `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="f0232-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="f0232-138">例如，RHEL 7.9 比 8 更接近 7.4。</span><span class="sxs-lookup"><span data-stu-id="f0232-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="f0232-139">在下面的命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="f0232-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0232-140">对于 Oracle Linux，将 *[distro]* 替换为"rhel"。</span><span class="sxs-lookup"><span data-stu-id="f0232-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="f0232-141">例如，如果你运行的是 CentOS 7，并且想要从 *Prod* 渠道在 Linux 上部署 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="f0232-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="f0232-142">或者，如果你想要在所选设备上探索新功能，你可能想要在 Linux 上将 Microsoft Defender for Endpoint 部署到预览 *体验成员-快频道* ：</span><span class="sxs-lookup"><span data-stu-id="f0232-142">Or if you wish to explore new features on selected devices, you might want to deploy Microsoft Defender for Endpoint on Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="f0232-143">安装 Microsoft GPG 公钥：</span><span class="sxs-lookup"><span data-stu-id="f0232-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="f0232-144">下载并启用当前启用的 yum 存储库的所有元数据：</span><span class="sxs-lookup"><span data-stu-id="f0232-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="f0232-145">SLES 和变量</span><span class="sxs-lookup"><span data-stu-id="f0232-145">SLES and variants</span></span>

- <span data-ttu-id="f0232-146">记下你的分发和版本，并按主要 (条目，然后在 下) 次要条目 `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="f0232-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="f0232-147">在下列命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="f0232-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="f0232-148">例如，如果你运行的是 SLES 12，并且想要从 *Prod* 渠道在 Linux 上部署 Microsoft Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="f0232-148">For example, if you are running SLES 12 and wish to deploy Microsoft Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="f0232-149">安装 Microsoft GPG 公钥：</span><span class="sxs-lookup"><span data-stu-id="f0232-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="f0232-150">Ubuntu 和 Debian 系统</span><span class="sxs-lookup"><span data-stu-id="f0232-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="f0232-151">如果 `curl` 尚未安装，请安装：</span><span class="sxs-lookup"><span data-stu-id="f0232-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="f0232-152">如果 `libplist-utils` 尚未安装，请安装：</span><span class="sxs-lookup"><span data-stu-id="f0232-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="f0232-153">记下你的分发和版本，并确定最近的条目 (按主要版本，然后在 下) 次要条目 `https://packages.microsoft.com/config` 。</span><span class="sxs-lookup"><span data-stu-id="f0232-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="f0232-154">在下面的命令中，将 *[distro]* 和 *[version]* 替换为已识别的信息：</span><span class="sxs-lookup"><span data-stu-id="f0232-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="f0232-155">例如，如果你运行的是 Ubuntu 18.04，并且想要从 *prod* 渠道部署适用于 Linux 的 MDE：</span><span class="sxs-lookup"><span data-stu-id="f0232-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="f0232-156">安装存储库配置：</span><span class="sxs-lookup"><span data-stu-id="f0232-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="f0232-157">例如，如果选择 *"专业频道* "：</span><span class="sxs-lookup"><span data-stu-id="f0232-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="f0232-158">安装 `gpg` 程序包（如果尚未安装）：</span><span class="sxs-lookup"><span data-stu-id="f0232-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="f0232-159">如果 `gpg` 不可用，则安装 `gnupg` 。</span><span class="sxs-lookup"><span data-stu-id="f0232-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="f0232-160">安装 Microsoft GPG 公钥：</span><span class="sxs-lookup"><span data-stu-id="f0232-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="f0232-161">如果 https 驱动程序不存在，请安装它：</span><span class="sxs-lookup"><span data-stu-id="f0232-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="f0232-162">更新存储库元数据：</span><span class="sxs-lookup"><span data-stu-id="f0232-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="f0232-163">应用程序安装</span><span class="sxs-lookup"><span data-stu-id="f0232-163">Application installation</span></span>

- <span data-ttu-id="f0232-164">CentOS 和 Oracle Linux (RHEL 和) ：</span><span class="sxs-lookup"><span data-stu-id="f0232-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="f0232-165">如果你在设备上配置了多个 Microsoft 存储库，你可以明确关于从哪个存储库安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="f0232-166">以下示例演示了如果在此设备上还配置了存储库通道，如何从该通道 `production` `insiders-fast` 安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="f0232-167">如果你正在设备上使用多个 Microsoft 产品，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="f0232-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="f0232-168">根据服务器的分发和版本，存储库别名可能不同于以下示例中的别名。</span><span class="sxs-lookup"><span data-stu-id="f0232-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

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

- <span data-ttu-id="f0232-169">SLES 和变量：</span><span class="sxs-lookup"><span data-stu-id="f0232-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="f0232-170">如果你在设备上配置了多个 Microsoft 存储库，你可以明确关于从哪个存储库安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="f0232-171">以下示例演示了如果在此设备上还配置了存储库通道，如何从该通道 `production` `insiders-fast` 安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="f0232-172">如果你正在设备上使用多个 Microsoft 产品，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="f0232-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

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

- <span data-ttu-id="f0232-173">Ubuntu 和 Debian 系统：</span><span class="sxs-lookup"><span data-stu-id="f0232-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="f0232-174">如果你在设备上配置了多个 Microsoft 存储库，你可以明确关于从哪个存储库安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="f0232-175">以下示例演示了如果在此设备上还配置了存储库通道，如何从该通道 `production` `insiders-fast` 安装程序包。</span><span class="sxs-lookup"><span data-stu-id="f0232-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="f0232-176">如果你正在设备上使用多个 Microsoft 产品，则可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="f0232-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

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

## <a name="download-the-onboarding-package"></a><span data-ttu-id="f0232-177">下载载入程序包</span><span class="sxs-lookup"><span data-stu-id="f0232-177">Download the onboarding package</span></span>

<span data-ttu-id="f0232-178">从以下网站下载载入Microsoft Defender 安全中心：</span><span class="sxs-lookup"><span data-stu-id="f0232-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="f0232-179">In Microsoft Defender 安全中心， go to **设置 > Device Management > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="f0232-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="f0232-180">在"第一个"下拉菜单中，选择 **"Linux Server"** 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="f0232-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="f0232-181">In the second drop-down menu， select **Local Script (for up to 10 devices)** as the deployment method.</span><span class="sxs-lookup"><span data-stu-id="f0232-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="f0232-182">选择 **下载载入程序包**。</span><span class="sxs-lookup"><span data-stu-id="f0232-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="f0232-183">将文件另存为WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="f0232-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 安全中心屏幕截图](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="f0232-185">在命令提示符下，验证您是否具有该文件。</span><span class="sxs-lookup"><span data-stu-id="f0232-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="f0232-186">提取存档的内容：</span><span class="sxs-lookup"><span data-stu-id="f0232-186">Extract the contents of the archive:</span></span>

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


## <a name="client-configuration"></a><span data-ttu-id="f0232-187">客户端配置</span><span class="sxs-lookup"><span data-stu-id="f0232-187">Client configuration</span></span>

1. <span data-ttu-id="f0232-188">将 MicrosoftDefenderATPOnboardingLinuxServer.py 复制到目标设备。</span><span class="sxs-lookup"><span data-stu-id="f0232-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="f0232-189">最初，客户端设备不与组织关联。</span><span class="sxs-lookup"><span data-stu-id="f0232-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="f0232-190">请注意 *，orgId* 属性为空：</span><span class="sxs-lookup"><span data-stu-id="f0232-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="f0232-191">运行 MicrosoftDefenderATPOnboardingLinuxServer.py。</span><span class="sxs-lookup"><span data-stu-id="f0232-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py.</span></span> 
   
    >[!NOTE]
    ><span data-ttu-id="f0232-192">若要运行此命令，你必须 `python` 已安装在设备上。</span><span class="sxs-lookup"><span data-stu-id="f0232-192">To run this command, you must have `python` installed on the device.</span></span> <span data-ttu-id="f0232-193">如果运行的是 RHEL 8.x 或 Ubuntu 20.04 或更高版本，则需要使用 Python 3 而不是 Python。</span><span class="sxs-lookup"><span data-stu-id="f0232-193">If you're running RHEL 8.x or Ubuntu 20.04 or higher, then you will need to use Python 3 instead of Python.</span></span>



    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="f0232-194">验证设备现在是否与组织关联，并报告有效的组织标识符：</span><span class="sxs-lookup"><span data-stu-id="f0232-194">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="f0232-195">完成安装后几分钟，可以通过运行以下命令来查看状态。</span><span class="sxs-lookup"><span data-stu-id="f0232-195">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="f0232-196">返回值 表示 `1` 产品正在正常运行：</span><span class="sxs-lookup"><span data-stu-id="f0232-196">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="f0232-197">当产品首次启动时，它将下载最新的反恶意软件定义。</span><span class="sxs-lookup"><span data-stu-id="f0232-197">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="f0232-198">根据您的 Internet 连接，这最多可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="f0232-198">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="f0232-199">在此期间，上述命令将返回 的值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="f0232-199">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="f0232-200">可以使用以下命令检查定义更新的状态：</span><span class="sxs-lookup"><span data-stu-id="f0232-200">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="f0232-201">请注意，完成初始安装后，可能还需要配置代理。</span><span class="sxs-lookup"><span data-stu-id="f0232-201">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="f0232-202">请参阅 [在 Linux 上为终结点配置静态代理发现：安装后配置](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)。</span><span class="sxs-lookup"><span data-stu-id="f0232-202">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="f0232-203">运行检测测试，验证设备是否正确载入并报告给服务。</span><span class="sxs-lookup"><span data-stu-id="f0232-203">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="f0232-204">对新载入的设备执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f0232-204">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="f0232-205">确保实时保护 (由运行以下命令或命令的结果 `1`) ：</span><span class="sxs-lookup"><span data-stu-id="f0232-205">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="f0232-206">打开"终端"窗口。</span><span class="sxs-lookup"><span data-stu-id="f0232-206">Open a Terminal window.</span></span> <span data-ttu-id="f0232-207">复制并执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f0232-207">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="f0232-208">该文件应该已由 Linux 上的 Defender for Endpoint 隔离。</span><span class="sxs-lookup"><span data-stu-id="f0232-208">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="f0232-209">使用以下命令列出所有检测到的威胁：</span><span class="sxs-lookup"><span data-stu-id="f0232-209">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a><span data-ttu-id="f0232-210">通过模拟攻击体验 Linux 终结点 (EDR) 响应和响应功能</span><span class="sxs-lookup"><span data-stu-id="f0232-210">Experience Linux endpoint detection and response (EDR) capabilities with simulated attacks</span></span>

<span data-ttu-id="f0232-211">若要测试适用于 Linux EDR的功能，请按照以下步骤在 Linux 服务器上模拟检测并调查这种情况。</span><span class="sxs-lookup"><span data-stu-id="f0232-211">To test out the functionalities of EDR for Linux, follow the steps below to simulate a detection on your Linux server and investigate the case.</span></span> 

1.  <span data-ttu-id="f0232-212">验证已载入的 Linux 服务器是否Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="f0232-212">Verify that the onboarded Linux server appears in Microsoft Defender Security Center.</span></span> <span data-ttu-id="f0232-213">如果这是计算机首次载入，可能需要最多 20 分钟才会显示。</span><span class="sxs-lookup"><span data-stu-id="f0232-213">If this is the first onboarding of the machine, it can take up to 20 minutes until it appears.</span></span> 

2.  <span data-ttu-id="f0232-214">将脚本文件 [下载并](https://aka.ms/LinuxDIY) 解压缩到载入的 Linux 服务器并运行以下命令： `./mde_linux_edr_diy.sh`</span><span class="sxs-lookup"><span data-stu-id="f0232-214">Download and extract the [script file](https://aka.ms/LinuxDIY) to an onboarded Linux server and run the following command: `./mde_linux_edr_diy.sh`</span></span>

3.  <span data-ttu-id="f0232-215">几分钟后，应在测试中引发Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="f0232-215">After a few minutes, a detection should be raised in Microsoft Defender Security Center.</span></span>

4.  <span data-ttu-id="f0232-216">查看警报详细信息、计算机时间线，并执行典型的调查步骤。</span><span class="sxs-lookup"><span data-stu-id="f0232-216">Look at the alert details, machine timeline, and perform your typical investigation steps.</span></span>




## <a name="installer-script"></a><span data-ttu-id="f0232-217">安装程序脚本</span><span class="sxs-lookup"><span data-stu-id="f0232-217">Installer script</span></span>

<span data-ttu-id="f0232-218">或者，您可以使用公共数据库存储库中提供的自动安装程序[bash](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) [GitHub脚本](https://github.com/microsoft/mdatp-xplat/)。</span><span class="sxs-lookup"><span data-stu-id="f0232-218">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="f0232-219">该脚本标识分发和版本，并设置设备以拉取最新的程序包并安装它。</span><span class="sxs-lookup"><span data-stu-id="f0232-219">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="f0232-220">您还可以使用提供的脚本载入。</span><span class="sxs-lookup"><span data-stu-id="f0232-220">You can also onboard with a provided script.</span></span>

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

<span data-ttu-id="f0232-221">在此处阅读[更多。](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)</span><span class="sxs-lookup"><span data-stu-id="f0232-221">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="f0232-222">记录安装问题</span><span class="sxs-lookup"><span data-stu-id="f0232-222">Log installation issues</span></span>

<span data-ttu-id="f0232-223">请参阅 [日志](linux-resources.md#log-installation-issues) 安装问题，详细了解如何在发生错误时查找安装程序创建的自动生成的日志。</span><span class="sxs-lookup"><span data-stu-id="f0232-223">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="f0232-224">操作系统升级</span><span class="sxs-lookup"><span data-stu-id="f0232-224">Operating system upgrades</span></span>

<span data-ttu-id="f0232-225">将操作系统升级到新的主要版本时，必须先卸载 Linux 上的 Defender for Endpoint，安装升级，最后在设备上重新配置 Linux 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f0232-225">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="f0232-226">如何从生产Insiders-Fast迁移到生产渠道</span><span class="sxs-lookup"><span data-stu-id="f0232-226">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="f0232-227">在 Linux 上卸载 Defender for Endpoint 的"Insiders-Fast channel"版本。</span><span class="sxs-lookup"><span data-stu-id="f0232-227">Uninstall the “Insiders-Fast channel” version of Defender for Endpoint on Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="f0232-228">在 Linux 上禁用 Defender for Endpoint Insiders-Fast存储库  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="f0232-228">Disable the Defender for Endpoint on Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0232-229">输出应显示"packages-microsoft-com-fast-prod"。</span><span class="sxs-lookup"><span data-stu-id="f0232-229">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="f0232-230">使用"生产通道"重新部署适用于 Linux 的 MDE。</span><span class="sxs-lookup"><span data-stu-id="f0232-230">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="f0232-231">卸载</span><span class="sxs-lookup"><span data-stu-id="f0232-231">Uninstallation</span></span>

<span data-ttu-id="f0232-232">请参阅 [卸载](linux-resources.md#uninstall) ，了解有关如何在 Linux 上从客户端设备中删除 Defender for Endpoint 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0232-232">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0232-233">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0232-233">See also</span></span>
- [<span data-ttu-id="f0232-234">调查代理运行状况问题</span><span class="sxs-lookup"><span data-stu-id="f0232-234">Investigate agent health issues</span></span>](health-status.md)
