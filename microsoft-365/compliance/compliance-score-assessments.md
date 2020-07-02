---
title: 通过评估自定义 Microsoft 合规性分数
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
description: 通过创建评估来帮助您管理组织的合规性，从而设计自定义的 Microsoft 合规性分数。
ms.openlocfilehash: 45a5e76aa4f6581146ded510f75d772c202751ee
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023305"
---
# <a name="customize-compliance-score-preview-with-assessments"></a><span data-ttu-id="3efbc-103">使用评估功能自定义合规性分数（预览）</span><span class="sxs-lookup"><span data-stu-id="3efbc-103">Customize Compliance Score (preview) with assessments</span></span>

<span data-ttu-id="3efbc-104">**本文内容：** 了解如何通过设置已准备好使用**评估**来自定义合规性分数。</span><span class="sxs-lookup"><span data-stu-id="3efbc-104">**In this article:** Learn how to customize Compliance Score by setting up ready to use **assessments**.</span></span> <span data-ttu-id="3efbc-105">了解如何修改评估的**模板**并创建您自己的自定义评估以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="3efbc-105">Read how to modify the **template** for an assessment and create your own Custom Assessments to suit your organization’s needs.</span></span> <span data-ttu-id="3efbc-106">本文还介绍了如何将评估组织为**组**、使用**控件**和导出评估**报告**。</span><span class="sxs-lookup"><span data-stu-id="3efbc-106">This article also explains how to organize assessments into **groups**, work with **controls**, and export assessment **reports**.</span></span>

## <a name="introduction-to-assessments"></a><span data-ttu-id="3efbc-107">评估简介</span><span class="sxs-lookup"><span data-stu-id="3efbc-107">Introduction to assessments</span></span>

<span data-ttu-id="3efbc-108">合规性分数可帮助您管理对您的组织适用的法规和认证的评估合规性。</span><span class="sxs-lookup"><span data-stu-id="3efbc-108">Compliance Score helps you manage compliance with assessments for the regulations and certifications that apply to your organization.</span></span> <span data-ttu-id="3efbc-109">评估是来自特定法规、标准或策略的控件组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-109">Assessments are groupings of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="3efbc-110">合规性分数通过提供可供使用的评估涵盖各种行业和区域的法规和认证，使您能够轻松地开始跟踪合规性。</span><span class="sxs-lookup"><span data-stu-id="3efbc-110">Compliance Score makes it easy to start tracking your compliance by providing ready to use assessments that cover a variety of industry and regional regulations and certifications.</span></span>

<span data-ttu-id="3efbc-111">每个评估都是通过模板创建的，它充当包含完成评估所需的控件和改进操作的框架。</span><span class="sxs-lookup"><span data-stu-id="3efbc-111">Each assessment is created from a template, which serves as a framework containing the necessary controls and improvement actions for completing the assessment.</span></span> <span data-ttu-id="3efbc-112">为你的组织设置最相关的评估可帮助确保你实施可限制合规性风险的策略和操作过程。</span><span class="sxs-lookup"><span data-stu-id="3efbc-112">Setting up the most relevant assessments for your organization helps ensure you’re implementing policies and operational procedures that can limit your compliance risk.</span></span>

