---
title: 适用于 Linux 的 Microsoft Defender ATP
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
ms.openlocfilehash: 84d85b723d4dcbdfc07a074c40241242c57bc390
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185583"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e68ee-104">Microsoft Defender for Endpoint for Linux</span><span class="sxs-lookup"><span data-stu-id="e68ee-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e68ee-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e68ee-105">**Applies to:**</span></span>
- [<span data-ttu-id="e68ee-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e68ee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e68ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e68ee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e68ee-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e68ee-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e68ee-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e68ee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e68ee-110">本主题介绍如何安装、配置、更新和使用适用于 Linux 的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="e68ee-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="e68ee-111">将其他第三方终结点保护产品与 Microsoft Defender for Endpoint for Linux 一起运行可能会导致性能问题和不可预知的系统错误。</span><span class="sxs-lookup"><span data-stu-id="e68ee-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e68ee-112">如何安装适用于 Linux 的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e68ee-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e68ee-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="e68ee-113">Prerequisites</span></span>

- <span data-ttu-id="e68ee-114">访问 Microsoft Defender 安全中心门户</span><span class="sxs-lookup"><span data-stu-id="e68ee-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="e68ee-115">使用系统 [系统管理器的](https://systemd.io/) Linux 分发</span><span class="sxs-lookup"><span data-stu-id="e68ee-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="e68ee-116">Linux 和 BASH 脚本的初学者级体验</span><span class="sxs-lookup"><span data-stu-id="e68ee-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="e68ee-117">手动部署时，设备上 (管理权限) </span><span class="sxs-lookup"><span data-stu-id="e68ee-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="e68ee-118">安装说明</span><span class="sxs-lookup"><span data-stu-id="e68ee-118">Installation instructions</span></span>

<span data-ttu-id="e68ee-119">有几种方法和部署工具可用于安装和配置 Microsoft Defender for Endpoint for Linux。</span><span class="sxs-lookup"><span data-stu-id="e68ee-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="e68ee-120">通常，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e68ee-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="e68ee-121">确保你拥有适用于终结点的 Microsoft Defender 订阅，并且你有权访问 [适用于终结点](microsoft-defender-security-center.md)的 Microsoft Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="e68ee-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="e68ee-122">使用下列部署方法之一部署适用于 Linux 的 Microsoft Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="e68ee-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="e68ee-123">命令行工具：</span><span class="sxs-lookup"><span data-stu-id="e68ee-123">The command-line tool:</span></span>
    - [<span data-ttu-id="e68ee-124">手动部署</span><span class="sxs-lookup"><span data-stu-id="e68ee-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="e68ee-125">第三方管理工具：</span><span class="sxs-lookup"><span data-stu-id="e68ee-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="e68ee-126">使用配置管理工具进行部署</span><span class="sxs-lookup"><span data-stu-id="e68ee-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="e68ee-127">使用可配置管理工具进行部署</span><span class="sxs-lookup"><span data-stu-id="e68ee-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="e68ee-128">如果遇到任何安装失败，请参阅 Microsoft [Defender for Endpoint for Linux](linux-support-install.md)中的安装失败疑难解答。</span><span class="sxs-lookup"><span data-stu-id="e68ee-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="e68ee-129">系统要求</span><span class="sxs-lookup"><span data-stu-id="e68ee-129">System requirements</span></span>

- <span data-ttu-id="e68ee-130">支持的 Linux 服务器分发和版本：</span><span class="sxs-lookup"><span data-stu-id="e68ee-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="e68ee-131">Red Hat Enterprise Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e68ee-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="e68ee-132">CentOS 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e68ee-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="e68ee-133">Ubuntu 16.04 LTS 或更高版本 LTS</span><span class="sxs-lookup"><span data-stu-id="e68ee-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="e68ee-134">Debian 9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e68ee-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="e68ee-135">SUSE Linux Enterprise Server 12 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e68ee-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="e68ee-136">Oracle Linux 7.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e68ee-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="e68ee-137">最低内核版本 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="e68ee-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="e68ee-138">`fanotify`必须启用内核选项</span><span class="sxs-lookup"><span data-stu-id="e68ee-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="e68ee-139">不支持将适用于 Linux 的 Defender for Endpoint 与其他 `fanotify` 基于的安全解决方案并行运行。</span><span class="sxs-lookup"><span data-stu-id="e68ee-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="e68ee-140">它可能会导致不可预知的结果，包括挂起操作系统。</span><span class="sxs-lookup"><span data-stu-id="e68ee-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="e68ee-141">磁盘空间：1GB</span><span class="sxs-lookup"><span data-stu-id="e68ee-141">Disk space: 1GB</span></span>
- <span data-ttu-id="e68ee-142">解决方案当前为以下文件系统类型提供实时保护：</span><span class="sxs-lookup"><span data-stu-id="e68ee-142">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="e68ee-143">启用该服务后，可能需要配置网络或防火墙以允许其与终结点之间的出站连接。</span><span class="sxs-lookup"><span data-stu-id="e68ee-143">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="e68ee-144">必须 `auditd` () 审核框架。</span><span class="sxs-lookup"><span data-stu-id="e68ee-144">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="e68ee-145">通过添加到 的规则捕获的系统事件将添加到审核日志 `audit.logs` ，并可能影响主机审核和上游收集。</span><span class="sxs-lookup"><span data-stu-id="e68ee-145">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="e68ee-146">由 Microsoft Defender for Endopoint for Linux 添加的事件将用密钥 `mdatp` 进行标记。</span><span class="sxs-lookup"><span data-stu-id="e68ee-146">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="e68ee-147">网络连接</span><span class="sxs-lookup"><span data-stu-id="e68ee-147">Network connections</span></span>

<span data-ttu-id="e68ee-148">以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。</span><span class="sxs-lookup"><span data-stu-id="e68ee-148">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="e68ee-149">应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则。</span><span class="sxs-lookup"><span data-stu-id="e68ee-149">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="e68ee-150">如果有，可能需要专门为 *他们创建允许* 规则。</span><span class="sxs-lookup"><span data-stu-id="e68ee-150">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="e68ee-151">**域列表电子表格**</span><span class="sxs-lookup"><span data-stu-id="e68ee-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="e68ee-152">**说明**</span><span class="sxs-lookup"><span data-stu-id="e68ee-152">**Description**</span></span>|
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | <span data-ttu-id="e68ee-154">服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。</span><span class="sxs-lookup"><span data-stu-id="e68ee-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="e68ee-155">在此处下载电子表格。</span><span class="sxs-lookup"><span data-stu-id="e68ee-155">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="e68ee-156">有关更具体的 URL 列表，请参阅 [配置代理和 Internet 连接设置](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="e68ee-156">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="e68ee-157">Defender for Endpoint 可以使用以下发现方法发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="e68ee-157">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="e68ee-158">透明代理</span><span class="sxs-lookup"><span data-stu-id="e68ee-158">Transparent proxy</span></span>
- <span data-ttu-id="e68ee-159">手动静态代理配置</span><span class="sxs-lookup"><span data-stu-id="e68ee-159">Manual static proxy configuration</span></span>

<span data-ttu-id="e68ee-160">如果代理或防火墙阻止匿名流量，请确保允许匿名流量位于前面列出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="e68ee-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="e68ee-161">对于透明代理，不需要对 Defender for Endpoint 进行其他配置。</span><span class="sxs-lookup"><span data-stu-id="e68ee-161">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="e68ee-162">对于静态代理，请按照手动静态代理 [配置 中的步骤操作](linux-static-proxy-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="e68ee-162">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="e68ee-163">不支持 PAC、WPAD 和经过身份验证的代理。</span><span class="sxs-lookup"><span data-stu-id="e68ee-163">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="e68ee-164">确保仅使用静态代理或透明代理。</span><span class="sxs-lookup"><span data-stu-id="e68ee-164">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="e68ee-165">出于安全考虑，也不支持 SSL 检查和截获代理。</span><span class="sxs-lookup"><span data-stu-id="e68ee-165">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="e68ee-166">为 SSL 检查和代理服务器配置例外，以直接将数据从 Defender for Endpoint for Linux 传递到相关 URL，而不会拦截。</span><span class="sxs-lookup"><span data-stu-id="e68ee-166">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="e68ee-167">将拦截证书添加到全局存储将不允许拦截。</span><span class="sxs-lookup"><span data-stu-id="e68ee-167">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="e68ee-168">有关疑难解答步骤，请参阅 [解决 Microsoft Defender for Endpoint for Linux 的云连接问题](linux-support-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e68ee-168">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e68ee-169">如何为 Linux 更新 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e68ee-169">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="e68ee-170">Microsoft 会定期发布软件更新，以提高性能、安全性和提供新功能。</span><span class="sxs-lookup"><span data-stu-id="e68ee-170">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="e68ee-171">若要更新适用于 Linux 的 Microsoft Defender for Endpoint，请参阅 [部署适用于 Linux](linux-updates.md)的 Microsoft Defender for Endpoint 的更新。</span><span class="sxs-lookup"><span data-stu-id="e68ee-171">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e68ee-172">如何配置适用于 Linux 的 Microsoft Defender 终结点</span><span class="sxs-lookup"><span data-stu-id="e68ee-172">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="e68ee-173">有关如何在企业环境中配置产品的指南可在设置适用于 Linux 的 [Microsoft Defender for Endpoint 的首选项中提供](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="e68ee-173">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="e68ee-174">资源</span><span class="sxs-lookup"><span data-stu-id="e68ee-174">Resources</span></span>

- <span data-ttu-id="e68ee-175">有关日志记录、卸载或其他主题的信息，请参阅 [资源](linux-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="e68ee-175">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
