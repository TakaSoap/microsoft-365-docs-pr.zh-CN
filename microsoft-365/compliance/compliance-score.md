---
title: Microsoft 合规性分数（预览）
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
description: Microsoft 合规性分数（预览版）可帮助组织简化和自动化风险评估，并建议用于帮助解决风险的建议措施。
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016135"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="2c8f4-103">Microsoft 合规性分数（预览）</span><span class="sxs-lookup"><span data-stu-id="2c8f4-103">Microsoft Compliance Score (preview)</span></span>

<span data-ttu-id="2c8f4-104">**本文内容：** 了解符合性分数是什么，它如何帮助简化管理法规遵从性的方式，以及如何为你的组织进行设置。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-104">**In this article:** Learn what Compliance Score is, how it helps simplify the way you manage compliance, and how to set it up for your organization.</span></span>

<span data-ttu-id="2c8f4-105">**新增功能：** 2020年6月发布的版本包含用于创建和管理评估的新功能，以及查看合规性分数内的控制措施。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-105">**What's new:** The June 2020 release includes new functionality to create and manage assessments, and to view controls within Compliance Score.</span></span> <span data-ttu-id="2c8f4-106">访问[合规性分数发行说明](compliance-score-release-notes.md)，查看合规性分数的公开预览版中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-106">Visit the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new in the public preview of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="2c8f4-107">合规性分数是什么</span><span class="sxs-lookup"><span data-stu-id="2c8f4-107">What is Compliance Score</span></span>

