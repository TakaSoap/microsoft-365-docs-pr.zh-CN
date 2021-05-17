---
title: 报告 Microsoft Defender for Endpoint ASR 规则并排除故障
description: 本主题介绍如何报告 Microsoft Defender for Endpoint ASR 规则并排除故障
keywords: 攻击面减少规则， asr， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， microsoft defender 终结点
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246012"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="1c1ce-104">针对 ATP ASR 规则报告 Microsoft Defender 并排除故障</span><span class="sxs-lookup"><span data-stu-id="1c1ce-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c1ce-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1c1ce-105">**Applies to:**</span></span>

- [<span data-ttu-id="1c1ce-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1c1ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1c1ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c1ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1c1ce-108">安全Microsoft 365中心是跨 Microsoft 标识、数据、设备、应用和基础结构监视和管理安全性的新界面。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="1c1ce-109">可在此处轻松查看组织的安全运行状况、配置设备、用户和应用，并获取可疑活动的警报。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="1c1ce-110">Microsoft 365 安全中心旨在帮助安全管理员和安全操作团队更好地管理和保护其组织。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="1c1ce-111">请访问 Microsoft 365安全中心 https://security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="1c1ce-112">在Microsoft 365安全中心，我们将提供你当前 ASR 规则配置和您资产中的事件的完整外观。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="1c1ce-113">请注意，你的设备必须载入到 Microsoft Defender for Endpoint 服务中，以填充这些报告。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="1c1ce-114">下面是报告设备攻击面减少Microsoft 365下的安全 (  >    >  **屏幕截图**) 。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="1c1ce-115">在设备级别 **，从攻击** 面减少规则 **窗格中选择配置** 。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="1c1ce-116">将显示以下屏幕，可在其中选择特定设备并检查其单独的 ASR 规则配置。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR 规则屏幕":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="1c1ce-118">Microsoft Defender for Endpoint – 高级搜寻</span><span class="sxs-lookup"><span data-stu-id="1c1ce-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="1c1ce-119">Microsoft Defender for Endpoint 的最强大功能之一是高级搜寻。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="1c1ce-120">如果你不熟悉高级搜寻，请参阅使用高级搜寻主动 [搜寻威胁](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="1c1ce-121">高级搜寻是基于查询的 (Kusto 查询语言) 威胁搜寻工具，允许你浏览从所有计算机收集的最多 30 天的已捕获 (原始)  (EDR) 数据。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="1c1ce-122">通过高级搜寻，你可以主动检查事件以查找有趣的指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="1c1ce-123">灵活访问数据有助于不受约束地搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="1c1ce-124">通过高级搜寻，可以提取 ASR 规则信息、创建报告，并获取有关给定 ASR 规则审核或阻止事件的上下文的深入信息。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="1c1ce-125">ASR 规则事件可从应用程序高级搜寻部分中的 DeviceEvents 表中Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="1c1ce-126">例如，如下所示的简单查询可以报告过去 30 天内将 ASR 规则作为数据源的所有事件，并按 ActionType 计数汇总这些事件，在这种情况下，它将是 ASR 规则的实际代码名。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高级搜寻查询":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="高级搜寻屏幕":::

<span data-ttu-id="1c1ce-129">借助高级搜寻，你可以使查询符合自己的喜好，以便你可以查看发生的情况，无论你是想要在单台计算机中定位某些内容，还是想要从整个环境中提取见解。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="1c1ce-130">Microsoft Defender for Endpoint 计算机时间线</span><span class="sxs-lookup"><span data-stu-id="1c1ce-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="1c1ce-131">Microsoft Defender for Endpoint 计算机时间线是高级搜寻的替代方法，但范围较窄。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="1c1ce-132">你可以查看过去六个月内在 Microsoft Defender 安全中心 中收集的所有设备事件，只需进入计算机列表，选择给定计算机，然后单击时间线选项卡即可。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="1c1ce-133">下图是给定终结点上这些事件的时间线视图的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="1c1ce-134">从此视图中，可以基于右侧窗格中的任何事件组筛选事件列表。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="1c1ce-135">还可以在查看警报和滚动历史时间线时启用或禁用已标记和详细事件。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="microsoft defender 安全中心时间线":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="1c1ce-137">如何解决 ASR 规则问题？</span><span class="sxs-lookup"><span data-stu-id="1c1ce-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="1c1ce-138">第一种也是最直接的方法就是在本地在 Windows 设备上检查哪些 ASR 规则已启用 (其配置) 是使用 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="1c1ce-139">下面是一些其他一些信息源，Windows ASR 规则的影响和操作疑难解答。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="1c1ce-140">查询哪些规则处于活动状态</span><span class="sxs-lookup"><span data-stu-id="1c1ce-140">Querying which rules are active</span></span>
<span data-ttu-id="1c1ce-141">确定 ASR 规则是否已启用的最简单方法之一是，通过 PowerShell cmdlet Get-MpPreference。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="1c1ce-142">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="1c1ce-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="get mppreference 脚本":::

<span data-ttu-id="1c1ce-144">有多个 ASR 规则处于活动状态，具有不同的配置操作。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="1c1ce-145">若要展开有关 ASR 规则的上述信息，可以使用属性 **AttackSurfaceReductionRules_Ids** 和/或 **AttackSurfaceReductionRules_Actions**。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="1c1ce-146">示例：</span><span class="sxs-lookup"><span data-stu-id="1c1ce-146">Example:</span></span>

<span data-ttu-id="1c1ce-147">*Get-MPPreference |Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="1c1ce-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="get mpreference 示例":::

<span data-ttu-id="1c1ce-149">上面显示了 ASR 规则的所有设置不同于 0 的 ID， (未配置) 。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="1c1ce-150">然后，下一步是列出每个 (配置) 的"阻止"或"审核"操作。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="1c1ce-151">*Get-MPPreference |Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="1c1ce-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference 示例 2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="1c1ce-153">查询阻止和审核事件</span><span class="sxs-lookup"><span data-stu-id="1c1ce-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="1c1ce-154">可以在活动日志中查看 ASR 规则Windows Defender事件。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="1c1ce-155">若要访问它，请Windows事件查看器，并浏览到应用程序和服务日志  >  **Microsoft** Windows Windows Defender  >    >    >  **操作**。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="事件查看器 scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="1c1ce-157">Microsoft Defender 恶意软件保护日志</span><span class="sxs-lookup"><span data-stu-id="1c1ce-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="1c1ce-158">您还可以通过称为 的专用命令行工具查看规则Microsoft Defender 防病毒，该工具可用于管理和配置任务，并 `*mpcmdrun.exe*` 根据需要自动执行任务。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="1c1ce-159">您可以在 *%ProgramFiles%\Windows Defender\MpCmdRun.exe找到此实用工具*。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="1c1ce-160">必须从提升的命令提示符运行 (，即以管理员角色) 。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="1c1ce-161">若要生成支持信息，请键入 *MpCmdRun.exe -getfiles*。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="1c1ce-162">一段时间之后，多个日志将打包到存档 (MpSupportFiles.cab) *C：\ProgramData\Microsoft\Windows Defender\Support 中提供*。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="恶意软件保护日志":::

<span data-ttu-id="1c1ce-164">提取该存档，你将具有许多可用于故障排除的文件。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="1c1ce-165">最相关的文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c1ce-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="1c1ce-166">**MPOperationalEvents.txt** - 此文件包含事件查看器中有关Windows Defender日志的相同级别的信息。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="1c1ce-167">**MPRegistry.txt** – 在此文件中，你可以分析从捕获支持日志Windows Defender所有当前配置。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="1c1ce-168">**MPLog.txt** – 此日志包含有关项目的所有操作Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="1c1ce-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
