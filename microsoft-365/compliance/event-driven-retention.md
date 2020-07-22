---
title: 从事件发生时开始计算保留期
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
ms.openlocfilehash: 5a04e97b341c66a78010e7255554be72aa073593
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199726"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="35a63-103">从事件发生时开始计算保留期</span><span class="sxs-lookup"><span data-stu-id="35a63-103">Start retention when an event occurs</span></span>

><span data-ttu-id="35a63-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="35a63-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="35a63-p101">如果你保留内容，保留期通常是以内容年限为依据。例如，可以先将文档自创建起保留 7 年，再删除它们。不过配置[保留标签](labels.md)时，还能让保留期以特定类型事件何时发生为依据。也就是说，事件触发开始计算保留期，并对所有包含针对相应事件类型应用的保留标签的内容强制执行标签的保留操作。</span><span class="sxs-lookup"><span data-stu-id="35a63-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="35a63-109">使用事件驱动保留的示例：</span><span class="sxs-lookup"><span data-stu-id="35a63-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="35a63-110">**员工离开组织**假设自员工离开组织之日起，必须将其记录保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="35a63-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="35a63-111">10 年过后，与该员工的雇用、绩效和离职相关的所有文档都需要进行处置。</span><span class="sxs-lookup"><span data-stu-id="35a63-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="35a63-112">员工离开组织便是触发 10 年保留期的事件。</span><span class="sxs-lookup"><span data-stu-id="35a63-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="35a63-113">**合同到期** 假设与合同相关的所有记录都需要在合同到期后保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="35a63-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="35a63-114">触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="35a63-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="35a63-p104">**产品生存期**：组织可能会对技术规范等内容规定与产品最后生产日期相关的保留要求。在这种情况下，触发保留期的事件是最后生产日期。</span><span class="sxs-lookup"><span data-stu-id="35a63-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="35a63-p105">事件驱动保留通常用于记录管理流程。也就是说：</span><span class="sxs-lookup"><span data-stu-id="35a63-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="35a63-119">基于事件的标签通常还可将内容分类为记录。</span><span class="sxs-lookup"><span data-stu-id="35a63-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="35a63-120">有关详细信息，请参阅[了解记录](records.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-120">For more information, see [Learn about records](records.md).</span></span>

- <span data-ttu-id="35a63-121">如果文档已归类为记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。</span><span class="sxs-lookup"><span data-stu-id="35a63-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="35a63-122">基于事件的保留标签通常在保留期末尾触发处置评审，因此记录管理人员可以手动评审并处置内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="35a63-123">有关详细信息，请参阅[内容的处置](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="35a63-124">基于事件的标签与 Microsoft 365 中的任何保留标签具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="35a63-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="35a63-125">有关详细信息，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="35a63-126">了解事件类型、标签、事件和资产 ID 之间的关系</span><span class="sxs-lookup"><span data-stu-id="35a63-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="35a63-127">为了成功使用事件驱动保留，请务必了解事件类型、保留标签、事件和资产 ID 之间的关系，如下图以及随后的说明所示：</span><span class="sxs-lookup"><span data-stu-id="35a63-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![事件类型、标签、事件和资产 ID 的关系图](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件类型、标签、事件和资产 ID 的关系图](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="35a63-130">为不同类型的内容创建保留标签，然后将其与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="35a63-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="35a63-131">例如，不同类型的产品文件和记录的保留标签与“产品生存期”事件类型相关联，因为必须将这些记录自产品生存期结束起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="35a63-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="35a63-132">用户（通常是记录管理人员）将这些保留标签应用于内容，并（对于 SharePoint 和 OneDrive 文档）为每一项输入资产 ID。</span><span class="sxs-lookup"><span data-stu-id="35a63-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="35a63-133">在此示例中，资产 ID 是组织使用的产品名称或代码。</span><span class="sxs-lookup"><span data-stu-id="35a63-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="35a63-134">因此，每个产品的记录都分配有一个保留标签，且每个记录都有包含资产 ID 的属性。</span><span class="sxs-lookup"><span data-stu-id="35a63-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="35a63-135">上图表示组织中所有产品记录的**全部内容**，且每一项都有记录所属产品的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="35a63-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="35a63-p111">事件类型是“产品生存期”，即事件是特定产品的生存期结束。当相应事件类型的事件（在本示例中，为产品生存期结束）发生时，创建指定以下信息的事件：</span><span class="sxs-lookup"><span data-stu-id="35a63-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="35a63-138">资产 ID（对于 SharePoint 和 OneDrive 文档）</span><span class="sxs-lookup"><span data-stu-id="35a63-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="35a63-p112">关键字（对于 Exchange 项）。在本示例中，组织在包含产品记录的邮件中使用产品代码，因此 Exchange 项的关键字与 SharePoint 和 OneDrive 文档的资产 ID 相同。</span><span class="sxs-lookup"><span data-stu-id="35a63-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="35a63-p113">事件发生日期。此日期用作保留期的开始日期。该日期可以是当前日期、过去日期或未来日期。</span><span class="sxs-lookup"><span data-stu-id="35a63-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="35a63-144">在你创建事件后，相应事件日期就会同步到符合以下条件的所有内容：具有相应事件类型的保留标签，且包含指定的资产 ID 或关键字。</span><span class="sxs-lookup"><span data-stu-id="35a63-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="35a63-145">与任何保留标签一样，这种同步最长可能需要 7 天才能完成。</span><span class="sxs-lookup"><span data-stu-id="35a63-145">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="35a63-146">在上图中，所有用红色圈起来的项的保留期都是由此事件触发的。</span><span class="sxs-lookup"><span data-stu-id="35a63-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="35a63-147">换言之，当此产品的生存期结束时，相应事件就会触发此产品的记录的保留期。</span><span class="sxs-lookup"><span data-stu-id="35a63-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="35a63-148">请务必注意，如果没有为事件指定资产 ID 或关键字，则具有该事件类型标签的**所有内容**均由该事件触发保留期。</span><span class="sxs-lookup"><span data-stu-id="35a63-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="35a63-149">也就是说，在上图中，所有内容将开始被保留。</span><span class="sxs-lookup"><span data-stu-id="35a63-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="35a63-150">这可能并非如你所愿。</span><span class="sxs-lookup"><span data-stu-id="35a63-150">This might not be what you intend.</span></span> 
  
<span data-ttu-id="35a63-151">最后，请注意，每个保留标签都有自己的保留设置。</span><span class="sxs-lookup"><span data-stu-id="35a63-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="35a63-152">在此示例中，它们全都指定保留 10 年，但事件也可触发保留期不同的各个保留标签。</span><span class="sxs-lookup"><span data-stu-id="35a63-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="35a63-153">如何设置事件驱动保留</span><span class="sxs-lookup"><span data-stu-id="35a63-153">How to set up event-driven retention</span></span>

<span data-ttu-id="35a63-154">事件驱动保留的工作流概览：</span><span class="sxs-lookup"><span data-stu-id="35a63-154">High-level workflow for event-driven retention:</span></span>
  
![事件驱动保留的设置工作流的关系图](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="35a63-156">有关使用 SharePont 中的托管属性来自动应用保留标签并实施事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="35a63-157">第 1 步：创建保留期以事件为依据的标签</span><span class="sxs-lookup"><span data-stu-id="35a63-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="35a63-158">要创建和配置保留标签，请按照[创建和配置保留标签](create-retention-labels.md#create-and-configure-retention-labels)中的说明进行操作，并在打开保留功能时，根据事件选择保留或删除内容的选项。</span><span class="sxs-lookup"><span data-stu-id="35a63-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="35a63-159">此设置意味着，保留设置暂不会生效，直到在步骤 5 中在“**事件**”页面上创建事件之后。</span><span class="sxs-lookup"><span data-stu-id="35a63-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="35a63-160">事件驱动的保留通常用于归类为记录的内容，因此这是检查是否还需要选择将内容标记为记录的选项的好时机。</span><span class="sxs-lookup"><span data-stu-id="35a63-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="35a63-161">事件驱动保留要求保留设置：</span><span class="sxs-lookup"><span data-stu-id="35a63-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="35a63-162">保留内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-162">Retain the content.</span></span>
    
- <span data-ttu-id="35a63-163">在保留期到期时自动删除内容或触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="35a63-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![让标签基于事件的选项](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="35a63-165">第 2 步：选择与此标签关联的事件类型</span><span class="sxs-lookup"><span data-stu-id="35a63-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="35a63-166">在标签设置中，选择将标签基于**事件**的选项后，将看到“**选择事件类型**”选项。</span><span class="sxs-lookup"><span data-stu-id="35a63-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="35a63-167">事件类型就是对要将标签与之相关联的事件的一般说明。</span><span class="sxs-lookup"><span data-stu-id="35a63-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="35a63-168">例如，如果创建“产品生存期”事件类型，将创建基于事件的保留标签，标签名称描述了要将标签应用于什么类型的内容（如“产品开发文件”或“产品业务决策记录”）。</span><span class="sxs-lookup"><span data-stu-id="35a63-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="35a63-169">选择一种内置事件类型，或自行创建一种类型并选中。</span><span class="sxs-lookup"><span data-stu-id="35a63-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="35a63-170">选择事件类型并保存保留标签后，便无法再更改事件类型。</span><span class="sxs-lookup"><span data-stu-id="35a63-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![用于创建或选择事件类型的选项](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="35a63-172">第 3 步：发布或自动应用基于事件的保留标签</span><span class="sxs-lookup"><span data-stu-id="35a63-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="35a63-173">与任何保留标签一样，需要发布或自动应用基于事件的标签，以便将它手动或自动应用于内容：</span><span class="sxs-lookup"><span data-stu-id="35a63-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="35a63-174">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="35a63-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="35a63-175">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="35a63-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="35a63-176">如果从“**记录管理**” > “**文件计划**”选项卡或“**数据管理**” > “**标签**”选项卡中选择基于事件的保留标签，“**自动应用标签**”按钮将不可用。</span><span class="sxs-lookup"><span data-stu-id="35a63-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="35a63-177">请使用以下位置之一的标签或策略列表上方的“**自动应用标签**”选项来代替此按钮：</span><span class="sxs-lookup"><span data-stu-id="35a63-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="35a63-178">“**记录管理**” > “**标签策略**”选项卡</span><span class="sxs-lookup"><span data-stu-id="35a63-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="35a63-179">“**数据管理**” > “**标签**”选项卡或“**标签策略**”选项卡</span><span class="sxs-lookup"><span data-stu-id="35a63-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![用于发布或自动应用保留标签的选项](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="35a63-181">第 4 步：输入资产 ID</span><span class="sxs-lookup"><span data-stu-id="35a63-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="35a63-182">将基于事件的标签应用于内容后，可为每一项输入资产 ID。</span><span class="sxs-lookup"><span data-stu-id="35a63-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="35a63-183">例如，组织可能使用：</span><span class="sxs-lookup"><span data-stu-id="35a63-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="35a63-184">产品代码：可用于仅保留特定产品的内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="35a63-185">项目代码：可用于仅保留特定项目的内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="35a63-186">员工 ID：可用于仅保留特定人员的内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="35a63-187">资产 ID 只是 SharePoint 和 OneDrive 中提供的另一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="35a63-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="35a63-188">你的组织可能已经使用其他文档属性和 ID 来分类内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="35a63-189">如果是这样，还可以在创建事件时使用这些属性和值（请参见后面的第 6 步）。</span><span class="sxs-lookup"><span data-stu-id="35a63-189">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="35a63-190">请务必注意，必须在文档属性中使用某种*属性:值*组合，将相应项与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="35a63-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![用于输入资产 ID 的文本框](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="35a63-192">第 5 步：创建事件</span><span class="sxs-lookup"><span data-stu-id="35a63-192">Step 5: Create an event</span></span>

<span data-ttu-id="35a63-193">当相应事件类型的特定实例（例如，产品的生存期结束）发生时，请转到 Microsoft 365 合规中心内的“**记录管理**” > “**事件**”页，并创建事件。</span><span class="sxs-lookup"><span data-stu-id="35a63-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="35a63-194">可通过创建事件来手动触发事件。</span><span class="sxs-lookup"><span data-stu-id="35a63-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="35a63-195">第 6 步：选择第 2 步中标签使用的相同事件类型</span><span class="sxs-lookup"><span data-stu-id="35a63-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="35a63-196">创建事件时，请选择第 2 步中的保留标签所使用的相同事件类型，如“产品生存期”。</span><span class="sxs-lookup"><span data-stu-id="35a63-196">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="35a63-197">只有具有相应事件类型的保留标签的内容，才会触发保留期。</span><span class="sxs-lookup"><span data-stu-id="35a63-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![“事件设置”中用于选择事件类型的选项](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="35a63-199">第 7 步：输入关键字或资产 ID</span><span class="sxs-lookup"><span data-stu-id="35a63-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="35a63-200">现在通过指定 SharePoint 和 OneDrive 内容的资产 ID 或指定 Exchange 内容的关键字，缩小内容的范围。</span><span class="sxs-lookup"><span data-stu-id="35a63-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="35a63-201">对于资产 ID，仅具有指定*属性:值*对的内容才会执行保留。</span><span class="sxs-lookup"><span data-stu-id="35a63-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="35a63-202">如果未输入资产 ID，具有该事件类型标签的所有内容都将应用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="35a63-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="35a63-203">例如：如果使用的是资产 ID 属性，请在下方所示的资产 ID 框中输入 `ComplianceAssetID:<value>`。</span><span class="sxs-lookup"><span data-stu-id="35a63-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="35a63-204">组织可能已经对与此事件类型相关的文档应用了其他属性和 ID。</span><span class="sxs-lookup"><span data-stu-id="35a63-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="35a63-205">例如，如果需要检测特定产品记录，ID 可能为自定义属性 ProductID 和值“XYZ”的组合。</span><span class="sxs-lookup"><span data-stu-id="35a63-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="35a63-206">在此情况下，需在下图所示的资产 ID 框中输入 `ProductID:XYZ`。</span><span class="sxs-lookup"><span data-stu-id="35a63-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="35a63-207">对于 Exchange 项目，请使用关键字。</span><span class="sxs-lookup"><span data-stu-id="35a63-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="35a63-208">你可以通过使用 AND、OR 和 NOT 等搜索运算符来使用查询。</span><span class="sxs-lookup"><span data-stu-id="35a63-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="35a63-209">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="35a63-210">最后，选择事件发生日期；此日期用作保留期的开始日期。</span><span class="sxs-lookup"><span data-stu-id="35a63-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="35a63-211">创建事件后，相应事件日期就会同步到所有具有相应事件类型的保留标签、资产 ID 和关键字的内容。</span><span class="sxs-lookup"><span data-stu-id="35a63-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="35a63-212">与任何保留标签一样，这种同步最长可能需要七天才能完成。</span><span class="sxs-lookup"><span data-stu-id="35a63-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![“事件设置”页](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="35a63-214">创建事件后，保留设置将对已标记和索引的内容生效。</span><span class="sxs-lookup"><span data-stu-id="35a63-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="35a63-215">如果创建事件后将保留标签添加到新内容，则必须创建具有相同详细信息的新事件。</span><span class="sxs-lookup"><span data-stu-id="35a63-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="35a63-216">删除事件不会取消现在对内容生效的保留设置。</span><span class="sxs-lookup"><span data-stu-id="35a63-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="35a63-217">若要执行此操作，请创建具有相同详细信息的新事件，但将日期保留为空。</span><span class="sxs-lookup"><span data-stu-id="35a63-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="35a63-218">使用内容搜索来查找所有包含特定标签或资产 ID 的内容</span><span class="sxs-lookup"><span data-stu-id="35a63-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="35a63-219">在保留标签分配到内容后，可通过内容搜索，查找所有已使用特定保留标签进行分类或包含特定资产 ID 的内容：</span><span class="sxs-lookup"><span data-stu-id="35a63-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="35a63-220">若要查找所有包含特定保留标签的内容，请选择“**保留标签**”条件，再输入完整或部分标签名称并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="35a63-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="35a63-221">要查找所有包含特定资产 ID 的内容，请使用格式 `ComplianceAssetID:<value>`，输入 **ComplianceAssetID** 属性和值。</span><span class="sxs-lookup"><span data-stu-id="35a63-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="35a63-222">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="35a63-223">权限</span><span class="sxs-lookup"><span data-stu-id="35a63-223">Permissions</span></span>

<span data-ttu-id="35a63-p129">评审者必须是包含 **“处置管理”** 角色和 **“仅供查看审核日志”** 角色的角色组的成员，才能获取对“事件”\*\*\*\* 页的访问权限。建议新建“处置评审者”角色组，向此角色组添加这两个角色，再将成员添加到角色组中。</span><span class="sxs-lookup"><span data-stu-id="35a63-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="35a63-226">有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="35a63-227">使用 PowerShell 自动触发事件</span><span class="sxs-lookup"><span data-stu-id="35a63-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="35a63-228">Microsoft 365 合规性中心可用于手动创建事件，并且不支持在事件发生时自动触发事件。</span><span class="sxs-lookup"><span data-stu-id="35a63-228">The Microsoft 365 compliance center lets you create events manually and doesn't support automatically triggering an event when it occurs.</span></span> <span data-ttu-id="35a63-229">但是，可以使用 Rest API 自动触发事件。</span><span class="sxs-lookup"><span data-stu-id="35a63-229">However, you can use a Rest API to trigger events automatically.</span></span> <span data-ttu-id="35a63-230">有关详细信息，请参阅[自动执行基于事件的保留](automate-event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="35a63-230">For more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="35a63-231">此外，还可使用 PowerShell 脚本从业务应用程序中自动执行基于事件的保留。</span><span class="sxs-lookup"><span data-stu-id="35a63-231">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="35a63-232">适用于基于事件的保留的 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="35a63-232">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="35a63-233">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="35a63-233">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="35a63-234">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="35a63-234">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="35a63-235">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="35a63-235">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="35a63-236">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="35a63-236">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="35a63-237">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="35a63-237">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="35a63-238">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="35a63-238">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

