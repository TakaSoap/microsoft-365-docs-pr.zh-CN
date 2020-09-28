---
title: 文档理解和表单处理模型之间的区别
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 介绍文档理解和表单处理模型之间的关键区别
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294744"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a><span data-ttu-id="71030-103">文档理解和表单处理模型之间的区别</span><span class="sxs-lookup"><span data-stu-id="71030-103">Difference between document understanding and form processing models</span></span> 

<span data-ttu-id="71030-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="71030-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="71030-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="71030-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="71030-106">通过项目 Cortex 中的内容理解，可以识别和分类上载到 SharePoint 文档库的文档，以及提取每个文件中的相关信息。</span><span class="sxs-lookup"><span data-stu-id="71030-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="71030-107">例如，在将文件上载到 SharePoint 文档库时，标识为 *采购订单* 的所有文件都按此进行分类，然后显示在自定义文档库视图中。</span><span class="sxs-lookup"><span data-stu-id="71030-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such, and then displayed in a custom document library view.</span></span> <span data-ttu-id="71030-108">此外，还可以从每个文件中提取特定信息 (例如， *PO 号* 和 *总计*) 并将其显示为文档库视图中的一列。</span><span class="sxs-lookup"><span data-stu-id="71030-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it as a column in your document library view.</span></span> 

<span data-ttu-id="71030-109">内容理解使您能够创建 *模型* 以标识和提取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="71030-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span> <span data-ttu-id="71030-110">以下是您可以使用的两种模型类型：</span><span class="sxs-lookup"><span data-stu-id="71030-110">These are two model types that you can use:</span></span>

- [<span data-ttu-id="71030-111">文档理解模型</span><span class="sxs-lookup"><span data-stu-id="71030-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="71030-112">表单处理模型</span><span class="sxs-lookup"><span data-stu-id="71030-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="71030-113">虽然这两种模型通常用于相同目的，但下面列出的主要区别将影响您可以使用的主要区别。</span><span class="sxs-lookup"><span data-stu-id="71030-113">While both models are generally used for the same purpose, the key differences listed below affect which ones you can use.</span></span>

## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="71030-114">结构化与非结构化和半结构化内容</span><span class="sxs-lookup"><span data-stu-id="71030-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="71030-115">使用文档理解模型标识并提取非结构化文档（如信函或合同）中的数据，其中要提取的文本实体位于文档的句子或特定区域中。</span><span class="sxs-lookup"><span data-stu-id="71030-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="71030-116">例如，非结构化文档可以是以不同方式编写的合同续订信函。</span><span class="sxs-lookup"><span data-stu-id="71030-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="71030-117">但是，信息在每个合同续订文档的正文中始终存在，如文本字符串 "服务开始日期"，后跟实际日期。</span><span class="sxs-lookup"><span data-stu-id="71030-117">However, information exists consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="71030-118">使用表单处理模型来标识文件，并从结构化或半结构化文档（例如表单或发票）中提取数据。</span><span class="sxs-lookup"><span data-stu-id="71030-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices.</span></span> <span data-ttu-id="71030-119">这些文档必须具有明文键值对 (例如， *Date： 10/1/2020*) \* 或 table data。</span><span class="sxs-lookup"><span data-stu-id="71030-119">These documents must have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="71030-120">例如，表单处理的一个好候选人是公司订单请求表单，客户端需要为位于文档布局相同区域（如 *姓名*、 *电话号码*、 *总成本*等）中的特定字段提供信息。 "税种" 表单是结构化文档的一个很有用的示例。</span><span class="sxs-lookup"><span data-stu-id="71030-120">As an example, a good candidate for form processing is a company's order request form that clients need to provide information for specific fields that are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="71030-121">创建位置</span><span class="sxs-lookup"><span data-stu-id="71030-121">Where they are created</span></span>

<span data-ttu-id="71030-122">文档理解模型是在 SharePoint 内容中心网站中创建和管理的。</span><span class="sxs-lookup"><span data-stu-id="71030-122">Document understanding models are created and managed in a SharePoint content center site.</span></span> 

> [!NOTE]
> <span data-ttu-id="71030-123">您必须具有对内容中心网站的访问权限，才能创建文档理解模型或将其应用到 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="71030-123">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="71030-124">表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库启动的。</span><span class="sxs-lookup"><span data-stu-id="71030-124">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint document library.</span></span> <span data-ttu-id="71030-125">需要在文档库中启用表单处理模型创建，以便用户为其创建表单处理模型，并且管理员可以在内容理解管理设置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="71030-125">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="71030-126">表单处理模型使用 PowerAutomate 流在文件上传到文档库时处理文件。</span><span class="sxs-lookup"><span data-stu-id="71030-126">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="71030-127">创建文档理解模型时，将创建一个新的 [sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) ，该类型将保存到 Sharepoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="71030-127">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="71030-128">或者，如果需要，可以使用现有内容类型来定义模型。</span><span class="sxs-lookup"><span data-stu-id="71030-128">Or you can use existing content types to define your model if needed.</span></span>

<span data-ttu-id="71030-129">表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库启动的。</span><span class="sxs-lookup"><span data-stu-id="71030-129">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="71030-130">需要在文档库中启用表单处理模型创建，用户才能为其创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="71030-130">Form processing model creation needs to be enabled on your document library for a user to create a form processing model for it.</span></span> <span data-ttu-id="71030-131">或者，管理员可以在内容理解管理设置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="71030-131">Or an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="71030-132">表单处理模型使用 PowerAutomate 流在文件上传到文档库时处理文件。</span><span class="sxs-lookup"><span data-stu-id="71030-132">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="71030-133">表单处理模型还创建新的 [sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，并且也存储在 Sharepoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="71030-133">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), and are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="71030-134">可以在何处应用它们</span><span class="sxs-lookup"><span data-stu-id="71030-134">Where they can be applied</span></span>

<span data-ttu-id="71030-135">您可以将文档理解模型应用于您有权访问的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="71030-135">You can apply document understanding models to SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="71030-136">使用内容中心创建文档理解模型，并将其应用于不同的文档库。</span><span class="sxs-lookup"><span data-stu-id="71030-136">Use the content center to create a document understanding model, and apply it to different document libraries.</span></span> <span data-ttu-id="71030-137">内容中心提供了对文档理解模型的使用及其应用位置的更多集中控制。</span><span class="sxs-lookup"><span data-stu-id="71030-137">The content center gives you a more central control for how document understanding models are used and where they are applied.</span></span> <span data-ttu-id="71030-138">注释此信息还必须汇总到内容中心。</span><span class="sxs-lookup"><span data-stu-id="71030-138">Note this information must also roll up to a content center.</span></span>

<span data-ttu-id="71030-139">表单处理模型目前只能应用于从中创建它们的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="71030-139">Form processing models can currently only be applied to the SharePoint document library from which you created them.</span></span> <span data-ttu-id="71030-140">这将允许具有网站访问权限的授权用户能够创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="71030-140">This allows licensed users with access to the site to be able to create a form processing model.</span></span>

 ## <a name="see-also"></a><span data-ttu-id="71030-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71030-141">See Also</span></span>
[<span data-ttu-id="71030-142">培训：使用 AI 生成器改进业务绩效</span><span class="sxs-lookup"><span data-stu-id="71030-142">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="71030-143">创建类元</span><span class="sxs-lookup"><span data-stu-id="71030-143">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="71030-144">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="71030-144">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="71030-145">应用文档理解模型</span><span class="sxs-lookup"><span data-stu-id="71030-145">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="71030-146">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="71030-146">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
