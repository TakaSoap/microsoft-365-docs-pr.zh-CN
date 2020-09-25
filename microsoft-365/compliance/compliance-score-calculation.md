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
description: 了解 Microsoft 合规性管理器如何根据为解决风险而采取的措施计算个性化分数，并提高合规性状态。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f1707e0117d0a61f572716f21d13a02821955401
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262265"
---
# <a name="compliance-score-calculation"></a><span data-ttu-id="5b801-103">合规性分数计算</span><span class="sxs-lookup"><span data-stu-id="5b801-103">Compliance score calculation</span></span>

<span data-ttu-id="5b801-104">**本文内容：** 了解合规性管理器如何为你的组织计算合规性分数。</span><span class="sxs-lookup"><span data-stu-id="5b801-104">**In this article:** Learn how Compliance Manager calculates a compliance score for your organization.</span></span> <span data-ttu-id="5b801-105">本文介绍如何 **解释你的成绩**、 **数据保护基准评估** 包括的内容、 **连续监控**以及 **管理和评分的不同类型的操作**的说明。</span><span class="sxs-lookup"><span data-stu-id="5b801-105">This article explains how to **interpret your score**, what the **Data Protection Baseline assessment** includes, **continuous monitoring**, and **how different types of actions are managed and scored**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b801-106">来自合规性管理器的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="5b801-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="5b801-107">根据您的法规环境评估和验证客户控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="5b801-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="5b801-108">这些服务受 [在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。</span><span class="sxs-lookup"><span data-stu-id="5b801-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="5b801-109">另请参阅 [适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="5b801-109">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-to-read-your-compliance-score"></a><span data-ttu-id="5b801-110">如何阅读合规性分数</span><span class="sxs-lookup"><span data-stu-id="5b801-110">How to read your compliance score</span></span>

<span data-ttu-id="5b801-111">合规性管理器仪表板将显示你的总体合规性分数。</span><span class="sxs-lookup"><span data-stu-id="5b801-111">The Compliance Manager dashboard displays your overall compliance score.</span></span> <span data-ttu-id="5b801-112">此分数用于衡量在控件中完成建议的改进操作的进度。</span><span class="sxs-lookup"><span data-stu-id="5b801-112">This score measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="5b801-113">你的分数可帮助你了解你当前的合规性状况。</span><span class="sxs-lookup"><span data-stu-id="5b801-113">Your score can help you understand your current compliance posture.</span></span> <span data-ttu-id="5b801-114">它还可帮助您根据其可能降低风险的可能性来确定操作优先级。</span><span class="sxs-lookup"><span data-stu-id="5b801-114">It can also help you prioritize actions based on their potential to reduce risk.</span></span>

<span data-ttu-id="5b801-115">分数值分配在三个级别：</span><span class="sxs-lookup"><span data-stu-id="5b801-115">A score value is assigned at three levels:</span></span>

1. <span data-ttu-id="5b801-116">**改进操作得分**：每项操作对你的分数有不同影响，具体取决于所涉及的潜在风险</span><span class="sxs-lookup"><span data-stu-id="5b801-116">**Improvement action score**: each action has a different impact on your score depending on the potential risk involved</span></span>

2. <span data-ttu-id="5b801-117">**控制分数**：此分数是通过在控件中完成改进操作达到的分数的总和。</span><span class="sxs-lookup"><span data-stu-id="5b801-117">**Control score**: this score is the sum of points earned by completing improvement actions within the control.</span></span> <span data-ttu-id="5b801-118">当控制同时满足以下两个条件时，此总和将全部应用于您的总体合规性分数：</span><span class="sxs-lookup"><span data-stu-id="5b801-118">This sum is applied in its entirety to your overall compliance score when the control meets both of the following conditions:</span></span>
    - <span data-ttu-id="5b801-119">**实现状态** 等于已 **实现** 或 **替代实现**，并且</span><span class="sxs-lookup"><span data-stu-id="5b801-119">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
    - <span data-ttu-id="5b801-120">**测试结果** 等于已 **通过**。</span><span class="sxs-lookup"><span data-stu-id="5b801-120">**Test Result** equals **Passed**.</span></span>

3. <span data-ttu-id="5b801-121">**评估成绩**：此分数是控制得分的总和。</span><span class="sxs-lookup"><span data-stu-id="5b801-121">**Assessment score**: this score is the sum of your control scores.</span></span> <span data-ttu-id="5b801-122">它使用 "操作分数" 进行计算。</span><span class="sxs-lookup"><span data-stu-id="5b801-122">It is calculated using action scores.</span></span> <span data-ttu-id="5b801-123">您的组织管理的每个 Microsoft 操作和每个改进操作都计算一次，而不考虑在控件中引用它的频率。</span><span class="sxs-lookup"><span data-stu-id="5b801-123">Each Microsoft action and each improvement action managed by your organization is counted once, regardless of how often it is referenced in a control.</span></span>

<span data-ttu-id="5b801-124">总体符合性分数是使用操作分数计算的，其中每个 Microsoft 操作计数一次，您管理的每个技术操作将计数一次，每个组管理的每个非技术操作将计入一次。</span><span class="sxs-lookup"><span data-stu-id="5b801-124">The overall compliance score is calculated using action scores, where each Microsoft action is counted once, each technical action you manage is counted once, and each non-technical action you manage is counted once per group.</span></span> <span data-ttu-id="5b801-125">此逻辑旨在提供最准确的会计，以了解如何在组织中实现和测试操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-125">This logic is designed to provide the most accurate accounting of how actions are implemented and tested in your organization.</span></span> <span data-ttu-id="5b801-126">你可能会注意到，这可能会导致你的总体合规性分数与评估分数的平均值不同。</span><span class="sxs-lookup"><span data-stu-id="5b801-126">You may notice that this can cause your overall compliance score to differ from the average of your assessment scores.</span></span> <span data-ttu-id="5b801-127">请阅读以下更多有关 [如何评分操作的](#action-types-and-points)信息。</span><span class="sxs-lookup"><span data-stu-id="5b801-127">Read more below about [how actions are scored](#action-types-and-points).</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="5b801-128">基于 Microsoft 365 数据保护基准的初始分数</span><span class="sxs-lookup"><span data-stu-id="5b801-128">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="5b801-129">合规性管理器为你提供了基于 Microsoft 365 数据保护基准的初始分数。</span><span class="sxs-lookup"><span data-stu-id="5b801-129">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="5b801-130">此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="5b801-130">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="5b801-131">此基线主要从 NIST CSF (美国国家标准 and 技术协会 Cybersecurity Framework) and ISO (国际标准化组织) 以及 FedRAMP (联邦风险和授权管理计划) 和 GDPR (常规数据保护法规的欧盟) 。</span><span class="sxs-lookup"><span data-stu-id="5b801-131">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="5b801-132">根据为所有组织提供的默认数据保护基准评估计算你的初始分数。</span><span class="sxs-lookup"><span data-stu-id="5b801-132">Your initial score is calculated according to the default Data Protection Baseline assessment provided to all organizations.</span></span> <span data-ttu-id="5b801-133">首次访问时，合规性管理器已从 Microsoft 365 解决方案中收集信号。</span><span class="sxs-lookup"><span data-stu-id="5b801-133">Upon your first visit, Compliance Manager is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="5b801-134">你将快速了解你的组织是如何相对于关键数据保护标准和管理法规执行的，并查看建议采取的改进措施。</span><span class="sxs-lookup"><span data-stu-id="5b801-134">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="5b801-135">由于每个组织都有特定的需求，因此合规性管理器依靠您来设置和管理评估，以帮助尽可能减少和缓解风险，使其尽可能最全面。</span><span class="sxs-lookup"><span data-stu-id="5b801-135">Because every organization has specific needs, Compliance Manager relies on you to set up and manage assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-manager-continuously-assesses-controls"></a><span data-ttu-id="5b801-136">合规性管理器如何持续评估控制措施</span><span class="sxs-lookup"><span data-stu-id="5b801-136">How Compliance Manager continuously assesses controls</span></span>

<span data-ttu-id="5b801-137">合规性管理器将自动扫描您的 Microsoft 365 环境，并检测系统设置，持续并自动更新您的技术动作状态。</span><span class="sxs-lookup"><span data-stu-id="5b801-137">Compliance Manager automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical action status.</span></span> <span data-ttu-id="5b801-138">Microsoft 安全分数是执行监控的基础引擎。</span><span class="sxs-lookup"><span data-stu-id="5b801-138">Microsoft Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="5b801-139">你的仪表板每24小时更新一次你的操作状态。</span><span class="sxs-lookup"><span data-stu-id="5b801-139">Your action status is updated on your dashboard every 24 hours.</span></span> <span data-ttu-id="5b801-140">一旦您遵循了实现控件的建议，您通常会看到在下一天更新控件状态。</span><span class="sxs-lookup"><span data-stu-id="5b801-140">Once you follow a recommendation to implement a control, you’ll typically see the control status updated the next day.</span></span>

<span data-ttu-id="5b801-141">例如，如果在 Azure AD 门户中启用了多重身份验证 (MFA) ，合规性管理器将检测到该设置并在控制访问解决方案详细信息中对其进行反映。</span><span class="sxs-lookup"><span data-stu-id="5b801-141">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Manager detects the setting and reflects it in the control access solution details.</span></span> <span data-ttu-id="5b801-142">相反，如果未启用 MFA，合规性管理器会将其标记为建议采取的操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-142">Conversely, if you didn’t turn on MFA, Compliance Manager flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="5b801-143">了解有关 [安全分数及其工作方式](../security/mtp/microsoft-secure-score-new.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b801-143">Learn more about [Secure Score and how it works](../security/mtp/microsoft-secure-score-new.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="5b801-144">操作类型和点</span><span class="sxs-lookup"><span data-stu-id="5b801-144">Action types and points</span></span>

<span data-ttu-id="5b801-145">合规性管理器跟踪两种类型的操作：</span><span class="sxs-lookup"><span data-stu-id="5b801-145">Compliance Manager tracks two types of actions:</span></span>

1. <span data-ttu-id="5b801-146">**您的改进操作**：您的组织管理的操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-146">**Your improvement actions**: actions that your organization manages.</span></span>
2. <span data-ttu-id="5b801-147">**Microsoft 操作**： microsoft 管理的操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-147">**Microsoft actions**: actions that Microsoft manages.</span></span>

<span data-ttu-id="5b801-148">两种类型的操作都具有在完成时计入整体得分的点。</span><span class="sxs-lookup"><span data-stu-id="5b801-148">Both types of actions have points that count toward your overall score when completed.</span></span>

### <a name="technical-and-non-technical-actions"></a><span data-ttu-id="5b801-149">技术和非技术操作</span><span class="sxs-lookup"><span data-stu-id="5b801-149">Technical and non-technical actions</span></span>

<span data-ttu-id="5b801-150">操作的分组依据是技术本身还是非技术性的。</span><span class="sxs-lookup"><span data-stu-id="5b801-150">Actions are grouped by whether they are technical or non-technical in nature.</span></span> <span data-ttu-id="5b801-151">每个操作对分数的影响因类型而异。</span><span class="sxs-lookup"><span data-stu-id="5b801-151">The scoring impact of each action differs by type.</span></span>

- <span data-ttu-id="5b801-152">通过与解决方案中的技术进行交互来实现**技术操作** (例如，更改配置) 。</span><span class="sxs-lookup"><span data-stu-id="5b801-152">**Technical actions** are implemented by interacting with the technology of a solution (for example, changing a configuration).</span></span> <span data-ttu-id="5b801-153">每个操作只授予一次技术操作点，而不管它属于多少个组。</span><span class="sxs-lookup"><span data-stu-id="5b801-153">The points for technical actions are granted once per action, regardless of how many groups it belongs to.</span></span>

- <span data-ttu-id="5b801-154">**非技术操作** 由您的组织管理，并采用与使用解决方案的技术不同的方式实施。</span><span class="sxs-lookup"><span data-stu-id="5b801-154">**Non-technical actions** are managed by your organization and implemented in ways other than working with the technology of a solution.</span></span> <span data-ttu-id="5b801-155">有两种类型的非技术操作： **文档** 和 **操作**。</span><span class="sxs-lookup"><span data-stu-id="5b801-155">There are two types of non-technical actions: **documentation** and **operational**.</span></span> <span data-ttu-id="5b801-156">这些操作的分数适用于组级别的合规性分数。</span><span class="sxs-lookup"><span data-stu-id="5b801-156">The points for these actions are applied to your compliance score at a group level.</span></span> <span data-ttu-id="5b801-157">这意味着，如果一个操作存在于多个组中，则每次在组中实现此操作时，都会收到操作的磅值。</span><span class="sxs-lookup"><span data-stu-id="5b801-157">This means that if an action exists in multiple groups, you will receive the action's point value each time you implement it within a group.</span></span>

<span data-ttu-id="5b801-158">**如何评分的技术和非技术性操作的示例：**</span><span class="sxs-lookup"><span data-stu-id="5b801-158">**Example of how technical and non-technical actions are scored:**</span></span>

<span data-ttu-id="5b801-159">假设您有一个技术行动值得5个组中存在3个棋位，并且您有一个非技术性操作值得在同一5个组中存在3个点。</span><span class="sxs-lookup"><span data-stu-id="5b801-159">Let's say you have a technical action worth 3 points that exists in 5 groups, and you have a non-technical action worth 3 points that exists in the same 5 groups.</span></span>

<span data-ttu-id="5b801-160">如果您成功实现技术操作，则您收到的总点数为3。</span><span class="sxs-lookup"><span data-stu-id="5b801-160">If you successfully implement the technical action, the total number of points you receive is 3.</span></span> <span data-ttu-id="5b801-161">这是因为您只需要为您的租户实现一次此操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-161">This is because you only need to implement the action once for your tenant.</span></span> <span data-ttu-id="5b801-162">技术操作的实现和测试状态在该操作所属的每个组中的所有实例中将显示相同。</span><span class="sxs-lookup"><span data-stu-id="5b801-162">The implementation and test status for the technical action will show the same in all instances of that action, in every group it belongs to.</span></span>

<span data-ttu-id="5b801-163">如果您在5个组中的每个组中都成功实现了非技术性操作，则您收到的总点数为15。</span><span class="sxs-lookup"><span data-stu-id="5b801-163">If you successfully implement the non-technical action in each of the 5 groups, the total number of points you receive is 15.</span></span> <span data-ttu-id="5b801-164">这是因为您需要在每个组中实施操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-164">This is because you need to implement the action in each group.</span></span> <span data-ttu-id="5b801-165">非技术性操作的实现和测试状态因组而异，因为该操作是在其每个组中单独实现的。</span><span class="sxs-lookup"><span data-stu-id="5b801-165">The implementation and test status for the non-technical action will differ across groups because the action is implemented separately within each of its groups.</span></span>

<span data-ttu-id="5b801-166">此评分逻辑旨在提供最准确的会计，以了解如何在组织中实现和测试操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-166">This scoring logic is designed to provide the most accurate accounting of how actions are implemented and tested in your organization.</span></span>

### <a name="how-score-values-are-determined"></a><span data-ttu-id="5b801-167">分数值的确定方式</span><span class="sxs-lookup"><span data-stu-id="5b801-167">How score values are determined</span></span>
 
<span data-ttu-id="5b801-168">根据操作是强制还是自由，以及是否为预防、侦探或纠正措施，为操作分配分数值。</span><span class="sxs-lookup"><span data-stu-id="5b801-168">Actions are assigned a score value based on whether they’re mandatory or discretionary, and whether they’re preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="5b801-169">强制和自由操作</span><span class="sxs-lookup"><span data-stu-id="5b801-169">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="5b801-170">无法绕过**强制操作**，无论是有意的还是意外的。</span><span class="sxs-lookup"><span data-stu-id="5b801-170">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="5b801-171">强制操作的一个示例是集中管理的密码策略，用于设置密码长度、复杂性和过期的要求。</span><span class="sxs-lookup"><span data-stu-id="5b801-171">An example of a mandatory action is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="5b801-172">用户必须遵循以下要求才能访问系统。</span><span class="sxs-lookup"><span data-stu-id="5b801-172">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="5b801-173">**任意操作** 取决于用户了解并遵守策略。</span><span class="sxs-lookup"><span data-stu-id="5b801-173">**Discretionary actions** rely upon users to understand and adhere to a policy.</span></span> <span data-ttu-id="5b801-174">例如，要求用户在离开它时锁定其计算机的策略是一个随意的操作，因为它依赖于用户。</span><span class="sxs-lookup"><span data-stu-id="5b801-174">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="5b801-175">预防性、侦探和纠正措施</span><span class="sxs-lookup"><span data-stu-id="5b801-175">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="5b801-176">**预防措施** 解决特定风险。</span><span class="sxs-lookup"><span data-stu-id="5b801-176">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="5b801-177">例如，使用加密保护静态信息是预防攻击和泄露的预防措施。</span><span class="sxs-lookup"><span data-stu-id="5b801-177">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="5b801-178">分离职责是一种预防措施，用于管理利益冲突并防范欺诈行为。</span><span class="sxs-lookup"><span data-stu-id="5b801-178">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="5b801-179">**侦探操作** 主动监视系统，以确定存在不稳定的条件或行为，以确定风险或可用于检测入侵或泄露的行为。</span><span class="sxs-lookup"><span data-stu-id="5b801-179">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="5b801-180">示例包括系统访问审核和特权管理操作。</span><span class="sxs-lookup"><span data-stu-id="5b801-180">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="5b801-181">法规遵从性审核是用于查找过程问题的侦探操作的一种。</span><span class="sxs-lookup"><span data-stu-id="5b801-181">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="5b801-182">**纠正操作** 尝试将安全事件的负面影响降至最低，采取纠正措施以降低即时效果，并在可能的情况下反转损坏。</span><span class="sxs-lookup"><span data-stu-id="5b801-182">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="5b801-183">隐私事件响应是一种纠正措施，用于将损坏和还原系统限制为受到破坏后的操作状态。</span><span class="sxs-lookup"><span data-stu-id="5b801-183">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="5b801-184">每个操作都在合规性管理器中分配了基于其表示的风险的值：</span><span class="sxs-lookup"><span data-stu-id="5b801-184">Each action has an assigned value in Compliance Manager based on the risk it represents:</span></span>

|<span data-ttu-id="5b801-185">**Type**</span><span class="sxs-lookup"><span data-stu-id="5b801-185">**Type**</span></span>|<span data-ttu-id="5b801-186">**分配分数**</span><span class="sxs-lookup"><span data-stu-id="5b801-186">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5b801-187">预防性强制</span><span class="sxs-lookup"><span data-stu-id="5b801-187">Preventative mandatory</span></span> | <span data-ttu-id="5b801-188">27</span><span class="sxs-lookup"><span data-stu-id="5b801-188">27</span></span> |
| <span data-ttu-id="5b801-189">预防自由</span><span class="sxs-lookup"><span data-stu-id="5b801-189">Preventative discretionary</span></span> | <span data-ttu-id="5b801-190">9 </span><span class="sxs-lookup"><span data-stu-id="5b801-190">9</span></span> |
| <span data-ttu-id="5b801-191">侦探必备</span><span class="sxs-lookup"><span data-stu-id="5b801-191">Detective mandatory</span></span> | <span data-ttu-id="5b801-192">第三章</span><span class="sxs-lookup"><span data-stu-id="5b801-192">3</span></span> |
| <span data-ttu-id="5b801-193">侦探自由</span><span class="sxs-lookup"><span data-stu-id="5b801-193">Detective discretionary</span></span> | <span data-ttu-id="5b801-194">1</span><span class="sxs-lookup"><span data-stu-id="5b801-194">1</span></span> |
| <span data-ttu-id="5b801-195">强制纠正</span><span class="sxs-lookup"><span data-stu-id="5b801-195">Corrective mandatory</span></span> | <span data-ttu-id="5b801-196">第三章</span><span class="sxs-lookup"><span data-stu-id="5b801-196">3</span></span> |
| <span data-ttu-id="5b801-197">随机纠正</span><span class="sxs-lookup"><span data-stu-id="5b801-197">Corrective discretionary</span></span> | <span data-ttu-id="5b801-198">1</span><span class="sxs-lookup"><span data-stu-id="5b801-198">1</span></span> |
  
<span data-ttu-id="5b801-199">![合规性管理器操作点值](../media/compliance-score-action-scoring.png "合规性管理器操作点值")</span><span class="sxs-lookup"><span data-stu-id="5b801-199">![Compliance Manager action point values](../media/compliance-score-action-scoring.png "Compliance Manager action point values")</span></span>