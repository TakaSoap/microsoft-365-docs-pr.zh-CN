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
ms.openlocfilehash: f2cf60eac1197ed7be3fd8cbbe69e41a37614f86
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048287"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="05bc6-103">事件驱动保留概述</span><span class="sxs-lookup"><span data-stu-id="05bc6-103">Overview of event-driven retention</span></span>

><span data-ttu-id="05bc6-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="05bc6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="05bc6-105">When you retain content, the retention period is often based on the age of the content.</span><span class="sxs-lookup"><span data-stu-id="05bc6-105">When you retain content, the retention period is often based on the age of the content.</span></span> <span data-ttu-id="05bc6-106">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="05bc6-106">For example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="05bc6-107">But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs.</span><span class="sxs-lookup"><span data-stu-id="05bc6-107">But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="05bc6-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="05bc6-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="05bc6-109">使用事件驱动保留的示例：</span><span class="sxs-lookup"><span data-stu-id="05bc6-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="05bc6-110">**员工离开组织**假设自员工离开组织之日起，必须将其记录保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="05bc6-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="05bc6-111">10 年过后，与该员工的雇用、绩效和离职相关的所有文档都需要进行处置。</span><span class="sxs-lookup"><span data-stu-id="05bc6-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="05bc6-112">员工离开组织便是触发 10 年保留期的事件。</span><span class="sxs-lookup"><span data-stu-id="05bc6-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="05bc6-113">**合同到期** 假设与合同相关的所有记录都需要在合同到期后保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="05bc6-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="05bc6-114">触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="05bc6-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="05bc6-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span><span class="sxs-lookup"><span data-stu-id="05bc6-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="05bc6-116">In this case, the last manufacturing date is the event that triggers the retention period.</span><span class="sxs-lookup"><span data-stu-id="05bc6-116">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="05bc6-117">Event-driven retention is typically used as part of a records-management process.</span><span class="sxs-lookup"><span data-stu-id="05bc6-117">Event-driven retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="05bc6-118">This means that:</span><span class="sxs-lookup"><span data-stu-id="05bc6-118">This means that:</span></span>
  
- <span data-ttu-id="05bc6-119">基于事件的标签通常还可将内容分类为记录。</span><span class="sxs-lookup"><span data-stu-id="05bc6-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="05bc6-120">有关详细信息，请参阅[了解记录](records.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-120">For more information, see [Learn about records](records.md).</span></span>
    
- <span data-ttu-id="05bc6-121">如果文档已归类为记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。</span><span class="sxs-lookup"><span data-stu-id="05bc6-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="05bc6-122">基于事件的保留标签通常在保留期末尾触发处置评审，因此记录管理人员可以手动评审并处置内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="05bc6-123">有关详细信息，请参阅[内容的处置](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-123">For more information, see [Disposition of content](disposition.md).</span></span>
    
