---
title: 自动应用保留标签来保留或删除内容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 创建和自动发布保留标签，以便你可以自动应用标签来保留所需内容并删除不需要的内容
ms.openlocfilehash: eb29a846f6a7352eec02683c70dad1b0a423bdfa
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127575"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="dfbba-103">自动应用保留标签来保留或删除内容</span><span class="sxs-lookup"><span data-stu-id="dfbba-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="dfbba-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="dfbba-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dfbba-105">[保留标签](retention.md)最强大的功能之一是能够将其自动应用于符合特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="dfbba-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="dfbba-106">此情况下，组织中的人员无需应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="dfbba-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="dfbba-107">Microsoft 365 会代为操作。</span><span class="sxs-lookup"><span data-stu-id="dfbba-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="dfbba-108">自动应用保留标签的功能非常强大，这是因为：</span><span class="sxs-lookup"><span data-stu-id="dfbba-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="dfbba-109">无需为用户提供有关所有分类的培训。</span><span class="sxs-lookup"><span data-stu-id="dfbba-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="dfbba-110">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="dfbba-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="dfbba-111">用户不再需要了解数据管理策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="dfbba-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="dfbba-112">当内容包含敏感信息、关键字或[可训练分类器](classifier-getting-started-with.md)的匹配项时，可以自动将保留标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="dfbba-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>
    
