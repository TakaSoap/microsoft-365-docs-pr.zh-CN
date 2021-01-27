---
title: 文档理解与表单处理模型之间的差异
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 描述文档理解与表单处理模型之间的主要差异
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975873"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a><span data-ttu-id="6a189-103">文档理解与表单处理模型之间的差异</span><span class="sxs-lookup"><span data-stu-id="6a189-103">Difference between document understanding and form processing models</span></span> 


<span data-ttu-id="6a189-104">通过 Microsoft SharePoint Syntex 中的内容理解功能，你可以识别上传到 SharePoint 文档库的文档、对其进行分类并从每个文件中提取相关信息。</span><span class="sxs-lookup"><span data-stu-id="6a189-104">Content understanding in Microsoft SharePoint Syntex allows you to identify and classify documents that are uploaded to SharePoint document libraries, and extract relevant information from each file.</span></span>  <span data-ttu-id="6a189-105">例如，当文件上传到 SharePoint 文档库中时，所有被识别为 *采购订单* 的文件都被归类为采购订单，然后在自定义文档库视图中显示。</span><span class="sxs-lookup"><span data-stu-id="6a189-105">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such, and then displayed in a custom document library view.</span></span> <span data-ttu-id="6a189-106">此外，可从每个文件中提取特定信息（例如， *PO 编号* 和 *总数*），并将其显示为文档库视图中的一列。</span><span class="sxs-lookup"><span data-stu-id="6a189-106">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it as a column in your document library view.</span></span> 

<span data-ttu-id="6a189-107">内容理解使你能够创建 *模型* 来识别和提取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="6a189-107">Content understanding lets you create *models* to identify and extract the information you need.</span></span> <span data-ttu-id="6a189-108">模型在帮助解决搜索、业务流程、合规性等业务问题上具有价值。</span><span class="sxs-lookup"><span data-stu-id="6a189-108">Models have value in helping to resolve business issues for search, business processes, compliance, and many others.</span></span>

<span data-ttu-id="6a189-109">有两种模型类型可以使用：</span><span class="sxs-lookup"><span data-stu-id="6a189-109">There are two model types that you can use:</span></span>

