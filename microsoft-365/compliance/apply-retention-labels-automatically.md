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
description: 创建保留标签和自动标记策略，以便你可以自动应用标签以保留需要的内容并删除不需要的内容
ms.openlocfilehash: 12e909964422d0c15312c1794ce3d9aacc2a1da8
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107634"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="aeae9-103">自动应用保留标签来保留或删除内容</span><span class="sxs-lookup"><span data-stu-id="aeae9-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="aeae9-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="aeae9-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="aeae9-105">[规章记录](records-management.md#records)不支持这种情况。</span><span class="sxs-lookup"><span data-stu-id="aeae9-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="aeae9-106">[保留标签](retention.md)最强大的功能之一是能够将其自动应用于符合特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="aeae9-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="aeae9-107">此情况下，组织中的人员无需应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="aeae9-108">Microsoft 365 会代为操作。</span><span class="sxs-lookup"><span data-stu-id="aeae9-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="aeae9-109">自动应用保留标签的功能非常强大，这是因为：</span><span class="sxs-lookup"><span data-stu-id="aeae9-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="aeae9-110">无需为用户提供有关所有分类的培训。</span><span class="sxs-lookup"><span data-stu-id="aeae9-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="aeae9-111">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="aeae9-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="aeae9-112">用户不再需要了解数据管理策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="aeae9-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="aeae9-113">当内容包含敏感信息、关键字或可搜索属性，或者[可训练分类器](classifier-get-started-with.md)的匹配项时，可以自动将保留标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="aeae9-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="aeae9-114">最近发布时，可使用可搜索属性标识 [团队会议](#microsoft-teams-meeting-recordings)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-114">Recently released, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="aeae9-115">将基于以下条件自动应用保留标签的流程：</span><span class="sxs-lookup"><span data-stu-id="aeae9-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![自动应用标签的角色和任务关系图](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="aeae9-117">按照以下说明进行两个管理步骤。</span><span class="sxs-lookup"><span data-stu-id="aeae9-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="aeae9-118">"自动策略" 使用服务侧标记（带条件）自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="aeae9-119">执行以下操作时，还可使用标签策略自动应用保留标签：</span><span class="sxs-lookup"><span data-stu-id="aeae9-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="aeae9-120">将保留标签应用于文档理解 SharePoint Syntex 中的模型</span><span class="sxs-lookup"><span data-stu-id="aeae9-120">Apply a retention label to a document understanding model in SharePoint Syntex</span></span>
> - <span data-ttu-id="aeae9-121">将默认保留标签应用于 SharePoint 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="aeae9-121">Apply a default retention label for SharePoint and Outlook</span></span>
>- <span data-ttu-id="aeae9-122">使用 Outlook 规则将保留标签应用于电子邮件</span><span class="sxs-lookup"><span data-stu-id="aeae9-122">Apply a retention label to email by using Outlook rules</span></span>
>
> <span data-ttu-id="aeae9-123">有关这些情况，请参阅 [在应用中创建和应用保留标签](create-apply-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-123">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="aeae9-124">准备工作</span><span class="sxs-lookup"><span data-stu-id="aeae9-124">Before you begin</span></span>

<span data-ttu-id="aeae9-125">组织的全局管理员拥有创建和编辑保留标签及其策略的完全权限。</span><span class="sxs-lookup"><span data-stu-id="aeae9-125">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="aeae9-126">如果你未以全局管理员的身份登录，请参阅[创建和管理保留策略和保留标签所需的权限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-126">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="aeae9-127">如何自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="aeae9-127">How to auto-apply a retention label</span></span>

<span data-ttu-id="aeae9-128">首先，创建你的保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-128">First, create your retention label.</span></span> <span data-ttu-id="aeae9-129">然后创建 "自动策略" 以应用该标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-129">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="aeae9-130">如果已创建保留标签，请跳转到 [创建自动策略](#step-2-create-an-auto-apply-policy)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-130">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="aeae9-131">导航说明取决于你是否正在使用[记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-131">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="aeae9-132">针对这两种情况提供了说明。</span><span class="sxs-lookup"><span data-stu-id="aeae9-132">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="aeae9-133">步骤 1：创建保留标签</span><span class="sxs-lookup"><span data-stu-id="aeae9-133">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="aeae9-134">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="aeae9-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="aeae9-135">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="aeae9-135">If you are using records management:</span></span>
        - <span data-ttu-id="aeae9-136">“**解决方案**” > “**记录管理**” > “**文件计划**”选项卡 > + “**创建标签**” > “**保留标签**”</span><span class="sxs-lookup"><span data-stu-id="aeae9-136">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="aeae9-137">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="aeae9-137">If you are not using records management:</span></span>
       - <span data-ttu-id="aeae9-138">“**解决方案**” > “**信息治理**” > “**标签**”选项卡 > +“**创建标签**”</span><span class="sxs-lookup"><span data-stu-id="aeae9-138">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="aeae9-139">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="aeae9-139">Don't immediately see your option?</span></span> <span data-ttu-id="aeae9-140">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="aeae9-140">First select **Show all**.</span></span> 

2. <span data-ttu-id="aeae9-141">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="aeae9-141">Follow the prompts in the wizard.</span></span> <span data-ttu-id="aeae9-142">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="aeae9-142">If you are using records management:</span></span>
    
    - <span data-ttu-id="aeae9-143">有关文件计划描述符的信息，请参阅[使用文件计划管理保留标签](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="aeae9-143">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="aeae9-144">若要使用保留标签来声明记录，请选择 **“将项目标记为记录”**，或者 **“将项目标记为合规性记录”**。</span><span class="sxs-lookup"><span data-stu-id="aeae9-144">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="aeae9-145">有关详细信息，请参阅[配置保留标签以声明记录](declare-records.md#configuring-retention-labels-to-declare-records)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-145">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="aeae9-146">创建标签后，你会看到用于发布标签、自动应用标签或 仅保存标签的选项：请选择“**将此标签自动应用到特定的内容类型**”，然后选择“**完成**”以启动“创建自动标记向导”，该向导将直接带你跳转到以下过程中的第 2 步。</span><span class="sxs-lookup"><span data-stu-id="aeae9-146">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="aeae9-147">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”来启动“编辑保留向导”，这个向导使你能够更改来自第 2 步的标签说明和任何 [符合条件的设置](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-147">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="aeae9-148">步骤 2：创建自动应用策略</span><span class="sxs-lookup"><span data-stu-id="aeae9-148">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="aeae9-149">创建自动应用策略时，根据指定的条件，选择要自动应用到内容的保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-149">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="aeae9-150">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="aeae9-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="aeae9-151">如果你正在使用记录管理：“**信息治理**”：</span><span class="sxs-lookup"><span data-stu-id="aeae9-151">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="aeae9-152">**“解决方案”** > **“记录管理”** > **“标签策略”** 选项卡 > **“自动应用标签”**</span><span class="sxs-lookup"><span data-stu-id="aeae9-152">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="aeae9-153">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="aeae9-153">If you are not using records management:</span></span>
        - <span data-ttu-id="aeae9-154">**“解决方案”** > **“信息治理”** > **“标签策略”** 选项卡 > **“自动应用标签”**</span><span class="sxs-lookup"><span data-stu-id="aeae9-154">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="aeae9-155">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="aeae9-155">Don't immediately see your option?</span></span> <span data-ttu-id="aeae9-156">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="aeae9-156">First select **Show all**.</span></span> 

2. <span data-ttu-id="aeae9-157">按照“创建自动标记向导”中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="aeae9-157">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="aeae9-158">有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。</span><span class="sxs-lookup"><span data-stu-id="aeae9-158">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="aeae9-159">有关保留标签支持的位置的信息，请参阅[保留标签和位置](retention.md#retention-label-policies-and-locations)部分。</span><span class="sxs-lookup"><span data-stu-id="aeae9-159">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="aeae9-160">若要编辑现有的自动应用策略，请将其选中以启动“编辑保留策略向导”，该向导可用于更改从第 2 步中选定的保留标签和的任何[符合条件的设置](#updating-retention-labels-and-their-policies)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-160">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

<span data-ttu-id="aeae9-161">使用自动应用标签策略标记内容后，无法通过更改内容或策略或新的自动应用标签策略自动删除或更改应用的标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-161">After content is labeled by using an auto-apply label policy, the applied label can't be automatically removed or changed by changing the content or the policy, or by a new auto-apply label policy.</span></span> <span data-ttu-id="aeae9-162">有关详细信息，请参阅 [一次只能有一个保留标签](retention.md#only-one-retention-label-at-a-time)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-162">For more information, see [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="aeae9-163">配置自动应用保留标签的条件</span><span class="sxs-lookup"><span data-stu-id="aeae9-163">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="aeae9-164">可将保留标签自动应用于包含以下各项的内容：</span><span class="sxs-lookup"><span data-stu-id="aeae9-164">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="aeae9-165">特定类型敏感信息</span><span class="sxs-lookup"><span data-stu-id="aeae9-165">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="aeae9-166">指定与所创建的查询匹配的特定关键字或可搜索属性</span><span class="sxs-lookup"><span data-stu-id="aeae9-166">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="aeae9-167">可训练分类器的匹配项</span><span class="sxs-lookup"><span data-stu-id="aeae9-167">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="aeae9-168">将标签自动应用于包含特定类型敏感信息的内容</span><span class="sxs-lookup"><span data-stu-id="aeae9-168">Auto-apply labels to content with specific types of sensitive information</span></span>

> [!WARNING]
> <span data-ttu-id="aeae9-169">该配置当前存在一个已知限制，即选定的敏感信息类型有匹配时，所有未标记的电子邮件始终应用所选的保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-169">This configuration currently has a known limitation where all unlabeled emails always have the selected retention label applied when there is a match for your chosen sensitive information types.</span></span> <span data-ttu-id="aeae9-170">例如，即使将自动应用策略的范围限定于特定用户，或者为该策略选择了 Exchange 以外的位置，如果匹配，标签始终会应用于未标记的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aeae9-170">For example, even if you scope your auto-apply policy to specific users, or select locations other than Exchange for the policy, the label is always applied to unlabeled emails when there is a match.</span></span>

<span data-ttu-id="aeae9-171">为敏感信息创建自动应用保留标签策略时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。</span><span class="sxs-lookup"><span data-stu-id="aeae9-171">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="aeae9-172">每个策略模板都是预配置的，用于查找特定类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="aeae9-172">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="aeae9-173">例如，此处显示的模板查找来自 **隐私** 类别的美国 ITIN、SSN 和护照号码，以及 **美国个人身份信息 (PII) 数据** 模板：</span><span class="sxs-lookup"><span data-stu-id="aeae9-173">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data** template:</span></span>

![包含敏感信息类型的策略模板](../media/sensitive-info-configuration.png)

<span data-ttu-id="aeae9-175">若要了解有关敏感信息类型的详细信息，请参阅“[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)”。</span><span class="sxs-lookup"><span data-stu-id="aeae9-175">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span> <span data-ttu-id="aeae9-176">目前[此方案](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)[完全匹配](document-fingerprinting.md)和文档指纹信息。</span><span class="sxs-lookup"><span data-stu-id="aeae9-176">Currently, [exact data matches](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) and [document fingerprinting](document-fingerprinting.md) are not supported for this scenario.</span></span>

<span data-ttu-id="aeae9-p114">选择策略模板后，既可以添加或删除任意类型敏感信息，也可以更改实例计数和匹配准确度。在下面的示例屏幕截图中，保留标签将只会在以下情况下自动应用：</span><span class="sxs-lookup"><span data-stu-id="aeae9-p114">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="aeae9-179">检测到的敏感信息类型具有至少 75 的匹配准确度（或可信度）。</span><span class="sxs-lookup"><span data-stu-id="aeae9-179">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="aeae9-180">许多敏感信息类型都由多个模式定义，其中具有较高匹配准确度的模式需要发现较多证据（如关键字、日期或地址），而具有较低匹配准确度的模式需要较少的证据。</span><span class="sxs-lookup"><span data-stu-id="aeae9-180">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="aeae9-181">**最小** 匹配准确度越低，内容越容易与条件匹配。</span><span class="sxs-lookup"><span data-stu-id="aeae9-181">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="aeae9-182">内容包含 1 到 9 个这三种敏感信息类型的实例。</span><span class="sxs-lookup"><span data-stu-id="aeae9-182">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="aeae9-183">可删除“**至**”值，将其更改为“**任何**”。</span><span class="sxs-lookup"><span data-stu-id="aeae9-183">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="aeae9-184">有关这些选项的详细信息，请参阅 DLP 文档中的以下指南“[调整规则，使它们更易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)”。</span><span class="sxs-lookup"><span data-stu-id="aeae9-184">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

<span data-ttu-id="aeae9-186">使用敏感信息类型自动应用保留标签时要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="aeae9-186">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="aeae9-187">新增项目和已修改项目可自动添加标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-187">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="aeae9-188">将标签自动应用于包含关键字或可搜索属性的内容</span><span class="sxs-lookup"><span data-stu-id="aeae9-188">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="aeae9-p117">可使用包含特定字词、短语或可搜索属性值的查询对内容自动应用标签。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。</span><span class="sxs-lookup"><span data-stu-id="aeae9-p117">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![查询编辑器](../media/new-retention-query-editor.png)

<span data-ttu-id="aeae9-192">有关使用关键字查询语言 (KQL) 的详细信息，请参阅[关键字查询语言 (KQL) 语法参考](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-192">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="aeae9-193">基于查询的自动应用策略使用与电子数据展示内容搜索相同的搜索索引来识别内容。</span><span class="sxs-lookup"><span data-stu-id="aeae9-193">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="aeae9-194">有关可使用的可搜索属性的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-194">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="aeae9-195">使用关键字或可搜索属性自动应用保留标签时需要考虑的一些事项：</span><span class="sxs-lookup"><span data-stu-id="aeae9-195">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="aeae9-196">对于 SharePoint、OneDrive 和 Exchange，新增项目、已修改项目和现有项目将自动添加标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-196">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="aeae9-197">对于 SharePoint，这些 KQL 查询不支持爬网属性和自定义属性，你必须仅使用预定义的托管属性。</span><span class="sxs-lookup"><span data-stu-id="aeae9-197">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="aeae9-198">但是，你可以在租户级别使用与默认情况下启用为精简条件的预定义托管属性（RefinableDate00-19、RefinableString00-99、RefinableInt00-49、RefinableDecimals00-09 和 RefinableDouble00-09）的映射。</span><span class="sxs-lookup"><span data-stu-id="aeae9-198">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="aeae9-199">有关详细信息，请参阅 [SharePoint Server 中的已爬网和托管属性概述](/SharePoint/technical-reference/crawled-and-managed-properties-overview)，有关说明，请参阅[创建新的托管属性](/sharepoint/manage-search-schema#create-a-new-managed-property)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-199">For more information, see [Overview of crawled and managed properties in SharePoint Server](/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="aeae9-200">如果将自定义属性映射到其中一个精简条件属性，请等待 24 小时，然后再在 KQL 查询中将其用于保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-200">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="aeae9-201">虽然 SharePoint 托管属性可以使用别名重命名，但请勿将它们用于标签中的 KQL 查询。</span><span class="sxs-lookup"><span data-stu-id="aeae9-201">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="aeae9-202">始终指定托管属性的实际名称，例如“RefinableString01”。</span><span class="sxs-lookup"><span data-stu-id="aeae9-202">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="aeae9-203">若要搜索包含空格或特殊字符的值，请使用双引号 (`" "`) 来包含短语；例如，`subject:"Financial Statements"`。</span><span class="sxs-lookup"><span data-stu-id="aeae9-203">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="aeae9-204">使用 *DocumentLink* 属性而不是 *Path* 来基于其 URL 匹配项目。</span><span class="sxs-lookup"><span data-stu-id="aeae9-204">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="aeae9-205">不支持后缀通配符搜索（如 `*cat` ）或子字符串通配符搜索（如 `*cat*`）。</span><span class="sxs-lookup"><span data-stu-id="aeae9-205">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="aeae9-206">但是，支持前缀通配符搜索（如 `cat*`）。</span><span class="sxs-lookup"><span data-stu-id="aeae9-206">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="aeae9-207">请注意，部分索引项可能会导致未对预期项目进行标记，或者在你使用 Not 运算符时不对你希望从标签中排除的项目进行标记。</span><span class="sxs-lookup"><span data-stu-id="aeae9-207">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="aeae9-208">有关详细信息，请参阅[内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-208">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="aeae9-209">示例查询：</span><span class="sxs-lookup"><span data-stu-id="aeae9-209">Examples queries:</span></span>

| <span data-ttu-id="aeae9-210">工作负载</span><span class="sxs-lookup"><span data-stu-id="aeae9-210">Workload</span></span> | <span data-ttu-id="aeae9-211">示例</span><span class="sxs-lookup"><span data-stu-id="aeae9-211">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="aeae9-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="aeae9-212">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="aeae9-213">Exchange</span><span class="sxs-lookup"><span data-stu-id="aeae9-213">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="aeae9-214">SharePoint</span><span class="sxs-lookup"><span data-stu-id="aeae9-214">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="aeae9-215">SharePoint</span><span class="sxs-lookup"><span data-stu-id="aeae9-215">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="aeae9-216">Exchange 或 SharePoint</span><span class="sxs-lookup"><span data-stu-id="aeae9-216">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="aeae9-217">更复杂的示例：</span><span class="sxs-lookup"><span data-stu-id="aeae9-217">More complex examples:</span></span>

<span data-ttu-id="aeae9-218">当 Word 文档或 Excel 电子表格包含关键字 **password**、**passwords** 或 **pw** 时，以下 SharePoint 查询将识别这些文件：</span><span class="sxs-lookup"><span data-stu-id="aeae9-218">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="aeae9-219">以下 Exchange 查询可识别电子邮件中包含单词 **nda** 或短语 **保密协议** 的任何 Word 文档或 PDF：</span><span class="sxs-lookup"><span data-stu-id="aeae9-219">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="aeae9-220">以下 SharePoint 查询可识别包含信用卡号的文档：</span><span class="sxs-lookup"><span data-stu-id="aeae9-220">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="aeae9-221">以下查询包含一些典型关键字，可帮助识别包含法律内容的文档或电子邮件：</span><span class="sxs-lookup"><span data-stu-id="aeae9-221">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="aeae9-222">以下查询包含一些典型关键字，可帮助识别人力资源相关的文档或电子邮件：</span><span class="sxs-lookup"><span data-stu-id="aeae9-222">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="aeae9-223">请注意，最后一个示例使用的最佳做法是始终在关键字之间包含运算符。</span><span class="sxs-lookup"><span data-stu-id="aeae9-223">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="aeae9-224">两个关键字（或两个 property:value 表达式）之间的空格与使用 AND 相同。</span><span class="sxs-lookup"><span data-stu-id="aeae9-224">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="aeae9-225">通过始终添加运算符，可更轻松地看出此示例查询将仅识别包含所有这些关键字的内容，而不是包含任何关键字的内容。</span><span class="sxs-lookup"><span data-stu-id="aeae9-225">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="aeae9-226">如果打算识别包含任何关键字的内容，请指定 OR，而不是 AND。</span><span class="sxs-lookup"><span data-stu-id="aeae9-226">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="aeae9-227">如本示例所示，当你始终指定运算符时，正确解读查询更为简单。</span><span class="sxs-lookup"><span data-stu-id="aeae9-227">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="aeae9-228">Microsoft Teams 会议记录</span><span class="sxs-lookup"><span data-stu-id="aeae9-228">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="aeae9-229">保留和删除 Teams 会议记录文件的功能目前处于预览阶段，在将记录保存到 OneDrive 或SharePoint 前，该功能将无法工作。</span><span class="sxs-lookup"><span data-stu-id="aeae9-229">The ability to retain and delete Teams meeting recordings won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="aeae9-230">有关详细信息，请参阅[使用 OneDrive for Business 和 SharePoint 或 Stream 进行会议记录](/MicrosoftTeams/tmr-meeting-recording-change)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-230">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="aeae9-231">若要确定存储在用户的 OneDrive 帐户或 SharePoint 中的 Microsoft Teams 会议记录，请为 **关键字查询编辑器** 指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="aeae9-231">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="aeae9-p125">大多数情况下，会议记录将保存到 OneDrive。但对于频道会议，它们将保存在SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="aeae9-p125">Most of the time, meeting recordings are saved to OneDrive. But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="aeae9-234">使用可训练分类器向内容自动应用标签</span><span class="sxs-lookup"><span data-stu-id="aeae9-234">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="aeae9-235">选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。</span><span class="sxs-lookup"><span data-stu-id="aeae9-235">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="aeae9-236">内置分类器包含 **简历**、**源代码**、**有针对性的骚扰**、**侮辱** 和 **威胁**：</span><span class="sxs-lookup"><span data-stu-id="aeae9-236">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![选择可训练分类器](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="aeae9-238">我们正在弃用 **冒犯性语言** 内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="aeae9-238">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="aeae9-239">请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。</span><span class="sxs-lookup"><span data-stu-id="aeae9-239">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="aeae9-240">我们建议改用 **针对性的骚扰**、**侮辱** 和 **猥亵** 内置分类器。</span><span class="sxs-lookup"><span data-stu-id="aeae9-240">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="aeae9-241">要通过此选项自动应用标签，SharePoint 网站和邮箱必须至少有 10 MB 的数据。</span><span class="sxs-lookup"><span data-stu-id="aeae9-241">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="aeae9-242">有关可训练分类器的详细信息，请参阅 [了解可训练分类器（预览版）](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-242">For more information about trainable classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="aeae9-243">如果你将可训练分类器用于 Exchange，请参阅 [如何重新培训内容资源管理器中的分类器](classifier-how-to-retrain-content-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-243">If you use trainable classifiers for Exchange, see [How to retrain a classifier in content explorer](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="aeae9-244">使用可训练的分类器自动应用保留标签时要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="aeae9-244">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="aeae9-245">新增项目和已修改项目可以自动添加标签，以及过去六个月的现有项目。</span><span class="sxs-lookup"><span data-stu-id="aeae9-245">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="aeae9-246">保留标签需要多长时间才能生效</span><span class="sxs-lookup"><span data-stu-id="aeae9-246">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="aeae9-247">自动应用保留标签时，可能需要等待长达 7 天，才能将保留标签应用于与条件匹配的所有现有内容。</span><span class="sxs-lookup"><span data-stu-id="aeae9-247">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="aeae9-249">如果 7 天后未显示期望的标签，请从合规中心的 **标签策略** 页面中检查自动应用策略的 **状态**。</span><span class="sxs-lookup"><span data-stu-id="aeae9-249">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="aeae9-250">如果看到“**关闭(错误)**”状态，并且在位置详细信息中看到一条消息显示部署策略（针对 SharePoint）或尝试重新部署策略（针对 OneDrive）所用的时间超过预期，请尝试运行 [RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell 命令，重新尝试策略分发：</span><span class="sxs-lookup"><span data-stu-id="aeae9-250">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="aeae9-251">[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-251">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="aeae9-252">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aeae9-252">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="aeae9-253">更新保留标签及其策略</span><span class="sxs-lookup"><span data-stu-id="aeae9-253">Updating retention labels and their policies</span></span>

<span data-ttu-id="aeae9-254">在编辑保留标签或自动应用策略，并且该保留标签已应用到内容时，更新后的设置将自动应用于此内容以及新标识的内容。</span><span class="sxs-lookup"><span data-stu-id="aeae9-254">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="aeae9-255">某些设置无法在创建并保存标签或策略后更改，包括：</span><span class="sxs-lookup"><span data-stu-id="aeae9-255">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="aeae9-256">保留标签和策略名称以及保留期以外的其他保留设置。</span><span class="sxs-lookup"><span data-stu-id="aeae9-256">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="aeae9-257">但是，如果保留期基于项目的标记时间，则不能更改保留期。</span><span class="sxs-lookup"><span data-stu-id="aeae9-257">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="aeae9-258">用于将项目标记为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="aeae9-258">The option to mark items as a record.</span></span>

### <a name="deleting-retention-labels"></a><span data-ttu-id="aeae9-259">创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-259">Deleting retention labels</span></span>

<span data-ttu-id="aeae9-260">可以删除当前未包含在任何保留标签策略中的保留标签、不针对基于事件保留而配置的保留标签，或将项目标记为法规记录的保留标签。</span><span class="sxs-lookup"><span data-stu-id="aeae9-260">You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records.</span></span>

<span data-ttu-id="aeae9-261">对于可以删除的保留标签，如果已应用到项目，则删除操作将失败，并且你将看到指向内容资源管理器的链接，以标识已标记的项目。</span><span class="sxs-lookup"><span data-stu-id="aeae9-261">For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.</span></span>

<span data-ttu-id="aeae9-262">但是，内容资源管理器可能需要多达两天时间才能显示标记的项目。</span><span class="sxs-lookup"><span data-stu-id="aeae9-262">However, it can take up to two days for content explorer to show the items that are labeled.</span></span> <span data-ttu-id="aeae9-263">在这种情况下，可能会删除保留标签，而不显示指向内容资源管理器的链接。</span><span class="sxs-lookup"><span data-stu-id="aeae9-263">In this scenario, the retention label might be deleted without showing you the link to content explorer.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="aeae9-264">锁定策略以防止更改</span><span class="sxs-lookup"><span data-stu-id="aeae9-264">Locking the policy to prevent changes</span></span>

<span data-ttu-id="aeae9-265">如果需要确保任何人都无法关闭策略、删除策略或降低其限制性，请参阅[使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-265">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="aeae9-266">后续步骤</span><span class="sxs-lookup"><span data-stu-id="aeae9-266">Next steps</span></span>

<span data-ttu-id="aeae9-267">有关使用事件驱动的保留和 SharePoint 中带有托管属性的自动应用保留标签策略来开启保留期的示例方案，请参阅[使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae9-267">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>