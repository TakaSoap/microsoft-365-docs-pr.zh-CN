---
title: 使用保留标签管理存储在 SharePoint 中的文档的生命周期
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 如何通过以下方法使用保留标签来管理 SharePoint 中的文档的生命周期：使用元数据对内容进行分类、自动应用标签，以及使用基于事件的保留来开始保留期。
ms.openlocfilehash: d02c8102dc53f455c5e0620acf1f8a9a7529bf08
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336687"
---
# <a name="use-retention-labels-to-manage-the-lifecycle-of-documents-stored-in-sharepoint"></a><span data-ttu-id="02199-103">使用保留标签管理存储在 SharePoint 中的文档的生命周期</span><span class="sxs-lookup"><span data-stu-id="02199-103">Use retention labels to manage the lifecycle of documents stored in SharePoint</span></span>

><span data-ttu-id="02199-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="02199-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="02199-105">本文介绍如何通过使用自动应用的保留标签和基于事件的保留来管理存储在 SharePoint 中的文档的生命周期。</span><span class="sxs-lookup"><span data-stu-id="02199-105">This article describes how you can manage the lifecycle of documents that are stored in SharePoint by using automatically applied retention labels and event-based retention.</span></span>

<span data-ttu-id="02199-106">自动应用功能使用 SharePoint 元数据来进行文档分类。</span><span class="sxs-lookup"><span data-stu-id="02199-106">The auto-apply functionality uses SharePoint metadata for document classification.</span></span> <span data-ttu-id="02199-107">本文中的示例针对产品相关文档，但相同的概念也可以用于其他方案。</span><span class="sxs-lookup"><span data-stu-id="02199-107">The example in this article is for product-related documents, but the same concepts can be used for other scenarios.</span></span> <span data-ttu-id="02199-108">例如，在石油和天然气行业，可以使用它来管理与石油平台、钻井日志或生产许可证等实物资产相关的文档的生命周期。</span><span class="sxs-lookup"><span data-stu-id="02199-108">For example, in the oil and gas industry, you could use it to manage the lifecycle of documents about physical assets such as oil platforms, well logs, or production licenses.</span></span> <span data-ttu-id="02199-109">在金融服务行业，你可以管理银行账户、抵押或保险合同方面的文档。</span><span class="sxs-lookup"><span data-stu-id="02199-109">In the financial services industry, you could manage bank account, mortgage, or insurance contract documents.</span></span> <span data-ttu-id="02199-110">在公共部门，你可以管理与施工许可证或纳税表。</span><span class="sxs-lookup"><span data-stu-id="02199-110">In the public sector, you could manage construction permits or tax forms.</span></span>

<span data-ttu-id="02199-111">在本文章，我们将探讨信息体系结构和保留标签的定义。</span><span class="sxs-lookup"><span data-stu-id="02199-111">In this article, we'll look at the information architecture and definition of the retention labels.</span></span> <span data-ttu-id="02199-112">然后，我们将通过自动应用标签对文档进行分类，</span><span class="sxs-lookup"><span data-stu-id="02199-112">Then we'll classify documents by auto-applying the labels.</span></span> <span data-ttu-id="02199-113">最后生成用于触发保留期的事件。</span><span class="sxs-lookup"><span data-stu-id="02199-113">And finally we'll generate the events that initiate the retention period.</span></span>

## <a name="information-architecture"></a><span data-ttu-id="02199-114">信息体系结构</span><span class="sxs-lookup"><span data-stu-id="02199-114">Information architecture</span></span>

<span data-ttu-id="02199-115">我们的方案基于一家制造公司，它使用 SharePoint 来存储与公司开发的产品相关的所有文档。</span><span class="sxs-lookup"><span data-stu-id="02199-115">Our scenario is a manufacturing company that uses SharePoint to store all the documents about the products that the company develops.</span></span> <span data-ttu-id="02199-116">这些文档包括产品规范、与供应商签订的协议以及用户手册。</span><span class="sxs-lookup"><span data-stu-id="02199-116">These documents include product specifications, agreements with suppliers, and user manuals.</span></span> <span data-ttu-id="02199-117">通过企业内容管理策略将这些文档存储在 SharePoint 中时，需要定义文档元数据，用于将其分类。</span><span class="sxs-lookup"><span data-stu-id="02199-117">When these documents are stored in SharePoint through Enterprise Content Management policies, document metadata is defined, which is used to classify them.</span></span> <span data-ttu-id="02199-118">每个文档都具有以下元数据属性：</span><span class="sxs-lookup"><span data-stu-id="02199-118">Each document has the following metadata properties:</span></span>

- <span data-ttu-id="02199-119">**文档类型**（例如产品规范、协议或用户手册）</span><span class="sxs-lookup"><span data-stu-id="02199-119">**Doc Type** (such as product specification, agreement, or user manual)</span></span>

- <span data-ttu-id="02199-120">**产品名称**</span><span class="sxs-lookup"><span data-stu-id="02199-120">**Product Name**</span></span>

- <span data-ttu-id="02199-121">**状态**（草稿或终稿）</span><span class="sxs-lookup"><span data-stu-id="02199-121">**Status** (draft or final)</span></span>

<span data-ttu-id="02199-122">此元数据形成所有文档的基本内容类型，它称为*生产文档*。</span><span class="sxs-lookup"><span data-stu-id="02199-122">This metadata forms a base content type called *Production Document* for all the documents.</span></span>

![产品文档元数据表](../media/SPRetention1.png)

> [!NOTE]
> <span data-ttu-id="02199-124">在方案的后面部分中，保留策略将使用**文档类型**和**状态**属性进行分类并自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="02199-124">The **Doc Type** and **Status** properties are used by retention policies later in this scenario to classify and auto-apply retention labels.</span></span>

<span data-ttu-id="02199-125">我们可能有几种表示不同类型文档的内容类型，但我们将重点介绍产品文档。</span><span class="sxs-lookup"><span data-stu-id="02199-125">We might have several content types that represent different types of documents, but let's focus on the product documentation.</span></span>

<span data-ttu-id="02199-126">在此方案中，我们使用托管元数据服务和术语库为*文档类型*创建一个术语集，并为*产品名称*创建另一个术语集。</span><span class="sxs-lookup"><span data-stu-id="02199-126">In this scenario, we use the Managed Metadata service and the Term Store to create a term set for *Doc Type* and another one for *Product Name*.</span></span> <span data-ttu-id="02199-127">对于每个术语集，我们将为每个值创建一个术语。</span><span class="sxs-lookup"><span data-stu-id="02199-127">For each term set, we create a term for each value.</span></span> <span data-ttu-id="02199-128">在 SharePoint 组织的术语库中，它看起来类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="02199-128">It would look like something like this in Term Store for your SharePoint organization:</span></span>

![术语库中的产品文档的示例术语集](../media/SPRetention2.png)

<span data-ttu-id="02199-130">可以使用[内容类型中心](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b)创建和发布*内容类型*，</span><span class="sxs-lookup"><span data-stu-id="02199-130">*Content Type* can be created and published by using the [Content Type Hub](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b).</span></span> <span data-ttu-id="02199-131">也可以使用网站预配工具（例如 [PnP 预配框架](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework)或[网站设计 JSON 架构](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type)）创建和发布内容类型。</span><span class="sxs-lookup"><span data-stu-id="02199-131">You can also create and publish a content type by using site provisioning tools, such as the [PnP provisioning framework](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-framework) or [site design JSON schema](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type).</span></span>

<span data-ttu-id="02199-132">每个产品都有一个专用的 SharePoint 网站，其中包含一个文档库，并且已启用正确的内容类型。</span><span class="sxs-lookup"><span data-stu-id="02199-132">Each product has a dedicated SharePoint site that contains one document library that has the right content types enabled.</span></span> <span data-ttu-id="02199-133">所有文档都存储在此文档库中。</span><span class="sxs-lookup"><span data-stu-id="02199-133">All documents are stored in this document library.</span></span>

