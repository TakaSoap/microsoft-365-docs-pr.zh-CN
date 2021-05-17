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
- m365solution-scenario
ms.custom: ''
description: 了解如何使用合规性分数和合规性管理器提高对个人数据的保护级别。
ms.openlocfilehash: 87131ea65661e8285fd7c3b36a87c79b618348d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918566"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="8268c-103">使用合规性管理器管理改进操作</span><span class="sxs-lookup"><span data-stu-id="8268c-103">Use Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="8268c-104">Microsoft 合规性管理器可帮助你管理与数据隐私法规相关的改进，例如欧盟一般数据保护条例 [ (GDPR) 、 ](/compliance/regulatory/gdpr)加州消费者保护法案 [CCPA ](/compliance/regulatory/ccpa-faq)) 、HIPAA-HITECH (美国医疗保健隐私法案) 和巴西数据保护法案 (LGPD) 。</span><span class="sxs-lookup"><span data-stu-id="8268c-104">Microsoft Compliance Manager can help you manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](/compliance/regulatory/gdpr), [California Consumer Protection Act CCPA)](/compliance/regulatory/ccpa-faq), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="8268c-105">本文提供有关出于数据隐私目的使用此工具的指南。</span><span class="sxs-lookup"><span data-stu-id="8268c-105">This article provides guidance on the use of this tool for data privacy purposes.</span></span>

