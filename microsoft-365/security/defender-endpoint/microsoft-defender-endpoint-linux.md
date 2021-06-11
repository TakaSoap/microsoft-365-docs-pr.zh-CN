---
title: Linux 版 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Linux 上安装和使用 Microsoft Defender for Endpoint。
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4175d3bedff86dc7f8cdafc1ff2366ca1c9cffc4
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893736"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="72a53-104">Linux 版 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72a53-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72a53-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="72a53-105">**Applies to:**</span></span>
- [<span data-ttu-id="72a53-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72a53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72a53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72a53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="72a53-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="72a53-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="72a53-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="72a53-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="72a53-110">本主题介绍如何在 Linux 上安装、配置、更新和使用 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="72a53-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="72a53-111">在 Linux 上运行其他第三方终结点保护产品以及 Microsoft Defender for Endpoint 可能会导致性能问题和不可预知的副作用。</span><span class="sxs-lookup"><span data-stu-id="72a53-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="72a53-112">如果非 Microsoft 终结点保护在你的环境中是绝对要求，在将防病毒功能配置为在被动模式下运行后，你仍然可以安全地利用 Linux EDR 上的 Defender for Endpoint[功能](linux-preferences.md#enable--disable-passive-mode)。</span><span class="sxs-lookup"><span data-stu-id="72a53-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="72a53-113">如何在 Linux 上安装 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72a53-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="72a53-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="72a53-114">Prerequisites</span></span>

- <span data-ttu-id="72a53-115">访问 Microsoft Defender 安全中心 门户</span><span class="sxs-lookup"><span data-stu-id="72a53-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="72a53-116">使用系统 [系统管理器的](https://systemd.io/) Linux 分发</span><span class="sxs-lookup"><span data-stu-id="72a53-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="72a53-117">Linux 和 BASH 脚本的初学者级体验</span><span class="sxs-lookup"><span data-stu-id="72a53-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="72a53-118">手动部署时，设备上 (管理权限) </span><span class="sxs-lookup"><span data-stu-id="72a53-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="72a53-119">Linux 代理上的 Microsoft Defender for Endpoint 独立于 [OMS 代理](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="72a53-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="72a53-120">Microsoft Defender for Endpoint 依赖于自己的独立遥测管道。</span><span class="sxs-lookup"><span data-stu-id="72a53-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="72a53-121">Linux 上的 Microsoft Defender for Endpoint 尚未集成到 Azure 安全中心。</span><span class="sxs-lookup"><span data-stu-id="72a53-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="72a53-122">安装说明</span><span class="sxs-lookup"><span data-stu-id="72a53-122">Installation instructions</span></span>

<span data-ttu-id="72a53-123">有几种方法和部署工具可用于在 Linux 上安装和配置 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="72a53-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="72a53-124">通常，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="72a53-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="72a53-125">确保你拥有适用于终结点的 Microsoft Defender 订阅，并且你有权访问 [适用于终结点](microsoft-defender-security-center.md)的 Microsoft Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="72a53-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="72a53-126">使用下列部署方法之一在 Linux 上部署 Microsoft Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="72a53-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="72a53-127">命令行工具：</span><span class="sxs-lookup"><span data-stu-id="72a53-127">The command-line tool:</span></span>
    - [<span data-ttu-id="72a53-128">手动部署</span><span class="sxs-lookup"><span data-stu-id="72a53-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="72a53-129">第三方管理工具：</span><span class="sxs-lookup"><span data-stu-id="72a53-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="72a53-130">使用配置管理工具进行部署</span><span class="sxs-lookup"><span data-stu-id="72a53-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="72a53-131">使用可配置管理工具进行部署</span><span class="sxs-lookup"><span data-stu-id="72a53-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="72a53-132">如果遇到任何安装失败，请参阅 Linux 上的 Microsoft Defender for Endpoint 中的安装 [失败疑难解答](linux-support-install.md)。</span><span class="sxs-lookup"><span data-stu-id="72a53-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="72a53-133">系统要求</span><span class="sxs-lookup"><span data-stu-id="72a53-133">System requirements</span></span>

- <span data-ttu-id="72a53-134">支持 Linux 服务器分发和 x64 (AMD64/EM64T) 版本：</span><span class="sxs-lookup"><span data-stu-id="72a53-134">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="72a53-135">Red Hat Enterprise Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="72a53-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="72a53-136">CentOS 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="72a53-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="72a53-137">Ubuntu 16.04 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="72a53-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="72a53-138">Debian 9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="72a53-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="72a53-139">SUSE Linux Enterprise Server 12 或更高版本</span><span class="sxs-lookup"><span data-stu-id="72a53-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="72a53-140">Oracle Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="72a53-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="72a53-141">未明确列出的分发和版本不受支持 (即使它们派生自正式支持的分发) 。</span><span class="sxs-lookup"><span data-stu-id="72a53-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="72a53-142">最低内核版本 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="72a53-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="72a53-143">`fanotify`必须启用内核选项</span><span class="sxs-lookup"><span data-stu-id="72a53-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="72a53-144">不支持在 Linux 上并行运行 Defender for Endpoint 和基于 `fanotify` 其他的安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="72a53-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="72a53-145">它可能会导致不可预知的结果，包括挂起操作系统。</span><span class="sxs-lookup"><span data-stu-id="72a53-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="72a53-146">磁盘空间：1 GB</span><span class="sxs-lookup"><span data-stu-id="72a53-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="72a53-147">/opt/microsoft/mdatp/sbin/wdavdaemon 需要可执行权限。</span><span class="sxs-lookup"><span data-stu-id="72a53-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="72a53-148">有关详细信息，请参阅在 Linux 上解决 Microsoft Defender for Endpoint 的安装问题中的"确保守护程序具有[可执行权限"。](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="72a53-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="72a53-149">核心：最少 2 个，首选 4 个</span><span class="sxs-lookup"><span data-stu-id="72a53-149">Cores: 2 minimum, 4 preferred</span></span>

- <span data-ttu-id="72a53-150">内存：最小 1 GB，首选 4 GB</span><span class="sxs-lookup"><span data-stu-id="72a53-150">Memory: 1 GB minimum, 4 preferred</span></span>

    > [!NOTE]
    > <span data-ttu-id="72a53-151">请确保 /var 中具有可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="72a53-151">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="72a53-152">解决方案当前为以下文件系统类型提供实时保护：</span><span class="sxs-lookup"><span data-stu-id="72a53-152">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="72a53-153">启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。</span><span class="sxs-lookup"><span data-stu-id="72a53-153">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="72a53-154">必须 `auditd` () 审核框架。</span><span class="sxs-lookup"><span data-stu-id="72a53-154">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="72a53-155">添加到 的规则捕获的系统事件将添加到 (，) `/etc/audit/rules.d/` `audit.log` 主机审核和上游集合。</span><span class="sxs-lookup"><span data-stu-id="72a53-155">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="72a53-156">Linux 上的 Microsoft Defender for Endpoint 添加的事件将用密钥 `mdatp` 进行标记。</span><span class="sxs-lookup"><span data-stu-id="72a53-156">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="72a53-157">网络连接</span><span class="sxs-lookup"><span data-stu-id="72a53-157">Network connections</span></span>

<span data-ttu-id="72a53-158">以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。</span><span class="sxs-lookup"><span data-stu-id="72a53-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="72a53-159">应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则。</span><span class="sxs-lookup"><span data-stu-id="72a53-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="72a53-160">如果有，可能需要专门为 *他们创建允许* 规则。</span><span class="sxs-lookup"><span data-stu-id="72a53-160">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="72a53-161">域列表电子表格</span><span class="sxs-lookup"><span data-stu-id="72a53-161">Spreadsheet of domains list</span></span> | <span data-ttu-id="72a53-162">说明</span><span class="sxs-lookup"><span data-stu-id="72a53-162">Description</span></span> |
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | <span data-ttu-id="72a53-164">服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。</span><span class="sxs-lookup"><span data-stu-id="72a53-164">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="72a53-165">在此处下载电子表格。</span><span class="sxs-lookup"><span data-stu-id="72a53-165">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="72a53-166">有关更具体的 URL 列表，请参阅 [配置代理和 Internet 连接设置](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="72a53-166">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="72a53-167">Defender for Endpoint 可以使用以下发现方法发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="72a53-167">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="72a53-168">透明代理</span><span class="sxs-lookup"><span data-stu-id="72a53-168">Transparent proxy</span></span>
- <span data-ttu-id="72a53-169">手动静态代理配置</span><span class="sxs-lookup"><span data-stu-id="72a53-169">Manual static proxy configuration</span></span>

<span data-ttu-id="72a53-170">如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="72a53-170">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="72a53-171">对于透明代理，不需要对 Defender for Endpoint 进行其他配置。</span><span class="sxs-lookup"><span data-stu-id="72a53-171">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="72a53-172">对于静态代理，请按照手动静态代理 [配置 中的步骤操作](linux-static-proxy-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="72a53-172">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="72a53-173">不支持 PAC、WPAD 和经过身份验证的代理。</span><span class="sxs-lookup"><span data-stu-id="72a53-173">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="72a53-174">确保仅使用静态代理或透明代理。</span><span class="sxs-lookup"><span data-stu-id="72a53-174">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="72a53-175">出于安全考虑，也不支持 SSL 检查和截获代理。</span><span class="sxs-lookup"><span data-stu-id="72a53-175">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="72a53-176">为 SSL 检查和代理服务器配置例外，以将数据从 Linux 上的 Defender for Endpoint 直接传递到相关 URL，而不会拦截。</span><span class="sxs-lookup"><span data-stu-id="72a53-176">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="72a53-177">将拦截证书添加到全局存储将不允许拦截。</span><span class="sxs-lookup"><span data-stu-id="72a53-177">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="72a53-178">有关疑难解答步骤，请参阅在 Linux 上解决 [Microsoft Defender for Endpoint 的云连接问题](linux-support-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="72a53-178">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="72a53-179">如何在 Linux 上更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72a53-179">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="72a53-180">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="72a53-180">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="72a53-181">若要在 Linux 上更新 Microsoft Defender for Endpoint，请参阅在 Linux 上部署 [Microsoft Defender for Endpoint 的更新](linux-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="72a53-181">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="72a53-182">如何配置 Linux 版 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72a53-182">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="72a53-183">有关如何在企业环境中配置产品的指南，可在在 Linux 上设置 [Microsoft Defender for Endpoint 的首选项中提供](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="72a53-183">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="72a53-184">资源</span><span class="sxs-lookup"><span data-stu-id="72a53-184">Resources</span></span>

- <span data-ttu-id="72a53-185">有关日志记录、卸载或其他主题的信息，请参阅 [资源](linux-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="72a53-185">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
