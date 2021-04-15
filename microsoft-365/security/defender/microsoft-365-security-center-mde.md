---
title: Microsoft 365 安全中心中的 Microsoft Defender for Endpoint
description: 了解从 Microsoft Defender 安全中心到 Microsoft 365 安全中心的更改
keywords: Microsoft 365 安全中心、OATP、MDATP、MDO、MDE、单窗格的门户、聚合门户、安全门户、Defender 安全门户入门
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: edf0baa369142f6a0aafc86794a47ab0be6e345a
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760046"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="30bc7-104">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="30bc7-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="30bc7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="30bc7-105">**Applies to:**</span></span>

- [<span data-ttu-id="30bc7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30bc7-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="30bc7-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="30bc7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30bc7-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="30bc7-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

<span data-ttu-id="30bc7-109">改进的 [Microsoft 365](overview-security-center.md) 安全中心结合了保护、检测、调查和响应电子邮件、协作、标识 [https://security.microsoft.com](https://security.microsoft.com) 和设备威胁的管理功能。</span><span class="sxs-lookup"><span data-stu-id="30bc7-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="30bc7-110">此安全中心将现有 Microsoft 安全门户（包括 Microsoft Defender 安全中心和 Office 365 安全与合规中心）&功能。</span><span class="sxs-lookup"><span data-stu-id="30bc7-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="30bc7-111">如果你熟悉 Microsoft Defender 安全中心，本文可帮助描述改进的 Microsoft 365 安全中心中的一些更改和改进。</span><span class="sxs-lookup"><span data-stu-id="30bc7-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="30bc7-112">但是，要注意一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="30bc7-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="30bc7-113">过去 [，Microsoft Defender 安全中心一](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) 直是 Microsoft Defender for Endpoint 的主页。</span><span class="sxs-lookup"><span data-stu-id="30bc7-113">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="30bc7-114">企业安全团队已使用它监视并帮助响应潜在高级永久性威胁活动或数据泄露的警报。</span><span class="sxs-lookup"><span data-stu-id="30bc7-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="30bc7-115">为帮助减少门户数量，Microsoft 365 安全中心将成为监视和管理 Microsoft 标识、数据、设备、应用和基础结构的安全性的主页。</span><span class="sxs-lookup"><span data-stu-id="30bc7-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="30bc7-116">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商 [ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 授予访问权限，方式与在 [Microsoft Defender](mssp-access.md)安全中心授予访问权限的方式相同。</span><span class="sxs-lookup"><span data-stu-id="30bc7-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="30bc7-117">你在 Microsoft 365 安全中心看到的情况取决于你的当前订阅。</span><span class="sxs-lookup"><span data-stu-id="30bc7-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="30bc7-118">例如，如果你没有适用于 Office 365 的 Microsoft Defender 许可证，将不会显示"电子邮件&协作"部分。</span><span class="sxs-lookup"><span data-stu-id="30bc7-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="30bc7-119">新的统一门户不适用于：</span><span class="sxs-lookup"><span data-stu-id="30bc7-119">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="30bc7-120">美国政府社区云 (GCC) </span><span class="sxs-lookup"><span data-stu-id="30bc7-120">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="30bc7-121">美国政府社区云高 (GCC 高) </span><span class="sxs-lookup"><span data-stu-id="30bc7-121">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="30bc7-122">美国国防部</span><span class="sxs-lookup"><span data-stu-id="30bc7-122">US Department of Defense</span></span>
>- <span data-ttu-id="30bc7-123">所有拥有商业许可证的美国政府机构</span><span class="sxs-lookup"><span data-stu-id="30bc7-123">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="30bc7-124">查看改进的 Microsoft 365 安全中心 [https://security.microsoft.com](https://security.microsoft.com) ：。</span><span class="sxs-lookup"><span data-stu-id="30bc7-124">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="30bc7-125">了解优点：Microsoft 365 [概述](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="30bc7-125">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="30bc7-126">更改内容</span><span class="sxs-lookup"><span data-stu-id="30bc7-126">What's changed</span></span>

<span data-ttu-id="30bc7-127">此表是 Microsoft Defender 安全中心与 Microsoft 365 安全中心之间更改的快速参考。</span><span class="sxs-lookup"><span data-stu-id="30bc7-127">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="30bc7-128">警报和操作</span><span class="sxs-lookup"><span data-stu-id="30bc7-128">Alerts and actions</span></span>

|<span data-ttu-id="30bc7-129">**区域**</span><span class="sxs-lookup"><span data-stu-id="30bc7-129">**Area**</span></span>  |<span data-ttu-id="30bc7-130">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="30bc7-130">**Description of change**</span></span> |
|---------|---------|
| [<span data-ttu-id="30bc7-131">事件&警报</span><span class="sxs-lookup"><span data-stu-id="30bc7-131">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="30bc7-132">在 Microsoft 365 安全中心，可以跨所有终结点、电子邮件和标识管理事件和警报。</span><span class="sxs-lookup"><span data-stu-id="30bc7-132">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="30bc7-133">我们已将体验融合在一起，帮助你更轻松地查找相关事件。</span><span class="sxs-lookup"><span data-stu-id="30bc7-133">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="30bc7-134">有关详细信息，请参阅 [事件概述](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="30bc7-134">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="30bc7-135">搜寻</span><span class="sxs-lookup"><span data-stu-id="30bc7-135">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="30bc7-136">修改在 Microsoft Defender for Endpoint 中创建的自定义检测规则，以包含标识和电子邮件表会自动将它们移动到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="30bc7-136">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="30bc7-137">其相应的警报也会显示在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="30bc7-137">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="30bc7-138">有关这些更改的更多详细信息，请阅读迁移 [自定义检测规则](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="30bc7-138">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="30bc7-139">高级 `DeviceAlertEvents` 搜寻表在 Microsoft 365 Defender 中不可用。</span><span class="sxs-lookup"><span data-stu-id="30bc7-139">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="30bc7-140">若要在 Microsoft 365 Defender 中查询特定于设备的警报信息，可以使用 和 表来容纳来自各种源 `AlertInfo` `AlertEvidence` 集的更多信息。</span><span class="sxs-lookup"><span data-stu-id="30bc7-140">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="30bc7-141">通过以下不含 [DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)的 Write 查询制作下一个与设备相关的查询。</span><span class="sxs-lookup"><span data-stu-id="30bc7-141">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="30bc7-142">操作中心</span><span class="sxs-lookup"><span data-stu-id="30bc7-142">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="30bc7-143">列出在自动调查和修正操作之后采取的挂起和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="30bc7-143">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="30bc7-144">以前，Microsoft Defender 安全中心的操作中心列出了仅对设备上采取的修正操作挂起和已完成的操作，而自动调查列出了警报和状态。</span><span class="sxs-lookup"><span data-stu-id="30bc7-144">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="30bc7-145">在改进的 Microsoft 365 安全中心中，操作中心将电子邮件、设备和用户之间的修正操作和调查汇集在一起，所有这些操作都位于一个位置。</span><span class="sxs-lookup"><span data-stu-id="30bc7-145">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="30bc7-146">威胁分析</span><span class="sxs-lookup"><span data-stu-id="30bc7-146">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="30bc7-147">移动到导航栏顶部，以便更轻松地发现和使用。</span><span class="sxs-lookup"><span data-stu-id="30bc7-147">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="30bc7-148">现在包括终结点以及电子邮件和协作的威胁信息。</span><span class="sxs-lookup"><span data-stu-id="30bc7-148">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="30bc7-149">终结点</span><span class="sxs-lookup"><span data-stu-id="30bc7-149">Endpoints</span></span>

|<span data-ttu-id="30bc7-150">**区域**</span><span class="sxs-lookup"><span data-stu-id="30bc7-150">**Area**</span></span>  |<span data-ttu-id="30bc7-151">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="30bc7-151">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="30bc7-152">搜索</span><span class="sxs-lookup"><span data-stu-id="30bc7-152">Search</span></span>   |  <span data-ttu-id="30bc7-153">Microsoft Defender for Endpoint 搜索栏不是位于标题中，而是在"终结点"部分下移动。</span><span class="sxs-lookup"><span data-stu-id="30bc7-153">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="30bc7-154">你可以继续搜索设备、文件、用户、URL、IP、漏洞、软件和建议。</span><span class="sxs-lookup"><span data-stu-id="30bc7-154">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="30bc7-155">仪表板</span><span class="sxs-lookup"><span data-stu-id="30bc7-155">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="30bc7-156">这是安全操作仪表板。</span><span class="sxs-lookup"><span data-stu-id="30bc7-156">This is your security operations dashboard.</span></span> <span data-ttu-id="30bc7-157">请参阅触发的活动警报数、处于风险中的设备、处于风险中的用户以及警报、设备和用户的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="30bc7-157">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="30bc7-158">还可以查看任何设备是否具有传感器问题、整体服务运行状况，以及如何检测到任何未解决的警报。</span><span class="sxs-lookup"><span data-stu-id="30bc7-158">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="30bc7-159">设备清单</span><span class="sxs-lookup"><span data-stu-id="30bc7-159">Device inventory</span></span> | <span data-ttu-id="30bc7-160">无更改。</span><span class="sxs-lookup"><span data-stu-id="30bc7-160">No changes.</span></span> |
|[<span data-ttu-id="30bc7-161">漏洞管理</span><span class="sxs-lookup"><span data-stu-id="30bc7-161">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="30bc7-162">已缩短名称以适合导航窗格。</span><span class="sxs-lookup"><span data-stu-id="30bc7-162">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="30bc7-163">它与威胁和漏洞管理部分相同，所有页面都位于下方。</span><span class="sxs-lookup"><span data-stu-id="30bc7-163">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="30bc7-164">合作伙伴和 API</span><span class="sxs-lookup"><span data-stu-id="30bc7-164">Partners and APIs</span></span> | <span data-ttu-id="30bc7-165">无更改。</span><span class="sxs-lookup"><span data-stu-id="30bc7-165">No changes.</span></span> |
| <span data-ttu-id="30bc7-166">评估&教程</span><span class="sxs-lookup"><span data-stu-id="30bc7-166">Evaluations & tutorials</span></span>    |     <span data-ttu-id="30bc7-167">新的测试和学习功能。</span><span class="sxs-lookup"><span data-stu-id="30bc7-167">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="30bc7-168">配置管理</span><span class="sxs-lookup"><span data-stu-id="30bc7-168">Configuration management</span></span>   |  <span data-ttu-id="30bc7-169">无更改。</span><span class="sxs-lookup"><span data-stu-id="30bc7-169">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="30bc7-170">**自动调查和修正** 现在是事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="30bc7-170">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="30bc7-171">You can see Automated investigation and remediation events in the **Incident > Investigation** tab.</span><span class="sxs-lookup"><span data-stu-id="30bc7-171">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="30bc7-172">访问和报告</span><span class="sxs-lookup"><span data-stu-id="30bc7-172">Access and reporting</span></span>

|<span data-ttu-id="30bc7-173">**区域**</span><span class="sxs-lookup"><span data-stu-id="30bc7-173">**Area**</span></span>  |<span data-ttu-id="30bc7-174">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="30bc7-174">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="30bc7-175">报表</span><span class="sxs-lookup"><span data-stu-id="30bc7-175">Reports</span></span>  | <span data-ttu-id="30bc7-176">请参阅终结点和电子邮件报告&协作，包括威胁防护、设备运行状况和合规性以及易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="30bc7-176">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="30bc7-177">健康</span><span class="sxs-lookup"><span data-stu-id="30bc7-177">Health</span></span>  |  <span data-ttu-id="30bc7-178">当前链接到 Microsoft [365](https://admin.microsoft.com/)管理中心中的"服务运行状况"页面。</span><span class="sxs-lookup"><span data-stu-id="30bc7-178">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="30bc7-179">设置</span><span class="sxs-lookup"><span data-stu-id="30bc7-179">Settings</span></span> |  <span data-ttu-id="30bc7-180">管理 Microsoft 365 安全中心、Microsoft 365 Defender、终结点、电子邮件&协作、标识和设备发现的设置。</span><span class="sxs-lookup"><span data-stu-id="30bc7-180">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="30bc7-181">Microsoft 365 安全导航和功能</span><span class="sxs-lookup"><span data-stu-id="30bc7-181">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="30bc7-182">左侧导航栏或快速启动栏将看起来熟悉。</span><span class="sxs-lookup"><span data-stu-id="30bc7-182">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="30bc7-183">但是，这个安全中心中有些新增和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="30bc7-183">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="30bc7-184">事件和警报</span><span class="sxs-lookup"><span data-stu-id="30bc7-184">Incidents and alerts</span></span>

<span data-ttu-id="30bc7-185">将跨电子邮件、设备和标识的事件和警报管理结合起来。</span><span class="sxs-lookup"><span data-stu-id="30bc7-185">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="30bc7-186">警报页面通过组合攻击信号来构造详细的情景，为警报提供完整的上下文。</span><span class="sxs-lookup"><span data-stu-id="30bc7-186">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="30bc7-187">全新的统一体验现在汇集了跨工作负荷的一致警报视图。</span><span class="sxs-lookup"><span data-stu-id="30bc7-187">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="30bc7-188">您可以快速分案、调查，以及采取有效措施。</span><span class="sxs-lookup"><span data-stu-id="30bc7-188">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="30bc7-189">详细了解事件</span><span class="sxs-lookup"><span data-stu-id="30bc7-189">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="30bc7-190">深入了解如何管理警报</span><span class="sxs-lookup"><span data-stu-id="30bc7-190">Learn more about managing alerts</span></span>](investigate-alerts.md)

![通知和操作快速启动栏](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="30bc7-192">搜寻</span><span class="sxs-lookup"><span data-stu-id="30bc7-192">Hunting</span></span>

<span data-ttu-id="30bc7-193">通过使用 [高级搜索查询来在终结点、Office 365 邮箱等位置主动搜索威胁、恶意软件和恶意](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="30bc7-193">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="30bc7-194">这些强大的查询可用于查找和查看威胁指示器和实体，了解已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="30bc7-194">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="30bc7-195">[自定义检测](custom-detection-rules.md) 规则可以从高级搜寻查询构建，以帮助你主动监视可能表示泄露活动和错误配置设备的事件。</span><span class="sxs-lookup"><span data-stu-id="30bc7-195">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="30bc7-196">操作中心</span><span class="sxs-lookup"><span data-stu-id="30bc7-196">Action center</span></span>

<span data-ttu-id="30bc7-197">操作中心显示自动调查和响应功能创建调查。</span><span class="sxs-lookup"><span data-stu-id="30bc7-197">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="30bc7-198">Microsoft 365 Defender 中的自动自恢复功能可自动响应特定事件，帮助团队实现安全。</span><span class="sxs-lookup"><span data-stu-id="30bc7-198">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="30bc7-199">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="30bc7-199">Learn more about the Action center</span></span>](m365d-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="30bc7-200">威胁分析</span><span class="sxs-lookup"><span data-stu-id="30bc7-200">Threat Analytics</span></span>

<span data-ttu-id="30bc7-201">从 Microsoft 安全研究人员获取威胁智能。</span><span class="sxs-lookup"><span data-stu-id="30bc7-201">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="30bc7-202">威胁分析可帮助安全团队在面对新兴威胁时更有效率。</span><span class="sxs-lookup"><span data-stu-id="30bc7-202">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="30bc7-203">威胁分析包括：</span><span class="sxs-lookup"><span data-stu-id="30bc7-203">Threat Analytics includes:</span></span>

- <span data-ttu-id="30bc7-204">Microsoft Defender for Office 365 的与电子邮件相关的检测和缓解措施。</span><span class="sxs-lookup"><span data-stu-id="30bc7-204">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="30bc7-205">除了从 Microsoft Defender for Endpoint 中可用的终结点数据外，还有一个终结点数据。</span><span class="sxs-lookup"><span data-stu-id="30bc7-205">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="30bc7-206">与威胁相关的事件视图。</span><span class="sxs-lookup"><span data-stu-id="30bc7-206">Incidents view related to the threats.</span></span>
- <span data-ttu-id="30bc7-207">增强的体验，可快速识别和使用报告中的可操作信息。</span><span class="sxs-lookup"><span data-stu-id="30bc7-207">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="30bc7-208">你可以从 Microsoft 365 安全中心的左上角导航栏或显示组织的主要威胁的专用仪表板卡访问威胁分析。</span><span class="sxs-lookup"><span data-stu-id="30bc7-208">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="30bc7-209">深入了解如何使用威胁 [跟踪和响应新兴威胁](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="30bc7-209">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="30bc7-210">终结点部分</span><span class="sxs-lookup"><span data-stu-id="30bc7-210">Endpoints section</span></span>

<span data-ttu-id="30bc7-211">查看和管理组织中终结点的安全性。</span><span class="sxs-lookup"><span data-stu-id="30bc7-211">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="30bc7-212">如果你已使用 Microsoft Defender 安全中心，它将看起来很熟悉。</span><span class="sxs-lookup"><span data-stu-id="30bc7-212">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![终结点快速启动栏](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="30bc7-214">访问和报告</span><span class="sxs-lookup"><span data-stu-id="30bc7-214">Access and reports</span></span>

<span data-ttu-id="30bc7-215">查看报表、更改设置和修改用户角色。</span><span class="sxs-lookup"><span data-stu-id="30bc7-215">View reports, change your settings, and modify user roles.</span></span>

!["访问和报告快速启动"栏](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="30bc7-217">SIEM API 连接</span><span class="sxs-lookup"><span data-stu-id="30bc7-217">SIEM API connections</span></span>

<span data-ttu-id="30bc7-218">如果你使用 [适用于终结点 SIEM API 的 Defender，](../defender-endpoint/enable-siem-integration.md)你可以继续这样做。</span><span class="sxs-lookup"><span data-stu-id="30bc7-218">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="30bc7-219">我们已在 API 负载上添加了指向 Microsoft 365 安全门户中的警报页面或事件页面的新链接。</span><span class="sxs-lookup"><span data-stu-id="30bc7-219">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="30bc7-220">新的 API 字段包括 LinkToMTP 和 IncidentLinkToMTP。</span><span class="sxs-lookup"><span data-stu-id="30bc7-220">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="30bc7-221">有关详细信息，请参阅将帐户从 [Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="30bc7-221">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="30bc7-222">电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="30bc7-222">Email alerts</span></span>

<span data-ttu-id="30bc7-223">你可以继续使用 Defender for Endpoint 的电子邮件警报。</span><span class="sxs-lookup"><span data-stu-id="30bc7-223">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="30bc7-224">我们已在电子邮件中添加指向 Microsoft 365 安全中心中的警报页面或事件页面的新链接。</span><span class="sxs-lookup"><span data-stu-id="30bc7-224">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="30bc7-225">有关详细信息，请参阅将帐户从 [Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="30bc7-225">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="30bc7-226">相关信息</span><span class="sxs-lookup"><span data-stu-id="30bc7-226">Related information</span></span>

- [<span data-ttu-id="30bc7-227">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="30bc7-227">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="30bc7-228">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="30bc7-228">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="30bc7-229">将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="30bc7-229">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)