---
title: 文档理解与表单处理模型之间的差异
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 描述文档理解与表单处理模型之间的主要差异
ms.openlocfilehash: 71887aeeb66699b3d756317b33d52607f480aa7d
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333868"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a><span data-ttu-id="c168e-103">文档理解与表单处理模型之间的差异</span><span class="sxs-lookup"><span data-stu-id="c168e-103">Difference between document understanding and form processing models</span></span> 


<span data-ttu-id="c168e-104">Microsoft SharePoint Syntex中的内容理解允许对上传到SharePoint文档库中的文档进行识别与分类，并从每个文件中提取相关信息。</span><span class="sxs-lookup"><span data-stu-id="c168e-104">Content understanding in Microsoft SharePoint Syntex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="c168e-105">例如，当文件上传到 SharePoint 文档库中时，所有被识别为*采购订单* 的文件都被归类为采购订单，然后在自定义文档库视图中显示。</span><span class="sxs-lookup"><span data-stu-id="c168e-105">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such, and then displayed in a custom document library view.</span></span> <span data-ttu-id="c168e-106">此外，可从每个文件中提取特定信息（例如， *PO 编号*和*总数*），并将其显示为文档库视图中的一列。</span><span class="sxs-lookup"><span data-stu-id="c168e-106">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it as a column in your document library view.</span></span> 

<span data-ttu-id="c168e-107">内容理解使你能够创建*模型*来识别和提取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c168e-107">Content understanding lets you create *models* to identify and extract the information you need.</span></span> <span data-ttu-id="c168e-108">模型在帮助解决搜索、业务流程、合规性等业务问题上具有价值。</span><span class="sxs-lookup"><span data-stu-id="c168e-108">Models have value in helping to resolve business issues for search, business processes, compliance, and many others.</span></span>

<span data-ttu-id="c168e-109">有两种模型类型可以使用：</span><span class="sxs-lookup"><span data-stu-id="c168e-109">There are two model types that you can use:</span></span>

