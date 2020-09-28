---
title: 文档理解概述
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft SharePoint Syntex 中的文档理解的概述。
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294756"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="83ae3-103">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="83ae3-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="83ae3-104">文档理解使用人工智能 (AI) 模型自动对文件和信息提取进行分类。</span><span class="sxs-lookup"><span data-stu-id="83ae3-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="83ae3-105">它最适用于非结构化文档，如信函或合同。</span><span class="sxs-lookup"><span data-stu-id="83ae3-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="83ae3-106">这些文档必须包含可根据短语或模式进行标识的文本。</span><span class="sxs-lookup"><span data-stu-id="83ae3-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="83ae3-107">标识的文本同时指定它 (其分类) 的文件类型，以及要 (其提取程序) 提取的内容。</span><span class="sxs-lookup"><span data-stu-id="83ae3-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="83ae3-108">文档理解模型在一种称为 *内容中心*的 SharePoint 网站中创建和管理。</span><span class="sxs-lookup"><span data-stu-id="83ae3-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="83ae3-109">当应用于 SharePoint 文档库时，模型与内容类型相关联的列用于存储要提取的信息。</span><span class="sxs-lookup"><span data-stu-id="83ae3-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="83ae3-110">您创建的内容类型存储在 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="83ae3-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="83ae3-111">您还可以选择使用现有内容类型来使用其架构。</span><span class="sxs-lookup"><span data-stu-id="83ae3-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="83ae3-112">向文档中添加 *分类* 器和 *提取程序* 了解模型以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83ae3-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="83ae3-113">分类器用于标识和分类上载到文档库的文档。</span><span class="sxs-lookup"><span data-stu-id="83ae3-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="83ae3-114">例如，可以 "训练有素" 分类器来识别上载到库中的所有 *合同续订* 文档。</span><span class="sxs-lookup"><span data-stu-id="83ae3-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="83ae3-115">创建分类器时，将会定义合同续订内容类型。</span><span class="sxs-lookup"><span data-stu-id="83ae3-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="83ae3-116">提取程序从这些文档中提取信息。</span><span class="sxs-lookup"><span data-stu-id="83ae3-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="83ae3-117">例如，对于您的文档库中标识的所有合同续订文档，在视图中显示的列也显示了每个合同续订文档的 *服务开始日期* 和  *客户端* 。</span><span class="sxs-lookup"><span data-stu-id="83ae3-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="83ae3-118">您可以使用示例文件在模型中培训和测试分类器和提取程序。</span><span class="sxs-lookup"><span data-stu-id="83ae3-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="83ae3-119">示例文件提供了在尝试标识文件中的数据并从中提取数据时要查找的内容的模型示例。</span><span class="sxs-lookup"><span data-stu-id="83ae3-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="83ae3-120">例如，您需要使用贵公司使用的合同续订文档的示例来培训合同续订分类和提取程序。</span><span class="sxs-lookup"><span data-stu-id="83ae3-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="83ae3-121">您还可以使用示例文件来测试模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="83ae3-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="83ae3-122">发布模型后，使用内容中心将其应用于您有权访问的任何 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="83ae3-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="83ae3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83ae3-123">See Also</span></span>
[<span data-ttu-id="83ae3-124">创建类元</span><span class="sxs-lookup"><span data-stu-id="83ae3-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="83ae3-125">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="83ae3-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="83ae3-126">[创建内容中心](create-a-content-center.md) 
[创建表单处理模型](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="83ae3-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="83ae3-127">[应用模型](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="83ae3-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="83ae3-128">文档理解与表单处理模型之间的区别</span><span class="sxs-lookup"><span data-stu-id="83ae3-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="83ae3-129">表单处理概述</span><span class="sxs-lookup"><span data-stu-id="83ae3-129">Form processing overview</span></span>](form-processing-overview.md)