<span data-ttu-id="02199-134">[![产品文档库](../media/SPRetention3.png)](../media/SPRetention3.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-134">[ ![Document library for product documentation](../media/SPRetention3.png) ](../media/SPRetention3.png#lightbox)</span></span>

> [!NOTE]
> <span data-ttu-id="02199-135">在此方案中，制造公司可以为每个产品使用 Microsoft 团队以支持团队成员之间的协作（例如持久聊天），而不是使每个产品都有一个 SharePoint 网站，它还可使用团队中的“**文件**”选项卡进行文档管理。</span><span class="sxs-lookup"><span data-stu-id="02199-135">Instead of having a SharePoint site per product, the manufacturing company in this scenario could use a Microsoft Team per product to support collaboration among members of the team, such as through persistent chat, and use the **Files** tab in Teams for document management.</span></span> <span data-ttu-id="02199-136">在本文中，我们只重点介绍文档，因此我们将只使用一个网站。</span><span class="sxs-lookup"><span data-stu-id="02199-136">In this article we only focus on documents, so, we'll only use a site.</span></span>

<span data-ttu-id="02199-137">以下是旋转小组件产品的文档库视图：</span><span class="sxs-lookup"><span data-stu-id="02199-137">Here's a view of the document library for the Spinning Widget product:</span></span>

<span data-ttu-id="02199-138">[![旋转小组件文档库](../media/SPRetention4.png)](../media/SPRetention4.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-138">[ ![Spinning Widget document library](../media/SPRetention4.png) ](../media/SPRetention4.png#lightbox)</span></span>

<span data-ttu-id="02199-139">现在，我们拥有用于文档管理的基本信息体系结构，下面让我们看一下使用元数据的文档保留和处置策略以及如何分类这些文档。</span><span class="sxs-lookup"><span data-stu-id="02199-139">Now that we have the basic information architecture in place for document management, let's look at the retention and disposal strategy for the documents that use the metadata and how we classify those documents.</span></span>

## <a name="retention-and-disposition"></a><span data-ttu-id="02199-140">保留和处置</span><span class="sxs-lookup"><span data-stu-id="02199-140">Retention and disposition</span></span>

<span data-ttu-id="02199-141">制造公司的合规性和数据管理策略规定了保存和处置数据的方式。</span><span class="sxs-lookup"><span data-stu-id="02199-141">The manufacturing company's compliance and data governance policies dictate how data is preserved and disposed of.</span></span> <span data-ttu-id="02199-142">与产品相关的文档必须在产品生产期间保存，并在生产之后额外保存一段时间。</span><span class="sxs-lookup"><span data-stu-id="02199-142">Product-related documents must be kept for as long as the product is manufactured and for a certain additional period.</span></span> <span data-ttu-id="02199-143">对于产品规范、协议和用户手册，该额外期限有所不同。</span><span class="sxs-lookup"><span data-stu-id="02199-143">The additional period differs for product specifications, agreements, and user manuals.</span></span> <span data-ttu-id="02199-144">下表列出了保留和处置要求：</span><span class="sxs-lookup"><span data-stu-id="02199-144">The following table indicates the retention and disposition requirements:</span></span>

|   <span data-ttu-id="02199-145">文档类型</span><span class="sxs-lookup"><span data-stu-id="02199-145">Document type</span></span>            |   <span data-ttu-id="02199-146">保留</span><span class="sxs-lookup"><span data-stu-id="02199-146">Retention</span></span>                            |   <span data-ttu-id="02199-147">处置</span><span class="sxs-lookup"><span data-stu-id="02199-147">Disposition</span></span>                                |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| <span data-ttu-id="02199-148">项目规范</span><span class="sxs-lookup"><span data-stu-id="02199-148">Product specifications</span></span>      | <span data-ttu-id="02199-149">产品停产后保留 5 年</span><span class="sxs-lookup"><span data-stu-id="02199-149">5 years after production stops</span></span>  | <span data-ttu-id="02199-150">删除</span><span class="sxs-lookup"><span data-stu-id="02199-150">Delete</span></span>                                       |
| <span data-ttu-id="02199-151">产品协议</span><span class="sxs-lookup"><span data-stu-id="02199-151">Product agreements</span></span>          | <span data-ttu-id="02199-152">产品停产后保留 10 年</span><span class="sxs-lookup"><span data-stu-id="02199-152">10 years after production stops</span></span> | <span data-ttu-id="02199-153">审阅</span><span class="sxs-lookup"><span data-stu-id="02199-153">Review</span></span>                                       |
| <span data-ttu-id="02199-154">用户手册</span><span class="sxs-lookup"><span data-stu-id="02199-154">User manuals</span></span>                | <span data-ttu-id="02199-155">产品停产后保留 5 年</span><span class="sxs-lookup"><span data-stu-id="02199-155">5 years after production stops</span></span>  | <span data-ttu-id="02199-156">删除</span><span class="sxs-lookup"><span data-stu-id="02199-156">Delete</span></span>                                       |
| <span data-ttu-id="02199-157">所有其他类型的文档</span><span class="sxs-lookup"><span data-stu-id="02199-157">All other types of documents</span></span> | <span data-ttu-id="02199-158">不主动保留</span><span class="sxs-lookup"><span data-stu-id="02199-158">Don't actively retain</span></span>  | <span data-ttu-id="02199-159">文档超过 3 年时删除</span><span class="sxs-lookup"><span data-stu-id="02199-159">Delete when document is older than 3 years</span></span> <br /><br /> <span data-ttu-id="02199-160">如果文档在过去 3 年内未曾修改，则视为超过 3 年。</span><span class="sxs-lookup"><span data-stu-id="02199-160">A document is considered older than 3 years if it hasn't been modified within the last 3 years.</span></span> |
|||

<span data-ttu-id="02199-161">我们使用 Microsoft 365 合规中心创建以下[保留标签](retention.md#retention-labels)：</span><span class="sxs-lookup"><span data-stu-id="02199-161">We use the Microsoft 365 compliance center to create the following [retention labels](retention.md#retention-labels):</span></span>

  - <span data-ttu-id="02199-162">产品规范</span><span class="sxs-lookup"><span data-stu-id="02199-162">Product Specification</span></span>

  - <span data-ttu-id="02199-163">产品协议</span><span class="sxs-lookup"><span data-stu-id="02199-163">Product Agreement</span></span>

  - <span data-ttu-id="02199-164">用户手册</span><span class="sxs-lookup"><span data-stu-id="02199-164">User Manual</span></span>

<span data-ttu-id="02199-165">在本文中，我们只介绍如何创建和自动应用产品规范保留标签。</span><span class="sxs-lookup"><span data-stu-id="02199-165">In this article, we only show how to create and auto-apply the Product Specification retention label.</span></span> <span data-ttu-id="02199-166">若要实施完整方案，也可创建并自动应用其他两种文档类型的保留标签。</span><span class="sxs-lookup"><span data-stu-id="02199-166">To implement the complete scenario, you would also create and auto-apply retention labels for the other two document types.</span></span>

### <a name="settings-for-the-product-specification-retention-label"></a><span data-ttu-id="02199-167">产品规范保留标签的设置</span><span class="sxs-lookup"><span data-stu-id="02199-167">Settings for the Product Specification retention label</span></span>

<span data-ttu-id="02199-168">以下是产品规范保留标签的[文件计划](file-plan-manager.md)：</span><span class="sxs-lookup"><span data-stu-id="02199-168">Here's the [file plan](file-plan-manager.md) for the Product Specification retention label:</span></span>

- <span data-ttu-id="02199-169">**名称：** 产品规范</span><span class="sxs-lookup"><span data-stu-id="02199-169">**Name:** Product Specification</span></span>

- <span data-ttu-id="02199-170">**管理员说明：** 产品停产后保留 5 年，自动删除，基于事件的保留，事件类型为“*产品停产*”。</span><span class="sxs-lookup"><span data-stu-id="02199-170">**Description for admins:** Retain for 5 years after production stops, auto delete, event-based retention, event type is *Product Cessation*.</span></span>

- <span data-ttu-id="02199-171">**用户说明：** 在产品停产后保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="02199-171">**Description for users:** Retain for 5 years after production stops.</span></span>

- <span data-ttu-id="02199-172">**保留操作：** 保留和删除。</span><span class="sxs-lookup"><span data-stu-id="02199-172">**Retention action:** Retain and delete.</span></span>

- <span data-ttu-id="02199-173">**保留期：** 5 年（1,825 天）。</span><span class="sxs-lookup"><span data-stu-id="02199-173">**Retention duration:** 5 years (1,825 days).</span></span>

- <span data-ttu-id="02199-174">**记录标签**：配置保留标签，以将内容分类为[记录](records-management.md#records)。</span><span class="sxs-lookup"><span data-stu-id="02199-174">**Record label**: Configure the retention label to classify content as a [record](records-management.md#records).</span></span> <span data-ttu-id="02199-175">（用户不能修改或删除分类为“*记录*”的文档。）</span><span class="sxs-lookup"><span data-stu-id="02199-175">(Documents that are classified as a *record* can't be modified or deleted by users.)</span></span>

- <span data-ttu-id="02199-176">**文件计划描述符：**（为简化方案，未提供文件描述符）</span><span class="sxs-lookup"><span data-stu-id="02199-176">**File plan descriptors:** (for simplifying the scenario, no file descriptors are provided)</span></span>

<span data-ttu-id="02199-177">以下屏幕截图显示了在 Microsoft 365 合规中心内创建产品规范保留标签时的设置。</span><span class="sxs-lookup"><span data-stu-id="02199-177">The following screenshot shows the settings when you create the Product Specification retention label in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="02199-178">创建保留标签时，可创建“*产品停产*”事件类型。</span><span class="sxs-lookup"><span data-stu-id="02199-178">You can create the *Product Cessation* event type when you create the retention label.</span></span> <span data-ttu-id="02199-179">请在下一节中查看相关程序。</span><span class="sxs-lookup"><span data-stu-id="02199-179">See the procedure in the following section.</span></span>

![产品规范标签的保留设置](../media/SPRetention5.png)

> [!NOTE]
> <span data-ttu-id="02199-181">为了避免需要等待 5 年才能删除文档，如果要在测试环境中重新创建此方案，请将保留期设置为 ***1 天***。</span><span class="sxs-lookup"><span data-stu-id="02199-181">To avoid a 5-year wait for document deletion, set the retention duration to ***1 day*** if you're recreating this scenario in a test environment.</span></span>

### <a name="create-an-event-type-when-you-create-a-retention-label"></a><span data-ttu-id="02199-182">创建保留标签时创建事件类型</span><span class="sxs-lookup"><span data-stu-id="02199-182">Create an event type when you create a retention label</span></span>

1. <span data-ttu-id="02199-183">从“**基于以下条件保留或删除内容**”下拉列表中，选择“**事件**”。</span><span class="sxs-lookup"><span data-stu-id="02199-183">From the **Retain or delete content based on** drop-down list, select **an event**.</span></span>

2. <span data-ttu-id="02199-184">选择“**选择事件类型**”。</span><span class="sxs-lookup"><span data-stu-id="02199-184">Select **Choose an event type**.</span></span>
    
    ![“为产品规范标签新建事件类型”对话框](../media/SPRetention6.png)

3. <span data-ttu-id="02199-186">然后在“**选择事件类型**”页上，在“**选择事件类型**”页面上选择“**创建新的事件类型**”。</span><span class="sxs-lookup"><span data-stu-id="02199-186">Select **Choose an event type**, and then select **Create new event types** on the **Choose an event type** page.</span></span>

4. <span data-ttu-id="02199-187">创建名为“***产品停产***”的事件类型，提供说明，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="02199-187">Create an event type named ***Product Cessation***, enter a description, and select **Finish**.</span></span>

5. <span data-ttu-id="02199-188">返回到“**选择事件类型**”页面上，选择所创建的“**产品停产**”事件类型，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="02199-188">Back on the **Choose an event type** page, select the **Product Cessation** event type that you created, and then select **Add**.</span></span>

   <span data-ttu-id="02199-189">以下是产品规范保留标签的设置的示例。</span><span class="sxs-lookup"><span data-stu-id="02199-189">Here's what the settings look like for the Product Specification retention label.</span></span> 

   ![新产品规范标签的设置](../media/SPRetention7.png)

6. <span data-ttu-id="02199-191">选择“**创建此标签**”。</span><span class="sxs-lookup"><span data-stu-id="02199-191">Select **Create this label**.</span></span> 

   > [!TIP]
   > <span data-ttu-id="02199-192">有关更详细的步骤，请参阅[创建保留期基于事件的标签](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event)。</span><span class="sxs-lookup"><span data-stu-id="02199-192">For more detailed steps, see [Create a label whose retention period is based on an event](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event).</span></span>

<span data-ttu-id="02199-193">现在，让我们看一下如何将保留标签自动应用于产品规范内容。</span><span class="sxs-lookup"><span data-stu-id="02199-193">Now let's look at auto-applying the retention label to product-specification content.</span></span>

## <a name="auto-apply-retention-labels-to-classify-content"></a><span data-ttu-id="02199-194">自动应用保留标签来分类内容</span><span class="sxs-lookup"><span data-stu-id="02199-194">Auto-apply retention labels to classify content</span></span>

<span data-ttu-id="02199-195">我们将使用关键字查询语言 (KQL) [自动应用](apply-retention-labels-automatically.md)创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="02199-195">We're going to use Keyword Query Language (KQL) to [auto-apply](apply-retention-labels-automatically.md) the retention labels that we created.</span></span> <span data-ttu-id="02199-196">KQL 是用于构建搜索查询的语言。</span><span class="sxs-lookup"><span data-stu-id="02199-196">KQL is the language that's used to build search queries.</span></span> <span data-ttu-id="02199-197">在 KQL 中，可使用关键字或托管属性进行搜索。</span><span class="sxs-lookup"><span data-stu-id="02199-197">In KQL, you can search by using keywords or managed properties.</span></span> <span data-ttu-id="02199-198">有关详细信息，请参阅[关键字查询语言 (KQL) 语法参考](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)。</span><span class="sxs-lookup"><span data-stu-id="02199-198">For more information, see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="02199-199">一般来说，我们希望告诉 Microsoft 365 将“*产品规范*”保留标签应用于所有“**状态**”为“***终稿***”且“**文档类型**”为“***产品规范***”的文档。</span><span class="sxs-lookup"><span data-stu-id="02199-199">Basically, we want to tell Microsoft 365 to "apply the *Product Specification* retention label to all documents that have a **Status** of ***Final*** and a **Doc Type** of ***Product Specification***."</span></span> <span data-ttu-id="02199-200">请记住，“**状态**”和“**文档类型**”是我们在“[信息体系结构](#information-architecture)”部分中为产品文档内容类型定义的网站栏。</span><span class="sxs-lookup"><span data-stu-id="02199-200">Recall that **Status** and **Doc Type** are the site columns that we defined for the Product Documentation content type in the [Information architecture](#information-architecture) section.</span></span> <span data-ttu-id="02199-201">若要执行此操作，我们需要配置搜索架构。</span><span class="sxs-lookup"><span data-stu-id="02199-201">To do this, we need to configure the search schema.</span></span>

<span data-ttu-id="02199-202">当 SharePoint 为内容创建索引时，它将自动为每个网站栏生成已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-202">When SharePoint indexes content, it automatically generates crawled properties for each site column.</span></span> <span data-ttu-id="02199-203">对于此方案，我们对**文档类型**和**状态**属性感兴趣。</span><span class="sxs-lookup"><span data-stu-id="02199-203">For this scenario, we're interested in the **Doc Type** and **Status** properties.</span></span> <span data-ttu-id="02199-204">我们需要库中的文档属于正确的内容类型，并填写网站栏，以便搜索并创建已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-204">We need documents in the library that are the right content type and have the site columns filled in for search to create the crawled properties.</span></span>

<span data-ttu-id="02199-205">在 SharePoint 管理中心，打开“搜索”配置，然后选择“**管理搜索架构**”以查看并配置已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-205">In the SharePoint admin center, open the Search configuration, and select **Manage Search Schema** to view and configure the crawled properties.</span></span>

![搜索架构中已爬网属性](../media/SPRetention8.png)

<span data-ttu-id="02199-207">如果在“**已爬网属性**”框中键入“***状态***”，然后选择绿色箭头，则会看到如下所示的结果：</span><span class="sxs-lookup"><span data-stu-id="02199-207">If we type ***status*** in the **Crawled properties** box and select the green arrow, we should see a result like this:</span></span>

![ows_Status 已爬网属性](../media/SPRetention9.png)

<span data-ttu-id="02199-209">**ows\_\_Status** 属性（注意双下划线）是我们感兴趣的属性。</span><span class="sxs-lookup"><span data-stu-id="02199-209">The **ows\_\_Status** property (notice the double underscore) is the one that interests us.</span></span> <span data-ttu-id="02199-210">它将映射到生产文档内容类型的**状态**属性。</span><span class="sxs-lookup"><span data-stu-id="02199-210">It maps to the **Status** property of the Production Document content type.</span></span>

<span data-ttu-id="02199-211">现在，如果我们键入 ***ows\_doc*** 并选择绿色箭头，则会看到如下所示的内容：</span><span class="sxs-lookup"><span data-stu-id="02199-211">Now, if we type ***ows\_doc*** and select the green arrow, we should see something like this:</span></span>

![ows_Doc_Type 已爬网属性](../media/SPRetention10.png)

<span data-ttu-id="02199-213">**ows\_Doc\_x0020\_Type** 属性是我们感兴趣的第二个属性。</span><span class="sxs-lookup"><span data-stu-id="02199-213">The **ows\_Doc\_x0020\_Type** property is the second property that interests us.</span></span> <span data-ttu-id="02199-214">它将映射到生产文档内容类型的**文档类型**属性。</span><span class="sxs-lookup"><span data-stu-id="02199-214">It maps to the **Doc Type** property of the Production Document content type.</span></span>

> [!TIP]
> <span data-ttu-id="02199-215">若要标识此方案的已爬网属性的名称，请转到包含生产文档的文档库，</span><span class="sxs-lookup"><span data-stu-id="02199-215">To identify the name of a crawled property for this scenario, go to the document library that contains the production documents.</span></span> <span data-ttu-id="02199-216">然后转到库设置。</span><span class="sxs-lookup"><span data-stu-id="02199-216">Then go to the library settings.</span></span> <span data-ttu-id="02199-217">对于“**栏**”，选择栏名称（例如“**状态**”或“**文档类型**”）以打开网站栏页面。</span><span class="sxs-lookup"><span data-stu-id="02199-217">For **Columns**, select the name of the column (for example, **Status** or **Doc Type**) to open the site column page.</span></span> <span data-ttu-id="02199-218">该页面的 URL 中的“*字段*”参数包含字段名称。</span><span class="sxs-lookup"><span data-stu-id="02199-218">The *Field* parameter in the URL for that page contains the name of the field.</span></span> <span data-ttu-id="02199-219">该字段名称以“ows_”为前缀，是已爬网属性的名称。</span><span class="sxs-lookup"><span data-stu-id="02199-219">This field name, prefixed with "ows_", is the name of the crawled property.</span></span> <span data-ttu-id="02199-220">例如，URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` 对应于 *ows\_\_Status* 已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-220">For example, the URL `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` corresponds to the *ows\_\_Status* crawled property.</span></span>

<span data-ttu-id="02199-221">如果你要查找的已爬网属性未显示在 SharePoint 管理中心的“管理搜索架构”部分中：</span><span class="sxs-lookup"><span data-stu-id="02199-221">If the crawled properties you're looking for don't appear in the Manage Search Schema section in SharePoint admin center:</span></span>

- <span data-ttu-id="02199-222">可能是由以下原因之一造成的。</span><span class="sxs-lookup"><span data-stu-id="02199-222">Maybe the documents haven't been indexed.</span></span> <span data-ttu-id="02199-223">你可以通过转到“**文档库设置**” > “**高级设置**”来强制重新编制库的索引。</span><span class="sxs-lookup"><span data-stu-id="02199-223">You can force a reindex of the library by going to **Document library settings** > **Advanced Settings**.</span></span>

- <span data-ttu-id="02199-224">如果文档库位于新式网站中，请确保 SharePoint 管理员也是网站集管理员。</span><span class="sxs-lookup"><span data-stu-id="02199-224">If the document library is in a modern site, make sure that the SharePoint admin is also a site collection admin.</span></span>

<span data-ttu-id="02199-225">有关已爬网属性和托管属性的详细信息，请参阅[在 SharePoint 服务器中自动创建托管的属性](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="02199-225">For more information about crawled and managed properties, see [Automatically created managed properties in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint).</span></span>

### <a name="map-crawled-properties-to-pre-defined-managed-properties"></a><span data-ttu-id="02199-226">将已爬网属性映射到预定义的托管属性</span><span class="sxs-lookup"><span data-stu-id="02199-226">Map crawled properties to pre-defined managed properties</span></span>

<span data-ttu-id="02199-227">KQL 不能在搜索查询中使用已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-227">KQL can't use crawled properties in search queries.</span></span> <span data-ttu-id="02199-228">它必须使用托管属性。</span><span class="sxs-lookup"><span data-stu-id="02199-228">It has to use a managed property.</span></span> <span data-ttu-id="02199-229">在典型搜索方案中，我们将创建托管属性，并将其映射到所需的已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-229">In a typical search scenario, we create a managed property and map it to the crawled property that we need.</span></span> <span data-ttu-id="02199-230">但是，对于自动应用保留标签，只能指定预定义的托管属性，而不能指定自定义托管属性。</span><span class="sxs-lookup"><span data-stu-id="02199-230">However, for auto-applying retention labels, you can only specify pre-defined managed properties in KQL, not custom managed properties.</span></span> <span data-ttu-id="02199-231">已在系统中为字符串 *RefinableString00* 到 *RefinableString199* 创建一组预定义的托管属性。</span><span class="sxs-lookup"><span data-stu-id="02199-231">There's a set of predefined managed properties in the system for string *RefinableString00* to *RefinableString199* that you can use.</span></span> <span data-ttu-id="02199-232">有关完整列表，请参阅[默认未使用托管属性](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties)。</span><span class="sxs-lookup"><span data-stu-id="02199-232">For a complete list, see [Default unused managed properties](https://docs.microsoft.com/sharepoint/manage-search-schema#default-unused-managed-properties).</span></span> <span data-ttu-id="02199-233">这些默认托管属性通常用于定义搜索精简程序。</span><span class="sxs-lookup"><span data-stu-id="02199-233">These default managed properties are typically used for defining search refiners.</span></span>

<span data-ttu-id="02199-234">为了使 KQL 查询自动将正确的保留标签应用于产品文档内容，我们将已爬网属性 **ows\_Doc\_x0020\_Type* 和 *ows\_\_Status** 映射到两个可精简的托管属性。</span><span class="sxs-lookup"><span data-stu-id="02199-234">For the KQL query to automatically apply the correct retention label to product document content, we map the crawled properties **ows\_Doc\_x0020\_Type* and *ows\_\_Status** to two refinable managed properties.</span></span> <span data-ttu-id="02199-235">在此方案的测试环境中，未使用 **RefinableString00** 和 **RefinableString01**。</span><span class="sxs-lookup"><span data-stu-id="02199-235">In our test environment for this scenario, **RefinableString00** and **RefinableString01** aren't being used.</span></span> <span data-ttu-id="02199-236">通过在 SharePoint 管理中心的“**管理搜索架构**”中查看“**托管属性**”，可以确定这一点。</span><span class="sxs-lookup"><span data-stu-id="02199-236">We determined this by looking at **Managed Properties** in **Manage Search Schema** in the SharePoint admin center.</span></span>

<span data-ttu-id="02199-237">[![搜索架构中托管属性](../media/SPRetention12.png)](../media/SPRetention12.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-237">[ ![Managed properties in search schema](../media/SPRetention12.png) ](../media/SPRetention12.png#lightbox)</span></span>

<span data-ttu-id="02199-238">请注意，先前屏幕截图中的“**映射的已爬网属性**”栏为空。</span><span class="sxs-lookup"><span data-stu-id="02199-238">Notice that the **Mapped Crawled Properties** column in the previous screenshot is empty.</span></span>

<span data-ttu-id="02199-239">若要映射 **ows\_Doc\_x0020\_Type** 已爬网属性，请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="02199-239">To map the **ows\_Doc\_x0020\_Type** crawled property, follow these steps:</span></span>

1. <span data-ttu-id="02199-240">在“**托管属性**”筛选器框中，键入 ***RefinableString00***，然后选择绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="02199-240">In the **Managed property** filter box, type ***RefinableString00*** and select the green arrow.</span></span>

2. <span data-ttu-id="02199-241">在结果列表中，选择**RefinableString00** 链接，然后向下滚动到“**到已爬网属性的映射**”部分。</span><span class="sxs-lookup"><span data-stu-id="02199-241">In the results list, select the **RefinableString00** link, and then scroll down to the **Mappings to crawled properties** section.</span></span>  

3. <span data-ttu-id="02199-242">选择“**添加映射**”，然后在“**已爬网属性选择**”窗口的“**搜索已爬网属性名称**”框中键入 ***ows\_Doc\_x0020\_Type***。</span><span class="sxs-lookup"><span data-stu-id="02199-242">Select **Add a Mapping**, and then type ***ows\_Doc\_x0020\_Type*** in the **Search for a crawled property name** box in the **Crawled property selection** window.</span></span> <span data-ttu-id="02199-243">选择“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="02199-243">Select **Find**.</span></span>  

4. <span data-ttu-id="02199-244">在结果列表中，选择“**ows\_Doc\_x0020\_Type**”，然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="02199-244">In the results list, select **ows\_Doc\_x0020\_Type** and then select **OK**.</span></span>

   <span data-ttu-id="02199-245">在**映射的已爬网属性**部分中，你将看到类似于以下屏幕截图的内容：</span><span class="sxs-lookup"><span data-stu-id="02199-245">In the **Mapped Crawled Properties** section, you should see something similar to this screenshot:</span></span>

   <span data-ttu-id="02199-246">[![在“映射的已爬网属性”部分，单击“添加映射”](../media/SPRetention13.png)](../media/SPRetention13.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-246">[ ![Select Add a mapping in the Mapped crawled properties section](../media/SPRetention13.png) ](../media/SPRetention13.png#lightbox)</span></span>


5. <span data-ttu-id="02199-247">滚动到页面的底部，然后选择“**确定**”以保存映射。</span><span class="sxs-lookup"><span data-stu-id="02199-247">Scroll to the bottom of the page and select **OK** to save the mapping.</span></span>

<span data-ttu-id="02199-248">重复上述步骤，以映射 **RefinableString01** 和 **ows\_\_Status**。</span><span class="sxs-lookup"><span data-stu-id="02199-248">Repeat these steps to map **RefinableString01** and **ows\_\_Status**.</span></span>

<span data-ttu-id="02199-249">现在，应该已将两个托管属性映射到两个已爬网属性：</span><span class="sxs-lookup"><span data-stu-id="02199-249">Now you should have two managed properties mapped to the two crawled properties:</span></span>

<span data-ttu-id="02199-250">[![显示的托管属性已映射至已爬网属性](../media/SPRetention14.png)](../media/SPRetention14.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-250">[ ![Managed properties shown mapped to crawled properties](../media/SPRetention14.png) ](../media/SPRetention14.png#lightbox)</span></span>

<span data-ttu-id="02199-251">通过运行企业级搜索来验证设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="02199-251">Let's verify that our setup is correct by running an enterprise search.</span></span> <span data-ttu-id="02199-252">在浏览器中，转到 *https://\<your_tenant>.sharepoint.com/search*。</span><span class="sxs-lookup"><span data-stu-id="02199-252">In a browser, go to *https://\<your_tenant>.sharepoint.com/search*.</span></span> <span data-ttu-id="02199-253">在搜索框中，键入 ***RefinableString00：“产品规范”***，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="02199-253">In the search box, type ***RefinableString00:"Product Specification"*** and press enter.</span></span> <span data-ttu-id="02199-254">此搜索应该会返回“***文档类型***”为“**产品规范**”的所有文档。</span><span class="sxs-lookup"><span data-stu-id="02199-254">This search should return all documents that have a **Product Specification** of ***Doc Type***.</span></span>

<span data-ttu-id="02199-255">现在，在搜索框中，键入 **RefinableString00：“产品规范”和 RefinableString01：终稿**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="02199-255">Now in the search box, type **RefinableString00:"Product Specification" AND RefinableString01:Final** and press enter.</span></span> <span data-ttu-id="02199-256">这会返回“**文档类型**”为“***产品规范***”且“**状态**”为“***终稿***”的所有文档。</span><span class="sxs-lookup"><span data-stu-id="02199-256">This should return all documents that have **Product Specification** of ***Doc Type*** and a **Status** of ***Final***.</span></span>

### <a name="create-auto-apply-label-policies"></a><span data-ttu-id="02199-257">创建自动应用标签策略</span><span class="sxs-lookup"><span data-stu-id="02199-257">Create auto-apply label policies</span></span>

<span data-ttu-id="02199-258">现在，我们已验证 KQL 查询可正常工作，下面让我们创建标签策略，它使用 KQL 查询将产品规范保留标签自动应用于相应的文档。</span><span class="sxs-lookup"><span data-stu-id="02199-258">Now that we've verified that the KQL query is working, let's create a label policy that uses a KQL query to auto-apply the Product Specification retention label to the appropriate documents.</span></span>

1. <span data-ttu-id="02199-259">在“[合规中心](https://compliance.microsoft.com/homepage)”，转到“**记录管理**” > “**标签策略**” > “**标签**”。</span><span class="sxs-lookup"><span data-stu-id="02199-259">In the [compliance center](https://compliance.microsoft.com/homepage), go to **Records management** > **Label policies** > **Auto-apply a label**.</span></span>

   <span data-ttu-id="02199-260">[![选择“标签”页面上的“自动应用标签”](../media/SPRetention16.png)](../media/SPRetention16.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-260">[ ![Select "Auto-apply a label" on the Labels page](../media/SPRetention16.png) ](../media/SPRetention16.png#lightbox)</span></span>

2. <span data-ttu-id="02199-261">在“**选择要自动应用的标签**”向导页面上，选择“**选择要自动应用的标签**”。</span><span class="sxs-lookup"><span data-stu-id="02199-261">On the **Choose a label to auto-apply** wizard page, select **Choose a label to auto-apply**.</span></span>

3. <span data-ttu-id="02199-262">从标签列表中，选择“**产品规范**”。</span><span class="sxs-lookup"><span data-stu-id="02199-262">From the list of labels, select **Product Specification**.</span></span> <span data-ttu-id="02199-263">然后选择“**添加**”和“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="02199-263">Then select **Add** and **Next**.</span></span>

4. <span data-ttu-id="02199-264">选择“**将标签应用到包含特定字词或短语或属性的内容**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="02199-264">Select **Apply label to content that contains specific words or phrases, or properties**, and then select **Next**.</span></span>

   <span data-ttu-id="02199-265">[![选择应用标签至含有指定单词、短语或属性的内容](../media/SPRetention17.png)](../media/SPRetention17.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-265">[ ![Select Apply label to content that contains specific words or phrases, or properties](../media/SPRetention17.png) ](../media/SPRetention17.png#lightbox)</span></span>

   <span data-ttu-id="02199-266">在下一步中，提供与我们在上一节中测试的查询相同的 KQL 搜索查询。</span><span class="sxs-lookup"><span data-stu-id="02199-266">In the next step, you'll provide the same KQL search query that we tested in the previous section.</span></span> <span data-ttu-id="02199-267">此查询返回状态为“*终稿*”的所有产品规范文档。</span><span class="sxs-lookup"><span data-stu-id="02199-267">This query returns all Product Specification documents that have a status of *Final*.</span></span> <span data-ttu-id="02199-268">在标签策略中使用此相同查询时，产品规范保留标签将自动应用于与该其匹配的所有文档。</span><span class="sxs-lookup"><span data-stu-id="02199-268">When we use this same query in the label policy, the Product Specification retention label will be automatically applied to all documents that match it.</span></span>

5. <span data-ttu-id="02199-269">在“**关键字查询编辑器**”框中，键入 ***RefinableString00：“产品规范”和 RefinableString01：终稿***，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="02199-269">In the **Keyword query editor** box, type ***RefinableString00:"Product Specification" AND RefinableString01:Final***, and then select **Next**.</span></span>

   ![在 "关键字查询编辑器" 框中指定查询](../media/SPRetention19.png)

6. <span data-ttu-id="02199-271">输入标签策略的名称（例如，“***自动应用产品规范标签***”）和可选说明，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="02199-271">Type a name (for example, ***Auto apply Product Specification label***) and an optional description for the label policy, and then select **Next**.</span></span>

7. <span data-ttu-id="02199-272">在**选择位置**向导页面上，选择要应用策略的内容位置。</span><span class="sxs-lookup"><span data-stu-id="02199-272">On the **Choose locations** wizard page, you select the content locations that you want to apply the policy to.</span></span> <span data-ttu-id="02199-273">对于此方案，我们将策略仅应用于 SharePoint 位置，因为所有生产文档都存储在 SharePoint 文档库中。</span><span class="sxs-lookup"><span data-stu-id="02199-273">For this scenario, we apply the policy only to SharePoint locations, because all the production documents are stored in SharePoint document libraries.</span></span> <span data-ttu-id="02199-274">选择“**让我选择特定位置**”，将 **Exchange 电子邮件**、**OneDrive 帐户**和 **Microsoft 365 组**的状态切换为关闭。</span><span class="sxs-lookup"><span data-stu-id="02199-274">Select **Let me choose specific locations** and then toggle the status for **Exchange email**, **OneDrive accounts**, and **Microsoft 365 Groups** to off.</span></span> <span data-ttu-id="02199-275">确保将 SharePoint 网站的状态切换为打开。</span><span class="sxs-lookup"><span data-stu-id="02199-275">Make sure that the status for SharePoint sites is set to on.</span></span> 

    ![选择自动应用标签的指定网站](../media/SPRetentionSPlocations.png)

   > [!TIP]
   > <span data-ttu-id="02199-277">可以选择“**选择网站**”并添加特定 SharePoint 网站的 URL，而不是将策略应用于所有 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="02199-277">Instead of applying the policy to all SharePoint sites, you can select **Choose sites** and add the URLs for specific SharePoint sites.</span></span>

8. <span data-ttu-id="02199-278">选择“**下一步**”以显示“**查看你的设置**”页面。</span><span class="sxs-lookup"><span data-stu-id="02199-278">Select **Next** to display the **Review your settings** page.</span></span>

    ![自动应用标签的设置](../media/SPRetention18.png)

9. <span data-ttu-id="02199-280">选择“**自动应用**”以创建标签策略。</span><span class="sxs-lookup"><span data-stu-id="02199-280">Select **Auto-apply** to create the label policy.</span></span>

   >[!NOTE]
   ><span data-ttu-id="02199-281">最多需要 7 天时间才能将产品规范标签自动应用到与 KQL 搜索查询匹配的所有文档。</span><span class="sxs-lookup"><span data-stu-id="02199-281">It takes up to 7 days to automatically apply the Product Specification label to all documents that match the KQL search query.</span></span>

### <a name="verify-that-the-retention-label-was-automatically-applied"></a><span data-ttu-id="02199-282">验证保留标签是否已自动应用</span><span class="sxs-lookup"><span data-stu-id="02199-282">Verify that the retention label was automatically applied</span></span>

<span data-ttu-id="02199-283">7 天后，使用合规中心内的[活动资源管理器](data-classification-activity-explorer.md)验证我们创建的标签策略是否已自动将保留标签应用于产品文档。</span><span class="sxs-lookup"><span data-stu-id="02199-283">After 7 days, use the [activity explorer](data-classification-activity-explorer.md) in the compliance center to verify that the label policy that we created  automatically applied the retention labels to the product documents.</span></span>

<span data-ttu-id="02199-284">此外，查看文档库中文档的属性。</span><span class="sxs-lookup"><span data-stu-id="02199-284">Also look at the properties of the documents in the Document Library.</span></span> <span data-ttu-id="02199-285">在信息面板中，你可以看到保留标签已应用于所选文档。</span><span class="sxs-lookup"><span data-stu-id="02199-285">In the information panel, you can see that the retention label is applied to a selected document.</span></span>

<span data-ttu-id="02199-286">[![通过查看文档库中的文档属性，验证标签是否已应用](../media/SPRetention21.png)](../media/SPRetention21.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-286">[ ![Verify that label was applied by looking at the document properties in the Document Library](../media/SPRetention21.png) ](../media/SPRetention21.png#lightbox)</span></span>

<span data-ttu-id="02199-287">由于保留标签已自动应用于文档，因此可以保护文档免遭删除，因为该保留标签已配置为将文档声明为*记录*。</span><span class="sxs-lookup"><span data-stu-id="02199-287">Because the retention labels were auto-applied to documents, those documents are protected from deletion because the retention label was configured to declare the documents as *records*.</span></span> <span data-ttu-id="02199-288">作为此保护的示例，我们会在尝试删除其中一个文档时收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="02199-288">As an example of this protection, we get the following error message when we try to delete one of these documents:</span></span>

<span data-ttu-id="02199-289">[![错误消息显示无法删除文档，因为标签声明文档为记录。](../media/SPRetention22.png)](../media/SPRetention22.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-289">[ ![An error message shows that documents can't be deleted because the label declares that the documents are records.](../media/SPRetention22.png) ](../media/SPRetention22.png#lightbox)</span></span>

## <a name="generate-the-event-that-triggers-the-retention-period"></a><span data-ttu-id="02199-290">生成触发保留期限的事件</span><span class="sxs-lookup"><span data-stu-id="02199-290">Generate the event that triggers the retention period</span></span>

<span data-ttu-id="02199-291">现在已应用保留标签，下面我们将重点介绍用于指示特定产品停产的事件。</span><span class="sxs-lookup"><span data-stu-id="02199-291">Now that the retention labels are applied, let's focus on the event that will indicate the end of production for a particular product.</span></span> <span data-ttu-id="02199-292">此事件触发保留标签中定义的保留期。</span><span class="sxs-lookup"><span data-stu-id="02199-292">This event triggers the beginning of the retention period that's defined in the retention labels.</span></span> <span data-ttu-id="02199-293">例如，对于产品规范文档，当触发“产品停产”事件时，将开始 5 年的保留期。</span><span class="sxs-lookup"><span data-stu-id="02199-293">For example, for product specification documents, the 5-year retention period begins when the "end of production" event is triggered.</span></span>

<span data-ttu-id="02199-294">可以通过转到“**记录管理**” > “**事件**”，在 Microsoft 365 合规中心手动创建事件。</span><span class="sxs-lookup"><span data-stu-id="02199-294">You can manually create the event in the Microsoft 365 compliance center by going to **Records Managements** > **Events**.</span></span> <span data-ttu-id="02199-295">可选择事件类型、设置正确的资产 ID 并输入事件的日期。</span><span class="sxs-lookup"><span data-stu-id="02199-295">You would choose the event type, set the correct asset IDs, and enter a date for the event.</span></span> <span data-ttu-id="02199-296">有关详细信息，请参阅[从事件发生时开始计算保留期](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="02199-296">For more information, see [Start retention when an event occurs](event-driven-retention.md).</span></span>

<span data-ttu-id="02199-297">对于此方案，我们将从外部生产系统自动生成事件。</span><span class="sxs-lookup"><span data-stu-id="02199-297">But for this scenario, we'll automatically generate the event from an external production system.</span></span> <span data-ttu-id="02199-298">系统是一个简单的 SharePoint 列表，用于指示产品是否已投入生产。</span><span class="sxs-lookup"><span data-stu-id="02199-298">The system is a simple SharePoint list that indicates whether a product is in production.</span></span> <span data-ttu-id="02199-299">与列表关联的 [Power Automate](https://docs.microsoft.com/flow/getting-started) 流将触发事件。</span><span class="sxs-lookup"><span data-stu-id="02199-299">A [Power Automate](https://docs.microsoft.com/flow/getting-started) flow that's associated with the list will trigger the event.</span></span> <span data-ttu-id="02199-300">在现实方案中，它可以使用各种系统（例如 HR 或 CRM 系统）生成事件。</span><span class="sxs-lookup"><span data-stu-id="02199-300">In a real-world scenario, you could use various systems to generate the event, such as an HR or CRM system.</span></span> <span data-ttu-id="02199-301">Power Automate 包含许多可供 Microsoft 365 工作负载（例如 Microsoft Exchange、SharePoint、Teams 和 Dynamics 365）及第三方应用（例如 Twitter、Box、Salesforce 和 Workdays）使用的交互和构建块。</span><span class="sxs-lookup"><span data-stu-id="02199-301">Power Automate contains many ready-to-use interactions and building block for Microsoft 365 workloads, such as Microsoft Exchange, SharePoint, Teams, and Dynamics 365, plus third-party apps such as Twitter, Box, Salesforce, and Workdays.</span></span> <span data-ttu-id="02199-302">此功能使你可以轻松地将 Power Automate 与各种系统集成。</span><span class="sxs-lookup"><span data-stu-id="02199-302">This feature makes it easy to integrate Power Automate with various systems.</span></span> <span data-ttu-id="02199-303">有关详细信息，请参阅[自动执行事件驱动的保留](automate-event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="02199-303">For more information, see [Automate event-driven retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="02199-304">以下屏幕截图显示将用于触发事件的 SharePoint 列表：</span><span class="sxs-lookup"><span data-stu-id="02199-304">The following screenshot shows the SharePoint list that will be used the trigger the event:</span></span>

<span data-ttu-id="02199-305">[![将触发保留事件的列表](../media/SPRetention23.png)](../media/SPRetention23.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-305">[ ![The list that will trigger the retention event](../media/SPRetention23.png) ](../media/SPRetention23.png#lightbox)</span></span>

<span data-ttu-id="02199-306">目前有两种产品已投入生产，“**投入生产**”栏中的“***是***”指明了这一点。</span><span class="sxs-lookup"><span data-stu-id="02199-306">There are two products currently in production, as indicated by the ***Yes*** in the **In Production** column.</span></span> <span data-ttu-id="02199-307">当产品的此栏中的值设置为“***否***”时，与列表关联的流将自动生成事件。</span><span class="sxs-lookup"><span data-stu-id="02199-307">When the value in this column is set to ***No*** for a product, the flow associated with the list will automatically generate the event.</span></span> <span data-ttu-id="02199-308">该事件会触发自动应用到相应产品文档的保留标签的保留期。</span><span class="sxs-lookup"><span data-stu-id="02199-308">The event triggers the start of the retention period for the retention label that was auto-applied to the corresponding product documents.</span></span>

<span data-ttu-id="02199-309">对于此方案，我们将使用以下流来触发事件：</span><span class="sxs-lookup"><span data-stu-id="02199-309">For this scenario, we use the following flow to trigger the event:</span></span>

<span data-ttu-id="02199-310">[![配置将触发事件的流程](../media/SPRetention24.png)](../media/SPRetention24.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-310">[ ![Configuring the flow that will trigger the event](../media/SPRetention24.png) ](../media/SPRetention24.png#lightbox)</span></span>

<span data-ttu-id="02199-311">若要创建此流，请从 SharePoint 连接器开始，并选择“**创建或修改项目时**”触发器。</span><span class="sxs-lookup"><span data-stu-id="02199-311">To create this flow, start from a SharePoint connector and select the **When an item is created or modified** trigger.</span></span> <span data-ttu-id="02199-312">指定网站地址和列表名称，</span><span class="sxs-lookup"><span data-stu-id="02199-312">Specify the site address and list name.</span></span> <span data-ttu-id="02199-313">然后根据“**投入生产**”列表栏值是否设置为“***否***”（或在条件卡中等于“*false*”）来添加条件。</span><span class="sxs-lookup"><span data-stu-id="02199-313">Then add a condition based on when the **In Production** list column value is set to ***No*** (or equal to *false* on the condition card).</span></span> <span data-ttu-id="02199-314">然后添加基于内置 HTTP 模板的操作。</span><span class="sxs-lookup"><span data-stu-id="02199-314">Then add an action based on the built-in HTTP template.</span></span> <span data-ttu-id="02199-315">使用以下部分中的值来配置 HTTP 操作。</span><span class="sxs-lookup"><span data-stu-id="02199-315">Use the values in the following section to configure the HTTP action.</span></span> <span data-ttu-id="02199-316">可从以下部分复制 **URI** 和**正文**属性值，然后将其粘贴到模板中。</span><span class="sxs-lookup"><span data-stu-id="02199-316">You can copy the values for the **URI** and **Body** properties from the following section and paste them into the template.</span></span>

- <span data-ttu-id="02199-317">**方法**：POST</span><span class="sxs-lookup"><span data-stu-id="02199-317">**Method**: POST</span></span>
- <span data-ttu-id="02199-318">**URI**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="02199-318">**URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="02199-319">**标头**：键 = Content-Type，值 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="02199-319">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="02199-320">**正文**：</span><span class="sxs-lookup"><span data-stu-id="02199-320">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'>
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
    <updated>9/9/2017 10:50:00 PM</updated>
    <content type='application/xml'>
    <m:properties>
    <d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
    <d:EventType>Product Cessation&lt;</d:EventType>
    <d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
    <d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
    </m:properties>
    </content&gt>
    </entry>
    ```

<span data-ttu-id="02199-321">此列表介绍必须专为此方案配置的操作的**正文**属性内的参数：</span><span class="sxs-lookup"><span data-stu-id="02199-321">This list describes the parameters in the **Body** property of the action that must be configured for this scenario:</span></span>

- <span data-ttu-id="02199-322">**名称**：此参数指定将在 Microsoft 365 合规中心内创建的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="02199-322">**Name**: This parameter specifies the name of the event that will be created in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="02199-323">对于此方案，名称为“产品停产 *xxx*”，其中 *xxx* 是我们之前创建的 **ProductName** 托管属性的值。</span><span class="sxs-lookup"><span data-stu-id="02199-323">For this scenario, the name is "Cessation Production *xxx*", where *xxx* is the value of the **ProductName** managed property that we created earlier.</span></span>
- <span data-ttu-id="02199-324">**EventType**：此参数的数值与将应用已创建事件的事件类型对应。</span><span class="sxs-lookup"><span data-stu-id="02199-324">**EventType**: The value for this parameter corresponds to the event type that the created event will apply to.</span></span> <span data-ttu-id="02199-325">此事件类型是在创建保留标签时定义的。</span><span class="sxs-lookup"><span data-stu-id="02199-325">This event type was defined when you created the retention label.</span></span> <span data-ttu-id="02199-326">对于此方案，事件类型为“产品停产”。</span><span class="sxs-lookup"><span data-stu-id="02199-326">For this scenario, the event type is "Product Cessation."</span></span>
- <span data-ttu-id="02199-327">**SharePointAssetIdQuery**：此参数定义事件的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="02199-327">**SharePointAssetIdQuery**: This parameter defines the asset ID for the event.</span></span> <span data-ttu-id="02199-328">基于事件的保留需要文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="02199-328">Event-based retention needs a unique identifier for the document.</span></span> <span data-ttu-id="02199-329">我们可以使用资产 ID 来标识特定事件适用的文档，或者像此方案一样，使用元数据栏 **Product Name** 进行标识。</span><span class="sxs-lookup"><span data-stu-id="02199-329">We can use asset IDs to identify the documents that a particular event applies to or, as in this scenario, the metadata column **Product Name**.</span></span> <span data-ttu-id="02199-330">为此，我们需要创建一个名为 **ProductName** 的新托管属性，可在 KQL 查询中使用该属性。</span><span class="sxs-lookup"><span data-stu-id="02199-330">To do  this, we need to create a new **ProductName** managed property that can be used in the KQL query.</span></span> <span data-ttu-id="02199-331">（或者，我们可以使用 **RefinableString00**，而不是创建新的托管属性）。</span><span class="sxs-lookup"><span data-stu-id="02199-331">(Alternatively, we could use **RefinableString00** instead of creating a new managed property).</span></span> <span data-ttu-id="02199-332">我们还需要将此新托管属性映射到 **ows_Product_x0020_Name** 已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-332">We also need to map this new managed property to the **ows_Product_x0020_Name** crawled property.</span></span> <span data-ttu-id="02199-333">下面是此托管属性的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="02199-333">Here's a screenshot of this managed property.</span></span>

    <span data-ttu-id="02199-334">[![保留托管属性](../media/SPRetention25.png)](../media/SPRetention25.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-334">[ ![Rentention managed property](../media/SPRetention25.png) ](../media/SPRetention25.png#lightbox)</span></span>

- <span data-ttu-id="02199-335">**EventDateTime**：此参数定义事件发生的日期。</span><span class="sxs-lookup"><span data-stu-id="02199-335">**EventDateTime**: This parameter defines the date that the event occurs.</span></span> <span data-ttu-id="02199-336">使用当前日期格式：</span><span class="sxs-lookup"><span data-stu-id="02199-336">Use the current date format:</span></span><br/><br/><span data-ttu-id="02199-337">*formatDateTime(utcNow(),'yyyy-MM-dd'*)</span><span class="sxs-lookup"><span data-stu-id="02199-337">*formatDateTime(utcNow(),'yyyy-MM-dd'*)</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="02199-338">汇总</span><span class="sxs-lookup"><span data-stu-id="02199-338">Putting it all together</span></span>

<span data-ttu-id="02199-339">现在，已创建并自动应用保留标签，并且已创建并配置流。</span><span class="sxs-lookup"><span data-stu-id="02199-339">Now the retention label is created and auto-applied, and the flow is configured and created.</span></span> <span data-ttu-id="02199-340">当产品列表中旋转小组件产品的“**投入生产**”栏中的值从“***是***”更改为“***否***”时，会触发该流程以创建事件。</span><span class="sxs-lookup"><span data-stu-id="02199-340">When the value in the **In Production** column for the Spinning Widget product in the Products list is changed from ***Yes*** to ***No***, the flow is triggered to create the event.</span></span> <span data-ttu-id="02199-341">若要在合规中心内查看此事件，请转到“**记录管理**” > “**事件**”。</span><span class="sxs-lookup"><span data-stu-id="02199-341">To see this event in the compliance center, go to **Records management** > **Events**.</span></span>

<span data-ttu-id="02199-342">[![流程触发的事件显示在合规中心的“事件”页面上。](../media/SPRetention28.png)](../media/SPRetention28.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-342">[ ![The event that was triggered by the flow is displayed on the Events page in the compliance center.](../media/SPRetention28.png) ](../media/SPRetention28.png#lightbox)</span></span>

<span data-ttu-id="02199-343">选择事件以查看弹出页面上的详细信息。</span><span class="sxs-lookup"><span data-stu-id="02199-343">Select the event to view the details on the flyout page.</span></span> <span data-ttu-id="02199-344">请注意，即使已创建事件，事件状态仍显示未处理任何 SharePoint 网站或文档。</span><span class="sxs-lookup"><span data-stu-id="02199-344">Notice that even though the event is created, the event status shows that no SharePoint sites or documents have been processed.</span></span>

![事件详情](../media/SPRetention29.png)

<span data-ttu-id="02199-346">但一段时间后，“事件状态”将显示已处理 SharePoint 网站和 SharePoint 文档。</span><span class="sxs-lookup"><span data-stu-id="02199-346">But after a delay, the event status shows that a SharePoint site and a SharePoint document have been processed.</span></span>  

![事件详情显示文档已处理。](../media/SPRetention31.png)
 
<span data-ttu-id="02199-348">它显示根据*旋转小组件产品停产*事件的事件日期，已触发应用于旋转小组件产品文档的标签的保留期。</span><span class="sxs-lookup"><span data-stu-id="02199-348">This shows that the retention period for the label applied to the Spinning Widget product document has been initiated, based on the event date of the *Cessation Production Spinning Widget* event.</span></span> <span data-ttu-id="02199-349">假设你通过配置一天的保留期在测试环境中实施了该方案，则可以在创建事件后的几天内转到产品文档的文档库，并验证该文档是否已被删除（在运行 SharePoint 中的删除作业之后）。</span><span class="sxs-lookup"><span data-stu-id="02199-349">Assuming that you implemented the scenario in your test environment by configuring a one-day retention period, you can go to the document library for your product documents a few days after the event was created and verify that the document was deleted (after the deletion job in SharePoint has run).</span></span>

### <a name="more-about-asset-ids"></a><span data-ttu-id="02199-350">有关资产 ID 的详细信息</span><span class="sxs-lookup"><span data-stu-id="02199-350">More about asset IDs</span></span>

<span data-ttu-id="02199-351">正如[从事件发生时开始计算保留期](event-driven-retention.md)一文中所述，理解事件类型、保留标签、事件和资产 ID 之间的关系非常重要。</span><span class="sxs-lookup"><span data-stu-id="02199-351">As the [Start retention when an event occurs](event-driven-retention.md) article explains, it's important to understand the relationship between event types, retention labels, events, and asset IDs.</span></span> <span data-ttu-id="02199-352">资产 ID 只是 SharePoint 和 OneDrive 中的一种文档属性。</span><span class="sxs-lookup"><span data-stu-id="02199-352">The asset ID is simply a document property in SharePoint and OneDrive.</span></span> <span data-ttu-id="02199-353">它可以帮助你标识将由事件触发其保留期的文档。</span><span class="sxs-lookup"><span data-stu-id="02199-353">It helps you identify the documents whose retention period will be triggered by the event.</span></span> <span data-ttu-id="02199-354">默认情况下，SharePoint 具有一个**资产 ID** 属性，你可以将其用于事件驱动的保留：</span><span class="sxs-lookup"><span data-stu-id="02199-354">By default, SharePoint has an **Asset Id** property that you can use for event-driven retention:</span></span>

![资产 ID 属性显示在文档属性详细信息页面。](../media/SPRetention26.png)

<span data-ttu-id="02199-356">如以下屏幕截图所示，资产 ID 托管属性称为 **ComplianceAssetId**。</span><span class="sxs-lookup"><span data-stu-id="02199-356">As the following screenshot shows, the asset ID managed property is called **ComplianceAssetId**.</span></span>

<span data-ttu-id="02199-357">[![ComplianceAssetId 托管属性](../media/SPRetention27.png)](../media/SPRetention27.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02199-357">[ ![ComplianceAssetId managed property](../media/SPRetention27.png) ](../media/SPRetention27.png#lightbox)</span></span>

<span data-ttu-id="02199-358">像此方案一样，你也可以使用任何其他属性，而不是使用默认**资产 ID** 属性。</span><span class="sxs-lookup"><span data-stu-id="02199-358">Instead of using the default **Asset Id** property as we do in this scenario, you can use any other property.</span></span> <span data-ttu-id="02199-359">但是，请务必了解，如果没有为事件指定资产 ID 或关键字，则具有该事件类型标签的所有内容均由该事件触发保留期。</span><span class="sxs-lookup"><span data-stu-id="02199-359">But it's important to understand that if you don't specify an asset ID or keywords for an event, all the content that has a label of that event type will get its retention period triggered by the event.</span></span>

### <a name="using-advanced-search-in-sharepoint"></a><span data-ttu-id="02199-360">在 SharePoint 中使用高级搜索</span><span class="sxs-lookup"><span data-stu-id="02199-360">Using advanced search in SharePoint</span></span>

<span data-ttu-id="02199-361">在前一屏幕截图中，还可以看到有另一个与保留标签相关的托管属性，它称为 **ComplianceTag** 并且已映射到已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-361">In the previous screenshot, you can see that there's another managed property related to retention labels called **ComplianceTag** that's mapped to a crawled property.</span></span> <span data-ttu-id="02199-362">**ComplianceAssetId** 托管属性也已映射到已爬网属性。</span><span class="sxs-lookup"><span data-stu-id="02199-362">The **ComplianceAssetId** managed property is also mapped to a crawled property.</span></span> <span data-ttu-id="02199-363">这意味着可在高级搜索中使用这些托管属性来检索已应用保留标签的所有文档。</span><span class="sxs-lookup"><span data-stu-id="02199-363">This means that you can use these managed properties in advanced search to retrieve all documents that have been tagged with a retention label.</span></span>
