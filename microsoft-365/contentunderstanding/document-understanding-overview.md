---
title: 文档理解概述（预览）
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 获取有关项目 Cortex 中的文档理解的概述。
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536933"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="67dec-103">文档理解概述（预览）</span><span class="sxs-lookup"><span data-stu-id="67dec-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="67dec-104">Project Cortex 当前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="67dec-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="67dec-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="67dec-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="67dec-106">文档理解使用 AI 模型自动对文件分类和提取信息。</span><span class="sxs-lookup"><span data-stu-id="67dec-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="67dec-107">它最适用于非结构化文档，如信函或合同。</span><span class="sxs-lookup"><span data-stu-id="67dec-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="67dec-108">文档应具有可根据短语或模式进行标识的文本。</span><span class="sxs-lookup"><span data-stu-id="67dec-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="67dec-109">标识的文本既可以指定它的文件类型（它的分类），也可以指定要提取的内容（其提取程序）。</span><span class="sxs-lookup"><span data-stu-id="67dec-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="67dec-110">文档理解模型在一种称为内容中心的 SharePoint 网站中创建和管理。</span><span class="sxs-lookup"><span data-stu-id="67dec-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="67dec-111">当应用于 SharePoint 文档库时，模型与包含存储提取信息的列的内容类型相关联。</span><span class="sxs-lookup"><span data-stu-id="67dec-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="67dec-112">您创建的内容类型存储在 SharePoint 内容类型库中。</span><span class="sxs-lookup"><span data-stu-id="67dec-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="67dec-113">您还可以选择使用现有的内容类型，以便使用其架构。</span><span class="sxs-lookup"><span data-stu-id="67dec-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="67dec-114">您可以将*分类*器和*提取程序*添加到文档理解模型中，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67dec-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="67dec-115">分类器用于标识和分类上载到文档库的文档。</span><span class="sxs-lookup"><span data-stu-id="67dec-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="67dec-116">例如，可以 "训练有素" 分类器来识别上载到库中的所有*合同续订*文档。</span><span class="sxs-lookup"><span data-stu-id="67dec-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="67dec-117">创建分类器时，将会定义合同续订内容类型。</span><span class="sxs-lookup"><span data-stu-id="67dec-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="67dec-118">提取程序从这些文档中提取信息。</span><span class="sxs-lookup"><span data-stu-id="67dec-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="67dec-119">例如，对于您的文档库中标识的所有合同续订文档，列将显示在您的视图中，这些文档还将显示每个合同续订文档的*服务开始日期*和*客户端*。</span><span class="sxs-lookup"><span data-stu-id="67dec-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="67dec-120">您可以使用示例文件来培训和测试模型中的分类和提取程序。</span><span class="sxs-lookup"><span data-stu-id="67dec-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="67dec-121">示例文件提供了在尝试标识文件中的数据并从中提取数据时要查找的内容的模型示例。</span><span class="sxs-lookup"><span data-stu-id="67dec-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="67dec-122">例如，您需要使用贵公司使用的合同续订文档的示例来培训合同续订分类和提取程序。</span><span class="sxs-lookup"><span data-stu-id="67dec-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="67dec-123">您还可以使用示例文件来测试模型的有效性。</span><span class="sxs-lookup"><span data-stu-id="67dec-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="67dec-124">发布模型后，使用内容中心将其应用于您有权访问的任何 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="67dec-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="67dec-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67dec-125">See Also</span></span>
[<span data-ttu-id="67dec-126">创建类元</span><span class="sxs-lookup"><span data-stu-id="67dec-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="67dec-127">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="67dec-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="67dec-128">[创建内容中心](create-a-content-center.md) 
[创建表单处理模型](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="67dec-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="67dec-129">[应用模型](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="67dec-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="67dec-130">文档理解与表单处理模型之间的区别</span><span class="sxs-lookup"><span data-stu-id="67dec-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="67dec-131">表单处理概述</span><span class="sxs-lookup"><span data-stu-id="67dec-131">Form processing overview</span></span>](form-processing-overview.md)




