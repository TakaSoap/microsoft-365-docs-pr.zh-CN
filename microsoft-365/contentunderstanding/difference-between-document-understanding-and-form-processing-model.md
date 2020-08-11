---
title: '文档理解和表单处理模型之间的差异 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 描述文档理解和表单处理模型之间的关键差异。
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612734"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="edf3a-103">文档理解和表单处理模型之间的差异 (预览) </span><span class="sxs-lookup"><span data-stu-id="edf3a-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="edf3a-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="edf3a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="edf3a-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="edf3a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="edf3a-106">通过项目 Cortex 中的内容理解，可以识别和分类上载到 SharePoint 文档库的文档，以及提取每个文件中的相关信息。</span><span class="sxs-lookup"><span data-stu-id="edf3a-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="edf3a-107">例如，在将文件上载到 SharePoint 文档库时，标识为*采购订单*的所有文件都将按此方式分类，并显示在显示它们的自定义文档库视图中。</span><span class="sxs-lookup"><span data-stu-id="edf3a-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="edf3a-108">此外，还可以从每个文件中提取特定信息 (例如， *PO 编号*和*总计*) 并将其显示在文档库视图中的列中。</span><span class="sxs-lookup"><span data-stu-id="edf3a-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="edf3a-109">内容理解使您能够创建*模型*以标识和提取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="edf3a-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="edf3a-110">可以使用以下两种类型的模型：</span><span class="sxs-lookup"><span data-stu-id="edf3a-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="edf3a-111">文档理解模型</span><span class="sxs-lookup"><span data-stu-id="edf3a-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="edf3a-112">表单处理模型</span><span class="sxs-lookup"><span data-stu-id="edf3a-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="edf3a-113">虽然这两种模型通常用于相同目的，但有一些主要差异会影响您可以选择使用的那些模型。</span><span class="sxs-lookup"><span data-stu-id="edf3a-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="edf3a-114">结构化与非结构化和半结构化内容</span><span class="sxs-lookup"><span data-stu-id="edf3a-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="edf3a-115">使用文档理解模型标识并提取非结构化文档（如信函或合同）中的数据，其中要提取的文本实体位于文档的句子或特定区域中。</span><span class="sxs-lookup"><span data-stu-id="edf3a-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="edf3a-116">例如，非结构化文档可以是以不同方式编写的合同续订信函。</span><span class="sxs-lookup"><span data-stu-id="edf3a-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="edf3a-117">但是，每个合同续订文档的正文中都存在一致的信息，例如文本字符串 "服务开始日期"，后跟实际日期。</span><span class="sxs-lookup"><span data-stu-id="edf3a-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="edf3a-118">使用表单处理模型来标识文件，并从结构化或半结构化文档（如窗体或发票）中提取数据，其中包含清楚的键值 (对，例如，*日期： 10/1/2020*) \* 或表数据。</span><span class="sxs-lookup"><span data-stu-id="edf3a-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="edf3a-119">例如，表单处理的一个好候选人是公司的订单请求表单，客户端需要为位于文档布局相同区域（如*姓名*、*电话号码*、*总成本*等）中的特定字段提供信息。 "税种" 表单是结构化文档的一个很有用的示例。</span><span class="sxs-lookup"><span data-stu-id="edf3a-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="edf3a-120">创建位置</span><span class="sxs-lookup"><span data-stu-id="edf3a-120">Where they are created</span></span>

<span data-ttu-id="edf3a-121">文档理解模型是在 SharePoint 内容中心网站中创建和管理的。</span><span class="sxs-lookup"><span data-stu-id="edf3a-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="edf3a-122">您必须具有对内容中心网站的访问权限，才能创建文档理解模型或将其应用到 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="edf3a-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="edf3a-123">创建文档理解模型时，将创建一个新的[sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，该类型将保存到 Sharepoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="edf3a-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="edf3a-124">如果需要，您可以选择使用现有内容类型来定义模型。</span><span class="sxs-lookup"><span data-stu-id="edf3a-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="edf3a-125">表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库启动的。</span><span class="sxs-lookup"><span data-stu-id="edf3a-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="edf3a-126">需要在文档库中启用表单处理模型创建，以便用户为其创建表单处理模型，并且管理员可以在内容理解管理设置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="edf3a-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="edf3a-127">表单处理模型使用 PowerAutomate 流在文件上传到文档库时处理文件。</span><span class="sxs-lookup"><span data-stu-id="edf3a-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="edf3a-128">表单处理模型还会创建新的[sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，这些类型也存储在 Sharepoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="edf3a-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="edf3a-129">可以在何处应用它们</span><span class="sxs-lookup"><span data-stu-id="edf3a-129">Where they can be applied</span></span>

<span data-ttu-id="edf3a-130">文档理解模型可应用于您有权访问的不同 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="edf3a-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="edf3a-131">您可以使用内容中心不仅创建文档理解模型，还可以将其应用于不同的文档库。</span><span class="sxs-lookup"><span data-stu-id="edf3a-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="edf3a-132">内容中心提供了对文档理解模型的使用方式和应用位置的更大的集中控制，因为此信息必须汇总到内容中心。</span><span class="sxs-lookup"><span data-stu-id="edf3a-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="edf3a-133">表单处理模型目前只能应用于从中创建它们的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="edf3a-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="edf3a-134">这将允许任何有权访问该网站的授权用户创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="edf3a-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="edf3a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edf3a-135">See Also</span></span>
[<span data-ttu-id="edf3a-136">培训：使用 AI 生成器改进业务绩效</span><span class="sxs-lookup"><span data-stu-id="edf3a-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="edf3a-137">创建类元</span><span class="sxs-lookup"><span data-stu-id="edf3a-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="edf3a-138">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="edf3a-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="edf3a-139">应用文档理解模型</span><span class="sxs-lookup"><span data-stu-id="edf3a-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="edf3a-140">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="edf3a-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



