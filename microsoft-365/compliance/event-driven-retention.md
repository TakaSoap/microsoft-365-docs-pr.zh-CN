---
title: 事件驱动保留概述
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 通常，它是记录管理解决方案的一部分，你可以配置保留标签以根据所识别的事件开始保留期。
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817801"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="55160-103">事件驱动保留概述</span><span class="sxs-lookup"><span data-stu-id="55160-103">Overview of event-driven retention</span></span>

><span data-ttu-id="55160-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="55160-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="55160-105">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="55160-105">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="55160-106">But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs.</span><span class="sxs-lookup"><span data-stu-id="55160-106">But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="55160-107">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="55160-107">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="55160-108">例如，可对以下事件结合使用标签和事件驱动保留：</span><span class="sxs-lookup"><span data-stu-id="55160-108">For example, you can use labels with event-driven retention for:</span></span>
  
- <span data-ttu-id="55160-109">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span><span class="sxs-lookup"><span data-stu-id="55160-109">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="55160-110">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed.</span><span class="sxs-lookup"><span data-stu-id="55160-110">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed.</span></span> <span data-ttu-id="55160-111">The event that triggers the 10-year retention period is the employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="55160-111">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="55160-112">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires.</span><span class="sxs-lookup"><span data-stu-id="55160-112">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="55160-113">The event that triggers the five-year retention period is the expiration of the contract.</span><span class="sxs-lookup"><span data-stu-id="55160-113">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="55160-114">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span><span class="sxs-lookup"><span data-stu-id="55160-114">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="55160-115">In this case, the last manufacturing date is the event that triggers the retention period.</span><span class="sxs-lookup"><span data-stu-id="55160-115">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="55160-116">Event-driven retention is typically used as part of a records-management process.</span><span class="sxs-lookup"><span data-stu-id="55160-116">Event-driven retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="55160-117">This means that:</span><span class="sxs-lookup"><span data-stu-id="55160-117">This means that:</span></span>
  
- <span data-ttu-id="55160-118">Labels based on events also usually classify content as a record.</span><span class="sxs-lookup"><span data-stu-id="55160-118">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="55160-119">For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span><span class="sxs-lookup"><span data-stu-id="55160-119">For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span></span>
    
- <span data-ttu-id="55160-120">如果文档已声明为记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。</span><span class="sxs-lookup"><span data-stu-id="55160-120">A document that's been declared as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="55160-121">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content.</span><span class="sxs-lookup"><span data-stu-id="55160-121">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content.</span></span> <span data-ttu-id="55160-122">For more information, see [Disposition of content](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="55160-122">For more information, see [Disposition of content](disposition.md).</span></span>
    
