---
title: 合规性分数计算
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
ms.openlocfilehash: e3bb9bc2d9d833eea8c5a9e4a29334d9777aebac
ms.sourcegitcommit: 544b10cc3abe04a47438085d51c4250c9238f76f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "38685062"
---
# <a name="microsoft-compliance-score-calculation-preview"></a><span data-ttu-id="3fdb5-103">Microsoft 合规性分数计算（预览）</span><span class="sxs-lookup"><span data-stu-id="3fdb5-103">Microsoft Compliance Score calculation (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fdb5-104">合规性分数不表示对任何特定标准或法规的组织合规性的绝对衡量。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-104">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="3fdb5-105">它表示您已采用的控制程度，可降低个人数据和个人隐私的风险。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-105">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="3fdb5-106">不应将合规性分数和合规性管理器中的建议解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-106">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="3fdb5-107">此服务目前处于预览阶段，并受[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-107">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="overview"></a><span data-ttu-id="3fdb5-108">概述</span><span class="sxs-lookup"><span data-stu-id="3fdb5-108">Overview</span></span>

<span data-ttu-id="3fdb5-109">合规性分数仪表板显示分数，用于衡量在控件中完成改进操作的进度。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="3fdb5-110">完成操作时，会对点进行累算。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-110">Your points accrue when you complete actions.</span></span>

<span data-ttu-id="3fdb5-111">根据 Microsoft 管理的操作和客户管理的操作的完成情况计算分数。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-111">Your score is calculated based on the completion of Microsoft-managed actions and customer-managed actions.</span></span> <span data-ttu-id="3fdb5-112">每项操作对你的分数有不同的影响，具体取决于所涉及的潜在风险，因此分数可帮助确定重点关注的操作以改进您的总体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-112">Each action has a different impact on your score, depending on the potential risks involved, so the score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="3fdb5-113">为该控件显示的符合性分数值将*全部*应用于通过通过/失败的总分。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-113">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="3fdb5-114">该控件已实现并通过后续评估测试，否则不会执行。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-114">Either the control is implemented and passes the subsequent assessment test or it does not.</span></span> <span data-ttu-id="3fdb5-115">当控件具有以下条件时，为合规性分数添加分配的点：</span><span class="sxs-lookup"><span data-stu-id="3fdb5-115">Assigned points are added to Compliance Score when the control has:</span></span>

- <span data-ttu-id="3fdb5-116">**实现状态**等于已**实现**或**替代实施**，以及</span><span class="sxs-lookup"><span data-stu-id="3fdb5-116">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="3fdb5-117">**测试结果**等于已**通过**。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-117">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="3fdb5-118">通过采取改进操作达到的分数总和是控制得分。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-118">The sum of points earned by taking improvement actions is the control score.</span></span> <span data-ttu-id="3fdb5-119">控制分数的总和是评估分数。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-119">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="3fdb5-120">评估分数总和是您的总体合规性分数</span><span class="sxs-lookup"><span data-stu-id="3fdb5-120">The sum of your assessment scores is your overall compliance score</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="3fdb5-121">基于 Microsoft 365 数据保护基准的初始分数</span><span class="sxs-lookup"><span data-stu-id="3fdb5-121">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="3fdb5-122">合规性分数为您提供了基于 Microsoft 365 数据保护基准的现成分数，这是一组包括用于数据保护和常规数据保护的关键法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-122">Compliance Score gives you an out-of-the-box score based on the Microsoft 365 data protection baseline, which is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="3fdb5-123">此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）和 FedRAMP （联邦风险和授权管理）中绘制元素程序）和 GDPR （欧盟的常规数据保护法规）。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="3fdb5-124">合规性分数如何持续评估控制措施</span><span class="sxs-lookup"><span data-stu-id="3fdb5-124">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="3fdb5-125">合规性分数将自动通过 Microsoft 365 环境扫描并检测系统设置，并持续并自动更新你的技术控制状态。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-125">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="3fdb5-126">例如，如果在 Azure AD 门户中启用了多重身份验证（MFA），合规性分数将检测设置，并在控制访问解决方案详细信息中反映出该设置。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-126">For example, if you turned on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="3fdb5-127">相反，如果未启用 MFA，合规性分数标志为建议采取的操作。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-127">Conversely, if you didn’t turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="3fdb5-128">合规性分数每24小时更新一次控件状态。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-128">Compliance Score updates your control status every 24 hours.</span></span> <span data-ttu-id="3fdb5-129">一旦您遵循了实现控件的建议，您将会看到在下一天更新控件状态。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-129">Once you follow a recommendation to implement a control, you will see the control status updated the next day.</span></span>

<span data-ttu-id="3fdb5-130">在公共预览过程中，连续评估适用于部分控件，但并非全部。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-130">During public preview, continuous assessment is available to a portion controls, but not all.</span></span>
  
## <a name="control-types-and-points"></a><span data-ttu-id="3fdb5-131">控件类型和点</span><span class="sxs-lookup"><span data-stu-id="3fdb5-131">Control types and points</span></span>

<span data-ttu-id="3fdb5-132">合规性分数跟踪两种类型的控件： Microsoft 管理的控件和客户管理的控件，其中每个控件都有对整体得分的积分：</span><span class="sxs-lookup"><span data-stu-id="3fdb5-132">Compliance Score tracks two types of controls—Microsoft-managed and customer-managed—each of which have points that contribute to your overall score:</span></span>