<span data-ttu-id="3efbc-113">您的所有评估都列在 "评估" 页上。</span><span class="sxs-lookup"><span data-stu-id="3efbc-113">All of your assessments are listed on the assessments page.</span></span> <span data-ttu-id="3efbc-114">[了解](compliance-score-setup.md#assessments-page)有关如何筛选你的评估视图和解释状态状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efbc-114">[Learn more](compliance-score-setup.md#assessments-page) about how to filter your view of your assessments and interpret status states.</span></span>

## <a name="data-protection-baseline-default-assessment"></a><span data-ttu-id="3efbc-115">数据保护基线默认评估</span><span class="sxs-lookup"><span data-stu-id="3efbc-115">Data protection baseline default assessment</span></span>

<span data-ttu-id="3efbc-116">为了让你入门，Microsoft 在合规性分数中提供了一个**默认**评估，其中包含 Microsoft 365 数据保护基准。</span><span class="sxs-lookup"><span data-stu-id="3efbc-116">To get you started, Microsoft provides a **default** assessment in Compliance Score for you that contains the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="3efbc-117">此基准是一组控件，包括用于数据保护和常规数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="3efbc-117">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="3efbc-118">此基线主要从 NIST CSF （美国国家标准和技术协会 Cybersecurity Framework）和 ISO （国际标准化组织）以及 FedRAMP （联邦风险和授权管理计划）和 GDPR （欧盟的常规数据保护法规）中提取元素。</span><span class="sxs-lookup"><span data-stu-id="3efbc-118">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="3efbc-119">在配置任何其他评估之前，此评估功能用于计算首次遵守合规性得分时的初始分数。</span><span class="sxs-lookup"><span data-stu-id="3efbc-119">This assessment is used to calculate your initial score the first time you come to Compliance Score, before you configure any other assessments.</span></span> <span data-ttu-id="3efbc-120">合规性分数收集来自 Microsoft 365 解决方案的初始信号。</span><span class="sxs-lookup"><span data-stu-id="3efbc-120">Compliance Score collects initial signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="3efbc-121">你将快速了解你的组织是如何相对于关键数据保护标准和管理法规执行的，并查看建议采取的改进措施。</span><span class="sxs-lookup"><span data-stu-id="3efbc-121">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="3efbc-122">由于每个组织都有特定的需求，因此合规性分数取决于您设置和管理您自己的评估以帮助尽可能地减少和缓解风险。</span><span class="sxs-lookup"><span data-stu-id="3efbc-122">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="assessment-creation-overview"></a><span data-ttu-id="3efbc-123">评估创建概述</span><span class="sxs-lookup"><span data-stu-id="3efbc-123">Assessment creation overview</span></span>

<span data-ttu-id="3efbc-124">您可以通过三种方法来设置评估：</span><span class="sxs-lookup"><span data-stu-id="3efbc-124">There are three ways you can set up assessments:</span></span>

1. <span data-ttu-id="3efbc-125">选择 "已准备好使用评估"。</span><span class="sxs-lookup"><span data-stu-id="3efbc-125">Choose a ready to use assessment.</span></span>
2. <span data-ttu-id="3efbc-126">修改评估的模板以满足您自己的需求。</span><span class="sxs-lookup"><span data-stu-id="3efbc-126">Modify the template of an assessment to suit your own needs.</span></span>
3. <span data-ttu-id="3efbc-127">创建您自己的自定义评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-127">Create your own Custom Assessment.</span></span>

<span data-ttu-id="3efbc-128">用户必须拥有全局管理员、合规性管理员、合规性数据管理员或安全管理员角色才能创建或修改评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-128">Users must hold a role of global administrator, compliance administrator, compliance data administrator, or security administrator in order to create or modify assessments.</span></span> <span data-ttu-id="3efbc-129">了解有关[角色和权限](compliance-score-setup.md#set-user-permissions-and-assign-roles)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efbc-129">Learn more about [roles and permissions](compliance-score-setup.md#set-user-permissions-and-assign-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="3efbc-130">在符合性分数中创建或修改的任何评估也将在合规性管理器中反映出来。</span><span class="sxs-lookup"><span data-stu-id="3efbc-130">Any assessments created or modified in Compliance Score will be also be reflected in Compliance Manager.</span></span> <span data-ttu-id="3efbc-131">了解有关[合规性分数和合规性管理器之间关系](compliance-score.md#relationship-to-compliance-manager)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efbc-131">Learn more about the [relationship between Compliance Score and Compliance Manager](compliance-score.md#relationship-to-compliance-manager).</span></span>

### <a name="ready-to-use-assessments"></a><span data-ttu-id="3efbc-132">准备好使用评估</span><span class="sxs-lookup"><span data-stu-id="3efbc-132">Ready to use assessments</span></span>

<span data-ttu-id="3efbc-133">通过从符合性分数选择用于创建评估的[模板](compliance-score-templates.md)中进行选择，启动合规性旅程。</span><span class="sxs-lookup"><span data-stu-id="3efbc-133">Kickstart your compliance journey by choosing from among Compliance Score’s selection of [templates](compliance-score-templates.md) for creating assessments.</span></span> <span data-ttu-id="3efbc-134">模板包含每个特定评估所需的控件和改进操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-134">Templates contain the controls and improvement actions necessary for each particular assessment.</span></span> <span data-ttu-id="3efbc-135">合规性分数的模板涵盖与行业、地区和常见数据保护标准（如 GDPR 和 ISO 27001）对应的法规和认证。</span><span class="sxs-lookup"><span data-stu-id="3efbc-135">Compliance Score’s templates cover regulations and certifications that align to industries, regions, and common data protection standards, such as GDPR and ISO 27001.</span></span>

<span data-ttu-id="3efbc-136">**若要设置评估**，请在[从向导开始构建评估](#create-an-assessment)时选择其中一个模板。</span><span class="sxs-lookup"><span data-stu-id="3efbc-136">**To set up an assessment**, choose one of the templates when you start  [building the assessment from the wizard](#create-an-assessment).</span></span>

### <a name="modify-the-template-of-an-assessment"></a><span data-ttu-id="3efbc-137">修改评估的模板</span><span class="sxs-lookup"><span data-stu-id="3efbc-137">Modify the template of an assessment</span></span>

<span data-ttu-id="3efbc-138">您可以修改评估合规性分数模板以便更好地满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="3efbc-138">You have the ability to modify Compliance Score templates for assessments in order to better suit your organization’s needs.</span></span> <span data-ttu-id="3efbc-139">例如，如果您通常需要遵守 HIPAA 但需要其他数据保护或安全控制，则可以采用 HIPAA 模板并添加自己的自定义字段，以创建新的评估，以根据您所需的方式监视进度。</span><span class="sxs-lookup"><span data-stu-id="3efbc-139">For example, if you generally need to comply with HIPAA but require additional data protection or security controls, you can take our HIPAA template and add your own custom fields to create a new assessment that monitors your progress in the ways you require.</span></span> <span data-ttu-id="3efbc-140">在公共预览版中，需要转到合规性管理器来修改模板。</span><span class="sxs-lookup"><span data-stu-id="3efbc-140">During public preview, you’ll need to go to Compliance Manger to modify templates.</span></span>

<span data-ttu-id="3efbc-141">**若要修改评估的模板**，请按照以下说明操作：</span><span class="sxs-lookup"><span data-stu-id="3efbc-141">**To modify the template of an assessment**, follow these instructions:</span></span>

1. <span data-ttu-id="3efbc-142">查看合规性分数中的可用模板列表，以确定要修改的[模板](compliance-score-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="3efbc-142">View the list of available [templates](compliance-score-templates.md) in Compliance Score to determine which one you want to modify.</span></span>
2. <span data-ttu-id="3efbc-143">[若要使用扩展过程自定义模板，请参阅合规性管理器说明](working-with-compliance-manager.md#customize-a-template-through-the-extension-process)。</span><span class="sxs-lookup"><span data-stu-id="3efbc-143">See the [Compliance Manager instructions to customize a template using the extension process](working-with-compliance-manager.md#customize-a-template-through-the-extension-process).</span></span>
3. <span data-ttu-id="3efbc-144">创建模板并将其导入到合规性管理器之后，您就可以在合规性分数中创建新的评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-144">Once you’ve created your template and imported it into Compliance Manger, you can then create your new assessment in Compliance Score.</span></span> <span data-ttu-id="3efbc-145">按照使用 "[评估创建向导](#create-an-assessment)" 生成评估的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-145">Follow the process of building your assessment using the [assessment creation wizard](#create-an-assessment).</span></span>

> [!NOTE]
> <span data-ttu-id="3efbc-146">详细了解公共预览版中[合规性分数和合规性管理器之间的关系](compliance-score.md#relationship-to-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="3efbc-146">Learn  more about the [relationship between Compliance Score and Compliance Manager](compliance-score.md#relationship-to-compliance-manager) during public preview.</span></span>

### <a name="create-your-own-custom-assessment"></a><span data-ttu-id="3efbc-147">创建自己的自定义评估</span><span class="sxs-lookup"><span data-stu-id="3efbc-147">Create your own Custom Assessment</span></span>

<span data-ttu-id="3efbc-148">您可以从头开始创建自己的评估，以准确地跟踪您的组织所需的内容。</span><span class="sxs-lookup"><span data-stu-id="3efbc-148">You can create your own assessment entirely from scratch to track precisely what your organization needs.</span></span> <span data-ttu-id="3efbc-149">与上面所述的修改过程一样，创建您自己的评估需要您先在合规性管理器中创建自己的评估模板。</span><span class="sxs-lookup"><span data-stu-id="3efbc-149">As with the modification process outlined above, creating your own assessment requires you to first create your own template for the assessment in Compliance Manager.</span></span>

<span data-ttu-id="3efbc-150">**若要创建自己的自定义评估**，请按照以下说明操作：</span><span class="sxs-lookup"><span data-stu-id="3efbc-150">**To create your own Custom Assessment**, follow these instructions:</span></span>

1. <span data-ttu-id="3efbc-151">阅读如何[在合规性管理器中创建自己的模板](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager)。</span><span class="sxs-lookup"><span data-stu-id="3efbc-151">Read how to [create your own template in Compliance Manager](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager).</span></span>
2. <span data-ttu-id="3efbc-152">创建模板并将其导入到合规性管理器之后，您就可以在合规性分数中创建新的评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-152">Once you’ve created your template and imported it into Compliance Manger, you can then create your new assessment in Compliance Score.</span></span> <span data-ttu-id="3efbc-153">按照使用 "[评估创建向导](#create-an-assessment)" 生成评估的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-153">Follow the process of building your assessment using the [assessment creation wizard](#create-an-assessment).</span></span>

## <a name="understand-groups-before-creating-assessments"></a><span data-ttu-id="3efbc-154">在创建评估之前了解组</span><span class="sxs-lookup"><span data-stu-id="3efbc-154">Understand groups before creating assessments</span></span>

<span data-ttu-id="3efbc-155">在创建或修改评估之前，请务必了解组的工作方式。</span><span class="sxs-lookup"><span data-stu-id="3efbc-155">Before you create or modify assessments, it’s important to understand how groups work.</span></span> <span data-ttu-id="3efbc-156">在创建评估时，需要在该过程中将其分配给一个组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-156">When you create an assessment, you’ll need to assign it to a group during that process.</span></span> <span data-ttu-id="3efbc-157">因此，我们建议您在创建评估之前规划评估的分组策略。</span><span class="sxs-lookup"><span data-stu-id="3efbc-157">We therefore recommend planning a grouping strategy for your assessments before you create assessments.</span></span>

### <a name="what-are-groups"></a><span data-ttu-id="3efbc-158">什么是组</span><span class="sxs-lookup"><span data-stu-id="3efbc-158">What are groups</span></span>

<span data-ttu-id="3efbc-159">组是允许您组织评估的容器。</span><span class="sxs-lookup"><span data-stu-id="3efbc-159">Groups are containers that allow you to organize assessments.</span></span> <span data-ttu-id="3efbc-160">您可以按符合您的方式对评估进行分组，如按年或按规定进行分组，或者基于组织的部门或地理位置进行分组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-160">You can group assessments in a way that is logical to you, such as by year or regulation, or based on your organization's divisions or geographies.</span></span> <span data-ttu-id="3efbc-161">以下是两个组及其基础评估的示例：</span><span class="sxs-lookup"><span data-stu-id="3efbc-161">Below are examples of two groups and their underlying assessments:</span></span>

- <span data-ttu-id="3efbc-162">**FFIEC 是评估2020**</span><span class="sxs-lookup"><span data-stu-id="3efbc-162">**FFIEC IS assessments 2020**</span></span>
  - <span data-ttu-id="3efbc-163">Office 365 + FFIEC 是</span><span class="sxs-lookup"><span data-stu-id="3efbc-163">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="3efbc-164">Intune + FFIEC 为</span><span class="sxs-lookup"><span data-stu-id="3efbc-164">Intune + FFIEC IS</span></span>
- <span data-ttu-id="3efbc-165">**数据安全性和隐私评估**</span><span class="sxs-lookup"><span data-stu-id="3efbc-165">**Data security and privacy assessments**</span></span>
  - <span data-ttu-id="3efbc-166">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="3efbc-166">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="3efbc-167">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="3efbc-167">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="3efbc-168">当同一个组中的两个不同评估共享由您管理的改进操作时，您对操作的实现详细信息或状态所做的任何更新将自动同步到组中任何其他评估中的相同操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-168">When two different assessments in the same group share improvement actions that are managed by you, any updates you make to an action's implementation details or status will automatically synchronize to the same action in any other assessment in the group.</span></span> <span data-ttu-id="3efbc-169">此同步使您能够实现一个改进操作，并在多个管理法规方面满足几个要求。</span><span class="sxs-lookup"><span data-stu-id="3efbc-169">This synchronization allows you to implement one improvement action and meet several requirements across multiple regulations.</span></span>

### <a name="how-to-create-a-group"></a><span data-ttu-id="3efbc-170">如何创建组</span><span class="sxs-lookup"><span data-stu-id="3efbc-170">How to create a group</span></span>

<span data-ttu-id="3efbc-171">在[创建新评估](#create-an-assessment)的过程中，您需要创建一个组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-171">You create a group during the process of [creating a new assessment](#create-an-assessment).</span></span>

<span data-ttu-id="3efbc-172">无法将组创建为独立实体;一个组必须至少包含一个评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-172">Groups cannot be created as standalone entities; a group must contain at least one assessment.</span></span> <span data-ttu-id="3efbc-173">若要创建组，必须首先创建要放入组中的评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-173">In order to create a group, you must first create an assessment to put in the group.</span></span>

### <a name="what-to-know-when-working-with-groups"></a><span data-ttu-id="3efbc-174">使用组时需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="3efbc-174">What to know when working with groups</span></span>

- <span data-ttu-id="3efbc-175">组名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3efbc-175">Group names must be unique within your organization.</span></span>
- <span data-ttu-id="3efbc-176">组没有安全属性。</span><span class="sxs-lookup"><span data-stu-id="3efbc-176">Groups don't have security properties.</span></span> <span data-ttu-id="3efbc-177">所有权限都与评估相关联。</span><span class="sxs-lookup"><span data-stu-id="3efbc-177">All permissions are associated with assessments.</span></span>
- <span data-ttu-id="3efbc-178">将评估添加到组后，不能更改分组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-178">Once you add an assessment to a group, the grouping cannot be changed.</span></span>
- <span data-ttu-id="3efbc-179">在同一组中的不同评估中的相关评估控件在完成后将自动更新。</span><span class="sxs-lookup"><span data-stu-id="3efbc-179">Related assessment controls in different assessments within the same group automatically update when completed.</span></span>
- <span data-ttu-id="3efbc-180">如果将新评估添加到现有组中，则会将该组中评估的常见信息复制到新评估中。</span><span class="sxs-lookup"><span data-stu-id="3efbc-180">If you add a new assessment to an existing group, common information from assessments in that group are copied to the new assessment.</span></span>
- <span data-ttu-id="3efbc-181">组可以包含对同一认证或法规的评估，但每个组只能包含针对特定产品认证对的一个评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-181">Groups can contain assessments for the same certification or regulation, but each group can only contain one assessment for a specific product-certification pair.</span></span> <span data-ttu-id="3efbc-182">例如，组不能包含针对 Office 365 和 NIST CSF 的两个评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-182">For example, a group can't contain two assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="3efbc-183">仅当一个组与同一个产品的对应证书或法规不同时，该组才可以包含对同一产品的多个评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-183">A group can contain multiple assessments for the same product only if the corresponding certification or regulation for each one is different.</span></span>
- <span data-ttu-id="3efbc-184">删除评估会破坏该评估与组之间的关系。</span><span class="sxs-lookup"><span data-stu-id="3efbc-184">Deleting an assessment breaks the relationship between that assessment and the group.</span></span>
- <span data-ttu-id="3efbc-185">无法删除组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-185">Groups can't be deleted.</span></span>
- <span data-ttu-id="3efbc-186">当对多个组中出现的改进进行更改时，该更改将反映在该改进操作的所有实例中。</span><span class="sxs-lookup"><span data-stu-id="3efbc-186">When a change is made to an improvement that appears in multiple groups, that change is reflected in all instances of that improvement action.</span></span>

## <a name="create-an-assessment"></a><span data-ttu-id="3efbc-187">创建评估</span><span class="sxs-lookup"><span data-stu-id="3efbc-187">Create an assessment</span></span>

<span data-ttu-id="3efbc-188">若要在合规性分数中创建评估，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3efbc-188">To create an assessment in Compliance Score, follow the steps below:</span></span>

1. <span data-ttu-id="3efbc-189">从评估页中，选择 "**添加评估**"。</span><span class="sxs-lookup"><span data-stu-id="3efbc-189">From your assessments page, select **Add assessment**.</span></span> <span data-ttu-id="3efbc-190">在大型浮出控件窗格中将显示一个评估向导。</span><span class="sxs-lookup"><span data-stu-id="3efbc-190">An assessment wizard will appear in a large flyout pane.</span></span>

2. <span data-ttu-id="3efbc-191">**选择一个模板：** 选择要用作评估基础的模板。</span><span class="sxs-lookup"><span data-stu-id="3efbc-191">**Select a template:** Choose a template to serve as the basis for your assessment.</span></span> <span data-ttu-id="3efbc-192">您可以选择 "已准备好使用" 模板，也可以选择已修改或创建的模板。</span><span class="sxs-lookup"><span data-stu-id="3efbc-192">You can choose a ready to use template, or a template you’ve modified or created.</span></span> <span data-ttu-id="3efbc-193">选择您选择的模板旁边的单选按钮，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="3efbc-193">Select the radio button next to your chosen template, then select  **Next**.</span></span>

> [!NOTE]
> <span data-ttu-id="3efbc-194">有关[创建和修改模板的说明](working-with-compliance-manager.md#templates)，请参阅合规性管理器中处理的过程。</span><span class="sxs-lookup"><span data-stu-id="3efbc-194">See [instructions for creating and modifying templates](working-with-compliance-manager.md#templates), a process handled in Compliance Manager.</span></span>

3. <span data-ttu-id="3efbc-195">**名称和组：** 在 "**评估名称**" 字段中输入评估的名称。</span><span class="sxs-lookup"><span data-stu-id="3efbc-195">**Name and group:** Enter a name for your assessment in the **Assessment name** field.</span></span> <span data-ttu-id="3efbc-196">评估名称在组中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3efbc-196">Assessment names must be unique within groups.</span></span> <span data-ttu-id="3efbc-197">如果评估的名称与任何给定组中的另一个评估的名称相匹配，则会收到一条错误，要求您创建一个不同的名称。</span><span class="sxs-lookup"><span data-stu-id="3efbc-197">If the name of your assessment matches the name of another assessment in any given group, you’ll receive an error asking you to create a different name.</span></span>

4. <span data-ttu-id="3efbc-198">将评估服务分配给一个组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-198">Assign your assessment to a group.</span></span> <span data-ttu-id="3efbc-199">您可以：</span><span class="sxs-lookup"><span data-stu-id="3efbc-199">You can either:</span></span>
    - <span data-ttu-id="3efbc-200">选择 "**使用现有组**将其分配给已创建的组";和</span><span class="sxs-lookup"><span data-stu-id="3efbc-200">Select **Use existing group** to assign it to a group you’ve already created; or</span></span>
    - <span data-ttu-id="3efbc-201">选择 "**创建新组**" 以创建新组，并将此评估分配给它。</span><span class="sxs-lookup"><span data-stu-id="3efbc-201">Select **Create new group** to create a new group and assign this assessment to it.</span></span> <span data-ttu-id="3efbc-202">确定组的名称，并将其输入到单选按钮下的字段中。</span><span class="sxs-lookup"><span data-stu-id="3efbc-202">Determine a name for your group and enter it in the field beneath the radio button.</span></span>

5. <span data-ttu-id="3efbc-203">**审阅并完成：** 向导的最后一个屏幕显示为评估选择的模板、名称和组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-203">**Review and finish:** The last screen of the wizard shows the template, name, and group chosen for the assessment.</span></span> <span data-ttu-id="3efbc-204">您可以从屏幕上的链接中编辑这些设置中的任何设置，这将返回到向导中的相关步骤。</span><span class="sxs-lookup"><span data-stu-id="3efbc-204">You can edit any of these settings from the links on the screen, which take you back to the relevant steps in the wizard.</span></span> <span data-ttu-id="3efbc-205">一旦您对设置感到满意，请选择 "**创建评估**"。</span><span class="sxs-lookup"><span data-stu-id="3efbc-205">Once you’re satisfied with the settings, select **Create assessment**.</span></span>

6. <span data-ttu-id="3efbc-206">下一个屏幕确认您已成功创建新的评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-206">The next screen confirms that you’ve successfully created your new assessment.</span></span> <span data-ttu-id="3efbc-207">选择 "**完成**" 以关闭向导，新评估的 "详细信息" 页将显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="3efbc-207">Select **Done** to close the wizard, and your new assessment's details page will appear on the screen.</span></span>

<span data-ttu-id="3efbc-208">如果在选择 "**创建评估**" 后看到 "**评估失败**" 屏幕，请选择 "**重试**" 以重新创建评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-208">If you see an **Assessment failed** screen after selecting **Create assessment**, select **Try again** to re-create your assessment.</span></span>

## <a name="delete-an-assessment"></a><span data-ttu-id="3efbc-209">删除评估</span><span class="sxs-lookup"><span data-stu-id="3efbc-209">Delete an assessment</span></span>

<span data-ttu-id="3efbc-210">删除评估会将其从评估页面上的列表中删除。</span><span class="sxs-lookup"><span data-stu-id="3efbc-210">Deleting an assessment removes it from the list on your assessments page.</span></span> <span data-ttu-id="3efbc-211">**删除评估是永久性的;您无法再取回它。**</span><span class="sxs-lookup"><span data-stu-id="3efbc-211">**Deleting an assessment is permanent; you cannot get it back.**</span></span> <span data-ttu-id="3efbc-212">如果想要再次进行相同的评估，则必须从头开始重新创建。</span><span class="sxs-lookup"><span data-stu-id="3efbc-212">If you want the same assessment again, it must be re-created from scratch.</span></span> <span data-ttu-id="3efbc-213">如果评估中的改进操作未在任何其他评估中显示，则在删除评估时将删除这些操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-213">If the improvement actions in the assessment do not appear in any other assessment, they will be deleted when the assessment is deleted.</span></span> <span data-ttu-id="3efbc-214">建议您先导出评估报告，然后再将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="3efbc-214">We recommend exporting a report of the assessment before you permanently delete it.</span></span>

<span data-ttu-id="3efbc-215">若要删除评估，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3efbc-215">To delete an assessment, follow the steps below:</span></span>

1. <span data-ttu-id="3efbc-216">从评估页中，选择要删除的评估以打开该评估的 "详细信息" 页。</span><span class="sxs-lookup"><span data-stu-id="3efbc-216">From your assessments page, select the assessment you wish to delete to open that assessment’s details page.</span></span>
2. <span data-ttu-id="3efbc-217">选择屏幕右上角的 "**删除评估**"。</span><span class="sxs-lookup"><span data-stu-id="3efbc-217">Select **Delete assessment** in the upper-right corner of your screen.</span></span>
3. <span data-ttu-id="3efbc-218">将显示一个窗口，要求您确认是否要永久删除该评估。</span><span class="sxs-lookup"><span data-stu-id="3efbc-218">A window will appear asking you to confirm that you want to permanently delete the assessment.</span></span> <span data-ttu-id="3efbc-219">选择 "**删除评估**" 以关闭该窗口。</span><span class="sxs-lookup"><span data-stu-id="3efbc-219">Select **Delete assessment** to close the window.</span></span> <span data-ttu-id="3efbc-220">你将收到一个确认窗口，指出评估已从合规性分数中删除。</span><span class="sxs-lookup"><span data-stu-id="3efbc-220">You’ll get a confirmation window that your assessment was deleted from Compliance Score.</span></span>

<span data-ttu-id="3efbc-221">如果您删除组中的唯一评估，则该组也将从合规性分数中删除。</span><span class="sxs-lookup"><span data-stu-id="3efbc-221">If you delete the only assessment in a group, then that group is also deleted from Compliance Score.</span></span>

## <a name="monitor-assessment-progress-and-controls"></a><span data-ttu-id="3efbc-222">监视评估进度和控制</span><span class="sxs-lookup"><span data-stu-id="3efbc-222">Monitor assessment progress and controls</span></span>

<span data-ttu-id="3efbc-223">每个评估都有一个详细信息页面，可在完成评估的过程中提供一览的一览视图。</span><span class="sxs-lookup"><span data-stu-id="3efbc-223">Each assessment has a details page that gives an at-a-glance view of your progress in completing the assessment.</span></span> <span data-ttu-id="3efbc-224">页面显示您在完成控件中的进度，以及这些控件中的关键改进操作的测试状态。</span><span class="sxs-lookup"><span data-stu-id="3efbc-224">The page shows your progress in completing controls, and the test status of key improvement actions within those controls.</span></span>

### <a name="overview-tab"></a><span data-ttu-id="3efbc-225">概述选项卡</span><span class="sxs-lookup"><span data-stu-id="3efbc-225">Overview tab</span></span>

<span data-ttu-id="3efbc-226">"概述" 选项卡包含一个显示评估结束百分比的图形。</span><span class="sxs-lookup"><span data-stu-id="3efbc-226">The overview tab contains a graph showing your percentage toward completion of the assessment.</span></span> <span data-ttu-id="3efbc-227">此图包含来自你所拥有的操作的点细目，以及 Microsoft 所拥有的操作的点，因此你可以看到完成此评估所需的更多分数。</span><span class="sxs-lookup"><span data-stu-id="3efbc-227">This graph contains a breakdown of points from actions you own, and points from actions owned by Microsoft, so you can see how many more points you need to complete the assessment.</span></span>

<span data-ttu-id="3efbc-228">评估中的控件的主要改进操作是按对赢得积分的最大潜在影响顺序列出的。</span><span class="sxs-lookup"><span data-stu-id="3efbc-228">The key improvement actions for controls in the assessment are listed in order of greatest potential impact to earn points.</span></span> <span data-ttu-id="3efbc-229">关联的关系图详细说明了您的改进操作的聚合测试状态，以便您可以快速估量已测试的内容以及仍需要完成的操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-229">The associated graph details the aggregated test status of your improvement actions so you can quickly gauge what has been tested and what still needs to be done.</span></span>

<span data-ttu-id="3efbc-230">若要访问各个改进操作，请转到 "控件" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3efbc-230">To access individual improvement actions, go to the controls tab.</span></span>

### <a name="controls-tab"></a><span data-ttu-id="3efbc-231">控件选项卡</span><span class="sxs-lookup"><span data-stu-id="3efbc-231">Controls tab</span></span>

<span data-ttu-id="3efbc-232">"控件" 选项卡显示映射到评估的每个控件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efbc-232">The controls tab displays detailed information for each control mapped to the assessment.</span></span> <span data-ttu-id="3efbc-233">**控件状态细分**图按系列显示控件的状态，因此您可以一目了然地查看控件的哪些组需要关注。</span><span class="sxs-lookup"><span data-stu-id="3efbc-233">A **control status breakdown** chart shows the status of controls by family, so you can see at a glance which groupings of controls need attention.</span></span>

<span data-ttu-id="3efbc-234">在图表下，表中列出了评估中每个控件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3efbc-234">Beneath the chart, a table lists detailed information about each control within the assessment.</span></span> <span data-ttu-id="3efbc-235">控件按控件系列分组。</span><span class="sxs-lookup"><span data-stu-id="3efbc-235">Controls are grouped by control family.</span></span> <span data-ttu-id="3efbc-236">展开每个系列名称以显示它所包含的各个控件。</span><span class="sxs-lookup"><span data-stu-id="3efbc-236">Expand each family name to reveal the individual controls it contains.</span></span> <span data-ttu-id="3efbc-237">为每个控件列出的信息包括：</span><span class="sxs-lookup"><span data-stu-id="3efbc-237">The information listed for each control includes:</span></span>

- <span data-ttu-id="3efbc-238">**控件标题**</span><span class="sxs-lookup"><span data-stu-id="3efbc-238">**Control title**</span></span>
- <span data-ttu-id="3efbc-239">**状态**：反映控件中的改进操作的测试状态</span><span class="sxs-lookup"><span data-stu-id="3efbc-239">**Status**: reflects the test status of the improvement actions within the control</span></span> 
    - <span data-ttu-id="3efbc-240">已**通过**-所有改进操作的测试状态均为 "已通过"，或者至少有一个已传递且其余值为 "超出范围"</span><span class="sxs-lookup"><span data-stu-id="3efbc-240">**Passed** - all improvement actions have a test status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    -  <span data-ttu-id="3efbc-241">**失败**-至少有一个改进操作的测试状态为 "Failed"</span><span class="sxs-lookup"><span data-stu-id="3efbc-241">**Failed** - at least one improvement action has a test status of “failed”</span></span>
    - <span data-ttu-id="3efbc-242">**None** -尚未测试所有改进操作</span><span class="sxs-lookup"><span data-stu-id="3efbc-242">**None** - all improvement actions have not been tested</span></span>
    - <span data-ttu-id="3efbc-243">**超出范围**-此评估的所有改进操作均超出范围</span><span class="sxs-lookup"><span data-stu-id="3efbc-243">**Out of scope** - all improvement actions are out of scope for this assessment</span></span>
    - <span data-ttu-id="3efbc-244">**进度**改善操作的状态不是上面列出的状态，可能包括 "正在进行中"、"部分信贷" 或 "未检测"。</span><span class="sxs-lookup"><span data-stu-id="3efbc-244">**In progress** - improvement actions have a status other than the ones listed above, which could include “in progress,” “partial credit,” or “undetected”</span></span>
- <span data-ttu-id="3efbc-245">**控件 ID**：控件的标识号，由其对应的法规、标准或策略分配</span><span class="sxs-lookup"><span data-stu-id="3efbc-245">**Control ID**: the control’s identification number, assigned by its corresponding regulation, standard, or policy</span></span>
- <span data-ttu-id="3efbc-246">**实现分数**：完成操作所得到的分数，即实现的总积分数</span><span class="sxs-lookup"><span data-stu-id="3efbc-246">**Points achieved**: the number of points earned by completing actions, out of the total number of achievable points</span></span> 
- <span data-ttu-id="3efbc-247">**您的操作**：要完成的操作的总数已完成的操作数</span><span class="sxs-lookup"><span data-stu-id="3efbc-247">**Your actions**: the number of your actions completed out of the total number of actions to be done</span></span>
- <span data-ttu-id="3efbc-248">**Microsoft 操作**： microsoft 完成的操作数</span><span class="sxs-lookup"><span data-stu-id="3efbc-248">**Microsoft actions**: the number of actions completed by Microsoft</span></span> 

<span data-ttu-id="3efbc-249">若要查看控件的详细信息，请从表的行中选择它。</span><span class="sxs-lookup"><span data-stu-id="3efbc-249">To view a control’s details, select it from its row in the table.</span></span> <span data-ttu-id="3efbc-250">"控件详细信息" 页将显示一个图，指示该控件中的操作的测试状态。</span><span class="sxs-lookup"><span data-stu-id="3efbc-250">The control details page shows a graph indicating the test status of the actions within that control.</span></span> <span data-ttu-id="3efbc-251">图下方的表格显示了该控件的关键改进操作。</span><span class="sxs-lookup"><span data-stu-id="3efbc-251">A table below the graph shows key improvement actions for that control.</span></span>

<span data-ttu-id="3efbc-252">从列表中选择 "改进操作"，以深入了解改进操作的详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="3efbc-252">Select an improvement action from the list to drill into the improvement action’s details page.</span></span> <span data-ttu-id="3efbc-253">详细信息页面显示了测试状态和实现说明，并启动了推荐的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3efbc-253">The details pages shows test status, implementation notes, and launch into the recommended solution.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="3efbc-254">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="3efbc-254">Learn more</span></span>
[<span data-ttu-id="3efbc-255">了解按合规性分数跟踪和评分的控制措施和改进措施。</span><span class="sxs-lookup"><span data-stu-id="3efbc-255">Understand how controls and improvement actions are tracked and scored by Compliance Score.</span></span>](compliance-score-methodology.md)

## <a name="export-an-assessment-report"></a><span data-ttu-id="3efbc-256">导出评估报告</span><span class="sxs-lookup"><span data-stu-id="3efbc-256">Export an assessment report</span></span>

<span data-ttu-id="3efbc-257">您可以按照[以下说明](working-with-compliance-manager.md#reports)将评估导出到您组织中的合规性利益干系人或外部审计员和管理机构的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="3efbc-257">You can export an assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators by [following these instructions](working-with-compliance-manager.md#reports).</span></span> <span data-ttu-id="3efbc-258">你需要访问合规性管理器以导出报告。</span><span class="sxs-lookup"><span data-stu-id="3efbc-258">You’ll  need to visit Compliance Manager to export the report.</span></span>

<span data-ttu-id="3efbc-259">报告是在导出的日期和时间进行评估的快照。</span><span class="sxs-lookup"><span data-stu-id="3efbc-259">The report is a snapshot of the assessment as of the date and time of the export.</span></span> <span data-ttu-id="3efbc-260">它包含由您和 Microsoft 管理的控件的详细信息，其中包括实施状态、测试日期、测试结果以及指向已上载证据文档的链接。</span><span class="sxs-lookup"><span data-stu-id="3efbc-260">It contains the details for controls managed by both you and Microsoft, including implementation status, test date, test results, and links to uploaded evidence documents.</span></span>