<span data-ttu-id="55160-123">基于事件的标签与 Microsoft 365 中的任何保留标签具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="55160-123">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="55160-124">有关详细信息，请参阅[了解保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="55160-124">For more information, see [Learn about retention labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="55160-125">了解事件类型、标签、事件和资产 ID 之间的关系</span><span class="sxs-lookup"><span data-stu-id="55160-125">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="55160-126">为了成功使用事件驱动保留，请务必了解事件类型、保留标签、事件和资产 ID 之间的关系，如下图以及随后的说明所示：</span><span class="sxs-lookup"><span data-stu-id="55160-126">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![事件类型、标签、事件和资产 ID 的关系图](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件类型、标签、事件和资产 ID 的关系图](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="55160-129">为不同类型的内容创建保留标签，然后将其与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="55160-129">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="55160-130">例如，不同类型的产品文件和记录的保留标签与“产品生存期”事件类型相关联，因为必须将这些记录自产品生存期结束起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="55160-130">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="55160-131">用户（通常是记录管理人员）将这些保留标签应用于内容，并（对于 SharePoint 和 OneDrive 文档）为每一项输入资产 ID。</span><span class="sxs-lookup"><span data-stu-id="55160-131">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="55160-132">在此示例中，资产 ID 是组织使用的产品名称或代码。</span><span class="sxs-lookup"><span data-stu-id="55160-132">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="55160-133">因此，每个产品的记录都分配有一个保留标签，且每个记录都有包含资产 ID 的属性。</span><span class="sxs-lookup"><span data-stu-id="55160-133">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="55160-134">上图表示组织中所有产品记录的**全部内容**，且每一项都有记录所属产品的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="55160-134">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="55160-135">Product Lifetime is the event type; a specific product reaching end of life is an event.</span><span class="sxs-lookup"><span data-stu-id="55160-135">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="55160-136">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span><span class="sxs-lookup"><span data-stu-id="55160-136">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="55160-137">资产 ID（对于 SharePoint 和 OneDrive 文档）</span><span class="sxs-lookup"><span data-stu-id="55160-137">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="55160-138">Keywords (for Exchange items).</span><span class="sxs-lookup"><span data-stu-id="55160-138">Keywords (for Exchange items).</span></span> <span data-ttu-id="55160-139">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span><span class="sxs-lookup"><span data-stu-id="55160-139">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="55160-140">The date when the event occurred.</span><span class="sxs-lookup"><span data-stu-id="55160-140">The date when the event occurred.</span></span> <span data-ttu-id="55160-141">This date is used as the start of the retention period.</span><span class="sxs-lookup"><span data-stu-id="55160-141">This date is used as the start of the retention period.</span></span> <span data-ttu-id="55160-142">This date can be the current, a past, or a future date.</span><span class="sxs-lookup"><span data-stu-id="55160-142">This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="55160-143">在你创建事件后，相应事件日期就会同步到符合以下条件的所有内容：具有相应事件类型的保留标签，且包含指定的资产 ID 或关键字。</span><span class="sxs-lookup"><span data-stu-id="55160-143">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="55160-144">与任何保留标签一样，这种同步最长可能需要 7 天才能完成。</span><span class="sxs-lookup"><span data-stu-id="55160-144">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="55160-145">在上图中，所有用红色圈起来的项的保留期都是由此事件触发的。</span><span class="sxs-lookup"><span data-stu-id="55160-145">In the previous diagram, all the items circled in red have their retention period triggered by this event .</span></span> <span data-ttu-id="55160-146">换言之，当此产品的生存期结束时，相应事件就会触发此产品的记录的保留期。</span><span class="sxs-lookup"><span data-stu-id="55160-146">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="55160-147">请务必注意，如果没有为事件指定资产 ID 或关键字，则具有该事件类型标签的**所有内容**均由该事件触发保留期。</span><span class="sxs-lookup"><span data-stu-id="55160-147">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="55160-148">也就是说，在上图中，所有内容将开始被保留。</span><span class="sxs-lookup"><span data-stu-id="55160-148">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="55160-149">这可能并非如你所愿。</span><span class="sxs-lookup"><span data-stu-id="55160-149">This might not be what you intend.</span></span> 
  
<span data-ttu-id="55160-150">最后，请注意，每个保留标签都有自己的保留设置。</span><span class="sxs-lookup"><span data-stu-id="55160-150">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="55160-151">在此示例中，它们全都指定保留 10 年，但事件也可触发保留期不同的各个保留标签。</span><span class="sxs-lookup"><span data-stu-id="55160-151">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="55160-152">如何设置事件驱动保留</span><span class="sxs-lookup"><span data-stu-id="55160-152">How to set up event-driven retention</span></span>

<span data-ttu-id="55160-153">事件驱动保留的工作流概览：</span><span class="sxs-lookup"><span data-stu-id="55160-153">High-level workflow for event-driven retention:</span></span>
  
![事件驱动保留的设置工作流的关系图](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="55160-155">有关使用 SharePont 中的托管属性来自动应用保留标签并实施事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="55160-155">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="55160-156">第 1 步：创建保留期以事件为依据的标签</span><span class="sxs-lookup"><span data-stu-id="55160-156">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="55160-157">在 Microsoft 365 合规中心的左侧导航中，选择“**信息治理**” > “**标签**” > “**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="55160-157">In the Microsoft 365 compliance center, in the left navigation, select **Information governance** > **Labels** > **Create a label**.</span></span> <span data-ttu-id="55160-158">如果“**信息治理**”未显示在导航窗格中，请向下滚动并选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="55160-158">If **Information governance** does not display in the navigation pane, scroll down and select **Show all**.</span></span>
  
<span data-ttu-id="55160-159">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event.</span><span class="sxs-lookup"><span data-stu-id="55160-159">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event.</span></span> <span data-ttu-id="55160-160">This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span><span class="sxs-lookup"><span data-stu-id="55160-160">This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="55160-161">请注意，事件驱动保留通常用于分类为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="55160-161">Note that event-driven retention is typically used for content that's classified as a record.</span></span> <span data-ttu-id="55160-162">因此，创建基于事件的保留标签时，通常需要选择“使用标签将内容分类为‘记录’”\*\*\*\* 选项。</span><span class="sxs-lookup"><span data-stu-id="55160-162">For this reason, when you create retention labels based on an event, you typically choose the option to **Use label to classify content as a "Record"**.</span></span>
  
<span data-ttu-id="55160-163">另请注意，事件驱动保留要求保留设置必须：</span><span class="sxs-lookup"><span data-stu-id="55160-163">Also note that event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="55160-164">保留内容。</span><span class="sxs-lookup"><span data-stu-id="55160-164">Retain the content.</span></span>
    
- <span data-ttu-id="55160-165">在保留期到期时自动删除内容或触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="55160-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![让标签基于事件的选项](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="55160-167">第 2 步：选择与此标签关联的事件类型</span><span class="sxs-lookup"><span data-stu-id="55160-167">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="55160-168">在标签设置中，选择将标签基于**事件**的选项后，将看到“**选择事件类型**”选项。</span><span class="sxs-lookup"><span data-stu-id="55160-168">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="55160-169">事件类型就是对要将标签与之相关联的事件的一般说明。</span><span class="sxs-lookup"><span data-stu-id="55160-169">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="55160-170">例如，如果创建“产品生存期”事件类型，将创建基于事件的保留标签，标签名称描述了要将标签应用于什么类型的内容（如“产品开发文件”或“产品业务决策记录”）。</span><span class="sxs-lookup"><span data-stu-id="55160-170">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="55160-171">请注意，一旦选择事件类型和创建保留标签后，便无法再更改事件类型。</span><span class="sxs-lookup"><span data-stu-id="55160-171">Note that once you choose an event type and create the retention label, the event type cannot be changed.</span></span>
  
![用于创建或选择事件类型的选项](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="55160-173">第 3 步：发布或自动应用基于事件的保留标签</span><span class="sxs-lookup"><span data-stu-id="55160-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="55160-174">与任何保留标签类似，需要[发布或自动应用](create-retention-labels.md)基于事件的标签，以便将其手动或自动应用到内容。</span><span class="sxs-lookup"><span data-stu-id="55160-174">Just like any retention label, you need to [publish or auto-apply](create-retention-labels.md) an event-based label, so that it's manually or automatically applied to content.</span></span>

> [!NOTE]
> <span data-ttu-id="55160-175">如果从“**记录管理**” > “**文件计划**”选项卡或“**数据管理**” > “**标签**”选项卡中选择事件驱动的保留标签，“**自动应用标签**”按钮将不可用。</span><span class="sxs-lookup"><span data-stu-id="55160-175">If you select an event-driven retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="55160-176">请使用以下位置之一的标签或策略列表上方的“**自动应用标签**”选项来代替此按钮：</span><span class="sxs-lookup"><span data-stu-id="55160-176">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="55160-177">“**记录管理**” > “**标签策略**”选项卡</span><span class="sxs-lookup"><span data-stu-id="55160-177">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="55160-178">“**数据管理**” > “**标签**”选项卡或“**标签策略**”选项卡</span><span class="sxs-lookup"><span data-stu-id="55160-178">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![用于发布或自动应用保留标签的选项](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="55160-180">第 4 步：输入资产 ID</span><span class="sxs-lookup"><span data-stu-id="55160-180">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="55160-181">After an event-driven label is applied to content, you can enter an asset ID for each item.</span><span class="sxs-lookup"><span data-stu-id="55160-181">After an event-driven label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="55160-182">For example, your organization might use:</span><span class="sxs-lookup"><span data-stu-id="55160-182">For example, your organization might use:</span></span>
  
- <span data-ttu-id="55160-183">产品代码：可用于仅保留特定产品的内容。</span><span class="sxs-lookup"><span data-stu-id="55160-183">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="55160-184">项目代码：可用于仅保留特定项目的内容。</span><span class="sxs-lookup"><span data-stu-id="55160-184">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="55160-185">员工 ID：可用于仅保留特定人员的内容。</span><span class="sxs-lookup"><span data-stu-id="55160-185">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="55160-186">请务必理解，资产 ID 只是 SharePoint 和 OneDrive for Business 中的另一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="55160-186">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="55160-187">你的组织可能已经使用其他文档属性和 ID 来分类内容。</span><span class="sxs-lookup"><span data-stu-id="55160-187">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="55160-188">如果是这样，还可以在创建事件时使用这些属性和值（请参见后面的第 6 步）。</span><span class="sxs-lookup"><span data-stu-id="55160-188">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="55160-189">请务必注意，组织必须在文档属性中使用某种属性:值组合，将相应项与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="55160-189">The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![用于输入资产 ID 的文本框](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="55160-191">第 5 步：创建事件</span><span class="sxs-lookup"><span data-stu-id="55160-191">Step 5: Create an event</span></span>

<span data-ttu-id="55160-192">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span><span class="sxs-lookup"><span data-stu-id="55160-192">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="55160-193">You need to manually trigger an event by creating it.</span><span class="sxs-lookup"><span data-stu-id="55160-193">You need to manually trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="55160-194">第 6 步：选择第 2 步中标签使用的相同事件类型</span><span class="sxs-lookup"><span data-stu-id="55160-194">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="55160-195">创建事件时，请选择第 2 步中的保留标签所使用的相同事件类型，如“产品生存期”。</span><span class="sxs-lookup"><span data-stu-id="55160-195">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="55160-196">只有具有相应事件类型的保留标签的内容，才会触发保留期。</span><span class="sxs-lookup"><span data-stu-id="55160-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![“事件设置”中用于选择事件类型的选项](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="55160-198">第 7 步：输入关键字或资产 ID</span><span class="sxs-lookup"><span data-stu-id="55160-198">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="55160-199">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span><span class="sxs-lookup"><span data-stu-id="55160-199">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span></span> <span data-ttu-id="55160-200">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span><span class="sxs-lookup"><span data-stu-id="55160-200">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span></span> <span data-ttu-id="55160-201">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span><span class="sxs-lookup"><span data-stu-id="55160-201">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="55160-202">请务必理解，资产 ID 只是 SharePoint 和 OneDrive for Business 中的另一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="55160-202">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="55160-203">如果使用的是资产 ID 属性，需在下方所示的资产 ID 框中输入 ComplianceAssetID:\<value\>。</span><span class="sxs-lookup"><span data-stu-id="55160-203">If you're using the Asset ID property, you would enter ComplianceAssetID:\<value\> in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="55160-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span><span class="sxs-lookup"><span data-stu-id="55160-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="55160-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span><span class="sxs-lookup"><span data-stu-id="55160-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="55160-206">In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span><span class="sxs-lookup"><span data-stu-id="55160-206">In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="55160-207">For Exchange items, you can include keywords.</span><span class="sxs-lookup"><span data-stu-id="55160-207">For Exchange items, you can include keywords.</span></span> <span data-ttu-id="55160-208">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="55160-208">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="55160-209">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="55160-209">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="55160-210">最后，选择事件发生日期；此日期用作保留期的开始日期。</span><span class="sxs-lookup"><span data-stu-id="55160-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="55160-211">创建事件后，相应事件日期就会同步到所有具有相应事件类型的保留标签、资产 ID 和关键字的内容。</span><span class="sxs-lookup"><span data-stu-id="55160-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="55160-212">与任何保留标签一样，这种同步最长可能需要 7 天才能完成。</span><span class="sxs-lookup"><span data-stu-id="55160-212">Like any retention label, this synchronization can take up to 7 days.</span></span>
  
![“事件设置”页](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="55160-214">使用内容搜索来查找所有包含特定标签或资产 ID 的内容</span><span class="sxs-lookup"><span data-stu-id="55160-214">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="55160-215">在保留标签分配到内容后，可通过内容搜索，查找所有已使用特定保留标签进行分类或包含特定资产 ID 的内容。</span><span class="sxs-lookup"><span data-stu-id="55160-215">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID.</span></span>
  
<span data-ttu-id="55160-216">创建内容搜索后：</span><span class="sxs-lookup"><span data-stu-id="55160-216">When you create a content search:</span></span>
  
- <span data-ttu-id="55160-217">若要查找所有包含特定保留标签的内容，请选择“合规性标记”\*\*\*\* 条件，再输入完整或部分标签名称并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="55160-217">To find all content with a specific retention label, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="55160-218">要查找所有包含特定资产 ID 的内容，请输入 **ComplianceAssetID** 属性和值，如 ComplianceAssetID:\<value\>。</span><span class="sxs-lookup"><span data-stu-id="55160-218">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, like ComplianceAssetID:\<value\>.</span></span> 
    
<span data-ttu-id="55160-219">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="55160-219">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="55160-220">权限</span><span class="sxs-lookup"><span data-stu-id="55160-220">Permissions</span></span>

<span data-ttu-id="55160-221">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span><span class="sxs-lookup"><span data-stu-id="55160-221">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="55160-222">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span><span class="sxs-lookup"><span data-stu-id="55160-222">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="55160-223">有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="55160-223">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="55160-224">使用 PowerShell 自动触发事件</span><span class="sxs-lookup"><span data-stu-id="55160-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="55160-225">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs.</span><span class="sxs-lookup"><span data-stu-id="55160-225">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs.</span></span> <span data-ttu-id="55160-226">However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="55160-226">However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="55160-227">此外，还可使用 PowerShell 脚本从业务应用程序中自动执行基于事件的保留。</span><span class="sxs-lookup"><span data-stu-id="55160-227">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="55160-228">适用于事件驱动保留的 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="55160-228">The PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="55160-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="55160-229">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="55160-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="55160-230">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="55160-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="55160-231">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="55160-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="55160-232">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="55160-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="55160-233">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="55160-234">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="55160-234">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

