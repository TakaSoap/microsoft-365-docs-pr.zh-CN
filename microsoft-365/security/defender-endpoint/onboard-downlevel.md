---
title: 在 Microsoft Defender for Endpoint Windows上载入早期版本的客户端
description: 载入受支持的早期版本的 Windows 设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器
keywords: onboard， windows， 7， 81， oms， sp1， enterprise， pro， down level
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 945645e0f20f316c094f746adb6ba193f6806f86
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861355"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="9ed8d-104">载入以前版本的 Windows</span><span class="sxs-lookup"><span data-stu-id="9ed8d-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9ed8d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9ed8d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9ed8d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ed8d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9ed8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ed8d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9ed8d-108">**平台**</span><span class="sxs-lookup"><span data-stu-id="9ed8d-108">**Platforms**</span></span>
- <span data-ttu-id="9ed8d-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9ed8d-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="9ed8d-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="9ed8d-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="9ed8d-111">Windows 8.1 专业版</span><span class="sxs-lookup"><span data-stu-id="9ed8d-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="9ed8d-112">Windows 8.1 企业版</span><span class="sxs-lookup"><span data-stu-id="9ed8d-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="9ed8d-113">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9ed8d-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="9ed8d-114">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="9ed8d-115">Defender for Endpoint 扩展支持以包括低级别操作系统，从而在受支持的版本上提供高级攻击检测和Windows功能。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="9ed8d-116">若要将低级别Windows客户端终结点载入到 Defender for Endpoint，你将需要：</span><span class="sxs-lookup"><span data-stu-id="9ed8d-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="9ed8d-117">配置和更新System Center Endpoint Protection客户端。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="9ed8d-118">安装并配置Microsoft Monitoring Agent (MMA) 向 Defender for Endpoint 报告传感器数据，如下所述。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="9ed8d-119">载入设备后，你可以选择运行检测测试，以验证它是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="9ed8d-120">有关详细信息，请参阅对新载入的 Defender 终结点终结点运行检测 [测试](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="9ed8d-121">配置和更新System Center Endpoint Protection客户端</span><span class="sxs-lookup"><span data-stu-id="9ed8d-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9ed8d-122">只有当您的组织使用 SCEP System Center Endpoint Protection (时，才需要) 。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="9ed8d-123">Defender for Endpoint 与 System Center Endpoint Protection集成，通过禁止潜在恶意文件或可疑恶意软件，提供恶意软件检测的可见性并阻止攻击在组织中传播。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="9ed8d-124">若要启用此集成，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9ed8d-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="9ed8d-125">为客户端[安装 2017](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)年 1 月Endpoint Protection更新</span><span class="sxs-lookup"><span data-stu-id="9ed8d-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="9ed8d-126">将 SCEP 客户端云保护服务成员身份配置为 **高级** 设置</span><span class="sxs-lookup"><span data-stu-id="9ed8d-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="9ed8d-127">配置网络以允许连接到 Microsoft Defender 防病毒 云。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="9ed8d-128">有关详细信息，请参阅允许[连接到 Microsoft Defender 防病毒 云](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="9ed8d-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="9ed8d-129">安装和配置 Microsoft Monitoring Agent (MMA) 以将传感器数据报告给 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ed8d-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="9ed8d-130">开始之前</span><span class="sxs-lookup"><span data-stu-id="9ed8d-130">Before you begin</span></span>
<span data-ttu-id="9ed8d-131">查看以下详细信息以验证最低系统要求：</span><span class="sxs-lookup"><span data-stu-id="9ed8d-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="9ed8d-132">安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="9ed8d-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="9ed8d-133">仅适用于 Windows 7 SP1 Enterprise Windows 7 SP1 Pro。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="9ed8d-134">安装 [客户体验和诊断遥测更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="9ed8d-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="9ed8d-135">安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="9ed8d-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ed8d-136">仅适用于 Windows 7 SP1 Enterprise Windows 7 SP1 Pro。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="9ed8d-137">不要安装 4.0.x .NET Framework 4.0.x，因为它将否定上述安装。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="9ed8d-138">满足 Azure Log Analytics 代理的最低系统要求。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="9ed8d-139">有关详细信息，请参阅使用[Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)从环境中的计算机收集数据</span><span class="sxs-lookup"><span data-stu-id="9ed8d-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="9ed8d-140">下载代理安装文件[：Windows 64](https://go.microsoft.com/fwlink/?LinkId=828603)位代理或 Windows [32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="9ed8d-141">获取工作区 ID：</span><span class="sxs-lookup"><span data-stu-id="9ed8d-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="9ed8d-142">在 Defender for Endpoint 导航窗格中，选择"设置 >**设备管理>载入"**</span><span class="sxs-lookup"><span data-stu-id="9ed8d-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="9ed8d-143">选择 **Windows 7 SP1 和 8.1** 作为操作系统</span><span class="sxs-lookup"><span data-stu-id="9ed8d-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="9ed8d-144">复制工作区 ID 和工作区密钥</span><span class="sxs-lookup"><span data-stu-id="9ed8d-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="9ed8d-145">使用 Workspace ID 和 Workspace 密钥选择以下任一安装方法以安装代理：</span><span class="sxs-lookup"><span data-stu-id="9ed8d-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="9ed8d-146">[使用安装程序 手动安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="9ed8d-147">在"**代理设置选项**"页上 **，连接代理设置为 Azure Log Analytics (OMS)**</span><span class="sxs-lookup"><span data-stu-id="9ed8d-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="9ed8d-148">[使用命令行 安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="9ed8d-149">[使用脚本 配置代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9ed8d-150">如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="9ed8d-151">如果使用代理连接到 Internet，请参阅配置代理设置部分。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="9ed8d-152">完成后，你应该在一小时内在门户中看到已载入的终结点。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="9ed8d-153">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="9ed8d-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="9ed8d-154">每个Windows终结点必须能够使用 HTTPS 连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="9ed8d-155">此连接可以是直接的、使用代理的，也可以通过 [OMS 网关进行](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="9ed8d-156">如果代理或防火墙默认阻止所有流量，并仅允许特定域通过或 HTTPS 扫描 (SSL 检查) 已启用，请确保启用对 Defender [for Endpoint 服务 URL 的访问](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="9ed8d-157">载出客户端终结点</span><span class="sxs-lookup"><span data-stu-id="9ed8d-157">Offboard client endpoints</span></span>
<span data-ttu-id="9ed8d-158">若要卸载，你可以从终结点卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="9ed8d-159">离开代理后，终结点将不再将传感器数据发送到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="9ed8d-160">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9ed8d-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="9ed8d-161">[注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)。</span><span class="sxs-lookup"><span data-stu-id="9ed8d-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

