---
title: 在 Microsoft 合规性管理器中生成和管理评估
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 在 Microsoft 合规性管理器中生成评估，帮助你满足对组织非常重要的法规和认证要求。
ms.openlocfilehash: 4530f8544834c672b3ae1ebb70625ffe8f2ae4ae
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148934"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a><span data-ttu-id="73895-103">在合规性管理器中生成和管理评估</span><span class="sxs-lookup"><span data-stu-id="73895-103">Build and manage assessments in Compliance Manager</span></span>

<span data-ttu-id="73895-104">**本文内容：** 了解如何通过创建和管理评估来为组织自定义合规性 **管理器**。</span><span class="sxs-lookup"><span data-stu-id="73895-104">**In this article:** Learn how to customize Compliance Manager for your organization by creating and managing **assessments**.</span></span> <span data-ttu-id="73895-105">本文将指导你完成如何创建评估、如何将评估组织到组中、使用控件 **、接受更新** 以及导出 **评估报告**。</span><span class="sxs-lookup"><span data-stu-id="73895-105">This article walks you through how to create assessments, how to organize them into **groups**, working with **controls**, accepting **updates**, and exporting assessment **reports**.</span></span>

## <a name="introduction-to-assessments"></a><span data-ttu-id="73895-106">评估简介</span><span class="sxs-lookup"><span data-stu-id="73895-106">Introduction to assessments</span></span>

<span data-ttu-id="73895-107">合规性管理器可帮助你创建评估是否符合适用于组织的行业和区域法规的评估。</span><span class="sxs-lookup"><span data-stu-id="73895-107">Compliance Manager helps you create assessments that evaluate your compliance with industry and regional regulations that apply to your organization.</span></span> <span data-ttu-id="73895-108">评估基于评估模板的框架构建，其中包含完成评估所需的控制措施、改进操作和 Microsoft 行动。</span><span class="sxs-lookup"><span data-stu-id="73895-108">Assessments are built upon the framework of assessment templates, which contain the necessary controls, improvement actions, and Microsoft actions for completing the assessment.</span></span> <span data-ttu-id="73895-109">为组织设置最相关的评估可以帮助您实施策略和运营过程，以限制合规性风险。</span><span class="sxs-lookup"><span data-stu-id="73895-109">Setting up the most relevant assessments for your organization can help you implement policies and operational procedures to limit your compliance risk.</span></span>