<span data-ttu-id="dfbba-113">将基于以下条件自动应用保留标签的流程：</span><span class="sxs-lookup"><span data-stu-id="dfbba-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![自动应用标签的角色和任务关系图](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="dfbba-115">按照以下说明进行两个管理步骤。</span><span class="sxs-lookup"><span data-stu-id="dfbba-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="dfbba-116">"自动策略" 使用服务侧标记（带条件）自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="dfbba-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="dfbba-117">执行以下操作时，还可使用标签策略自动应用保留标签：</span><span class="sxs-lookup"><span data-stu-id="dfbba-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="dfbba-118">将默认保留标签应用于 SharePoint 库、文件夹或文档集，以便自动标记该容器中未标记的内容</span><span class="sxs-lookup"><span data-stu-id="dfbba-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="dfbba-119">使用规则将保留标签应用于电子邮件</span><span class="sxs-lookup"><span data-stu-id="dfbba-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="dfbba-120">有关这些情况，请参阅 [在应用中创建和应用保留标签](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dfbba-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="dfbba-121">Before you begin</span></span>

<span data-ttu-id="dfbba-122">组织的全局管理员具有创建和编辑保留标签及其策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="dfbba-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="dfbba-123">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="dfbba-124">如何自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="dfbba-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="dfbba-125">首先，创建你的保留标签。</span><span class="sxs-lookup"><span data-stu-id="dfbba-125">First, create your retention label.</span></span> <span data-ttu-id="dfbba-126">然后创建 "自动策略" 以应用该标签。</span><span class="sxs-lookup"><span data-stu-id="dfbba-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="dfbba-127">如果已创建保留标签，请跳转到 [创建自动策略](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="dfbba-128">导航说明取决于你是否正在使用[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="dfbba-129">针对这两种情况提供了说明。</span><span class="sxs-lookup"><span data-stu-id="dfbba-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="dfbba-130">步骤 1：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="dfbba-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="dfbba-131">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="dfbba-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="dfbba-132">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="dfbba-132">If you are using records management:</span></span>
        - <span data-ttu-id="dfbba-133">“**解决方案**” > “**记录管理**” > “**文件计划**”选项卡 > + “**创建标签**” > “**保留标签**”</span><span class="sxs-lookup"><span data-stu-id="dfbba-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="dfbba-134">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="dfbba-134">If you are not using records management:</span></span>
       - <span data-ttu-id="dfbba-135">“**解决方案**” > “**信息治理**” > “**标签**”选项卡 > +“**创建标签**”</span><span class="sxs-lookup"><span data-stu-id="dfbba-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="dfbba-136">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="dfbba-136">Don't immediately see your option?</span></span> <span data-ttu-id="dfbba-137">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="dfbba-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="dfbba-138">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="dfbba-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="dfbba-139">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="dfbba-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="dfbba-140">有关文件计划描述符的信息，请参阅[使用文件计划管理保留标签](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="dfbba-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="dfbba-141">要使用保留标签将内容声明为记录，请启用“**使用标签将内容分类为“记录”**”复选框。</span><span class="sxs-lookup"><span data-stu-id="dfbba-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="dfbba-142">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”启动同一向导，以便在步骤 2 中更改标签说明和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="dfbba-143">或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。</span><span class="sxs-lookup"><span data-stu-id="dfbba-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="dfbba-144">步骤 2：创建自动应用策略</span><span class="sxs-lookup"><span data-stu-id="dfbba-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="dfbba-145">创建自动应用策略时，根据指定的条件，选择要自动应用到内容的保留标签。</span><span class="sxs-lookup"><span data-stu-id="dfbba-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="dfbba-146">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="dfbba-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="dfbba-147">如果你正在使用记录管理：“**信息治理**”：</span><span class="sxs-lookup"><span data-stu-id="dfbba-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="dfbba-148">“**解决方案**” > “**记录管理**” > “**标签策略**”选项卡 >“**自动应用标签**”</span><span class="sxs-lookup"><span data-stu-id="dfbba-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="dfbba-149">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="dfbba-149">If you are not using records management:</span></span>
        - <span data-ttu-id="dfbba-150">“**解决方案**” > “**信息治理**” > “**标签策略**”选项卡 >“**自动应用标签**”</span><span class="sxs-lookup"><span data-stu-id="dfbba-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="dfbba-151">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="dfbba-151">Don't immediately see your option?</span></span> <span data-ttu-id="dfbba-152">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="dfbba-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="dfbba-153">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="dfbba-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="dfbba-154">有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。</span><span class="sxs-lookup"><span data-stu-id="dfbba-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="dfbba-155">有关保留标签支持的位置的信息，请参阅[保留标签和位置](retention.md#retention-label-policies-and-locations)部分。</span><span class="sxs-lookup"><span data-stu-id="dfbba-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="dfbba-156">若要编辑现有自动应用标签策略，请将其选中，然后选择“**编辑策略**”启动同一向导，以便在步骤 2 中更改策略描述和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="dfbba-157">或者，选择任意可用的**编辑**选项，直接转到相关页面进行更新。</span><span class="sxs-lookup"><span data-stu-id="dfbba-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="dfbba-158">配置自动应用保留标签的条件</span><span class="sxs-lookup"><span data-stu-id="dfbba-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="dfbba-159">可将保留标签自动应用于包含以下各项的内容：</span><span class="sxs-lookup"><span data-stu-id="dfbba-159">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="dfbba-160">特定类型敏感信息</span><span class="sxs-lookup"><span data-stu-id="dfbba-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="dfbba-161">与你创建的查询匹配的特定关键字</span><span class="sxs-lookup"><span data-stu-id="dfbba-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="dfbba-162">可训练分类器的匹配项</span><span class="sxs-lookup"><span data-stu-id="dfbba-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="dfbba-163">将标签自动应用于包含特定类型敏感信息的内容</span><span class="sxs-lookup"><span data-stu-id="dfbba-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="dfbba-164">为敏感信息创建自动应用保留标签时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。</span><span class="sxs-lookup"><span data-stu-id="dfbba-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="dfbba-165">预配置每个策略模板以查找特定类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="dfbba-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="dfbba-166">例如，此处显示的模板用于查找美国 ITIN、SSN 和护照号码。</span><span class="sxs-lookup"><span data-stu-id="dfbba-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="dfbba-167">若要深入了解 DLP，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="dfbba-169">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span><span class="sxs-lookup"><span data-stu-id="dfbba-169">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="dfbba-170">In the example shown here, a retention label will be auto-applied only when:</span><span class="sxs-lookup"><span data-stu-id="dfbba-170">In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="dfbba-171">The content contains between 1 and 9 instances of any of these three sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="dfbba-171">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="dfbba-172">You can delete the **max** value so that it changes to **any**.</span><span class="sxs-lookup"><span data-stu-id="dfbba-172">You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="dfbba-173">检测到的敏感信息类型具有至少 75 的匹配准确度（或可信度）。</span><span class="sxs-lookup"><span data-stu-id="dfbba-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="dfbba-174">许多敏感信息类型都由多个模式定义，其中具有较高匹配准确度的模式需要发现较多证据（如关键字、日期或地址），而具有较低匹配准确度的模式需要较少的证据。</span><span class="sxs-lookup"><span data-stu-id="dfbba-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="dfbba-175">**最小**匹配准确度越低，内容越容易与条件匹配。</span><span class="sxs-lookup"><span data-stu-id="dfbba-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="dfbba-176">要详细了解这些选项，请参阅[微调规则以增加或降低匹配的难度](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="dfbba-178">将标签自动应用于包含关键字或可搜索属性的内容</span><span class="sxs-lookup"><span data-stu-id="dfbba-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="dfbba-179">You can auto-apply labels to content that satisfies certain conditions.</span><span class="sxs-lookup"><span data-stu-id="dfbba-179">You can auto-apply labels to content that satisfies certain conditions.</span></span> <span data-ttu-id="dfbba-180">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span><span class="sxs-lookup"><span data-stu-id="dfbba-180">The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties.</span></span> <span data-ttu-id="dfbba-181">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="dfbba-181">You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="dfbba-182">有关查询语法的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dfbba-182">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="dfbba-183">关键字查询语言 (KQL) 语法参考</span><span class="sxs-lookup"><span data-stu-id="dfbba-183">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="dfbba-184">Query-based labels use the search index to identify content.</span><span class="sxs-lookup"><span data-stu-id="dfbba-184">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="dfbba-185">For more information on valid searchable properties, see:</span><span class="sxs-lookup"><span data-stu-id="dfbba-185">For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="dfbba-186">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="dfbba-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="dfbba-187">已爬网和托管属性在 SharePoint Server 中的概述</span><span class="sxs-lookup"><span data-stu-id="dfbba-187">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="dfbba-188">示例查询：</span><span class="sxs-lookup"><span data-stu-id="dfbba-188">Examples queries:</span></span>

- <span data-ttu-id="dfbba-189">Exchange</span><span class="sxs-lookup"><span data-stu-id="dfbba-189">Exchange</span></span>
    - <span data-ttu-id="dfbba-190">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="dfbba-190">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="dfbba-191">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="dfbba-191">recipients:garthf</span></span><!--nolink--><span data-ttu-id="dfbba-192">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dfbba-192">@contoso.com</span></span>
- <span data-ttu-id="dfbba-193">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="dfbba-193">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="dfbba-194">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="dfbba-194">contenttype:contract</span></span>
    - <span data-ttu-id="dfbba-195">site:https</span><span class="sxs-lookup"><span data-stu-id="dfbba-195">site:https</span></span><!--nolink--><span data-ttu-id="dfbba-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="dfbba-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![查询编辑器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="dfbba-198">使用可训练分类器向内容自动应用标签</span><span class="sxs-lookup"><span data-stu-id="dfbba-198">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="dfbba-199">选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。</span><span class="sxs-lookup"><span data-stu-id="dfbba-199">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="dfbba-200">内置分类器包含**简历**、**源代码**、**有针对性的骚扰**、**侮辱**和**威胁**：</span><span class="sxs-lookup"><span data-stu-id="dfbba-200">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![选择可训练分类器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="dfbba-202">我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="dfbba-202">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="dfbba-203">请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。</span><span class="sxs-lookup"><span data-stu-id="dfbba-203">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="dfbba-204">我们建议改用**针对性的骚扰**、**侮辱**和**猥亵**内置分类器。</span><span class="sxs-lookup"><span data-stu-id="dfbba-204">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="dfbba-205">要通过此选项自动应用标签，SharePoint Online 网站和邮箱必须至少有 10 MB 的数据。</span><span class="sxs-lookup"><span data-stu-id="dfbba-205">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="dfbba-206">有关可训练分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-206">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="dfbba-207">有关示例配置，请参阅[如何做好准备并使用内置分类器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-207">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="dfbba-208">保留标签需要多长时间才能生效</span><span class="sxs-lookup"><span data-stu-id="dfbba-208">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="dfbba-209">自动应用保留标签时，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。</span><span class="sxs-lookup"><span data-stu-id="dfbba-209">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="dfbba-211">更新保留标签及其策略</span><span class="sxs-lookup"><span data-stu-id="dfbba-211">Updating retention labels and their policies</span></span>

<span data-ttu-id="dfbba-212">在编辑保留标签或自动应用策略，并且该保留标签已应用到内容时，更新后的设置将自动应用于此内容以及新标识的内容。</span><span class="sxs-lookup"><span data-stu-id="dfbba-212">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="dfbba-213">某些设置无法在创建并保存标签或策略后更改，包括：</span><span class="sxs-lookup"><span data-stu-id="dfbba-213">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="dfbba-214">除保留期外的保留设置，除非已将标签配置为根据创建的时间保留或删除内容。</span><span class="sxs-lookup"><span data-stu-id="dfbba-214">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="dfbba-215">用于分类为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="dfbba-215">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dfbba-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dfbba-216">Next steps</span></span>

<span data-ttu-id="dfbba-217">请考虑将保留标签与另一种形式的自动化配合使用，[事件驱动的保留](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-217">Consider using retention labels with another form of automation, [event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="dfbba-218">使用此配置时，将通过你标识的事件触发保留开始。</span><span class="sxs-lookup"><span data-stu-id="dfbba-218">When you use this configuration, the start of retention is triggered by an event that you identify.</span></span> <span data-ttu-id="dfbba-219">可通过自动策略或标签策略使用事件驱动的保留。</span><span class="sxs-lookup"><span data-stu-id="dfbba-219">You can use event-driven retention with an auto-policy or a label policy.</span></span>

<span data-ttu-id="dfbba-220">有关使用 SharePont 中的托管属性来自动应用保留标签并实施事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbba-220">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>