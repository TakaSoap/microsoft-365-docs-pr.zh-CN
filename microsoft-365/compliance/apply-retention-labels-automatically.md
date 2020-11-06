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
ms.openlocfilehash: c1c18f5445b326ad7353d8c534940d3db69a3f24
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931976"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="e232c-103">自动应用保留标签来保留或删除内容</span><span class="sxs-lookup"><span data-stu-id="e232c-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="e232c-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e232c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="e232c-105">[规章记录](records-management.md#records)不支持这种情况。</span><span class="sxs-lookup"><span data-stu-id="e232c-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="e232c-106">[保留标签](retention.md)最强大的功能之一是能够将其自动应用于符合特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="e232c-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="e232c-107">此情况下，组织中的人员无需应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e232c-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="e232c-108">Microsoft 365 会代为操作。</span><span class="sxs-lookup"><span data-stu-id="e232c-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="e232c-109">自动应用保留标签的功能非常强大，这是因为：</span><span class="sxs-lookup"><span data-stu-id="e232c-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="e232c-110">无需为用户提供有关所有分类的培训。</span><span class="sxs-lookup"><span data-stu-id="e232c-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="e232c-111">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="e232c-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="e232c-112">用户不再需要了解数据管理策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="e232c-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="e232c-113">当内容包含敏感信息、关键字或可搜索属性，或者[可训练分类器](classifier-get-started-with.md)的匹配项时，可以自动将保留标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="e232c-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="e232c-114">现在在预览中，使用可搜索的属性标识 [Teams 会议记录](#microsoft-teams-meeting-recordings)。</span><span class="sxs-lookup"><span data-stu-id="e232c-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="e232c-115">将基于以下条件自动应用保留标签的流程：</span><span class="sxs-lookup"><span data-stu-id="e232c-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![自动应用标签的角色和任务关系图](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="e232c-117">按照以下说明进行两个管理步骤。</span><span class="sxs-lookup"><span data-stu-id="e232c-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="e232c-118">"自动策略" 使用服务侧标记（带条件）自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e232c-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="e232c-119">执行以下操作时，还可使用标签策略自动应用保留标签：</span><span class="sxs-lookup"><span data-stu-id="e232c-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="e232c-120">将默认保留标签应用于 SharePoint 库、文件夹或文档集，以便自动标记该容器中未标记的内容</span><span class="sxs-lookup"><span data-stu-id="e232c-120">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="e232c-121">使用规则将保留标签应用于电子邮件</span><span class="sxs-lookup"><span data-stu-id="e232c-121">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="e232c-122">有关这些情况，请参阅 [在应用中创建和应用保留标签](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="e232c-122">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e232c-123">准备工作</span><span class="sxs-lookup"><span data-stu-id="e232c-123">Before you begin</span></span>

<span data-ttu-id="e232c-124">组织的全局管理员拥有创建和编辑保留标签及其策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="e232c-124">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="e232c-125">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="e232c-125">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="e232c-126">如何自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="e232c-126">How to auto-apply a retention label</span></span>

