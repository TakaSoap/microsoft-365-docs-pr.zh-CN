---
title: 创建、发布和自动应用保留标签
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
description: 有关创建、发布和自动应用保留标签以保留所需内容、删除不需要的内容，并在 Office 365 环境中将项目声明为记录的说明。
ms.openlocfilehash: 1b34833c8320e5d27029474a4da9f0534a63dc51
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262383"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="daef2-103">创建、发布和自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="daef2-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="daef2-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="daef2-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="daef2-105">使用以下信息可帮助你创建[保留标签](labels.md)，然后将其自动应用到文档和电子邮件，或发布它们以便用户可以手动应用。</span><span class="sxs-lookup"><span data-stu-id="daef2-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="daef2-106">保留标签可帮助你保留所需内容并删除不需要的内容。</span><span class="sxs-lookup"><span data-stu-id="daef2-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="daef2-107">它们还用于将项目声明为记录，作为 Microsoft 365 数据的[记录管理](records-management.md)解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="daef2-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="daef2-108">创建和配置保留标签的位置取决于你是否使用记录管理。</span><span class="sxs-lookup"><span data-stu-id="daef2-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="daef2-109">针对这两种情况提供了说明。</span><span class="sxs-lookup"><span data-stu-id="daef2-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="daef2-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="daef2-110">Before you begin</span></span>

