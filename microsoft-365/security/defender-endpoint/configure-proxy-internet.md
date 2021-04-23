---
title: 配置设备代理和 Internet 连接设置
description: 配置 Microsoft Defender for Endpoint 代理和 Internet 设置以启用与云服务的通信。
keywords: 配置， 代理， Internet， Internet 连接， 设置， 代理设置， netsh， winhttp， 代理服务器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8f25b924109823951c331fe744b548d372eaf11
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957606"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="d7777-104">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="d7777-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d7777-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d7777-105">**Applies to:**</span></span>
- [<span data-ttu-id="d7777-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d7777-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d7777-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7777-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d7777-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="d7777-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d7777-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d7777-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="d7777-110">Defender for Endpoint 传感器需要 Microsoft Windows HTTP (WinHTTP) 报告传感器数据并与 Defender for Endpoint 服务通信。</span><span class="sxs-lookup"><span data-stu-id="d7777-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="d7777-111">嵌入的 Defender for Endpoint 传感器使用 LocalSystem 帐户在系统上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="d7777-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="d7777-112">该传感器使用 Microsoft Windows HTTP Services (WinHTTP) 启用与 Defender for Endpoint 云服务的通信。</span><span class="sxs-lookup"><span data-stu-id="d7777-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="d7777-113">对于使用正向代理作为 Internet 网关的组织，可以使用网络保护来调查代理背后的情况。</span><span class="sxs-lookup"><span data-stu-id="d7777-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="d7777-114">有关详细信息，请参阅[调查正向代理背后发生的连接事件](investigate-behind-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="d7777-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="d7777-115">WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用下列发现方法发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="d7777-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="d7777-116">自动发现方法：</span><span class="sxs-lookup"><span data-stu-id="d7777-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="d7777-117">透明代理</span><span class="sxs-lookup"><span data-stu-id="d7777-117">Transparent proxy</span></span>
  - <span data-ttu-id="d7777-118">Web 代理自动发现协议 (WPAD)</span><span class="sxs-lookup"><span data-stu-id="d7777-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="d7777-119">如果在网络拓扑中使用的是透明代理或 WPAD，则不需要特殊的配置设置。</span><span class="sxs-lookup"><span data-stu-id="d7777-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="d7777-120">有关代理中的 Defender 终结点 URL 排除项详细信息，请参阅在代理服务器中启用对 [Defender for Endpoint 服务 URL 的访问](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="d7777-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="d7777-121">手动静态代理配置：</span><span class="sxs-lookup"><span data-stu-id="d7777-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="d7777-122">基于注册表的配置</span><span class="sxs-lookup"><span data-stu-id="d7777-122">Registry based configuration</span></span>
  - <span data-ttu-id="d7777-123">使用 netsh 命令配置的 WinHTTP – 仅适用于稳定拓扑中的桌面（例如：同一代理后面的公司网络中的桌面）</span><span class="sxs-lookup"><span data-stu-id="d7777-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="d7777-124">使用基于注册表的静态代理手动配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="d7777-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="d7777-125">配置基于注册表的静态代理，以在不允许计算机连接到 Internet 时仅允许 Defender for Endpoint 传感器报告诊断数据并与 Defender for Endpoint 服务通信。</span><span class="sxs-lookup"><span data-stu-id="d7777-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

> [!NOTE]
> - <span data-ttu-id="d7777-126">在 Windows 10 或 Windows Server 2019 上使用此选项时，建议让以下 (或更高版本) 版本和累积更新汇总：</span><span class="sxs-lookup"><span data-stu-id="d7777-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span></br>
> <span data-ttu-id="d7777-127">Windows 10 版本 1809 或 Windows Server 2019 - https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="d7777-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span> <br>
> <span data-ttu-id="d7777-128">Windows 10 版本 1909 - https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="d7777-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span></br>
> <span data-ttu-id="d7777-129">Windows 10 版本 2004 - https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="d7777-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="d7777-130">Windows 10 版本 20H2 - https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="d7777-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="d7777-131">这些更新改进了 CnC (Command and Control) 连接和可靠性。</span><span class="sxs-lookup"><span data-stu-id="d7777-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span></br>

<span data-ttu-id="d7777-132">静态代理可以通过组策略 (GP) 配置。</span><span class="sxs-lookup"><span data-stu-id="d7777-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="d7777-133">可以在以下位置找到组策略：</span><span class="sxs-lookup"><span data-stu-id="d7777-133">The group policy can be found under:</span></span>

- <span data-ttu-id="d7777-134">Windows 组件>模板>数据收集和预览>配置连接的用户体验和遥测服务的已验证代理使用情况</span><span class="sxs-lookup"><span data-stu-id="d7777-134">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="d7777-135">将其设置为 **已启用，** 然后选择 **"禁用经过身份验证的代理用法**： ![ 组策略的图像"设置1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="d7777-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="d7777-136">**Windows 组件>模板>数据收集和预览>配置连接的用户体验和遥测**：</span><span class="sxs-lookup"><span data-stu-id="d7777-136">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="d7777-137">配置代理：</span><span class="sxs-lookup"><span data-stu-id="d7777-137">Configure the proxy:</span></span><br>
    <span data-ttu-id="d7777-138">![组策略设置 2 的图像](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="d7777-138">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="d7777-139">策略将注册表项 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的两个注册表值 `TelemetryProxyServer` 设置为 REG\u SZ，`DisableEnterpriseAuthProxy` 设置为 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="d7777-139">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="d7777-140">注册表值 `TelemetryProxyServer` 采用以下字符串格式：</span><span class="sxs-lookup"><span data-stu-id="d7777-140">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="d7777-141">例如：10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="d7777-141">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="d7777-142">此注册表值 `DisableEnterpriseAuthProxy` 应当设置为 1。</span><span class="sxs-lookup"><span data-stu-id="d7777-142">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="d7777-143">使用 netsh 命令手动配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="d7777-143">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="d7777-144">使用 netsh 配置系统范围的静态代理。</span><span class="sxs-lookup"><span data-stu-id="d7777-144">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="d7777-145">这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="d7777-145">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="d7777-146">更改拓扑结构（例如 (：从办公室到家庭) netsh 将发生故障。</span><span class="sxs-lookup"><span data-stu-id="d7777-146">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="d7777-147">使用基于注册表的静态代理配置。</span><span class="sxs-lookup"><span data-stu-id="d7777-147">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="d7777-148">打开提升的命令行：</span><span class="sxs-lookup"><span data-stu-id="d7777-148">Open an elevated command-line:</span></span>

    <span data-ttu-id="d7777-149">a.</span><span class="sxs-lookup"><span data-stu-id="d7777-149">a.</span></span> <span data-ttu-id="d7777-150">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="d7777-150">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="d7777-151">b.</span><span class="sxs-lookup"><span data-stu-id="d7777-151">b.</span></span> <span data-ttu-id="d7777-152">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="d7777-152">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="d7777-153">输入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="d7777-153">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="d7777-154">例如：netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="d7777-154">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="d7777-155">若要重置 winhttp 代理，请输入以下命令并按 **Enter**</span><span class="sxs-lookup"><span data-stu-id="d7777-155">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="d7777-156">若要了解详细信息。，请参见 [Netsh 命令语法、上下文和格式](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts)。</span><span class="sxs-lookup"><span data-stu-id="d7777-156">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="d7777-157">在代理服务器中启用对 Microsoft Defender for Endpoint 服务 URL 的访问</span><span class="sxs-lookup"><span data-stu-id="d7777-157">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="d7777-158">如果代理或防火墙在默认情况下阻止所有通信，并且只允许特定域通过，请将可下载工作表中列出的域添加到允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="d7777-158">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="d7777-159">以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。</span><span class="sxs-lookup"><span data-stu-id="d7777-159">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="d7777-160">应确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。 </span><span class="sxs-lookup"><span data-stu-id="d7777-160">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="d7777-161">**域列表电子表格**</span><span class="sxs-lookup"><span data-stu-id="d7777-161">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="d7777-162">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7777-162">**Description**</span></span>|
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | <span data-ttu-id="d7777-164">服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。</span><span class="sxs-lookup"><span data-stu-id="d7777-164">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="d7777-165">在此处下载电子表格。</span><span class="sxs-lookup"><span data-stu-id="d7777-165">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="d7777-166">如果代理或防火墙启用了 HTTPS 扫描（SSL 检查），则从 HTTPS 扫描中排除上表中列出的域。</span><span class="sxs-lookup"><span data-stu-id="d7777-166">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="d7777-167">settings-win.data.microsoft.com 运行版本 1803 或更早版本的 Windows 10 设备时，才需要此配置。</span><span class="sxs-lookup"><span data-stu-id="d7777-167">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="d7777-168">仅在 Windows 10 设备运行版本 1803 或更高版本时，才需要包含 v20 的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7777-168">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="d7777-169">例如，运行版本 1803 或更高版本并载入到美国数据存储地区的 ```us-v20.events.data.microsoft.com``` Windows 10 设备需要 。</span><span class="sxs-lookup"><span data-stu-id="d7777-169">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="d7777-170">如果你正在环境中使用 Microsoft Defender 防病毒，请参阅配置与 [Microsoft Defender 防病毒云服务的网络连接](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="d7777-170">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="d7777-171">如果代理或防火墙阻止匿名流量，因为 Defender for Endpoint 传感器从系统上下文连接，请确保允许匿名流量位于前面列出的 URL 中。</span><span class="sxs-lookup"><span data-stu-id="d7777-171">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="d7777-172">Microsoft Monitoring Agent (MMA) - 旧版 Windows 客户端或 Windows Server 的代理和防火墙要求</span><span class="sxs-lookup"><span data-stu-id="d7777-172">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="d7777-173">以下信息列出了与 Log Analytics 代理通信所需的代理和防火墙配置信息 (通常称为以前版本的 Windows（如 Windows 7 SP1、Windows 8.1、Windows Server 2008 R2、Windows Server 2012 R2 和 Windows Server 2016）的 Microsoft 监视代理) 。</span><span class="sxs-lookup"><span data-stu-id="d7777-173">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="d7777-174">代理资源</span><span class="sxs-lookup"><span data-stu-id="d7777-174">Agent Resource</span></span>|<span data-ttu-id="d7777-175">端口</span><span class="sxs-lookup"><span data-stu-id="d7777-175">Ports</span></span> |<span data-ttu-id="d7777-176">Direction</span><span class="sxs-lookup"><span data-stu-id="d7777-176">Direction</span></span> |<span data-ttu-id="d7777-177">绕过 HTTPS 检查</span><span class="sxs-lookup"><span data-stu-id="d7777-177">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="d7777-178">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="d7777-178">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="d7777-179">端口 443</span><span class="sxs-lookup"><span data-stu-id="d7777-179">Port 443</span></span> |<span data-ttu-id="d7777-180">出站</span><span class="sxs-lookup"><span data-stu-id="d7777-180">Outbound</span></span>|<span data-ttu-id="d7777-181">是</span><span class="sxs-lookup"><span data-stu-id="d7777-181">Yes</span></span> |  
|<span data-ttu-id="d7777-182">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="d7777-182">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="d7777-183">端口 443</span><span class="sxs-lookup"><span data-stu-id="d7777-183">Port 443</span></span> |<span data-ttu-id="d7777-184">出站</span><span class="sxs-lookup"><span data-stu-id="d7777-184">Outbound</span></span>|<span data-ttu-id="d7777-185">是</span><span class="sxs-lookup"><span data-stu-id="d7777-185">Yes</span></span> |  
|<span data-ttu-id="d7777-186">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="d7777-186">\*.blob.core.windows.net</span></span> |<span data-ttu-id="d7777-187">端口 443</span><span class="sxs-lookup"><span data-stu-id="d7777-187">Port 443</span></span> |<span data-ttu-id="d7777-188">出站</span><span class="sxs-lookup"><span data-stu-id="d7777-188">Outbound</span></span>|<span data-ttu-id="d7777-189">是</span><span class="sxs-lookup"><span data-stu-id="d7777-189">Yes</span></span> |
|<span data-ttu-id="d7777-190">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="d7777-190">\*.azure-automation.net</span></span> |<span data-ttu-id="d7777-191">端口 443</span><span class="sxs-lookup"><span data-stu-id="d7777-191">Port 443</span></span> |<span data-ttu-id="d7777-192">出站</span><span class="sxs-lookup"><span data-stu-id="d7777-192">Outbound</span></span>|<span data-ttu-id="d7777-193">是</span><span class="sxs-lookup"><span data-stu-id="d7777-193">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="d7777-194">作为基于云的解决方案，IP 范围可能会更改。</span><span class="sxs-lookup"><span data-stu-id="d7777-194">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="d7777-195">建议移动到 DNS 解析设置。</span><span class="sxs-lookup"><span data-stu-id="d7777-195">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="d7777-196">确认 Microsoft 监控代理 (MMA) 服务 URL 要求</span><span class="sxs-lookup"><span data-stu-id="d7777-196">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="d7777-197">请参阅以下指南，在将 Microsoft 监视代理 (MMA) 用于以前版本的 Windows 时，消除特定环境的通配符 (\*) 要求。</span><span class="sxs-lookup"><span data-stu-id="d7777-197">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="d7777-198">使用 Microsoft 监视代理 (MMA) 将以前的操作系统载入到 Defender for Endpoint (中有关详细信息，请参阅在 [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) 上载入以前版本的 Windows 和载入 Windows [服务器](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="d7777-198">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="d7777-199">确保计算机已成功报告到 Microsoft Defender 安全中心门户。</span><span class="sxs-lookup"><span data-stu-id="d7777-199">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="d7777-200">从"C：\Program Files\Microsoft Monitoring Agent\Agent"运行 TestCloudConnection.exe 工具，以验证连接并查看特定工作区所需的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7777-200">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="d7777-201">请查看 Microsoft Defender 终结点 URL 列表，了解你的地区要求的完整 (请参阅服务 URL[电子表格) 。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="d7777-201">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![网站中的管理员Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="d7777-203">\*.ods.opinsights.azure.com、) \*.oms.opinsights.azure.com 和 *.agentsvc.azure-automation.net URL 终结点中使用的通配符 (*agentsvc.azure-automation.net ID 可以替换为特定的工作区 ID。</span><span class="sxs-lookup"><span data-stu-id="d7777-203">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="d7777-204">工作区 ID 特定于你的环境和工作区，可以在 Microsoft Defender 安全中心门户内的租户载入部分找到。</span><span class="sxs-lookup"><span data-stu-id="d7777-204">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="d7777-205">\*.blob.core.windows.net URL 终结点可以替换为测试结果的"防火墙规则： \*.blob.core.windows.net"部分中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7777-205">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7777-206">如果通过 Azure Defender 载入，可能使用多个工作区。</span><span class="sxs-lookup"><span data-stu-id="d7777-206">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="d7777-207">你需要在每个工作区 (的已载入计算机上执行上述 TestCloudConnection.exe 过程，以确定工作区和工作区之间的 \*.blob.core.windows.net URL) 。</span><span class="sxs-lookup"><span data-stu-id="d7777-207">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="d7777-208">验证与 Microsoft Defender for Endpoint 服务 URL 的客户端连接</span><span class="sxs-lookup"><span data-stu-id="d7777-208">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="d7777-209">验证代理配置是否成功完成，WinHTTP 是否可以在你的环境中发现代理服务器并通过代理服务器进行通信，以及代理服务器是否允许到 Defender for Endpoint 服务 URL 的通信。</span><span class="sxs-lookup"><span data-stu-id="d7777-209">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="d7777-210">将 [MDATP 客户端分析器工具](https://aka.ms/mdatpanalyzer) 下载到运行 Defender for Endpoint 传感器的电脑。</span><span class="sxs-lookup"><span data-stu-id="d7777-210">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="d7777-211">提取设备上 MDATPClientAnalyzer.zip 的内容。</span><span class="sxs-lookup"><span data-stu-id="d7777-211">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="d7777-212">打开提升的命令行：</span><span class="sxs-lookup"><span data-stu-id="d7777-212">Open an elevated command-line:</span></span>

    <span data-ttu-id="d7777-213">a.</span><span class="sxs-lookup"><span data-stu-id="d7777-213">a.</span></span> <span data-ttu-id="d7777-214">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="d7777-214">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="d7777-215">b.</span><span class="sxs-lookup"><span data-stu-id="d7777-215">b.</span></span>  <span data-ttu-id="d7777-216">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="d7777-216">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="d7777-217">输入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="d7777-217">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="d7777-218">例如，用下载 MDATPClientAnalyzer 工具的路径替换 *HardDrivePath*</span><span class="sxs-lookup"><span data-stu-id="d7777-218">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="d7777-219">提取 *MDATPClientAnalyzerResult.zip\*\*在 HardDrivePath* 中使用的文件夹中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="d7777-219">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="d7777-220">打开 *MDATPClientAnalyzerResult.txt* 并验证是否已执行代理配置步骤以启用服务器发现和对服务 URL 的访问。</span><span class="sxs-lookup"><span data-stu-id="d7777-220">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="d7777-221">该工具检查 Defender for Endpoint 客户端配置为与之交互的 Defender for Endpoint 服务 URL 的连接性。</span><span class="sxs-lookup"><span data-stu-id="d7777-221">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="d7777-222">然后，它将结果打印到每个可能用于与 Defender for Endpoint 服务进行通信的 URL 的 *MDATPClientAnalyzerResult.txt* 文件中。</span><span class="sxs-lookup"><span data-stu-id="d7777-222">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="d7777-223">例如：</span><span class="sxs-lookup"><span data-stu-id="d7777-223">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="d7777-224">如果至少有一个连接选项返回 (200) 状态，则 Defender for Endpoint 客户端可以使用此连接方法与测试的 URL 正确通信。</span><span class="sxs-lookup"><span data-stu-id="d7777-224">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="d7777-225">但是，如果连接检查结果显示失败，则会显示 HTTP 错误（请参阅 HTTP 状态代码）。</span><span class="sxs-lookup"><span data-stu-id="d7777-225">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="d7777-226">然后，可以使用在代理服务器 中启用对 Defender [for Endpoint 服务 URL](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)的访问中显示的表中的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7777-226">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="d7777-227">将使用的 URL 取决于在载入过程中选择的区域。</span><span class="sxs-lookup"><span data-stu-id="d7777-227">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="d7777-228">Connectivity Analyzer 工具与 ASR 规则不兼容[阻止源自 PSExec 和 WMI 命令的进程创建](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="d7777-228">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="d7777-229">需要暂时禁用此规则才能运行连接工具。</span><span class="sxs-lookup"><span data-stu-id="d7777-229">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="d7777-230">当在注册表中或通过组策略设置 TelemetryProxyServer 时，如果 Defender for Endpoint 无法访问定义的代理，它将回退到直接。</span><span class="sxs-lookup"><span data-stu-id="d7777-230">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d7777-231">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7777-231">Related topics</span></span>

- [<span data-ttu-id="d7777-232">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="d7777-232">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="d7777-233">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="d7777-233">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
