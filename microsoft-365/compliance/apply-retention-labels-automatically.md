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
ms.openlocfilehash: dc525a9f7a2ea97f61f03320495eea737465cfd9
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171300"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="44992-103">自动应用保留标签来保留或删除内容</span><span class="sxs-lookup"><span data-stu-id="44992-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="44992-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="44992-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="44992-105">[保留标签](retention.md)最强大的功能之一是能够将其自动应用于符合特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="44992-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="44992-106">此情况下，组织中的人员无需应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="44992-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="44992-107">Microsoft 365 会代为操作。</span><span class="sxs-lookup"><span data-stu-id="44992-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="44992-108">自动应用保留标签的功能非常强大，这是因为：</span><span class="sxs-lookup"><span data-stu-id="44992-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="44992-109">无需为用户提供有关所有分类的培训。</span><span class="sxs-lookup"><span data-stu-id="44992-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="44992-110">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="44992-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="44992-111">用户不再需要了解数据管理策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="44992-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="44992-112">当内容包含敏感信息、关键字或可搜索属性，或者[可训练分类器](classifier-get-started-with.md)的匹配项时，可以自动将保留标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="44992-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

<span data-ttu-id="44992-113">将基于以下条件自动应用保留标签的流程：</span><span class="sxs-lookup"><span data-stu-id="44992-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![自动应用标签的角色和任务关系图](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="44992-115">按照以下说明进行两个管理步骤。</span><span class="sxs-lookup"><span data-stu-id="44992-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="44992-116">"自动策略" 使用服务侧标记（带条件）自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="44992-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="44992-117">执行以下操作时，还可使用标签策略自动应用保留标签：</span><span class="sxs-lookup"><span data-stu-id="44992-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="44992-118">将默认保留标签应用于 SharePoint 库、文件夹或文档集，以便自动标记该容器中未标记的内容</span><span class="sxs-lookup"><span data-stu-id="44992-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="44992-119">使用规则将保留标签应用于电子邮件</span><span class="sxs-lookup"><span data-stu-id="44992-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="44992-120">有关这些情况，请参阅 [在应用中创建和应用保留标签](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="44992-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="44992-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="44992-121">Before you begin</span></span>

<span data-ttu-id="44992-122">组织的全局管理员拥有创建和编辑保留标签及其策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="44992-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="44992-123">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="44992-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="44992-124">如何自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="44992-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="44992-125">首先，创建你的保留标签。</span><span class="sxs-lookup"><span data-stu-id="44992-125">First, create your retention label.</span></span> <span data-ttu-id="44992-126">然后创建 "自动策略" 以应用该标签。</span><span class="sxs-lookup"><span data-stu-id="44992-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="44992-127">如果已创建保留标签，请跳转到 [创建自动策略](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="44992-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="44992-128">导航说明取决于你是否正在使用[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="44992-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="44992-129">针对这两种情况提供了说明。</span><span class="sxs-lookup"><span data-stu-id="44992-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="44992-130">步骤 1：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="44992-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="44992-131">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="44992-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="44992-132">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="44992-132">If you are using records management:</span></span>
        - <span data-ttu-id="44992-133">“**解决方案**” > “**记录管理**” > “**文件计划**”选项卡 > + “**创建标签**” > “**保留标签**”</span><span class="sxs-lookup"><span data-stu-id="44992-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="44992-134">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="44992-134">If you are not using records management:</span></span>
       - <span data-ttu-id="44992-135">“**解决方案**” > “**信息治理**” > “**标签**”选项卡 > +“**创建标签**”</span><span class="sxs-lookup"><span data-stu-id="44992-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="44992-136">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="44992-136">Don't immediately see your option?</span></span> <span data-ttu-id="44992-137">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="44992-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="44992-138">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="44992-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="44992-139">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="44992-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="44992-140">有关文件计划描述符的信息，请参阅[使用文件计划管理保留标签](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="44992-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="44992-141">若要使用保留标签声明[记录](records-management.md#records)，请启用“**将项目标记为记录**”的选项。</span><span class="sxs-lookup"><span data-stu-id="44992-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="44992-142">创建标签后，你会看到用于发布标签、自动应用标签或 仅保存标签的选项：请选择“**将此标签自动应用到特定的内容类型**”，然后选择“**完成**”以启动“创建自动标记向导”，该向导将直接带你跳转到以下过程中的第 2 步。</span><span class="sxs-lookup"><span data-stu-id="44992-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="44992-143">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”来启动“编辑保留向导”，这个向导使你能够更改来自第 2 步的标签说明和任何[符合条件的设置](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="44992-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="44992-144">步骤 2：创建自动应用策略</span><span class="sxs-lookup"><span data-stu-id="44992-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="44992-145">创建自动应用策略时，根据指定的条件，选择要自动应用到内容的保留标签。</span><span class="sxs-lookup"><span data-stu-id="44992-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="44992-146">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="44992-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="44992-147">如果你正在使用记录管理：“**信息治理**”：</span><span class="sxs-lookup"><span data-stu-id="44992-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="44992-148">**“解决方案”** > **“记录管理”** > **“标签策略”** 选项卡 > **“自动应用标签”**</span><span class="sxs-lookup"><span data-stu-id="44992-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="44992-149">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="44992-149">If you are not using records management:</span></span>
        - <span data-ttu-id="44992-150">**“解决方案”** > **“信息治理”** > **“标签策略”** 选项卡 > **“自动应用标签”**</span><span class="sxs-lookup"><span data-stu-id="44992-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="44992-151">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="44992-151">Don't immediately see your option?</span></span> <span data-ttu-id="44992-152">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="44992-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="44992-153">按照“创建自动标记向导”中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="44992-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="44992-154">有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。</span><span class="sxs-lookup"><span data-stu-id="44992-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="44992-155">有关保留标签支持的位置的信息，请参阅[保留标签和位置](retention.md#retention-label-policies-and-locations)部分。</span><span class="sxs-lookup"><span data-stu-id="44992-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="44992-156">若要编辑现有的自动应用策略，请将其选中以启动“编辑保留策略向导”，该向导可用于更改从第 2 步中选定的保留标签和的任何[符合条件的设置](#updating-retention-labels-and-their-policies) 。</span><span class="sxs-lookup"><span data-stu-id="44992-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="44992-157">配置自动应用保留标签的条件</span><span class="sxs-lookup"><span data-stu-id="44992-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="44992-158">可将保留标签自动应用于包含以下各项的内容：</span><span class="sxs-lookup"><span data-stu-id="44992-158">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="44992-159">特定类型敏感信息</span><span class="sxs-lookup"><span data-stu-id="44992-159">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="44992-160">指定与所创建的查询匹配的特定关键字或可搜索属性</span><span class="sxs-lookup"><span data-stu-id="44992-160">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="44992-161">可训练分类器的匹配项</span><span class="sxs-lookup"><span data-stu-id="44992-161">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="44992-162">将标签自动应用于包含特定类型敏感信息的内容</span><span class="sxs-lookup"><span data-stu-id="44992-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="44992-163">为敏感信息创建自动应用保留标签时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。</span><span class="sxs-lookup"><span data-stu-id="44992-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="44992-164">每个策略模板都是预配置的，用于查找特定类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="44992-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="44992-165">例如，此处显示的模板查找来自“**隐私**”类别的美国 ITIN、SSN 和护照号码，以及**美国个人身份信息（PII）数据模板**：</span><span class="sxs-lookup"><span data-stu-id="44992-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="44992-167">若要了解有关敏感信息类型的详细信息，请参阅“[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)”。</span><span class="sxs-lookup"><span data-stu-id="44992-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="44992-168">选择策略模板后，可添加或删除任意类型的敏感信息，且可更改实例计数和匹配准确度。</span><span class="sxs-lookup"><span data-stu-id="44992-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="44992-169">在下面的示例屏幕截图中，保留标签将只会在以下情况下自动应用：</span><span class="sxs-lookup"><span data-stu-id="44992-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="44992-170">检测到的敏感信息类型具有至少 75 的匹配准确度（或可信度）。</span><span class="sxs-lookup"><span data-stu-id="44992-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="44992-171">许多敏感信息类型都由多个模式定义，其中具有较高匹配准确度的模式需要发现较多证据（如关键字、日期或地址），而具有较低匹配准确度的模式需要较少的证据。</span><span class="sxs-lookup"><span data-stu-id="44992-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="44992-172">**最小**匹配准确度越低，内容越容易与条件匹配。</span><span class="sxs-lookup"><span data-stu-id="44992-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="44992-173">内容包含 1 到 9 个这三种敏感信息类型的实例。</span><span class="sxs-lookup"><span data-stu-id="44992-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="44992-174">可删除“**至**”值，将其更改为“**任何**”。</span><span class="sxs-lookup"><span data-stu-id="44992-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="44992-175">有关这些选项的详细信息，请参阅 DLP 文档中的以下指南“[调整规则，使它们更易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)”。</span><span class="sxs-lookup"><span data-stu-id="44992-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="44992-177">将标签自动应用于包含关键字或可搜索属性的内容</span><span class="sxs-lookup"><span data-stu-id="44992-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="44992-p113">可使用包含特定字词、短语或可搜索属性值的查询对内容自动应用标签。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。</span><span class="sxs-lookup"><span data-stu-id="44992-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![查询编辑器](../media/new-retention-query-editor.png)

<span data-ttu-id="44992-181">有关使用关键字查询语言 (KQL) 的详细信息，请参阅[关键字查询语言 (KQL) 语法参考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。</span><span class="sxs-lookup"><span data-stu-id="44992-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="44992-182">基于查询的标签使用搜索索引来标识内容。</span><span class="sxs-lookup"><span data-stu-id="44992-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="44992-183">有关可使用的可搜索属性的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="44992-183">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="44992-184">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="44992-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="44992-185">已爬网和托管属性在 SharePoint Server 中的概述</span><span class="sxs-lookup"><span data-stu-id="44992-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="44992-186">尽管 SharePoint 托管属性支持别名，但在配置保留标签时，请不要使用它们。</span><span class="sxs-lookup"><span data-stu-id="44992-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="44992-187">始终指定托管属性的实际名称，例如“RefinableString01”。</span><span class="sxs-lookup"><span data-stu-id="44992-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="44992-188">示例查询：</span><span class="sxs-lookup"><span data-stu-id="44992-188">Examples queries:</span></span>

| <span data-ttu-id="44992-189">工作负载</span><span class="sxs-lookup"><span data-stu-id="44992-189">Workload</span></span> | <span data-ttu-id="44992-190">示例</span><span class="sxs-lookup"><span data-stu-id="44992-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="44992-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="44992-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="44992-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="44992-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="44992-193">SharePoint</span><span class="sxs-lookup"><span data-stu-id="44992-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="44992-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="44992-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="44992-195">使用可训练分类器向内容自动应用标签</span><span class="sxs-lookup"><span data-stu-id="44992-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="44992-196">选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。</span><span class="sxs-lookup"><span data-stu-id="44992-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="44992-197">内置分类器包含**简历**、**源代码**、**有针对性的骚扰**、**侮辱**和**威胁**：</span><span class="sxs-lookup"><span data-stu-id="44992-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![选择可训练分类器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="44992-199">我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="44992-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="44992-200">请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。</span><span class="sxs-lookup"><span data-stu-id="44992-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="44992-201">我们建议改用**针对性的骚扰**、**侮辱**和**猥亵**内置分类器。</span><span class="sxs-lookup"><span data-stu-id="44992-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="44992-202">要通过此选项自动应用标签，SharePoint 网站和邮箱必须至少有 10 MB 的数据。</span><span class="sxs-lookup"><span data-stu-id="44992-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="44992-203">有关可训练分类器的详细信息，请参阅“[了解可训练分类器（预览版）](classifier-learn-about.md)”。</span><span class="sxs-lookup"><span data-stu-id="44992-203">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="44992-204">如果你将可训练的分类器用于 Exchange，请参阅最近发布的[如何重新培训内容资源管理器（预览版）](classifier-how-to-retrain-content-explorer.md)中的分类器。</span><span class="sxs-lookup"><span data-stu-id="44992-204">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="44992-205">保留标签需要多长时间才能生效</span><span class="sxs-lookup"><span data-stu-id="44992-205">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="44992-206">自动应用保留标签时，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。</span><span class="sxs-lookup"><span data-stu-id="44992-206">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="44992-208">更新保留标签及其策略</span><span class="sxs-lookup"><span data-stu-id="44992-208">Updating retention labels and their policies</span></span>

<span data-ttu-id="44992-209">在编辑保留标签或自动应用策略，并且该保留标签已应用到内容时，更新后的设置将自动应用于此内容以及新标识的内容。</span><span class="sxs-lookup"><span data-stu-id="44992-209">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="44992-210">某些设置无法在创建并保存标签或策略后更改，包括：</span><span class="sxs-lookup"><span data-stu-id="44992-210">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="44992-211">除保留期外的保留设置，除非已将标签配置为根据创建的时间保留或删除内容。</span><span class="sxs-lookup"><span data-stu-id="44992-211">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="44992-212">用于将项目标记为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="44992-212">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44992-213">后续步骤</span><span class="sxs-lookup"><span data-stu-id="44992-213">Next steps</span></span>

<span data-ttu-id="44992-214">有关使用事件驱动的保留和 SharePoint 中带有托管属性的自动应用策略来开启保留期的示例方案，请参阅[使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="44992-214">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