<span data-ttu-id="daef2-111">负责创建保留标签的合规性团队成员必须有权访问安全&amp;合规中心。</span><span class="sxs-lookup"><span data-stu-id="daef2-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="daef2-112">默认情况下，租户管理员有权访问此位置，并可向合规部主管及其他人员授予对安全&amp;合规中心的访问权限，而不授予租户管理员的所有权限。为此，建议转到安全&amp;合规中心内的“**权限**”页，编辑“**合规性管理员**”角色组，再向此角色组添加成员。</span><span class="sxs-lookup"><span data-stu-id="daef2-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="daef2-113">有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="daef2-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="daef2-p104">只有在创建和应用保留标签和标签策略时，才必须拥有这些权限。强制执行策略并不需要访问内容。</span><span class="sxs-lookup"><span data-stu-id="daef2-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="daef2-116">创建和配置保留标签</span><span class="sxs-lookup"><span data-stu-id="daef2-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="daef2-117">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="daef2-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="daef2-118">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="daef2-118">If you are using records management:</span></span>
        - <span data-ttu-id="daef2-119">“**解决方案**” > “**记录管理**” > “**文件计划**”选项卡 > + “**创建标签**” > “**保留标签**”</span><span class="sxs-lookup"><span data-stu-id="daef2-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="daef2-120">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="daef2-120">If you are not using records management:</span></span>
       - <span data-ttu-id="daef2-121">“**解决方案**” > “**信息治理**” > “**标签**”选项卡 > +“**创建标签**”</span><span class="sxs-lookup"><span data-stu-id="daef2-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="daef2-122">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="daef2-122">Don't immediately see your option?</span></span> <span data-ttu-id="daef2-123">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="daef2-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="daef2-124">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="daef2-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="daef2-125">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="daef2-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="daef2-126">有关文件计划描述符的信息，请参阅[文件计划管理器概述](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="daef2-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="daef2-127">要使用保留标签将内容声明为记录，请启用“**使用标签将内容分类为“记录”**”复选框。</span><span class="sxs-lookup"><span data-stu-id="daef2-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="daef2-128">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="daef2-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="daef2-129">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="daef2-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="daef2-130">这将启动同一向导，可用于更改步骤 2 中的标签说明和设置。</span><span class="sxs-lookup"><span data-stu-id="daef2-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="daef2-131">通过创建保留标签策略发布保留标签</span><span class="sxs-lookup"><span data-stu-id="daef2-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="daef2-132">发布保留标签，以便用户可以可以手动应用它们。</span><span class="sxs-lookup"><span data-stu-id="daef2-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="daef2-133">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="daef2-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="daef2-134">如果你正在使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="daef2-134">If you are using records management:</span></span>
        - <span data-ttu-id="daef2-135">“**解决方案**” > “**记录管理**”> >“**标签策略**”选项卡 >“**发布标签**”</span><span class="sxs-lookup"><span data-stu-id="daef2-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="daef2-136">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="daef2-136">If you are not using records management:</span></span>
        - <span data-ttu-id="daef2-137">“**解决方案**” > “**信息治理**” > “**标签策略**”选项卡 >“**发布标签**”</span><span class="sxs-lookup"><span data-stu-id="daef2-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="daef2-138">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="daef2-138">Don't immediately see your option?</span></span> <span data-ttu-id="daef2-139">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="daef2-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="daef2-140">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="daef2-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="daef2-141">有关配置位置的信息，请参阅此页面上的[保留标签和位置](#retention-labels-and-locations)部分。</span><span class="sxs-lookup"><span data-stu-id="daef2-141">For information about configuring the locations, see the [Retention labels and locations](#retention-labels-and-locations) section on this page.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="daef2-142">自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="daef2-142">Auto-apply a retention label</span></span>

<span data-ttu-id="daef2-143">根据指定的条件自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="daef2-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="daef2-144">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="daef2-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="daef2-145">如果你正在使用记录管理：“**信息治理**”：</span><span class="sxs-lookup"><span data-stu-id="daef2-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="daef2-146">“**解决方案**” > “**记录管理**” > “**标签策略**”选项卡 >“**自动应用标签**”</span><span class="sxs-lookup"><span data-stu-id="daef2-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="daef2-147">如果你没有使用记录管理：</span><span class="sxs-lookup"><span data-stu-id="daef2-147">If you are not using records management:</span></span>
        - <span data-ttu-id="daef2-148">“**解决方案**” > “**信息治理**” > “**标签策略**”选项卡 >“**自动应用标签**”</span><span class="sxs-lookup"><span data-stu-id="daef2-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="daef2-149">没有立即看到你的选项？</span><span class="sxs-lookup"><span data-stu-id="daef2-149">Don't immediately see your option?</span></span> <span data-ttu-id="daef2-150">首先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="daef2-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="daef2-151">按照向导中的提示进行操作。</span><span class="sxs-lookup"><span data-stu-id="daef2-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="daef2-152">有关配置自动应用保留标签的条件的信息，请参阅此页面上的[配置自动应用保留标签的条件](#configuring-conditions-for-auto-apply-retention-labels)部分。</span><span class="sxs-lookup"><span data-stu-id="daef2-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="daef2-153">有关配置位置的信息，请参阅此页面上的下一部分[保留标签和位置](#retention-labels-and-locations)。</span><span class="sxs-lookup"><span data-stu-id="daef2-153">For information about configuring the locations, see the next section on this page, [Retention labels and locations](#retention-labels-and-locations).</span></span>

## <a name="retention-labels-and-locations"></a><span data-ttu-id="daef2-154">保留标签和位置</span><span class="sxs-lookup"><span data-stu-id="daef2-154">Retention labels and locations</span></span>

<span data-ttu-id="daef2-155">不同类型的保留标签可发布到不同位置，具体视保留标签用途而定。</span><span class="sxs-lookup"><span data-stu-id="daef2-155">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
|<span data-ttu-id="daef2-156">**如果保留标签…**</span><span class="sxs-lookup"><span data-stu-id="daef2-156">**If the retention label is…**</span></span>|<span data-ttu-id="daef2-157">**可将标签策略应用于…**</span><span class="sxs-lookup"><span data-stu-id="daef2-157">**Then the label policy can be applied to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="daef2-158">发布给最终用户</span><span class="sxs-lookup"><span data-stu-id="daef2-158">Published to end users</span></span>  <br/> |<span data-ttu-id="daef2-159">Exchange、SharePoint、OneDrive 和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="daef2-159">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
|<span data-ttu-id="daef2-160">根据敏感信息类型自动应用</span><span class="sxs-lookup"><span data-stu-id="daef2-160">Auto-applied based on sensitive information types</span></span>  <br/> |<span data-ttu-id="daef2-161">Exchange（仅全部邮箱）、SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="daef2-161">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="daef2-162">根据查询自动应用</span><span class="sxs-lookup"><span data-stu-id="daef2-162">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="daef2-163">Exchange、SharePoint、OneDrive 和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="daef2-163">Exchange, SharePoint, OneDrive, Office 365 groups</span></span>  <br/> |
   
<span data-ttu-id="daef2-164">在 Exchange 中，自动应用（同时针对查询和敏感信息类型）的保留标签只会应用于新发送的邮件（传输中的数据），而非当前邮箱中的所有项目（静态数据）。</span><span class="sxs-lookup"><span data-stu-id="daef2-164">In Exchange, auto-apply retention labels (for both queries and sensitive information types) are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="daef2-165">此外，用于敏感信息类型的自动应用的保留标签只能应用于全部邮箱；不能选择特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="daef2-165">Also, auto-apply retention labels for sensitive information types can apply only to all mailboxes; you can't select the specific mailboxes.</span></span>
  
<span data-ttu-id="daef2-166">Exchange 公用文件夹和 Skype 不支持保留标签。</span><span class="sxs-lookup"><span data-stu-id="daef2-166">Exchange public folders and Skype do not support retention labels.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="daef2-167">配置自动应用保留标签的条件</span><span class="sxs-lookup"><span data-stu-id="daef2-167">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="daef2-168">可将保留标签自动应用于包含以下各项的内容：</span><span class="sxs-lookup"><span data-stu-id="daef2-168">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="daef2-169">特定类型敏感信息</span><span class="sxs-lookup"><span data-stu-id="daef2-169">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="daef2-170">与你创建的查询匹配的特定关键字</span><span class="sxs-lookup"><span data-stu-id="daef2-170">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="daef2-171">可训练分类器的匹配项</span><span class="sxs-lookup"><span data-stu-id="daef2-171">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![自动应用标签的“选择条件”页](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="daef2-173">自动应用保留标签最多可能需要 7 天才会应用到与你配置的条件相匹配的所有内容。</span><span class="sxs-lookup"><span data-stu-id="daef2-173">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="daef2-174">将标签自动应用于包含特定类型敏感信息的内容</span><span class="sxs-lookup"><span data-stu-id="daef2-174">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="daef2-175">为敏感信息创建自动应用保留标签时，可看到与创建数据丢失防护 (DLP) 策略时相同的策略模板列表。</span><span class="sxs-lookup"><span data-stu-id="daef2-175">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="daef2-176">预配置每个策略模板以查找特定类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="daef2-176">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="daef2-177">例如，此处显示的模板用于查找美国 ITIN、SSN 和护照号码。</span><span class="sxs-lookup"><span data-stu-id="daef2-177">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="daef2-178">若要深入了解 DLP，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="daef2-178">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![包含敏感信息类型的策略模板](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="daef2-p112">选择策略模板后，既可以添加或删除任意类型敏感信息，也可以更改实例计数和匹配准确度。在下面的示例中，保留标签仅在以下情况下自动应用：</span><span class="sxs-lookup"><span data-stu-id="daef2-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="daef2-p113">内容包含的这三种类型敏感信息的实例数介于 1 和 9 个之间。可删除“最大”\*\*\*\* 值，这样就会变为“任意”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="daef2-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="daef2-p114">检测到的敏感信息类型的匹配准确度（或可信度）至少为 75。许多敏感信息类型都是通过多个模式进行定义，其中模式的匹配准确度越高，需要发现的证据（如关键字、日期或地址）就越多，而模式的匹配准确度越低，需要发现的证据就越少。简而言之，“最小”\*\*\*\* 匹配准确度越低，内容就越容易与条件匹配。</span><span class="sxs-lookup"><span data-stu-id="daef2-p114">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="daef2-187">要详细了解这些选项，请参阅[微调规则以增加或降低匹配的难度](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="daef2-187">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![用于确定敏感信息类型的选项](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="daef2-189">将标签自动应用于包含关键字或可搜索属性的内容</span><span class="sxs-lookup"><span data-stu-id="daef2-189">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="daef2-p115">可将标签自动应用于满足特定条件的内容。目前可用的条件支持将标签应用于包含特定字词、短语或可搜索属性值的内容。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。</span><span class="sxs-lookup"><span data-stu-id="daef2-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="daef2-193">有关查询语法的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="daef2-193">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="daef2-194">关键字查询语言 (KQL) 语法参考</span><span class="sxs-lookup"><span data-stu-id="daef2-194">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="daef2-p116">基于查询的标签使用搜索索引来标识内容。有关有效可搜索属性的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="daef2-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="daef2-197">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="daef2-197">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="daef2-198">已爬网和托管属性在 SharePoint Server 中的概述</span><span class="sxs-lookup"><span data-stu-id="daef2-198">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="daef2-199">示例查询：</span><span class="sxs-lookup"><span data-stu-id="daef2-199">Examples queries:</span></span>

- <span data-ttu-id="daef2-200">Exchange</span><span class="sxs-lookup"><span data-stu-id="daef2-200">Exchange</span></span>
    - <span data-ttu-id="daef2-201">subject:"Quarterly Financials"</span><span class="sxs-lookup"><span data-stu-id="daef2-201">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="daef2-202">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="daef2-202">recipients:garthf</span></span><!--nolink--><span data-ttu-id="daef2-203">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="daef2-203">@contoso.com</span></span>
- <span data-ttu-id="daef2-204">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="daef2-204">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="daef2-205">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="daef2-205">contenttype:contract</span></span>
    - <span data-ttu-id="daef2-206">site:https</span><span class="sxs-lookup"><span data-stu-id="daef2-206">site:https</span></span><!--nolink--><span data-ttu-id="daef2-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="daef2-207">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![查询编辑器](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="daef2-209">使用可训练分类器向内容自动应用标签</span><span class="sxs-lookup"><span data-stu-id="daef2-209">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="daef2-210">选择可训练分类器的选项后，可选择其中一个内置分类器或选择自定义分类器。</span><span class="sxs-lookup"><span data-stu-id="daef2-210">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="daef2-211">内置分类器包含**简历**、**源代码**、**有针对性的骚扰**、**侮辱**和**威胁**：</span><span class="sxs-lookup"><span data-stu-id="daef2-211">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![选择可训练分类器](../media/retention-label-classifers.png)

<span data-ttu-id="daef2-213">要通过此选项自动应用标签，SharePoint Online 网站和邮箱必须至少有 10 MB 的数据。</span><span class="sxs-lookup"><span data-stu-id="daef2-213">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="daef2-214">有关可训练分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="daef2-214">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="daef2-215">有关示例配置，请参阅[如何做好准备并使用内置分类器](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs)。</span><span class="sxs-lookup"><span data-stu-id="daef2-215">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="daef2-216">保留标签需要多长时间才能生效</span><span class="sxs-lookup"><span data-stu-id="daef2-216">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="daef2-217">保留标签在发布或自动应用后不会立即生效：</span><span class="sxs-lookup"><span data-stu-id="daef2-217">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="daef2-218">首先，需要将标签策略从管理中心同步到策略中的位置。</span><span class="sxs-lookup"><span data-stu-id="daef2-218">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="daef2-219">然后，该位置可能需要一段时间才能使已发布的保留标签对最终用户可用或将标签自动应用到内容。</span><span class="sxs-lookup"><span data-stu-id="daef2-219">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="daef2-220">所需时间长短取决于保留标签的位置和类型。</span><span class="sxs-lookup"><span data-stu-id="daef2-220">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="daef2-221">已发布的保留标签</span><span class="sxs-lookup"><span data-stu-id="daef2-221">Published retention labels</span></span>

<span data-ttu-id="daef2-p119">如果将保留标签发布到 SharePoint 或 OneDrive，可能需要等待 1 天时间，这些保留标签才会向最终用户显示。此外，如果向 Exchange 发布保留标签，可能需要等待 7 天，这些保留标签才会向最终用户显示，并且邮箱至少必须包含 10MB 数据。</span><span class="sxs-lookup"><span data-stu-id="daef2-p119">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![手动标签生效时间关系图](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="daef2-225">自动应用保留标签</span><span class="sxs-lookup"><span data-stu-id="daef2-225">Auto-apply retention labels</span></span>

<span data-ttu-id="daef2-226">如果将保留标签自动应用于符合特定条件的内容，可能需要等待 7 天，才能将保留标签应用于与条件匹配的所有现有内容。</span><span class="sxs-lookup"><span data-stu-id="daef2-226">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![自动应用标签生效时间关系图](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="daef2-228">如何检查发布到 Exchange 的保留标签的状态</span><span class="sxs-lookup"><span data-stu-id="daef2-228">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="daef2-p120">在 Exchange Online 中，有一个流程每 7 天运行一次，用于向最终用户提供保留标签。使用 PowerShell，可查看此流程的上次运行时间，从而确定它何时再次运行。</span><span class="sxs-lookup"><span data-stu-id="daef2-p120">In Exchange Online, retention labels are made available to end users by a process that runs every seven days. By using Powershell, you can see when this process last ran and thus determine when it will run again.</span></span>
  
1. <span data-ttu-id="daef2-231">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773)。</span><span class="sxs-lookup"><span data-stu-id="daef2-231">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="daef2-232">运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="daef2-232">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="daef2-233">在结果中，`ELCLastSuccessTimeStamp` (UTC) 属性显示系统上次处理你邮箱的时间。</span><span class="sxs-lookup"><span data-stu-id="daef2-233">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="daef2-234">如果自创建策略起未处理，则不会显示标签。</span><span class="sxs-lookup"><span data-stu-id="daef2-234">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="daef2-235">若要强制处理，请运行 `Start-ManagedFolderAssistant -Identity <user>`。</span><span class="sxs-lookup"><span data-stu-id="daef2-235">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="daef2-236">如果标签没有显示在 Outlook 网页版中，但你认为标签应显示，请务必清除浏览器中的缓存 (Ctrl+F5)。</span><span class="sxs-lookup"><span data-stu-id="daef2-236">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="daef2-237">更新保留标签及其策略</span><span class="sxs-lookup"><span data-stu-id="daef2-237">Updating retention labels and their policies</span></span>

<span data-ttu-id="daef2-238">如果要编辑保留标签、保留标签策略或自动应用策略，并且该保留标签已应用到内容，则更新后的设置将自动应用于此内容以及新标记的内容。</span><span class="sxs-lookup"><span data-stu-id="daef2-238">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="daef2-239">查找保留标签的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="daef2-239">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="daef2-240">要使用保留标签 cmdlet，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="daef2-240">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="daef2-241">连接到 Office 365 安全与合规中心 Powershell</span><span class="sxs-lookup"><span data-stu-id="daef2-241">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="daef2-242">使用这些 Office 365 安全与合规中心 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="daef2-242">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="daef2-243">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="daef2-243">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)
    
    - [<span data-ttu-id="daef2-244">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="daef2-244">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)
    
    - [<span data-ttu-id="daef2-245">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="daef2-245">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)
    
    - [<span data-ttu-id="daef2-246">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="daef2-246">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)
    
    - [<span data-ttu-id="daef2-247">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="daef2-247">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)
    
    - [<span data-ttu-id="daef2-248">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="daef2-248">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)
    
    - [<span data-ttu-id="daef2-249">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="daef2-249">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="daef2-250">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="daef2-250">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="daef2-251">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="daef2-251">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="daef2-252">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="daef2-252">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="daef2-253">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="daef2-253">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)
    
    - [<span data-ttu-id="daef2-254">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="daef2-254">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)
    
    - [<span data-ttu-id="daef2-255">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="daef2-255">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="daef2-256">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="daef2-256">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
