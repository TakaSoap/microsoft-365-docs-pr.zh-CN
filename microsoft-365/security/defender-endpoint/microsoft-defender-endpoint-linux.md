---
title: Microsoft Defender for Endpoint for Linux
ms.reviewer: ''
description: 介绍如何安装和使用适用于 Linux 的 Microsoft Defender ATP。
keywords: microsoft， defender， atp， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cc2f5be700395f6d88c05481d74501f4d9d92b76
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500674"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="eb588-104">Microsoft Defender for Endpoint for Linux</span><span class="sxs-lookup"><span data-stu-id="eb588-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eb588-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eb588-105">**Applies to:**</span></span>
- [<span data-ttu-id="eb588-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb588-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eb588-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb588-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eb588-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="eb588-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eb588-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="eb588-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="eb588-110">本主题介绍如何安装、配置、更新和使用适用于 Linux 的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="eb588-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="eb588-111">将其他第三方终结点保护产品与 Microsoft Defender for Endpoint for Linux 一起运行可能会导致性能问题和不可预知的副作用。</span><span class="sxs-lookup"><span data-stu-id="eb588-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="eb588-112">如果非 Microsoft 终结点保护在你的环境中是绝对要求，在将防病毒功能配置为在被动模式下运行后，你仍然可以安全地利用适用于 Linux EDR 的 Defender for [Endpoint 功能](linux-preferences.md#enable--disable-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="eb588-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="eb588-113">如何安装适用于 Linux 的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb588-113">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="eb588-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="eb588-114">Prerequisites</span></span>

- <span data-ttu-id="eb588-115">访问 Microsoft Defender 安全中心门户</span><span class="sxs-lookup"><span data-stu-id="eb588-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="eb588-116">使用系统 [系统管理器的](https://systemd.io/) Linux 分发</span><span class="sxs-lookup"><span data-stu-id="eb588-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="eb588-117">Linux 和 BASH 脚本的初学者级体验</span><span class="sxs-lookup"><span data-stu-id="eb588-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="eb588-118">手动部署时，设备上 (管理权限) </span><span class="sxs-lookup"><span data-stu-id="eb588-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="eb588-119">安装说明</span><span class="sxs-lookup"><span data-stu-id="eb588-119">Installation instructions</span></span>

<span data-ttu-id="eb588-120">有几种方法和部署工具可用于安装和配置 Microsoft Defender for Endpoint for Linux。</span><span class="sxs-lookup"><span data-stu-id="eb588-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="eb588-121">通常，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb588-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="eb588-122">确保你拥有适用于终结点的 Microsoft Defender 订阅，并且你有权访问 [适用于终结点](microsoft-defender-security-center.md)的 Microsoft Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="eb588-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="eb588-123">使用下列部署方法之一部署适用于 Linux 的 Microsoft Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="eb588-123">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="eb588-124">命令行工具：</span><span class="sxs-lookup"><span data-stu-id="eb588-124">The command-line tool:</span></span>
    - [<span data-ttu-id="eb588-125">手动部署</span><span class="sxs-lookup"><span data-stu-id="eb588-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="eb588-126">第三方管理工具：</span><span class="sxs-lookup"><span data-stu-id="eb588-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="eb588-127">使用配置管理工具进行部署</span><span class="sxs-lookup"><span data-stu-id="eb588-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="eb588-128">使用可配置管理工具进行部署</span><span class="sxs-lookup"><span data-stu-id="eb588-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="eb588-129">如果遇到任何安装失败，请参阅 Microsoft [Defender for Endpoint for Linux](linux-support-install.md)中的安装失败疑难解答。</span><span class="sxs-lookup"><span data-stu-id="eb588-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="eb588-130">系统要求</span><span class="sxs-lookup"><span data-stu-id="eb588-130">System requirements</span></span>

- <span data-ttu-id="eb588-131">支持的 Linux 服务器分发和版本：</span><span class="sxs-lookup"><span data-stu-id="eb588-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="eb588-132">Red Hat Enterprise Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb588-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="eb588-133">CentOS 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb588-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="eb588-134">Ubuntu 16.04 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="eb588-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="eb588-135">Debian 9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb588-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="eb588-136">SUSE Linux Enterprise Server 12 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb588-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="eb588-137">Oracle Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="eb588-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="eb588-138">最低内核版本 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="eb588-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="eb588-139">`fanotify`必须启用内核选项</span><span class="sxs-lookup"><span data-stu-id="eb588-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="eb588-140">不支持将适用于 Linux 的 Defender for Endpoint 与其他 `fanotify` 基于的安全解决方案并行运行。</span><span class="sxs-lookup"><span data-stu-id="eb588-140">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="eb588-141">它可能会导致不可预知的结果，包括挂起操作系统。</span><span class="sxs-lookup"><span data-stu-id="eb588-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="eb588-142">磁盘空间：1GB</span><span class="sxs-lookup"><span data-stu-id="eb588-142">Disk space: 1GB</span></span>
- <span data-ttu-id="eb588-143">/opt/microsoft/mdatp/sbin/wdavdaemon 需要可执行权限。</span><span class="sxs-lookup"><span data-stu-id="eb588-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="eb588-144">有关详细信息，请参阅解决适用于 Linux 的 Microsoft Defender ATP 的安装问题中的"确保守护程序具有可执行[权限"。](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="eb588-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="eb588-145">内存：1GB</span><span class="sxs-lookup"><span data-stu-id="eb588-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="eb588-146">请确保 /var 中具有可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="eb588-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="eb588-147">解决方案当前为以下文件系统类型提供实时保护：</span><span class="sxs-lookup"><span data-stu-id="eb588-147">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="eb588-148">启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。</span><span class="sxs-lookup"><span data-stu-id="eb588-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="eb588-149">必须 `auditd` () 审核框架。</span><span class="sxs-lookup"><span data-stu-id="eb588-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="eb588-150">添加到 的规则捕获的系统事件将添加到 (，) `/etc/audit/rules.d/` `audit.log` 主机审核和上游集合。</span><span class="sxs-lookup"><span data-stu-id="eb588-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="eb588-151">Microsoft Defender for Endpoint for Linux 添加的事件将用密钥 `mdatp` 进行标记。</span><span class="sxs-lookup"><span data-stu-id="eb588-151">Events added by Microsoft Defender for Endpoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="eb588-152">网络连接</span><span class="sxs-lookup"><span data-stu-id="eb588-152">Network connections</span></span>

<span data-ttu-id="eb588-153">以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。</span><span class="sxs-lookup"><span data-stu-id="eb588-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="eb588-154">应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则。</span><span class="sxs-lookup"><span data-stu-id="eb588-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="eb588-155">如果有，可能需要专门为 *他们创建允许* 规则。</span><span class="sxs-lookup"><span data-stu-id="eb588-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="eb588-156">**域列表电子表格**</span><span class="sxs-lookup"><span data-stu-id="eb588-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="eb588-157">**描述**</span><span class="sxs-lookup"><span data-stu-id="eb588-157">**Description**</span></span>|
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | <span data-ttu-id="eb588-159">服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。</span><span class="sxs-lookup"><span data-stu-id="eb588-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="eb588-160">在此处下载电子表格。</span><span class="sxs-lookup"><span data-stu-id="eb588-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="eb588-161">有关更具体的 URL 列表，请参阅 [配置代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="eb588-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="eb588-162">Defender for Endpoint 可以使用以下发现方法发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="eb588-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="eb588-163">透明代理</span><span class="sxs-lookup"><span data-stu-id="eb588-163">Transparent proxy</span></span>
- <span data-ttu-id="eb588-164">手动静态代理配置</span><span class="sxs-lookup"><span data-stu-id="eb588-164">Manual static proxy configuration</span></span>

<span data-ttu-id="eb588-165">如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="eb588-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="eb588-166">对于透明代理，不需要对 Defender for Endpoint 进行其他配置。</span><span class="sxs-lookup"><span data-stu-id="eb588-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="eb588-167">对于静态代理，请按照手动静态代理 [配置 中的步骤操作](linux-static-proxy-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="eb588-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="eb588-168">不支持 PAC、WPAD 和经过身份验证的代理。</span><span class="sxs-lookup"><span data-stu-id="eb588-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="eb588-169">确保仅使用静态代理或透明代理。</span><span class="sxs-lookup"><span data-stu-id="eb588-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="eb588-170">出于安全考虑，也不支持 SSL 检查和截获代理。</span><span class="sxs-lookup"><span data-stu-id="eb588-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="eb588-171">为 SSL 检查和代理服务器配置例外，以直接将数据从 Defender for Endpoint for Linux 传递到相关 URL，而不会拦截。</span><span class="sxs-lookup"><span data-stu-id="eb588-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="eb588-172">将拦截证书添加到全局存储将不允许拦截。</span><span class="sxs-lookup"><span data-stu-id="eb588-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="eb588-173">有关疑难解答步骤，请参阅 [解决 Microsoft Defender for Endpoint for Linux 的云连接问题](linux-support-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="eb588-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="eb588-174">如何为 Linux 更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb588-174">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="eb588-175">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="eb588-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="eb588-176">若要更新适用于 Linux 的 Microsoft Defender for Endpoint，请参阅 [部署适用于 Linux](linux-updates.md)的 Microsoft Defender for Endpoint 的更新。</span><span class="sxs-lookup"><span data-stu-id="eb588-176">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="eb588-177">如何配置适用于 Linux 的 Microsoft Defender 终结点</span><span class="sxs-lookup"><span data-stu-id="eb588-177">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="eb588-178">有关如何在企业环境中配置产品的指南可在设置适用于 Linux 的 [Microsoft Defender for Endpoint 的首选项中提供](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="eb588-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="eb588-179">资源</span><span class="sxs-lookup"><span data-stu-id="eb588-179">Resources</span></span>

- <span data-ttu-id="eb588-180">有关日志记录、卸载或其他主题的信息，请参阅 [资源](linux-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="eb588-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
