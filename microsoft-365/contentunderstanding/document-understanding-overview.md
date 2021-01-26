---
title: 文档理解概述
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
description: 获取 Microsoft SharePoint Syntex 中的文档理解概述。
ms.openlocfilehash: c0396c8e702d3e32db93d26dba23ab038546bea0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976515"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="a83cf-103">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="a83cf-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="a83cf-104">文档理解使用人工智能 (AI) 模型自动对文件和提取信息进行分类。</span><span class="sxs-lookup"><span data-stu-id="a83cf-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="a83cf-105">它最适用于非结构化文档，例如字母或协定。</span><span class="sxs-lookup"><span data-stu-id="a83cf-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="a83cf-106">这些文档必须包含可以根据短语或图案进行识别的文本。</span><span class="sxs-lookup"><span data-stu-id="a83cf-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="a83cf-107">标识的文本将指定文件类型（分类）和要提取的内容（提取程序）。</span><span class="sxs-lookup"><span data-stu-id="a83cf-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="a83cf-108">有关文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采用：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)。</span><span class="sxs-lookup"><span data-stu-id="a83cf-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="a83cf-109">文档理解模型在一种称为 *内容中心* 的 SharePoint 网站中创建和管理。</span><span class="sxs-lookup"><span data-stu-id="a83cf-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="a83cf-110">应用于 SharePoint 文档库时，该模型与内容类型关联，包含用于存储所提取信息的列。</span><span class="sxs-lookup"><span data-stu-id="a83cf-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="a83cf-111">你创建的内容类型存储在 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="a83cf-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="a83cf-112">也可以选择使用现有内容类型来使用其架构。</span><span class="sxs-lookup"><span data-stu-id="a83cf-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="a83cf-113">只读或密封的内容类型无法更新，因此不能在模型中使用。</span><span class="sxs-lookup"><span data-stu-id="a83cf-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="a83cf-114">向文档理解模型添加 *分类器* 和 *提取器* 以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a83cf-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="a83cf-115">分类器用于识别上载到文档库的文档并对其进行分类。</span><span class="sxs-lookup"><span data-stu-id="a83cf-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="a83cf-116">例如，一个分类器可通过“训练有素”来标识上载到库的所有 *合同续订* 文档。</span><span class="sxs-lookup"><span data-stu-id="a83cf-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="a83cf-117">当你创建分类器时，合同续订内容类型由你定义。</span><span class="sxs-lookup"><span data-stu-id="a83cf-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="a83cf-118">提取器从这些文档提取信息。</span><span class="sxs-lookup"><span data-stu-id="a83cf-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="a83cf-119">例如，对于文档库中标识的所有合同续订文档，将在视图中显示每个合同续订文档的 *服务开始日期* 和 *客户*。</span><span class="sxs-lookup"><span data-stu-id="a83cf-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="a83cf-120">可使用示例文件在模型中培训并测试分类器和提取器。</span><span class="sxs-lookup"><span data-stu-id="a83cf-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="a83cf-121">示例文件提供了有关尝试从文件识别和提取数据时要查找的内容的模型示例。</span><span class="sxs-lookup"><span data-stu-id="a83cf-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="a83cf-122">例如，你将使用公司使用的合同续订文档的示例来训练你的合同续订分类和提取器。</span><span class="sxs-lookup"><span data-stu-id="a83cf-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="a83cf-123">还可以使用示例文件来测试模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="a83cf-123">You can also use example files to test the effectiveness of your model.</span></span>

> [!NOTE]
> <span data-ttu-id="a83cf-124">如果您使用光学字符识别（OCR）技术扫描文档，则Syntex的模型训练限制为15页。</span><span class="sxs-lookup"><span data-stu-id="a83cf-124">If you use optical character recognition (OCR) technology to scan documents, Syntex has a 15-page limit for model training.</span></span>

<span data-ttu-id="a83cf-125">发布模型后，请使用内容中心将其应用到你有权访问的任何 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="a83cf-125">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a83cf-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a83cf-126">See Also</span></span>
[<span data-ttu-id="a83cf-127">创建分类器</span><span class="sxs-lookup"><span data-stu-id="a83cf-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a83cf-128">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="a83cf-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a83cf-129">创建内容中心</span><span class="sxs-lookup"><span data-stu-id="a83cf-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="a83cf-130">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="a83cf-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="a83cf-131">应用模型</span><span class="sxs-lookup"><span data-stu-id="a83cf-131">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="a83cf-132">文档理解与表单处理模型之间的差异</span><span class="sxs-lookup"><span data-stu-id="a83cf-132">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="a83cf-133">表单处理概述</span><span class="sxs-lookup"><span data-stu-id="a83cf-133">Form processing overview</span></span>](form-processing-overview.md)