<span data-ttu-id="73895-110">所有评估都列在合规性管理器的评估选项卡上。</span><span class="sxs-lookup"><span data-stu-id="73895-110">All of your assessments are listed on the assessments tab of Compliance Manager.</span></span> <span data-ttu-id="73895-111">了解有关如何 [筛选评估视图和解释状态状态的信息](compliance-manager-setup.md#assessments-page)。</span><span class="sxs-lookup"><span data-stu-id="73895-111">Learn more about [how to filter your view of your assessments and interpret status states](compliance-manager-setup.md#assessments-page).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73895-112">组织可用于生成评估的模板取决于您的许可协议。</span><span class="sxs-lookup"><span data-stu-id="73895-112">The templates available to your organization for building assessments depend on your licensing agreement.</span></span> <span data-ttu-id="73895-113">[查看许可详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="73895-113">[Review licensing details](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="data-protection-baseline-default-assessment"></a><span data-ttu-id="73895-114">数据保护基线默认评估</span><span class="sxs-lookup"><span data-stu-id="73895-114">Data Protection Baseline default assessment</span></span>

<span data-ttu-id="73895-115">为了开始操作，Microsoft 在合规性管理器中提供了针对Microsoft 365 **基准的默认评估**。</span><span class="sxs-lookup"><span data-stu-id="73895-115">To get you started, Microsoft provides a **default** assessment in Compliance Manager for the **Microsoft 365 data protection baseline**.</span></span> <span data-ttu-id="73895-116">此基线评估具有一组针对数据保护关键法规和标准以及一般数据管理的控制措施。</span><span class="sxs-lookup"><span data-stu-id="73895-116">This baseline assessment has a set of controls for key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="73895-117">此基线主要来自 NIST CSF (国家标准和技术网络安全协会) 和 ISO (国际标准化组织) ，以及 FedRAMP (联邦风险和授权管理计划) 以及欧盟) 的 GDPR (一般数据保护条例。</span><span class="sxs-lookup"><span data-stu-id="73895-117">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="73895-118">此评估用于在配置任何其他评估之前，在首次访问合规性管理器时计算初始合规性分数。</span><span class="sxs-lookup"><span data-stu-id="73895-118">This assessment is used to calculate your initial compliance score the first time you come to Compliance Manager, before you configure any other assessments.</span></span> <span data-ttu-id="73895-119">合规性管理器从你的解决方案中收集Microsoft 365信号。</span><span class="sxs-lookup"><span data-stu-id="73895-119">Compliance Manager collects initial signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="73895-120">你可以一目了然地查看组织相对于关键数据保护标准和法规的表现，并查看建议的改进措施。</span><span class="sxs-lookup"><span data-stu-id="73895-120">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="73895-121">随着构建和管理自己的评估以满足组织的特定需求，合规性管理器将变得更加有用。</span><span class="sxs-lookup"><span data-stu-id="73895-121">Compliance Manager becomes more helpful as you build and manage your own assessments to meet your organization's particular needs.</span></span>

## <a name="understand-groups-before-creating-assessments"></a><span data-ttu-id="73895-122">在创建评估之前了解组</span><span class="sxs-lookup"><span data-stu-id="73895-122">Understand groups before creating assessments</span></span>

<span data-ttu-id="73895-123">创建评估时，需要将其分配给组。</span><span class="sxs-lookup"><span data-stu-id="73895-123">When you create an assessment, you’ll need to assign it to a group.</span></span> <span data-ttu-id="73895-124">组是一些容器，允许您按符合逻辑的方式（如按年份或法规，或基于组织的部门或地理位置）组织评估。</span><span class="sxs-lookup"><span data-stu-id="73895-124">Groups are containers that allow you to organize assessments in a way that is logical to you, such as by year or regulation, or based on your organization's divisions or geographies.</span></span> <span data-ttu-id="73895-125">这就是我们建议你在创建评估之前规划分组策略的原因。</span><span class="sxs-lookup"><span data-stu-id="73895-125">This is why we recommend planning a grouping strategy before you create assessments.</span></span>

<span data-ttu-id="73895-126">下面是两个组及其基础评估的示例：</span><span class="sxs-lookup"><span data-stu-id="73895-126">Below are examples of two groups and their underlying assessments:</span></span>

- <span data-ttu-id="73895-127">**FFIEC IS assessment 2020**</span><span class="sxs-lookup"><span data-stu-id="73895-127">**FFIEC IS assessment 2020**</span></span>
  - <span data-ttu-id="73895-128">FFIEC IS</span><span class="sxs-lookup"><span data-stu-id="73895-128">FFIEC IS</span></span>
- <span data-ttu-id="73895-129">**数据安全和隐私评估**</span><span class="sxs-lookup"><span data-stu-id="73895-129">**Data security and privacy assessments**</span></span>
  - <span data-ttu-id="73895-130">ISO 27001：2013</span><span class="sxs-lookup"><span data-stu-id="73895-130">ISO 27001:2013</span></span>
  - <span data-ttu-id="73895-131">ISO 27018：2014</span><span class="sxs-lookup"><span data-stu-id="73895-131">ISO 27018:2014</span></span>

<span data-ttu-id="73895-132">当你管理的同一个组共享改进操作中的两个不同评估时，对操作的实施详细信息或状态进行的任何更新将自动在整个组中同步。</span><span class="sxs-lookup"><span data-stu-id="73895-132">When two different assessments in the same group share improvement actions that you manage, any updates you make to an action's implementation details or status will automatically synchronize throughout the group.</span></span> <span data-ttu-id="73895-133">此同步允许您同时实施一个改进操作并满足多个要求。</span><span class="sxs-lookup"><span data-stu-id="73895-133">This synchronization allows you to implement one improvement action and meet several requirements simultaneously.</span></span>

### <a name="create-a-group"></a><span data-ttu-id="73895-134">创建群组</span><span class="sxs-lookup"><span data-stu-id="73895-134">Create a group</span></span>

<span data-ttu-id="73895-135">可以在创建新评估时创建一个组。</span><span class="sxs-lookup"><span data-stu-id="73895-135">You can create a group while creating a new assessment.</span></span> <span data-ttu-id="73895-136">组不能创建为独立实体。</span><span class="sxs-lookup"><span data-stu-id="73895-136">Groups can't be created as standalone entities.</span></span>

### <a name="what-to-know-when-working-with-groups"></a><span data-ttu-id="73895-137">使用组时要了解哪些方面</span><span class="sxs-lookup"><span data-stu-id="73895-137">What to know when working with groups</span></span>

- <span data-ttu-id="73895-138">一个组必须至少包含一个评估。</span><span class="sxs-lookup"><span data-stu-id="73895-138">A group must contain at least one assessment.</span></span>
- <span data-ttu-id="73895-139">组名称在组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="73895-139">Group names must be unique within your organization.</span></span>
- <span data-ttu-id="73895-140">组没有安全属性。</span><span class="sxs-lookup"><span data-stu-id="73895-140">Groups don't have security properties.</span></span> <span data-ttu-id="73895-141">所有权限都与评估相关联。</span><span class="sxs-lookup"><span data-stu-id="73895-141">All permissions are associated with assessments.</span></span>
- <span data-ttu-id="73895-142">向组添加评估后，无法更改分组。</span><span class="sxs-lookup"><span data-stu-id="73895-142">Once you add an assessment to a group, the grouping can't be changed.</span></span>
- <span data-ttu-id="73895-143">如果向现有组添加新评估，则该组中评估的常见信息将复制到新评估。</span><span class="sxs-lookup"><span data-stu-id="73895-143">If you add a new assessment to an existing group, common information from assessments in that group are copied to the new assessment.</span></span>
- <span data-ttu-id="73895-144">完成时，同一组内不同评估中的相关评估控制措施将自动更新。</span><span class="sxs-lookup"><span data-stu-id="73895-144">Related assessment controls in different assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="73895-145">当对出现在多个组的改进进行了更改时，该更改将反映在该改进操作的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="73895-145">When a change is made to an improvement that appears in multiple groups, that change is reflected in all instances of that improvement action.</span></span>
- <span data-ttu-id="73895-146">组可以包含针对相同认证或法规的评估，但每个组只能包含一个特定产品认证对的评估。</span><span class="sxs-lookup"><span data-stu-id="73895-146">Groups can contain assessments for the same certification or regulation, but each group can only contain one assessment for a specific product-certification pair.</span></span> <span data-ttu-id="73895-147">例如，一个组不能包含针对 Office 365 和 NIST CSF 的两个评估。</span><span class="sxs-lookup"><span data-stu-id="73895-147">For example, a group can't contain two assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="73895-148">只有在针对同一产品的相应认证或法规不同时，组才能包含针对同一产品的多个评估。</span><span class="sxs-lookup"><span data-stu-id="73895-148">A group can contain multiple assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="73895-149">删除评估会破坏该评估与组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="73895-149">Deleting an assessment breaks the relationship between that assessment and the group.</span></span>
- <span data-ttu-id="73895-150">无法手动删除组。</span><span class="sxs-lookup"><span data-stu-id="73895-150">Groups can't be manually deleted.</span></span>

## <a name="create-assessments"></a><span data-ttu-id="73895-151">创建评估</span><span class="sxs-lookup"><span data-stu-id="73895-151">Create assessments</span></span>

> [!NOTE]
> <span data-ttu-id="73895-152">只有具有全局管理员、合规性管理器管理或合规性管理器评估员角色的用户才能创建和修改评估。</span><span class="sxs-lookup"><span data-stu-id="73895-152">Only users who hold a Global Administrator, Compliance Manager Administration, or Compliance Manager Assessor role can create and modify assessments.</span></span> <span data-ttu-id="73895-153">详细了解角色 [和权限](compliance-manager-setup.md#set-user-permissions-and-assign-roles)。</span><span class="sxs-lookup"><span data-stu-id="73895-153">Learn more about [roles and permissions](compliance-manager-setup.md#set-user-permissions-and-assign-roles).</span></span>

<span data-ttu-id="73895-154">若要开始构建评估，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="73895-154">To begin building assessments, follow these steps.</span></span>

1. <span data-ttu-id="73895-155">了解您将评估分配到哪个组，或者准备为此评估创建新组。</span><span class="sxs-lookup"><span data-stu-id="73895-155">Know which group you’ll assign your assessment to, or be prepared to create a new one for this assessment.</span></span>

2. <span data-ttu-id="73895-156">打开评估向导。</span><span class="sxs-lookup"><span data-stu-id="73895-156">Open the assessment wizard.</span></span> <span data-ttu-id="73895-157">可以从两处之一访问此飞出窗格：</span><span class="sxs-lookup"><span data-stu-id="73895-157">You can access this flyout pane from one of two places:</span></span>
    - <span data-ttu-id="73895-158">Go to your **assessments** page in Compliance Manager and select **Add assessment**;或</span><span class="sxs-lookup"><span data-stu-id="73895-158">Go to your **assessments** page in Compliance Manager and select **Add assessment**; or</span></span>
    - <span data-ttu-id="73895-159">在评估模板选项卡上找到想要使用的模板，查看其详细信息，然后选择创建 **评估**。</span><span class="sxs-lookup"><span data-stu-id="73895-159">Find the template you want to use on the **assessment templates** tab, view its details, and select **Create assessment**.</span></span> <span data-ttu-id="73895-160">这将填充向导的模板选择字段。</span><span class="sxs-lookup"><span data-stu-id="73895-160">This will populate the wizard's template selection field for you.</span></span>

3. <span data-ttu-id="73895-161">**选择模板**：如果还没有在步骤 2 中选择模板，请选择模板作为评估的基础。</span><span class="sxs-lookup"><span data-stu-id="73895-161">**Select a template**: If you didn't already choose a template in step 2, choose a template to serve as the basis for your assessment.</span></span> <span data-ttu-id="73895-162">你将看到分为包含和高级类别的模板列表， ([模板](compliance-manager-templates.md#template-availability-and-licensing) 类型了解) 。</span><span class="sxs-lookup"><span data-stu-id="73895-162">You’ll see the list of templates divided into included and premium categories (see [Template types](compliance-manager-templates.md#template-availability-and-licensing) for more information).</span></span> <span data-ttu-id="73895-163">选择所选模板旁边的单选按钮，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="73895-163">Select the radio button next to your chosen template, then select **Next**.</span></span>

4. <span data-ttu-id="73895-164">**名称和组：** 设置这些属性以标识评估并将其分配给组。</span><span class="sxs-lookup"><span data-stu-id="73895-164">**Name and group:** Set these properties to identify your assessment and assign it to a group.</span></span>
    - <span data-ttu-id="73895-165">**名称**：在"评估名称"字段中输入 **评估的名称** 。</span><span class="sxs-lookup"><span data-stu-id="73895-165">**Name**: Enter a name for your assessment in the **Assessment name** field.</span></span> <span data-ttu-id="73895-166">评估名称在组中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="73895-166">Assessment names must be unique within groups.</span></span> <span data-ttu-id="73895-167">如果你的评估名称与任意给定组中另一个评估的名称相匹配，你将收到一个错误，要求您创建其他名称。</span><span class="sxs-lookup"><span data-stu-id="73895-167">If the name of your assessment matches the name of another assessment in any given group, you’ll receive an error asking you to create a different name.</span></span>
    - <span data-ttu-id="73895-168">**组**：将评估分配到组。</span><span class="sxs-lookup"><span data-stu-id="73895-168">**Group**: Assign your assessment to a group.</span></span> <span data-ttu-id="73895-169">您可以：</span><span class="sxs-lookup"><span data-stu-id="73895-169">You can either:</span></span>
        - <span data-ttu-id="73895-170">选择 **"使用现有** 组"将其分配给已创建的组;或</span><span class="sxs-lookup"><span data-stu-id="73895-170">Select **Use existing group** to assign it to a group you’ve already created; or</span></span>
        - <span data-ttu-id="73895-171">选择 **创建新组** 以创建新组，并将此评估分配给它：</span><span class="sxs-lookup"><span data-stu-id="73895-171">Select **Create new group** to create a new group and assign this assessment to it:</span></span>
            - <span data-ttu-id="73895-172">确定组的名称，在单选按钮下方的字段中输入该名称。</span><span class="sxs-lookup"><span data-stu-id="73895-172">Determine a name for your group and enter it in the field beneath the radio button.</span></span>
            - <span data-ttu-id="73895-173">通过 **选择相应的框，** 可以从现有组（如实现和测试详细信息和文档）复制数据。</span><span class="sxs-lookup"><span data-stu-id="73895-173">You can **copy data from an existing group**, such as implementation and testing details and documents, by selecting the appropriate boxes.</span></span>

    <span data-ttu-id="73895-174">完成后，选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="73895-174">When finished, select **Next**.</span></span>

5. <span data-ttu-id="73895-175">**查看并完成：** 向导的最后一个屏幕显示为评估选择的模板、名称和组。</span><span class="sxs-lookup"><span data-stu-id="73895-175">**Review and finish:** The last screen of the wizard shows the template, name, and group chosen for the assessment.</span></span> <span data-ttu-id="73895-176">你可以从屏幕上的链接编辑其中任何设置，这将返回到向导中的相关步骤。</span><span class="sxs-lookup"><span data-stu-id="73895-176">You can edit any of these settings from the links on the screen, which take you back to the relevant steps in the wizard.</span></span> <span data-ttu-id="73895-177">准备就绪后，选择创建 **评估**。</span><span class="sxs-lookup"><span data-stu-id="73895-177">When you're ready, select **Create assessment**.</span></span>

6. <span data-ttu-id="73895-178">下一个屏幕将确认已成功创建新评估。</span><span class="sxs-lookup"><span data-stu-id="73895-178">The next screen confirms that you’ve successfully created your new assessment.</span></span> <span data-ttu-id="73895-179">选择 **"** 完成"关闭向导，屏幕上将显示新评估的详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="73895-179">Select **Done** to close the wizard, and your new assessment's details page will appear on the screen.</span></span>

<span data-ttu-id="73895-180">如果在选择"创建评估"**后** 看到"评估失败"屏幕，请选择"重试"以重新创建评估。</span><span class="sxs-lookup"><span data-stu-id="73895-180">If you see an **Assessment failed** screen after selecting **Create assessment**, select **Try again** to re-create your assessment.</span></span>

<span data-ttu-id="73895-181">创建评估后，可以通过选择评估详细信息页面右上角的"编辑名称"按钮来[更改评估名称](#monitor-assessment-progress-and-controls)。</span><span class="sxs-lookup"><span data-stu-id="73895-181">You can change the name of your assessment after you create it by selecting the **Edit name** button in the upper-right corner of the [assessment's details page](#monitor-assessment-progress-and-controls).</span></span>

## <a name="monitor-assessment-progress-and-controls"></a><span data-ttu-id="73895-182">监视评估进度和控制</span><span class="sxs-lookup"><span data-stu-id="73895-182">Monitor assessment progress and controls</span></span>

<span data-ttu-id="73895-183">每个评估都有一个详细信息页面，其中提供了完成评估的进度的概览。</span><span class="sxs-lookup"><span data-stu-id="73895-183">Each assessment has a details page that gives an at-a-glance view of your progress in completing the assessment.</span></span> <span data-ttu-id="73895-184">该页显示您完成控件的进度，以及这些控件中关键改进操作的测试状态。</span><span class="sxs-lookup"><span data-stu-id="73895-184">The page shows your progress in completing controls, and the test status of key improvement actions within those controls.</span></span>

### <a name="overview-tab"></a><span data-ttu-id="73895-185">"概述"选项卡</span><span class="sxs-lookup"><span data-stu-id="73895-185">Overview tab</span></span>

<span data-ttu-id="73895-186">"概述"选项卡包含显示完成评估的百分比的图形。</span><span class="sxs-lookup"><span data-stu-id="73895-186">The overview tab contains a graph showing your percentage toward completion of the assessment.</span></span> <span data-ttu-id="73895-187">此图包含你拥有的操作的分项细目和 Microsoft 拥有的操作的分数，因此你可以看到完成评估还需要多少点。</span><span class="sxs-lookup"><span data-stu-id="73895-187">This graph contains a breakdown of points from actions you own, and points from actions owned by Microsoft, so you can see how many more points you need to complete the assessment.</span></span>

<span data-ttu-id="73895-188">评估中控制措施的关键改进措施按获得分数的潜在影响最大顺序列出。</span><span class="sxs-lookup"><span data-stu-id="73895-188">The key improvement actions for controls in the assessment are listed in order of greatest potential impact to earn points.</span></span> <span data-ttu-id="73895-189">关联的图表详细介绍了改进操作聚合的测试状态，以便快速判断已经过测试的情况以及需要完成的操作。</span><span class="sxs-lookup"><span data-stu-id="73895-189">The associated graph details the aggregated test status of your improvement actions so you can quickly gauge what has been tested and what still needs to be done.</span></span>

<span data-ttu-id="73895-190">若要访问单个改进操作，请访问" **控件** "选项卡或" **你的改进操作"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="73895-190">To access individual improvement actions, visit the **Controls** tab or the **Your improvement actions** tab.</span></span>

### <a name="controls-tab"></a><span data-ttu-id="73895-191">控件选项卡</span><span class="sxs-lookup"><span data-stu-id="73895-191">Controls tab</span></span>

<span data-ttu-id="73895-192">"控件"选项卡显示映射到评估的每个控制措施的详细信息。</span><span class="sxs-lookup"><span data-stu-id="73895-192">The controls tab displays detailed information for each control mapped to the assessment.</span></span> <span data-ttu-id="73895-193">控件 **状态细分** 图表按系列显示控件的状态，因此您可以一目了然地查看哪些控件分组需要关注。</span><span class="sxs-lookup"><span data-stu-id="73895-193">A **control status breakdown** chart shows the status of controls by family, so you can see at a glance which groupings of controls need attention.</span></span>

<span data-ttu-id="73895-194">在图表下方，表格列出了评估中每个控件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="73895-194">Beneath the chart, a table lists detailed information about each control within the assessment.</span></span> <span data-ttu-id="73895-195">控件按控件系列进行分组。</span><span class="sxs-lookup"><span data-stu-id="73895-195">Controls are grouped by control family.</span></span> <span data-ttu-id="73895-196">展开每个系列名称以显示其包含的单个控件。</span><span class="sxs-lookup"><span data-stu-id="73895-196">Expand each family name to reveal the individual controls it contains.</span></span> <span data-ttu-id="73895-197">每个控件列出的信息包括：</span><span class="sxs-lookup"><span data-stu-id="73895-197">The information listed for each control includes:</span></span>

- <span data-ttu-id="73895-198">**控件标题**</span><span class="sxs-lookup"><span data-stu-id="73895-198">**Control title**</span></span>
- <span data-ttu-id="73895-199">**状态**：反映控件中改进操作的测试状态</span><span class="sxs-lookup"><span data-stu-id="73895-199">**Status**: reflects the test status of the improvement actions within the control</span></span> 
    - <span data-ttu-id="73895-200">**通过** - 所有改进操作均具有"通过"的测试状态，或至少一项通过，其余操作均"超出范围"</span><span class="sxs-lookup"><span data-stu-id="73895-200">**Passed** - all improvement actions have a test status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    -  <span data-ttu-id="73895-201">**失败** - 至少有一个改进操作的测试状态为"失败"</span><span class="sxs-lookup"><span data-stu-id="73895-201">**Failed** - at least one improvement action has a test status of “failed”</span></span>
    - <span data-ttu-id="73895-202">**无** - 所有改进操作都未经过测试</span><span class="sxs-lookup"><span data-stu-id="73895-202">**None** - all improvement actions have not been tested</span></span>
    - <span data-ttu-id="73895-203">**超出范围** - 所有改进操作均超出此评估范围</span><span class="sxs-lookup"><span data-stu-id="73895-203">**Out of scope** - all improvement actions are out of scope for this assessment</span></span>
    - <span data-ttu-id="73895-204">**进行** 中 - 改进操作的状态与上面列出的不同，可能包括"正在进行"、"部分信用"或"未检测"</span><span class="sxs-lookup"><span data-stu-id="73895-204">**In progress** - improvement actions have a status other than the ones listed above, which could include “in progress,” “partial credit,” or “undetected”</span></span>
- <span data-ttu-id="73895-205">**控件 ID：** 控件的标识号，由相应的法规、标准或策略分配</span><span class="sxs-lookup"><span data-stu-id="73895-205">**Control ID**: the control’s identification number, assigned by its corresponding regulation, standard, or policy</span></span>
- <span data-ttu-id="73895-206">**获得点数**：完成操作获得的点数（总可实现分数数）</span><span class="sxs-lookup"><span data-stu-id="73895-206">**Points achieved**: the number of points earned by completing actions, out of the total number of achievable points</span></span> 
- <span data-ttu-id="73895-207">**操作**：要完成的操作总数中的完成操作数</span><span class="sxs-lookup"><span data-stu-id="73895-207">**Your actions**: the number of your actions completed out of the total number of actions to be done</span></span>
- <span data-ttu-id="73895-208">**Microsoft 操作**：Microsoft 完成的操作数</span><span class="sxs-lookup"><span data-stu-id="73895-208">**Microsoft actions**: the number of actions completed by Microsoft</span></span> 

<span data-ttu-id="73895-209">若要查看控件的详细信息，请从控件在表格中的行中选择它。</span><span class="sxs-lookup"><span data-stu-id="73895-209">To view a control’s details, select it from its row in the table.</span></span> <span data-ttu-id="73895-210">"控件详细信息"页显示一个指示该控件内操作的测试状态的图形。</span><span class="sxs-lookup"><span data-stu-id="73895-210">The control details page shows a graph indicating the test status of the actions within that control.</span></span> <span data-ttu-id="73895-211">此图下方的表格显示了该控件的关键改进操作。</span><span class="sxs-lookup"><span data-stu-id="73895-211">A table below the graph shows key improvement actions for that control.</span></span>

<span data-ttu-id="73895-212">从列表中选择改进操作以深入了解改进操作的详细信息页。</span><span class="sxs-lookup"><span data-stu-id="73895-212">Select an improvement action from the list to drill into the improvement action’s details page.</span></span> <span data-ttu-id="73895-213">详细信息页显示测试状态、实现说明，并启动到建议的解决方案中。</span><span class="sxs-lookup"><span data-stu-id="73895-213">The details pages shows test status, implementation notes, and launch into the recommended solution.</span></span>

### <a name="your-improvement-actions-tab"></a><span data-ttu-id="73895-214">"改进操作"选项卡</span><span class="sxs-lookup"><span data-stu-id="73895-214">Your improvement actions tab</span></span>

<span data-ttu-id="73895-215">改进操作选项卡列出了评估中由组织管理的所有控制措施。</span><span class="sxs-lookup"><span data-stu-id="73895-215">The tab for your improvement actions lists all the controls in the assessment that are managed by your organization.</span></span> <span data-ttu-id="73895-216">状态栏详细介绍评估中改进操作聚合的测试状态，以便快速判断已测试内容以及需要完成的操作。</span><span class="sxs-lookup"><span data-stu-id="73895-216">The status bar details the aggregated test status of your improvement actions in the assessment so you can quickly gauge what has been tested and what still needs to be done.</span></span> <span data-ttu-id="73895-217">栏下方是改进操作的完整列表和关键详细信息，包括：测试状态、潜在和挣点的数量、关联的法规和标准、适用的解决方案、操作类型和控制系列。</span><span class="sxs-lookup"><span data-stu-id="73895-217">Beneath the bar is the full list of improvement actions and key details, including: test status, the number of potential and earned points, associated regulations and standards, applicable solution, action type, and control family.</span></span> <span data-ttu-id="73895-218">详细了解操作 [如何参与合规性分数](compliance-score-calculation.md#action-types-and-points)。</span><span class="sxs-lookup"><span data-stu-id="73895-218">Learn more about [how actions contribute to your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

<span data-ttu-id="73895-219">选择改进操作以查看其详细信息页面，然后选择"立即启动"链接以打开解决方案以采取操作。</span><span class="sxs-lookup"><span data-stu-id="73895-219">Select an improvement action to view its details page, and select the **Launch now** link to open the solution to take action.</span></span>

### <a name="microsoft-actions-tab"></a><span data-ttu-id="73895-220">Microsoft 操作选项卡</span><span class="sxs-lookup"><span data-stu-id="73895-220">Microsoft actions tab</span></span>

<span data-ttu-id="73895-221">"Microsoft 操作"选项卡列出了评估中由 Microsoft 管理的所有操作。</span><span class="sxs-lookup"><span data-stu-id="73895-221">The Microsoft actions tab lists all the actions in the assessment that are managed by Microsoft.</span></span> <span data-ttu-id="73895-222">该列表显示了关键操作详细信息，包括：测试状态、参与整体合规性分数的分数、相关的法规和标准、适用的解决方案、操作类型和控制系列。</span><span class="sxs-lookup"><span data-stu-id="73895-222">The list shows key action details, including: test status, points that contribute to your overall compliance score, associated regulations and standards, applicable solution, action type, and control family.</span></span> <span data-ttu-id="73895-223">选择改进操作以查看其详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="73895-223">Select an improvement action to view its details page.</span></span>

<span data-ttu-id="73895-224">详细了解如何 [跟踪控制措施和改进操作并评分。](compliance-score-calculation.md)</span><span class="sxs-lookup"><span data-stu-id="73895-224">Learn more about [how controls and improvement actions are tracked and scored.](compliance-score-calculation.md)</span></span>

## <a name="accept-updates-to-assessments"></a><span data-ttu-id="73895-225">接受评估更新</span><span class="sxs-lookup"><span data-stu-id="73895-225">Accept updates to assessments</span></span>

<span data-ttu-id="73895-226">当更新可用于评估时，你将看到一条通知，并且可以选择接受更新或延迟更新以稍后进行。</span><span class="sxs-lookup"><span data-stu-id="73895-226">When an update is available for an assessment, you’ll see a notification and have the option to accept the update or defer it for a later time.</span></span>

### <a name="what-causes-an-update"></a><span data-ttu-id="73895-227">导致更新的原因</span><span class="sxs-lookup"><span data-stu-id="73895-227">What causes an update</span></span>

<span data-ttu-id="73895-228">当存在影响评分的基础模板更改时，将发生评估更新。</span><span class="sxs-lookup"><span data-stu-id="73895-228">An assessment update occurs when there are underlying template changes that impact scoring.</span></span> <span data-ttu-id="73895-229">更改可能涉及根据法规更改或产品更改调整控制映射或其他指南。</span><span class="sxs-lookup"><span data-stu-id="73895-229">Changes may involve adjusting control mapping or other guidance based on regulatory changes or product changes.</span></span> <span data-ttu-id="73895-230">评估更新可能源自 (，例如，在 Microsoft 和 Microsoft [](compliance-manager-templates.md#modify-a-template)) 修改自定义模板时。</span><span class="sxs-lookup"><span data-stu-id="73895-230">Assessment updates can originate from your organization (such as, when a [custom template is modified](compliance-manager-templates.md#modify-a-template)) as well as from Microsoft.</span></span>

<span data-ttu-id="73895-231">如果 Microsoft 更新你扩展的合规性管理器模板，则你的评估将在你接受这些更新后继承这些更新。</span><span class="sxs-lookup"><span data-stu-id="73895-231">If Microsoft updates a Compliance Manager template that you extended, your assessment will inherit those updates once you accept them.</span></span> <span data-ttu-id="73895-232">在扩展评估时，评估将保留应用于评估的其他属性。</span><span class="sxs-lookup"><span data-stu-id="73895-232">Your assessment will retain the additional attributes you applied to the assessment when you extended it.</span></span>

<span data-ttu-id="73895-233">您创建的自定义评估不会收到来自 Microsoft 的任何模板更新。</span><span class="sxs-lookup"><span data-stu-id="73895-233">Custom assessments that you create do not receive any template updates from Microsoft.</span></span> <span data-ttu-id="73895-234">自定义评估可以接收改进行动更新，但用于控制评估与改进行动之间的映射的任何 Microsoft 更新不适用于自定义模板。</span><span class="sxs-lookup"><span data-stu-id="73895-234">Custom assessments can receive improvement action updates, but any Microsoft updates to control mapping between assessments and improvement actions don't apply to custom templates.</span></span>

> [!NOTE]
> <span data-ttu-id="73895-235">评估更新仅适用于组级别。</span><span class="sxs-lookup"><span data-stu-id="73895-235">Updates to assessments apply only at the group level.</span></span> <span data-ttu-id="73895-236">如果你有两个基于同一模板构建的评估，它们存在于两个不同的组中，则每个评估将具有一个挂起的更新通知，并且你将需要分别接受对各自组中每个评估的更新。</span><span class="sxs-lookup"><span data-stu-id="73895-236">If you have two assessments built from the same template that exist in two different groups, each assessment will have a pending update notification, and you’ll need to accept the update to each assessment in its respective group individually.</span></span>

#### <a name="where-youll-see-assessment-update-notifications"></a><span data-ttu-id="73895-237">你将在哪里看到评估更新通知</span><span class="sxs-lookup"><span data-stu-id="73895-237">Where you’ll see assessment update notifications</span></span>

<span data-ttu-id="73895-238">评估详细信息页面还会在评估 **旁边** 显示"挂起的更新"标签以及更新。</span><span class="sxs-lookup"><span data-stu-id="73895-238">The assessment details page also shows a **Pending update** label next to the assessment with an update.</span></span> <span data-ttu-id="73895-239">选择该评估以进入其详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="73895-239">Select that assessment to get to its details page.</span></span>

<span data-ttu-id="73895-240">评估详细信息页面顶部附近的一条消息显示该评估提供了更新。</span><span class="sxs-lookup"><span data-stu-id="73895-240">A message near the top of the assessment details page shows that an update is available for that assessment.</span></span> <span data-ttu-id="73895-241">选择 **横幅中的"** 查看更新"按钮，查看特定更改并接受或延迟更新。</span><span class="sxs-lookup"><span data-stu-id="73895-241">Select the **Review update** button in the banner to review the specific changes and accept or defer the update.</span></span>

<span data-ttu-id="73895-242">评估详细信息页面可能还列出了旁边有"挂起 **的更新"** 标签的改进操作。</span><span class="sxs-lookup"><span data-stu-id="73895-242">The assessment details page may also list improvement actions that have a **Pending update** label next to them.</span></span> <span data-ttu-id="73895-243">这些更新适用于对改进操作本身进行的特定更改，需要单独接受。</span><span class="sxs-lookup"><span data-stu-id="73895-243">Those updates are for specific changes to the improvement actions themselves and need to be accepted separately.</span></span> <span data-ttu-id="73895-244">若要 [了解更多信息，请访问接受更新以改进](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) 操作。</span><span class="sxs-lookup"><span data-stu-id="73895-244">Visit [Accepting updates to improvement actions](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) to learn more.</span></span>

#### <a name="review-update-to-accept-or-defer"></a><span data-ttu-id="73895-245">查看更新以接受或延迟</span><span class="sxs-lookup"><span data-stu-id="73895-245">Review update to accept or defer</span></span>

<span data-ttu-id="73895-246">从 **评估详细信息页面** 选择"审阅更新"后，屏幕右侧将显示一个飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="73895-246">After selecting **Review update** from the assessment details page, a flyout pane appears on the right side of your screen.</span></span> <span data-ttu-id="73895-247">该飞出窗格提供了以下有关挂起更新的关键详细信息：</span><span class="sxs-lookup"><span data-stu-id="73895-247">The flyout pane provides the key details below about the pending update:</span></span>

- <span data-ttu-id="73895-248">模板标题</span><span class="sxs-lookup"><span data-stu-id="73895-248">The template title</span></span>
- <span data-ttu-id="73895-249">Microsoft、 (或特定用户的更新源) </span><span class="sxs-lookup"><span data-stu-id="73895-249">Source of the update (Microsoft, your organization, or a specific user)</span></span>
- <span data-ttu-id="73895-250">更新的创建日期</span><span class="sxs-lookup"><span data-stu-id="73895-250">The date the update was created</span></span>
- <span data-ttu-id="73895-251">说明更新的概述</span><span class="sxs-lookup"><span data-stu-id="73895-251">An overview explaining the update</span></span>
- <span data-ttu-id="73895-252">有关更改的特定详细信息，包括对合规性分数的影响、评估完成进度以及改进操作和控制措施的特定更改数。</span><span class="sxs-lookup"><span data-stu-id="73895-252">Specific details about the changes, including the impact to your compliance score, the amount of progress toward completion of the assessment, and the specific number of changes to improvement actions and controls.</span></span>

<span data-ttu-id="73895-253">选择 **"更新的模板**"链接将下载一Excel文件，其中包含包含挂起更新的模板版本的控件数据。</span><span class="sxs-lookup"><span data-stu-id="73895-253">Selecting the **Updated template** link will download an Excel file containing control data for the version of the template with the pending updates.</span></span> <span data-ttu-id="73895-254">选择 **"当前模板** "链接将下载现有模板的文件，而不进行更改。</span><span class="sxs-lookup"><span data-stu-id="73895-254">Selecting the **Current template** link downloads a file of the existing template without the changes.</span></span>

<span data-ttu-id="73895-255">若要接受更新并更改评估，请选择"接受 **更新"。**</span><span class="sxs-lookup"><span data-stu-id="73895-255">To accept the update and make the changes to your assessment, select **Accept update**.</span></span> <span data-ttu-id="73895-256">接受的更改是永久性的。</span><span class="sxs-lookup"><span data-stu-id="73895-256">Accepted changes are permanent.</span></span>

<span data-ttu-id="73895-257">如果选择" **取消"，** 则更新不会应用于评估。</span><span class="sxs-lookup"><span data-stu-id="73895-257">If you select **Cancel**, the update won't be applied to the assessment.</span></span> <span data-ttu-id="73895-258">但是，您将继续看到"挂起的更新" **通知，** 直到您接受更新。</span><span class="sxs-lookup"><span data-stu-id="73895-258">However, you’ll continue to see the **Pending update** notification until you accept the update.</span></span>

<span data-ttu-id="73895-259">**为何我们建议接受更新**</span><span class="sxs-lookup"><span data-stu-id="73895-259">**Why we recommend accepting updates**</span></span>

<span data-ttu-id="73895-260">接受更新有助于确保你拥有有关使用解决方案和采取相应改进操作的最新指南，以帮助你满足当前认证的要求。</span><span class="sxs-lookup"><span data-stu-id="73895-260">Accepting updates helps ensure you have the most updated guidance on using solutions and taking appropriate improvement actions to help you meet the requirements of the certification at hand.</span></span>

<span data-ttu-id="73895-261">**为什么您可能需要延迟更新**</span><span class="sxs-lookup"><span data-stu-id="73895-261">**Why you might want to defer an update**</span></span>

<span data-ttu-id="73895-262">如果正在完成评估，你可能希望确保在接受可能中断控制映射的评估更新之前已完成对评估的工作。</span><span class="sxs-lookup"><span data-stu-id="73895-262">If you’re in the middle of completing an assessment, you may want to ensure you’ve finished work on it before you accept an update to the assessment that could disrupt control mapping.</span></span> <span data-ttu-id="73895-263">可以在审阅更新飞出窗格中选择"取消"，将更新延迟一段时间。</span><span class="sxs-lookup"><span data-stu-id="73895-263">You can defer the update for a later time by selecting **Cancel** on the review update flyout pane.</span></span>

## <a name="export-an-assessment-report"></a><span data-ttu-id="73895-264">导出评估报告</span><span class="sxs-lookup"><span data-stu-id="73895-264">Export an assessment report</span></span>

<span data-ttu-id="73895-265">可以将评估导出到组织Excel合规性利益干系人或外部审核员和监管机构的配置文件。</span><span class="sxs-lookup"><span data-stu-id="73895-265">You can export an assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="73895-266">在评估详细信息页面上，选择页面顶部附近的"生成报告"按钮，这将创建一Excel可保存和共享的报告文件。</span><span class="sxs-lookup"><span data-stu-id="73895-266">On your assessment details page, select the **Generate report** button near the top of the page, which creates an Excel file you can save and share.</span></span>

<span data-ttu-id="73895-267">该报告是自导出日期和时间起评估的快照。</span><span class="sxs-lookup"><span data-stu-id="73895-267">The report is a snapshot of the assessment as of the date and time of the export.</span></span> <span data-ttu-id="73895-268">它包含由你和 Microsoft 管理的控制措施的详细信息，包括实现状态、测试日期和测试结果。</span><span class="sxs-lookup"><span data-stu-id="73895-268">It contains the details for controls managed by both you and Microsoft, including implementation status, test date, and test results.</span></span>

## <a name="delete-an-assessment"></a><span data-ttu-id="73895-269">删除评估</span><span class="sxs-lookup"><span data-stu-id="73895-269">Delete an assessment</span></span>

<span data-ttu-id="73895-270">删除评估会将其从评估页面的列表中删除。</span><span class="sxs-lookup"><span data-stu-id="73895-270">Deleting an assessment removes it from the list on your assessments page.</span></span> <span data-ttu-id="73895-271">请注意以下有关删除评估的重要要点：</span><span class="sxs-lookup"><span data-stu-id="73895-271">Note these important points about deleting assessments:</span></span>

- <span data-ttu-id="73895-272">**删除评估是永久性的;你无法返回它。**</span><span class="sxs-lookup"><span data-stu-id="73895-272">**Deleting an assessment is permanent; you cannot get it back.**</span></span> <span data-ttu-id="73895-273">如果要再次使用相同的评估，则需要重新创建它。</span><span class="sxs-lookup"><span data-stu-id="73895-273">If you want to use the same assessment again, you'll need to re-create it.</span></span>
- <span data-ttu-id="73895-274">如果评估中的改进操作未显示在任何其他评估中，则删除评估后，这些操作将被删除。</span><span class="sxs-lookup"><span data-stu-id="73895-274">If the improvement actions in the assessment don't appear in any other assessment, they'll be deleted when the assessment is deleted.</span></span>
- <span data-ttu-id="73895-275">建议 [在永久删除](#export-an-assessment-report) 评估前导出评估报告。</span><span class="sxs-lookup"><span data-stu-id="73895-275">We recommend [exporting a report](#export-an-assessment-report) of the assessment before you permanently delete it.</span></span>

<span data-ttu-id="73895-276">若要删除评估，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="73895-276">To delete an assessment, follow the steps below:</span></span>

1. <span data-ttu-id="73895-277">从 **评估页面** ，选择要删除的评估以打开该评估的详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="73895-277">From your **assessments** page, select the assessment you wish to delete to open that assessment’s details page.</span></span>

2. <span data-ttu-id="73895-278">选择 **屏幕** 右上角的"删除评估"。</span><span class="sxs-lookup"><span data-stu-id="73895-278">Select **Delete assessment** in the upper-right corner of your screen.</span></span>

3. <span data-ttu-id="73895-279">将显示一个窗口，要求您确认是否要永久删除评估。</span><span class="sxs-lookup"><span data-stu-id="73895-279">A window will appear asking you to confirm that you want to permanently delete the assessment.</span></span> <span data-ttu-id="73895-280">选择 **"删除评估** "以关闭该窗口。</span><span class="sxs-lookup"><span data-stu-id="73895-280">Select **Delete assessment** to close the window.</span></span> <span data-ttu-id="73895-281">你会收到一个确认窗口，表明你的评估已从合规性管理器中删除。</span><span class="sxs-lookup"><span data-stu-id="73895-281">You’ll get a confirmation window that your assessment was deleted from Compliance Manager.</span></span>

<span data-ttu-id="73895-282">如果删除组中唯一的评估，则该组也将从合规性管理器中删除。</span><span class="sxs-lookup"><span data-stu-id="73895-282">If you delete the only assessment in a group, then that group is also deleted from Compliance Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="73895-283">无法删除所有评估。</span><span class="sxs-lookup"><span data-stu-id="73895-283">You can't delete all of your assessments.</span></span> <span data-ttu-id="73895-284">组织至少需要一项评估，合规性管理器正常运行。</span><span class="sxs-lookup"><span data-stu-id="73895-284">Organizations need at least one assessment for Compliance Manager to function properly.</span></span> <span data-ttu-id="73895-285">如果要删除的评估是唯一一个，在删除另一个评估之前添加另一个评估。</span><span class="sxs-lookup"><span data-stu-id="73895-285">If the assessment you want to delete is the only one, add another assessment before deleting the other assessment.</span></span>