<span data-ttu-id="2c8f4-108">[Microsoft 合规性分数](https://compliance.microsoft.com/compliancescore)是[microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的一项预览功能，可帮助您了解组织的合规性状况。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-108">[Microsoft Compliance Score](https://compliance.microsoft.com/compliancescore) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture.</span></span> <span data-ttu-id="2c8f4-109">它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-109">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="2c8f4-110">您可以使用合规性分数作为一种工具来跟踪所有风险评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-110">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="2c8f4-111">它提供了工作流功能，可帮助您通过通用工具高效完成风险评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-111">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="2c8f4-112">[合规性管理器](compliance-manager-overview.md)用户将注意到，合规性分数现在是一项独立功能，具有更简单、更易于使用用户的设计，可帮助组织更轻松地管理合规性。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-112">[Compliance Manager](compliance-manager-overview.md) users will notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help organizations more easily manage compliance.</span></span>

<span data-ttu-id="2c8f4-113">主合规性分数页面是自定义仪表板。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-113">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="2c8f4-114">它显示了你当前的成绩，可帮助你查看需要注意的事项，并指导你提高成绩的操作。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-114">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="2c8f4-115">您的合规性分数仪表板将如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c8f4-115">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="2c8f4-116">![合规性分数-仪表板](../media/compliance-score-dashboard.png "合规性分数仪表板")</span><span class="sxs-lookup"><span data-stu-id="2c8f4-116">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="2c8f4-117">简化了合规性管理</span><span class="sxs-lookup"><span data-stu-id="2c8f4-117">Simplified compliance management</span></span>

<span data-ttu-id="2c8f4-118">合规性分数通过提供以下功能来帮助简化合规性管理：</span><span class="sxs-lookup"><span data-stu-id="2c8f4-118">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="2c8f4-119">**持续评估**：通过 Microsoft 365 环境自动扫描，以检测和监视系统中数据保护控件的有效性</span><span class="sxs-lookup"><span data-stu-id="2c8f4-119">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="2c8f4-120">**建议的操作**：提供有关如何实现控制以最大化分数的建议和分步指南</span><span class="sxs-lookup"><span data-stu-id="2c8f4-120">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="2c8f4-121">**内置的控件映射**：通过提供内置的通用控制框架，帮助您及时了解日益发展的合规性环境</span><span class="sxs-lookup"><span data-stu-id="2c8f4-121">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c8f4-122">合规性分数和合规性管理器中提供的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-122">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="2c8f4-123">根据您的法规环境评估和验证客户控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-123">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="2c8f4-124">这些服务当前处于预览阶段，并遵循[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-124">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="2c8f4-125">另请参阅[适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-125">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="2c8f4-126">与合规性管理器的关系</span><span class="sxs-lookup"><span data-stu-id="2c8f4-126">Relationship to Compliance Manager</span></span>

<span data-ttu-id="2c8f4-127">将合规性分数视为合规性管理器的简化体验。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-127">Think of Compliance Score as a simplified experience of Compliance Manager.</span></span> <span data-ttu-id="2c8f4-128">虽然这两个功能与集成的工具不同时存在，但遵从性分数可使您更轻松地监控整体合规性状况并采取措施来改进。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-128">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="2c8f4-129">合规性分数与合规性管理器共享相同的后端。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-129">Compliance Score shares the same backend with Compliance Manager.</span></span> <span data-ttu-id="2c8f4-130">您在一个工具中执行的任何操作都将在另一个工具中呈现。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-130">Anything that you do in one tool will surface in the other tool.</span></span>

<span data-ttu-id="2c8f4-131">在公共预览过程中，评估和模板管理的一些功能仍在合规性管理器中。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-131">Some functionality for assessment and template management remains in Compliance Manager during public preview.</span></span> <span data-ttu-id="2c8f4-132">我们建议你在合规性分数中开始所有合规性管理活动。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="2c8f4-133">当你转到合规性管理器处理的函数时，我们将指导你。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-133">When you come to functions handled by Compliance Manager, we’ll guide you there.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="2c8f4-134">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2c8f4-134">Learn more</span></span>

<span data-ttu-id="2c8f4-135">[了解合规性分数与合规性管理器之间的关系](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-135">[Understand the relationship between Compliance Score and Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="2c8f4-136">了解你的成绩</span><span class="sxs-lookup"><span data-stu-id="2c8f4-136">Understanding your score</span></span>

<span data-ttu-id="2c8f4-137">合规性分数奖项您需要完成的操作，以遵守法规、标准或策略。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-137">Compliance Score awards you points for completing actions taken to comply with a regulation, standard, or policy.</span></span> <span data-ttu-id="2c8f4-138">每个操作对你的分数有不同的影响，具体取决于所涉及的潜在风险。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-138">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="2c8f4-139">你的分数可帮助优先考虑要关注的操作，以改进你的总体合规性状况。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-139">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="2c8f4-140">合规性分数为你提供了基于 Microsoft 365 数据保护基准的初始分数。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-140">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span>  <span data-ttu-id="2c8f4-141">此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-141">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="2c8f4-142">此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）以及 FedRAMP （联邦风险和授权管理计划）和 GDPR （欧盟的常规数据保护法规）中提取元素。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-142">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="2c8f4-143">数据保护基准评估用于在配置任何其他评估之前计算您的初始分数。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-143">The data protection baseline assessment is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="2c8f4-144">首次访问时，合规性分数已从 Microsoft 365 解决方案中收集信号。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-144">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="2c8f4-145">你将快速了解你的组织是如何相对于关键数据保护标准和管理法规执行的，并查看建议采取的改进措施。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-145">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="2c8f4-146">由于每个组织都有特定的需求，因此合规性分数取决于您设置和管理您自己的评估以更好地缓解风险。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-146">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to better mitigate risks.</span></span> <span data-ttu-id="2c8f4-147">例如，如果您的组织属于金融服务行业，您可能需要添加 FFIEC 评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-147">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="2c8f4-148">如果您的组织属于医疗保健行业，则可以添加 HIPAA/高科技评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-148">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="2c8f4-149">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2c8f4-149">Learn more</span></span>

<span data-ttu-id="2c8f4-150">[了解如何计算和持续监控合规性分数](compliance-score-methodology.md)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-150">[Understand how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>

<span data-ttu-id="2c8f4-151">[在合规性分数中创建和管理评估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-151">[Create and manage assessments in Compliance Score](compliance-score-assessments.md).</span></span>

## <a name="key-components-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="2c8f4-152">关键组件：控件、评估、模板、改进操作</span><span class="sxs-lookup"><span data-stu-id="2c8f4-152">Key components: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="2c8f4-153">合规性分数使用多个组件来帮助您管理合规性活动。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-153">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="2c8f4-154">在使用合规性分数分配、测试和监视合规性活动时，有必要对关键组件有一个基本的了解：控件、评估、模板和改进操作。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-154">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key components: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="2c8f4-155">控件</span><span class="sxs-lookup"><span data-stu-id="2c8f4-155">Controls</span></span>

<span data-ttu-id="2c8f4-156">控件是法规、标准或策略的要求。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-156">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="2c8f4-157">它定义了如何评估和管理系统配置、组织过程以及负责满足法规、标准或策略的特定要求的人员。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-157">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="2c8f4-158">合规性分数跟踪两种类型的控件：</span><span class="sxs-lookup"><span data-stu-id="2c8f4-158">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="2c8f4-159">**Microsoft 托管控件**： microsoft 云服务的控件，microsoft 负责实现</span><span class="sxs-lookup"><span data-stu-id="2c8f4-159">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="2c8f4-160">**您的控件**：有时称为 "客户控件"，它们是由您的组织实现和管理的控件</span><span class="sxs-lookup"><span data-stu-id="2c8f4-160">**Your controls**: sometimes referred to as customer controls, these are controls implemented and managed by your organization</span></span>

#### <a name="learn-more"></a><span data-ttu-id="2c8f4-161">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2c8f4-161">Learn more</span></span>

<span data-ttu-id="2c8f4-162">[监视控件的进度](compliance-score-assessments.md#monitor-assessment-progress-and-controls)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-162">[Monitor progress of your controls](compliance-score-assessments.md#monitor-assessment-progress-and-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="2c8f4-163">评估</span><span class="sxs-lookup"><span data-stu-id="2c8f4-163">Assessments</span></span>

<span data-ttu-id="2c8f4-164">评估是从特定的法规、标准或策略中对控件进行分组。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-164">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="2c8f4-165">完成评估中的操作可帮助您满足标准、法规或法律的要求。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-165">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="2c8f4-166">例如，您可以进行一项评估，在完成其中的所有操作后，会将 Microsoft 365 设置为符合 ISO 27001 要求的行为。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-166">For example, you may have an assessment that, when you complete all actions within it, brings your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="2c8f4-167">评估具有以下几个组件：</span><span class="sxs-lookup"><span data-stu-id="2c8f4-167">Assessments have several components:</span></span>

- <span data-ttu-id="2c8f4-168">**范围内的服务**：适用于评估的一组特定的 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="2c8f4-168">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="2c8f4-169">**Microsoft 托管控件**： microsoft 实现和测试的控件</span><span class="sxs-lookup"><span data-stu-id="2c8f4-169">**Microsoft managed controls**: controls that Microsoft implements and tests</span></span>
- <span data-ttu-id="2c8f4-170">**您的控件**：您管理的控件</span><span class="sxs-lookup"><span data-stu-id="2c8f4-170">**Your controls**: controls that you manage</span></span>
- <span data-ttu-id="2c8f4-171">**评估分数**：在该评估中完成改进操作所实现的分数百分比</span><span class="sxs-lookup"><span data-stu-id="2c8f4-171">**Assessment score**: the percentage of the points achieved by completing improvement actions within that assessment</span></span>

<span data-ttu-id="2c8f4-172">在创建评估时，您需要将其分配给一个**组**。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-172">When creating assessments, you'll assign them to a **group**.</span></span> <span data-ttu-id="2c8f4-173">您可以按对组织的最逻辑的任何方式配置组。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-173">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="2c8f4-174">例如，您可以按年、合规性标准、服务、组织内的团队或其他方式对评估进行分组。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-174">For example, you may group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span> <span data-ttu-id="2c8f4-175">创建组后，您可以[筛选合规性分数仪表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一个或多个组的分数。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-175">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="2c8f4-176">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2c8f4-176">Learn more</span></span>

<span data-ttu-id="2c8f4-177">[在合规性分数中创建和管理评估](compliance-score-assessments.md)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-177">[Create and manage assessments in Compliance Score](compliance-score-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="2c8f4-178">模板</span><span class="sxs-lookup"><span data-stu-id="2c8f4-178">Templates</span></span>

<span data-ttu-id="2c8f4-179">合规性分数提供可供你快速创建评估的模板。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-179">Compliance Score provides templates that are ready for you to quickly create assessments.</span></span> <span data-ttu-id="2c8f4-180">您可以修改这些模板以创建针对您的需求而优化的评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-180">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="2c8f4-181">您还可以通过使用自己的控件和操作来开发自己的模板来创建自定义评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-181">You can also create a Custom Assessment by developing your own template with your own controls and actions.</span></span> <span data-ttu-id="2c8f4-182">例如，您可能希望模板涵盖内部业务流程控制或一个我们的模板未涵盖的区域数据保护标准。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-182">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our templates.</span></span>

<span data-ttu-id="2c8f4-183">通过创建您自己的模板，不仅可以跟踪 Microsoft 云评估，还可以跟踪组织范围内的任何其他风险评估。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-183">Creating your own templates lets you track not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="2c8f4-184">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2c8f4-184">Learn more</span></span>

<span data-ttu-id="2c8f4-185">[查看适用于构建评估的合规性分数中的模板](compliance-score-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-185">[View the templates available in Compliance Score for building assessments](compliance-score-templates.md).</span></span>

<span data-ttu-id="2c8f4-186">[获取有关创建和修改模板合规性管理器的详细说明](working-with-compliance-manager.md#templates)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-186">[Get detailed instructions for creating and modifying templates Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="2c8f4-187">改进操作</span><span class="sxs-lookup"><span data-stu-id="2c8f4-187">Improvement actions</span></span>

<span data-ttu-id="2c8f4-188">改进的操作将对合规性活动进行集中。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-188">Improvement actions centralize your compliance activities.</span></span> <span data-ttu-id="2c8f4-189">每个改进操作都提供了详细的实施指导，可帮助您与数据保护法规和标准保持一致。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-189">Each improvement action gives detailed implementation guidance to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="2c8f4-190">可将操作分配给组织中的用户，以执行实施和测试工作。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-190">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="2c8f4-191">您还可以在 "改进" 操作中存储文档、注释和记录状态更新。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-191">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="2c8f4-192">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2c8f4-192">Learn more</span></span>

<span data-ttu-id="2c8f4-193">[使用提高操作来管理合规性工作流](compliance-score-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-193">[Use improvement actions to manage your compliance workflow](compliance-score-improvement-actions.md).</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="2c8f4-194">后续步骤：设置和自定义</span><span class="sxs-lookup"><span data-stu-id="2c8f4-194">Next steps: set up and customize</span></span>

<span data-ttu-id="2c8f4-195">了解如何登录、设置权限和角色、配置安全分数更新以及在[合规性分数设置](compliance-score-setup.md)时对仪表板视图进行个性化设置。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-195">Learn how to sign in, set permissions and roles, configure Secure Score updates, and personalize your dashboard view at [Compliance Score setup](compliance-score-setup.md).</span></span>

<span data-ttu-id="2c8f4-196">然后，通过[设置评估](compliance-score-assessments.md)开始为你的组织自定义合规性分数。</span><span class="sxs-lookup"><span data-stu-id="2c8f4-196">Then start customizing Compliance Score for your organization by [setting up assessments](compliance-score-assessments.md).</span></span>