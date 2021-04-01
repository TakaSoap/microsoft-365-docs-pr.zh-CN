---
title: 将 Windows 服务器载入 Microsoft Defender for Endpoint 服务
description: 载入 Windows 服务器，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器。
keywords: 载入服务器， 服务器， 2012r2， 2016， 2019， 服务器载入， 设备管理， 配置 Windows ATP 服务器， 载入 Microsoft Defender 终结点服务器， 载入 Microsoft Defender for Endpoint Server
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1757160b37500e97586fbb6dfb16d81303bc54e4
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476477"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="56794-104">将 Windows 服务器载入 Microsoft Defender for Endpoint 服务</span><span class="sxs-lookup"><span data-stu-id="56794-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="56794-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="56794-105">**Applies to:**</span></span>

- <span data-ttu-id="56794-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="56794-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="56794-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="56794-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="56794-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="56794-108">Windows Server 2016</span></span>
- <span data-ttu-id="56794-109">Windows Server (SAC) 版本 1803 及更高版本</span><span class="sxs-lookup"><span data-stu-id="56794-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="56794-110">Windows Server 2019 及更高版本</span><span class="sxs-lookup"><span data-stu-id="56794-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="56794-111">Windows Server 2019 核心版本</span><span class="sxs-lookup"><span data-stu-id="56794-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="56794-112">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="56794-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="56794-113">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="56794-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="56794-114">Defender for Endpoint 扩展了支持，还包括 Windows Server 操作系统。</span><span class="sxs-lookup"><span data-stu-id="56794-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="56794-115">此支持通过 Microsoft Defender 安全中心控制台无缝提供高级攻击检测和调查功能。</span><span class="sxs-lookup"><span data-stu-id="56794-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="56794-116">有关许可和基础结构需要满足的实际指导，请参阅使用 Defender for Endpoint [保护 Windows 服务器](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。</span><span class="sxs-lookup"><span data-stu-id="56794-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="56794-117">有关如何下载和使用 Windows 服务器的 Windows 安全基线的指南，请参阅 [Windows 安全基线](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="56794-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="56794-118">Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="56794-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="56794-119">可以使用以下任一选项将 Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016 载入 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="56794-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="56794-120">**选项 1：**[通过安装和配置 Microsoft](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Monitoring Agent (MMA) </span><span class="sxs-lookup"><span data-stu-id="56794-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="56794-121">**选项 2：**[通过 Azure 安全中心载入](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="56794-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="56794-122">**选项 3：**[通过 Microsoft Endpoint Manager 版本 2002 及更高版本载入](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="56794-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="56794-123">使用提供的任一选项完成载入步骤后，你需要配置和更新 [System Center Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="56794-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="56794-124">每个节点都需要 Defender for Endpoint 独立服务器许可证，才能通过 Microsoft 监视代理 (选项 1) 或 Microsoft Endpoint Manager (选项 3) 载入 Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="56794-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="56794-125">或者，每个节点都需要 Azure Defender for Servers 许可证，才能通过 Azure 安全中心 (选项 2) 载入 Windows 服务器，请参阅 Azure 安全中心中提供的支持 [功能](https://docs.microsoft.com/azure/security-center/security-center-services)。</span><span class="sxs-lookup"><span data-stu-id="56794-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="56794-126">选项 1：通过安装和配置 Microsoft Monitoring Agent (MMA) </span><span class="sxs-lookup"><span data-stu-id="56794-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="56794-127">你需要为 Windows 服务器安装和配置 MMA，以将传感器数据报告给 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="56794-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="56794-128">有关详细信息，请参阅使用 [Azure Log Analytics 代理收集日志数据](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="56794-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="56794-129">如果你已在使用 System Center Operations Manager (SCOM) 或 Azure Monitor (以前称为 Operations Management Suite (OMS) ) ，请附加 Microsoft Monitoring Agent (MMA) 以通过多托管支持向 Defender for Endpoint 工作区报告。</span><span class="sxs-lookup"><span data-stu-id="56794-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="56794-130">通常，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="56794-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="56794-131">满足开始之前部分 **中列出的载入** 要求。</span><span class="sxs-lookup"><span data-stu-id="56794-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="56794-132">从 Microsoft Defender 安全中心打开服务器监视。</span><span class="sxs-lookup"><span data-stu-id="56794-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="56794-133">安装和配置服务器的 MMA，以将传感器数据报告给 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="56794-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="56794-134">配置和更新 System Center Endpoint Protection 客户端。</span><span class="sxs-lookup"><span data-stu-id="56794-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="56794-135">载入设备后，你可以选择运行检测测试，以验证它是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="56794-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="56794-136">有关详细信息，请参阅对新载入的 Defender 终结点终结点运行检测 [测试](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="56794-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="56794-137">准备工作</span><span class="sxs-lookup"><span data-stu-id="56794-137">Before you begin</span></span> 
<span data-ttu-id="56794-138">执行以下步骤以满足载入要求：</span><span class="sxs-lookup"><span data-stu-id="56794-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="56794-139">对于 Windows Server 2008 R2 SP1 或 Windows Server 2012 R2，请确保安装以下修补程序：</span><span class="sxs-lookup"><span data-stu-id="56794-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="56794-140">客户体验和诊断遥测更新</span><span class="sxs-lookup"><span data-stu-id="56794-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="56794-141">此外，对于 Windows Server 2008 R2 SP1，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="56794-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="56794-142">安装 [2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="56794-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="56794-143">安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="56794-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>
   
   > [!NOTE]
    > <span data-ttu-id="56794-144">如果使用 SCCM 管理 Windows Server 2008 R2 SP1，SCCM 客户端代理将安装 .Net Framework 4.5.2。</span><span class="sxs-lookup"><span data-stu-id="56794-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="56794-145">因此，无需安装 .NET framework 4.5 (或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="56794-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>
   
 - <span data-ttu-id="56794-146">对于 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2：配置和更新 [System Center Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="56794-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="56794-147">只有当组织使用 System Center Endpoint Protection (SCEP) 并且要载入 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2 时，才需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="56794-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="56794-148">安装和配置 Microsoft 监视代理 (MMA) 向 Microsoft Defender for Endpoint 报告传感器数据</span><span class="sxs-lookup"><span data-stu-id="56794-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="56794-149">下载代理设置文件 [：Windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603)。</span><span class="sxs-lookup"><span data-stu-id="56794-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="56794-150">使用在上一过程中获取的 Workspace ID 和 Workspace 密钥，选择以下任一安装方法在 Windows 服务器上安装代理：</span><span class="sxs-lookup"><span data-stu-id="56794-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="56794-151">[使用安装程序 手动安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="56794-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="56794-152">在"**代理设置选项"** 页上，选择"将代理 **连接到 Azure Log Analytics (OMS) "。**</span><span class="sxs-lookup"><span data-stu-id="56794-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="56794-153">[使用命令行 安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="56794-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="56794-154">[使用脚本 配置代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="56794-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="56794-155">如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。</span><span class="sxs-lookup"><span data-stu-id="56794-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="56794-156">根据需要配置 Windows 服务器代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="56794-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="56794-157">如果你的服务器需要使用代理与 Defender for Endpoint 通信，请使用以下方法之一将 MMA 配置为使用代理服务器：</span><span class="sxs-lookup"><span data-stu-id="56794-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="56794-158">配置 MMA 以使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="56794-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="56794-159">配置 Windows 以将代理服务器用于所有连接</span><span class="sxs-lookup"><span data-stu-id="56794-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="56794-160">如果代理或防火墙已在使用中，请确保服务器可以直接访问所有 Microsoft Defender for Endpoint 服务 URL，且无需 SSL 拦截。</span><span class="sxs-lookup"><span data-stu-id="56794-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="56794-161">有关详细信息，请参阅启用对 [Defender for Endpoint 服务 URL 的访问](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="56794-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="56794-162">使用 SSL 拦截将阻止系统与 Defender for Endpoint 服务通信。</span><span class="sxs-lookup"><span data-stu-id="56794-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="56794-163">完成后，你应该在一小时内在门户中看到已载入的 Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="56794-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="56794-164">选项 2：通过 Azure 安全中心载入 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="56794-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="56794-165">在 Microsoft Defender 安全中心导航窗格中，**选择设置**  >  **设备管理**  >  **载入**。</span><span class="sxs-lookup"><span data-stu-id="56794-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="56794-166">选择 **Windows Server 2008 R2 SP1、2012 R2 和 2016** 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="56794-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="56794-167">单击 **Azure 安全中心中的载入服务器**。</span><span class="sxs-lookup"><span data-stu-id="56794-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="56794-168">按照 Microsoft Defender for Endpoint with Azure 安全中心 [中的载入说明进行操作](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="56794-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="56794-169">完成载入步骤后，你需要配置和更新 System Center [Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="56794-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="56794-170">若要通过 Azure Defender for Servers (以前是 Azure 安全中心标准版) 载入，服务器必须在 Microsoft 监视代理 (MMA) 设置中配置适当的工作区和密钥。</span><span class="sxs-lookup"><span data-stu-id="56794-170">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="56794-171">配置后，相应的云管理包将部署在计算机中，并且传感器 (MsSenseS.exe) 将部署和启动。</span><span class="sxs-lookup"><span data-stu-id="56794-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="56794-172">如果服务器配置为使用 OMS 网关服务器作为代理，则也要求这样做。</span><span class="sxs-lookup"><span data-stu-id="56794-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="56794-173">选项 3：通过 Microsoft Endpoint Manager 版本 2002 及更高版本载入 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="56794-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="56794-174">可以使用 Microsoft Endpoint Manager Windows Server 2012版本 2002 和更高版本载入 R2 和 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="56794-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="56794-175">有关详细信息，请参阅[Microsoft Endpoint Manager current branch 中的 Microsoft Defender for Endpoint。](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="56794-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="56794-176">完成载入步骤后，你需要配置和更新 System Center [Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="56794-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="56794-177">Windows Server (SAC) 版本 1803、Windows Server 2019 和 Windows Server 2019 Core 版本</span><span class="sxs-lookup"><span data-stu-id="56794-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="56794-178">可以使用以下部署方法载入 Windows Server (SAC) 版本 1803、Windows Server 2019 或 Windows Server 2019 Core 版本：</span><span class="sxs-lookup"><span data-stu-id="56794-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="56794-179">本地脚本</span><span class="sxs-lookup"><span data-stu-id="56794-179">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="56794-180">组策略</span><span class="sxs-lookup"><span data-stu-id="56794-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="56794-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="56794-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="56794-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="56794-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="56794-183">用于非永久性设备的 VDI 载入脚本</span><span class="sxs-lookup"><span data-stu-id="56794-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="56794-184">通过 Microsoft Endpoint Manager 的 Windows Server 2019 载入程序包当前附带了一个脚本。</span><span class="sxs-lookup"><span data-stu-id="56794-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="56794-185">若要详细了解如何在 Configuration Manager 中部署脚本，请参阅 Configuration [Manager 中的程序包和程序](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="56794-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="56794-186">本地脚本适用于概念证明，但不应用于生产部署。</span><span class="sxs-lookup"><span data-stu-id="56794-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="56794-187">对于生产部署，我们建议使用组策略或 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="56794-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="56794-188">对 Windows Server 的支持可更深入地了解服务器活动、内核和内存攻击检测的范围，并启用响应操作。</span><span class="sxs-lookup"><span data-stu-id="56794-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="56794-189">使用适用于 Windows 10 设备的相同工具和方法在 Windows 服务器上配置适用于终结点载入设置的 Defender。</span><span class="sxs-lookup"><span data-stu-id="56794-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="56794-190">有关详细信息，请参阅载入 [Windows 10 设备](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="56794-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="56794-191">如果你运行的是第三方反恶意软件解决方案，则需要应用以下 Microsoft Defender AV 被动模式设置。</span><span class="sxs-lookup"><span data-stu-id="56794-191">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="56794-192">验证是否正确配置了它：</span><span class="sxs-lookup"><span data-stu-id="56794-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="56794-193">设置以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="56794-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="56794-194">路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="56794-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="56794-195">名称：ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="56794-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="56794-196">类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="56794-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="56794-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="56794-197">Value: 1</span></span>

    1. <span data-ttu-id="56794-198">运行以下 PowerShell 命令以验证被动模式是否配置：</span><span class="sxs-lookup"><span data-stu-id="56794-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="56794-199">确认找到包含被动模式事件的最近事件：</span><span class="sxs-lookup"><span data-stu-id="56794-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![被动模式验证结果的图像](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="56794-201">运行以下命令检查是否安装了 Microsoft Defender AV：</span><span class="sxs-lookup"><span data-stu-id="56794-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="56794-202">如果结果是"指定服务作为已安装服务不存在"，则需要安装 Microsoft Defender AV。</span><span class="sxs-lookup"><span data-stu-id="56794-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="56794-203">有关详细信息，请参阅 [Windows 10 中的 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="56794-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="56794-204">有关如何使用组策略在 Windows 服务器上配置和管理 Microsoft Defender 防病毒的信息，请参阅使用组策略设置配置 [和管理 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="56794-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="56794-205">与 Azure 安全中心集成</span><span class="sxs-lookup"><span data-stu-id="56794-205">Integration with Azure Security Center</span></span>
<span data-ttu-id="56794-206">Defender for Endpoint 可以与 Azure 安全中心集成，以提供全面的 Windows 服务器保护解决方案。</span><span class="sxs-lookup"><span data-stu-id="56794-206">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="56794-207">通过此集成，Azure 安全中心可以使用 Defender for Endpoint 功能为 Windows 服务器提供改进的威胁检测。</span><span class="sxs-lookup"><span data-stu-id="56794-207">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="56794-208">此集成中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="56794-208">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="56794-209">自动载入 - 在载入到 Azure 安全中心的 Windows 服务器上自动启用 Defender for Endpoint 传感器。</span><span class="sxs-lookup"><span data-stu-id="56794-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="56794-210">有关 Azure 安全中心载入详细信息，请参阅载入 Azure 安全中心 [标准增强的安全性](https://docs.microsoft.com/azure/security-center/security-center-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="56794-210">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="56794-211">Azure Defender for Servers 和 Microsoft Defender for Endpoint 之间的集成已扩展为支持[Windows Server 2019 和 Windows 虚拟桌面 (WVD) 。 ](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="56794-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="56794-212">Azure 安全中心监视的 Windows 服务器还将在 Defender for Endpoint 中可用 - Azure 安全中心无缝连接到 Defender for Endpoint 租户，跨客户端和服务器提供单个视图。</span><span class="sxs-lookup"><span data-stu-id="56794-212">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="56794-213">此外，适用于终结点的 Defender 警报将在 Azure 安全中心控制台中提供。</span><span class="sxs-lookup"><span data-stu-id="56794-213">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="56794-214">服务器调查 - Azure 安全中心客户可以访问 Microsoft Defender 安全中心执行详细调查，以发现潜在泄露的范围。</span><span class="sxs-lookup"><span data-stu-id="56794-214">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="56794-215">当你使用 Azure 安全中心监视服务器时，会自动在美国为美国 (，在欧盟为欧洲和英国用户创建 Defender for Endpoint) 。</span><span class="sxs-lookup"><span data-stu-id="56794-215">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="56794-216">Defender for Endpoint 收集的数据存储在预配期间标识的租户地理位置中。</span><span class="sxs-lookup"><span data-stu-id="56794-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="56794-217">如果在使用 Azure 安全中心之前使用 Defender for Endpoint，则数据将存储在创建租户时指定的位置，即使以后与 Azure 安全中心集成。</span><span class="sxs-lookup"><span data-stu-id="56794-217">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="56794-218">配置后，你无法更改数据存储的位置。</span><span class="sxs-lookup"><span data-stu-id="56794-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="56794-219">如果需要将数据移动到其他位置，需要联系 Microsoft 支持部门来重置租户。</span><span class="sxs-lookup"><span data-stu-id="56794-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="56794-220">已针对 Office 365 GCC 客户禁用利用此集成的服务器终结点监视。</span><span class="sxs-lookup"><span data-stu-id="56794-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="56794-221">配置和更新 System Center Endpoint Protection 客户端</span><span class="sxs-lookup"><span data-stu-id="56794-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="56794-222">Defender for Endpoint 与 System Center Endpoint Protection 集成。</span><span class="sxs-lookup"><span data-stu-id="56794-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="56794-223">集成提供了恶意软件检测的可见性，并禁止潜在恶意文件或可疑恶意软件，从而停止攻击在组织中传播。</span><span class="sxs-lookup"><span data-stu-id="56794-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="56794-224">若要启用此集成，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="56794-224">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="56794-225">安装 [Endpoint Protection 客户端的 2017 年 1 月反恶意软件平台更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)。</span><span class="sxs-lookup"><span data-stu-id="56794-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="56794-226">[将 SCEP 客户端云保护服务成员身份配置为](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)**高级** 设置。</span><span class="sxs-lookup"><span data-stu-id="56794-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="56794-227">载出 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="56794-227">Offboard Windows servers</span></span>
<span data-ttu-id="56794-228">可以使用适用于 Windows 10 客户端设备的相同方法从 Windows Server (SAC) 、Windows Server 2019 和 Windows Server 2019 Core 版本上离开。</span><span class="sxs-lookup"><span data-stu-id="56794-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="56794-229">对于其他 Windows 服务器版本，你有两个选项从服务中离开 Windows 服务器：</span><span class="sxs-lookup"><span data-stu-id="56794-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="56794-230">卸载 MMA 代理</span><span class="sxs-lookup"><span data-stu-id="56794-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="56794-231">删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="56794-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="56794-232">"载出"会导致 Windows 服务器停止向门户发送传感器数据，但 Windows 服务器的数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="56794-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="56794-233">通过卸载 MMA 代理卸载 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="56794-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="56794-234">若要卸载 Windows 服务器，你可以从 Windows 服务器卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。</span><span class="sxs-lookup"><span data-stu-id="56794-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="56794-235">在离开代理后，Windows 服务器将不再将传感器数据发送到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="56794-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="56794-236">有关详细信息，请参阅禁用 [代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="56794-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="56794-237">删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="56794-237">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="56794-238">若要从 Windows 服务器中注销，可以使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="56794-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="56794-239">从 MMA 代理中删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="56794-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="56794-240">运行 PowerShell 命令以删除配置</span><span class="sxs-lookup"><span data-stu-id="56794-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="56794-241">从 MMA 代理中删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="56794-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="56794-242">在 **"Microsoft 监视代理属性"** 中，选择 **"Azure Log Analytics (OMS) "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56794-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="56794-243">选择"适用于终结点的 Defender"工作区，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="56794-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Microsoft 监视代理属性的图像](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="56794-245">运行 PowerShell 命令以删除配置</span><span class="sxs-lookup"><span data-stu-id="56794-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="56794-246">获取工作区 ID：</span><span class="sxs-lookup"><span data-stu-id="56794-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="56794-247">在导航窗格中，选择"**设置**  >  **""载入"。**</span><span class="sxs-lookup"><span data-stu-id="56794-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="56794-248">选择 **Windows Server 2008 R2 SP1、2012 R2 和 2016** 作为操作系统并获取工作区 ID：</span><span class="sxs-lookup"><span data-stu-id="56794-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Windows 服务器载入的图像](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="56794-250">打开提升的 PowerShell 并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="56794-250">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="56794-251">使用你获取的工作区 ID 并替换 `WorkspaceID` ：</span><span class="sxs-lookup"><span data-stu-id="56794-251">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a><span data-ttu-id="56794-252">相关主题</span><span class="sxs-lookup"><span data-stu-id="56794-252">Related topics</span></span>
- [<span data-ttu-id="56794-253">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="56794-253">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="56794-254">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="56794-254">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="56794-255">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="56794-255">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="56794-256">在新载入的适用于终结点的 Defender 设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="56794-256">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="56794-257">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="56794-257">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