- [<span data-ttu-id="6a189-110">文档理解模型 </span><span class="sxs-lookup"><span data-stu-id="6a189-110">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="6a189-111">表单处理模型</span><span class="sxs-lookup"><span data-stu-id="6a189-111">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="6a189-112">虽然这两种模型通常用于相同的用途，但下面列出的主要差异会影响你使用的区别。</span><span class="sxs-lookup"><span data-stu-id="6a189-112">While both models are generally used for the same purpose, the key differences listed below affect which ones you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="6a189-113">有关表单处理和文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采纳：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="6a189-113">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing and document understanding scenario examples.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="6a189-114">结构化内容与非结构化和半结构化内容的比较</span><span class="sxs-lookup"><span data-stu-id="6a189-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="6a189-115">使用文档理解模型从信件或合同等非结构化文档中识别和提取数据，在这些文档中，所需提取的文本实体位于文档的句子或特定区域中。</span><span class="sxs-lookup"><span data-stu-id="6a189-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract is in sentences or specific regions of the document.</span></span> <span data-ttu-id="6a189-116">例如，一个非结构化的文件可以是一份可以用不同的方式来写的续签合同书。</span><span class="sxs-lookup"><span data-stu-id="6a189-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="6a189-117">然而，每份合同续签文档的正文中都有一致的信息，例如 *服务开始日期* 的文本字符串，后是实际日期。</span><span class="sxs-lookup"><span data-stu-id="6a189-117">However, information exists consistently in the body of each contract renewal document, such as the text string *Service start date of* followed by an actual date.</span></span>

<span data-ttu-id="6a189-118">使用表单处理模型来识别文件，并从结构化或半结构化的文件（如表单或发票）中提取数据。</span><span class="sxs-lookup"><span data-stu-id="6a189-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices.</span></span> <span data-ttu-id="6a189-119">表单处理模型将通过示例文档来进行训练，从而了解表单的布局，并学会从相似的位置查找需要提取的数据。</span><span class="sxs-lookup"><span data-stu-id="6a189-119">Form processing models are trained to understand the layout of your form from example documents, and learn to look for the data you need to extract from similar locations.</span></span> <span data-ttu-id="6a189-120">表单通常具有结构化程度更高的布局，其中的实体均位于同一位置（例如，纳税表单中的社会保险号）。</span><span class="sxs-lookup"><span data-stu-id="6a189-120">Forms usually have a more structured layout where entities are in the same location (for example, a social security number in a tax form).</span></span>

> [!NOTE]
> <span data-ttu-id="6a189-121">必须有访问内容中心站点的权限，才能创建文档理解模型或将其应用于SharePoint文档库。</span><span class="sxs-lookup"><span data-stu-id="6a189-121">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 


## <a name="where-models-are-created"></a><span data-ttu-id="6a189-122">模型创建位置</span><span class="sxs-lookup"><span data-stu-id="6a189-122">Where models are created</span></span>

<span data-ttu-id="6a189-123">文档理解模型在 SharePoint 内容中心站点中创建和管理。</span><span class="sxs-lookup"><span data-stu-id="6a189-123">Document understanding models are created and managed in a SharePoint content center site.</span></span> 

> [!NOTE]
> <span data-ttu-id="6a189-124">有关输入文档的详细信息，请参阅 [表单处理模型的要求和限制](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="6a189-124">For more information about input documents, see [Form processing model requirements and limitations](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

<span data-ttu-id="6a189-125">表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建而成，但创建活动是直接从 SharePoint 文档库开始的。</span><span class="sxs-lookup"><span data-stu-id="6a189-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation starts directly from a SharePoint document library.</span></span> <span data-ttu-id="6a189-126">文档库必须启用表单处理模型创建，用户才能为其创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="6a189-126">A document library must have form processing model creation enabled before a user can create a form processing model for it.</span></span> <span data-ttu-id="6a189-127">管理员可以在内容理解管理员设置中启用表单处理模型创建。</span><span class="sxs-lookup"><span data-stu-id="6a189-127">Admins can enable form processing model creation in the content understanding admin settings.</span></span> <span data-ttu-id="6a189-128">当文件上传到文档库时，表格处理模型会使用 PowerAutomate 流来处理文件。</span><span class="sxs-lookup"><span data-stu-id="6a189-128">Form processing models use PowerAutomate flows to process files when they're uploaded to the document library.</span></span>

<span data-ttu-id="6a189-129">创建文档理解模型时，将创建一个新的 [SharePoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) 保存到 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="6a189-129">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="6a189-130">或者如果需要的话，可使用现有的内容类型来定义模型。</span><span class="sxs-lookup"><span data-stu-id="6a189-130">Or you can use existing content types to define your model if needed.</span></span>

<span data-ttu-id="6a189-131">表单处理模型还可创建新 [SharePoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，并且还存储在 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="6a189-131">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), and are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="6a189-132">可适用的地方</span><span class="sxs-lookup"><span data-stu-id="6a189-132">Where they can be applied</span></span>

<span data-ttu-id="6a189-133">可将文档理解模型应用于有权访问的 SharePoint 文档库中。</span><span class="sxs-lookup"><span data-stu-id="6a189-133">You can apply document understanding models to SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="6a189-134">使用内容中心创建文档理解模型，并将其应用于不同的文档库。</span><span class="sxs-lookup"><span data-stu-id="6a189-134">Use the content center to create a document understanding model, and apply it to different document libraries.</span></span> <span data-ttu-id="6a189-135">内容中心可以让你更集中地控制文档理解模型的使用方式和应用位置。</span><span class="sxs-lookup"><span data-stu-id="6a189-135">The content center gives you a more central control for how document understanding models are used and where they're applied.</span></span> <span data-ttu-id="6a189-136">注意，这些信息也必须滚动到内容中心。</span><span class="sxs-lookup"><span data-stu-id="6a189-136">Note this information must also roll up to a content center.</span></span>

<span data-ttu-id="6a189-137">表单处理模型目前只能应用于创建它们的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="6a189-137">Form processing models can currently only be applied to the SharePoint document library from which you created them.</span></span> <span data-ttu-id="6a189-138">这使得拥有网站访问权限的许可用户能够创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="6a189-138">This allows licensed users with access to the site to create a form processing model.</span></span> <span data-ttu-id="6a189-139">请注意，管理员需要在 SharePoint 文档库中启用表单处理功能，以便供许可用户使用。</span><span class="sxs-lookup"><span data-stu-id="6a189-139">Note that an admin needs to enable form processing on a SharePoint document library for it to be available to licensed users.</span></span>

 ## <a name="see-also"></a><span data-ttu-id="6a189-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a189-140">See Also</span></span>
[<span data-ttu-id="6a189-141">培训：使用 AI 生成器提高业务绩效</span><span class="sxs-lookup"><span data-stu-id="6a189-141">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[<span data-ttu-id="6a189-142">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="6a189-142">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="6a189-143">表单处理概述</span><span class="sxs-lookup"><span data-stu-id="6a189-143">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="6a189-144">SharePoint Syntex 简介</span><span class="sxs-lookup"><span data-stu-id="6a189-144">Introduction to SharePoint Syntex</span></span>](index.md)
