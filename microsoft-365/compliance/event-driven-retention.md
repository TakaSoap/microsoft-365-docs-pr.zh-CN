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
ms.openlocfilehash: 49fe330fa6844361a77caaebb0e6a411297ee643
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907012"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="d04a6-103">从事件发生时开始计算保留期</span><span class="sxs-lookup"><span data-stu-id="d04a6-103">Start retention when an event occurs</span></span>

><span data-ttu-id="d04a6-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="d04a6-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="d04a6-p101">如果你保留内容，保留期通常是以内容年限为依据。例如，可以先将文档自创建起保留 7 年，再删除它们。不过配置[保留标签](retention.md#retention-labels)时，还能让保留期以特定类型事件何时发生为依据。也就是说，事件触发开始计算保留期，并对所有包含针对相应事件类型应用的保留标签的内容强制执行标签的保留操作。</span><span class="sxs-lookup"><span data-stu-id="d04a6-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="d04a6-109">使用基于事件的保留的示例：</span><span class="sxs-lookup"><span data-stu-id="d04a6-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="d04a6-110">**员工离开组织** 假设自员工离开组织之日起，必须将其记录保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="d04a6-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="d04a6-111">10 年过后，与该员工的雇用、绩效和离职相关的所有文档都需要进行处置。</span><span class="sxs-lookup"><span data-stu-id="d04a6-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="d04a6-112">员工离开组织便是触发 10 年保留期的事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="d04a6-113">**合同到期** 假设与合同相关的所有记录都需要在合同到期后保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="d04a6-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="d04a6-114">触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="d04a6-p104">**产品生存期**：组织可能会对技术规范等内容规定与产品最后生产日期相关的保留要求。在这种情况下，触发保留期的事件是最后生产日期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="d04a6-p105">基于事件的保留通常用于记录管理流程。也就是说：</span><span class="sxs-lookup"><span data-stu-id="d04a6-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="d04a6-119">作为记录管理解决方案的一部分，基于事件的保留标签通常还会将项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="d04a6-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="d04a6-120">有关详细信息，请参阅[了解记录管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="d04a6-121">如果文档已被声明成记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。</span><span class="sxs-lookup"><span data-stu-id="d04a6-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="d04a6-122">基于事件的保留标签通常在保留期末尾触发处置评审，因此记录管理人员可以手动评审并处置内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="d04a6-123">有关详细信息，请参阅[内容的处置](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="d04a6-124">基于事件的保留标签与 Microsoft 365 中的任何保留标签具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="d04a6-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="d04a6-125">有关详细信息，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="d04a6-126">了解事件类型、标签、事件和资产 ID 之间的关系</span><span class="sxs-lookup"><span data-stu-id="d04a6-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="d04a6-127">为了成功使用基于事件的保留，请务必了解事件类型、保留标签、事件和资产 ID 之间的关系，如下图以及随后的说明所示：</span><span class="sxs-lookup"><span data-stu-id="d04a6-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![图 1 （共 2 张图）：事件类型、标签、事件和资产 ID 的关系图](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![图 2 （共 2 张图）：事件类型、标签、事件和资产 ID 的关系图](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="d04a6-130">为不同类型的内容创建保留标签，然后将其与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="d04a6-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="d04a6-131">例如，不同类型的产品文件和记录的保留标签与“产品生存期”事件类型相关联，因为必须将这些记录自产品生存期结束起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="d04a6-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="d04a6-132">用户（通常是记录管理人员）将这些保留标签应用于内容，并（对 SharePoint 和 OneDrive 中的文档）为每一项输入资产 ID。</span><span class="sxs-lookup"><span data-stu-id="d04a6-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="d04a6-133">在此示例中，资产 ID 是组织使用的产品名称或代码。</span><span class="sxs-lookup"><span data-stu-id="d04a6-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="d04a6-134">然后，每个产品的记录都分配有一个保留标签，且每个记录都有包含资产 ID 的属性。</span><span class="sxs-lookup"><span data-stu-id="d04a6-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="d04a6-135">上图表示组织中所有产品记录的 **全部内容**，且每一项都有记录所属产品的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="d04a6-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="d04a6-p111">事件类型是“产品生存期”，即事件是特定产品的生存期结束。当相应事件类型的事件（在本示例中，为产品生存期结束）发生时，创建指定以下信息的事件：</span><span class="sxs-lookup"><span data-stu-id="d04a6-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="d04a6-138">资产 ID（对于 SharePoint 和 OneDrive 文档）</span><span class="sxs-lookup"><span data-stu-id="d04a6-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="d04a6-p112">关键字（对于 Exchange 项）。在本示例中，组织在包含产品记录的邮件中使用产品代码，因此 Exchange 项的关键字与 SharePoint 和 OneDrive 文档的资产 ID 在功能上来说是相同的。</span><span class="sxs-lookup"><span data-stu-id="d04a6-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="d04a6-p113">事件发生日期。此日期用作保留期的开始日期。该日期可以是当前日期、过去日期或未来日期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="d04a6-144">在你创建事件后，相应事件日期就会同步到符合以下条件的所有内容：具有相应事件类型的保留标签，且包含指定的资产 ID 或关键字。</span><span class="sxs-lookup"><span data-stu-id="d04a6-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="d04a6-145">与任何保留标签一样，这种同步最长可能需要七天才能完成。</span><span class="sxs-lookup"><span data-stu-id="d04a6-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="d04a6-146">在上图中，所有用红色圈起来的项的保留期都是由此事件触发的。</span><span class="sxs-lookup"><span data-stu-id="d04a6-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="d04a6-147">换言之，当此产品的生存期结束时，相应事件就会触发此产品的记录的保留期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="d04a6-148">请务必注意，如果你没有为事件指定资产 ID 或关键字，那么对于具有相应事件类型的保留标签的 **所有内容**，保留期都是由事件触发的。</span><span class="sxs-lookup"><span data-stu-id="d04a6-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="d04a6-149">也就是说，在上图中，所有内容将开始被保留。</span><span class="sxs-lookup"><span data-stu-id="d04a6-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="d04a6-150">这可能并非如你所愿。</span><span class="sxs-lookup"><span data-stu-id="d04a6-150">This might not be what you intend.</span></span>

<span data-ttu-id="d04a6-151">最后，请注意，每个保留标签都有自己的保留设置。</span><span class="sxs-lookup"><span data-stu-id="d04a6-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="d04a6-152">在此示例中，它们全都指定保留 10 年，但事件也可触发保留期不同的各个保留标签。</span><span class="sxs-lookup"><span data-stu-id="d04a6-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="d04a6-153">如何设置事件驱动保留</span><span class="sxs-lookup"><span data-stu-id="d04a6-153">How to set up event-driven retention</span></span>

<span data-ttu-id="d04a6-154">事件驱动保留的工作流概览：</span><span class="sxs-lookup"><span data-stu-id="d04a6-154">High-level workflow for event-driven retention:</span></span>
  
![事件驱动保留的设置工作流的关系图](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="d04a6-156">有关使用 SharePont 中的托管属性来自动应用保留标签并实现事件驱动保留的详细方案，请参阅[使用保留标签管理 SharePoint 中存储的文档的生命周期](auto-apply-retention-labels-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="d04a6-157">第 1 步：创建保留期以事件为依据的标签</span><span class="sxs-lookup"><span data-stu-id="d04a6-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="d04a6-158">若要创建和配置保留标签，请使用“[创建和配置保留标签](./create-apply-retention-labels.md#create-and-configure-retention-labels)”中的说明。</span><span class="sxs-lookup"><span data-stu-id="d04a6-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](./create-apply-retention-labels.md#create-and-configure-retention-labels).</span></span> <span data-ttu-id="d04a6-159">但是特定于基于事件的保留，在“创建保留标签向导”的“**定义保留设置**”页面上，在“**启动保留期，基于：**”后，从下拉列表中选择一个默认事件类型，或选择“**创建新事件类型**”来自行创建：</span><span class="sxs-lookup"><span data-stu-id="d04a6-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![为保留标签创建新事件类型](../media/SPRetention6.png)

<span data-ttu-id="d04a6-161">事件类型就是对要将标签与之相关联的事件的一般说明。</span><span class="sxs-lookup"><span data-stu-id="d04a6-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="d04a6-162">在下拉列表中的名称后面，默认事件类型都会有 **（事件类型）**，以便更轻松地标识，你还可以从“**记录管理**” > “**事件**”选项卡 > “**管理事件类型**” 那里查看和创建事件类型。</span><span class="sxs-lookup"><span data-stu-id="d04a6-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="d04a6-163">基于事件的保留要求保留设置：</span><span class="sxs-lookup"><span data-stu-id="d04a6-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="d04a6-164">保留内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-164">Retain the content.</span></span>
    
- <span data-ttu-id="d04a6-165">在保留期到期时自动删除内容或触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="d04a6-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="d04a6-166">基于事件的保留通常用于声明为记录的内容，因此这是检查是否还需要选择将内容标记为[记录](records-management.md#records)的选项的好时机。</span><span class="sxs-lookup"><span data-stu-id="d04a6-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="d04a6-167">如果你使用的是现有事件类型，而不是创建新的事件类型，请跳到第 3 步。</span><span class="sxs-lookup"><span data-stu-id="d04a6-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="d04a6-168">选择事件类型并保存保留标签后，便无法再更改事件类型。</span><span class="sxs-lookup"><span data-stu-id="d04a6-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="d04a6-169">第 2 步：为标签创建新事件类型</span><span class="sxs-lookup"><span data-stu-id="d04a6-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="d04a6-170">对于保留设置，如果已选择“**创建新事件类型**”，那就输入事件类型的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="d04a6-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="d04a6-171">然后选择 “**下一步**”、“**提交**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d04a6-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="d04a6-172">返回到“**定义保留设置**”页面， 针对“**启动保留期，基于：**”一项，请使用下拉列表选择所创建的事件类型。</span><span class="sxs-lookup"><span data-stu-id="d04a6-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="d04a6-173">第 3 步：发布或自动应用基于事件的保留标签</span><span class="sxs-lookup"><span data-stu-id="d04a6-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="d04a6-174">与任何保留标签一样，需要发布或自动应用基于事件的标签，以便将它手动或自动应用于内容：</span><span class="sxs-lookup"><span data-stu-id="d04a6-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="d04a6-175">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="d04a6-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="d04a6-176">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="d04a6-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="d04a6-177">第 4 步：输入资产 ID</span><span class="sxs-lookup"><span data-stu-id="d04a6-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="d04a6-178">将基于事件的标签应用于内容后，可为每一项输入资产 ID。</span><span class="sxs-lookup"><span data-stu-id="d04a6-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="d04a6-179">例如，组织可能使用：</span><span class="sxs-lookup"><span data-stu-id="d04a6-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="d04a6-180">产品代码：可用于仅保留特定产品的内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="d04a6-181">项目代码：可用于仅保留特定项目的内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="d04a6-182">员工 ID：可用于仅保留特定人员的内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="d04a6-183">资产 ID 只是 SharePoint 和 OneDrive 中提供的另一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="d04a6-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="d04a6-184">你的组织可能已经使用其他文档属性和 ID 来分类内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="d04a6-185">如果是这样，还可以在创建事件时使用这些属性和值（请参见后面的第 6 步）。</span><span class="sxs-lookup"><span data-stu-id="d04a6-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="d04a6-186">请务必注意，必须在文档属性中使用某种 *属性:值* 组合，将相应项与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="d04a6-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![用于输入资产 ID 的文本框](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="d04a6-188">第 5 步：创建事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-188">Step 5: Create an event</span></span>

<span data-ttu-id="d04a6-189">当相应事件类型的特定实例（例如，产品的生存期结束）发生时，请转到 Microsoft 365 合规中心内的“**记录管理**” > “**事件**”页，并选择 “**+ 创建**”来创建事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="d04a6-190">可通过创建事件来手动触发事件，就在这里。</span><span class="sxs-lookup"><span data-stu-id="d04a6-190">You trigger the event by creating it, here.</span></span>

![创建事件以便为基于事件的保留标签启动保留](../media/create-event-records-management.png)

<span data-ttu-id="d04a6-192">每个租户支持多达一百万个事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="d04a6-193">第 6 步：选择第 2 步中标签使用的相同事件类型</span><span class="sxs-lookup"><span data-stu-id="d04a6-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="d04a6-194">创建事件时，请选择第 2 步中的保留标签设置所指定的相同事件类型。</span><span class="sxs-lookup"><span data-stu-id="d04a6-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="d04a6-195">例如，如果你选择了“**产品生命周期**”作为标签设置的事件类型，请在创建事件时选择“**产品生命周期**”。</span><span class="sxs-lookup"><span data-stu-id="d04a6-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="d04a6-196">只有具有相应事件类型的保留标签的内容，才会触发保留期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![“事件设置”中用于选择事件类型的选项](../media/choose-event-type-records-management.png)

<span data-ttu-id="d04a6-198">或者，如果需要为具有不同事件类型的多个保留标签创建事件，请选择“**选择现有标签**”选项。</span><span class="sxs-lookup"><span data-stu-id="d04a6-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="d04a6-199">然后，选择想要与此事件相关联的事件类型所配置的标签。</span><span class="sxs-lookup"><span data-stu-id="d04a6-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="d04a6-200">第 7 步：输入关键字或资产 ID</span><span class="sxs-lookup"><span data-stu-id="d04a6-200">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="d04a6-201">现在通过指定 SharePoint 和 OneDrive 内容的资产 ID 或指定 Exchange 内容的关键字，缩小内容的范围。</span><span class="sxs-lookup"><span data-stu-id="d04a6-201">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="d04a6-202">对于资产 ID，仅具有指定 *属性:值* 对的内容才会执行保留。</span><span class="sxs-lookup"><span data-stu-id="d04a6-202">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="d04a6-203">如果未输入资产 ID，具有该事件类型标签的所有内容都将应用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-203">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="d04a6-204">例如：如果使用的是资产 ID 属性，请在下方所示的资产 ID 框中输入 `ComplianceAssetID:<value>`。</span><span class="sxs-lookup"><span data-stu-id="d04a6-204">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="d04a6-205">组织可能已经对与此事件类型相关的文档应用了其他属性和 ID。</span><span class="sxs-lookup"><span data-stu-id="d04a6-205">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="d04a6-206">例如，如果需要检测特定产品记录，ID 可能为自定义属性 ProductID 和值“XYZ”的组合。</span><span class="sxs-lookup"><span data-stu-id="d04a6-206">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="d04a6-207">在此情况下，需在下图所示的资产 ID 框中输入 `ProductID:XYZ`。</span><span class="sxs-lookup"><span data-stu-id="d04a6-207">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="d04a6-208">对于 Exchange 项目，请使用关键字。</span><span class="sxs-lookup"><span data-stu-id="d04a6-208">For Exchange items, use keywords.</span></span> <span data-ttu-id="d04a6-209">你可以通过使用 AND、OR 和 NOT 等搜索运算符来使用查询。</span><span class="sxs-lookup"><span data-stu-id="d04a6-209">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="d04a6-210">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-210">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="d04a6-211">最后，选择事件发生日期；此日期用作保留期的开始日期。</span><span class="sxs-lookup"><span data-stu-id="d04a6-211">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="d04a6-212">创建事件后，相应事件日期就会同步到所有具有相应事件类型的保留标签、资产 ID 和关键字的内容。</span><span class="sxs-lookup"><span data-stu-id="d04a6-212">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="d04a6-213">与任何保留标签一样，这种同步最长可能需要七天才能完成。</span><span class="sxs-lookup"><span data-stu-id="d04a6-213">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![“事件设置”页](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="d04a6-215">创建事件后，保留设置将对已标记和索引的内容生效。</span><span class="sxs-lookup"><span data-stu-id="d04a6-215">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="d04a6-216">如果创建事件后将保留标签添加到新内容，则必须创建具有相同详细信息的新事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-216">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="d04a6-217">删除事件不会取消现在对内容生效的保留设置。</span><span class="sxs-lookup"><span data-stu-id="d04a6-217">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="d04a6-218">若要执行此操作，请创建具有相同详细信息的新事件，但将日期保留为空。</span><span class="sxs-lookup"><span data-stu-id="d04a6-218">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="d04a6-219">使用内容搜索来查找所有包含特定标签或资产 ID 的内容</span><span class="sxs-lookup"><span data-stu-id="d04a6-219">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="d04a6-220">在保留标签分配到内容后，可通过内容搜索，查找所有已使用特定保留标签进行分类或包含特定资产 ID 的内容：</span><span class="sxs-lookup"><span data-stu-id="d04a6-220">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="d04a6-221">若要查找所有包含特定保留标签的内容，请选择“**保留标签**”条件，再输入完整或部分标签名称并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="d04a6-221">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="d04a6-222">要查找所有包含特定资产 ID 的内容，请使用格式 `ComplianceAssetID:<value>`，输入 **ComplianceAssetID** 属性和值。</span><span class="sxs-lookup"><span data-stu-id="d04a6-222">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="d04a6-223">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-223">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="d04a6-224">使用 PowerShell 自动触发事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="d04a6-225">可以使用 PowerShell 脚本从业务应用程序中自动执行基于事件的保留。</span><span class="sxs-lookup"><span data-stu-id="d04a6-225">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="d04a6-226">适用于基于事件的保留的 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d04a6-226">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="d04a6-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="d04a6-227">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="d04a6-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="d04a6-228">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="d04a6-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="d04a6-229">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="d04a6-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="d04a6-230">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="d04a6-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="d04a6-231">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="d04a6-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="d04a6-232">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="d04a6-233">使用 REST API 自动触发事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-233">Automate events by using a REST API</span></span>

<span data-ttu-id="d04a6-234">可使用 REST API 自动创建用于触发保留期开始的事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-234">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="d04a6-235">REST API 是一个支持多组 HTTP 操作（方法）的服务终结点，提供对服务资源的创建/检索/更新/删除操作权限。</span><span class="sxs-lookup"><span data-stu-id="d04a6-235">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="d04a6-236">有关详细信息，请参阅 [REST API 请求/响应组件](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-236">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="d04a6-237">通过使用 Microsoft 365 REST API，可以使用 POST 和 GET 方法来创建和检索事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-237">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="d04a6-238">使用 REST API 有两种选择：</span><span class="sxs-lookup"><span data-stu-id="d04a6-238">There are two options for using the REST API:</span></span>

- <span data-ttu-id="d04a6-239">**Microsoft Power Automate 或类似的应用程序**，可用于自动触发事件的发生。</span><span class="sxs-lookup"><span data-stu-id="d04a6-239">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="d04a6-240">Microsoft Power Automate 是一种用于连接其他系统的协调程序，你无需编写自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="d04a6-240">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="d04a6-241">有关详细信息，请参阅 [Power Automate 网站](https://flow.microsoft.com/zh-CN/)。</span><span class="sxs-lookup"><span data-stu-id="d04a6-241">For more information, see the [Power Automate website](https://flow.microsoft.com/zh-CN/).</span></span>

- <span data-ttu-id="d04a6-242">**通过 PowerShell 或 HTTP 客户端调用 REST API**，可使用 PowerShell（版本 6 或更高版本）创建事件，它是自定义解决方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="d04a6-242">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="d04a6-243">在使用 REST API 之前，请以全局管理员身份，确认要用于保留事件调用的 URL。</span><span class="sxs-lookup"><span data-stu-id="d04a6-243">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="d04a6-244">为此，请使用 REST API URL 运行 GET 保留事件调用：</span><span class="sxs-lookup"><span data-stu-id="d04a6-244">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="d04a6-245">检查响应代码。</span><span class="sxs-lookup"><span data-stu-id="d04a6-245">Check the response code.</span></span> <span data-ttu-id="d04a6-246">如果是 302，则从响应标头的 Location 属性获取重定向 URL，并使用该 URL，而不是随后说明中的 `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`。</span><span class="sxs-lookup"><span data-stu-id="d04a6-246">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="d04a6-247">通过在 Microsoft 365 合规中心 >“**记录管理**” >  “**事件**”中进行查看，确认自动创建的事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-247">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="d04a6-248">使用 Microsoft Power Automate 创建事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-248">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="d04a6-249">使用 Microsoft 365 REST API 创建用于创建事件的流：</span><span class="sxs-lookup"><span data-stu-id="d04a6-249">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![使用流创建事件](../media/automate-event-driven-retention-flow-1.png)

![使用流调用 REST API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="d04a6-252">创建事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-252">Create an event</span></span>

<span data-ttu-id="d04a6-253">用于调用 REST API 的示例代码：</span><span class="sxs-lookup"><span data-stu-id="d04a6-253">Sample code to call the REST API:</span></span>

- <span data-ttu-id="d04a6-254">**方法**：POST</span><span class="sxs-lookup"><span data-stu-id="d04a6-254">**Method**: POST</span></span>
- <span data-ttu-id="d04a6-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="d04a6-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="d04a6-256">**标头**：键 = Content-Type，值 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d04a6-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="d04a6-257">**正文**：</span><span class="sxs-lookup"><span data-stu-id="d04a6-257">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="d04a6-258">**身份验证**: 基本</span><span class="sxs-lookup"><span data-stu-id="d04a6-258">**Authentication**: Basic</span></span>
- <span data-ttu-id="d04a6-259">**用户名**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d04a6-259">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="d04a6-260">**密码**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d04a6-260">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="d04a6-261">可用参数</span><span class="sxs-lookup"><span data-stu-id="d04a6-261">Available parameters</span></span>


|<span data-ttu-id="d04a6-262">参数</span><span class="sxs-lookup"><span data-stu-id="d04a6-262">Parameters</span></span>|<span data-ttu-id="d04a6-263">说明</span><span class="sxs-lookup"><span data-stu-id="d04a6-263">Description</span></span>|<span data-ttu-id="d04a6-264">注释</span><span class="sxs-lookup"><span data-stu-id="d04a6-264">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="d04a6-265"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="d04a6-265"><d:Name></d:Name></span></span>|<span data-ttu-id="d04a6-266">为事件提供唯一的名称，</span><span class="sxs-lookup"><span data-stu-id="d04a6-266">Provide a unique name for the event,</span></span>|<span data-ttu-id="d04a6-267">不能包含尾随空格或以下字符：% \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="d04a6-267">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="d04a6-268">, : ;</span><span class="sxs-lookup"><span data-stu-id="d04a6-268">, : ;</span></span>|
|<span data-ttu-id="d04a6-269"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="d04a6-269"><d:EventType></d:EventType></span></span>|<span data-ttu-id="d04a6-270">输入事件类型名称（或 Guid），</span><span class="sxs-lookup"><span data-stu-id="d04a6-270">Enter event type name (or Guid),</span></span>|<span data-ttu-id="d04a6-271">示例：“雇佣终止”。</span><span class="sxs-lookup"><span data-stu-id="d04a6-271">Example: "Employee termination".</span></span> <span data-ttu-id="d04a6-272">事件类型必须与保留标签相关联。</span><span class="sxs-lookup"><span data-stu-id="d04a6-272">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="d04a6-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="d04a6-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="d04a6-274">输入“ComplianceAssetId:” + 员工 ID</span><span class="sxs-lookup"><span data-stu-id="d04a6-274">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="d04a6-275">示例："ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="d04a6-275">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="d04a6-276"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="d04a6-276"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="d04a6-277">事件日期和时间</span><span class="sxs-lookup"><span data-stu-id="d04a6-277">Event Date and Time</span></span>|<span data-ttu-id="d04a6-278">格式：yyyy-MM-ddTHH:mm:ssZ，示例：2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="d04a6-278">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="d04a6-279">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-279">Response codes</span></span>

| <span data-ttu-id="d04a6-280">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-280">Response Code</span></span> | <span data-ttu-id="d04a6-281">说明</span><span class="sxs-lookup"><span data-stu-id="d04a6-281">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="d04a6-282">302</span><span class="sxs-lookup"><span data-stu-id="d04a6-282">302</span></span>               | <span data-ttu-id="d04a6-283">重定向</span><span class="sxs-lookup"><span data-stu-id="d04a6-283">Redirect</span></span>              |
| <span data-ttu-id="d04a6-284">201</span><span class="sxs-lookup"><span data-stu-id="d04a6-284">201</span></span>               | <span data-ttu-id="d04a6-285">已创建</span><span class="sxs-lookup"><span data-stu-id="d04a6-285">Created</span></span>               |
| <span data-ttu-id="d04a6-286">403</span><span class="sxs-lookup"><span data-stu-id="d04a6-286">403</span></span>               | <span data-ttu-id="d04a6-287">授权失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-287">Authorization Failed</span></span>  |
| <span data-ttu-id="d04a6-288">401</span><span class="sxs-lookup"><span data-stu-id="d04a6-288">401</span></span>               | <span data-ttu-id="d04a6-289">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-289">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="d04a6-290">根据时间范围获取事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-290">Get events based on a time range</span></span>

- <span data-ttu-id="d04a6-291">**方法**: GET</span><span class="sxs-lookup"><span data-stu-id="d04a6-291">**Method**: GET</span></span>

- <span data-ttu-id="d04a6-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="d04a6-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="d04a6-293">**标头**：键 = Content-Type，值 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d04a6-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="d04a6-294">**身份验证**: 基本</span><span class="sxs-lookup"><span data-stu-id="d04a6-294">**Authentication**: Basic</span></span>

- <span data-ttu-id="d04a6-295">**用户名**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d04a6-295">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="d04a6-296">**密码**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d04a6-296">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="d04a6-297">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-297">Response codes</span></span>

| <span data-ttu-id="d04a6-298">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-298">Response Code</span></span> | <span data-ttu-id="d04a6-299">说明</span><span class="sxs-lookup"><span data-stu-id="d04a6-299">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="d04a6-300">200</span><span class="sxs-lookup"><span data-stu-id="d04a6-300">200</span></span>               | <span data-ttu-id="d04a6-301">正常，atom+ xml 中的事件列表</span><span class="sxs-lookup"><span data-stu-id="d04a6-301">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="d04a6-302">404</span><span class="sxs-lookup"><span data-stu-id="d04a6-302">404</span></span>               | <span data-ttu-id="d04a6-303">未找到</span><span class="sxs-lookup"><span data-stu-id="d04a6-303">Not found</span></span>                         |
| <span data-ttu-id="d04a6-304">302</span><span class="sxs-lookup"><span data-stu-id="d04a6-304">302</span></span>               | <span data-ttu-id="d04a6-305">重定向</span><span class="sxs-lookup"><span data-stu-id="d04a6-305">Redirect</span></span>                          |
| <span data-ttu-id="d04a6-306">401</span><span class="sxs-lookup"><span data-stu-id="d04a6-306">401</span></span>               | <span data-ttu-id="d04a6-307">授权失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-307">Authorization Failed</span></span>              |
| <span data-ttu-id="d04a6-308">403</span><span class="sxs-lookup"><span data-stu-id="d04a6-308">403</span></span>               | <span data-ttu-id="d04a6-309">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-309">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="d04a6-310">按 ID 获取事件。</span><span class="sxs-lookup"><span data-stu-id="d04a6-310">Get an event by ID</span></span>

- <span data-ttu-id="d04a6-311">**方法**: GET</span><span class="sxs-lookup"><span data-stu-id="d04a6-311">**Method**: GET</span></span>

- <span data-ttu-id="d04a6-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="d04a6-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="d04a6-313">**标头**：键 = Content-Type，值 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d04a6-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="d04a6-314">**身份验证**: 基本</span><span class="sxs-lookup"><span data-stu-id="d04a6-314">**Authentication**: Basic</span></span>

- <span data-ttu-id="d04a6-315">**用户名**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d04a6-315">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="d04a6-316">**密码**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d04a6-316">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="d04a6-317">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-317">Response codes</span></span>

| <span data-ttu-id="d04a6-318">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-318">Response Code</span></span> | <span data-ttu-id="d04a6-319">说明</span><span class="sxs-lookup"><span data-stu-id="d04a6-319">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="d04a6-320">200</span><span class="sxs-lookup"><span data-stu-id="d04a6-320">200</span></span>               | <span data-ttu-id="d04a6-321">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-321">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="d04a6-322">404</span><span class="sxs-lookup"><span data-stu-id="d04a6-322">404</span></span>               | <span data-ttu-id="d04a6-323">未找到</span><span class="sxs-lookup"><span data-stu-id="d04a6-323">Not found</span></span>                                            |
| <span data-ttu-id="d04a6-324">302</span><span class="sxs-lookup"><span data-stu-id="d04a6-324">302</span></span>               | <span data-ttu-id="d04a6-325">重定向</span><span class="sxs-lookup"><span data-stu-id="d04a6-325">Redirect</span></span>                                             |
| <span data-ttu-id="d04a6-326">401</span><span class="sxs-lookup"><span data-stu-id="d04a6-326">401</span></span>               | <span data-ttu-id="d04a6-327">授权失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-327">Authorization Failed</span></span>                                 |
| <span data-ttu-id="d04a6-328">403</span><span class="sxs-lookup"><span data-stu-id="d04a6-328">403</span></span>               | <span data-ttu-id="d04a6-329">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-329">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="d04a6-330">按名称获取事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-330">Get an event by name</span></span>

- <span data-ttu-id="d04a6-331">**方法**: GET</span><span class="sxs-lookup"><span data-stu-id="d04a6-331">**Method**: GET</span></span>

- <span data-ttu-id="d04a6-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="d04a6-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="d04a6-333">**标头**：键 = Content-Type，值 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="d04a6-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="d04a6-334">**身份验证**: 基本</span><span class="sxs-lookup"><span data-stu-id="d04a6-334">**Authentication**: Basic</span></span>

- <span data-ttu-id="d04a6-335">**用户名**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="d04a6-335">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="d04a6-336">**密码**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="d04a6-336">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="d04a6-337">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-337">Response codes</span></span>

| <span data-ttu-id="d04a6-338">响应代码</span><span class="sxs-lookup"><span data-stu-id="d04a6-338">Response Code</span></span> | <span data-ttu-id="d04a6-339">说明</span><span class="sxs-lookup"><span data-stu-id="d04a6-339">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="d04a6-340">200</span><span class="sxs-lookup"><span data-stu-id="d04a6-340">200</span></span>               | <span data-ttu-id="d04a6-341">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="d04a6-342">404</span><span class="sxs-lookup"><span data-stu-id="d04a6-342">404</span></span>               | <span data-ttu-id="d04a6-343">未找到</span><span class="sxs-lookup"><span data-stu-id="d04a6-343">Not found</span></span>                                            |
| <span data-ttu-id="d04a6-344">302</span><span class="sxs-lookup"><span data-stu-id="d04a6-344">302</span></span>               | <span data-ttu-id="d04a6-345">重定向</span><span class="sxs-lookup"><span data-stu-id="d04a6-345">Redirect</span></span>                                             |
| <span data-ttu-id="d04a6-346">401</span><span class="sxs-lookup"><span data-stu-id="d04a6-346">401</span></span>               | <span data-ttu-id="d04a6-347">授权失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="d04a6-348">403</span><span class="sxs-lookup"><span data-stu-id="d04a6-348">403</span></span>               | <span data-ttu-id="d04a6-349">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="d04a6-349">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="d04a6-350">使用 PowerShell 或任何 HTTP 客户端创建事件</span><span class="sxs-lookup"><span data-stu-id="d04a6-350">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="d04a6-351">PowerShell 必须是版本 6 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d04a6-351">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="d04a6-352">在 PowerShell 会话中，运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="d04a6-352">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```