- [<span data-ttu-id="c168e-110">文档理解模型 </span><span class="sxs-lookup"><span data-stu-id="c168e-110">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="c168e-111">表单处理模型</span><span class="sxs-lookup"><span data-stu-id="c168e-111">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="c168e-112">虽然这两种模型通常用于相同的用途，但下面列出的主要差异会影响你使用的区别。</span><span class="sxs-lookup"><span data-stu-id="c168e-112">While both models are generally used for the same purpose, the key differences listed below affect which ones you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="c168e-113">有关表单处理和文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采纳：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="c168e-113">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing and document understanding scenario examples.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="c168e-114">结构化内容与非结构化和半结构化内容的比较</span><span class="sxs-lookup"><span data-stu-id="c168e-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="c168e-115">使用文档理解模型从非结构化文档（如信件或合同）中识别和提取数据，在这些文档中，所需提取的文本实体位于句子或文档的特定区域中。</span><span class="sxs-lookup"><span data-stu-id="c168e-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="c168e-116">例如，一个非结构化的文件可以是一份可以用不同的方式来写的续签合同书。</span><span class="sxs-lookup"><span data-stu-id="c168e-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="c168e-117">然而，每份合同续签文档的正文中都有一致的信息，例如*服务开始日期*的文本字符串，后是实际日期。</span><span class="sxs-lookup"><span data-stu-id="c168e-117">However, information exists consistently in the body of each contract renewal document, such as the text string *Service start date of* followed by an actual date.</span></span>   

<span data-ttu-id="c168e-118">使用表单处理模型来识别文件，并从结构化或半结构化的文件（如表单或发票）中提取数据。</span><span class="sxs-lookup"><span data-stu-id="c168e-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices.</span></span> <span data-ttu-id="c168e-119">表单处理模型经过训练，可从示例文档中理解表单布局，并学会从类似的位置中寻找所需提取的数据，因为表单实体处于相同的位置而具有更多结构性的布局（例如，税务单中的社保号）。</span><span class="sxs-lookup"><span data-stu-id="c168e-119">Form processing models are trained to understand the layout of your form from example documents, and learn to look for the data you need to extract from  similar locations, since forms have a more structured layout where entities are in the same location (for example, a social security number in a tax form).</span></span> 

> [!NOTE]
> <span data-ttu-id="c168e-120">必须有访问内容中心站点的权限，才能创建文档理解模型或将其应用于SharePoint文档库。</span><span class="sxs-lookup"><span data-stu-id="c168e-120">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 


## <a name="where-they-are-created"></a><span data-ttu-id="c168e-121">创建地点</span><span class="sxs-lookup"><span data-stu-id="c168e-121">Where they are created</span></span>

<span data-ttu-id="c168e-122">文档理解模型在 SharePoint 内容中心站点中创建和管理。</span><span class="sxs-lookup"><span data-stu-id="c168e-122">Document understanding models are created and managed in a SharePoint content center site.</span></span> 

> [!NOTE]
> <span data-ttu-id="c168e-123">有关输入文档的详细信息，请参阅 [表单处理模型的要求和限制](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。</span><span class="sxs-lookup"><span data-stu-id="c168e-123">For more information about input documents, see [Form processing model requirements and limitations](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

<span data-ttu-id="c168e-124">表单处理模型是在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从SharePoint文档库中开始的。</span><span class="sxs-lookup"><span data-stu-id="c168e-124">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint document library.</span></span> <span data-ttu-id="c168e-125">表单处理模型的创建需要在文档库上启用，以便用户为其创建表单处理模型，管理员可以在内容理解管理员设置中进行。</span><span class="sxs-lookup"><span data-stu-id="c168e-125">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="c168e-126">当文件上传到文件库时，表格处理模型使用PowerAutomate流来处理文件。</span><span class="sxs-lookup"><span data-stu-id="c168e-126">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="c168e-127">创建文档理解模型时，将创建一个新的 [SharePoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) 保存到 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="c168e-127">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="c168e-128">或者如果需要的话，可使用现有的内容类型来定义模型。</span><span class="sxs-lookup"><span data-stu-id="c168e-128">Or you can use existing content types to define your model if needed.</span></span>

<span data-ttu-id="c168e-129">表单处理模型在 PowerApps的[AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库中开始的。</span><span class="sxs-lookup"><span data-stu-id="c168e-129">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="c168e-130">表单处理模型的创建需要在文档库上启用，用户才能为其创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="c168e-130">Form processing model creation needs to be enabled on your document library for a user to create a form processing model for it.</span></span> <span data-ttu-id="c168e-131">或者管理员可以在内容理解管理设置中进行。</span><span class="sxs-lookup"><span data-stu-id="c168e-131">Or an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="c168e-132">当文件上传到文件库时，表格处理模型使用PowerAutomate流来处理文件。</span><span class="sxs-lookup"><span data-stu-id="c168e-132">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="c168e-133">表单处理模型还可创建新 [SharePoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，并且还存储在 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="c168e-133">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), and are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="c168e-134">可适用的地方</span><span class="sxs-lookup"><span data-stu-id="c168e-134">Where they can be applied</span></span>

<span data-ttu-id="c168e-135">可将文档理解模型应用于有权访问的 SharePoint 文档库中。</span><span class="sxs-lookup"><span data-stu-id="c168e-135">You can apply document understanding models to SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="c168e-136">使用内容中心创建文档理解模型，并将其应用于不同的文档库。</span><span class="sxs-lookup"><span data-stu-id="c168e-136">Use the content center to create a document understanding model, and apply it to different document libraries.</span></span> <span data-ttu-id="c168e-137">内容中心可以让你更集中地控制文档理解模型的使用方式和应用位置。</span><span class="sxs-lookup"><span data-stu-id="c168e-137">The content center gives you a more central control for how document understanding models are used and where they are applied.</span></span> <span data-ttu-id="c168e-138">注意，这些信息也必须滚动到内容中心。</span><span class="sxs-lookup"><span data-stu-id="c168e-138">Note this information must also roll up to a content center.</span></span>

<span data-ttu-id="c168e-139">表单处理模型目前只能应用于创建它们的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="c168e-139">Form processing models can currently only be applied to the SharePoint document library from which you created them.</span></span> <span data-ttu-id="c168e-140">这使得拥有访问权限的用户能够创建表单处理模型。</span><span class="sxs-lookup"><span data-stu-id="c168e-140">This allows licensed users with access to the site to be able to create a form processing model.</span></span> <span data-ttu-id="c168e-141">请注意，管理员需要在 SharePoint 文档库中启用表单处理功能，以便供拥有许可的用户使用。</span><span class="sxs-lookup"><span data-stu-id="c168e-141">Note that your admin needs to enable form processing on a SharePoint document library for it to be available to licensed users.</span></span>

 ## <a name="see-also"></a><span data-ttu-id="c168e-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c168e-142">See Also</span></span>
[<span data-ttu-id="c168e-143">培训：使用 AI 生成器提高业务绩效</span><span class="sxs-lookup"><span data-stu-id="c168e-143">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)

[<span data-ttu-id="c168e-144">创建分类器</span><span class="sxs-lookup"><span data-stu-id="c168e-144">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c168e-145">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="c168e-145">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c168e-146">应用文档理解模型</span><span class="sxs-lookup"><span data-stu-id="c168e-146">Apply a document understanding model</span></span>](apply-a-model.md)

[<span data-ttu-id="c168e-147">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="c168e-147">Create a form processing model</span></span>](create-a-form-processing-model.md)
