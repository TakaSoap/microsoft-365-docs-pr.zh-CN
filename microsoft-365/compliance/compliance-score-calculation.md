---
title: 合规性分数计算
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解 Microsoft 合规性管理器如何根据为应对风险和改进合规性状态而采取的操作计算个性化分数。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 756ce207b1e9583bf63f19351e85955950487404
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052110"
---
# <a name="compliance-score-calculation"></a><span data-ttu-id="9f394-103">合规性分数计算</span><span class="sxs-lookup"><span data-stu-id="9f394-103">Compliance score calculation</span></span>

<span data-ttu-id="9f394-104">**本文内容：** 了解合规性管理器如何计算组织的合规性分数。</span><span class="sxs-lookup"><span data-stu-id="9f394-104">**In this article:** Learn how Compliance Manager calculates a compliance score for your organization.</span></span> <span data-ttu-id="9f394-105">本文介绍了如何解释分数、数据保护基线评估包括哪些内容、持续监视以及不同类型的操作如何管理和 **评分**。</span><span class="sxs-lookup"><span data-stu-id="9f394-105">This article explains how to **interpret your score**, what the **Data Protection Baseline assessment** includes, **continuous monitoring**, and **how different types of actions are managed and scored**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f394-106">来自合规性管理器的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="9f394-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="9f394-107">由你根据法规环境评估和验证客户控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="9f394-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="9f394-108">这些服务受联机服务条款中的 [条款和条件限制](https://go.microsoft.com/fwlink/?linkid=2108910)。</span><span class="sxs-lookup"><span data-stu-id="9f394-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="9f394-109">另请参阅 [Microsoft 365 安全与合规许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="9f394-109">See also [Microsoft 365 licensing guidance for security and compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-to-read-your-compliance-score"></a><span data-ttu-id="9f394-110">如何读取合规性分数</span><span class="sxs-lookup"><span data-stu-id="9f394-110">How to read your compliance score</span></span>

<span data-ttu-id="9f394-111">合规性管理器仪表板显示整体合规性分数。</span><span class="sxs-lookup"><span data-stu-id="9f394-111">The Compliance Manager dashboard displays your overall compliance score.</span></span> <span data-ttu-id="9f394-112">此分数用于衡量在控件中完成建议改进操作的进度。</span><span class="sxs-lookup"><span data-stu-id="9f394-112">This score measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="9f394-113">分数可帮助你了解当前的合规性状态。</span><span class="sxs-lookup"><span data-stu-id="9f394-113">Your score can help you understand your current compliance posture.</span></span> <span data-ttu-id="9f394-114">它还可以帮助您根据操作可降低风险的可能性确定操作优先级。</span><span class="sxs-lookup"><span data-stu-id="9f394-114">It can also help you prioritize actions based on their potential to reduce risk.</span></span>

<span data-ttu-id="9f394-115">分数值在三个级别分配：</span><span class="sxs-lookup"><span data-stu-id="9f394-115">A score value is assigned at three levels:</span></span>

1. <span data-ttu-id="9f394-116">**改进操作分数**：每项操作对分数的影响各不相同，具体取决于所涉及的潜在风险</span><span class="sxs-lookup"><span data-stu-id="9f394-116">**Improvement action score**: each action has a different impact on your score depending on the potential risk involved</span></span>

2. <span data-ttu-id="9f394-117">**控制分数**：此分数是完成控件中的改进操作所赚取的分数的总和。</span><span class="sxs-lookup"><span data-stu-id="9f394-117">**Control score**: this score is the sum of points earned by completing improvement actions within the control.</span></span> <span data-ttu-id="9f394-118">当控件满足以下两个条件时，此总和将全部应用于总体合规性分数：</span><span class="sxs-lookup"><span data-stu-id="9f394-118">This sum is applied in its entirety to your overall compliance score when the control meets both of the following conditions:</span></span>
    - <span data-ttu-id="9f394-119">**实现状态** 等于 **"已实现** " **或"备用实现"，** 并且</span><span class="sxs-lookup"><span data-stu-id="9f394-119">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
    - <span data-ttu-id="9f394-120">**测试结果等于\*\*\*\*通过**。</span><span class="sxs-lookup"><span data-stu-id="9f394-120">**Test Result** equals **Passed**.</span></span>

3. <span data-ttu-id="9f394-121">**评估分数**：此分数是控制分数的总和。</span><span class="sxs-lookup"><span data-stu-id="9f394-121">**Assessment score**: this score is the sum of your control scores.</span></span> <span data-ttu-id="9f394-122">它使用操作分数进行计算。</span><span class="sxs-lookup"><span data-stu-id="9f394-122">It is calculated using action scores.</span></span> <span data-ttu-id="9f394-123">你的组织管理的每个 Microsoft 操作和每个改进操作都计算一次，无论控件中引用它多久一次。</span><span class="sxs-lookup"><span data-stu-id="9f394-123">Each Microsoft action and each improvement action managed by your organization is counted once, regardless of how often it is referenced in a control.</span></span>

<span data-ttu-id="9f394-124">总体合规性分数使用操作分数计算，其中每个 Microsoft 操作计算一次，管理的每个技术操作计算一次，并且您管理的每个非技术操作按组计算一次。</span><span class="sxs-lookup"><span data-stu-id="9f394-124">The overall compliance score is calculated using action scores, where each Microsoft action is counted once, each technical action you manage is counted once, and each non-technical action you manage is counted once per group.</span></span> <span data-ttu-id="9f394-125">此逻辑旨在最准确地描述如何在组织中实施和测试操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-125">This logic is designed to provide the most accurate accounting of how actions are implemented and tested in your organization.</span></span> <span data-ttu-id="9f394-126">你可能会注意到，这可能会导致整体合规性分数与评估分数的平均值不同。</span><span class="sxs-lookup"><span data-stu-id="9f394-126">You may notice that this can cause your overall compliance score to differ from the average of your assessment scores.</span></span> <span data-ttu-id="9f394-127">阅读下文中 [有关操作如何进行评分的详细信息](#action-types-and-points)。</span><span class="sxs-lookup"><span data-stu-id="9f394-127">Read more below about [how actions are scored](#action-types-and-points).</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="9f394-128">基于 Microsoft 365 数据保护基线的初始分数</span><span class="sxs-lookup"><span data-stu-id="9f394-128">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="9f394-129">合规性管理器根据 Microsoft 365 数据保护基线提供初始分数。</span><span class="sxs-lookup"><span data-stu-id="9f394-129">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="9f394-130">此基线是一组控制措施，其中包括数据保护和一般数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="9f394-130">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="9f394-131">此基线主要来自 NIST CSF (国家标准和技术网络安全协会) 和 ISO (国际标准化组织) ，以及 FedRAMP (联邦风险和授权管理计划) 以及欧盟) 的 GDPR (一般数据保护条例。</span><span class="sxs-lookup"><span data-stu-id="9f394-131">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="9f394-132">根据提供给所有组织的默认数据保护基线评估计算初始分数。</span><span class="sxs-lookup"><span data-stu-id="9f394-132">Your initial score is calculated according to the default Data Protection Baseline assessment provided to all organizations.</span></span> <span data-ttu-id="9f394-133">首次访问时，合规性管理器已收集来自 Microsoft 365 解决方案的信号。</span><span class="sxs-lookup"><span data-stu-id="9f394-133">Upon your first visit, Compliance Manager is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="9f394-134">你可以一目了然地查看组织相对于关键数据保护标准和法规的表现，并查看建议的改进措施。</span><span class="sxs-lookup"><span data-stu-id="9f394-134">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="9f394-135">由于每个组织都有特定需求，因此合规性管理器需要你设置和管理评估，以帮助尽可能全面减少和减少风险。</span><span class="sxs-lookup"><span data-stu-id="9f394-135">Because every organization has specific needs, Compliance Manager relies on you to set up and manage assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-manager-continuously-assesses-controls"></a><span data-ttu-id="9f394-136">合规性管理器如何持续评估控制措施</span><span class="sxs-lookup"><span data-stu-id="9f394-136">How Compliance Manager continuously assesses controls</span></span>

<span data-ttu-id="9f394-137">合规性管理器自动扫描你的 Microsoft 365 环境并检测你的系统设置，持续自动更新你的技术操作状态。</span><span class="sxs-lookup"><span data-stu-id="9f394-137">Compliance Manager automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical action status.</span></span> <span data-ttu-id="9f394-138">Microsoft 安全分数是执行监视的基础引擎。</span><span class="sxs-lookup"><span data-stu-id="9f394-138">Microsoft Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="9f394-139">你的操作状态每 24 小时在仪表板上更新一次。</span><span class="sxs-lookup"><span data-stu-id="9f394-139">Your action status is updated on your dashboard every 24 hours.</span></span> <span data-ttu-id="9f394-140">按照建议实现控件后，通常会看到第二天更新了控件状态。</span><span class="sxs-lookup"><span data-stu-id="9f394-140">Once you follow a recommendation to implement a control, you’ll typically see the control status updated the next day.</span></span>

<span data-ttu-id="9f394-141">例如，如果你在 Azure AD 门户 (MFA) 多重身份验证，合规性管理器将检测该设置，并反映在控制访问解决方案详细信息中。</span><span class="sxs-lookup"><span data-stu-id="9f394-141">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Manager detects the setting and reflects it in the control access solution details.</span></span> <span data-ttu-id="9f394-142">相反，如果未打开 MFA，合规性管理器会将其标记为建议的操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-142">Conversely, if you didn’t turn on MFA, Compliance Manager flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="9f394-143">详细了解安全 [分数及其工作方式](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="9f394-143">Learn more about [Secure Score and how it works](../security/defender/microsoft-secure-score.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="9f394-144">操作类型和点</span><span class="sxs-lookup"><span data-stu-id="9f394-144">Action types and points</span></span>

<span data-ttu-id="9f394-145">合规性管理器跟踪两种类型的操作：</span><span class="sxs-lookup"><span data-stu-id="9f394-145">Compliance Manager tracks two types of actions:</span></span>

1. <span data-ttu-id="9f394-146">**您的改进操作**：组织管理的操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-146">**Your improvement actions**: actions that your organization manages.</span></span>
2. <span data-ttu-id="9f394-147">**Microsoft 操作**：Microsoft 管理的操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-147">**Microsoft actions**: actions that Microsoft manages.</span></span>

<span data-ttu-id="9f394-148">这两种类型的操作都有完成时计入总体分数的分数。</span><span class="sxs-lookup"><span data-stu-id="9f394-148">Both types of actions have points that count toward your overall score when completed.</span></span>

### <a name="technical-and-non-technical-actions"></a><span data-ttu-id="9f394-149">技术和非技术操作</span><span class="sxs-lookup"><span data-stu-id="9f394-149">Technical and non-technical actions</span></span>

<span data-ttu-id="9f394-150">操作按操作在本质上是技术操作还是非技术操作进行分组。</span><span class="sxs-lookup"><span data-stu-id="9f394-150">Actions are grouped by whether they are technical or non-technical in nature.</span></span> <span data-ttu-id="9f394-151">每项操作对评分的影响因类型不同而不同。</span><span class="sxs-lookup"><span data-stu-id="9f394-151">The scoring impact of each action differs by type.</span></span>

- <span data-ttu-id="9f394-152">**技术操作** 通过与解决方案技术交互实现 (例如，更改配置) 。</span><span class="sxs-lookup"><span data-stu-id="9f394-152">**Technical actions** are implemented by interacting with the technology of a solution (for example, changing a configuration).</span></span> <span data-ttu-id="9f394-153">技术操作点针对每个操作授予一次，无论它属于多少个组。</span><span class="sxs-lookup"><span data-stu-id="9f394-153">The points for technical actions are granted once per action, regardless of how many groups it belongs to.</span></span>

- <span data-ttu-id="9f394-154">**非技术操作** 由您的组织进行管理，并且以除使用解决方案技术外的其他方式实现。</span><span class="sxs-lookup"><span data-stu-id="9f394-154">**Non-technical actions** are managed by your organization and implemented in ways other than working with the technology of a solution.</span></span> <span data-ttu-id="9f394-155">有两种类型的非技术操作：**文档操作\*\*\*\*和操作操作**。</span><span class="sxs-lookup"><span data-stu-id="9f394-155">There are two types of non-technical actions: **documentation** and **operational**.</span></span> <span data-ttu-id="9f394-156">这些操作分数将应用于组级别的合规性分数。</span><span class="sxs-lookup"><span data-stu-id="9f394-156">The points for these actions are applied to your compliance score at a group level.</span></span> <span data-ttu-id="9f394-157">这意味着，如果某个操作存在于多个组中，则每次在一个组中实现该操作时，您都会收到该操作的点值。</span><span class="sxs-lookup"><span data-stu-id="9f394-157">This means that if an action exists in multiple groups, you will receive the action's point value each time you implement it within a group.</span></span>

<span data-ttu-id="9f394-158">**如何对技术和非技术操作进行评分的示例：**</span><span class="sxs-lookup"><span data-stu-id="9f394-158">**Example of how technical and non-technical actions are scored:**</span></span>

<span data-ttu-id="9f394-159">假设有一个技术操作，其值 3 分存在于 5 个组中，并且有一个非技术操作，其值 3 分存在于相同的 5 个组中。</span><span class="sxs-lookup"><span data-stu-id="9f394-159">Let's say you have a technical action worth 3 points that exists in 5 groups, and you have a non-technical action worth 3 points that exists in the same 5 groups.</span></span>

<span data-ttu-id="9f394-160">如果成功实施技术操作，则收到的总点数为 3。</span><span class="sxs-lookup"><span data-stu-id="9f394-160">If you successfully implement the technical action, the total number of points you receive is 3.</span></span> <span data-ttu-id="9f394-161">这是因为只需为租户实现一次操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-161">This is because you only need to implement the action once for your tenant.</span></span> <span data-ttu-id="9f394-162">技术操作的实施和测试状态将在该操作的所有实例中及其所属的每个组中显示相同。</span><span class="sxs-lookup"><span data-stu-id="9f394-162">The implementation and test status for the technical action will show the same in all instances of that action, in every group it belongs to.</span></span>

<span data-ttu-id="9f394-163">如果在 5 个组中分别成功实现非技术操作，则收到的总点数为 15。</span><span class="sxs-lookup"><span data-stu-id="9f394-163">If you successfully implement the non-technical action in each of the 5 groups, the total number of points you receive is 15.</span></span> <span data-ttu-id="9f394-164">这是因为您需要在每个组中实现操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-164">This is because you need to implement the action in each group.</span></span> <span data-ttu-id="9f394-165">非技术操作的实施和测试状态因各组单独实现而不同。</span><span class="sxs-lookup"><span data-stu-id="9f394-165">The implementation and test status for the non-technical action will differ across groups because the action is implemented separately within each of its groups.</span></span>

<span data-ttu-id="9f394-166">此评分逻辑旨在最准确地描述如何在组织中实施和测试操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-166">This scoring logic is designed to provide the most accurate accounting of how actions are implemented and tested in your organization.</span></span>

### <a name="how-score-values-are-determined"></a><span data-ttu-id="9f394-167">如何确定分数值</span><span class="sxs-lookup"><span data-stu-id="9f394-167">How score values are determined</span></span>
 
<span data-ttu-id="9f394-168">根据操作是必需还是随意，以及操作是预防型、检测型还是纠正型，为操作分配分数值。</span><span class="sxs-lookup"><span data-stu-id="9f394-168">Actions are assigned a score value based on whether they’re mandatory or discretionary, and whether they’re preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="9f394-169">强制和随意操作</span><span class="sxs-lookup"><span data-stu-id="9f394-169">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="9f394-170">**不能有意** 或无意地绕过强制操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-170">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="9f394-171">强制操作的示例是集中管理的密码策略，用于设置密码长度、复杂性和过期要求。</span><span class="sxs-lookup"><span data-stu-id="9f394-171">An example of a mandatory action is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="9f394-172">用户必须遵循这些要求来访问系统。</span><span class="sxs-lookup"><span data-stu-id="9f394-172">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="9f394-173">**随意操作** 依赖用户了解并遵守策略。</span><span class="sxs-lookup"><span data-stu-id="9f394-173">**Discretionary actions** rely upon users to understand and adhere to a policy.</span></span> <span data-ttu-id="9f394-174">例如，要求用户在离开计算机时锁定计算机的策略是一项随意操作，因为它依赖用户。</span><span class="sxs-lookup"><span data-stu-id="9f394-174">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="9f394-175">预防性、检测性以及纠正性操作</span><span class="sxs-lookup"><span data-stu-id="9f394-175">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="9f394-176">**预防性措施** 可应对特定风险。</span><span class="sxs-lookup"><span data-stu-id="9f394-176">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="9f394-177">例如，使用加密保护静态信息是抵御攻击和泄露的预防性措施。</span><span class="sxs-lookup"><span data-stu-id="9f394-177">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="9f394-178">职责分离是管理利益冲突和防范欺诈的预防性措施。</span><span class="sxs-lookup"><span data-stu-id="9f394-178">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="9f394-179">**检测操作** 主动监视系统，以识别代表风险的异常状况或行为，或可用于检测入侵或泄露的情况或行为。</span><span class="sxs-lookup"><span data-stu-id="9f394-179">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="9f394-180">示例包括系统访问审核和特权管理操作。</span><span class="sxs-lookup"><span data-stu-id="9f394-180">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="9f394-181">法规合规性审核是一种检测性操作，用于查找流程问题。</span><span class="sxs-lookup"><span data-stu-id="9f394-181">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="9f394-182">**纠正措施** 尝试将安全事件的负面影响降至最低，采取纠正措施以减少立即影响，并尽可能撤消损害。</span><span class="sxs-lookup"><span data-stu-id="9f394-182">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="9f394-183">隐私事件响应是一种纠正措施，可限制损坏，在泄露后将系统恢复为可操作状态。</span><span class="sxs-lookup"><span data-stu-id="9f394-183">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="9f394-184">每个操作在合规性管理器中都有一个分配的值，该值基于它所代表的风险：</span><span class="sxs-lookup"><span data-stu-id="9f394-184">Each action has an assigned value in Compliance Manager based on the risk it represents:</span></span>

|<span data-ttu-id="9f394-185">**类型**</span><span class="sxs-lookup"><span data-stu-id="9f394-185">**Type**</span></span>|<span data-ttu-id="9f394-186">**分配的分数**</span><span class="sxs-lookup"><span data-stu-id="9f394-186">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="9f394-187">预防性强制</span><span class="sxs-lookup"><span data-stu-id="9f394-187">Preventative mandatory</span></span> | <span data-ttu-id="9f394-188">27</span><span class="sxs-lookup"><span data-stu-id="9f394-188">27</span></span> |
| <span data-ttu-id="9f394-189">预防性随意</span><span class="sxs-lookup"><span data-stu-id="9f394-189">Preventative discretionary</span></span> | <span data-ttu-id="9f394-190">9 </span><span class="sxs-lookup"><span data-stu-id="9f394-190">9</span></span> |
| <span data-ttu-id="9f394-191">检测强制</span><span class="sxs-lookup"><span data-stu-id="9f394-191">Detective mandatory</span></span> | <span data-ttu-id="9f394-192">3</span><span class="sxs-lookup"><span data-stu-id="9f394-192">3</span></span> |
| <span data-ttu-id="9f394-193">检测随意</span><span class="sxs-lookup"><span data-stu-id="9f394-193">Detective discretionary</span></span> | <span data-ttu-id="9f394-194">1</span><span class="sxs-lookup"><span data-stu-id="9f394-194">1</span></span> |
| <span data-ttu-id="9f394-195">更正强制</span><span class="sxs-lookup"><span data-stu-id="9f394-195">Corrective mandatory</span></span> | <span data-ttu-id="9f394-196">3</span><span class="sxs-lookup"><span data-stu-id="9f394-196">3</span></span> |
| <span data-ttu-id="9f394-197">更正随意</span><span class="sxs-lookup"><span data-stu-id="9f394-197">Corrective discretionary</span></span> | <span data-ttu-id="9f394-198">1</span><span class="sxs-lookup"><span data-stu-id="9f394-198">1</span></span> |
  
<span data-ttu-id="9f394-199">![合规性管理器操作点值](../media/compliance-score-action-scoring.png "合规性管理器操作点值")</span><span class="sxs-lookup"><span data-stu-id="9f394-199">![Compliance Manager action point values](../media/compliance-score-action-scoring.png "Compliance Manager action point values")</span></span>