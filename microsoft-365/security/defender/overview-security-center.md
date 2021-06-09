---
title: Microsoft 365合并 MDO、MDE、MDI 和 MCAS 的 Defender 概述
description: Microsoft 365 Defender 的优势，将适用于 Office 365 (MDO) 的 Microsoft Defender 与适用于终结点 (MDE) 的 Microsoft Defender 与 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 结合使用。 本文概述了Microsoft 365 Defender 的前进。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
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
ms.openlocfilehash: e88f23013a1a7d9fbeb6ae1d72592182eaaa7547
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841674"
---
# <a name="microsoft-365-defender-overview"></a><span data-ttu-id="bf58b-105">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="bf58b-105">Microsoft 365 Defender overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bf58b-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bf58b-106">**Applies to:**</span></span>

- [<span data-ttu-id="bf58b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf58b-107">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="bf58b-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf58b-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf58b-109">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="bf58b-109">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

> <span data-ttu-id="bf58b-110">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="bf58b-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="bf58b-111">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-111">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

<span data-ttu-id="bf58b-112">**Microsoft 365 Defender** () 中心门户中，将电子邮件、协作、标识和设备威胁的保护、检测、调查和 [https://security.microsoft.com](https://security.microsoft.com) 响应组合在一起。 </span><span class="sxs-lookup"><span data-stu-id="bf58b-112">**Microsoft 365 Defender** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="bf58b-113">Microsoft 365Defender 将现有 Microsoft 安全门户（如 Microsoft Defender 安全中心 和 Office 365 安全&中心）的功能汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="bf58b-113">Microsoft 365 Defender brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="bf58b-114">安全中心强调快速访问信息、简化布局以及将相关信息汇集在一起以便于使用。</span><span class="sxs-lookup"><span data-stu-id="bf58b-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="bf58b-115">此中心包括：</span><span class="sxs-lookup"><span data-stu-id="bf58b-115">This center includes:</span></span>

- <span data-ttu-id="bf58b-116">**[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365通过一组防护、检测、调查和搜寻功能帮助组织保护其企业，以保护电子邮件Office 365资源。</span><span class="sxs-lookup"><span data-stu-id="bf58b-116">**[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="bf58b-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 为贵组织的设备提供预防性保护、攻破后检测、自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="bf58b-117">**[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="bf58b-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** 是 Microsoft 扩展检测和响应 *(* XDR) 解决方案的一部分，该解决方案利用 Microsoft 365 安全项目组合自动分析跨域的威胁数据，并生成单个仪表板上攻击的图片。</span><span class="sxs-lookup"><span data-stu-id="bf58b-118">**[Microsoft 365 Defender](microsoft-365-defender.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="bf58b-119">如果需要有关安全与合规中心或Office 365更改&的信息，Microsoft Defender 安全中心：</span><span class="sxs-lookup"><span data-stu-id="bf58b-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="bf58b-120">defender for Office 365 in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf58b-120">Defender for Office 365 in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="bf58b-121">Microsoft 365 Defender 中的 Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf58b-121">Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)

> [!NOTE]
> <span data-ttu-id="bf58b-122">安全Microsoft 365门户使用和强制执行现有的基于角色的访问，并且将每个安全模型移动到统一门户。</span><span class="sxs-lookup"><span data-stu-id="bf58b-122">The Microsoft 365 security portal uses and enforces existing roles-based access, and will move each security model into the unified portal.</span></span> <span data-ttu-id="bf58b-123">每个聚合工作负荷 (如 MDO 或 MDE) 都有自己的基于角色的访问。</span><span class="sxs-lookup"><span data-stu-id="bf58b-123">Each converged workload (such as MDO or MDE) has its own roles-based access.</span></span> <span data-ttu-id="bf58b-124">产品中已有的角色将自动聚合到Microsoft 365门户中。</span><span class="sxs-lookup"><span data-stu-id="bf58b-124">The roles already in the products will be converged into the Microsoft 365 security portal, automatically.</span></span> <span data-ttu-id="bf58b-125">但是，MCAS 的角色和权限仍将在 MCAS 中处理。</span><span class="sxs-lookup"><span data-stu-id="bf58b-125">However, roles and permissions for MCAS will still handled over in MCAS.</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="bf58b-126">预期结果</span><span class="sxs-lookup"><span data-stu-id="bf58b-126">What to expect</span></span>

<span data-ttu-id="bf58b-127">现在，可在 Office 365 Defender 中Office 365安全与合规中心 (protection.office.com) 和 Microsoft Defender 安全中心 (securitycenter.microsoft.com) 使用的所有安全Microsoft 365 *内容*。</span><span class="sxs-lookup"><span data-stu-id="bf58b-127">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 Defender*.</span></span>

<span data-ttu-id="bf58b-128">Microsoft 365Defender 通过将来自不同工作负载的信号引入一组统一体验来帮助安全团队调查和响应攻击：：</span><span class="sxs-lookup"><span data-stu-id="bf58b-128">Microsoft 365 Defender helps security teams investigate and respond to attacks by bringing in signals from different workloads into a set of unified experiences for:</span></span>

- <span data-ttu-id="bf58b-129">事件&警报</span><span class="sxs-lookup"><span data-stu-id="bf58b-129">Incidents & alerts</span></span>
- <span data-ttu-id="bf58b-130">搜寻</span><span class="sxs-lookup"><span data-stu-id="bf58b-130">Hunting</span></span>
- <span data-ttu-id="bf58b-131">操作中心</span><span class="sxs-lookup"><span data-stu-id="bf58b-131">Action center</span></span>
- <span data-ttu-id="bf58b-132">威胁分析</span><span class="sxs-lookup"><span data-stu-id="bf58b-132">Threat analytics</span></span>

<span data-ttu-id="bf58b-133">Microsoft 365Defender 在 *将* Microsoft Defender for Office 365和 Microsoft Defender for Endpoint 合并时，它强调统一、清晰和共同的目标。</span><span class="sxs-lookup"><span data-stu-id="bf58b-133">Microsoft 365 Defender emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bf58b-134">合并基于下面列出的优先级，在不影响每个安全套件组合提供的功能的情况下进行：</span><span class="sxs-lookup"><span data-stu-id="bf58b-134">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination of:</span></span>

- <span data-ttu-id="bf58b-135">常见构建基块</span><span class="sxs-lookup"><span data-stu-id="bf58b-135">Common building blocks</span></span>
- <span data-ttu-id="bf58b-136">常用术语</span><span class="sxs-lookup"><span data-stu-id="bf58b-136">Common terminology</span></span>
- <span data-ttu-id="bf58b-137">常见实体</span><span class="sxs-lookup"><span data-stu-id="bf58b-137">Common entities</span></span>
- <span data-ttu-id="bf58b-138">与其他工作负荷的功能奇偶校验</span><span class="sxs-lookup"><span data-stu-id="bf58b-138">Feature parity with other workloads</span></span>

> [!NOTE]
> <span data-ttu-id="bf58b-139">Microsoft 365无需客户执行迁移步骤或购买新许可证，即可访问 Defender。</span><span class="sxs-lookup"><span data-stu-id="bf58b-139">Microsoft 365 Defender will be accessible without any need for customers to take migration steps or purchase a new license.</span></span> <span data-ttu-id="bf58b-140">例如，具有 E3 订阅的管理员可以访问这个新门户，就像使用 Microsoft Defender for Office 365 计划 1 和计划 2 的管理员一样;但是，Exchange Online Protection或 MDO 计划 1 客户只能看到其订阅许可证支持的安全功能。</span><span class="sxs-lookup"><span data-stu-id="bf58b-140">For example, this new portal will be accessible to administrators with an E3 subscription, just as it is to those with Microsoft Defender for Office 365 Plan 1 and Plan 2; however, Exchange Online Protection, or MDO Plan 1 customers will see only the security features their subscription license supports.</span></span> <span data-ttu-id="bf58b-141">新中心的目标是集中安全性。</span><span class="sxs-lookup"><span data-stu-id="bf58b-141">The goal of the new center is to centralize security.</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="bf58b-142">统一调查</span><span class="sxs-lookup"><span data-stu-id="bf58b-142">Unified investigations</span></span>

<span data-ttu-id="bf58b-143">聚合安全中心为调查整个安全中心的安全事件Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bf58b-143">Converging security centers creates a single place for investigating security incidents across Microsoft 365.</span></span> <span data-ttu-id="bf58b-144">主要示例是 **"事件**"下& **Defender** 快速启动时警报Microsoft 365事件。</span><span class="sxs-lookup"><span data-stu-id="bf58b-144">A primary example is **Incidents** under **Incidents & alerts** on the quick launch of Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Microsoft 365 Defender 中的&quot;事件&quot;页面。":::

<span data-ttu-id="bf58b-146">选择事件名称将显示一个页面，该页面演示聚合安全中心的价值。</span><span class="sxs-lookup"><span data-stu-id="bf58b-146">Selecting an incident name displays a page that demonstrates the value of converging security centers.</span></span>

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender 中事件的&quot;摘要&quot;页面示例":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender](../../media/converged-incident-info-3.png)
--> 

<span data-ttu-id="bf58b-148">在事件页面顶部，你将看到摘要、警报、设备、**用户**、**邮箱**、调查和 **证据** 选项卡。   </span><span class="sxs-lookup"><span data-stu-id="bf58b-148">Along the top of an incident page, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span> <span data-ttu-id="bf58b-149">选择这些选项卡可获取更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="bf58b-149">Select these tabs for more detailed information.</span></span> <span data-ttu-id="bf58b-150">例如，"用户"选项卡显示聚合工作负载 (Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security) 以及一系列源（如本地 Active Directory 域服务 (AD DS) 、Azure Active Directory (Azure AD) 和第三方标识提供程序）的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="bf58b-150">For example, the **Users** tab displays information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security) and a range of sources such as on-premises Active Directory Domain Services (AD DS), Azure Active Directory (Azure AD), and third-party identity providers.</span></span> <span data-ttu-id="bf58b-151">有关详细信息，请参阅 [调查用户](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-151">For more information, see [investigate users](investigate-users.md).</span></span>

<span data-ttu-id="bf58b-152">花时间查看环境中的事件，深入了解这些选项卡，并实践了解如何访问为不同类型的威胁事件提供的信息。</span><span class="sxs-lookup"><span data-stu-id="bf58b-152">Take the time to review the incidents in your environment, drill down into these tabs, and practice building an understanding of how to access the information provided for incidents for different kinds of threats.</span></span>

<span data-ttu-id="bf58b-153">有关详细信息，请参阅[Microsoft 365 Defender 中的事件](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-153">For more information, see [incidents in Microsoft 365 Defender](incidents-overview.md).</span></span>

## <a name="improved-processes"></a><span data-ttu-id="bf58b-154">改进的流程</span><span class="sxs-lookup"><span data-stu-id="bf58b-154">Improved processes</span></span>

<span data-ttu-id="bf58b-155">常用控件和内容要么显示在同一位置，要么压缩为一个数据馈送，以便于查找。</span><span class="sxs-lookup"><span data-stu-id="bf58b-155">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="bf58b-156">例如，统一设置。</span><span class="sxs-lookup"><span data-stu-id="bf58b-156">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="bf58b-157">统一设置</span><span class="sxs-lookup"><span data-stu-id="bf58b-157">Unified settings</span></span>

![单击"角色"并打开设置页面，其中包括常规设置、权限、API 和规则。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="bf58b-161">角色&权限</span><span class="sxs-lookup"><span data-stu-id="bf58b-161">Permissions & roles</span></span>

!["&角色"页显示终结点角色&组、角色和设备组。](../../media/converged-roles-5.png)

 <span data-ttu-id="bf58b-163">对 Microsoft 365 Defender 的访问权限使用全局Azure Active Directory角色或自定义角色进行配置。</span><span class="sxs-lookup"><span data-stu-id="bf58b-163">Access to Microsoft 365 Defender is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="bf58b-164">对于 Defender for Endpoint，请参阅[分配用户对 Microsoft Defender 安全中心](/microsoft-365/security/defender-endpoint/assign-portal-access)的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf58b-164">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/assign-portal-access).</span></span> <span data-ttu-id="bf58b-165">For Defender for Office 365， see [Permissions in the Microsoft 365 compliance center and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).</span><span class="sxs-lookup"><span data-stu-id="bf58b-165">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="bf58b-166">了解有关如何管理对[Microsoft 365 Defender 的访问权限](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="bf58b-166">Learn more about how to [manage access to Microsoft 365 Defender](m365d-permissions.md)</span></span>
- <span data-ttu-id="bf58b-167">详细了解如何在 Microsoft 365 [](custom-roles.md) Defender 中创建自定义角色</span><span class="sxs-lookup"><span data-stu-id="bf58b-167">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 Defender</span></span>

> [!NOTE]
> <span data-ttu-id="bf58b-168">Microsoft 365 Defender 中的 Microsoft Defender for Endpoint 支持向托管安全服务提供商[ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)授予访问权限，方式与在 Microsoft Defender 安全中心中授予访问权限[的方式相同](./mssp-access.md)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-168">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="bf58b-169">集成报告</span><span class="sxs-lookup"><span data-stu-id="bf58b-169">Integrated reports</span></span>

<span data-ttu-id="bf58b-170">报告在 Microsoft 365 Defender 中也统一。</span><span class="sxs-lookup"><span data-stu-id="bf58b-170">Reports are also unified in Microsoft 365 Defender.</span></span> <span data-ttu-id="bf58b-171">管理员可以从一般安全报告开始，分支到有关终结点、电子邮件和协作&报告。</span><span class="sxs-lookup"><span data-stu-id="bf58b-171">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="bf58b-172">此处的链接基于工作负荷配置动态生成。</span><span class="sxs-lookup"><span data-stu-id="bf58b-172">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="bf58b-173">快速查看Microsoft 365环境</span><span class="sxs-lookup"><span data-stu-id="bf58b-173">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="bf58b-174">主页 **显示** 安全团队所需的许多公用卡片。</span><span class="sxs-lookup"><span data-stu-id="bf58b-174">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="bf58b-175">卡片和数据的组合取决于用户角色。</span><span class="sxs-lookup"><span data-stu-id="bf58b-175">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="bf58b-176">由于Microsoft 365中心使用基于角色的访问控制，因此不同的角色将看到对日常工作更有意义的卡片。</span><span class="sxs-lookup"><span data-stu-id="bf58b-176">Because Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="bf58b-177">此概览信息可帮助您了解组织中的最新活动。</span><span class="sxs-lookup"><span data-stu-id="bf58b-177">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="bf58b-178">Microsoft 365Defender 将来自不同源的信号汇集在一起，以呈现你的Microsoft 365视图。</span><span class="sxs-lookup"><span data-stu-id="bf58b-178">Microsoft 365 Defender brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="bf58b-179">卡片分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="bf58b-179">The cards fall into these categories:</span></span>

- <span data-ttu-id="bf58b-180">**标识**- 监视组织中的身份，并跟踪可疑或有风险的行为。</span><span class="sxs-lookup"><span data-stu-id="bf58b-180">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="bf58b-181">[了解有关标识保护的更多信息](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-181">[Learn more about identity protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="bf58b-182">**数据** - 帮助跟踪可能导致未经授权的数据泄露的用户活动。</span><span class="sxs-lookup"><span data-stu-id="bf58b-182">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="bf58b-183">**设备** - 获取有关设备上警报、泄露活动和其他威胁最新信息。</span><span class="sxs-lookup"><span data-stu-id="bf58b-183">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="bf58b-184">**应用** - 深入了解在组织中如何使用云应用。</span><span class="sxs-lookup"><span data-stu-id="bf58b-184">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="bf58b-185">[了解有关已发现云应用安全应用的信息](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-185">[Learn more about Cloud App Security discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="bf58b-186">具有更好的数据覆盖范围的威胁分析</span><span class="sxs-lookup"><span data-stu-id="bf58b-186">Threat analytics with better data coverage</span></span>
<span data-ttu-id="bf58b-187">通过以下 Defender 威胁分析集成体验Microsoft 365和应对新出现的威胁：</span><span class="sxs-lookup"><span data-stu-id="bf58b-187">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="bf58b-188">Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的数据覆盖范围更好，从而可以跨域进行联合事件管理、自动调查、修正以及主动或被动威胁搜寻。</span><span class="sxs-lookup"><span data-stu-id="bf58b-188">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="bf58b-189">来自 Microsoft Defender for Office 365 电子邮件相关的检测和缓解，以及 Microsoft Defender for Endpoint 中已提供的终结点数据。</span><span class="sxs-lookup"><span data-stu-id="bf58b-189">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="bf58b-190">威胁相关事件的视图，可跨 Microsoft Defender for Endpoint 和 microsoft Defender for Office 365 将警报聚合到端到端攻击案例，以减少工作队列，以及简化和加快调查。</span><span class="sxs-lookup"><span data-stu-id="bf58b-190">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="bf58b-191">Defender 解决方案检测到并阻止Microsoft 365攻击尝试。</span><span class="sxs-lookup"><span data-stu-id="bf58b-191">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="bf58b-192">还有一些数据可用于推动预防性操作，以缓解进一步暴露的风险并增加恢复能力。</span><span class="sxs-lookup"><span data-stu-id="bf58b-192">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="bf58b-193">增强型设计，将可操作信息置于聚焦中，帮助你快速识别数据以紧急关注、调查和利用报告。</span><span class="sxs-lookup"><span data-stu-id="bf58b-193">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="bf58b-194">集中式学习中心</span><span class="sxs-lookup"><span data-stu-id="bf58b-194">A centralized Learning Hub</span></span>

<span data-ttu-id="bf58b-195">Microsoft 365安全中心包括一个学习中心，从 Microsoft 安全博客、YouTube 上的 Microsoft 安全社区以及 docs.microsoft.com 上的官方文档等资源中提供正式指导。</span><span class="sxs-lookup"><span data-stu-id="bf58b-195">Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="bf58b-196">在学习中心内，电子邮件 & 协作 (Microsoft Defender for Office 365 或 MDO) 指南与 Endpoint (Microsoft Defender for Endpoint 或 MDE) 以及 Microsoft 365 Defender 学习资源并行提供。</span><span class="sxs-lookup"><span data-stu-id="bf58b-196">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365 or MDO) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint or MDE), and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="bf58b-197">学习中心将打开，学习路径围绕"如何使用 defender Microsoft 365调查？"</span><span class="sxs-lookup"><span data-stu-id="bf58b-197">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="bf58b-198">和"Microsoft Defender for Office 365最佳做法"。</span><span class="sxs-lookup"><span data-stu-id="bf58b-198">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="bf58b-199">此部分当前由 Microsoft 内部的安全产品组提供。</span><span class="sxs-lookup"><span data-stu-id="bf58b-199">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="bf58b-200">每个学习路径反映了了解概念所花的预计时间。</span><span class="sxs-lookup"><span data-stu-id="bf58b-200">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="bf58b-201">例如，"Microsoft Defender for Office 365用户帐户泄露时要执行的步骤"预计需要 8 分钟，并且会进行一些有价值的学习。</span><span class="sxs-lookup"><span data-stu-id="bf58b-201">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="bf58b-202">单击内容后，为该网站添加书签，将书签组织到"安全"或"关键"文件夹中可能很有用。</span><span class="sxs-lookup"><span data-stu-id="bf58b-202">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="bf58b-203">To see all Learning paths， click the Show all link in the main panel.</span><span class="sxs-lookup"><span data-stu-id="bf58b-203">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="bf58b-204">Microsoft 365 Defender学习中心顶部有有用的筛选器，让你可以选择当前 (Microsoft 365 Defender、Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="bf58b-204">There are helpful **filters** along the top of Microsoft 365 Defender learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="bf58b-205">请注意，列出了每个部分的学习资源数量，这可以帮助学习者跟踪他们有多少资源可用于培训和学习。</span><span class="sxs-lookup"><span data-stu-id="bf58b-205">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="bf58b-206">除产品筛选器外，还列出了当前主题、 (网络研讨会) 、对安全区域、安全角色和产品功能的熟悉程度或经验。</span><span class="sxs-lookup"><span data-stu-id="bf58b-206">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

> [!TIP]
> <span data-ttu-id="bf58b-207">Microsoft Learn 中有很多其他 [学习机会](/e/learn/)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-207">There are lots of other learning opportunities in [Microsoft Learn](/e/learn/).</span></span> <span data-ttu-id="bf58b-208">你将找到认证培训，例如[MS-500T02-A：实施Microsoft 365威胁防护。](/learn/certifications/courses/ms-500t02)</span><span class="sxs-lookup"><span data-stu-id="bf58b-208">You'll find certification training such as [Course MS-500T02-A: Implementing Microsoft 365 Threat Protection](/learn/certifications/courses/ms-500t02).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="bf58b-209">向我们发送反馈</span><span class="sxs-lookup"><span data-stu-id="bf58b-209">Send us your feedback</span></span>

<span data-ttu-id="bf58b-210">我们需要你提供反馈。</span><span class="sxs-lookup"><span data-stu-id="bf58b-210">We need your feedback.</span></span> <span data-ttu-id="bf58b-211">我们一直在希望改进，因此如果你希望查看某些内容，请将你的 Microsoft 365 [Defender 反馈发送给我们](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。</span><span class="sxs-lookup"><span data-stu-id="bf58b-211">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="bf58b-212">您还可以从本文留下反馈。</span><span class="sxs-lookup"><span data-stu-id="bf58b-212">You can also leave feedback from this article.</span></span> <span data-ttu-id="bf58b-213">在"提交和查看反馈"结尾的"反馈"部分中，选项为 *"此* 产品"或 *"此页面"。*</span><span class="sxs-lookup"><span data-stu-id="bf58b-213">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="bf58b-214">使用 **"此产品** "按钮获得 *产品* 反馈：</span><span class="sxs-lookup"><span data-stu-id="bf58b-214">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="bf58b-215">在 *文章* 底部选择"此产品"。</span><span class="sxs-lookup"><span data-stu-id="bf58b-215">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="bf58b-216">如果要继续阅读这些方向，请右键单击该按钮，然后单击"在新建选项卡中打开"。</span><span class="sxs-lookup"><span data-stu-id="bf58b-216">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="bf58b-217">这将导航到 **UserVoice 论坛**。</span><span class="sxs-lookup"><span data-stu-id="bf58b-217">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="bf58b-218">有 2 个选项：</span><span class="sxs-lookup"><span data-stu-id="bf58b-218">You have 2 options:</span></span>
    1. <span data-ttu-id="bf58b-219">向下滚动到文本框"我们如何提高合规性或更好地保护用户 *Office 365？* 并粘贴到 *Microsoft 365 Defender 中*。</span><span class="sxs-lookup"><span data-stu-id="bf58b-219">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 Defender*.</span></span> <span data-ttu-id="bf58b-220">可以在结果中搜索类似你的想法并投票，或使用"发布新想法 **"按钮**。</span><span class="sxs-lookup"><span data-stu-id="bf58b-220">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="bf58b-221">如果确定已报告此问题，并且想要通过投票 (或) ，请使用 UserVoice 右边的"提供反馈"框。 </span><span class="sxs-lookup"><span data-stu-id="bf58b-221">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="bf58b-222">搜索 *Microsoft 365 Defender，* 查找问题 **，** 并使用投票按钮提升其状态。</span><span class="sxs-lookup"><span data-stu-id="bf58b-222">Search for *Microsoft 365 Defender*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="bf58b-223">使用 *此页面* 可就文章本身提供反馈。</span><span class="sxs-lookup"><span data-stu-id="bf58b-223">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="bf58b-224">感谢您的反馈。</span><span class="sxs-lookup"><span data-stu-id="bf58b-224">Thanks for your feedback.</span></span> <span data-ttu-id="bf58b-225">您的声音可帮助我们改进产品。</span><span class="sxs-lookup"><span data-stu-id="bf58b-225">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="bf58b-226">探索安全中心必须提供哪些功能</span><span class="sxs-lookup"><span data-stu-id="bf58b-226">Explore what the security center has to offer</span></span>

<span data-ttu-id="bf58b-227">继续探索 Microsoft 365 Defender 中的特性和功能：</span><span class="sxs-lookup"><span data-stu-id="bf58b-227">Keep exploring the features and capabilities in Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="bf58b-228">管理事件和警报</span><span class="sxs-lookup"><span data-stu-id="bf58b-228">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="bf58b-229">使用威胁分析跟踪和响应新出现的威胁</span><span class="sxs-lookup"><span data-stu-id="bf58b-229">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="bf58b-230">操作中心</span><span class="sxs-lookup"><span data-stu-id="bf58b-230">The Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="bf58b-231">跨设备、电子邮件、应用和标识搜索威胁</span><span class="sxs-lookup"><span data-stu-id="bf58b-231">Hunt for threats across devices, emails, apps, and identities</span></span>](./advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bf58b-232">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="bf58b-232">Custom detection rules</span></span>](./custom-detection-rules.md)
- [<span data-ttu-id="bf58b-233">电子邮件和协作警报</span><span class="sxs-lookup"><span data-stu-id="bf58b-233">Email & collaboration alerts</span></span>](../../compliance/alert-policies.md#default-alert-policies)
- <span data-ttu-id="bf58b-234">[创建网络钓鱼攻击模拟](../office-365-security/attack-simulation-training.md)[并创建用于培训团队的有效负载](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="bf58b-234">[Create a phishing attack simulation](../office-365-security/attack-simulation-training.md) and [create a payload for training your teams](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="bf58b-235">相关信息</span><span class="sxs-lookup"><span data-stu-id="bf58b-235">Related information</span></span>
- [<span data-ttu-id="bf58b-236">Microsoft Defender for Office 365 in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf58b-236">Microsoft Defender for Office 365 in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="bf58b-237">Microsoft Defender for Endpoint in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf58b-237">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="bf58b-238">将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf58b-238">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>](microsoft-365-security-mde-redirection.md)