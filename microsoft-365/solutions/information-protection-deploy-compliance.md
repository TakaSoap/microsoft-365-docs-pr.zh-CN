---
title: 使用合规性分数和合规性管理器管理改进操作
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: 了解如何使用合规性分数和合规性管理器改进个人数据保护级别。
ms.openlocfilehash: d3730f7a91876befc05f749497540fbe9abe9641
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126544"
---
# <a name="use-compliance-score-and-compliance-manager-to-manage-improvement-actions"></a><span data-ttu-id="7de8f-103">使用合规性分数和合规性管理器管理改进操作</span><span class="sxs-lookup"><span data-stu-id="7de8f-103">Use Compliance Score and Compliance Manager to manage improvement actions</span></span>

<span data-ttu-id="7de8f-104">Microsoft 合规性分数和合规性管理器可结合使用，以管理与数据隐私法规相关的改进（如欧盟[通用数据保护条例（GDPR）](../compliance/gdpr.md)、[加利福尼亚州消费者保护法 CCPA）](../compliance/ccpa-faq.md)、HIPAA-高科技（美国卫生保健隐私法案）和巴西数据保护法案（LGPD）。</span><span class="sxs-lookup"><span data-stu-id="7de8f-104">Microsoft Compliance Score and Compliance Manager can be used together to manage improvements related to data privacy regulations such as the European Union [General Data Protection Regulation (GDPR)](../compliance/gdpr.md), [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="7de8f-105">本文提供了有关如何使用这些工具来实现数据保密的指南。</span><span class="sxs-lookup"><span data-stu-id="7de8f-105">This article provides guidance on the use of these tools for data privacy purposes.</span></span>

![管理合规性分数和合规性管理器以管理改进操作](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-grid.png)

>[!Note]
><span data-ttu-id="7de8f-107">合规性管理器中提供的客户操作是建议。</span><span class="sxs-lookup"><span data-stu-id="7de8f-107">The customer actions provided in Compliance Manager are recommendations.</span></span> <span data-ttu-id="7de8f-108">在实施之前，您需要评估这些建议在法规环境中的有效性。</span><span class="sxs-lookup"><span data-stu-id="7de8f-108">It is up to you to evaluate the effectiveness of these recommendations in your regulatory environments prior to implementation.</span></span> <span data-ttu-id="7de8f-109">合规性管理器建议不应解释为合规性保证。</span><span class="sxs-lookup"><span data-stu-id="7de8f-109">Compliance Manager recommendations should not be interpreted as a guarantee of compliance.</span></span>
>

## <a name="planned-updates-for-compliance-score-and-compliance-manager"></a><span data-ttu-id="7de8f-110">针对合规性分数和合规性管理器的计划更新</span><span class="sxs-lookup"><span data-stu-id="7de8f-110">Planned updates for Compliance Score and Compliance Manager</span></span>

<span data-ttu-id="7de8f-111">[合规性分数](../compliance/compliance-score.md)（当前处于预览阶段）需要在[合规性管理器](../compliance/compliance-manager-overview.md)中添加法规的目标评估（如 GDPR）。</span><span class="sxs-lookup"><span data-stu-id="7de8f-111">[Compliance Score](../compliance/compliance-score.md) (currently in preview) requires adding your target assessments for a regulation (such as GDPR) from the [Compliance Manager](../compliance/compliance-manager-overview.md).</span></span> <span data-ttu-id="7de8f-112">在将来的版本中，合规性管理器中的很多功能将合并到统一的合规性分数体验中，从而减少了对多个工具的需求。</span><span class="sxs-lookup"><span data-stu-id="7de8f-112">In a future release, much of the functionality in Compliance Manager will be merged into a unified Compliance Score experience, reducing the need for multiple tools.</span></span>

<span data-ttu-id="7de8f-113">以下是你的订阅的工具，它需要你登录：</span><span class="sxs-lookup"><span data-stu-id="7de8f-113">Here are the tools for your subscription, which require you to sign-in:</span></span>

- [<span data-ttu-id="7de8f-114">Microsoft 合规性管理中心中的合规性分数</span><span class="sxs-lookup"><span data-stu-id="7de8f-114">Compliance Score in the Microsoft Compliance admin center</span></span>](https://compliance.microsoft.com/compliancescore)
- [<span data-ttu-id="7de8f-115">Microsoft Services 信任门户中的合规性管理器</span><span class="sxs-lookup"><span data-stu-id="7de8f-115">Compliance Manager in the Microsoft Services Trust Portal</span></span>](https://servicetrust.microsoft.com/ComplianceManager/V3)

## <a name="getting-started-with-compliance-manager"></a><span data-ttu-id="7de8f-116">合规性管理器入门</span><span class="sxs-lookup"><span data-stu-id="7de8f-116">Getting started with Compliance Manager</span></span> 

<span data-ttu-id="7de8f-117">[合规性管理器](../compliance/working-with-compliance-manager.md)（当前处于预览阶段）是 Microsoft 服务信任门户中的基于工作流的风险评估工具，用于管理与 Microsoft 云服务相关的法规遵从性活动。</span><span class="sxs-lookup"><span data-stu-id="7de8f-117">[Compliance Manager](../compliance/working-with-compliance-manager.md) (currently in preview) is a free workflow-based risk assessment tool in the Microsoft Service Trust Portal for managing regulatory compliance activities related to Microsoft cloud services.</span></span> <span data-ttu-id="7de8f-118">作为 Microsoft 365 或 Azure Active Directory （Azure AD）订阅的一部分，合规性管理器可帮助您管理 Microsoft 云服务的共享职责模型中的法规遵从性。</span><span class="sxs-lookup"><span data-stu-id="7de8f-118">As part of your Microsoft 365 or Azure Active Directory (Azure AD) subscription, Compliance Manager helps you manage regulatory compliance within the shared responsibility model for Microsoft cloud services.</span></span>

<span data-ttu-id="7de8f-119">虽然您可以查看您的总体合规性分数并在合规中心的**合规性分数**页面中执行许多其他功能，但您需要通过服务信任门户使用合规性管理器，以便先为您的数据隐私管理法规配置评估。</span><span class="sxs-lookup"><span data-stu-id="7de8f-119">While you can view your overall compliance score and perform a number of other functions in the Compliance center's **Compliance Score** page, you need to use Compliance Manager through the Services Trust Portal to first configure assessments for your data privacy regulations.</span></span> <span data-ttu-id="7de8f-120">这些评估中的数据将显示在合规性分数中，以供进一步查看和筛选。</span><span class="sxs-lookup"><span data-stu-id="7de8f-120">Data from these assessments will then show up in Compliance Score for further viewing and filtering.</span></span> 

<span data-ttu-id="7de8f-121">使用合规性管理器界面，您可以选择一个或多个与数据隐私相关的规章模板，并对其进行分组以评估和跟踪整个集所需的改进操作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-121">Using the Compliance Manager interface, you can select one or more data privacy-related regulation templates and group them to assess and track required improvement actions across the set.</span></span> <span data-ttu-id="7de8f-122">您还可以查看有关特定于目标服务的控制措施的信息，由 Microsoft vs 和客户托管的控件分隔。</span><span class="sxs-lookup"><span data-stu-id="7de8f-122">You can also view information about the controls each regulation calls for specific to the target service, separated by Microsoft vs. customer-managed controls.</span></span>

<span data-ttu-id="7de8f-123">在此处选择的评估和改进状态也会在 Microsoft 合规性中心中显示，以强调合规性管理器中的初始设置的重要性。</span><span class="sxs-lookup"><span data-stu-id="7de8f-123">Assessments and improvement status selected here also appear in Compliance Score in the Microsoft Compliance Center, which emphasize the importance of your initial setup in Compliance Manager.</span></span> <span data-ttu-id="7de8f-124">此图中显示了这些关系。</span><span class="sxs-lookup"><span data-stu-id="7de8f-124">These relationships are shown in this figure.</span></span>
 
![Microsoft 合规性中心中合规性分数的关系](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-ui.png)

<span data-ttu-id="7de8f-126">下面是帮助您入门的关键步骤。</span><span class="sxs-lookup"><span data-stu-id="7de8f-126">Here are the key steps to help you get started.</span></span>

### <a name="1-assessment-templates"></a><span data-ttu-id="7de8f-127">1. 评估模板</span><span class="sxs-lookup"><span data-stu-id="7de8f-127">1. Assessment templates</span></span>

<span data-ttu-id="7de8f-128">从合规性管理器中，第一步是添加特定于感兴趣的数据隐私规章的评估，并将其包含在定义的 "数据隐私法规" 组中。</span><span class="sxs-lookup"><span data-stu-id="7de8f-128">From the Compliance Manager, the first step is to add assessments specific to the data privacy regulations of interest and include them in a defined "Data Privacy Regulations" group.</span></span>

<span data-ttu-id="7de8f-129">[组](../compliance/working-with-compliance-manager.md#groups)是允许您组织评估的容器，并在评估之间共享具有相同或相关的客户托管控件的常见信息和工作流任务。</span><span class="sxs-lookup"><span data-stu-id="7de8f-129">[Groups](../compliance/working-with-compliance-manager.md#groups) are containers that allow you to organize Assessments and share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="7de8f-130">当同一个组中的两个不同评估共享客户托管控件时，该控件的实现详细信息、测试和状态的完成将自动同步到组中任何其他评估中的相同控件。</span><span class="sxs-lookup"><span data-stu-id="7de8f-130">When two different Assessments in the same group share customer-managed control, the completion of implementation details, testing, and status for the control automatically synchronize to the same control in any other Assessment in the Group.</span></span> <span data-ttu-id="7de8f-131">这将统一分配给组中每个控件的已分配操作项并减少重复工作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-131">This unifies the assigned Action Items for each control across the group and reduces duplicating work.</span></span> 

<span data-ttu-id="7de8f-132">您还可以选择使用组进行组织。</span><span class="sxs-lookup"><span data-stu-id="7de8f-132">You can also choose to use groups to organize.</span></span> <span data-ttu-id="7de8f-133">按年、区域、合规性标准或其他分组进行评估，以帮助组织合规性工作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-133">Assessments by year, area, compliance standard, or other groupings to help organize your compliance work.</span></span>


### <a name="2-action-items"></a><span data-ttu-id="7de8f-134">2. 操作项</span><span class="sxs-lookup"><span data-stu-id="7de8f-134">2. Action items</span></span>

<span data-ttu-id="7de8f-135">添加评估后，可以查看特定于每个组或单个规章的操作项：</span><span class="sxs-lookup"><span data-stu-id="7de8f-135">Once the assessments have been added, you can view Action Items specific to each group or individual regulation:</span></span>

- <span data-ttu-id="7de8f-136">**改进操作列表。**</span><span class="sxs-lookup"><span data-stu-id="7de8f-136">**Improvement action list.**</span></span> <span data-ttu-id="7de8f-137">导航到 "操作项" 列表，并查看与组中包括的法规关联的改进操作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-137">Navigate to the Action Items list and view the improvement actions associated across the regulations included in the group.</span></span> <span data-ttu-id="7de8f-138">许多操作都涉及管理法规，因此单个列表项可能代表多项管理法规。</span><span class="sxs-lookup"><span data-stu-id="7de8f-138">Many actions span regulations so a single list item may represent multiple regulations.</span></span> 
 
- <span data-ttu-id="7de8f-139">**改进操作筛选。**</span><span class="sxs-lookup"><span data-stu-id="7de8f-139">**Improvement action filtering.**</span></span> <span data-ttu-id="7de8f-140">对于许多数据隐私法规和管理法规而言，改进操作列表可能非常大，因此请考虑使用筛选器下拉列表筛选列表。</span><span class="sxs-lookup"><span data-stu-id="7de8f-140">For many data privacy regulations and groups of regulations, the list of improvement actions can be quite large, so consider filtering the list using the filter drop down.</span></span> <span data-ttu-id="7de8f-141">例如，如果选择 "技术控件"，则该列表将减少为组织中具有技术实施的那些操作，因为许多操作与业务的各个方面（也在合规性管理器中进行了记录）的管理操作有关。</span><span class="sxs-lookup"><span data-stu-id="7de8f-141">For example, if you select "technical controls", the list will be reduced to just those which have a technical implementation in the organization, as many of the actions are related to administrative operations in various aspects of the business which are also documented in Compliance Manager.</span></span> <span data-ttu-id="7de8f-142">在本文中，我们将重点介绍技术控件，因此建议采用此筛选方法。</span><span class="sxs-lookup"><span data-stu-id="7de8f-142">In this article, we will focus on technical controls, so this filtering approach is recommended.</span></span>
 
- <span data-ttu-id="7de8f-143">**其他信息和审查。**</span><span class="sxs-lookup"><span data-stu-id="7de8f-143">**Additional information and review.**</span></span> <span data-ttu-id="7de8f-144">对于每个操作，您可以单击链接以**阅读更多**，这会告诉您有关建议的活动或**审阅**的详细信息，该窗体允许您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7de8f-144">For each action, you can click on the link to **Read More**, which tells you more about the recommended activity, or **Review**, which opens a form allowing you to do the following:</span></span>
 
   - <span data-ttu-id="7de8f-145">将操作分配给组织中的某个人以管理</span><span class="sxs-lookup"><span data-stu-id="7de8f-145">Assign the action to a someone in your organization to manage</span></span>
   - <span data-ttu-id="7de8f-146">管理与解决操作相关的文档</span><span class="sxs-lookup"><span data-stu-id="7de8f-146">Manage documents related to addressing the action</span></span>
   - <span data-ttu-id="7de8f-147">指定项目的状态</span><span class="sxs-lookup"><span data-stu-id="7de8f-147">Specify status for the item</span></span>
   - <span data-ttu-id="7de8f-148">指定实现和测试日期</span><span class="sxs-lookup"><span data-stu-id="7de8f-148">Specify implementation and test dates</span></span>
   - <span data-ttu-id="7de8f-149">记录主题操作的其他信息、实现说明和测试计划备注</span><span class="sxs-lookup"><span data-stu-id="7de8f-149">Record additional information, implementation notes, and test plan notes for the subject action</span></span>
  
- <span data-ttu-id="7de8f-150">**非适用项超出范围。**</span><span class="sxs-lookup"><span data-stu-id="7de8f-150">**Non-applicable items as out-of-scope.**</span></span> <span data-ttu-id="7de8f-151">"操作项" 列表中包含的某些改进操作可能不适用于您计划的实现。</span><span class="sxs-lookup"><span data-stu-id="7de8f-151">Some improvement actions included in the Action Items list might not apply to your planned implementation.</span></span> <span data-ttu-id="7de8f-152">您可以指定它们不在合规性管理器的作用域中，并从 "合规性分数" 值的计算中删除该操作及其证据。</span><span class="sxs-lookup"><span data-stu-id="7de8f-152">You can specify that they are out of scope in Compliance Manager and remove the action and its evidence from the calculation of the compliance score value.</span></span> 

<span data-ttu-id="7de8f-153">例如，如果您的组织已选择使用 Microsoft 托管密钥 ""，则建议使用 "客户密钥" 不适用于您的部署。</span><span class="sxs-lookup"><span data-stu-id="7de8f-153">For example, if your organization has elected to use Microsoft Managed Key", a recommendation to Use Customer Key is not applicable to your deployment.</span></span> <span data-ttu-id="7de8f-154">在这种情况下，您的组织会将其标记为 "**不在作用域**中" 适用的规章模板的**控制操作**。</span><span class="sxs-lookup"><span data-stu-id="7de8f-154">In this case, your organization would mark it as **Not in scope** in the **Control Actions** for the applicable regulatory template.</span></span>
 
### <a name="3-controls-info"></a><span data-ttu-id="7de8f-155">3. 控件信息</span><span class="sxs-lookup"><span data-stu-id="7de8f-155">3. Controls info</span></span>

<span data-ttu-id="7de8f-156">对于特定于评估的视图，请查看每个评估组的 "[控件信息](../compliance/compliance-manager-overview.md#controls)"。</span><span class="sxs-lookup"><span data-stu-id="7de8f-156">For an assessment-specific view, view the [Controls Info](../compliance/compliance-manager-overview.md#controls) for each assessment group.</span></span> <span data-ttu-id="7de8f-157">这提供了特定于评估的视图，这与 "操作项" 列表不同，后者提供了特定于技术控件的视图。</span><span class="sxs-lookup"><span data-stu-id="7de8f-157">This provides an assessment-specific view, which is difference than the Action Items list, which provides a technical control-specific view.</span></span>
 
![评估与控制项目的关系](../media/information-protection-deploy-compliance/information-protection-deploy-compliance-control.png)

<span data-ttu-id="7de8f-159">导航到 "**控件信息**" 列表，并查看所述法规的范围内服务的列表。</span><span class="sxs-lookup"><span data-stu-id="7de8f-159">Navigate to the **Controls Info** list and view the list of in-scope services for the regulation in question.</span></span> 
 
<span data-ttu-id="7de8f-160">特定于规章的控制分组列出了由每个服务区域的控制区域提供的操作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-160">Regulation-specific control groupings list the actions provided by control area for each service area.</span></span> <span data-ttu-id="7de8f-161">对于每组操作，合规性管理器都会提供有关操作的详细信息，并可能建议或提供审阅选项以帮助组织选择控制方法。</span><span class="sxs-lookup"><span data-stu-id="7de8f-161">For each set of actions, the Compliance Manager provides more information on the action and may suggest or provide review options to assist the organization in choosing a control approach.</span></span>
 
<span data-ttu-id="7de8f-162">请注意，此接口提供了查看特定于技术操作的详细信息的功能，以及与该控件相关的操作的状态，以及与该操作相关的规章的补充上下文。</span><span class="sxs-lookup"><span data-stu-id="7de8f-162">Note that this interface provides the capability to view details specific to the technical action, together with the status of actions related to the control, and supplemental context about the regulations to which the action is related.</span></span>

### <a name="4-template-download"></a><span data-ttu-id="7de8f-163">4. 模板下载</span><span class="sxs-lookup"><span data-stu-id="7de8f-163">4. Template download</span></span>

<span data-ttu-id="7de8f-164">对于更熟悉基于电子表格的法规分析，另一种方法是使用 "模板" 列表下载每个相应评估的模板。</span><span class="sxs-lookup"><span data-stu-id="7de8f-164">For those more familiar with spreadsheet-based regulatory analysis, another approach is to download the template for each respective assessment using the Templates listing.</span></span> <span data-ttu-id="7de8f-165">下载的模板列出了管理法规以及每个模板的技术控制信息，并且可能更易于特定角色导航/筛选和生成特定于业务的视图。</span><span class="sxs-lookup"><span data-stu-id="7de8f-165">The downloaded templates list both the regulatory as well as technical control information for each template and may be easier for certain roles to navigate/filter and to generate business-specific views.</span></span>
 
<span data-ttu-id="7de8f-166">您还可以使用 "**添加模板**"，基于现有模板为您的组织添加一个新的自定义模板。</span><span class="sxs-lookup"><span data-stu-id="7de8f-166">You can also add a new template customized for your organization based on an existing template, using **Add Template**.</span></span> <span data-ttu-id="7de8f-167">这要求您下载选择的模板（如 HIPAA/高科技）），然后根据您的需要修改它并将其上传回合规性管理器工具，在这种情况下，它将在整个合规性管理器和合规性记分工具集的一部分中推动与其他模板和评估类似的评估和评分。</span><span class="sxs-lookup"><span data-stu-id="7de8f-167">This requires that you download a template of choice (such as HIPAA/HITECH)), then modify it for your purposes and upload back into the Compliance Manager tool, where it will now drive assessments and scoring similar to other templates and assessments as part of the overall Compliance Manager and Compliance Score toolset.</span></span>
 
>[!Tip]
><span data-ttu-id="7de8f-168">如果要处理大量管理法规或重叠的改进操作，请考虑分别下载每个模板并组合数据集，删除不适用于组织的改进操作或控制类型，然后重新上载。</span><span class="sxs-lookup"><span data-stu-id="7de8f-168">if dealing with a large number of regulations or overlapping improvement actions, consider downloading each respective template and combining the data sets, removing improvement actions or control types that do not apply to your organization, and re-uploading.</span></span> <span data-ttu-id="7de8f-169">这可能比导航每个 "控制信息" 部分更容易，并将每个 "" 标记为 "超出范围"。</span><span class="sxs-lookup"><span data-stu-id="7de8f-169">This may be easier than navigating every control info section and marking each as out of scope.</span></span>
>

## <a name="compliance-score"></a><span data-ttu-id="7de8f-170">合规性分数</span><span class="sxs-lookup"><span data-stu-id="7de8f-170">Compliance Score</span></span>

<span data-ttu-id="7de8f-171">在合规性管理器中执行评估和审阅规范之后，你现在可以转到 "[合规性分数](../compliance/compliance-score.md)" 工具并查看分数和切片，并进一步切出数据，包括控制区域。</span><span class="sxs-lookup"><span data-stu-id="7de8f-171">Once the assessments and review specifications are performed in Compliance Manager, you can now go to the [Compliance Score](../compliance/compliance-score.md) tool and review the score and slice and dice the data further, including by control area.</span></span>

<span data-ttu-id="7de8f-172">Microsoft 365 合规性管理中心中的合规性分数工具提供了几种查看和筛选从合规性管理器和各种 Microsoft 365 服务获取的合规性数据的方法。</span><span class="sxs-lookup"><span data-stu-id="7de8f-172">The Compliance Score tool in the Microsoft 365 Compliance admin center provides several approaches to review and filter compliance data obtained from Compliance Manager and various Microsoft 365 services.</span></span> <span data-ttu-id="7de8f-173">在实施各种配置设置并共享带有 Microsoft 安全分数的信号时，将自动更新此工具，以便在两个分数中显示多个改进操作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-173">This tool is automatically updated when various configuration settings are implemented and shares signals with the Microsoft Secure Score so that many improvement actions will show up in both scores.</span></span> 
 
<span data-ttu-id="7de8f-174">合规性分数提供了：</span><span class="sxs-lookup"><span data-stu-id="7de8f-174">The Compliance Score provides:</span></span>

- <span data-ttu-id="7de8f-175">由 Microsoft 和客户托管的控件细分的收集分数</span><span class="sxs-lookup"><span data-stu-id="7de8f-175">A collected score, broken down by Microsoft and customer-managed controls</span></span>
- <span data-ttu-id="7de8f-176">改进操作和完成状态的汇总</span><span class="sxs-lookup"><span data-stu-id="7de8f-176">A rollup of improvement actions and completion status</span></span>
- <span data-ttu-id="7de8f-177">影响你成绩的 Microsoft 365 解决方案的列表</span><span class="sxs-lookup"><span data-stu-id="7de8f-177">A listing of Microsoft 365 solutions impacting your score</span></span>

### <a name="how-the-compliance-score-gets-calculated"></a><span data-ttu-id="7de8f-178">如何计算合规性分数</span><span class="sxs-lookup"><span data-stu-id="7de8f-178">How the compliance score gets calculated</span></span>

<span data-ttu-id="7de8f-179">简言之，分数是基于 Microsoft 和客户托管的控制实施的组合计算的，如[Microsoft 合规性分数计算文章](../compliance/compliance-score-methodology.md)中更详细地介绍。</span><span class="sxs-lookup"><span data-stu-id="7de8f-179">In short, the score is calculated based on a combination of Microsoft and customer-managed control implementations, as explained in more detail in the [Microsoft Compliance Score calculation article](../compliance/compliance-score-methodology.md).</span></span>

<span data-ttu-id="7de8f-180">根据控件是强制性的还是自由的，以及是否为预防性、侦探或纠正措施，为控件分配分数值。</span><span class="sxs-lookup"><span data-stu-id="7de8f-180">Controls are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span> <span data-ttu-id="7de8f-181">这些共同体现了其相对于其他控件的实现风险。</span><span class="sxs-lookup"><span data-stu-id="7de8f-181">These collectively represent the risk of not implementing it relative to other controls.</span></span>

<span data-ttu-id="7de8f-182">如 Microsoft 合规性分数计算文章中所示，预防性控制获得比侦探和纠正措施更高的分数，强制性控制措施比随机控制获得更高的分数。</span><span class="sxs-lookup"><span data-stu-id="7de8f-182">As presented in the Microsoft Compliance Score calculation article, preventative controls get a higher score than detective and corrective ones, and mandatory controls get a higher score than discretionary ones.</span></span>
 
<span data-ttu-id="7de8f-183">请注意，合规性分数管理 UI 不会列出这些参数，也不能提供进行筛选的功能。</span><span class="sxs-lookup"><span data-stu-id="7de8f-183">Note that the Compliance Score admin UI does not list these parameters, nor does it provide the ability to filter by them.</span></span> <span data-ttu-id="7de8f-184">但是，如果从合规性管理器工具下载关联的模板，则生成的数据集将为大多数管理法规列出这些参数。</span><span class="sxs-lookup"><span data-stu-id="7de8f-184">However, if you download the associated template from the Compliance Manager tool, the resulting data set does list these parameters for most regulations.</span></span>

<span data-ttu-id="7de8f-185">对于技术控制，在激活相关功能后，合规性分数将自动更新改进操作得分。</span><span class="sxs-lookup"><span data-stu-id="7de8f-185">For technical controls, Compliance Score will automatically update the improvement action score once the related feature is activated.</span></span> <span data-ttu-id="7de8f-186">在 &mdash; &mdash; 服务信任门户的合规性管理器工具中，需要手动记录可运行或与文档相关的其他非技术性控制操作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-186">Other, non-technical control actions&mdash;such as those that are operational or related to documentation&mdash;need to be recorded manually in the Compliance Manager tool on the Services Trust Portal.</span></span> 

<span data-ttu-id="7de8f-187">您还需要为其他目的实施某些改进操作，例如， &mdash; 使用保留标签作为数据隐私法规遵从性之外的原因 &mdash; ，这样您就可以获得使用此类功能的信用，即使它用于其他用途，也不是有意的合规性操作的一部分。</span><span class="sxs-lookup"><span data-stu-id="7de8f-187">You many also be implementing certain improvement actions for other purposes&mdash;for example using retention labels for reasons other than data privacy regulation compliance&mdash;so you would get credit for using such a feature even if it is being used for other purposes, and not part of a deliberate compliance action.</span></span>

<span data-ttu-id="7de8f-188">应将合规性分数视为跟踪广泛规模改进的相对度量。</span><span class="sxs-lookup"><span data-stu-id="7de8f-188">Your Compliance Score should be considered a relative measure to track improvement on a broad scale.</span></span> <span data-ttu-id="7de8f-189">您不应争取一个理想的分数。</span><span class="sxs-lookup"><span data-stu-id="7de8f-189">You should not pursue a perfect score.</span></span> 

### <a name="additional-guidance"></a><span data-ttu-id="7de8f-190">其他指南</span><span class="sxs-lookup"><span data-stu-id="7de8f-190">Additional guidance</span></span>

<span data-ttu-id="7de8f-191">下面是有关使用合规性分数和合规性管理器来实现数据隐私法规遵从性的一些重要提示：</span><span class="sxs-lookup"><span data-stu-id="7de8f-191">Here are a few important tips for the use of Compliance Score and Compliance Manager for you to achieve data privacy regulation compliance:</span></span>

- <span data-ttu-id="7de8f-192">每个数据隐私法规都结合了技术控制、文档规范以及操作、过程和报告要求。</span><span class="sxs-lookup"><span data-stu-id="7de8f-192">Each data privacy regulation has a combination of technical controls, documentation specifications, and operational, process, and reporting requirements.</span></span> <span data-ttu-id="7de8f-193">所有这些操作都显示在改进操作中。</span><span class="sxs-lookup"><span data-stu-id="7de8f-193">All of these show up in the improvement actions.</span></span> 

- <span data-ttu-id="7de8f-194">本文重点介绍了在合规性管理器和合规性分数中为数据隐私指定的技术控件的子集。</span><span class="sxs-lookup"><span data-stu-id="7de8f-194">This article focuses on a subset of the technical controls specified for data privacy in Compliance Manager and Compliance Score.</span></span> <span data-ttu-id="7de8f-195">有关非技术性管理控件的详细信息，请参阅合规性管理器工具和[文档](../compliance/compliance-score.md)。</span><span class="sxs-lookup"><span data-stu-id="7de8f-195">Refer to the Compliance Manager tool and [documentation](../compliance/compliance-score.md) for more information on non-technical administrative controls.</span></span>

- <span data-ttu-id="7de8f-196">若要将改进操作视图集中到您感兴趣的领域，可以在合规性分数管理中的 "**解决方案**" 选项卡上按操作类型进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7de8f-196">To focus the view of improvement actions to your area of interest, you can filter by action type in the **Solutions** tab in the Compliance Score admin.</span></span>

- <span data-ttu-id="7de8f-197">应将合规性分数中确定的改进措施的相对重要性和优先级视为广泛风险审查的一部分，以及已确定组织需要管理的数据隐私风险。</span><span class="sxs-lookup"><span data-stu-id="7de8f-197">The relative importance and priority of improvement actions identified in Compliance Score should be considered as part of a broader risk review along with the data privacy risk you've determined your organization needs to manage.</span></span> 

- <span data-ttu-id="7de8f-198">如果您是全球组织，并将多个数据隐私法规模板添加到合规性管理器中作为评估，则合规性分数将在每个改进操作的字段列表中合并每个适用的项。</span><span class="sxs-lookup"><span data-stu-id="7de8f-198">If you are a global organization and you add multiple data privacy regulation templates into Compliance Manager as Assessments, Compliance Score will combine each applicable one in a field listing for each improvement action.</span></span>
 
- <span data-ttu-id="7de8f-199">即使选择了跨多个法规要求的改进操作聚合，如果选择了 GDPR、LGPD、CCPA 和 HIPAA-高科技的法规评估模板，例如，在合规性分数中将列出几乎400的改进操作。</span><span class="sxs-lookup"><span data-stu-id="7de8f-199">Even with improvement action aggregation across multiple regulatory requirements, if the regulation assessment templates for GDPR, LGPD, CCPA, and HIPAA-HITECH are selected, for example, almost 400 improvement actions will be listed in Compliance Score.</span></span> <span data-ttu-id="7de8f-200">若要更好地解决此较长的列表，请使用改进操作筛选器将结果集减少为更易于管理的列表。</span><span class="sxs-lookup"><span data-stu-id="7de8f-200">To better tackle this long list, use the improvement action filter to reduce the result set to a more manageable list.</span></span>

- <span data-ttu-id="7de8f-201">"类别" 筛选器提供了一种通过逻辑分组来筛选改进操作的方法，此整体解决方案中的跟踪、阻止、保护、保留和调查文章与对应。</span><span class="sxs-lookup"><span data-stu-id="7de8f-201">The Categories filter provides a means to filter improvement actions by logical grouping, which the Track, Prevent, Protect, Retain, and Investigate articles in this overall solution align to.</span></span> 

- <span data-ttu-id="7de8f-202">在改进操作中列出的某些控件可能更直接绑定到特定法规文章，而其他控件可能更与法规精神更直接关联，而在很多情况下，您应考虑无论如何做的事情。</span><span class="sxs-lookup"><span data-stu-id="7de8f-202">Some of the controls listed in the improvement actions may be considered more directly tied to a specific regulatory article, while other controls may be more indirectly associated with the spirit of a regulation and are many times just things you should consider doing anyway.</span></span>

