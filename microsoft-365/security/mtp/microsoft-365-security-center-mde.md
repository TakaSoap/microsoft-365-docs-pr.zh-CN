---
title: Microsoft 365 安全中心中的 Microsoft Defender for Endpoint
description: 了解从 Microsoft Defender 安全中心到 Microsoft 365 安全中心的更改
keywords: Microsoft 365 安全中心、OATP、MDATP、MDO、MDE、单窗格、聚合门户、安全门户、Defender 安全门户入门
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 1fd32aa688256f1ac8e63eec902c3a18b2143f09
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242910"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="b9611-104">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b9611-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="b9611-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b9611-105">**Applies to:**</span></span>

- [<span data-ttu-id="b9611-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9611-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="b9611-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b9611-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b9611-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b9611-108">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

<span data-ttu-id="b9611-109">改进的 [Microsoft 365](overview-security-center.md) 安全中心结合了保护、检测、 [https://security.microsoft.com](https://security.microsoft.com) 调查和响应电子邮件、协作、标识和设备威胁的管理功能。</span><span class="sxs-lookup"><span data-stu-id="b9611-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="b9611-110">此安全中心将现有 Microsoft 安全门户（包括 Microsoft Defender 安全中心和 Office 365 安全与合规中心）&功能。</span><span class="sxs-lookup"><span data-stu-id="b9611-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="b9611-111">如果你熟悉 Microsoft Defender 安全中心，本文有助于介绍改进的 Microsoft 365 安全中心中的一些更改和改进。</span><span class="sxs-lookup"><span data-stu-id="b9611-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="b9611-112">但是，要注意一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="b9611-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="b9611-113">过去 [，Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) 一直是 Microsoft Defender for Endpoint 的主页。</span><span class="sxs-lookup"><span data-stu-id="b9611-113">Historically, the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b9611-114">企业安全团队已使用它监视和帮助响应潜在高级永久性威胁活动或数据泄露的警报。</span><span class="sxs-lookup"><span data-stu-id="b9611-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="b9611-115">为了帮助减少门户数量，Microsoft 365 安全中心将是监视和管理 Microsoft 标识、数据、设备、应用和基础结构的安全性的主页。</span><span class="sxs-lookup"><span data-stu-id="b9611-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="b9611-116">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint 支持以在 Microsoft Defender 安全中心授予访问权限的方式向托管安全服务提供商 [ (MSSP) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 授予 [访问权限](mssp-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b9611-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="b9611-117">你在 Microsoft 365 安全中心看到的情况取决于您当前的订阅。</span><span class="sxs-lookup"><span data-stu-id="b9611-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="b9611-118">例如，如果你没有适用于 Office 365 的 Microsoft Defender 许可证，将不会显示"电子邮件&协作"部分。</span><span class="sxs-lookup"><span data-stu-id="b9611-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

<span data-ttu-id="b9611-119">查看改进的 Microsoft 365 安全 [https://security.microsoft.com](https://security.microsoft.com) 中心：</span><span class="sxs-lookup"><span data-stu-id="b9611-119">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="b9611-120">详细了解优势 [：Microsoft 365 安全中心概述](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="b9611-120">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="b9611-121">更改内容</span><span class="sxs-lookup"><span data-stu-id="b9611-121">What's changed</span></span>

<span data-ttu-id="b9611-122">此表是 Microsoft Defender 安全中心与 Microsoft 365 安全中心之间更改的快速参考。</span><span class="sxs-lookup"><span data-stu-id="b9611-122">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="b9611-123">警报和操作</span><span class="sxs-lookup"><span data-stu-id="b9611-123">Alerts and actions</span></span>

|<span data-ttu-id="b9611-124">**区域**</span><span class="sxs-lookup"><span data-stu-id="b9611-124">**Area**</span></span>  |<span data-ttu-id="b9611-125">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="b9611-125">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="b9611-126">事件&警报</span><span class="sxs-lookup"><span data-stu-id="b9611-126">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="b9611-127">在 Microsoft 365 安全中心，你可以管理所有终结点、电子邮件和标识中的事件和警报。</span><span class="sxs-lookup"><span data-stu-id="b9611-127">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="b9611-128">我们已融合体验，帮助你更轻松地查找相关事件。</span><span class="sxs-lookup"><span data-stu-id="b9611-128">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="b9611-129">有关详细信息，请参阅 [事件概述](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b9611-129">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="b9611-130">搜寻</span><span class="sxs-lookup"><span data-stu-id="b9611-130">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="b9611-131">修改在 Microsoft Defender for Endpoint 中创建的自定义检测规则以包含标识和电子邮件表会自动将它们移动到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="b9611-131">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="b9611-132">其相应的警报也会显示在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="b9611-132">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="b9611-133">有关这些更改的更多详细信息，请阅读"[迁移自定义检测规则"。](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="b9611-133">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <span data-ttu-id="b9611-134">高级 `DeviceAlertEvents` 搜寻表在 Microsoft 365 Defender 中不可用。</span><span class="sxs-lookup"><span data-stu-id="b9611-134">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="b9611-135">若要在 Microsoft 365 Defender 中查询特定于设备的警报信息，可以使用和表来容纳来自一组不同源 `AlertInfo` `AlertEvidence` 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="b9611-135">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="b9611-136">通过遵循不含 [DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)的写入查询来制作下一个与设备相关的查询。</span><span class="sxs-lookup"><span data-stu-id="b9611-136">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="b9611-137">操作中心</span><span class="sxs-lookup"><span data-stu-id="b9611-137">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="b9611-138">列出在自动调查和修正操作之后采取的挂起和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="b9611-138">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="b9611-139">以前，Microsoft Defender 安全中心的操作中心列出了仅对设备上采取的修正操作挂起和已完成的操作，而自动调查列出了警报和状态。</span><span class="sxs-lookup"><span data-stu-id="b9611-139">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="b9611-140">在改进的 Microsoft 365 安全中心中，操作中心将跨电子邮件、设备和用户（全部位于一个位置）的修正操作和调查汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="b9611-140">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="b9611-141">威胁分析</span><span class="sxs-lookup"><span data-stu-id="b9611-141">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="b9611-142">移至导航栏顶部，更易于发现和使用。</span><span class="sxs-lookup"><span data-stu-id="b9611-142">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="b9611-143">现在包括终结点以及电子邮件和协作的威胁信息。</span><span class="sxs-lookup"><span data-stu-id="b9611-143">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="b9611-144">终结点</span><span class="sxs-lookup"><span data-stu-id="b9611-144">Endpoints</span></span>

|<span data-ttu-id="b9611-145">**区域**</span><span class="sxs-lookup"><span data-stu-id="b9611-145">**Area**</span></span>  |<span data-ttu-id="b9611-146">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="b9611-146">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="b9611-147">搜索</span><span class="sxs-lookup"><span data-stu-id="b9611-147">Search</span></span>   |  <span data-ttu-id="b9611-148">Microsoft Defender for Endpoint 搜索栏正在"终结点"部分下移动，而不是位于标题中。</span><span class="sxs-lookup"><span data-stu-id="b9611-148">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="b9611-149">你可以继续搜索设备、文件、用户、URL、IP、漏洞、软件和建议。</span><span class="sxs-lookup"><span data-stu-id="b9611-149">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="b9611-150">仪表板</span><span class="sxs-lookup"><span data-stu-id="b9611-150">Dashboard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="b9611-151">这是安全操作仪表板。</span><span class="sxs-lookup"><span data-stu-id="b9611-151">This is your security operations dashboard.</span></span> <span data-ttu-id="b9611-152">查看触发的活动警报数、存在风险的设备、处于风险中的用户以及警报、设备和用户的严重性级别的概述。</span><span class="sxs-lookup"><span data-stu-id="b9611-152">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="b9611-153">还可以查看任何设备是否有传感器问题、整体服务运行状况以及如何检测到任何未解决的警报。</span><span class="sxs-lookup"><span data-stu-id="b9611-153">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="b9611-154">设备清单</span><span class="sxs-lookup"><span data-stu-id="b9611-154">Device inventory</span></span> | <span data-ttu-id="b9611-155">无更改。</span><span class="sxs-lookup"><span data-stu-id="b9611-155">No changes.</span></span> |
|[<span data-ttu-id="b9611-156">漏洞管理</span><span class="sxs-lookup"><span data-stu-id="b9611-156">Vulnerability management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="b9611-157">名称已缩短以适合导航窗格。</span><span class="sxs-lookup"><span data-stu-id="b9611-157">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="b9611-158">它与威胁和漏洞管理部分相同，所有页面都位于下方。</span><span class="sxs-lookup"><span data-stu-id="b9611-158">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="b9611-159">合作伙伴和 API</span><span class="sxs-lookup"><span data-stu-id="b9611-159">Partners and APIs</span></span> | <span data-ttu-id="b9611-160">无更改。</span><span class="sxs-lookup"><span data-stu-id="b9611-160">No changes.</span></span> |
| <span data-ttu-id="b9611-161">评估&教程</span><span class="sxs-lookup"><span data-stu-id="b9611-161">Evaluations & tutorials</span></span>    |     <span data-ttu-id="b9611-162">新的测试和学习功能。</span><span class="sxs-lookup"><span data-stu-id="b9611-162">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="b9611-163">配置管理</span><span class="sxs-lookup"><span data-stu-id="b9611-163">Configuration management</span></span>   |  <span data-ttu-id="b9611-164">无更改。</span><span class="sxs-lookup"><span data-stu-id="b9611-164">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="b9611-165">**自动调查和修正** 现在是事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9611-165">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="b9611-166">You can see Automated investigation and remediation events in the **Incident > Investigation** tab.</span><span class="sxs-lookup"><span data-stu-id="b9611-166">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="b9611-167">访问和报告</span><span class="sxs-lookup"><span data-stu-id="b9611-167">Access and reporting</span></span>

|<span data-ttu-id="b9611-168">**区域**</span><span class="sxs-lookup"><span data-stu-id="b9611-168">**Area**</span></span>  |<span data-ttu-id="b9611-169">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="b9611-169">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="b9611-170">报表</span><span class="sxs-lookup"><span data-stu-id="b9611-170">Reports</span></span>  | <span data-ttu-id="b9611-171">请参阅终结点和电子邮件报告&协作，包括威胁防护、设备运行状况和合规性以及易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="b9611-171">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="b9611-172">健康</span><span class="sxs-lookup"><span data-stu-id="b9611-172">Health</span></span>  |  <span data-ttu-id="b9611-173">当前链接到 Microsoft [365](https://admin.microsoft.com/)管理中心中的"服务运行状况"页面。</span><span class="sxs-lookup"><span data-stu-id="b9611-173">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="b9611-174">设置</span><span class="sxs-lookup"><span data-stu-id="b9611-174">Settings</span></span> |  <span data-ttu-id="b9611-175">管理 Microsoft 365 安全中心、Microsoft 365 Defender、终结点、电子邮件&协作、标识和设备发现的设置。</span><span class="sxs-lookup"><span data-stu-id="b9611-175">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="b9611-176">Microsoft 365 安全导航和功能</span><span class="sxs-lookup"><span data-stu-id="b9611-176">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="b9611-177">左侧导航栏或快速启动栏看起来很熟悉。</span><span class="sxs-lookup"><span data-stu-id="b9611-177">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="b9611-178">但是，此安全中心有一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="b9611-178">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="b9611-179">事件和警报</span><span class="sxs-lookup"><span data-stu-id="b9611-179">Incidents and alerts</span></span>

<span data-ttu-id="b9611-180">将跨电子邮件、设备和标识的事件和警报管理汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="b9611-180">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="b9611-181">警报页面通过组合攻击信号来构造详细情景，为警报提供完整上下文。</span><span class="sxs-lookup"><span data-stu-id="b9611-181">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="b9611-182">新的统一体验现在将跨工作负载的警报视图统一起来。</span><span class="sxs-lookup"><span data-stu-id="b9611-182">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="b9611-183">您可以快速会审、调查和采取有效操作。</span><span class="sxs-lookup"><span data-stu-id="b9611-183">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="b9611-184">详细了解事件</span><span class="sxs-lookup"><span data-stu-id="b9611-184">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="b9611-185">了解有关管理警报的更多信息</span><span class="sxs-lookup"><span data-stu-id="b9611-185">Learn more about managing alerts</span></span>](investigate-alerts.md)

![通知和操作快速启动栏](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="b9611-187">搜寻</span><span class="sxs-lookup"><span data-stu-id="b9611-187">Hunting</span></span>

<span data-ttu-id="b9611-188">使用高级搜寻查询，在终结点、Office 365 邮箱等位置主动搜索威胁、恶意软件和恶意 [活动](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b9611-188">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="b9611-189">这些强大的查询可用于查找和查看威胁指示器和实体，了解已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="b9611-189">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="b9611-190">[可以从高级](custom-detection-rules.md) 搜寻查询构建自定义检测规则，以帮助你主动监视可能表示泄露活动和配置错误的设备的事件。</span><span class="sxs-lookup"><span data-stu-id="b9611-190">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="b9611-191">操作中心</span><span class="sxs-lookup"><span data-stu-id="b9611-191">Action center</span></span>

<span data-ttu-id="b9611-192">操作中心将显示由自动调查和响应功能创建的调查。</span><span class="sxs-lookup"><span data-stu-id="b9611-192">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="b9611-193">Microsoft 365 Defender 中的这种自动自我修复功能可以通过自动响应特定事件来帮助安全团队。</span><span class="sxs-lookup"><span data-stu-id="b9611-193">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="b9611-194">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="b9611-194">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="b9611-195">威胁分析</span><span class="sxs-lookup"><span data-stu-id="b9611-195">Threat Analytics</span></span>

<span data-ttu-id="b9611-196">从 Microsoft 安全专家研究人员获取威胁情报。</span><span class="sxs-lookup"><span data-stu-id="b9611-196">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="b9611-197">威胁分析可帮助安全团队在应对新出现的威胁时提高效率。</span><span class="sxs-lookup"><span data-stu-id="b9611-197">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="b9611-198">威胁分析包括：</span><span class="sxs-lookup"><span data-stu-id="b9611-198">Threat Analytics includes:</span></span>

- <span data-ttu-id="b9611-199">来自 Microsoft Defender for Office 365 的电子邮件相关检测和缓解。</span><span class="sxs-lookup"><span data-stu-id="b9611-199">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b9611-200">这是 Microsoft Defender for Endpoint 中已提供的终结点数据之外的数据。</span><span class="sxs-lookup"><span data-stu-id="b9611-200">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="b9611-201">与威胁相关的事件视图。</span><span class="sxs-lookup"><span data-stu-id="b9611-201">Incidents view related to the threats.</span></span>
- <span data-ttu-id="b9611-202">用于快速识别和使用报告中可操作信息的增强体验。</span><span class="sxs-lookup"><span data-stu-id="b9611-202">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="b9611-203">可以从 Microsoft 365 安全中心的左上角导航栏或显示组织的主要威胁的专用仪表板卡访问威胁分析。</span><span class="sxs-lookup"><span data-stu-id="b9611-203">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="b9611-204">详细了解如何使用威胁分析跟踪和响应 [新出现的威胁](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="b9611-204">Learn more about how to [track and respond to emerging threats with threat analytics](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="b9611-205">"终结点"部分</span><span class="sxs-lookup"><span data-stu-id="b9611-205">Endpoints section</span></span>

<span data-ttu-id="b9611-206">查看和管理组织中终结点的安全性。</span><span class="sxs-lookup"><span data-stu-id="b9611-206">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="b9611-207">如果你已使用 Microsoft Defender 安全中心，它将看起来很熟悉。</span><span class="sxs-lookup"><span data-stu-id="b9611-207">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![终结点快速启动栏](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="b9611-209">访问和报告</span><span class="sxs-lookup"><span data-stu-id="b9611-209">Access and reports</span></span>

<span data-ttu-id="b9611-210">查看报告、更改设置和修改用户角色。</span><span class="sxs-lookup"><span data-stu-id="b9611-210">View reports, change your settings, and modify user roles.</span></span>

!["访问和报告快速启动"栏](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="b9611-212">SIEM API 连接</span><span class="sxs-lookup"><span data-stu-id="b9611-212">SIEM API connections</span></span>

<span data-ttu-id="b9611-213">如果你使用 [Defender for Endpoint SIEM API，](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)你可以继续这样做。</span><span class="sxs-lookup"><span data-stu-id="b9611-213">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="b9611-214">我们在 API 负载上添加了指向 Microsoft 365 安全门户中的警报页面或事件页面的新链接。</span><span class="sxs-lookup"><span data-stu-id="b9611-214">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="b9611-215">新的 API 字段包括 LinkToMTP 和 IncidentLinkToMTP。</span><span class="sxs-lookup"><span data-stu-id="b9611-215">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="b9611-216">有关详细信息，请参阅 [将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="b9611-216">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="b9611-217">电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="b9611-217">Email alerts</span></span>

<span data-ttu-id="b9611-218">你可以继续使用 Defender for Endpoint 的电子邮件警报。</span><span class="sxs-lookup"><span data-stu-id="b9611-218">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="b9611-219">我们已在电子邮件中添加了指向 Microsoft 365 安全中心中的警报页面或事件页面的新链接。</span><span class="sxs-lookup"><span data-stu-id="b9611-219">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="b9611-220">有关详细信息，请参阅 [将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="b9611-220">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="b9611-221">相关信息</span><span class="sxs-lookup"><span data-stu-id="b9611-221">Related information</span></span>

- [<span data-ttu-id="b9611-222">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="b9611-222">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="b9611-223">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b9611-223">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="b9611-224">将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="b9611-224">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
