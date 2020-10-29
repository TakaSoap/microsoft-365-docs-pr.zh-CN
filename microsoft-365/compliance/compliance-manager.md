---
title: Microsoft 合规性管理器
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器可帮助组织简化和自动化风险评估，并建议用于帮助解决风险的建议措施。
ms.openlocfilehash: d7136368a1c9726d1a77a0c99e717b98e1920242
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791799"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="6499d-103">Microsoft 合规性管理器</span><span class="sxs-lookup"><span data-stu-id="6499d-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="6499d-104">**本文内容：** 了解什么是合规性管理器、它如何帮助简化合规性并降低风险以及关键组件。</span><span class="sxs-lookup"><span data-stu-id="6499d-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="6499d-105">新增功能：合规性管理器的正式发行版</span><span class="sxs-lookup"><span data-stu-id="6499d-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="6499d-106">合规性管理器现已推出 (GA) 作为 [Microsoft 365 合规性中心](microsoft-365-compliance-center.md)内的端到端合规性管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6499d-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="6499d-107">在此版本中，合规性管理器将从 Microsoft 服务信任门户中先前的位置完成转换。</span><span class="sxs-lookup"><span data-stu-id="6499d-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span>

<span data-ttu-id="6499d-108">由于合规性分数的公开预览发展成为集中式工具，具有增强的合规性管理功能和更易于使用的功能。</span><span class="sxs-lookup"><span data-stu-id="6499d-108">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="6499d-109">GA 发行版中引入了一个更大的预建评估集合，可帮助您扩展合规性活动。</span><span class="sxs-lookup"><span data-stu-id="6499d-109">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="6499d-110">**了解有关 GA 版本的详细信息：**</span><span class="sxs-lookup"><span data-stu-id="6499d-110">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="6499d-111">我们的 [常见问题](compliance-manager-faq.md) 将更详细地引导您完成发展。</span><span class="sxs-lookup"><span data-stu-id="6499d-111">Our [frequently asked questions](compliance-manager-faq.md) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="6499d-112">阅读 [此博客文章](https://aka.ms/compliancemanager/GAblog)中的 "GA 功能增强"。</span><span class="sxs-lookup"><span data-stu-id="6499d-112">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="6499d-113">观看以下视频，了解合规性管理器如何帮助简化组织管理合规性的方式：</span><span class="sxs-lookup"><span data-stu-id="6499d-113">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="6499d-114">什么是合规性管理器</span><span class="sxs-lookup"><span data-stu-id="6499d-114">What is Compliance Manager</span></span>

<span data-ttu-id="6499d-115">[Microsoft 合规性管理器](https://compliance.microsoft.com/compliancemanager) 是 [microsoft 365 合规性中心](microsoft-365-compliance-center.md) 中的一项功能，可帮助您更轻松、方便地管理组织的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="6499d-115">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="6499d-116">合规性管理器可帮助你在法规遵从性旅程中进行，从获取数据保护风险的清单到管理实施控制的复杂性，保持最新的管理法规和证书，并向审计员报告。</span><span class="sxs-lookup"><span data-stu-id="6499d-116">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="6499d-117">合规性管理器通过提供以下功能帮助简化合规性并降低风险：</span><span class="sxs-lookup"><span data-stu-id="6499d-117">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="6499d-118">针对常见行业和区域标准和管理法规的预建评估，或自定义评估以满足您的独特合规性需求 (可用评估取决于您的许可协议; [了解详细](https://go.microsoft.com/fwlink/?linkid=2132371)) 。</span><span class="sxs-lookup"><span data-stu-id="6499d-118">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](https://go.microsoft.com/fwlink/?linkid=2132371)).</span></span>

- <span data-ttu-id="6499d-119">工作流功能，可帮助您通过单一工具高效地完成风险评估。</span><span class="sxs-lookup"><span data-stu-id="6499d-119">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="6499d-120">有关建议的改进措施的详细分步指南，可帮助您遵守与贵组织最相关的标准和法规。</span><span class="sxs-lookup"><span data-stu-id="6499d-120">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="6499d-121">对于由 Microsoft 管理的操作，你将看到 "实施详细信息" 和 "审核结果"。</span><span class="sxs-lookup"><span data-stu-id="6499d-121">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="6499d-122">基于风险的符合性分数，可帮助您了解完成改进措施中的进度，以帮助您了解合规性状态。</span><span class="sxs-lookup"><span data-stu-id="6499d-122">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="6499d-123">合规性管理器仪表板显示了你当前的合规性分数，可帮助你查看需要注意的事项，并指导你执行关键改进操作。</span><span class="sxs-lookup"><span data-stu-id="6499d-123">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="6499d-124">下面是合规性管理器仪表板外观的示例：</span><span class="sxs-lookup"><span data-stu-id="6499d-124">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="6499d-125">![合规性管理器-仪表板](../media/compliance-manager-dashboard.png "合规性管理器仪表板")</span><span class="sxs-lookup"><span data-stu-id="6499d-125">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="6499d-126">了解合规性分数</span><span class="sxs-lookup"><span data-stu-id="6499d-126">Understanding your compliance score</span></span>

<span data-ttu-id="6499d-127">合规性管理者奖项您要为符合法规、标准或策略的措施完成改进措施，并将这些点组合到整体合规性分数中。</span><span class="sxs-lookup"><span data-stu-id="6499d-127">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="6499d-128">每个操作对你的分数有不同的影响，具体取决于所涉及的潜在风险。</span><span class="sxs-lookup"><span data-stu-id="6499d-128">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="6499d-129">您的合规性分数可帮助您确定重点关注的操作，以改进您的总体合规性状态。</span><span class="sxs-lookup"><span data-stu-id="6499d-129">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="6499d-130">合规性管理器为你提供了基于 Microsoft 365 数据保护基准的初始分数。</span><span class="sxs-lookup"><span data-stu-id="6499d-130">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="6499d-131">此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="6499d-131">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="6499d-132">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6499d-132">Learn more</span></span>

<span data-ttu-id="6499d-133">[了解如何计算合规性分数](compliance-score-calculation.md)。</span><span class="sxs-lookup"><span data-stu-id="6499d-133">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="6499d-134">[了解如何处理改进操作](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="6499d-134">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="6499d-135">关键元素：控件、评估、模板、改进操作</span><span class="sxs-lookup"><span data-stu-id="6499d-135">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="6499d-136">合规性管理器使用多个数据元素来帮助您管理合规性活动。</span><span class="sxs-lookup"><span data-stu-id="6499d-136">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="6499d-137">在使用合规性管理器分配、测试和监视合规性活动时，对关键元素有一个基本的了解是很有帮助的：控件、评估、模板和改进操作。</span><span class="sxs-lookup"><span data-stu-id="6499d-137">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="6499d-138">控件</span><span class="sxs-lookup"><span data-stu-id="6499d-138">Controls</span></span>

<span data-ttu-id="6499d-139">控件是法规、标准或策略的要求。</span><span class="sxs-lookup"><span data-stu-id="6499d-139">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="6499d-140">它定义了如何评估和管理系统配置、组织过程以及负责满足法规、标准或策略的特定要求的人员。</span><span class="sxs-lookup"><span data-stu-id="6499d-140">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="6499d-141">合规性管理器跟踪以下类型的控件：</span><span class="sxs-lookup"><span data-stu-id="6499d-141">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="6499d-142">**Microsoft 托管控件** ： microsoft 云服务的控件，microsoft 负责实现</span><span class="sxs-lookup"><span data-stu-id="6499d-142">**Microsoft managed controls** : controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="6499d-143">**您的控件** ：有时称为 "客户托管控件"，它们是由您的组织实现和管理的控件</span><span class="sxs-lookup"><span data-stu-id="6499d-143">**Your controls** : sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="6499d-144">**共享控件** ：这些控件是你的组织和 Microsoft 共同负责实施的控制</span><span class="sxs-lookup"><span data-stu-id="6499d-144">**Shared controls** : these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="6499d-145">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6499d-145">Learn more</span></span>

<span data-ttu-id="6499d-146">[监视控件的进度](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)。</span><span class="sxs-lookup"><span data-stu-id="6499d-146">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="6499d-147">[了解合规性管理器如何持续评估控件](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。</span><span class="sxs-lookup"><span data-stu-id="6499d-147">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="6499d-148">评估</span><span class="sxs-lookup"><span data-stu-id="6499d-148">Assessments</span></span>

<span data-ttu-id="6499d-149">评估是从特定的法规、标准或策略中对控件进行分组。</span><span class="sxs-lookup"><span data-stu-id="6499d-149">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="6499d-150">完成评估中的操作可帮助您满足标准、法规或法律的要求。</span><span class="sxs-lookup"><span data-stu-id="6499d-150">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="6499d-151">例如，您可能有一个评估，在完成其中的所有操作后，可帮助您将 Microsoft 365 设置为符合 ISO 27001 的要求。</span><span class="sxs-lookup"><span data-stu-id="6499d-151">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="6499d-152">评估具有以下几个组件：</span><span class="sxs-lookup"><span data-stu-id="6499d-152">Assessments have several components:</span></span>

- <span data-ttu-id="6499d-153">**范围内的服务** ：适用于评估的一组特定的 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="6499d-153">**In-scope services** : the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="6499d-154">**Microsoft 托管控件** ： microsoft 云服务的控件，microsoft 云服务代表你代表你实施</span><span class="sxs-lookup"><span data-stu-id="6499d-154">**Microsoft managed controls** : controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="6499d-155">**您的控件** ：有时称为 "客户托管控件"，它们是由您的组织实现和管理的控件</span><span class="sxs-lookup"><span data-stu-id="6499d-155">**Your controls** : sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="6499d-156">**共享控件** ：这些控件是你的组织和 Microsoft 共同负责实施的控制</span><span class="sxs-lookup"><span data-stu-id="6499d-156">**Shared controls** : these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="6499d-157">**评估成绩** ：显示从评估中的操作（由组织和 Microsoft 管理）获得的可能积分总数的进度</span><span class="sxs-lookup"><span data-stu-id="6499d-157">**Assessment score** : shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="6499d-158">在创建评估时，您需要将其分配给一个组。</span><span class="sxs-lookup"><span data-stu-id="6499d-158">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="6499d-159">您可以按对组织的最逻辑的任何方式配置组。</span><span class="sxs-lookup"><span data-stu-id="6499d-159">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="6499d-160">例如，您可以按审核年、区域、解决方案、组织内的团队或其他某种方式对评估进行分组。</span><span class="sxs-lookup"><span data-stu-id="6499d-160">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="6499d-161">创建组后，您可以对 [合规性管理器仪表板进行筛选](compliance-manager-setup.md#filtering-your-dashboard-view) ，以查看一个或多个组的分数。</span><span class="sxs-lookup"><span data-stu-id="6499d-161">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="6499d-162">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6499d-162">Learn more</span></span>

<span data-ttu-id="6499d-163">[在合规性管理器中构建和管理评估](compliance-manager-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="6499d-163">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="6499d-164">模板</span><span class="sxs-lookup"><span data-stu-id="6499d-164">Templates</span></span>

<span data-ttu-id="6499d-165">合规性管理器提供可帮助您快速创建评估的模板。</span><span class="sxs-lookup"><span data-stu-id="6499d-165">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="6499d-166">您可以修改这些模板以创建针对您的需求而优化的评估。</span><span class="sxs-lookup"><span data-stu-id="6499d-166">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="6499d-167">您还可以通过创建包含自己的控件和操作的模板来构建自定义评估。</span><span class="sxs-lookup"><span data-stu-id="6499d-167">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="6499d-168">例如，您可能希望模板涵盖内部业务流程控制，或者是我们的150个预构建的评估模板中的一个不包含的区域数据保护标准。</span><span class="sxs-lookup"><span data-stu-id="6499d-168">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 150+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="6499d-169">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6499d-169">Learn more</span></span>

<span data-ttu-id="6499d-170">[查看合规性管理器提供的评估模板的列表](compliance-manager-templates-list.md)。</span><span class="sxs-lookup"><span data-stu-id="6499d-170">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="6499d-171">[获取创建和修改用于评估的模板的详细说明](compliance-manager-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="6499d-171">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="6499d-172">改进操作</span><span class="sxs-lookup"><span data-stu-id="6499d-172">Improvement actions</span></span>

<span data-ttu-id="6499d-173">改进操作可帮助您集中执行合规性活动。</span><span class="sxs-lookup"><span data-stu-id="6499d-173">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="6499d-174">每个改进操作都提供了建议的指南，旨在帮助您与数据保护法规和标准保持一致。</span><span class="sxs-lookup"><span data-stu-id="6499d-174">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="6499d-175">可将改进操作分配给组织中的用户，以执行实施和测试工作。</span><span class="sxs-lookup"><span data-stu-id="6499d-175">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="6499d-176">您还可以在 "改进" 操作中存储文档、注释和记录状态更新。</span><span class="sxs-lookup"><span data-stu-id="6499d-176">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="6499d-177">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6499d-177">Learn more</span></span>

<span data-ttu-id="6499d-178">[使用提高操作来管理合规性工作流](compliance-manager-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="6499d-178">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="6499d-179">[了解操作对合规性分数的影响](compliance-score-calculation.md#action-types-and-points)。</span><span class="sxs-lookup"><span data-stu-id="6499d-179">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="6499d-180">支持的语言</span><span class="sxs-lookup"><span data-stu-id="6499d-180">Supported languages</span></span>

<span data-ttu-id="6499d-181">合规性管理器可采用以下语言：</span><span class="sxs-lookup"><span data-stu-id="6499d-181">Compliance Manager is available in the following languages:</span></span>

- <span data-ttu-id="6499d-182">英语</span><span class="sxs-lookup"><span data-stu-id="6499d-182">English</span></span>
- <span data-ttu-id="6499d-183">马来印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="6499d-183">Bahasa Indonesian</span></span>
- <span data-ttu-id="6499d-184">马来马来语</span><span class="sxs-lookup"><span data-stu-id="6499d-184">Bahasa Malay</span></span>
- <span data-ttu-id="6499d-185">中文（简体）</span><span class="sxs-lookup"><span data-stu-id="6499d-185">Chinese (Simplified)</span></span>
- <span data-ttu-id="6499d-186">中文（繁体）</span><span class="sxs-lookup"><span data-stu-id="6499d-186">Chinese (Traditional)</span></span>
- <span data-ttu-id="6499d-187">捷克语</span><span class="sxs-lookup"><span data-stu-id="6499d-187">Czech</span></span>
- <span data-ttu-id="6499d-188">丹麦语</span><span class="sxs-lookup"><span data-stu-id="6499d-188">Danish</span></span>
- <span data-ttu-id="6499d-189">荷兰语</span><span class="sxs-lookup"><span data-stu-id="6499d-189">Dutch</span></span>
- <span data-ttu-id="6499d-190">芬兰语</span><span class="sxs-lookup"><span data-stu-id="6499d-190">Finnish</span></span>
- <span data-ttu-id="6499d-191">法语</span><span class="sxs-lookup"><span data-stu-id="6499d-191">French</span></span>
- <span data-ttu-id="6499d-192">德语</span><span class="sxs-lookup"><span data-stu-id="6499d-192">German</span></span>
- <span data-ttu-id="6499d-193">希伯来语</span><span class="sxs-lookup"><span data-stu-id="6499d-193">Hebrew</span></span>
- <span data-ttu-id="6499d-194">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="6499d-194">Hungarian</span></span>
- <span data-ttu-id="6499d-195">意大利语</span><span class="sxs-lookup"><span data-stu-id="6499d-195">Italian</span></span>
- <span data-ttu-id="6499d-196">日语</span><span class="sxs-lookup"><span data-stu-id="6499d-196">Japanese</span></span>
- <span data-ttu-id="6499d-197">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="6499d-197">Korean</span></span>
- <span data-ttu-id="6499d-198">挪威语</span><span class="sxs-lookup"><span data-stu-id="6499d-198">Norwegian</span></span>
- <span data-ttu-id="6499d-199">波兰语</span><span class="sxs-lookup"><span data-stu-id="6499d-199">Polish</span></span>
- <span data-ttu-id="6499d-200">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="6499d-200">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="6499d-201">俄语</span><span class="sxs-lookup"><span data-stu-id="6499d-201">Russian</span></span>
- <span data-ttu-id="6499d-202">西班牙语</span><span class="sxs-lookup"><span data-stu-id="6499d-202">Spanish</span></span>
- <span data-ttu-id="6499d-203">瑞典语</span><span class="sxs-lookup"><span data-stu-id="6499d-203">Swedish</span></span>
- <span data-ttu-id="6499d-204">泰语</span><span class="sxs-lookup"><span data-stu-id="6499d-204">Thai</span></span>
- <span data-ttu-id="6499d-205">土耳其语</span><span class="sxs-lookup"><span data-stu-id="6499d-205">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="6499d-206">后续步骤：设置和自定义</span><span class="sxs-lookup"><span data-stu-id="6499d-206">Next steps: set up and customize</span></span>

<span data-ttu-id="6499d-207">了解如何登录、分配权限和角色、配置设置以及在 [合规性管理器开始](compliance-manager-setup.md)时自定义仪表板视图。</span><span class="sxs-lookup"><span data-stu-id="6499d-207">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="6499d-208">然后，开始自定义合规性管理器，以帮助您遵循与您的组织最重要的行业标准（通过 [设置评估](compliance-manager-assessments.md)）。</span><span class="sxs-lookup"><span data-stu-id="6499d-208">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>