---
title: Microsoft 合规性分数（预览）计算
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
description: 了解 Microsoft 合规性分数如何根据为解决风险而采取的措施计算个性化分数，并提高您的合规性状况。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024672"
---
# <a name="compliance-score-preview-calculation"></a><span data-ttu-id="19756-103">合规性分数（预览）计算</span><span class="sxs-lookup"><span data-stu-id="19756-103">Compliance Score (preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19756-104">合规性分数和合规性管理器中提供的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="19756-104">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="19756-105">根据您的法规环境评估和验证客户控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="19756-105">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="19756-106">这些服务当前处于预览阶段，并遵循[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件。</span><span class="sxs-lookup"><span data-stu-id="19756-106">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="19756-107">另请参阅[适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="19756-107">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-compliance-score-works"></a><span data-ttu-id="19756-108">合规性分数的工作原理</span><span class="sxs-lookup"><span data-stu-id="19756-108">How Compliance Score works</span></span>

<span data-ttu-id="19756-109">合规性分数仪表板显示分数，用于衡量在控件中完成改进操作的进度。</span><span class="sxs-lookup"><span data-stu-id="19756-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="19756-110">每项操作对你的分数有不同的影响，具体取决于所涉及的潜在风险。</span><span class="sxs-lookup"><span data-stu-id="19756-110">Each action has a different impact on your score, depending on the potential risks involved.</span></span> <span data-ttu-id="19756-111">你的分数可帮助优先考虑要关注的操作，以改进你的总体合规性状况。</span><span class="sxs-lookup"><span data-stu-id="19756-111">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="19756-112">为该控件显示的符合性分数值将*全部*应用于通过通过/失败的总分。</span><span class="sxs-lookup"><span data-stu-id="19756-112">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="19756-113">该控件已实现并传递后续评估测试，否则不会。</span><span class="sxs-lookup"><span data-stu-id="19756-113">Either the control is implemented and passes the subsequent assessment test, or it doesn't.</span></span> 

<span data-ttu-id="19756-114">当控件具有以下条件时，将其添加到符合性分数：</span><span class="sxs-lookup"><span data-stu-id="19756-114">Points are added to your compliance score when the control has:</span></span>

- <span data-ttu-id="19756-115">**实现状态**等于已**实现**或**替代实现**，并且</span><span class="sxs-lookup"><span data-stu-id="19756-115">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
- <span data-ttu-id="19756-116">**测试结果**等于已**通过**。</span><span class="sxs-lookup"><span data-stu-id="19756-116">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="19756-117">控制分数是通过采取改进操作获得的分数总和。</span><span class="sxs-lookup"><span data-stu-id="19756-117">A control score is the sum of points earned by taking improvement actions.</span></span> <span data-ttu-id="19756-118">控制分数的总和是评估分数。</span><span class="sxs-lookup"><span data-stu-id="19756-118">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="19756-119">**评估分数总和是您的总体合规性分数。**</span><span class="sxs-lookup"><span data-stu-id="19756-119">**The sum of your assessment scores is your overall compliance score.**</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="19756-120">基于 Microsoft 365 数据保护基准的初始分数</span><span class="sxs-lookup"><span data-stu-id="19756-120">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="19756-121">合规性分数为你提供了基于 Microsoft 365 数据保护基准的初始分数。</span><span class="sxs-lookup"><span data-stu-id="19756-121">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="19756-122">此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="19756-122">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="19756-123">此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）以及 FedRAMP （联邦风险和授权管理计划）和 GDPR （欧盟的常规数据保护法规）中提取元素。</span><span class="sxs-lookup"><span data-stu-id="19756-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="19756-124">数据保护基准评估（默认情况下为所有组织提供）用于在配置任何其他评估之前计算您的初始分数。</span><span class="sxs-lookup"><span data-stu-id="19756-124">The data protection baseline assessment (provided by default to all organizations) is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="19756-125">首次访问时，合规性分数已从 Microsoft 365 解决方案中收集信号。</span><span class="sxs-lookup"><span data-stu-id="19756-125">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="19756-126">你将快速了解你的组织是如何相对于关键数据保护标准和管理法规执行的，并查看建议采取的改进措施。</span><span class="sxs-lookup"><span data-stu-id="19756-126">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="19756-127">由于每个组织都有特定的需求，因此合规性分数取决于您设置和管理您自己的评估以帮助尽可能地减少和缓解风险。</span><span class="sxs-lookup"><span data-stu-id="19756-127">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="19756-128">合规性分数如何持续评估控制措施</span><span class="sxs-lookup"><span data-stu-id="19756-128">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="19756-129">合规性分数将自动通过 Microsoft 365 环境扫描并检测系统设置，并持续并自动更新你的技术控制状态。</span><span class="sxs-lookup"><span data-stu-id="19756-129">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="19756-130">安全分数是执行监控的基础引擎。</span><span class="sxs-lookup"><span data-stu-id="19756-130">Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="19756-131">你的合规性分数仪表板每24小时更新一次你的控制状态。</span><span class="sxs-lookup"><span data-stu-id="19756-131">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="19756-132">一旦您遵循了实现控件的建议，您将看到在下一天更新控件状态。</span><span class="sxs-lookup"><span data-stu-id="19756-132">Once you follow a recommendation to implement a control, you'll see the control status updated the next day.</span></span>

