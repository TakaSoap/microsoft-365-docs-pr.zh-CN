---
title: 使用合规性管理器管理改进操作
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: 了解如何使用合规性分数和合规性管理器改进个人数据保护级别。
ms.openlocfilehash: b5a112b7614de23af8540346e26dac3b7a4fa1c9
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333476"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="6943c-103">使用合规性管理器管理改进操作</span><span class="sxs-lookup"><span data-stu-id="6943c-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="6943c-104">Microsoft 合规性管理器可帮助您管理与数据隐私法规相关的改进，如欧盟 [通用数据保护法规 (GDPR) ](../compliance/gdpr.md)、 [加利福尼亚州消费者保护法 CCPA) ](../compliance/ccpa-faq.md)、HIPAA-高科技 (法案) LGPD (。</span><span class="sxs-lookup"><span data-stu-id="6943c-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="6943c-105">本文提供了有关使用此工具进行数据保密的指南。</span><span class="sxs-lookup"><span data-stu-id="6943c-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="6943c-106">来自合规性管理器的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="6943c-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="6943c-107">根据您的法规环境评估和验证客户控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="6943c-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="6943c-108">这些服务受 [在线服务条款](https://go.microsoft.com/fwlink/?linkid=2108910)中的条款和条件的制约。</span><span class="sxs-lookup"><span data-stu-id="6943c-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="6943c-109">另请参阅 [适用于安全性和合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span><span class="sxs-lookup"><span data-stu-id="6943c-109">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="6943c-110">合规性管理器入门</span><span class="sxs-lookup"><span data-stu-id="6943c-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="6943c-111">什么是合规性管理器</span><span class="sxs-lookup"><span data-stu-id="6943c-111">What is Compliance Manager</span></span>

<span data-ttu-id="6943c-112">[合规性管理器](../compliance/compliance-manager.md) 是 microsoft 365 合规性中心中基于工作流的风险评估工具，用于管理与 Microsoft 云服务相关的法规遵从性活动。</span><span class="sxs-lookup"><span data-stu-id="6943c-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="6943c-113">作为 Microsoft 365 或 Azure Active Directory (Azure AD) 订阅的一部分，合规性管理器可帮助您管理 Microsoft 云服务的共享职责模型中的法规遵从性。</span><span class="sxs-lookup"><span data-stu-id="6943c-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="6943c-114">**准备好使用评估**</span><span class="sxs-lookup"><span data-stu-id="6943c-114">**Ready to use assessments**</span></span>

<span data-ttu-id="6943c-115">合规性管理器提供了预构建的模板，用于建立与与数据隐私相关的法规（如 GDPR 和 HIPAA/高科技）相适应的 [评估](../compliance/compliance-manager-assessments.md) 。</span><span class="sxs-lookup"><span data-stu-id="6943c-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="6943c-116">这些模板具有内置的控件映射，可帮助您采取改进措施来满足该规章的要求。</span><span class="sxs-lookup"><span data-stu-id="6943c-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="6943c-117">每个评估提供有关特定于目标服务的每项规章调用的控件信息，由您管理和控制 Microsoft 管理的控件来细分。</span><span class="sxs-lookup"><span data-stu-id="6943c-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="6943c-118">使用预建的模板可帮助您快速开始使用风险评估。</span><span class="sxs-lookup"><span data-stu-id="6943c-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="6943c-119">随着您在使用合规性管理器方面更加熟练，可以通过添加自己的控件和改进操作来自定义预建的模板，也可以创建自己的自定义评估以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="6943c-119">As you become more proficient in using Compliance Manger, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="6943c-120">查看合规性管理器提供 [的评估模板的完整列表](../compliance/compliance-manager-templates-list.md) 。</span><span class="sxs-lookup"><span data-stu-id="6943c-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="6943c-121">**实时合规性分数**</span><span class="sxs-lookup"><span data-stu-id="6943c-121">**Real-time compliance score**</span></span>

<span data-ttu-id="6943c-122">合规性管理器还提供了合规性分数，用于衡量在控件中完成建议的改进操作的进度。</span><span class="sxs-lookup"><span data-stu-id="6943c-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="6943c-123">您可以使用此分数帮助监视进度，并根据其可能降低风险的可能性对操作进行排序。</span><span class="sxs-lookup"><span data-stu-id="6943c-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="6943c-124">使用合规性管理器快速入门指南</span><span class="sxs-lookup"><span data-stu-id="6943c-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="6943c-125">[合规性管理器快速入门](../compliance/compliance-manager-quickstart.md)指南提供了渐变步骤和指向关键资源的链接，可帮助您使用合规性管理器：</span><span class="sxs-lookup"><span data-stu-id="6943c-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="6943c-126">首次访问：熟悉合规性管理器</span><span class="sxs-lookup"><span data-stu-id="6943c-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="6943c-127">使用合规性管理器仪表板</span><span class="sxs-lookup"><span data-stu-id="6943c-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="6943c-128">了解合规性分数</span><span class="sxs-lookup"><span data-stu-id="6943c-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="6943c-129">了解改进操作</span><span class="sxs-lookup"><span data-stu-id="6943c-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="6943c-130">了解评估和模板</span><span class="sxs-lookup"><span data-stu-id="6943c-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="6943c-131">斜向向上刀：配置合规性管理器以管理合规性活动</span><span class="sxs-lookup"><span data-stu-id="6943c-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="6943c-132">构建和管理您的首个评估</span><span class="sxs-lookup"><span data-stu-id="6943c-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="6943c-133">执行实施和测试有关改进操作的工作以完成评估中的控件</span><span class="sxs-lookup"><span data-stu-id="6943c-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="6943c-134">了解不同操作对合规性分数有何影响</span><span class="sxs-lookup"><span data-stu-id="6943c-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="6943c-135">向上扩展：使用高级功能满足你的自定义需求</span><span class="sxs-lookup"><span data-stu-id="6943c-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="6943c-136">创建自定义评估以跟踪非 Microsoft 365 产品</span><span class="sxs-lookup"><span data-stu-id="6943c-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="6943c-137">修改现有模板以添加或删除控件</span><span class="sxs-lookup"><span data-stu-id="6943c-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="6943c-138">设置对改进操作的自动测试</span><span class="sxs-lookup"><span data-stu-id="6943c-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="6943c-139">如何计算合规性分数</span><span class="sxs-lookup"><span data-stu-id="6943c-139">How your compliance score is calculated</span></span>

<span data-ttu-id="6943c-140">您的合规性分数是基于 Microsoft 和客户托管的控制实施的组合计算的。</span><span class="sxs-lookup"><span data-stu-id="6943c-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="6943c-141">有关详细说明，请参阅 [合规性分数计算](../compliance/compliance-score-calculation.md) 。</span><span class="sxs-lookup"><span data-stu-id="6943c-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="6943c-142">根据控件是强制性的还是自由的，以及是否为预防性、侦探或纠正措施，为控件分配分数值。</span><span class="sxs-lookup"><span data-stu-id="6943c-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="6943c-143">这些共同体现了其相对于其他控件的实现风险。</span><span class="sxs-lookup"><span data-stu-id="6943c-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="6943c-144">如合规性分数计算文章中所示，预防性控制获得比侦探和纠正措施更高的分数，强制性控制措施比随机控制获得更高的分数。</span><span class="sxs-lookup"><span data-stu-id="6943c-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="6943c-145">合规性分数管理 UI 不会列出这些参数，也不能提供对其进行筛选的功能。</span><span class="sxs-lookup"><span data-stu-id="6943c-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="6943c-146">但是，如果从合规性管理器下载关联的模板，则生成的数据集将为大多数管理法规列出这些参数。</span><span class="sxs-lookup"><span data-stu-id="6943c-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="6943c-147">对于技术控制，合规性管理器会在成功实现并测试操作后自动更新改进操作得分。</span><span class="sxs-lookup"><span data-stu-id="6943c-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="6943c-148">其他非技术性控制操作 &mdash; （如可操作或与文档相关的操作） &mdash; 需要手动记录，然后再按磅数计算到您的成绩。</span><span class="sxs-lookup"><span data-stu-id="6943c-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="6943c-149">您还需要为其他目的实施某些改进操作，例如， &mdash; 使用保留标签作为数据隐私法规遵从性之外的原因 &mdash; ，这样您就可以获得使用此类功能的信用，即使它用于其他用途，也不是有意的合规性操作的一部分。</span><span class="sxs-lookup"><span data-stu-id="6943c-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="6943c-150">应将合规性分数视为跟踪广泛规模改进的相对度量。</span><span class="sxs-lookup"><span data-stu-id="6943c-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="6943c-151">您不应争取一个理想的分数。</span><span class="sxs-lookup"><span data-stu-id="6943c-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="6943c-152">其他指南</span><span class="sxs-lookup"><span data-stu-id="6943c-152">Additional guidance</span></span>

<span data-ttu-id="6943c-153">下面是使用合规性管理器帮助您实现数据隐私法规遵从性的一些重要提示：</span><span class="sxs-lookup"><span data-stu-id="6943c-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="6943c-154">每个数据隐私法规都结合了技术控制、文档规范以及操作、过程和报告要求。</span><span class="sxs-lookup"><span data-stu-id="6943c-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="6943c-155">所有这些操作都显示在改进操作中。</span><span class="sxs-lookup"><span data-stu-id="6943c-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="6943c-156">若要将改进操作视图集中到您感兴趣的领域，可以在合规性管理器管理员的 " **解决方案** " 选项卡中按操作类型进行筛选。了解有关 [筛选合规性管理器仪表板视图](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6943c-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="6943c-157">应将合规性管理器中标识的改进操作的相对重要性和优先级视为广泛风险评审的一部分以及已确定组织需要管理的数据隐私风险。</span><span class="sxs-lookup"><span data-stu-id="6943c-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="6943c-158">即使选择了跨多个法规要求的改进操作聚合，如果选择了 GDPR、LGPD、CCPA 和 HIPAA-高科技的法规评估模板，例如，合规性管理器中将列出几乎400的改进操作。</span><span class="sxs-lookup"><span data-stu-id="6943c-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="6943c-159">若要更好地解决此较长的列表，请使用改进操作筛选器将结果集减少为更易于管理的列表。</span><span class="sxs-lookup"><span data-stu-id="6943c-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="6943c-160">"类别" 筛选器提供了一种通过逻辑分组来筛选改进操作的方法，此整体解决方案中的跟踪、阻止、保护、保留和调查文章与对应。</span><span class="sxs-lookup"><span data-stu-id="6943c-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="6943c-161">改进操作中列出的某些控件可能更直接绑定到特定的规章文章，而其他控件可能更直接与法规精神关联，而多次只是建议的活动或最佳做法。</span><span class="sxs-lookup"><span data-stu-id="6943c-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>