>[!Note]
><span data-ttu-id="8268c-106">来自合规性管理器的建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="8268c-106">Recommendations from Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="8268c-107">由你根据法规环境评估和验证客户控制措施的有效性。</span><span class="sxs-lookup"><span data-stu-id="8268c-107">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="8268c-108">这些服务受联机服务条款中的 [条款和条件限制](https://go.microsoft.com/fwlink/?linkid=2108910)。</span><span class="sxs-lookup"><span data-stu-id="8268c-108">These services are subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="8268c-109">另请参阅[Microsoft 365安全性和合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span><span class="sxs-lookup"><span data-stu-id="8268c-109">See also [Microsoft 365 licensing guidance for security and compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)</span></span>
>

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="8268c-110">合规性管理器入门</span><span class="sxs-lookup"><span data-stu-id="8268c-110">Getting started with Compliance Manager</span></span>

#### <a name="what-is-compliance-manager"></a><span data-ttu-id="8268c-111">什么是合规性管理器</span><span class="sxs-lookup"><span data-stu-id="8268c-111">What is Compliance Manager</span></span>

<span data-ttu-id="8268c-112">[合规性管理器](../compliance/compliance-manager.md)是 Microsoft 365 中心中基于工作流的风险评估工具，用于管理与 Microsoft 云服务相关的法规合规性活动。</span><span class="sxs-lookup"><span data-stu-id="8268c-112">[Compliance Manager](../compliance/compliance-manager.md) is a workflow-based risk assessment tool in the Microsoft 365 compliance center for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="8268c-113">作为 Azure AD Microsoft 365 或 Azure Active Directory (订阅的一) ，合规性管理器可帮助你在 Microsoft 云服务的共享责任模型中管理法规合规性。</span><span class="sxs-lookup"><span data-stu-id="8268c-113">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="8268c-114">**准备使用评估**</span><span class="sxs-lookup"><span data-stu-id="8268c-114">**Ready to use assessments**</span></span>

<span data-ttu-id="8268c-115">合规性管理器提供预建模板，用于构建[](../compliance/compliance-manager-assessments.md)符合数据隐私相关法规（如 GDPR 和 HIPAA/HITECH）的评估。</span><span class="sxs-lookup"><span data-stu-id="8268c-115">Compliance Manager provides pre-built templates for [building assessments](../compliance/compliance-manager-assessments.md) that are aligned to data privacy-related regulations, such as GDPR and HIPAA/HITECH.</span></span> <span data-ttu-id="8268c-116">这些模板具有内置的控制映射，可帮助你采取改进措施，满足法规的要求。</span><span class="sxs-lookup"><span data-stu-id="8268c-116">The templates have built-in control mapping to help you take improvement actions for meeting the regulation's requirements.</span></span> <span data-ttu-id="8268c-117">每项评估都提供有关特定于目标服务的每个法规调用的控制措施的信息，这些信息由你管理的控制措施和 Microsoft 管理的控制措施细分。</span><span class="sxs-lookup"><span data-stu-id="8268c-117">Each assessment provides information about the controls each regulation calls for specific to the target service, broken out by controls you manage and controls Microsoft manages.</span></span> 

<span data-ttu-id="8268c-118">使用预建模板可帮助你快速开始使用风险评估。</span><span class="sxs-lookup"><span data-stu-id="8268c-118">Using a pre-built template helps you quickly get started with risk assessments.</span></span> <span data-ttu-id="8268c-119">随着你更加熟练地使用合规性管理器，可以通过添加自己的控制措施和改进操作来自定义预建模板，也可以创建自己的自定义评估以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="8268c-119">As you become more proficient in using Compliance Manager, you can customize a pre-built template by adding your own controls and improvement actions, or you can create your own custom assessments to suit your organization's needs.</span></span>

<span data-ttu-id="8268c-120">查看 [合规性管理器提供的评估](../compliance/compliance-manager-templates-list.md) 模板的完整列表。</span><span class="sxs-lookup"><span data-stu-id="8268c-120">View the [full list of assessment templates](../compliance/compliance-manager-templates-list.md) provided by Compliance Manager.</span></span>

<span data-ttu-id="8268c-121">**实时合规性分数**</span><span class="sxs-lookup"><span data-stu-id="8268c-121">**Real-time compliance score**</span></span>

<span data-ttu-id="8268c-122">合规性管理器还会提供合规性分数，用于衡量在控制措施中完成建议改进操作的进度。</span><span class="sxs-lookup"><span data-stu-id="8268c-122">Compliance Manager also provides you with a compliance score that measures your progress in completing recommended improvement actions within controls.</span></span> <span data-ttu-id="8268c-123">可以使用此分数来帮助监视进度，并基于操作可降低风险的可能性确定操作优先级。</span><span class="sxs-lookup"><span data-stu-id="8268c-123">You can use this score to help monitor your progress and prioritize actions based on their potential to reduce risk.</span></span>

#### <a name="use-the-compliance-manager-quickstart-guide"></a><span data-ttu-id="8268c-124">使用合规性管理器快速入门指南</span><span class="sxs-lookup"><span data-stu-id="8268c-124">Use the Compliance Manager quickstart guide</span></span>

<span data-ttu-id="8268c-125">合规性 [管理器快速入门](../compliance/compliance-manager-quickstart.md) 指南提供了关键资源的指导步骤和链接，以帮助您使用合规性管理器：</span><span class="sxs-lookup"><span data-stu-id="8268c-125">The [Compliance Manager quickstart](../compliance/compliance-manager-quickstart.md) guide provides graduated steps and links to key resources to help you work with Compliance Manager:</span></span>

- [<span data-ttu-id="8268c-126">首次访问：熟悉合规性管理器</span><span class="sxs-lookup"><span data-stu-id="8268c-126">First visit: get familiar with Compliance Manager</span></span>](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - <span data-ttu-id="8268c-127">使用合规性管理器仪表板</span><span class="sxs-lookup"><span data-stu-id="8268c-127">Working with your Compliance Manager dashboard</span></span>
    - <span data-ttu-id="8268c-128">了解合规性分数</span><span class="sxs-lookup"><span data-stu-id="8268c-128">Understanding your compliance score</span></span>
    - <span data-ttu-id="8268c-129">了解改进操作</span><span class="sxs-lookup"><span data-stu-id="8268c-129">Learning about improvement actions</span></span>
    - <span data-ttu-id="8268c-130">了解评估和模板</span><span class="sxs-lookup"><span data-stu-id="8268c-130">Understanding assessments and templates</span></span>
- [<span data-ttu-id="8268c-131">加速：配置合规性管理器以管理合规性活动</span><span class="sxs-lookup"><span data-stu-id="8268c-131">Ramping up: configure Compliance Manager to manage your compliance activities</span></span>](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - <span data-ttu-id="8268c-132">生成和管理你的第一个评估</span><span class="sxs-lookup"><span data-stu-id="8268c-132">Building and managing your first assessment</span></span>
    - <span data-ttu-id="8268c-133">执行实施和测试工作以改进操作以完成评估中的控制措施</span><span class="sxs-lookup"><span data-stu-id="8268c-133">Performing implementation and testing work on improvement actions to complete controls in your assessments</span></span>
    - <span data-ttu-id="8268c-134">了解不同操作对合规性分数的影响</span><span class="sxs-lookup"><span data-stu-id="8268c-134">Understanding how different actions impact your compliance score</span></span>
- [<span data-ttu-id="8268c-135">向上扩展：使用高级功能来满足自定义需求</span><span class="sxs-lookup"><span data-stu-id="8268c-135">Scaling up: use advanced functionality to meet your custom needs</span></span>](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - <span data-ttu-id="8268c-136">创建自定义评估以跟踪非Microsoft 365产品</span><span class="sxs-lookup"><span data-stu-id="8268c-136">Creating your custom assessments to track non-Microsoft 365 products</span></span>
    - <span data-ttu-id="8268c-137">修改现有模板以添加或删除控件</span><span class="sxs-lookup"><span data-stu-id="8268c-137">Modifying existing templates to add or remove controls</span></span>
    - <span data-ttu-id="8268c-138">设置改进操作自动化测试</span><span class="sxs-lookup"><span data-stu-id="8268c-138">Setting up automated testing of improvement actions</span></span>

## <a name="how-your-compliance-score-is-calculated"></a><span data-ttu-id="8268c-139">如何计算合规性分数</span><span class="sxs-lookup"><span data-stu-id="8268c-139">How your compliance score is calculated</span></span>

<span data-ttu-id="8268c-140">合规性分数根据 Microsoft 和客户管理的控件实现的组合进行计算。</span><span class="sxs-lookup"><span data-stu-id="8268c-140">Your compliance score is calculated based on a combination of Microsoft and customer-managed control implementations.</span></span> <span data-ttu-id="8268c-141">有关 [详细说明，请参阅](../compliance/compliance-score-calculation.md) 合规性分数计算。</span><span class="sxs-lookup"><span data-stu-id="8268c-141">See [compliance score calculation](../compliance/compliance-score-calculation.md) for a detailed explanation.</span></span>

<span data-ttu-id="8268c-142">根据控制措施是必需还是随意，以及控制措施是预防型、检测型还是纠正型，为控制措施分配分数值。</span><span class="sxs-lookup"><span data-stu-id="8268c-142">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="8268c-143">这些统一表示未实现它相对于其他控件的风险。</span><span class="sxs-lookup"><span data-stu-id="8268c-143">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="8268c-144">如合规性分数计算文章所介绍，预防性控制措施的分数高于检测分数和纠正分数，强制控制措施的分数高于随意控制措施的分数。</span><span class="sxs-lookup"><span data-stu-id="8268c-144">As presented in the compliance score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>

<span data-ttu-id="8268c-145">合规性分数管理 UI 不会列出这些参数，也不提供按这些参数进行筛选的能力。</span><span class="sxs-lookup"><span data-stu-id="8268c-145">The Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="8268c-146">但是，如果从合规性管理器下载关联的模板，生成的数据集会列出大多数法规的这些参数。</span><span class="sxs-lookup"><span data-stu-id="8268c-146">However, if you download the associated template from  Compliance Manager, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="8268c-147">对于技术控制措施，一旦成功实施和测试了改进行动，合规性管理器就会自动更新改进行动分数。</span><span class="sxs-lookup"><span data-stu-id="8268c-147">For technical controls, Compliance Manager automatically updates the improvement action score once the action has been successfully implemented and tested.</span></span> <span data-ttu-id="8268c-148">其他非技术控制操作（如可操作或与文档相关的操作）需要手动记录为已实现，然后点 &mdash; &mdash; 算在你的分数中。</span><span class="sxs-lookup"><span data-stu-id="8268c-148">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually as implemented before points count toward your score.</span></span>

<span data-ttu-id="8268c-149">你还出于其他目的实施某些改进操作，例如，出于数据隐私法规合规性外的其他原因，使用保留标签，以便即使此功能用于其他目的，并且不是有意的合规性措施的一部分，也会因使用此功能而获得支持。 &mdash; &mdash;</span><span class="sxs-lookup"><span data-stu-id="8268c-149">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="8268c-150">合规性分数应视为跟踪大规模改进的相对度量。</span><span class="sxs-lookup"><span data-stu-id="8268c-150">Your compliance score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="8268c-151">你不应获得完美分数。</span><span class="sxs-lookup"><span data-stu-id="8268c-151">You should not pursue a perfect score.</span></span>

## <a name="additional-guidance"></a><span data-ttu-id="8268c-152">其他指南</span><span class="sxs-lookup"><span data-stu-id="8268c-152">Additional guidance</span></span>

<span data-ttu-id="8268c-153">以下是有关使用合规性管理器帮助你实现数据隐私法规合规性的一些重要提示：</span><span class="sxs-lookup"><span data-stu-id="8268c-153">Here are a few important tips for using Compliance Manager to help you achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="8268c-154">每个数据隐私法规都组合了技术控制、文档规范以及操作、过程和报告要求。</span><span class="sxs-lookup"><span data-stu-id="8268c-154">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="8268c-155">所有这些操作都显示在改进操作中。</span><span class="sxs-lookup"><span data-stu-id="8268c-155">All of these show up in the improvement actions.</span></span>

- <span data-ttu-id="8268c-156">若要将改进操作视图集中在你感兴趣的领域，可以在合规性管理器管理员的"解决方案"选项卡中按操作类型进行筛选。详细了解如何[筛选合规性管理器仪表板视图](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)。</span><span class="sxs-lookup"><span data-stu-id="8268c-156">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Manager admin. Learn more about [filtering your Compliance Manager dashboard view](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).</span></span>

- <span data-ttu-id="8268c-157">合规性管理器中确定的改进措施的相对重要性和优先级应视为更广泛的风险评审的一部分，以及确定组织需要管理的数据隐私风险。</span><span class="sxs-lookup"><span data-stu-id="8268c-157">The relative importance and priority of improvement actions identified in Compliance Manager should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span>

- <span data-ttu-id="8268c-158">即使跨多个法规要求聚合了改进行动，如果选择适用于 GDPR、LGPD、CCPA 和 HIPAA-HITECH 的法规评估模板（例如，合规性管理器中将列出近 400 项改进操作）。</span><span class="sxs-lookup"><span data-stu-id="8268c-158">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Manager.</span></span> <span data-ttu-id="8268c-159">为了更好地应对这一长列表，请使用改进操作筛选器结果集更易于管理的列表。</span><span class="sxs-lookup"><span data-stu-id="8268c-159">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="8268c-160">类别筛选器提供了一种通过逻辑分组来筛选改进操作的方法，此整体解决方案中的跟踪、阻止、保护、保留和调查文章与逻辑分组一致。</span><span class="sxs-lookup"><span data-stu-id="8268c-160">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span>

- <span data-ttu-id="8268c-161">改进操作中列出的某些控制措施可能被视为与特定法规条款更直接关联，而其他控制措施可能更间接地与法规的体现相关联，并且许多时候只是建议的活动或最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8268c-161">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and many times are simply recommended activities or best practices.</span></span>