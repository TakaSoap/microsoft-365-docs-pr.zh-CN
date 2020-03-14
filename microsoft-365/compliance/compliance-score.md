---
title: Microsoft 合规性分数
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
description: Microsoft 合规性分数可帮助组织简化和自动化风险评估，并建议用于帮助解决风险的建议措施。
ms.openlocfilehash: dff5e6c057df37c076e328d5203a1eb4e4b3207a
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635110"
---
# <a name="microsoft-compliance-score-preview"></a><span data-ttu-id="1c170-103">Microsoft 合规性分数（预览）</span><span class="sxs-lookup"><span data-stu-id="1c170-103">Microsoft Compliance Score (Preview)</span></span>

<span data-ttu-id="1c170-104">Microsoft 合规性分数有助于简化管理合规性的方式，并通过用户友好的体验降低合规性风险。</span><span class="sxs-lookup"><span data-stu-id="1c170-104">Microsoft Compliance Score helps to simplify the way you manage compliance and reduce compliance risks through a user-friendly experience.</span></span> <span data-ttu-id="1c170-105">合规性分数现在适用于[Microsoft 365 合规性中心](microsoft-365-compliance-center.md)中的公共预览版。</span><span class="sxs-lookup"><span data-stu-id="1c170-105">Compliance Score is now available for public preview in the  [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>

<span data-ttu-id="1c170-106">**本文内容：** 阅读本文，了解符合性分数以及如何对组织进行设置。</span><span class="sxs-lookup"><span data-stu-id="1c170-106">**In this article:** Read this article to understand what Compliance Score is and how to set it up for your organization.</span></span>

<span data-ttu-id="1c170-107">**了解更新：** 转到[合规性分数发行说明](compliance-score-release-notes.md)，以查看符合性分数的预览版本的新增和已知问题。</span><span class="sxs-lookup"><span data-stu-id="1c170-107">**Learn about updates:** Go to the [Compliance Score release notes](compliance-score-release-notes.md) to see what's new and known issues with the preview version of Compliance Score.</span></span>

## <a name="what-is-compliance-score"></a><span data-ttu-id="1c170-108">合规性分数是什么</span><span class="sxs-lookup"><span data-stu-id="1c170-108">What is Compliance Score</span></span>

<span data-ttu-id="1c170-109">Microsoft 合规性分数是 Microsoft 365 合规性中心中的一项预览功能，可帮助您了解组织的合规性状况。</span><span class="sxs-lookup"><span data-stu-id="1c170-109">Microsoft Compliance Score is a preview feature in the Microsoft 365 compliance center to help you understand your organization’s compliance posture.</span></span> <span data-ttu-id="1c170-110">它将计算基于风险的分数，以衡量您在帮助降低数据保护和法规标准方面的风险的完成操作的进度。</span><span class="sxs-lookup"><span data-stu-id="1c170-110">It calculates a risk-based score measuring your progress in completing actions that help reduce risks around data protection and regulatory standards.</span></span>

<span data-ttu-id="1c170-111">您可以使用合规性分数作为一种工具来跟踪所有风险评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-111">You can use Compliance Score as a tool to track all of your risk assessments.</span></span> <span data-ttu-id="1c170-112">它提供了工作流功能，可帮助您通过通用工具高效完成风险评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-112">It provides workflow capabilities to help you efficiently complete your risk assessments through a common tool.</span></span>

<span data-ttu-id="1c170-113">如果您当前使用[合规性管理器](compliance-manager-overview.md)，您会注意到，合规性分数现在是一个独立的功能，具有更简单、更易于使用用户的设计，可帮助您更轻松地管理合规性。</span><span class="sxs-lookup"><span data-stu-id="1c170-113">If you currently use [Compliance Manager](compliance-manager-overview.md), you’ll notice that Compliance Score is now a standalone feature with a simpler, more user-friendly design to help you manage compliance more easily.</span></span> 

<span data-ttu-id="1c170-114">主合规性分数页面是自定义仪表板。</span><span class="sxs-lookup"><span data-stu-id="1c170-114">The main Compliance Score page is your custom dashboard.</span></span> <span data-ttu-id="1c170-115">它显示了你当前的成绩，可帮助你查看需要注意的事项，并指导你提高成绩的操作。</span><span class="sxs-lookup"><span data-stu-id="1c170-115">It shows your current score, helps you see what needs attention, and guides you to actions to improve your score.</span></span> <span data-ttu-id="1c170-116">您的合规性分数仪表板将如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c170-116">Your Compliance Score dashboard will look like this:</span></span>

<span data-ttu-id="1c170-117">![合规性分数-仪表板](../media/compliance-score-dashboard.png "合规性分数仪表板")</span><span class="sxs-lookup"><span data-stu-id="1c170-117">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="simplified-compliance-management"></a><span data-ttu-id="1c170-118">简化了合规性管理</span><span class="sxs-lookup"><span data-stu-id="1c170-118">Simplified compliance management</span></span>

<span data-ttu-id="1c170-119">合规性分数通过提供以下功能来帮助简化合规性管理：</span><span class="sxs-lookup"><span data-stu-id="1c170-119">Compliance Score helps simplify compliance management by providing:</span></span>

- <span data-ttu-id="1c170-120">**持续评估**：通过 Microsoft 365 环境自动扫描，以检测和监视系统中数据保护控件的有效性</span><span class="sxs-lookup"><span data-stu-id="1c170-120">**Continuous assessments**: automatically scans through your Microsoft 365 environments to detect and monitor the effectiveness of data protection controls in your system</span></span>
- <span data-ttu-id="1c170-121">**建议的操作**：提供有关如何实现控制以最大化分数的建议和分步指南</span><span class="sxs-lookup"><span data-stu-id="1c170-121">**Recommended actions**: provides recommendations and step-by-step guidance for how to implement controls to maximize your score</span></span>
-  <span data-ttu-id="1c170-122">**内置的控件映射**：通过提供内置的通用控制框架，帮助您及时了解日益发展的合规性环境</span><span class="sxs-lookup"><span data-stu-id="1c170-122">**Built-in control mapping**: helps you stay current with the evolving compliance landscape by providing a built-in common control framework</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="1c170-123">合规性分数不表示对任何特定标准或法规的组织合规性的绝对衡量。</span><span class="sxs-lookup"><span data-stu-id="1c170-123">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="1c170-124">它表示您已采用的控制程度，可降低个人数据和个人隐私的风险。</span><span class="sxs-lookup"><span data-stu-id="1c170-124">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="1c170-125">不应将合规性分数和合规性管理器中的建议解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="1c170-125">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="1c170-126">此服务目前处于预览阶段，并受[在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。</span><span class="sxs-lookup"><span data-stu-id="1c170-126">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="relationship-to-compliance-manager"></a><span data-ttu-id="1c170-127">与合规性管理器的关系</span><span class="sxs-lookup"><span data-stu-id="1c170-127">Relationship to Compliance Manager</span></span>

<span data-ttu-id="1c170-128">将合规性分数视为合规性管理器的简化版本。</span><span class="sxs-lookup"><span data-stu-id="1c170-128">Think of Compliance Score as a simplified version of Compliance Manager.</span></span> <span data-ttu-id="1c170-129">虽然这两个功能与集成的工具不同时存在，但遵从性分数可使您更轻松地监控整体合规性状况并采取措施来改进。</span><span class="sxs-lookup"><span data-stu-id="1c170-129">While the two exist as distinct yet integrated tools, Compliance Score makes it easier to monitor your overall compliance posture and take steps to improve it.</span></span>

<span data-ttu-id="1c170-130">合规性分数与合规性管理器共享相同的后端，因此合规性管理器中可能已具有的任何数据将在合规性分数中显示。</span><span class="sxs-lookup"><span data-stu-id="1c170-130">Compliance Score shares the same backend with Compliance Manager, so any data you may already have in Compliance Manager will show in Compliance Score.</span></span>

<span data-ttu-id="1c170-131">在公共预览版中，某些功能仅保留在合规性管理器中，例如管理评估和创建模板。</span><span class="sxs-lookup"><span data-stu-id="1c170-131">During public preview, some functionality remains solely in Compliance Manager, such as managing assessments and creating templates.</span></span> <span data-ttu-id="1c170-132">我们建议你在合规性分数中开始所有合规性管理活动。</span><span class="sxs-lookup"><span data-stu-id="1c170-132">We recommend beginning all of your compliance management activities in Compliance Score.</span></span> <span data-ttu-id="1c170-133">当您转到合规性管理器处理的函数时，系统将指导您使用该工具。</span><span class="sxs-lookup"><span data-stu-id="1c170-133">When you come to functions handled by Compliance Manager, you will be guided to that tool.</span></span> <span data-ttu-id="1c170-134">出于此原因，本文档中的一些文档将向您提供合规性管理器主题。</span><span class="sxs-lookup"><span data-stu-id="1c170-134">For that reason, some of this documentation directs you to Compliance Manager topics.</span></span>

<span data-ttu-id="1c170-135">了解有关[合规性分数发行说明](compliance-score-release-notes.md)中合规性分数和合规性管理器之间关系的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1c170-135">Learn more about the relationship between Compliance Score and Compliance Manager in the [Compliance Score release notes](compliance-score-release-notes.md).</span></span>

## <a name="understanding-your-score"></a><span data-ttu-id="1c170-136">了解你的成绩</span><span class="sxs-lookup"><span data-stu-id="1c170-136">Understanding your score</span></span>

<span data-ttu-id="1c170-137">合规性分数为你提供了基于 Microsoft 365 数据保护基准的初始分数。</span><span class="sxs-lookup"><span data-stu-id="1c170-137">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="1c170-138">此基准是一组包含常见行业法规和标准的控件。</span><span class="sxs-lookup"><span data-stu-id="1c170-138">This baseline is a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="1c170-139">虽然这一分数是评估合规性状况的一个很好的起点，但一旦添加了与贵组织更相关的评估，合规性分数就会变得更加强大。</span><span class="sxs-lookup"><span data-stu-id="1c170-139">While this score is a good starting point for assessing your compliance posture, Compliance Score becomes more powerful once you add assessments that are more relevant to your organization.</span></span>

<span data-ttu-id="1c170-140">例如，如果您的组织属于金融服务行业，您可能需要添加 FFIEC 评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-140">For example, if your organization belongs to the financial services industry, you may want to add the FFIEC assessment.</span></span> <span data-ttu-id="1c170-141">如果您的组织属于医疗保健行业，则可以添加 HIPAA/高科技评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-141">If your organization belongs to the healthcare industry, you can add the HIPAA/HITECH assessment.</span></span> <span data-ttu-id="1c170-142">了解如何[在合规性管理器中添加评估](working-with-compliance-manager.md#assessments)。</span><span class="sxs-lookup"><span data-stu-id="1c170-142">Learn how to [add assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

<span data-ttu-id="1c170-143">了解有关[如何计算和持续监控合规性分数](compliance-score-methodology.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1c170-143">Learn more about [how your compliance score is calculated and continuously monitored](compliance-score-methodology.md).</span></span>


## <a name="key-components-controls-assessments-templates-groups"></a><span data-ttu-id="1c170-144">关键组件：控件、评估、模板、组</span><span class="sxs-lookup"><span data-stu-id="1c170-144">Key components: controls, assessments, templates, groups</span></span>

<span data-ttu-id="1c170-145">合规性分数使用多个组件来帮助您管理合规性活动。</span><span class="sxs-lookup"><span data-stu-id="1c170-145">Compliance Score uses several components to help you manage your compliance activities.</span></span> <span data-ttu-id="1c170-146">在使用合规性分数分配、测试和监视合规性活动时，有必要对这些关键组件有一个基本的了解。</span><span class="sxs-lookup"><span data-stu-id="1c170-146">As you use Compliance Score to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of these key components.</span></span> <span data-ttu-id="1c170-147">此图显示了它们之间的关系：</span><span class="sxs-lookup"><span data-stu-id="1c170-147">This diagram shows the relationships among them:</span></span>

<span data-ttu-id="1c170-148">![合规性管理器版本3中的关系](../media/compliance-manager-relationships.png "合规性分数组件")</span><span class="sxs-lookup"><span data-stu-id="1c170-148">![Relationships in Compliance Manager Version 3](../media/compliance-manager-relationships.png "Compliance Score components")</span></span>

### <a name="controls"></a><span data-ttu-id="1c170-149">控件</span><span class="sxs-lookup"><span data-stu-id="1c170-149">Controls</span></span>

<span data-ttu-id="1c170-150">控件定义评估和管理系统配置、组织过程和人员责任的方式，以满足法规、标准或内部策略的特定要求。</span><span class="sxs-lookup"><span data-stu-id="1c170-150">A control defines how you assess and manage system configuration, organizational process, and people accountability to meet a specific requirement of a regulation, standard, or internal policy.</span></span>

<span data-ttu-id="1c170-151">合规性分数跟踪两种类型的控件：</span><span class="sxs-lookup"><span data-stu-id="1c170-151">Compliance Score tracks two types of controls:</span></span>

1. <span data-ttu-id="1c170-152">**Microsoft 托管控件**： microsoft 云服务的控件，microsoft 负责实现</span><span class="sxs-lookup"><span data-stu-id="1c170-152">**Microsoft-managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="1c170-153">**客户管理的控件**：由您的组织管理的、负责实施的控件</span><span class="sxs-lookup"><span data-stu-id="1c170-153">**Customer-managed controls**: controls managed by your organization, which you are responsible for implementing</span></span>
 
### <a name="assessments"></a><span data-ttu-id="1c170-154">评估</span><span class="sxs-lookup"><span data-stu-id="1c170-154">Assessments</span></span>

<span data-ttu-id="1c170-155">评估是对为您的组织启动计分过程的模板的评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-155">An assessment is an evaluation of a template that initiates the scoring process for your organization.</span></span> <span data-ttu-id="1c170-156">评估组满足标准、法规或法律要求所必需的操作。</span><span class="sxs-lookup"><span data-stu-id="1c170-156">Assessments group the actions necessary to meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="1c170-157">例如，您可以进行一项评估，在完成所有操作后，将 Office 365 设置为符合 ISO 27001 要求的行为。</span><span class="sxs-lookup"><span data-stu-id="1c170-157">For example, you may have an assessment that, when you complete all actions within it, brings your Office 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="1c170-158">默认情况下，合规性分数为您的组织提供基于 Microsoft 365 数据保护基准的评估，这是降低数据保护和合规性风险的建议（[了解详细信息](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)）。</span><span class="sxs-lookup"><span data-stu-id="1c170-158">By default, Compliance Score provides your organization with an assessment based on the Microsoft 365 data protection baseline, a recommendation for reducing your data protection and compliance risks ([learn more](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)).</span></span>

<span data-ttu-id="1c170-159">评估包括以下几个组件：</span><span class="sxs-lookup"><span data-stu-id="1c170-159">Assessments include several components:</span></span>

- <span data-ttu-id="1c170-160">**范围内的服务**：适用于评估的一组特定的 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="1c170-160">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="1c170-161">**Microsoft 托管控件**： microsoft 实现和测试的控件</span><span class="sxs-lookup"><span data-stu-id="1c170-161">**Microsoft-managed controls**: controls that Microsoft implemented and tested</span></span>
- <span data-ttu-id="1c170-162">**客户管理的控件**：您管理的控件</span><span class="sxs-lookup"><span data-stu-id="1c170-162">**Customer-managed controls**: controls that you manage</span></span>
- <span data-ttu-id="1c170-163">**评估成绩**：完成该评估中的操作所实现的分数百分比</span><span class="sxs-lookup"><span data-stu-id="1c170-163">**Assessment score**: the percentage of the points achieved by completing actions within that assessment</span></span>

> [!NOTE]
> <span data-ttu-id="1c170-164">合规性分数显示你的评估以及它们对你的总体成绩的影响。</span><span class="sxs-lookup"><span data-stu-id="1c170-164">Compliance Score displays your assessments and how they factor into your overall score.</span></span> <span data-ttu-id="1c170-165">但是，在公开预览过程中，你将转到合规性管理器来管理评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-165">However, during public preview you will be directed to Compliance Manager to manage your assessments.</span></span>

<span data-ttu-id="1c170-166">查看[合规性管理器中使用评估](working-with-compliance-manager.md#assessments)的详细说明。</span><span class="sxs-lookup"><span data-stu-id="1c170-166">View detailed instructions for [working with assessments in Compliance Manager](working-with-compliance-manager.md#assessments).</span></span>

### <a name="templates"></a><span data-ttu-id="1c170-167">模板</span><span class="sxs-lookup"><span data-stu-id="1c170-167">Templates</span></span>

<span data-ttu-id="1c170-168">合规性分数提供了预配置的评估模板。</span><span class="sxs-lookup"><span data-stu-id="1c170-168">Compliance Score provides pre-configured templates for assessments.</span></span> <span data-ttu-id="1c170-169">合规性分数还允许您创建自己的评估模板以满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="1c170-169">Compliance Score also allows you to create templates for your own assessments to suit your needs.</span></span> <span data-ttu-id="1c170-170">例如，您可以为业务流程控制创建一个模板，或为不包含在某个预先配置的模板中的区域数据保护或合规性标准的模板。</span><span class="sxs-lookup"><span data-stu-id="1c170-170">For example, you can create a template for your business process control, or a template for a regional data protection or compliance standard that isn’t covered by one of the pre-configured templates.</span></span>  <span data-ttu-id="1c170-171">通过创建您自己的模板，您可以创建自定义评估，以确保合规性分数不仅跟踪 Microsoft 云评估，还跟踪组织范围内的任何其他风险评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-171">By creating your own templates, you can create custom assessments to ensure that Compliance Score tracks not only Microsoft cloud assessments, but also any other risk assessments in scope for your organization.</span></span>

<span data-ttu-id="1c170-172">您可以通过复制现有模板或从 Excel 文件中导入控件信息来创建新模板。</span><span class="sxs-lookup"><span data-stu-id="1c170-172">You can create new templates by copying an existing template, or by importing controls information from an Excel file.</span></span> <span data-ttu-id="1c170-173">查看[在合规性管理器中创建模板](working-with-compliance-manager.md#templates)的详细说明。</span><span class="sxs-lookup"><span data-stu-id="1c170-173">View detailed instructions for [creating templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>

<span data-ttu-id="1c170-174">预配置的合规性分数模板包括：</span><span class="sxs-lookup"><span data-stu-id="1c170-174">The pre-configured templates for Compliance Score are:</span></span>

1. [<span data-ttu-id="1c170-175">巴西常规数据保护法律（LGPD）</span><span class="sxs-lookup"><span data-stu-id="1c170-175">Brazil General Data Protection Law (LGPD)</span></span>](https://go.microsoft.com/fwlink/?linkid=2115387)
2. <span data-ttu-id="1c170-176">[加利福尼亚州消费者隐私法案（CCPA）](https://go.microsoft.com/fwlink/?linkid=2108871) （预览）</span><span class="sxs-lookup"><span data-stu-id="1c170-176">[California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (Preview)</span></span>
3. [<span data-ttu-id="1c170-177">云安全联盟（CSA）云控制矩阵（CCM）3.0。1</span><span class="sxs-lookup"><span data-stu-id="1c170-177">Cloud Security Alliance (CSA) Cloud Controls Matrix (CCM) 3.0.1</span></span>](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [<span data-ttu-id="1c170-178">欧洲联合 GDPR</span><span class="sxs-lookup"><span data-stu-id="1c170-178">European Union GDPR</span></span>](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [<span data-ttu-id="1c170-179">联邦金融机构检查委员会（FFIEC）信息安全手册</span><span class="sxs-lookup"><span data-stu-id="1c170-179">Federal Financial Institutions Examination Council (FFIEC) Information Security Booklet</span></span>](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [<span data-ttu-id="1c170-180">FedRAMP 中等</span><span class="sxs-lookup"><span data-stu-id="1c170-180">FedRAMP Moderate</span></span>](https://go.microsoft.com/fwlink/?linkid=2108869)
7. <span data-ttu-id="1c170-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / 高[科技](https://go.microsoft.com/fwlink/?linkid=2109079)</span><span class="sxs-lookup"><span data-stu-id="1c170-181">[HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078) / [HITECH](https://go.microsoft.com/fwlink/?linkid=2109079)</span></span>
8. <span data-ttu-id="1c170-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [澳大利亚政府版 ISM](https://go.microsoft.com/fwlink/?linkid=2113024) （预览）</span><span class="sxs-lookup"><span data-stu-id="1c170-182">[IRAP](https://go.microsoft.com/fwlink/?linkid=2113709) / [Australian Government ISM](https://go.microsoft.com/fwlink/?linkid=2113024) (Preview)</span></span>
9. [<span data-ttu-id="1c170-183">ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="1c170-183">ISO 27001:2013</span></span>](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [<span data-ttu-id="1c170-184">ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="1c170-184">ISO 27018:2014</span></span>](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [<span data-ttu-id="1c170-185">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="1c170-185">ISO 27701:2019</span></span>](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [<span data-ttu-id="1c170-186">Microsoft 365 数据保护基准</span><span class="sxs-lookup"><span data-stu-id="1c170-186">Microsoft 365 Data Protection Baseline</span></span>](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [<span data-ttu-id="1c170-187">NIST 800-53 修订版4</span><span class="sxs-lookup"><span data-stu-id="1c170-187">NIST 800-53 Rev. 4</span></span>](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [<span data-ttu-id="1c170-188">NIST 800-171</span><span class="sxs-lookup"><span data-stu-id="1c170-188">NIST 800-171</span></span>](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [<span data-ttu-id="1c170-189">NIST Cybersecurity Framework （CSF）</span><span class="sxs-lookup"><span data-stu-id="1c170-189">NIST Cybersecurity Framework (CSF)</span></span>](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [<span data-ttu-id="1c170-190">SOC 1</span><span class="sxs-lookup"><span data-stu-id="1c170-190">SOC 1</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [<span data-ttu-id="1c170-191">SOC 2</span><span class="sxs-lookup"><span data-stu-id="1c170-191">SOC 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2115184)

> [!NOTE]
> <span data-ttu-id="1c170-192">在公共预览过程中，转到合规性管理器以创建和管理模板。</span><span class="sxs-lookup"><span data-stu-id="1c170-192">During public preview, go to Compliance Manager to create and manage your templates.</span></span>

### <a name="groups"></a><span data-ttu-id="1c170-193">组</span><span class="sxs-lookup"><span data-stu-id="1c170-193">Groups</span></span>

<span data-ttu-id="1c170-194">组允许您按符合您的逻辑方式组织评估。</span><span class="sxs-lookup"><span data-stu-id="1c170-194">Groups allow you to organize assessments in a way that is logical to you.</span></span> <span data-ttu-id="1c170-195">例如，您可以选择按年、合规性标准、服务、组织内的团队或其他方式对评估进行分组。</span><span class="sxs-lookup"><span data-stu-id="1c170-195">For example, you may choose to group assessments by year, compliance standard, service, teams within your organization, or some other way.</span></span>

<span data-ttu-id="1c170-196">当同一个组中的两个不同评估共享客户管理的操作时，一个评估中的操作的实施详细信息、测试和状态自动同步到组中任何其他评估中的相同操作。</span><span class="sxs-lookup"><span data-stu-id="1c170-196">When two different assessments in the same group share customer-managed actions, the completion of implementation details, testing, and status for the action in one assessment automatically synchronizes to the same action in any other assessment in the group.</span></span> <span data-ttu-id="1c170-197">这将统一分配给整个组的已分配改进操作，并减少重复工作。</span><span class="sxs-lookup"><span data-stu-id="1c170-197">This unifies the assigned improvement actions across the group and reduces duplicating work.</span></span>

<span data-ttu-id="1c170-198">了解如何[在合规性管理器中创建组](working-with-compliance-manager.md#groups)。</span><span class="sxs-lookup"><span data-stu-id="1c170-198">Learn how to [create groups in Compliance Manager](working-with-compliance-manager.md#groups).</span></span> <span data-ttu-id="1c170-199">创建组后，您可以[筛选合规性分数仪表板](compliance-score-setup.md#filtering-your-dashboard-view)，以查看一个或多个组的分数。</span><span class="sxs-lookup"><span data-stu-id="1c170-199">Once you create groups, you can [filter you Compliance Score dashboard](compliance-score-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

## <a name="next-step-begin-setup"></a><span data-ttu-id="1c170-200">下一步：开始安装</span><span class="sxs-lookup"><span data-stu-id="1c170-200">Next step: begin setup</span></span>

<span data-ttu-id="1c170-201">了解如何在[合规性分数设置](compliance-score-setup.md)中登录、设置权限以及配置更新和仪表板视图。</span><span class="sxs-lookup"><span data-stu-id="1c170-201">Learn how to sign in, set up permissions, and configure updates and dashboard views at [Compliance Score setup](compliance-score-setup.md).</span></span>