1. <span data-ttu-id="3fdb5-133">根据您的组织管理的控件，**客户管理的积分**将有助于满足您的合规性分数。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-133">**Customer-managed points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="3fdb5-134">根据 Microsoft 作为云服务提供商托管的控件， **Microsoft 管理点**将对您的合规性分数构成贡献。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-134">**Microsoft-managed points** contribute to your compliance score based on controls managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="3fdb5-135">根据控件是必需的还是任意的，以及是否为预防、侦探或纠正措施（如下所述），会为控件分配一个分数值。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-135">Controls are assigned a score value based on whether they are mandatory or discretionary, and whether they are preventative, detective, or corrective—as described below.</span></span>

### <a name="mandatory-and-discretionary-controls"></a><span data-ttu-id="3fdb5-136">强制和任意控件</span><span class="sxs-lookup"><span data-stu-id="3fdb5-136">Mandatory and discretionary controls</span></span>

 - <span data-ttu-id="3fdb5-137">**强制控制**措施是不能有意地或无意中回避的操作。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-137">**Mandatory controls** are actions that cannot be bypassed either intentionally or accidentally.</span></span> <span data-ttu-id="3fdb5-138">例如集中管理的密码策略，用于设置密码长度、复杂性和过期的要求。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-138">An example is a centrally-managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="3fdb5-139">用户必须遵守这些要求才能访问系统。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-139">Users must comply with these requirements to access the system.</span></span>
  
 - <span data-ttu-id="3fdb5-140">**任意控件**依赖于用户了解策略并相应地执行操作。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-140">**Discretionary controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="3fdb5-141">例如，要求用户在其离开时锁定其计算机的策略是自由控制，因为它依赖于用户。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-141">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-controls"></a><span data-ttu-id="3fdb5-142">预防性、侦探和纠正控制措施</span><span class="sxs-lookup"><span data-stu-id="3fdb5-142">Preventative, detective, and corrective controls</span></span>
  
 - <span data-ttu-id="3fdb5-143">**预防控制措施**解决特定风险。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-143">**Preventative controls** address specific risks.</span></span> <span data-ttu-id="3fdb5-144">例如，使用加密保护静态信息是抵御攻击和泄露的预防控制措施。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-144">For example, protecting information at rest using encryption is a preventative control against attacks and breaches.</span></span> <span data-ttu-id="3fdb5-145">分离职责是一种预防性控制，用于管理利益冲突并防范欺诈行为。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-145">Separation of duties is a preventative control to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="3fdb5-146">**侦探控件**主动监视系统，以找出表示风险或可用于检测入侵情况或确定是否发生了入侵的不规则条件或行为。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-146">**Detective controls** actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach occurs.</span></span> <span data-ttu-id="3fdb5-147">系统访问审核和特权管理操作审核是侦探监视控件的类型。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-147">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="3fdb5-148">法规遵从性审核是一种用于查找进程问题的侦探控件。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-148">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
- <span data-ttu-id="3fdb5-149">**纠正控制**尝试将安全事件的负面影响降至最低，采取纠正措施以降低即时效果，并在可能的情况下反转损坏。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-149">**Corrective controls** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="3fdb5-150">"隐私事件响应" 是一种纠正控制，用于将损坏和还原系统限制为受到破坏后的操作状态。</span><span class="sxs-lookup"><span data-stu-id="3fdb5-150">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="3fdb5-151">根据其表示的风险，每个控件都在合规性分数中分配了一个值：</span><span class="sxs-lookup"><span data-stu-id="3fdb5-151">Each control has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="3fdb5-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="3fdb5-152">**Type**</span></span>|<span data-ttu-id="3fdb5-153">**分配分数**</span><span class="sxs-lookup"><span data-stu-id="3fdb5-153">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="3fdb5-154">预防性强制</span><span class="sxs-lookup"><span data-stu-id="3fdb5-154">Preventative mandatory</span></span> | <span data-ttu-id="3fdb5-155">27</span><span class="sxs-lookup"><span data-stu-id="3fdb5-155">27</span></span> |
| <span data-ttu-id="3fdb5-156">预防自由</span><span class="sxs-lookup"><span data-stu-id="3fdb5-156">Preventative discretionary</span></span> | <span data-ttu-id="3fdb5-157">第</span><span class="sxs-lookup"><span data-stu-id="3fdb5-157">9</span></span> |
| <span data-ttu-id="3fdb5-158">侦探必备</span><span class="sxs-lookup"><span data-stu-id="3fdb5-158">Detective mandatory</span></span> | <span data-ttu-id="3fdb5-159">第三章</span><span class="sxs-lookup"><span data-stu-id="3fdb5-159">3</span></span> |
| <span data-ttu-id="3fdb5-160">侦探自由</span><span class="sxs-lookup"><span data-stu-id="3fdb5-160">Detective discretionary</span></span> | <span data-ttu-id="3fdb5-161">1</span><span class="sxs-lookup"><span data-stu-id="3fdb5-161">1</span></span> |
| <span data-ttu-id="3fdb5-162">强制纠正</span><span class="sxs-lookup"><span data-stu-id="3fdb5-162">Corrective mandatory</span></span> | <span data-ttu-id="3fdb5-163">第三章</span><span class="sxs-lookup"><span data-stu-id="3fdb5-163">3</span></span> |
| <span data-ttu-id="3fdb5-164">随机纠正</span><span class="sxs-lookup"><span data-stu-id="3fdb5-164">Corrective discretionary</span></span> | <span data-ttu-id="3fdb5-165">1</span><span class="sxs-lookup"><span data-stu-id="3fdb5-165">1</span></span> |
  