<span data-ttu-id="05bc6-124">基于事件的保留标签与 Microsoft 365 中的任何保留标签具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="05bc6-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="05bc6-125">有关详细信息，请参阅[了解保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-125">For more information, see [Learn about retention labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="05bc6-126">了解事件类型、标签、事件和资产 ID 之间的关系</span><span class="sxs-lookup"><span data-stu-id="05bc6-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="05bc6-127">为了成功使用事件驱动保留，请务必了解事件类型、保留标签、事件和资产 ID 之间的关系，如下图以及随后的说明所示：</span><span class="sxs-lookup"><span data-stu-id="05bc6-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![事件类型、标签、事件和资产 ID 的关系图](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件类型、标签、事件和资产 ID 的关系图](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="05bc6-130">为不同类型的内容创建保留标签，然后将其与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="05bc6-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="05bc6-131">例如，不同类型的产品文件和记录的保留标签与“产品生存期”事件类型相关联，因为必须将这些记录自产品生存期结束起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="05bc6-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="05bc6-132">用户（通常是记录管理人员）将这些保留标签应用于内容，并（对于 SharePoint 和 OneDrive 文档）为每一项输入资产 ID。</span><span class="sxs-lookup"><span data-stu-id="05bc6-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="05bc6-133">在此示例中，资产 ID 是组织使用的产品名称或代码。</span><span class="sxs-lookup"><span data-stu-id="05bc6-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="05bc6-134">因此，每个产品的记录都分配有一个保留标签，且每个记录都有包含资产 ID 的属性。</span><span class="sxs-lookup"><span data-stu-id="05bc6-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="05bc6-135">上图表示组织中所有产品记录的**全部内容**，且每一项都有记录所属产品的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="05bc6-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="05bc6-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span><span class="sxs-lookup"><span data-stu-id="05bc6-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="05bc6-137">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span><span class="sxs-lookup"><span data-stu-id="05bc6-137">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="05bc6-138">资产 ID（对于 SharePoint 和 OneDrive 文档）</span><span class="sxs-lookup"><span data-stu-id="05bc6-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="05bc6-139">Keywords (for Exchange items).</span><span class="sxs-lookup"><span data-stu-id="05bc6-139">Keywords (for Exchange items).</span></span> <span data-ttu-id="05bc6-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span><span class="sxs-lookup"><span data-stu-id="05bc6-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="05bc6-141">The date when the event occurred.</span><span class="sxs-lookup"><span data-stu-id="05bc6-141">The date when the event occurred.</span></span> <span data-ttu-id="05bc6-142">This date is used as the start of the retention period.</span><span class="sxs-lookup"><span data-stu-id="05bc6-142">This date is used as the start of the retention period.</span></span> <span data-ttu-id="05bc6-143">This date can be the current, a past, or a future date.</span><span class="sxs-lookup"><span data-stu-id="05bc6-143">This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="05bc6-144">在你创建事件后，相应事件日期就会同步到符合以下条件的所有内容：具有相应事件类型的保留标签，且包含指定的资产 ID 或关键字。</span><span class="sxs-lookup"><span data-stu-id="05bc6-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="05bc6-145">与任何保留标签一样，这种同步最长可能需要 7 天才能完成。</span><span class="sxs-lookup"><span data-stu-id="05bc6-145">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="05bc6-146">在上图中，所有用红色圈起来的项的保留期都是由此事件触发的。</span><span class="sxs-lookup"><span data-stu-id="05bc6-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="05bc6-147">换言之，当此产品的生存期结束时，相应事件就会触发此产品的记录的保留期。</span><span class="sxs-lookup"><span data-stu-id="05bc6-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="05bc6-148">请务必注意，如果没有为事件指定资产 ID 或关键字，则具有该事件类型标签的**所有内容**均由该事件触发保留期。</span><span class="sxs-lookup"><span data-stu-id="05bc6-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="05bc6-149">也就是说，在上图中，所有内容将开始被保留。</span><span class="sxs-lookup"><span data-stu-id="05bc6-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="05bc6-150">这可能并非如你所愿。</span><span class="sxs-lookup"><span data-stu-id="05bc6-150">This might not be what you intend.</span></span> 
  
<span data-ttu-id="05bc6-151">最后，请注意，每个保留标签都有自己的保留设置。</span><span class="sxs-lookup"><span data-stu-id="05bc6-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="05bc6-152">在此示例中，它们全都指定保留 10 年，但事件也可触发保留期不同的各个保留标签。</span><span class="sxs-lookup"><span data-stu-id="05bc6-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="05bc6-153">如何设置事件驱动保留</span><span class="sxs-lookup"><span data-stu-id="05bc6-153">How to set up event-driven retention</span></span>

<span data-ttu-id="05bc6-154">事件驱动保留的工作流概览：</span><span class="sxs-lookup"><span data-stu-id="05bc6-154">High-level workflow for event-driven retention:</span></span>
  
![事件驱动保留的设置工作流的关系图](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="05bc6-156">有关使用 SharePont 中的托管属性来自动应用保留标签并实施事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="05bc6-157">第 1 步：创建保留期以事件为依据的标签</span><span class="sxs-lookup"><span data-stu-id="05bc6-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="05bc6-158">要创建和配置保留标签，请按照[创建和配置保留标签](create-retention-labels.md#create-and-configure-retention-labels)中的说明进行操作，并在打开保留功能时，根据事件选择保留或删除内容的选项。</span><span class="sxs-lookup"><span data-stu-id="05bc6-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="05bc6-159">此设置意味着，保留设置暂不会生效，直到在步骤 5 中在“**事件**”页面上创建事件之后。</span><span class="sxs-lookup"><span data-stu-id="05bc6-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="05bc6-160">事件驱动的保留通常用于归类为记录的内容，因此这是检查是否还需要选择将内容标记为记录的选项的好时机。</span><span class="sxs-lookup"><span data-stu-id="05bc6-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="05bc6-161">事件驱动保留要求保留设置：</span><span class="sxs-lookup"><span data-stu-id="05bc6-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="05bc6-162">保留内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-162">Retain the content.</span></span>
    
- <span data-ttu-id="05bc6-163">在保留期到期时自动删除内容或触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="05bc6-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![让标签基于事件的选项](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="05bc6-165">第 2 步：选择与此标签关联的事件类型</span><span class="sxs-lookup"><span data-stu-id="05bc6-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="05bc6-166">在标签设置中，选择将标签基于**事件**的选项后，将看到“**选择事件类型**”选项。</span><span class="sxs-lookup"><span data-stu-id="05bc6-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="05bc6-167">事件类型就是对要将标签与之相关联的事件的一般说明。</span><span class="sxs-lookup"><span data-stu-id="05bc6-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="05bc6-168">例如，如果创建“产品生存期”事件类型，将创建基于事件的保留标签，标签名称描述了要将标签应用于什么类型的内容（如“产品开发文件”或“产品业务决策记录”）。</span><span class="sxs-lookup"><span data-stu-id="05bc6-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="05bc6-169">选择事件类型并保存保留标签后，便无法再更改事件类型。</span><span class="sxs-lookup"><span data-stu-id="05bc6-169">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![用于创建或选择事件类型的选项](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="05bc6-171">第 3 步：发布或自动应用基于事件的保留标签</span><span class="sxs-lookup"><span data-stu-id="05bc6-171">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="05bc6-172">与任何保留标签类似，需要[发布或自动应用](create-retention-labels.md)基于事件的标签，以便将其手动或自动应用到内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-172">Just like any retention label, you need to [publish or auto-apply](create-retention-labels.md) an event-based label, so that it's manually or automatically applied to content.</span></span>

> [!NOTE]
> <span data-ttu-id="05bc6-173">如果从“**记录管理**” > “**文件计划**”选项卡或“**数据管理**” > “**标签**”选项卡中选择事件驱动的保留标签，“**自动应用标签**”按钮将不可用。</span><span class="sxs-lookup"><span data-stu-id="05bc6-173">If you select an event-driven retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="05bc6-174">请使用以下位置之一的标签或策略列表上方的“**自动应用标签**”选项来代替此按钮：</span><span class="sxs-lookup"><span data-stu-id="05bc6-174">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="05bc6-175">“**记录管理**” > “**标签策略**”选项卡</span><span class="sxs-lookup"><span data-stu-id="05bc6-175">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="05bc6-176">“**数据管理**” > “**标签**”选项卡或“**标签策略**”选项卡</span><span class="sxs-lookup"><span data-stu-id="05bc6-176">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![用于发布或自动应用保留标签的选项](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="05bc6-178">第 4 步：输入资产 ID</span><span class="sxs-lookup"><span data-stu-id="05bc6-178">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="05bc6-179">After an event-driven label is applied to content, you can enter an asset ID for each item.</span><span class="sxs-lookup"><span data-stu-id="05bc6-179">After an event-driven label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="05bc6-180">For example, your organization might use:</span><span class="sxs-lookup"><span data-stu-id="05bc6-180">For example, your organization might use:</span></span>
  
- <span data-ttu-id="05bc6-181">产品代码：可用于仅保留特定产品的内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-181">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="05bc6-182">项目代码：可用于仅保留特定项目的内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-182">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="05bc6-183">员工 ID：可用于仅保留特定人员的内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-183">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="05bc6-184">资产 ID 只是 SharePoint 和 OneDrive 中的另一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="05bc6-184">Asset ID is simply another document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="05bc6-185">你的组织可能已经使用其他文档属性和 ID 来分类内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-185">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="05bc6-186">如果是这样，还可以在创建事件时使用这些属性和值（请参见后面的第 6 步）。</span><span class="sxs-lookup"><span data-stu-id="05bc6-186">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="05bc6-187">请务必注意，组织必须在文档属性中使用某种属性:值组合，将相应项与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="05bc6-187">The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![用于输入资产 ID 的文本框](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="05bc6-189">第 5 步：创建事件</span><span class="sxs-lookup"><span data-stu-id="05bc6-189">Step 5: Create an event</span></span>

<span data-ttu-id="05bc6-190">当相应事件类型的特定实例（例如，产品的生存期结束）发生时，请转到 Microsoft 365 合规中心内的“**记录管理**” > “**事件**”页，并创建事件。</span><span class="sxs-lookup"><span data-stu-id="05bc6-190">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="05bc6-191">需要通过创建事件来手动触发事件。</span><span class="sxs-lookup"><span data-stu-id="05bc6-191">You need to manually trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="05bc6-192">第 6 步：选择第 2 步中标签使用的相同事件类型</span><span class="sxs-lookup"><span data-stu-id="05bc6-192">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="05bc6-193">创建事件时，请选择第 2 步中的保留标签所使用的相同事件类型，如“产品生存期”。</span><span class="sxs-lookup"><span data-stu-id="05bc6-193">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="05bc6-194">只有具有相应事件类型的保留标签的内容，才会触发保留期。</span><span class="sxs-lookup"><span data-stu-id="05bc6-194">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![“事件设置”中用于选择事件类型的选项](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="05bc6-196">第 7 步：输入关键字或资产 ID</span><span class="sxs-lookup"><span data-stu-id="05bc6-196">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="05bc6-197">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span><span class="sxs-lookup"><span data-stu-id="05bc6-197">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content.</span></span> <span data-ttu-id="05bc6-198">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span><span class="sxs-lookup"><span data-stu-id="05bc6-198">For asset IDs, retention will be enforced only on content with the specified property:value pair.</span></span> <span data-ttu-id="05bc6-199">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span><span class="sxs-lookup"><span data-stu-id="05bc6-199">If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="05bc6-200">资产 ID 只是 SharePoint 和 OneDrive 中的另一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="05bc6-200">Asset ID is simply another document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="05bc6-201">如果使用的是资产 ID 属性，需在下方所示的资产 ID 框中输入 `ComplianceAssetID:<value>`。</span><span class="sxs-lookup"><span data-stu-id="05bc6-201">If you're using the Asset ID property, you would enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="05bc6-202">组织可能已经对与此事件类型相关的文档应用了其他属性和 ID。</span><span class="sxs-lookup"><span data-stu-id="05bc6-202">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="05bc6-203">例如，如果需要检测特定产品记录，ID 可能为自定义属性 ProductID 和值“XYZ”的组合。</span><span class="sxs-lookup"><span data-stu-id="05bc6-203">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="05bc6-204">在此情况下，需在下方所示的资产 ID 框中输入 `ProductID:XYZ`。</span><span class="sxs-lookup"><span data-stu-id="05bc6-204">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="05bc6-205">For Exchange items, you can include keywords.</span><span class="sxs-lookup"><span data-stu-id="05bc6-205">For Exchange items, you can include keywords.</span></span> <span data-ttu-id="05bc6-206">You can refine your query by using search operators like AND, OR, and NOT.</span><span class="sxs-lookup"><span data-stu-id="05bc6-206">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="05bc6-207">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="05bc6-207">For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="05bc6-208">最后，选择事件发生日期；此日期用作保留期的开始日期。</span><span class="sxs-lookup"><span data-stu-id="05bc6-208">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="05bc6-209">创建事件后，相应事件日期就会同步到所有具有相应事件类型的保留标签、资产 ID 和关键字的内容。</span><span class="sxs-lookup"><span data-stu-id="05bc6-209">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="05bc6-210">与任何保留标签一样，这种同步最长可能需要七天才能完成。</span><span class="sxs-lookup"><span data-stu-id="05bc6-210">Like any retention label, this synchronization can take up to seven days.</span></span>
  
![“事件设置”页](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

> [!NOTE]
> <span data-ttu-id="05bc6-212">创建事件后，保留设置将对已标记和索引的内容生效。</span><span class="sxs-lookup"><span data-stu-id="05bc6-212">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="05bc6-213">如果创建事件后将保留标签添加到新内容，则必须创建具有相同详细信息的新事件。</span><span class="sxs-lookup"><span data-stu-id="05bc6-213">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="05bc6-214">删除事件不会取消现在对内容生效的保留设置。</span><span class="sxs-lookup"><span data-stu-id="05bc6-214">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="05bc6-215">若要执行此操作，请创建具有相同详细信息的新事件，但将日期保留为空。</span><span class="sxs-lookup"><span data-stu-id="05bc6-215">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="05bc6-216">使用内容搜索来查找所有包含特定标签或资产 ID 的内容</span><span class="sxs-lookup"><span data-stu-id="05bc6-216">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="05bc6-217">在保留标签分配到内容后，可通过内容搜索，查找所有已使用特定保留标签进行分类或包含特定资产 ID 的内容：</span><span class="sxs-lookup"><span data-stu-id="05bc6-217">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="05bc6-218">若要查找所有包含特定保留标签的内容，请选择“**合规性标签**”条件，再输入完整或部分标签名称并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="05bc6-218">To find all content with a specific retention label, choose the **Compliance label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="05bc6-219">要查找所有包含特定资产 ID 的内容，请使用格式 `ComplianceAssetID:<value>`，输入 **ComplianceAssetID** 属性和值。</span><span class="sxs-lookup"><span data-stu-id="05bc6-219">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="05bc6-220">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-220">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="05bc6-221">权限</span><span class="sxs-lookup"><span data-stu-id="05bc6-221">Permissions</span></span>

<span data-ttu-id="05bc6-222">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span><span class="sxs-lookup"><span data-stu-id="05bc6-222">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="05bc6-223">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span><span class="sxs-lookup"><span data-stu-id="05bc6-223">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="05bc6-224">有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-224">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="05bc6-225">使用 PowerShell 自动触发事件</span><span class="sxs-lookup"><span data-stu-id="05bc6-225">Automate events by using PowerShell</span></span>

<span data-ttu-id="05bc6-226">Microsoft 365 合规性中心可用于手动创建事件，并且不支持在事件发生时自动触发事件。</span><span class="sxs-lookup"><span data-stu-id="05bc6-226">The Microsoft 365 compliance center lets you create events manually and doesn't support automatically triggering an event when it occurs.</span></span> <span data-ttu-id="05bc6-227">但是，可以使用 Rest API 自动触发事件。</span><span class="sxs-lookup"><span data-stu-id="05bc6-227">However, you can use a Rest API to trigger events automatically.</span></span> <span data-ttu-id="05bc6-228">有关详细信息，请参阅[自动执行基于事件的保留](automate-event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="05bc6-228">For more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="05bc6-229">此外，还可使用 PowerShell 脚本从业务应用程序中自动执行基于事件的保留。</span><span class="sxs-lookup"><span data-stu-id="05bc6-229">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="05bc6-230">适用于事件驱动保留的 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="05bc6-230">The PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="05bc6-231">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="05bc6-231">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="05bc6-232">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="05bc6-232">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="05bc6-233">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="05bc6-233">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="05bc6-234">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="05bc6-234">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="05bc6-235">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="05bc6-235">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="05bc6-236">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="05bc6-236">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

