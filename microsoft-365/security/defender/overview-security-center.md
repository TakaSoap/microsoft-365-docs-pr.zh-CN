---
title: Microsoft 365 安全中心概述
description: Microsoft 365 安全中心的优势，将 Microsoft Defender for Office 365 (MDO) 和 Microsoft Defender for Endpoint (MDE) 与 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 相结合。 本文概述了 Microsoft 365 安全中心对管理员的推进。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 3b2e5d834caab9973006eda64e369a2a6aa17b5d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163311"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a><span data-ttu-id="980df-105">统一 Microsoft 365 安全中心概述</span><span class="sxs-lookup"><span data-stu-id="980df-105">The unified Microsoft 365 security center overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="980df-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="980df-106">**Applies to:**</span></span>

- [<span data-ttu-id="980df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="980df-107">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="980df-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="980df-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="980df-109">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="980df-109">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/defender-365-security/defender-for-office-365)

> <span data-ttu-id="980df-110">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="980df-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="980df-111">可以在[实验室环境中评估它或在](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)[生产中运行你的试验项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="980df-111">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

<span data-ttu-id="980df-112">改进的 **Microsoft 365** 安全中心 () 中心门户中对电子邮件、协作、标识和设备威胁的保护、检测、调查和 [https://security.microsoft.com](https://security.microsoft.com) 响应。   </span><span class="sxs-lookup"><span data-stu-id="980df-112">The improved **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="980df-113">Microsoft 365 安全中心将现有 Microsoft 安全门户（如 Microsoft Defender 安全中心和 Office 365 安全与合规中心）&功能。</span><span class="sxs-lookup"><span data-stu-id="980df-113">Microsoft 365 security center brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="980df-114">安全中心强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。</span><span class="sxs-lookup"><span data-stu-id="980df-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="980df-115">此中心包括：</span><span class="sxs-lookup"><span data-stu-id="980df-115">This center includes:</span></span>

- <span data-ttu-id="980df-116">**[Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/defender-for-office-365)** Microsoft Defender for Office 365 通过一组保护电子邮件和 Office 365 资源的预防、检测、调查和搜寻功能帮助组织保护其企业。</span><span class="sxs-lookup"><span data-stu-id="980df-116">**[Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/defender-for-office-365)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="980df-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 为贵组织的设备提供预防性保护、攻破后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="980df-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="980df-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft 扩展检测和响应 *(* XDR) 解决方案的一部分，该解决方案利用 Microsoft 365 安全项目组合自动分析跨域的威胁数据，并生成单个仪表板上攻击的图片。</span><span class="sxs-lookup"><span data-stu-id="980df-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="980df-119">如果需要有关 Office 365 安全中心或 Microsoft Defender 安全中心&更改的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="980df-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="980df-120">Microsoft 365 安全中心中的 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="980df-120">Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="980df-121">Microsoft 365 安全中心中的 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="980df-121">Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a><span data-ttu-id="980df-122">预期结果</span><span class="sxs-lookup"><span data-stu-id="980df-122">What to expect</span></span>

<span data-ttu-id="980df-123">在 Office 365 安全与合规中心 (protection.office.com) 和 Microsoft Defender 安全中心 (securitycenter.microsoft.com) 中使用的所有安全内容现在都可以在 *Microsoft 365* 安全中心找到。</span><span class="sxs-lookup"><span data-stu-id="980df-123">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 security center*.</span></span>

<span data-ttu-id="980df-124">Microsoft 365 安全中心通过将来自不同工作负载的信号融入单个统一体验来帮助安全团队调查和响应攻击：</span><span class="sxs-lookup"><span data-stu-id="980df-124">Microsoft 365 security center helps security teams investigate and respond to attacks by brining in signals from different workloads into a single, unified experiences:</span></span>

- <span data-ttu-id="980df-125">事件&警报</span><span class="sxs-lookup"><span data-stu-id="980df-125">Incidents & alerts</span></span>
- <span data-ttu-id="980df-126">搜寻</span><span class="sxs-lookup"><span data-stu-id="980df-126">Hunting</span></span>
- <span data-ttu-id="980df-127">操作中心</span><span class="sxs-lookup"><span data-stu-id="980df-127">Action Center</span></span>
- <span data-ttu-id="980df-128">威胁分析</span><span class="sxs-lookup"><span data-stu-id="980df-128">Threat analytics</span></span>

<span data-ttu-id="980df-129">Microsoft 365 安全中心在将 Microsoft Defender for Office 365 和 Microsoft Defender for Endpoint 合并时强调统一、清晰和共同的目标。</span><span class="sxs-lookup"><span data-stu-id="980df-129">The Microsoft 365 security center emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="980df-130">合并基于下面列出的优先级，在不影响每个安全套件为组合提供的功能的情况下进行：</span><span class="sxs-lookup"><span data-stu-id="980df-130">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination:</span></span>

- <span data-ttu-id="980df-131">公共构建基块</span><span class="sxs-lookup"><span data-stu-id="980df-131">common building blocks</span></span>
- <span data-ttu-id="980df-132">常用术语</span><span class="sxs-lookup"><span data-stu-id="980df-132">common terminology</span></span>
- <span data-ttu-id="980df-133">通用实体</span><span class="sxs-lookup"><span data-stu-id="980df-133">common entities</span></span>
- <span data-ttu-id="980df-134">与其他工作负载的功能奇偶校验</span><span class="sxs-lookup"><span data-stu-id="980df-134">feature parity with other workloads</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="980df-135">统一调查</span><span class="sxs-lookup"><span data-stu-id="980df-135">Unified investigations</span></span>

<span data-ttu-id="980df-136">简化安全中心可创建一个窗格，用于调查 Microsoft 365 组织内的任何事件。</span><span class="sxs-lookup"><span data-stu-id="980df-136">Streamlining security centers creates a single pane for investigating any incidents across a Microsoft 365 organization.</span></span> <span data-ttu-id="980df-137">主要示例是 Microsoft  365 安全中心快速启动上的"事件"节点。</span><span class="sxs-lookup"><span data-stu-id="980df-137">A primary example is the **Incidents** node on the quick launch of the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO 中的&quot;事件&quot;页。":::

<span data-ttu-id="980df-139">例如，双击具有高严重性的事件名称，将你带到一个演示聚合中心优势的页面。</span><span class="sxs-lookup"><span data-stu-id="980df-139">As an example, double-clicking on an incident name with **High** severity brings you to a page that demonstrates the advantage of converging centers.</span></span>

![涉及多个终结点上的特权升级的多阶段事件，显示 16 个受影响的设备和 9 个受到影响的用户。](../../media/converged-incident-info-3.png)

> [!TIP]
> <span data-ttu-id="980df-141">聚合的用户 **选项卡** 是开始查询的一个好位置。</span><span class="sxs-lookup"><span data-stu-id="980df-141">The converged **Users** tab is a good place to begin your inquiries.</span></span> <span data-ttu-id="980df-142">如果你利用聚合工作负载 (Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 MCAS) 以及一系列源（如本地 Active Directory、Azure Active Directory、已同步、本地和第三方用户）的信息，则此单页显示来自聚合工作负载的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="980df-142">This single page surfaces information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and MCAS, if you leverage it) and a range of sources such as on-premises Active Directory, Azure Active Directory, synced, local, and third-party users.</span></span> <span data-ttu-id="980df-143">详细了解新的 [用户体验](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="980df-143">Learn more about [the new Users experience](investigate-users.md).</span></span>

<span data-ttu-id="980df-144">事件信息显示在受影响的邮箱旁边的用户/标识详细信息和存在风险的设备。</span><span class="sxs-lookup"><span data-stu-id="980df-144">Incident information shows user/identity specifics and at-risk devices, beside affected mailboxes.</span></span> <span data-ttu-id="980df-145">它还关联所有 **调查信息和收集\*\*\*\*的证据**。</span><span class="sxs-lookup"><span data-stu-id="980df-145">It also relates any **Investigation information** and gathered **Evidence**.</span></span> <span data-ttu-id="980df-146">这使管理员和安全操作团队可以更轻松地从一个高风险警报透视到受影响的用户和邮箱。</span><span class="sxs-lookup"><span data-stu-id="980df-146">This makes it easier for admins and security operation teams to pivot from one high-risk alert to the affected users and mailboxes.</span></span> <span data-ttu-id="980df-147">查看 **此页面顶部的** "事件"选项卡，此单个位置提供了其他关键安全透视。</span><span class="sxs-lookup"><span data-stu-id="980df-147">Looking at the **Incident** tabs at the top of this page, there are other key security pivots available from this single location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="980df-148">在特定事件的任何页面顶部，你将看到摘要、警报、设备、用户、**邮箱**、调查和 **证据选项卡。**   </span><span class="sxs-lookup"><span data-stu-id="980df-148">Along the top of any page for a specific Incident, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span>

<span data-ttu-id="980df-149">选择 **"** 调查"将打开一个页面，其中显示正在分析的图形，并列出状态 (如等待审批) 修正。</span><span class="sxs-lookup"><span data-stu-id="980df-149">Selecting **Investigations** opens  a page that features a graphic of the analysis taking place and lists a status (such as **pending approval**) for remediation.</span></span> <span data-ttu-id="980df-150">花时间选择环境中的特定事件，深入到这些选项卡，然后实践为不同类型的威胁构建配置文件。</span><span class="sxs-lookup"><span data-stu-id="980df-150">Take time to select specific incidents in your environment, drill down into these tabs, and practice building a profile for different kinds of threats.</span></span> <span data-ttu-id="980df-151">熟悉度将受益于任何稍后的紧急调查。</span><span class="sxs-lookup"><span data-stu-id="980df-151">Familiarity will benefit any later pressing investigations.</span></span>

## <a name="improved-processes"></a><span data-ttu-id="980df-152">改进的流程</span><span class="sxs-lookup"><span data-stu-id="980df-152">Improved processes</span></span>

<span data-ttu-id="980df-153">常用控件和内容要么显示在同一位置，要么压缩为一个数据馈送，以便于查找。</span><span class="sxs-lookup"><span data-stu-id="980df-153">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="980df-154">例如，统一设置。</span><span class="sxs-lookup"><span data-stu-id="980df-154">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="980df-155">统一设置</span><span class="sxs-lookup"><span data-stu-id="980df-155">Unified settings</span></span>

![单击"角色"并打开"设置"页，其中包括常规设置、权限、API 和规则。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="980df-159">角色&权限</span><span class="sxs-lookup"><span data-stu-id="980df-159">Permissions & roles</span></span>

!["&角色"页显示终结点角色&组、角色和设备组。](../../media/converged-roles-5.png)

 <span data-ttu-id="980df-161">访问 Microsoft 365 安全中心使用 Azure Active Directory 全局角色或自定义角色进行配置。</span><span class="sxs-lookup"><span data-stu-id="980df-161">Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="980df-162">对于适用于终结点的 Defender，请参阅 [分配用户对 Microsoft Defender 安全中心的访问权限](/microsoft-365/security/defender-endpoint/assign-portal-access)。</span><span class="sxs-lookup"><span data-stu-id="980df-162">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/assign-portal-access).</span></span> <span data-ttu-id="980df-163">对于适用于 Office 365 的 Defender，请参阅 [Microsoft 365 合规中心和 Microsoft 365 安全中心中的权限](../defender-365-security/permissions-microsoft-365-compliance-security.md)。</span><span class="sxs-lookup"><span data-stu-id="980df-163">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](../defender-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="980df-164">详细了解如何管理对 [Microsoft 365 Defender 的访问权限](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="980df-164">Learn more about how to [manage access to Microsoft 365 Defender](m365d-permissions.md)</span></span>
- <span data-ttu-id="980df-165">详细了解如何在 Microsoft 365 [安全中心](custom-roles.md) 创建自定义角色</span><span class="sxs-lookup"><span data-stu-id="980df-165">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 security center</span></span>

> [!NOTE]
> <span data-ttu-id="980df-166">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商 [ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 授予访问权限，方式与在 [Microsoft Defender](./mssp-access.md)安全中心授予访问权限的方式相同。</span><span class="sxs-lookup"><span data-stu-id="980df-166">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="980df-167">集成报告</span><span class="sxs-lookup"><span data-stu-id="980df-167">Integrated reports</span></span>

<span data-ttu-id="980df-168">Microsoft 365 安全中心也统一了报告。</span><span class="sxs-lookup"><span data-stu-id="980df-168">Reports are also unified in the Microsoft 365 security center.</span></span> <span data-ttu-id="980df-169">管理员可以从一般安全报告开始，分支到有关终结点、电子邮件和协作&报告。</span><span class="sxs-lookup"><span data-stu-id="980df-169">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="980df-170">此处的链接基于工作负荷配置动态生成。</span><span class="sxs-lookup"><span data-stu-id="980df-170">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="980df-171">快速查看 Microsoft 365 环境</span><span class="sxs-lookup"><span data-stu-id="980df-171">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="980df-172">主页 **显示** 安全团队所需的许多公用卡片。</span><span class="sxs-lookup"><span data-stu-id="980df-172">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="980df-173">卡片和数据的组合取决于用户角色。</span><span class="sxs-lookup"><span data-stu-id="980df-173">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="980df-174">由于 Microsoft 365 安全中心使用基于角色的访问控制，因此不同的角色将看到对日常工作更有意义的卡片。</span><span class="sxs-lookup"><span data-stu-id="980df-174">Because the Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="980df-175">此概览信息可帮助您了解组织中的最新活动。</span><span class="sxs-lookup"><span data-stu-id="980df-175">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="980df-176">Microsoft 365 安全中心将来自不同来源的信号汇集在一起，以呈现 Microsoft 365 环境的整体视图。</span><span class="sxs-lookup"><span data-stu-id="980df-176">The Microsoft 365 security center brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="980df-177">卡片分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="980df-177">The cards fall into these categories:</span></span>

- <span data-ttu-id="980df-178">**标识**- 监视组织中的身份，并跟踪可疑或有风险的行为。</span><span class="sxs-lookup"><span data-stu-id="980df-178">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="980df-179">[了解有关标识保护的更多信息](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="980df-179">[Learn more about identity protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="980df-180">**数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。</span><span class="sxs-lookup"><span data-stu-id="980df-180">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="980df-181">**设备** - 获取有关设备上警报、泄露活动和其他威胁最新信息。</span><span class="sxs-lookup"><span data-stu-id="980df-181">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="980df-182">**应用** - 深入了解在组织中如何使用云应用。</span><span class="sxs-lookup"><span data-stu-id="980df-182">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="980df-183">[了解有关 Cloud App Security 发现的应用的更多信息](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="980df-183">[Learn more about Cloud App Security discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="980df-184">具有更好的数据覆盖范围的威胁分析</span><span class="sxs-lookup"><span data-stu-id="980df-184">Threat analytics with better data coverage</span></span>
<span data-ttu-id="980df-185">通过以下 Microsoft 365 Defender 威胁分析集成体验跟踪和响应新出现的威胁：</span><span class="sxs-lookup"><span data-stu-id="980df-185">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="980df-186">Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的数据覆盖范围更好，从而可以跨域进行联合事件管理、自动调查、修正以及主动或被动威胁搜寻。</span><span class="sxs-lookup"><span data-stu-id="980df-186">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="980df-187">来自 Microsoft Defender for Office 365 的电子邮件相关检测和缓解，以及 Microsoft Defender for Endpoint 中已提供的终结点数据。</span><span class="sxs-lookup"><span data-stu-id="980df-187">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="980df-188">威胁相关事件的视图，将警报聚合到跨 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的端到端攻击案例，以减少工作队列，以及简化和加快调查。</span><span class="sxs-lookup"><span data-stu-id="980df-188">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="980df-189">Microsoft 365 Defender 解决方案检测到并阻止的攻击尝试。</span><span class="sxs-lookup"><span data-stu-id="980df-189">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="980df-190">还有一些数据可用于推动预防性操作，以缓解进一步暴露的风险并增加恢复能力。</span><span class="sxs-lookup"><span data-stu-id="980df-190">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="980df-191">增强型设计，将可操作信息置于聚焦中，帮助你快速识别数据以紧急关注、调查和利用报告。</span><span class="sxs-lookup"><span data-stu-id="980df-191">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="980df-192">集中式学习中心</span><span class="sxs-lookup"><span data-stu-id="980df-192">A centralized Learning Hub</span></span>

<span data-ttu-id="980df-193">Microsoft 365 安全中心包括一个学习中心，从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区以及 docs.microsoft.com 上的官方文档等资源中提供正式指导。</span><span class="sxs-lookup"><span data-stu-id="980df-193">The Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="980df-194">在学习中心内，Email & Collaboration (Microsoft Defender for Office 365 或 MDO) 指南与 Endpoint (Microsoft Defender for Endpoint 或 MDE) 以及 Microsoft 365 Defender 学习资源并排提供。</span><span class="sxs-lookup"><span data-stu-id="980df-194">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365 or MDO) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint or MDE), and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="980df-195">学习中心将打开，学习路径围绕"如何使用 Microsoft 365 Defender 进行调查？"等主题组织。</span><span class="sxs-lookup"><span data-stu-id="980df-195">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="980df-196">和"Microsoft Defender for Office 365 最佳做法"。</span><span class="sxs-lookup"><span data-stu-id="980df-196">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="980df-197">此部分当前由 Microsoft 内部的安全产品组提供。</span><span class="sxs-lookup"><span data-stu-id="980df-197">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="980df-198">每个学习路径反映了了解概念所花的预计时间。</span><span class="sxs-lookup"><span data-stu-id="980df-198">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="980df-199">例如，"Microsoft Defender for Office 365 用户帐户泄露时要执行的步骤"预计需要 8 分钟，并且会进行一些有价值的学习。</span><span class="sxs-lookup"><span data-stu-id="980df-199">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="980df-200">单击内容后，为该网站添加书签，将书签组织到"安全"或"关键"文件夹中可能很有用。</span><span class="sxs-lookup"><span data-stu-id="980df-200">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="980df-201">To see all Learning paths， click the Show all link in the main panel.</span><span class="sxs-lookup"><span data-stu-id="980df-201">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="980df-202">Microsoft 365 安全中心学习中心顶部有一些有用的筛选器，可让你选择当前为 Microsoft 365 Defender 的产品 (Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365) 。 </span><span class="sxs-lookup"><span data-stu-id="980df-202">There are helpful **filters** along the top of the Microsoft 365 security center learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="980df-203">请注意，列出了每个部分的学习资源数量，这可以帮助学习者跟踪他们有多少资源可用于培训和学习。</span><span class="sxs-lookup"><span data-stu-id="980df-203">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="980df-204">除产品筛选器外，还列出了当前主题、 (网络研讨会) 、对安全区域、安全角色和产品功能的熟悉程度或经验。</span><span class="sxs-lookup"><span data-stu-id="980df-204">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="980df-205">向我们发送反馈</span><span class="sxs-lookup"><span data-stu-id="980df-205">Send us your feedback</span></span>

<span data-ttu-id="980df-206">我们需要你提供反馈。</span><span class="sxs-lookup"><span data-stu-id="980df-206">We need your feedback.</span></span> <span data-ttu-id="980df-207">我们一直在希望改进，因此如果你希望查看某些内容，请将 [你的 Microsoft 365 Defender 反馈发送给我们](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。</span><span class="sxs-lookup"><span data-stu-id="980df-207">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="980df-208">您还可以从本文留下反馈。</span><span class="sxs-lookup"><span data-stu-id="980df-208">You can also leave feedback from this article.</span></span> <span data-ttu-id="980df-209">在"提交和查看反馈"结尾的"反馈"部分中，选项为 *"此* 产品"或 *"此页面"。*</span><span class="sxs-lookup"><span data-stu-id="980df-209">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="980df-210">使用 **"此产品** "按钮获得 *产品* 反馈：</span><span class="sxs-lookup"><span data-stu-id="980df-210">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="980df-211">在 *文章* 底部选择"此产品"。</span><span class="sxs-lookup"><span data-stu-id="980df-211">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="980df-212">如果要继续阅读这些方向，请右键单击该按钮，然后单击"在新建选项卡中打开"。</span><span class="sxs-lookup"><span data-stu-id="980df-212">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="980df-213">这将导航到 **UserVoice 论坛**。</span><span class="sxs-lookup"><span data-stu-id="980df-213">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="980df-214">有 2 个选项：</span><span class="sxs-lookup"><span data-stu-id="980df-214">You have 2 options:</span></span>
    1. <span data-ttu-id="980df-215">向下滚动到文本框 *"我们可以如何在 Office 365* 中提高合规性或更好地保护你的用户？"，并粘贴到 *Microsoft 365 安全中心*。</span><span class="sxs-lookup"><span data-stu-id="980df-215">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 security center*.</span></span> <span data-ttu-id="980df-216">可以在结果中搜索类似你的想法并投票，或使用"发布新想法 **"按钮**。</span><span class="sxs-lookup"><span data-stu-id="980df-216">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="980df-217">如果确定已报告此问题，并且想要通过投票 (或) ，请使用 UserVoice 右边的"提供反馈"框。 </span><span class="sxs-lookup"><span data-stu-id="980df-217">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="980df-218">搜索 *Microsoft 365 安全中心*，查找问题，并使用投票 **按钮** 提升其状态。</span><span class="sxs-lookup"><span data-stu-id="980df-218">Search for *Microsoft 365 security center*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="980df-219">使用 *此页面* 可就文章本身提供反馈。</span><span class="sxs-lookup"><span data-stu-id="980df-219">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="980df-220">感谢您的反馈。</span><span class="sxs-lookup"><span data-stu-id="980df-220">Thanks for your feedback.</span></span> <span data-ttu-id="980df-221">您的声音可帮助我们改进产品。</span><span class="sxs-lookup"><span data-stu-id="980df-221">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="980df-222">探索安全中心必须提供哪些功能</span><span class="sxs-lookup"><span data-stu-id="980df-222">Explore what the security center has to offer</span></span>

<span data-ttu-id="980df-223">继续探索 Microsoft 365 安全中心中的特性和功能：</span><span class="sxs-lookup"><span data-stu-id="980df-223">Keep exploring the features and capabilities in the Microsoft 365 security center:</span></span>

- [<span data-ttu-id="980df-224">管理事件和警报</span><span class="sxs-lookup"><span data-stu-id="980df-224">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="980df-225">使用威胁分析跟踪和响应新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="980df-225">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="980df-226">操作中心</span><span class="sxs-lookup"><span data-stu-id="980df-226">The Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="980df-227">跨设备、电子邮件、应用和标识搜索威胁</span><span class="sxs-lookup"><span data-stu-id="980df-227">Hunt for threats across devices, emails, apps, and identities</span></span>](./advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="980df-228">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="980df-228">Custom detection rules</span></span>](./custom-detection-rules.md)
- [<span data-ttu-id="980df-229">电子邮件和协作警报</span><span class="sxs-lookup"><span data-stu-id="980df-229">Email & collaboration alerts</span></span>](../../compliance/alert-policies.md#default-alert-policies)
- <span data-ttu-id="980df-230">[创建网络钓鱼攻击模拟](../defender-365-security/attack-simulation-training.md)[并创建用于培训团队的有效负载](/microsoft-365/security/defender-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="980df-230">[Create a phishing attack simulation](../defender-365-security/attack-simulation-training.md) and [create a payload for training your teams](/microsoft-365/security/defender-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="980df-231">相关信息</span><span class="sxs-lookup"><span data-stu-id="980df-231">Related information</span></span>
- [<span data-ttu-id="980df-232">Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="980df-232">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="980df-233">Microsoft 365 安全中心中适用于 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="980df-233">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="980df-234">Microsoft 365 安全中心中的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="980df-234">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="980df-235">将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="980df-235">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)