---
title: 安全中心中的 Microsoft Defender Microsoft 365终结点
description: 了解从安全中心Microsoft Defender 安全中心安全Microsoft 365更改
keywords: 入门：Microsoft 365安全中心、适用于 Office 365 的 Microsoft Defender、适用于终结点的 Microsoft Defender、MDO、MDE、单窗格的门户、聚合门户、安全门户、Defender 安全门户
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: bad31160bb27c79f672ddd28a5fced3bf8c2ee1b
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943037"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="3cc1d-104">安全中心中的 Microsoft Defender Microsoft 365终结点</span><span class="sxs-lookup"><span data-stu-id="3cc1d-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3cc1d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-105">**Applies to:**</span></span>

- [<span data-ttu-id="3cc1d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cc1d-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="3cc1d-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3cc1d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3cc1d-108">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3cc1d-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

<span data-ttu-id="3cc1d-109">改进的安全[Microsoft 365](overview-security-center.md)中心结合使用了保护、检测、调查和响应电子邮件、协作、标识 [https://security.microsoft.com](https://security.microsoft.com) 和设备威胁的管理功能。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="3cc1d-110">此安全中心将现有 Microsoft 安全门户的功能汇集在一起，Microsoft Defender 安全中心安全Office 365安全&中心。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="3cc1d-111">如果您熟悉本文中的Microsoft Defender 安全中心，本文可帮助描述改进的安全中心中的一Microsoft 365改进。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="3cc1d-112">但是，要注意一些新的和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="3cc1d-113">过去[，Microsoft Defender 安全中心](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)一直是 Microsoft Defender for Endpoint 的主页。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-113">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3cc1d-114">Enterprise安全团队已使用它监视和帮助响应潜在高级永久性威胁活动或数据泄露的警报。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="3cc1d-115">为了帮助减少门户数量，Microsoft 365安全中心将是监视和管理 Microsoft 标识、数据、设备、应用和基础结构的安全性的主页。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="3cc1d-116">Microsoft 365安全中心中的 Microsoft Defender for Endpoint 支持以在 Microsoft Defender 安全中心中授予访问权限的相同方式向托管安全服务提供商[ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)授予[访问权限](mssp-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="3cc1d-117">在安全中心Microsoft 365取决于你的当前订阅。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="3cc1d-118">例如，如果你没有 Microsoft Defender for Office 365 许可证，将不会显示"电子邮件&协作"部分。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="3cc1d-119">新的统一门户不适用于：</span><span class="sxs-lookup"><span data-stu-id="3cc1d-119">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="3cc1d-120">美国政府社区云 (GCC) </span><span class="sxs-lookup"><span data-stu-id="3cc1d-120">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="3cc1d-121">美国政府社区云高 (GCC高) </span><span class="sxs-lookup"><span data-stu-id="3cc1d-121">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="3cc1d-122">美国国防部</span><span class="sxs-lookup"><span data-stu-id="3cc1d-122">US Department of Defense</span></span>
>- <span data-ttu-id="3cc1d-123">所有拥有商业许可证的美国政府机构</span><span class="sxs-lookup"><span data-stu-id="3cc1d-123">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="3cc1d-124">查看改进的安全 [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365：。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-124">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="3cc1d-125">了解优点：Microsoft 365 [概述](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="3cc1d-125">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="3cc1d-126">更改内容</span><span class="sxs-lookup"><span data-stu-id="3cc1d-126">What's changed</span></span>

<span data-ttu-id="3cc1d-127">下表快速引用了安全中心Microsoft Defender 安全中心安全Microsoft 365更改。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-127">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="3cc1d-128">警报和操作</span><span class="sxs-lookup"><span data-stu-id="3cc1d-128">Alerts and actions</span></span>

|<span data-ttu-id="3cc1d-129">**区域**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-129">**Area**</span></span>  |<span data-ttu-id="3cc1d-130">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-130">**Description of change**</span></span> |
|---------|---------|
| [<span data-ttu-id="3cc1d-131">事件&警报</span><span class="sxs-lookup"><span data-stu-id="3cc1d-131">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="3cc1d-132">在Microsoft 365安全中心，可以跨所有终结点、电子邮件和标识管理事件和警报。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-132">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="3cc1d-133">我们已将体验融合在一起，帮助你更轻松地查找相关事件。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-133">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="3cc1d-134">有关详细信息，请参阅 [事件概述](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-134">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="3cc1d-135">搜寻</span><span class="sxs-lookup"><span data-stu-id="3cc1d-135">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="3cc1d-136">修改在 Microsoft Defender for Endpoint 中创建的自定义检测规则，以包含标识和电子邮件表会自动将它们Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-136">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="3cc1d-137">其相应的警报也会显示在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-137">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="3cc1d-138">有关这些更改的更多详细信息，请阅读迁移 [自定义检测规则](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-138">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="3cc1d-139">高级 `DeviceAlertEvents` 搜寻的表在 Microsoft 365 Defender 中不可用。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-139">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="3cc1d-140">若要在 Microsoft 365 Defender 中查询特定于设备的警报信息，可以使用 和 表来容纳来自各种源 `AlertInfo` `AlertEvidence` 集的更多信息。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-140">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="3cc1d-141">通过以下不含 [DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)的 Write 查询制作下一个与设备相关的查询。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-141">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="3cc1d-142">操作中心</span><span class="sxs-lookup"><span data-stu-id="3cc1d-142">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="3cc1d-143">列出在自动调查和修正操作之后采取的挂起和已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-143">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="3cc1d-144">以前，"操作中心"Microsoft Defender 安全中心列出仅对设备上采取的修正操作挂起和已完成的操作，而自动调查列出了警报和状态。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-144">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="3cc1d-145">在改进的安全Microsoft 365，操作中心将电子邮件、设备和用户之间的修正操作和调查汇集在一起，所有这些操作都位于一个位置。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-145">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="3cc1d-146">威胁分析</span><span class="sxs-lookup"><span data-stu-id="3cc1d-146">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="3cc1d-147">移动到导航栏顶部，以便更轻松地发现和使用。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-147">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="3cc1d-148">现在包括终结点以及电子邮件和协作的威胁信息。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-148">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="3cc1d-149">终结点</span><span class="sxs-lookup"><span data-stu-id="3cc1d-149">Endpoints</span></span>

|<span data-ttu-id="3cc1d-150">**区域**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-150">**Area**</span></span>  |<span data-ttu-id="3cc1d-151">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-151">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="3cc1d-152">搜索</span><span class="sxs-lookup"><span data-stu-id="3cc1d-152">Search</span></span>   |  <span data-ttu-id="3cc1d-153">Microsoft Defender for Endpoint 搜索栏不是位于标题中，而是在"终结点"部分下移动。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-153">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="3cc1d-154">你可以继续搜索设备、文件、用户、URL、IP、漏洞、软件和建议。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-154">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="3cc1d-155">仪表板</span><span class="sxs-lookup"><span data-stu-id="3cc1d-155">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="3cc1d-156">这是安全操作仪表板。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-156">This is your security operations dashboard.</span></span> <span data-ttu-id="3cc1d-157">请参阅触发的活动警报数、处于风险中的设备、处于风险中的用户以及警报、设备和用户的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-157">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="3cc1d-158">还可以查看任何设备是否具有传感器问题、整体服务运行状况，以及如何检测到任何未解决的警报。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-158">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="3cc1d-159">设备清单</span><span class="sxs-lookup"><span data-stu-id="3cc1d-159">Device inventory</span></span> | <span data-ttu-id="3cc1d-160">无更改。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-160">No changes.</span></span> |
|[<span data-ttu-id="3cc1d-161">漏洞管理</span><span class="sxs-lookup"><span data-stu-id="3cc1d-161">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="3cc1d-162">已缩短名称以适合导航窗格。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-162">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="3cc1d-163">它与"页面"部分危险和漏洞管理相同，所有页面位于下方。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-163">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="3cc1d-164">合作伙伴和 API</span><span class="sxs-lookup"><span data-stu-id="3cc1d-164">Partners and APIs</span></span> | <span data-ttu-id="3cc1d-165">无更改。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-165">No changes.</span></span> |
| <span data-ttu-id="3cc1d-166">评估&教程</span><span class="sxs-lookup"><span data-stu-id="3cc1d-166">Evaluations & tutorials</span></span>    |     <span data-ttu-id="3cc1d-167">新的测试和学习功能。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-167">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="3cc1d-168">配置管理</span><span class="sxs-lookup"><span data-stu-id="3cc1d-168">Configuration management</span></span>   |  <span data-ttu-id="3cc1d-169">无更改。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-169">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="3cc1d-170">**自动调查和修正** 现在是事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-170">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="3cc1d-171">You can see Automated investigation and remediation events in the **Incident > Investigation** tab.</span><span class="sxs-lookup"><span data-stu-id="3cc1d-171">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

> [!TIP]
> <span data-ttu-id="3cc1d-172">设备搜索从 Endpoints > Search 完成。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-172">Device search is done from Endpoints > Search.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="3cc1d-173">访问和报告</span><span class="sxs-lookup"><span data-stu-id="3cc1d-173">Access and reporting</span></span>

|<span data-ttu-id="3cc1d-174">**区域**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-174">**Area**</span></span>  |<span data-ttu-id="3cc1d-175">**更改说明**</span><span class="sxs-lookup"><span data-stu-id="3cc1d-175">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="3cc1d-176">报表</span><span class="sxs-lookup"><span data-stu-id="3cc1d-176">Reports</span></span>  | <span data-ttu-id="3cc1d-177">请参阅终结点和电子邮件报告&协作，包括威胁防护、设备运行状况和合规性以及易受攻击的设备。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-177">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="3cc1d-178">健康</span><span class="sxs-lookup"><span data-stu-id="3cc1d-178">Health</span></span>  |  <span data-ttu-id="3cc1d-179">当前链接到管理中心 中的"服务运行状况["Microsoft 365页面](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-179">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="3cc1d-180">设置</span><span class="sxs-lookup"><span data-stu-id="3cc1d-180">Settings</span></span> |  <span data-ttu-id="3cc1d-181">管理安全中心、Microsoft 365 Defender、Microsoft 365、电子邮件&协作、标识和设备发现的设置。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-181">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="3cc1d-182">Microsoft 365安全导航和功能</span><span class="sxs-lookup"><span data-stu-id="3cc1d-182">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="3cc1d-183">左侧导航栏或快速启动栏将看起来熟悉。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-183">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="3cc1d-184">但是，这个安全中心中有些新增和更新的元素。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-184">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="3cc1d-185">事件和警报</span><span class="sxs-lookup"><span data-stu-id="3cc1d-185">Incidents and alerts</span></span>

<span data-ttu-id="3cc1d-186">将跨电子邮件、设备和标识的事件和警报管理结合起来。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-186">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="3cc1d-187">警报页面通过组合攻击信号来构造详细的情景，为警报提供完整的上下文。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-187">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="3cc1d-188">全新的统一体验现在汇集了跨工作负荷的一致警报视图。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-188">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="3cc1d-189">您可以快速分案、调查，以及采取有效措施。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-189">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="3cc1d-190">详细了解事件</span><span class="sxs-lookup"><span data-stu-id="3cc1d-190">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="3cc1d-191">深入了解如何管理警报</span><span class="sxs-lookup"><span data-stu-id="3cc1d-191">Learn more about managing alerts</span></span>](investigate-alerts.md)

![通知和操作快速启动栏](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="3cc1d-193">搜寻</span><span class="sxs-lookup"><span data-stu-id="3cc1d-193">Hunting</span></span>

<span data-ttu-id="3cc1d-194">通过使用 [高级搜索查询来在终结点、Office 365 邮箱等位置主动搜索威胁、恶意软件和恶意](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-194">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="3cc1d-195">这些强大的查询可用于查找和查看威胁指示器和实体，了解已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-195">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="3cc1d-196">[自定义检测](custom-detection-rules.md) 规则可以从高级搜寻查询构建，以帮助你主动监视可能表示泄露活动和错误配置设备的事件。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-196">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="3cc1d-197">操作中心</span><span class="sxs-lookup"><span data-stu-id="3cc1d-197">Action center</span></span>

<span data-ttu-id="3cc1d-198">操作中心显示自动调查和响应功能创建调查。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-198">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="3cc1d-199">Microsoft 365 Defender 中的自动自恢复功能可自动响应特定事件，帮助团队实现安全。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-199">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="3cc1d-200">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="3cc1d-200">Learn more about the Action center</span></span>](m365d-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="3cc1d-201">威胁分析</span><span class="sxs-lookup"><span data-stu-id="3cc1d-201">Threat Analytics</span></span>

<span data-ttu-id="3cc1d-202">从 Microsoft 安全研究人员获取威胁智能。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-202">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="3cc1d-203">威胁分析可帮助安全团队在面对新兴威胁时更有效率。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-203">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="3cc1d-204">威胁分析包括：</span><span class="sxs-lookup"><span data-stu-id="3cc1d-204">Threat Analytics includes:</span></span>

- <span data-ttu-id="3cc1d-205">Microsoft Defender for Office 365 的与电子邮件相关的检测和缓解措施。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-205">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="3cc1d-206">除了从 Microsoft Defender for Endpoint 中可用的终结点数据外，还有一个终结点数据。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-206">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="3cc1d-207">与威胁相关的事件视图。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-207">Incidents view related to the threats.</span></span>
- <span data-ttu-id="3cc1d-208">增强的体验，可快速识别和使用报告中的可操作信息。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-208">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="3cc1d-209">你可以从安全中心的左上角导航Microsoft 365访问威胁分析，也可以从显示组织的主要威胁的专用仪表板卡访问威胁分析。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-209">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="3cc1d-210">深入了解如何使用威胁 [跟踪和响应新兴威胁](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="3cc1d-210">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="3cc1d-211">终结点部分</span><span class="sxs-lookup"><span data-stu-id="3cc1d-211">Endpoints section</span></span>

<span data-ttu-id="3cc1d-212">查看和管理组织中终结点的安全性。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-212">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="3cc1d-213">如果你已使用Microsoft Defender 安全中心，它看起来会很熟悉。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-213">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![终结点快速启动栏](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="3cc1d-215">访问和报告</span><span class="sxs-lookup"><span data-stu-id="3cc1d-215">Access and reports</span></span>

<span data-ttu-id="3cc1d-216">查看报表、更改设置和修改用户角色。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-216">View reports, change your settings, and modify user roles.</span></span>

!["访问和报告快速启动"栏](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="3cc1d-218">SIEM API 连接</span><span class="sxs-lookup"><span data-stu-id="3cc1d-218">SIEM API connections</span></span>

<span data-ttu-id="3cc1d-219">如果你使用 [适用于终结点 SIEM API 的 Defender，](../defender-endpoint/enable-siem-integration.md)你可以继续这样做。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-219">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="3cc1d-220">我们已在 API 负载上添加了指向安全门户中的警报页面或事件Microsoft 365链接。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-220">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="3cc1d-221">新的 API 字段包括 LinkToMTP 和 IncidentLinkToMTP。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-221">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="3cc1d-222">有关详细信息，请参阅将帐户从[Microsoft Defender for Endpoint 重定向到Microsoft 365中心](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-222">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="3cc1d-223">电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="3cc1d-223">Email alerts</span></span>

<span data-ttu-id="3cc1d-224">你可以继续使用 Defender for Endpoint 的电子邮件警报。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-224">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="3cc1d-225">我们已在电子邮件中添加指向安全中心内警报页面或事件Microsoft 365链接。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-225">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="3cc1d-226">有关详细信息，请参阅将帐户从[Microsoft Defender for Endpoint 重定向到Microsoft 365中心](./microsoft-365-security-mde-redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc1d-226">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="3cc1d-227">相关信息</span><span class="sxs-lookup"><span data-stu-id="3cc1d-227">Related information</span></span>

- [<span data-ttu-id="3cc1d-228">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="3cc1d-228">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="3cc1d-229">安全中心中的 Microsoft Defender Microsoft 365终结点</span><span class="sxs-lookup"><span data-stu-id="3cc1d-229">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="3cc1d-230">将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="3cc1d-230">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)