<span data-ttu-id="19756-133">例如，如果在 Azure AD 门户中打开多重身份验证（MFA），合规性分数将检测设置，并在控制访问解决方案详细信息中反映该设置。</span><span class="sxs-lookup"><span data-stu-id="19756-133">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="19756-134">相反，如果未启用 MFA，合规性分数标志为建议采取的操作。</span><span class="sxs-lookup"><span data-stu-id="19756-134">Conversely, if you didn't turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="19756-135">在公共预览过程中，连续评估适用于部分控件，但并非全部。</span><span class="sxs-lookup"><span data-stu-id="19756-135">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="19756-136">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="19756-136">Learn more</span></span>
<span data-ttu-id="19756-137">[阅读有关安全分数及其工作方式的信息](../security/mtp/microsoft-secure-score-new.md)。</span><span class="sxs-lookup"><span data-stu-id="19756-137">[Read about Secure Score and how it works](../security/mtp/microsoft-secure-score-new.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="19756-138">操作类型和点</span><span class="sxs-lookup"><span data-stu-id="19756-138">Action types and points</span></span>

<span data-ttu-id="19756-139">合规性分数跟踪两种类型的操作：您管理的操作以及 Microsoft 管理的操作。</span><span class="sxs-lookup"><span data-stu-id="19756-139">Compliance Score tracks two types of actions: actions you manage, and actions Microsoft manages.</span></span> <span data-ttu-id="19756-140">完成后，这两种类型的操作都将计入总得分的点：</span><span class="sxs-lookup"><span data-stu-id="19756-140">Both types of actions have points that count toward your overall score when completed:</span></span>

1. <span data-ttu-id="19756-141">**你的积分**根据你的组织管理的控件来贡献合规性分数。</span><span class="sxs-lookup"><span data-stu-id="19756-141">**Your points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="19756-142">**Microsoft 托管点**根据 Microsoft 作为云服务提供商管理的操作，为你的合规性分数提供贡献。</span><span class="sxs-lookup"><span data-stu-id="19756-142">**Microsoft managed points** contribute to your compliance score based on actions managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="19756-143">根据操作是强制还是自由，以及是否为预防、侦探或纠正措施，为操作分配分数值。</span><span class="sxs-lookup"><span data-stu-id="19756-143">Actions are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="19756-144">强制和自由操作</span><span class="sxs-lookup"><span data-stu-id="19756-144">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="19756-145">无法绕过**强制操作**，无论是有意的还是意外的。</span><span class="sxs-lookup"><span data-stu-id="19756-145">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="19756-146">例如，集中管理的密码策略，设置密码长度、复杂性和过期的要求。</span><span class="sxs-lookup"><span data-stu-id="19756-146">An example is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="19756-147">用户必须遵循以下要求才能访问系统。</span><span class="sxs-lookup"><span data-stu-id="19756-147">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="19756-148">**任意操作**取决于用户了解策略并相应地执行操作。</span><span class="sxs-lookup"><span data-stu-id="19756-148">**Discretionary actions** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="19756-149">例如，要求用户在离开它时锁定其计算机的策略是一个随意的操作，因为它依赖于用户。</span><span class="sxs-lookup"><span data-stu-id="19756-149">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="19756-150">预防性、侦探和纠正措施</span><span class="sxs-lookup"><span data-stu-id="19756-150">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="19756-151">**预防措施**解决特定风险。</span><span class="sxs-lookup"><span data-stu-id="19756-151">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="19756-152">例如，使用加密保护静态信息是预防攻击和泄露的预防措施。</span><span class="sxs-lookup"><span data-stu-id="19756-152">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="19756-153">分离职责是一种预防措施，用于管理利益冲突并防范欺诈行为。</span><span class="sxs-lookup"><span data-stu-id="19756-153">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="19756-154">**侦探操作**主动监视系统，以确定存在不稳定的条件或行为，以确定风险或可用于检测入侵或泄露的行为。</span><span class="sxs-lookup"><span data-stu-id="19756-154">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="19756-155">示例包括系统访问审核和特权管理操作。</span><span class="sxs-lookup"><span data-stu-id="19756-155">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="19756-156">法规遵从性审核是用于查找过程问题的侦探操作的一种。</span><span class="sxs-lookup"><span data-stu-id="19756-156">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="19756-157">**纠正操作**尝试将安全事件的负面影响降至最低，采取纠正措施以降低即时效果，并在可能的情况下反转损坏。</span><span class="sxs-lookup"><span data-stu-id="19756-157">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="19756-158">隐私事件响应是一种纠正措施，用于将损坏和还原系统限制为受到破坏后的操作状态。</span><span class="sxs-lookup"><span data-stu-id="19756-158">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="19756-159">每个操作在符合性分数中分配的值基于它表示的风险：</span><span class="sxs-lookup"><span data-stu-id="19756-159">Each action has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="19756-160">**类型**</span><span class="sxs-lookup"><span data-stu-id="19756-160">**Type**</span></span>|<span data-ttu-id="19756-161">**分配分数**</span><span class="sxs-lookup"><span data-stu-id="19756-161">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="19756-162">预防性强制</span><span class="sxs-lookup"><span data-stu-id="19756-162">Preventative mandatory</span></span> | <span data-ttu-id="19756-163">27</span><span class="sxs-lookup"><span data-stu-id="19756-163">27</span></span> |
| <span data-ttu-id="19756-164">预防自由</span><span class="sxs-lookup"><span data-stu-id="19756-164">Preventative discretionary</span></span> | <span data-ttu-id="19756-165">9 </span><span class="sxs-lookup"><span data-stu-id="19756-165">9</span></span> |
| <span data-ttu-id="19756-166">侦探必备</span><span class="sxs-lookup"><span data-stu-id="19756-166">Detective mandatory</span></span> | <span data-ttu-id="19756-167">3 </span><span class="sxs-lookup"><span data-stu-id="19756-167">3</span></span> |
| <span data-ttu-id="19756-168">侦探自由</span><span class="sxs-lookup"><span data-stu-id="19756-168">Detective discretionary</span></span> | <span data-ttu-id="19756-169">1 </span><span class="sxs-lookup"><span data-stu-id="19756-169">1</span></span> |
| <span data-ttu-id="19756-170">强制纠正</span><span class="sxs-lookup"><span data-stu-id="19756-170">Corrective mandatory</span></span> | <span data-ttu-id="19756-171">3 </span><span class="sxs-lookup"><span data-stu-id="19756-171">3</span></span> |
| <span data-ttu-id="19756-172">随机纠正</span><span class="sxs-lookup"><span data-stu-id="19756-172">Corrective discretionary</span></span> | <span data-ttu-id="19756-173">1 </span><span class="sxs-lookup"><span data-stu-id="19756-173">1</span></span> |
  
<span data-ttu-id="19756-174">![合规性分数控制点值](../media/compliance-score-controls-scoring.png "合规性分数控制点值")</span><span class="sxs-lookup"><span data-stu-id="19756-174">![Compliance Score controls point values](../media/compliance-score-controls-scoring.png "Compliance Score controls point values")</span></span>