<span data-ttu-id="e232c-127">首先，创建你的保留标签。</span><span class="sxs-lookup"><span data-stu-id="e232c-127">First, create your retention label.</span></span> <span data-ttu-id="e232c-128">然后创建 "自动策略" 以应用该标签。</span><span class="sxs-lookup"><span data-stu-id="e232c-128">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="e232c-129">如果已创建保留标签，请跳转到 [创建自动策略](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="e232c-129">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="e232c-130">导航说明取决于你是否正在使用[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="e232c-130">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="e232c-131">针对这两种情况提供了说明。</span><span class="sxs-lookup"><span data-stu-id="e232c-131">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="e232c-132">步骤 1：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="e232c-132">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="e232c-133">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="e232c-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="e232c-134">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="e232c-134">If you are using records management:</span></span>
        - <span data-ttu-id="e232c-135">“ **解决方案** ” > “ **记录管理** ” > “ **文件计划** ”选项卡 > + “ **创建标签** ” > “ **保留标签** ”</span><span class="sxs-lookup"><span data-stu-id="e232c-135">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="e232c-136">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="e232c-136">If you are not using records management:</span></span>
       - <span data-ttu-id="e232c-137">“ **解决方案** ” > “ **信息治理** ” > “ **标签** ”选项卡 > +“ **创建标签** ”</span><span class="sxs-lookup"><span data-stu-id="e232c-137">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="e232c-138">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="e232c-138">Don't immediately see your option?</span></span> <span data-ttu-id="e232c-139">首先选择“ **全部显示** ”。</span><span class="sxs-lookup"><span data-stu-id="e232c-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="e232c-140">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="e232c-140">Follow the prompts in the wizard.</span></span> <span data-ttu-id="e232c-141">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="e232c-141">If you are using records management:</span></span>
    
    - <span data-ttu-id="e232c-142">有关文件计划描述符的信息，请参阅[使用文件计划管理保留标签](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e232c-142">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="e232c-143">若要使用保留标签来声明记录，请选择 **“将项目标记为记录”** ，或者 **“将项目标记为合规性记录”** 。</span><span class="sxs-lookup"><span data-stu-id="e232c-143">To use the retention label to declare records, select **Mark items as records** , or **Mark items as regulatory records**.</span></span> <span data-ttu-id="e232c-144">有关详细信息，请参阅[配置保留标签以声明记录](declare-records.md#configuring-retention-labels-to-declare-records)。</span><span class="sxs-lookup"><span data-stu-id="e232c-144">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="e232c-145">创建标签后，你会看到用于发布标签、自动应用标签或 仅保存标签的选项：请选择“ **将此标签自动应用到特定的内容类型** ”，然后选择“ **完成** ”以启动“创建自动标记向导”，该向导将直接带你跳转到以下过程中的第 2 步。</span><span class="sxs-lookup"><span data-stu-id="e232c-145">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content** , and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="e232c-146">若要编辑现有标签，请将其选中，然后选择“ **编辑标签** ”来启动“编辑保留向导”，这个向导使你能够更改来自第 2 步的标签说明和任何 [符合条件的设置](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="e232c-146">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="e232c-147">步骤 2：创建自动应用策略</span><span class="sxs-lookup"><span data-stu-id="e232c-147">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="e232c-148">创建自动应用策略时，根据指定的条件，选择要自动应用到内容的保留标签。</span><span class="sxs-lookup"><span data-stu-id="e232c-148">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="e232c-149">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="e232c-149">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="e232c-150">如果你正在使用记录管理：“ **信息治理** ”：</span><span class="sxs-lookup"><span data-stu-id="e232c-150">If you are using records management: **Information governance** :</span></span>
        - <span data-ttu-id="e232c-151">**“解决方案”** > **“记录管理”** > **“标签策略”** 选项卡 > **“自动应用标签”**</span><span class="sxs-lookup"><span data-stu-id="e232c-151">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="e232c-152">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="e232c-152">If you are not using records management:</span></span>
        - <span data-ttu-id="e232c-153">**“解决方案”** > **“信息治理”** > **“标签策略”** 选项卡 > **“自动应用标签”**</span><span class="sxs-lookup"><span data-stu-id="e232c-153">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="e232c-154">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="e232c-154">Don't immediately see your option?</span></span> <span data-ttu-id="e232c-155">首先选择“ **全部显示** ”。</span><span class="sxs-lookup"><span data-stu-id="e232c-155">First select **Show all**.</span></span> 

2. <span data-ttu-id="e232c-156">按照“创建自动标记向导”中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="e232c-156">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="e232c-157">有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。</span><span class="sxs-lookup"><span data-stu-id="e232c-157">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="e232c-158">有关保留标签支持的位置的信息，请参阅[保留标签和位置](retention.md#retention-label-policies-and-locations)部分。</span><span class="sxs-lookup"><span data-stu-id="e232c-158">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="e232c-159">若要编辑现有的自动应用策略，请将其选中以启动“编辑保留策略向导”，该向导可用于更改从第 2 步中选定的保留标签和的任何[符合条件的设置](#updating-retention-labels-and-their-policies) 。</span><span class="sxs-lookup"><span data-stu-id="e232c-159">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="e232c-160">配置自动应用保留标签的条件</span><span class="sxs-lookup"><span data-stu-id="e232c-160">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="e232c-161">可将保留标签自动应用于包含以下各项的内容：</span><span class="sxs-lookup"><span data-stu-id="e232c-161">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="e232c-162">特定类型敏感信息</span><span class="sxs-lookup"><span data-stu-id="e232c-162">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="e232c-163">指定与所创建的查询匹配的特定关键字或可搜索属性</span><span class="sxs-lookup"><span data-stu-id="e232c-163">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="e232c-164">可训练分类器的匹配项</span><span class="sxs-lookup"><span data-stu-id="e232c-164">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="e232c-165">将标签自动应用于包含特定类型敏感信息的内容</span><span class="sxs-lookup"><span data-stu-id="e232c-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="e232c-166">为敏感信息创建自动应用保留标签策略时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。</span><span class="sxs-lookup"><span data-stu-id="e232c-166">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="e232c-167">每个策略模板都是预配置的，用于查找特定类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e232c-167">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="e232c-168">例如，此处显示的模板查找来自“ **隐私** ”类别的美国 ITIN、SSN 和护照号码，以及 **美国个人身份信息（PII）数据模板** ：</span><span class="sxs-lookup"><span data-stu-id="e232c-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template** :</span></span>

![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="e232c-170">若要了解有关敏感信息类型的详细信息，请参阅“[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)”。</span><span class="sxs-lookup"><span data-stu-id="e232c-170">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="e232c-171">选择策略模板后，可添加或删除任意类型的敏感信息，且可更改实例计数和匹配准确度。</span><span class="sxs-lookup"><span data-stu-id="e232c-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="e232c-172">在下面的示例屏幕截图中，保留标签将只会在以下情况下自动应用：</span><span class="sxs-lookup"><span data-stu-id="e232c-172">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="e232c-173">检测到的敏感信息类型具有至少 75 的匹配准确度（或可信度）。</span><span class="sxs-lookup"><span data-stu-id="e232c-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="e232c-174">许多敏感信息类型都由多个模式定义，其中具有较高匹配准确度的模式需要发现较多证据（如关键字、日期或地址），而具有较低匹配准确度的模式需要较少的证据。</span><span class="sxs-lookup"><span data-stu-id="e232c-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="e232c-175">**最小** 匹配准确度越低，内容越容易与条件匹配。</span><span class="sxs-lookup"><span data-stu-id="e232c-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="e232c-176">内容包含 1 到 9 个这三种敏感信息类型的实例。</span><span class="sxs-lookup"><span data-stu-id="e232c-176">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="e232c-177">可删除“ **至** ”值，将其更改为“ **任何** ”。</span><span class="sxs-lookup"><span data-stu-id="e232c-177">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="e232c-178">有关这些选项的详细信息，请参阅 DLP 文档中的以下指南“[调整规则，使它们更易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)”。</span><span class="sxs-lookup"><span data-stu-id="e232c-178">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="e232c-180">将标签自动应用于包含关键字或可搜索属性的内容</span><span class="sxs-lookup"><span data-stu-id="e232c-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="e232c-p114">可使用包含特定字词、短语或可搜索属性值的查询对内容自动应用标签。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。</span><span class="sxs-lookup"><span data-stu-id="e232c-p114">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![查询编辑器](../media/new-retention-query-editor.png)

<span data-ttu-id="e232c-184">有关使用关键字查询语言 (KQL) 的详细信息，请参阅[关键字查询语言 (KQL) 语法参考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。</span><span class="sxs-lookup"><span data-stu-id="e232c-184">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="e232c-185">基于查询的标签使用搜索索引来标识内容。</span><span class="sxs-lookup"><span data-stu-id="e232c-185">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="e232c-186">有关可使用的可搜索属性的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="e232c-186">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="e232c-187">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="e232c-187">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="e232c-188">已爬网和托管属性在 SharePoint Server 中的概述</span><span class="sxs-lookup"><span data-stu-id="e232c-188">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="e232c-189">尽管 SharePoint 托管属性支持别名，但在配置保留标签时，请不要使用它们。</span><span class="sxs-lookup"><span data-stu-id="e232c-189">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="e232c-190">始终指定托管属性的实际名称，例如“RefinableString01”。</span><span class="sxs-lookup"><span data-stu-id="e232c-190">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="e232c-191">示例查询：</span><span class="sxs-lookup"><span data-stu-id="e232c-191">Examples queries:</span></span>

| <span data-ttu-id="e232c-192">工作负载</span><span class="sxs-lookup"><span data-stu-id="e232c-192">Workload</span></span> | <span data-ttu-id="e232c-193">示例</span><span class="sxs-lookup"><span data-stu-id="e232c-193">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="e232c-194">Exchange</span><span class="sxs-lookup"><span data-stu-id="e232c-194">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="e232c-195">Exchange</span><span class="sxs-lookup"><span data-stu-id="e232c-195">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="e232c-196">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e232c-196">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="e232c-197">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e232c-197">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="e232c-198">Microsoft Teams 会议记录</span><span class="sxs-lookup"><span data-stu-id="e232c-198">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="e232c-199">保留和删除 Teams 会议记录将在预览中进行，记录保存到 OneDrive 或 SharePoint 前，将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="e232c-199">The ability to retain and delete Teams meeting recordings is rolling out in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="e232c-200">有关详细信息，请参阅[使用 OneDrive for Business 和 SharePoint 或 Stream 进行会议记录](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)。</span><span class="sxs-lookup"><span data-stu-id="e232c-200">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="e232c-201">若要确定存储在用户的 OneDrive 帐户或 SharePoint 中的 Microsoft Teams 会议记录，请为 **关键字查询编辑器** 指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e232c-201">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor** :</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="e232c-202">大多数情况下，会议记录将保存到 OneDrive 中。</span><span class="sxs-lookup"><span data-stu-id="e232c-202">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="e232c-203">但对于渠道会议，它们将保存在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="e232c-203">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="e232c-204">使用可训练分类器向内容自动应用标签</span><span class="sxs-lookup"><span data-stu-id="e232c-204">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="e232c-205">选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。</span><span class="sxs-lookup"><span data-stu-id="e232c-205">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="e232c-206">内置分类器包含 **简历** 、 **源代码** 、 **有针对性的骚扰** 、 **侮辱** 和 **威胁** ：</span><span class="sxs-lookup"><span data-stu-id="e232c-206">The built-in classifiers include **Resumes** , **SourceCode** , **Targeted Harassment** , **Profanity** , and **Threat** :</span></span>

![选择可训练分类器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="e232c-208">我们正在弃用 **冒犯性语言** 内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="e232c-208">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="e232c-209">请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。</span><span class="sxs-lookup"><span data-stu-id="e232c-209">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="e232c-210">我们建议改用 **针对性的骚扰** 、 **侮辱** 和 **猥亵** 内置分类器。</span><span class="sxs-lookup"><span data-stu-id="e232c-210">We recommend using the **Targeted Harassment** , **Profanity** , and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="e232c-211">要通过此选项自动应用标签，SharePoint 网站和邮箱必须至少有 10 MB 的数据。</span><span class="sxs-lookup"><span data-stu-id="e232c-211">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="e232c-212">有关可训练分类器的详细信息，请参阅“[了解可训练分类器（预览版）](classifier-learn-about.md)”。</span><span class="sxs-lookup"><span data-stu-id="e232c-212">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="e232c-213">如果你将可训练的分类器用于 Exchange，请参阅最近发布的[如何重新培训内容资源管理器（预览版）](classifier-how-to-retrain-content-explorer.md)中的分类器。</span><span class="sxs-lookup"><span data-stu-id="e232c-213">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="e232c-214">保留标签需要多长时间才能生效</span><span class="sxs-lookup"><span data-stu-id="e232c-214">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="e232c-215">自动应用保留标签时，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。</span><span class="sxs-lookup"><span data-stu-id="e232c-215">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="e232c-217">如果 7 天后未显示期望的标签，请从合规中心的 **标签策略** 页面中检查自动应用策略的 **状态** 。</span><span class="sxs-lookup"><span data-stu-id="e232c-217">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="e232c-218">如果看到“ **关闭(错误)** ”状态，并且在位置详细信息中看到一条消息显示部署策略（针对 SharePoint）或尝试重新部署策略（针对 OneDrive）所用的时间超过预期，请尝试运行 [RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell 命令，重新尝试策略分发：</span><span class="sxs-lookup"><span data-stu-id="e232c-218">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="e232c-219">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e232c-219">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e232c-220">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e232c-220">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="e232c-221">更新保留标签及其策略</span><span class="sxs-lookup"><span data-stu-id="e232c-221">Updating retention labels and their policies</span></span>

<span data-ttu-id="e232c-222">在编辑保留标签或自动应用策略，并且该保留标签已应用到内容时，更新后的设置将自动应用于此内容以及新标识的内容。</span><span class="sxs-lookup"><span data-stu-id="e232c-222">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="e232c-223">某些设置无法在创建并保存标签或策略后更改，包括：</span><span class="sxs-lookup"><span data-stu-id="e232c-223">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="e232c-224">除保留期外的保留设置，除非已将标签配置为根据创建的时间保留或删除内容。</span><span class="sxs-lookup"><span data-stu-id="e232c-224">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="e232c-225">用于将项目标记为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="e232c-225">The option to mark items as a record.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="e232c-226">锁定策略以防止更改</span><span class="sxs-lookup"><span data-stu-id="e232c-226">Locking the policy to prevent changes</span></span>

<span data-ttu-id="e232c-227">如果需要确保任何人都无法关闭策略、删除策略或降低其限制性，请参阅[使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="e232c-227">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e232c-228">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e232c-228">Next steps</span></span>

<span data-ttu-id="e232c-229">有关使用事件驱动的保留和 SharePoint 中带有托管属性的自动应用保留标签策略来开启保留期的示例方案，请参阅[使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="e232c-229">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
