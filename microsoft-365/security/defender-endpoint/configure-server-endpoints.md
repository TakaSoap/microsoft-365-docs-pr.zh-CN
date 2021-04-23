---
title: 将 Windows 服务器载入 Microsoft Defender for Endpoint 服务
description: 载入 Windows 服务器，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器。
keywords: 载入服务器， 服务器， 2012r2， 2016， 2019， 服务器载入， 设备管理， 配置适用于终结点服务器的 Microsoft Defender， 载入适用于终结点服务器的 Microsoft Defender， 载入适用于终结点服务器的 Microsoft Defender
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
ms.openlocfilehash: 17aca5fb388aef26504902ee63b22410420c8827
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952484"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="8514d-104">将 Windows 服务器载入 Microsoft Defender for Endpoint 服务</span><span class="sxs-lookup"><span data-stu-id="8514d-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8514d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8514d-105">**Applies to:**</span></span>

- <span data-ttu-id="8514d-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="8514d-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="8514d-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8514d-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="8514d-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8514d-108">Windows Server 2016</span></span>
- <span data-ttu-id="8514d-109">Windows Server (SAC) 版本 1803 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8514d-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="8514d-110">Windows Server 2019 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8514d-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="8514d-111">Windows Server 2019 核心版本</span><span class="sxs-lookup"><span data-stu-id="8514d-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="8514d-112">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="8514d-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8514d-113">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8514d-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="8514d-114">Defender for Endpoint 扩展了支持，还包括 Windows Server 操作系统。</span><span class="sxs-lookup"><span data-stu-id="8514d-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="8514d-115">此支持通过 Microsoft Defender 安全中心控制台无缝提供高级攻击检测和调查功能。</span><span class="sxs-lookup"><span data-stu-id="8514d-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="8514d-116">有关许可和基础结构需要满足的实际指导，请参阅使用 Defender for Endpoint [保护 Windows 服务器](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。</span><span class="sxs-lookup"><span data-stu-id="8514d-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="8514d-117">有关如何下载和使用 Windows 服务器的 Windows 安全基线的指南，请参阅 [Windows 安全基线](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="8514d-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="8514d-118">Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8514d-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="8514d-119">可以使用以下任一选项将 Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016 载入 Defender for Endpoint：</span><span class="sxs-lookup"><span data-stu-id="8514d-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="8514d-120">**选项 1：**[通过安装和配置 Microsoft](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) Monitoring Agent (MMA) </span><span class="sxs-lookup"><span data-stu-id="8514d-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="8514d-121">**选项 2：**[通过 Azure 安全中心载入](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="8514d-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="8514d-122">**选项 3：**[通过 Microsoft Endpoint Manager 版本 2002 及更高版本载入](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="8514d-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="8514d-123">使用提供的任一选项完成载入步骤后，你需要配置和更新 [System Center Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="8514d-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="8514d-124">每个节点都需要 Defender for Endpoint 独立服务器许可证，才能通过 Microsoft 监视代理 (选项 1) 或 Microsoft Endpoint Manager (选项 3) 载入 Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="8514d-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="8514d-125">或者，每个节点都需要 Azure Defender for Servers 许可证，才能通过 Azure 安全中心 (选项 2) 载入 Windows 服务器，请参阅 [Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services)中提供的支持功能。</span><span class="sxs-lookup"><span data-stu-id="8514d-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="8514d-126">选项 1：通过安装和配置 Microsoft Monitoring Agent (MMA) </span><span class="sxs-lookup"><span data-stu-id="8514d-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="8514d-127">你需要为 Windows 服务器安装和配置 MMA，以将传感器数据报告给 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8514d-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="8514d-128">有关详细信息，请参阅使用 [Azure Log Analytics 代理收集日志数据](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="8514d-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="8514d-129">如果你已在使用 System Center Operations Manager (SCOM) 或 Azure Monitor (以前称为 Operations Management Suite (OMS) ) ，请附加 Microsoft Monitoring Agent (MMA) 以通过多托管支持向 Defender for Endpoint 工作区报告。</span><span class="sxs-lookup"><span data-stu-id="8514d-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="8514d-130">通常，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8514d-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="8514d-131">满足开始之前部分 **中列出的载入** 要求。</span><span class="sxs-lookup"><span data-stu-id="8514d-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="8514d-132">从 Microsoft Defender 安全中心打开服务器监视。</span><span class="sxs-lookup"><span data-stu-id="8514d-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="8514d-133">安装和配置服务器的 MMA，以将传感器数据报告给 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8514d-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="8514d-134">配置和更新 System Center Endpoint Protection 客户端。</span><span class="sxs-lookup"><span data-stu-id="8514d-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="8514d-135">载入设备后，你可以选择运行检测测试，以验证它是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="8514d-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="8514d-136">有关详细信息，请参阅对新载入的 Defender 终结点终结点运行检测 [测试](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="8514d-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="8514d-137">准备工作</span><span class="sxs-lookup"><span data-stu-id="8514d-137">Before you begin</span></span>

<span data-ttu-id="8514d-138">执行以下步骤以满足载入要求：</span><span class="sxs-lookup"><span data-stu-id="8514d-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="8514d-139">对于 Windows Server 2008 R2 SP1 或 Windows Server 2012 R2，请确保安装以下修补程序：</span><span class="sxs-lookup"><span data-stu-id="8514d-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="8514d-140">客户体验和诊断遥测更新</span><span class="sxs-lookup"><span data-stu-id="8514d-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="8514d-141">对于 Windows Server 2008 R2 SP1，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="8514d-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="8514d-142">安装 [2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="8514d-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="8514d-143">安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="8514d-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="8514d-144">如果使用 SCCM 管理 Windows Server 2008 R2 SP1，SCCM 客户端代理将安装 .Net Framework 4.5.2。</span><span class="sxs-lookup"><span data-stu-id="8514d-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="8514d-145">因此，无需安装 .NET framework 4.5 (或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="8514d-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="8514d-146">对于 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2：配置和更新 [System Center Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="8514d-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="8514d-147">只有当组织使用 System Center Endpoint Protection (SCEP) 并且要载入 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2 时，才需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="8514d-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="8514d-148">安装和配置 Microsoft 监视代理 (MMA) 向 Microsoft Defender for Endpoint 报告传感器数据</span><span class="sxs-lookup"><span data-stu-id="8514d-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="8514d-149">下载代理设置文件 [：Windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603)。</span><span class="sxs-lookup"><span data-stu-id="8514d-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="8514d-150">使用在上一过程中获取的 Workspace ID 和 Workspace 密钥，选择以下任一安装方法在 Windows 服务器上安装代理：</span><span class="sxs-lookup"><span data-stu-id="8514d-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="8514d-151">[使用安装程序 手动安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。</span><span class="sxs-lookup"><span data-stu-id="8514d-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="8514d-152">在"**代理设置选项"** 页上，选择"将代理 **连接到 Azure Log Analytics (OMS) "。**</span><span class="sxs-lookup"><span data-stu-id="8514d-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="8514d-153">[使用命令行 安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。</span><span class="sxs-lookup"><span data-stu-id="8514d-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="8514d-154">[使用脚本 配置代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。</span><span class="sxs-lookup"><span data-stu-id="8514d-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="8514d-155">如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。</span><span class="sxs-lookup"><span data-stu-id="8514d-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="8514d-156">根据需要配置 Windows 服务器代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="8514d-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="8514d-157">如果你的服务器需要使用代理与 Defender for Endpoint 通信，请使用以下方法之一将 MMA 配置为使用代理服务器：</span><span class="sxs-lookup"><span data-stu-id="8514d-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="8514d-158">配置 MMA 以使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="8514d-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="8514d-159">配置 Windows 以将代理服务器用于所有连接</span><span class="sxs-lookup"><span data-stu-id="8514d-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="8514d-160">如果代理或防火墙已在使用中，请确保服务器可以直接访问所有 Microsoft Defender for Endpoint 服务 URL，且无需 SSL 拦截。</span><span class="sxs-lookup"><span data-stu-id="8514d-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="8514d-161">有关详细信息，请参阅启用对 [Defender for Endpoint 服务 URL 的访问](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="8514d-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="8514d-162">使用 SSL 拦截将阻止系统与 Defender for Endpoint 服务通信。</span><span class="sxs-lookup"><span data-stu-id="8514d-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="8514d-163">完成后，你应该在一小时内在门户中看到已载入的 Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="8514d-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="8514d-164">选项 2：通过 Azure 安全中心载入 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="8514d-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="8514d-165">在 Microsoft Defender 安全中心导航窗格中，**选择设置**  >  **设备管理**  >  **载入**。</span><span class="sxs-lookup"><span data-stu-id="8514d-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="8514d-166">选择 **Windows Server 2008 R2 SP1、2012 R2 和 2016** 作为操作系统。</span><span class="sxs-lookup"><span data-stu-id="8514d-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="8514d-167">单击 **Azure 安全中心中的载入服务器**。</span><span class="sxs-lookup"><span data-stu-id="8514d-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="8514d-168">按照使用 Azure Defender 的 [Microsoft Defender for Endpoint](https://docs.microsoft.com/azure/security-center/security-center-wdatp) 中的载入说明操作，如果你使用的是 Azure ARC，请按照启用适用于终结点集成的 Microsoft Defender [中的载入说明操作](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)。</span><span class="sxs-lookup"><span data-stu-id="8514d-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="8514d-169">完成载入步骤后，你需要配置和更新 System Center [Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="8514d-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="8514d-170">若要通过 Azure Defender for Servers 载入以正常工作，服务器必须在 Microsoft Monitoring Agent (MMA) 配置相应的工作区和密钥。</span><span class="sxs-lookup"><span data-stu-id="8514d-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="8514d-171">配置后，相应的云管理包将部署在计算机中，并且传感器 (MsSenseS.exe) 将部署和启动。</span><span class="sxs-lookup"><span data-stu-id="8514d-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="8514d-172">如果服务器配置为使用 OMS 网关服务器作为代理，则也要求这样做。</span><span class="sxs-lookup"><span data-stu-id="8514d-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="8514d-173">选项 3：通过 Microsoft Endpoint Manager 版本 2002 及更高版本载入 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="8514d-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="8514d-174">可以使用 Microsoft Endpoint Manager Windows Server 2012版本 2002 和更高版本载入 R2 和 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="8514d-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="8514d-175">有关详细信息，请参阅[Microsoft Endpoint Manager current branch 中的 Microsoft Defender for Endpoint。](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="8514d-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="8514d-176">完成载入步骤后，你需要配置和更新 System Center [Endpoint Protection 客户端](#configure-and-update-system-center-endpoint-protection-clients)。</span><span class="sxs-lookup"><span data-stu-id="8514d-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="8514d-177">Windows Server (SAC) 版本 1803、Windows Server 2019 和 Windows Server 2019 Core 版本</span><span class="sxs-lookup"><span data-stu-id="8514d-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="8514d-178">可以使用以下部署方法载入 Windows Server (SAC) 版本 1803、Windows Server 2019 或 Windows Server 2019 Core 版本：</span><span class="sxs-lookup"><span data-stu-id="8514d-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="8514d-179">本地脚本</span><span class="sxs-lookup"><span data-stu-id="8514d-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="8514d-180">组策略</span><span class="sxs-lookup"><span data-stu-id="8514d-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="8514d-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8514d-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="8514d-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="8514d-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="8514d-183">用于非永久性设备的 VDI 载入脚本</span><span class="sxs-lookup"><span data-stu-id="8514d-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="8514d-184">通过 Microsoft Endpoint Manager 的 Windows Server 2019 载入程序包当前附带了一个脚本。</span><span class="sxs-lookup"><span data-stu-id="8514d-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="8514d-185">若要详细了解如何在 Configuration Manager 中部署脚本，请参阅 Configuration [Manager 中的程序包和程序](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="8514d-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="8514d-186">本地脚本适用于概念证明，但不应用于生产部署。</span><span class="sxs-lookup"><span data-stu-id="8514d-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="8514d-187">对于生产部署，我们建议使用组策略或 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="8514d-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="8514d-188">对 Windows Server 的支持可更深入地了解服务器活动、内核和内存攻击检测的范围，并启用响应操作。</span><span class="sxs-lookup"><span data-stu-id="8514d-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="8514d-189">使用适用于 Windows 10 设备的相同工具和方法在 Windows 服务器上配置适用于终结点载入设置的 Defender。</span><span class="sxs-lookup"><span data-stu-id="8514d-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="8514d-190">有关详细信息，请参阅载入 [Windows 10 设备](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="8514d-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="8514d-191">如果你运行的是第三方反恶意软件解决方案，则需要应用以下 Microsoft Defender AV 被动模式设置。</span><span class="sxs-lookup"><span data-stu-id="8514d-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="8514d-192">验证是否正确配置了它：</span><span class="sxs-lookup"><span data-stu-id="8514d-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="8514d-193">设置以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="8514d-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="8514d-194">路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="8514d-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="8514d-195">名称：ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="8514d-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="8514d-196">类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="8514d-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="8514d-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="8514d-197">Value: 1</span></span>

    1. <span data-ttu-id="8514d-198">运行以下 PowerShell 命令以验证被动模式是否配置：</span><span class="sxs-lookup"><span data-stu-id="8514d-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="8514d-199">确认找到包含被动模式事件的最近事件：</span><span class="sxs-lookup"><span data-stu-id="8514d-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![被动模式验证结果的图像](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="8514d-201">运行以下命令检查是否安装了 Microsoft Defender AV：</span><span class="sxs-lookup"><span data-stu-id="8514d-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="8514d-202">如果结果是"指定服务作为已安装服务不存在"，则需要安装 Microsoft Defender AV。</span><span class="sxs-lookup"><span data-stu-id="8514d-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="8514d-203">有关详细信息，请参阅 [Windows 10 中的 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="8514d-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="8514d-204">有关如何使用组策略在 Windows 服务器上配置和管理 Microsoft Defender 防病毒的信息，请参阅使用组策略设置配置 [和管理 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="8514d-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="8514d-205">与 Azure Defender 集成</span><span class="sxs-lookup"><span data-stu-id="8514d-205">Integration with Azure Defender</span></span>

<span data-ttu-id="8514d-206">Defender for Endpoint 可以与 Azure Defender 集成，以提供全面的 Windows 服务器保护解决方案。</span><span class="sxs-lookup"><span data-stu-id="8514d-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="8514d-207">通过此集成，Azure Defender 可以使用 Defender for Endpoint 功能为 Windows 服务器提供改进的威胁检测。</span><span class="sxs-lookup"><span data-stu-id="8514d-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="8514d-208">此集成中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="8514d-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="8514d-209">自动载入 - 适用于终结点的 Defender 传感器在载入到 Azure Defender 的 Windows 服务器上自动启用。</span><span class="sxs-lookup"><span data-stu-id="8514d-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="8514d-210">有关 Azure Defender 载入详细信息，请参阅使用集成的 [Microsoft Defender for Endpoint 许可证](https://docs.microsoft.com/azure/security-center/security-center-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="8514d-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8514d-211">Azure Defender for Servers 和 Microsoft Defender for Endpoint 之间的集成已扩展为支持[Windows Server 2019 和 Windows 虚拟桌面 (WVD) 。 ](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="8514d-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="8514d-212">受 Azure Defender 监视的 Windows 服务器还将在 Defender for Endpoint 中可用 - Azure Defender 无缝连接到 Defender for Endpoint 租户，跨客户端和服务器提供单个视图。</span><span class="sxs-lookup"><span data-stu-id="8514d-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="8514d-213">此外，适用于终结点的 Defender 警报将在 Azure Defender 控制台中提供。</span><span class="sxs-lookup"><span data-stu-id="8514d-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="8514d-214">服务器调查 - Azure Defender 客户可以访问 Microsoft Defender 安全中心执行详细调查，以发现潜在泄露的范围。</span><span class="sxs-lookup"><span data-stu-id="8514d-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="8514d-215">当你使用 Azure Defender 监视服务器时，会自动在美国为美国 (，在欧盟为欧洲用户和英国用户创建 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="8514d-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="8514d-216">Defender for Endpoint 收集的数据存储在预配期间标识的租户地理位置中。</span><span class="sxs-lookup"><span data-stu-id="8514d-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="8514d-217">如果在使用 Azure Defender 之前使用 Defender for Endpoint，则数据将存储在创建租户时指定的位置，即使以后与 Azure Defender 集成。</span><span class="sxs-lookup"><span data-stu-id="8514d-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="8514d-218">配置后，你无法更改数据存储的位置。</span><span class="sxs-lookup"><span data-stu-id="8514d-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="8514d-219">如果需要将数据移动到其他位置，需要联系 Microsoft 支持部门来重置租户。</span><span class="sxs-lookup"><span data-stu-id="8514d-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="8514d-220">已针对 Office 365 GCC 客户禁用利用此集成的服务器终结点监视。</span><span class="sxs-lookup"><span data-stu-id="8514d-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="8514d-221">配置和更新 System Center Endpoint Protection 客户端</span><span class="sxs-lookup"><span data-stu-id="8514d-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="8514d-222">Defender for Endpoint 与 System Center Endpoint Protection 集成。</span><span class="sxs-lookup"><span data-stu-id="8514d-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="8514d-223">集成提供了恶意软件检测的可见性，并禁止潜在恶意文件或可疑恶意软件，从而停止攻击在组织中传播。</span><span class="sxs-lookup"><span data-stu-id="8514d-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="8514d-224">若要启用此集成，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8514d-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="8514d-225">安装 [Endpoint Protection 客户端的 2017 年 1 月反恶意软件平台更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)。</span><span class="sxs-lookup"><span data-stu-id="8514d-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="8514d-226">[将 SCEP 客户端云保护服务成员身份配置为](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)**高级** 设置。</span><span class="sxs-lookup"><span data-stu-id="8514d-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="8514d-227">载出 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="8514d-227">Offboard Windows servers</span></span>

<span data-ttu-id="8514d-228">可以使用适用于 Windows 10 客户端设备的相同方法从 Windows Server (SAC) 、Windows Server 2019 和 Windows Server 2019 Core 版本上离开。</span><span class="sxs-lookup"><span data-stu-id="8514d-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="8514d-229">对于其他 Windows 服务器版本，你有两个选项从服务中离开 Windows 服务器：</span><span class="sxs-lookup"><span data-stu-id="8514d-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="8514d-230">卸载 MMA 代理</span><span class="sxs-lookup"><span data-stu-id="8514d-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="8514d-231">删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="8514d-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="8514d-232">"载出"会导致 Windows 服务器停止向门户发送传感器数据，但 Windows 服务器的数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="8514d-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="8514d-233">通过卸载 MMA 代理卸载 Windows 服务器</span><span class="sxs-lookup"><span data-stu-id="8514d-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="8514d-234">若要卸载 Windows 服务器，你可以从 Windows 服务器卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。</span><span class="sxs-lookup"><span data-stu-id="8514d-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="8514d-235">在离开代理后，Windows 服务器将不再将传感器数据发送到 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8514d-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="8514d-236">有关详细信息，请参阅禁用 [代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="8514d-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="8514d-237">删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="8514d-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="8514d-238">若要从 Windows 服务器中注销，可以使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="8514d-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="8514d-239">从 MMA 代理中删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="8514d-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="8514d-240">运行 PowerShell 命令以删除配置</span><span class="sxs-lookup"><span data-stu-id="8514d-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="8514d-241">从 MMA 代理中删除 Defender for Endpoint 工作区配置</span><span class="sxs-lookup"><span data-stu-id="8514d-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="8514d-242">在 **"Microsoft 监视代理属性"** 中，选择 **"Azure Log Analytics (OMS) "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8514d-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="8514d-243">选择"适用于终结点的 Defender"工作区，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="8514d-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Microsoft 监视代理属性的图像](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="8514d-245">运行 PowerShell 命令以删除配置</span><span class="sxs-lookup"><span data-stu-id="8514d-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="8514d-246">获取工作区 ID：</span><span class="sxs-lookup"><span data-stu-id="8514d-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="8514d-247">在导航窗格中，选择"**设置**  >  **""载入"。**</span><span class="sxs-lookup"><span data-stu-id="8514d-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="8514d-248">选择 **Windows Server 2008 R2 SP1、2012 R2 和 2016** 作为操作系统并获取工作区 ID：</span><span class="sxs-lookup"><span data-stu-id="8514d-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Windows 服务器载入的图像](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="8514d-250&quot;>打开提升的 PowerShell 并运行以下命令。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8514d-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;8514d-251&quot;>使用你获取的工作区 ID 并替换 `WorkspaceID` ：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;8514d-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="8514d-252">载入服务器，无管理解决方案</span><span class="sxs-lookup"><span data-stu-id="8514d-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="8514d-253">使用组策略</span><span class="sxs-lookup"><span data-stu-id="8514d-253">Using Group Policy</span></span>

<span data-ttu-id="8514d-254">**步骤 1：创建复制到服务器所需的文件。**</span><span class="sxs-lookup"><span data-stu-id="8514d-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="8514d-255">导航到 c：\windows\sysvol\domain\scripts (其中一个域控制器上需要更改控件。) </span><span class="sxs-lookup"><span data-stu-id="8514d-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="8514d-256">创建一个名为 MMA 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8514d-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="8514d-257">下载以下内容，并放置到 MMA 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="8514d-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="8514d-258">**Windows Server 2008 R2 和 (R2 Windows Server 2012遥测)**</span><span class="sxs-lookup"><span data-stu-id="8514d-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="8514d-259">对于 Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="8514d-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="8514d-260">对于 Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="8514d-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="8514d-261">本文假定你正在使用基于 x64 的服务器 (MMA 代理 .exe x64 [新 SHA-2](https://go.microsoft.com/fwlink/?LinkId=828603) 兼容) </span><span class="sxs-lookup"><span data-stu-id="8514d-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="8514d-262">**步骤 2：使用记事本工具创建 (DeployMMA.cmd)** 将以下行添加到 cmd 文件。</span><span class="sxs-lookup"><span data-stu-id="8514d-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="8514d-263">请注意，你将需要工作区 ID 和密钥。</span><span class="sxs-lookup"><span data-stu-id="8514d-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="8514d-264">组策略配置</span><span class="sxs-lookup"><span data-stu-id="8514d-264">Group Policy Configuration</span></span>

<span data-ttu-id="8514d-265">创建专用于载入设备的新组策略，例如"适用于终结点载入的 Microsoft Defender"。</span><span class="sxs-lookup"><span data-stu-id="8514d-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="8514d-266">创建名为"c：\windows\MMA"的组策略文件夹</span><span class="sxs-lookup"><span data-stu-id="8514d-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="folders":::

    <span data-ttu-id="8514d-268">**这将在应用 GPO 的每台服务器上添加新文件夹（称为 MMA）并存储在 c：\windows 中。这将包含 MMA 的安装文件、必备组件和安装脚本。**</span><span class="sxs-lookup"><span data-stu-id="8514d-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="8514d-269">为存储在 Net 登录中的每个文件创建组策略文件首选项。</span><span class="sxs-lookup"><span data-stu-id="8514d-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="组策略图像 1":::

<span data-ttu-id="8514d-271">它将文件从 DOMAIN\NETLOGON\MMA\filename 复制到 C：\windows\MMA\filename ，因此安装文件是服务器 **的本地文件**：</span><span class="sxs-lookup"><span data-stu-id="8514d-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="部署 mma cmd":::

<span data-ttu-id="8514d-273">对于两个 KB (一个针对 Windows Server 2008R2/Windows 7，另一个针对 Windows Server 2012 R2) 重复此过程，但在 COMMON 选项卡上创建项目级别目标，因此文件仅复制到作用域中相应的平台/操作系统版本：</span><span class="sxs-lookup"><span data-stu-id="8514d-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="目标编辑器":::

- <span data-ttu-id="8514d-275">对于 Windows Server 2008 R2，你需要 (并且它将仅向下复制) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="8514d-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="8514d-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="8514d-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="8514d-277">完成此操作后，你需要创建启动脚本策略：</span><span class="sxs-lookup"><span data-stu-id="8514d-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="启动属性":::

<span data-ttu-id="8514d-279">要在此处运行的文件的名称为 c：\windows\MMA\DeployMMA.cmd。</span><span class="sxs-lookup"><span data-stu-id="8514d-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="8514d-280">在启动过程中重新启动服务器后，它将安装客户体验更新和诊断遥测 KB，然后安装 MMA 代理，同时设置工作区 ID 和密钥，并且将载入服务器。</span><span class="sxs-lookup"><span data-stu-id="8514d-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="8514d-281">如果不想重新启动所有 **服务器** ，您也可以使用即时任务运行 deployMMA.cmd。</span><span class="sxs-lookup"><span data-stu-id="8514d-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="8514d-282">这分两个阶段完成。</span><span class="sxs-lookup"><span data-stu-id="8514d-282">This could be done in two phases.</span></span> <span data-ttu-id="8514d-283">首先 **在** GPO 中创建文件和文件夹 – 为系统提供时间来确保已应用 GPO，并且所有服务器都有安装文件。</span><span class="sxs-lookup"><span data-stu-id="8514d-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="8514d-284">然后，添加即时任务。</span><span class="sxs-lookup"><span data-stu-id="8514d-284">Then, add the immediate task.</span></span> <span data-ttu-id="8514d-285">这将获得相同的结果，而无需重新启动。</span><span class="sxs-lookup"><span data-stu-id="8514d-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="8514d-286">由于脚本具有退出方法，并且如果安装了 MMA，将不会重新运行，因此，您还可以使用每日计划任务来实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="8514d-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="8514d-287">与 Configuration Manager 合规性策略类似，它每天都会检查以确保 MMA 存在。</span><span class="sxs-lookup"><span data-stu-id="8514d-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="计划任务":::

:::image type="content" source="images/newtaskprops.png" alt-text="新任务属性":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="部署 mma 下载属性":::

:::image type="content" source="images/tasksch.png" alt-text="任务计划程序":::

<span data-ttu-id="8514d-292">如 Server 的载入文档特别围绕 Server 2008 R2 所述，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="8514d-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="8514d-293">对于 Windows Server 2008 R2 PS1，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="8514d-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="8514d-294">安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="8514d-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="8514d-295">安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="8514d-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="8514d-296">请在载入 Windows Server 2008 R2 之前检查这些 KB 是否存在：如果你还没有配置管理器管理服务器，此过程允许你载入所有服务器。</span><span class="sxs-lookup"><span data-stu-id="8514d-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8514d-297">相关主题</span><span class="sxs-lookup"><span data-stu-id="8514d-297">Related topics</span></span>

- [<span data-ttu-id="8514d-298">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="8514d-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="8514d-299">载入非 Windows 设备</span><span class="sxs-lookup"><span data-stu-id="8514d-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="8514d-300">配置代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="8514d-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="8514d-301">在新载入的适用于终结点的 Defender 设备上运行检测测试</span><span class="sxs-lookup"><span data-stu-id="8514d-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="8514d-302">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="8514d-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
