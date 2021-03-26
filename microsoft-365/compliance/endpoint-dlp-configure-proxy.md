---
title: 为 Endpoint DLP 配置设备代理和 Internet 连接设置
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 了解如何为 Endpoint DLP 配置设备代理和 Internet 连接设置。
ms.openlocfilehash: 4d1aa3b75ec0a0720f3d92c847bf7c6cde6d966f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199271"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="fe059-103">为 Endpoint DLP 配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="fe059-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="fe059-104">Microsoft Endpoint DLP 使用 Microsoft Windows HTTP (WinHTTP) 报告数据并与 Microsoft Endpoint 云服务通信。</span><span class="sxs-lookup"><span data-stu-id="fe059-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="fe059-105">嵌入的 Endpoint DLP 使用 LocalSystem 账户在系统上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="fe059-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="fe059-106">对于使用正向代理作为 Internet 网关的组织，可以使用网络保护来调查代理背后的情况。</span><span class="sxs-lookup"><span data-stu-id="fe059-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="fe059-107">有关详细信息，请参阅[调查正向代理背后发生的连接事件](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy)。</span><span class="sxs-lookup"><span data-stu-id="fe059-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="fe059-108">WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用以下自动发现方法来发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="fe059-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="fe059-109">透明代理</span><span class="sxs-lookup"><span data-stu-id="fe059-109">Transparent proxy</span></span>
- <span data-ttu-id="fe059-110">Web 代理自动发现协议 (WPAD)</span><span class="sxs-lookup"><span data-stu-id="fe059-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="fe059-111">如果在网络拓扑中使用透明代理或 WPAD，则不需要特殊的配置设置。</span><span class="sxs-lookup"><span data-stu-id="fe059-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="fe059-112">有关代理中 Defender for Endpoint URL 排除的更多信息，请参阅[在代理服务器中启用对 Defender for Endpoint 云服务 URL 的访问](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="fe059-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="fe059-113">手动静态代理配置：</span><span class="sxs-lookup"><span data-stu-id="fe059-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="fe059-114">基于注册表的配置</span><span class="sxs-lookup"><span data-stu-id="fe059-114">Registry-based configuration</span></span>
    - <span data-ttu-id="fe059-115">使用 netsh 命令配置的 WinHTTP – 仅适用于稳定拓扑中的桌面（例如：同一代理后面的公司网络中的桌面）</span><span class="sxs-lookup"><span data-stu-id="fe059-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="fe059-116">使用基于注册表的静态代理手动配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="fe059-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="fe059-117">对于不允许连接到 Internet 的端点设备，需要配置基于注册表的静态代理。</span><span class="sxs-lookup"><span data-stu-id="fe059-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="fe059-118">您需要将其配置为仅允许 Microsoft Endpoint DLP 报告诊断数据并与 Microsoft Endpoint 云服务通信。</span><span class="sxs-lookup"><span data-stu-id="fe059-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="fe059-119">静态代理可以通过组策略 (GP) 配置。</span><span class="sxs-lookup"><span data-stu-id="fe059-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="fe059-120">可以在以下位置找到组策略：</span><span class="sxs-lookup"><span data-stu-id="fe059-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="fe059-121">打开 **“管理模板” > “Windows 组件” > “数据收集和预览版本” > “为连接的用户体验和遥测服务配置经验证的代理用法”**</span><span class="sxs-lookup"><span data-stu-id="fe059-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="fe059-122">将其设置为“**已启用**”，然后选择 **禁止使用经验证的代理**：</span><span class="sxs-lookup"><span data-stu-id="fe059-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![组策略设置 1 的图像](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="fe059-124">打开 **“管理模板” > “Windows 组件” > “数据收集和预览版” > “配置连接的用户体验和遥测”**：</span><span class="sxs-lookup"><span data-stu-id="fe059-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="fe059-125">配置代理</span><span class="sxs-lookup"><span data-stu-id="fe059-125">Configure the proxy</span></span>

![组策略设置 2 的图像](../media/atp-gpo-proxy2.png)

<span data-ttu-id="fe059-127">策略将注册表项 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的两个注册表值 `TelemetryProxyServer` 设置为 REG\u SZ，`DisableEnterpriseAuthProxy` 设置为 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="fe059-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="fe059-128">注册表值 TelemetryProxyServer 的格式为：\<server name or ip\>\<port\>。</span><span class="sxs-lookup"><span data-stu-id="fe059-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="fe059-129">例如：**10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="fe059-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="fe059-130">此注册表值 `DisableEnterpriseAuthProxy` 应当设置为 1。</span><span class="sxs-lookup"><span data-stu-id="fe059-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="fe059-131">使用“netsh”命令手动配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="fe059-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="fe059-132">使用 netsh 配置系统范围的静态代理。</span><span class="sxs-lookup"><span data-stu-id="fe059-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="fe059-133">这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="fe059-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="fe059-134">-正在改变拓扑的笔记本电脑（例如：从办公室到家）将出现 netsh 故障。</span><span class="sxs-lookup"><span data-stu-id="fe059-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="fe059-135">使用基于注册表的静态代理配置。</span><span class="sxs-lookup"><span data-stu-id="fe059-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="fe059-136">打开提升的命令行:</span><span class="sxs-lookup"><span data-stu-id="fe059-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="fe059-137">转到“**开始**”并键入“**cmd**”</span><span class="sxs-lookup"><span data-stu-id="fe059-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="fe059-138">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="fe059-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="fe059-139">输入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="fe059-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="fe059-140">例如：**netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="fe059-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="fe059-141">要重置 winhttp 代理，请输入以下命令并按 **Enter** 键：</span><span class="sxs-lookup"><span data-stu-id="fe059-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="fe059-142">若要了解详细信息。，请参见 [Netsh 命令语法、上下文和格式](/windows-server/networking/technologies/netsh/netsh-contexts)。</span><span class="sxs-lookup"><span data-stu-id="fe059-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="fe059-143">在代理服务器中启用对端点 DLP 云服务 URL 的访问</span><span class="sxs-lookup"><span data-stu-id="fe059-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="fe059-144">如果代理或防火墙在默认情况下阻止所有通信，并且只允许特定域通过，请将可下载工作表中列出的域添加到允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="fe059-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="fe059-145">此[可下载的电子表格](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)列出了网络必须能够连接到的服务及其关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="fe059-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="fe059-146">应该确保没有防火墙或网络过滤规则会拒绝访问这些 URL，或者可能需要专门为它们创建允许规则。</span><span class="sxs-lookup"><span data-stu-id="fe059-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="fe059-147">如果代理或防火墙启用了 HTTPS 扫描（SSL 检查），则从 HTTPS 扫描中排除上表中列出的域。</span><span class="sxs-lookup"><span data-stu-id="fe059-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="fe059-148">如果代理或防火墙阻止匿名通信，因为端点 DLP 是从系统上下文连接的，请确保前面列出的 URL 中允许匿名通信。</span><span class="sxs-lookup"><span data-stu-id="fe059-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="fe059-149">验证客户端与 Microsoft 云服务 URL 的连接</span><span class="sxs-lookup"><span data-stu-id="fe059-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="fe059-150">验证代理配置是否成功完成，WinHTTP 是否可以在你的环境中发现代理服务器并通过代理服务器进行通信，以及代理服务器是否允许到 Defender for Endpoint 服务 URL 的通信。</span><span class="sxs-lookup"><span data-stu-id="fe059-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="fe059-151">将 [MDATP 客户端分析器工具](https://aka.ms/mdatpanalyzer)下载到运行端点 DLP 的电脑上。</span><span class="sxs-lookup"><span data-stu-id="fe059-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="fe059-152">提取设备上 MDATPClientAnalyzer.zip 的内容。</span><span class="sxs-lookup"><span data-stu-id="fe059-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="fe059-153">打开提升的命令行:</span><span class="sxs-lookup"><span data-stu-id="fe059-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="fe059-154">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="fe059-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="fe059-155">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="fe059-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="fe059-156">输入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="fe059-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="fe059-157">例如，用下载 MDATPClientAnalyzer 工具的路径替换 *HardDrivePath*</span><span class="sxs-lookup"><span data-stu-id="fe059-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="fe059-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="fe059-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="fe059-159">在 _HardDrivePath\* 中使用的文件夹中提取由工具创建的 **MDATPClientAnalyzerResult.zip** _ 文件。</span><span class="sxs-lookup"><span data-stu-id="fe059-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="fe059-160">打开 **MDATPClientAnalyzerResult.txt** 并验证是否已执行代理配置步骤以启用服务器发现和对服务 URL 的访问。</span><span class="sxs-lookup"><span data-stu-id="fe059-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="fe059-161">该工具检查 Defender for Endpoint 客户端配置为与之交互的 Defender for Endpoint 服务 URL 的连接性。</span><span class="sxs-lookup"><span data-stu-id="fe059-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="fe059-162">然后，它将结果打印到每个可能用于与 Defender for Endpoint 服务进行通信的 URL 的 **MDATPClientAnalyzerResult.txt** 文件中。</span><span class="sxs-lookup"><span data-stu-id="fe059-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="fe059-163">例如：</span><span class="sxs-lookup"><span data-stu-id="fe059-163">For example:</span></span>

    <span data-ttu-id="fe059-164">**测试 URL：https://xxx.microsoft.com/xxx</br>1 - 默认代理：成功 (200) </br>2 - 代理自动发现 (WPAD)：成功 (200) </br> 3 - 禁用代理：成功 (200) </br> 4 - 命名代理：不存在 </br> 5 - 命令行代理：不存在**</span><span class="sxs-lookup"><span data-stu-id="fe059-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="fe059-165">如果至少有一个连接选项返回 (200) 状态，则 Defender for Endpoint 客户端可以使用此连接方法与测试的 URL 正确通信。</span><span class="sxs-lookup"><span data-stu-id="fe059-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="fe059-166">但是，如果连接检查结果显示失败，则会显示 HTTP 错误（请参阅 HTTP 状态代码）。</span><span class="sxs-lookup"><span data-stu-id="fe059-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="fe059-167">然后可以使用[启用对端点 DLP 云服务 URL 的访问](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)中所示的表中的 URL。</span><span class="sxs-lookup"><span data-stu-id="fe059-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="fe059-168">你将使用的 URL 将取决于载入过程中选择的区域。</span><span class="sxs-lookup"><span data-stu-id="fe059-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="fe059-169">Connectivity Analyzer 工具与 ASR 规则不兼容[阻止源自 PSExec 和 WMI 命令的进程创建](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="fe059-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="fe059-170">需要暂时禁用此规则才能运行连接工具。</span><span class="sxs-lookup"><span data-stu-id="fe059-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="fe059-171">在注册表中或通过组策略设置 TelemetryProxyServer 时，如果 Defender for Endpoint 无法访问定义的代理，它将回退到 direct。</span><span class="sxs-lookup"><span data-stu-id="fe059-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="fe059-172">相关主题 • 载入 Windows 10 设备 • Microsoft Endpoint DLP 登录问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="fe059-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="fe059-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe059-173">See also</span></span>

- [<span data-ttu-id="fe059-174">了解终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="fe059-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="fe059-175">使用终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="fe059-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="fe059-176">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="fe059-176">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="fe059-177">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="fe059-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="fe059-178">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="fe059-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="fe059-179">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe059-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="fe059-180">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="fe059-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="fe059-181">Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="fe059-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="fe059-182">已建立 Azure AD 联接的设备</span><span class="sxs-lookup"><span data-stu-id="fe059-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="fe059-183">下载基于 Chromium 的新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fe059-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)