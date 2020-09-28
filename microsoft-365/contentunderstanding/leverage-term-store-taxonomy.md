---
title: 创建提取器时利用术语存储分类
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Microsoft SharePoint Syntex 中的文档理解模型中创建提取器时，利用术语库分类。
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295742"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="854ff-103">创建提取器时利用术语存储分类</span><span class="sxs-lookup"><span data-stu-id="854ff-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="854ff-104">当您在 SharePoint Syntex 中的文档理解模型中创建提取器时，可以利用 [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 术语库分类来显示您提取的数据的首选术语。</span><span class="sxs-lookup"><span data-stu-id="854ff-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="854ff-105">例如，您的模型标识并分类所有上载到文档库的 **合同** 文档。</span><span class="sxs-lookup"><span data-stu-id="854ff-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="854ff-106">此外，该模型还会从每个合同中提取 **合同服务** 值，并将其显示在库视图中的列中。</span><span class="sxs-lookup"><span data-stu-id="854ff-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="854ff-107">在合同的各种合同服务值中，您的公司不再使用且已重命名的几个旧值。</span><span class="sxs-lookup"><span data-stu-id="854ff-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="854ff-108">例如，对术语 " *设计*"、" *图形*" 或 " *拓扑* 服务" 合同服务的所有引用现在都称为 " *创造性*"。</span><span class="sxs-lookup"><span data-stu-id="854ff-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="854ff-109">只要您的模型从合同文档中提取了一个过期的术语，您就希望它在库视图中显示当前术语 "创作"。</span><span class="sxs-lookup"><span data-stu-id="854ff-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="854ff-110">在下面的示例中，在培训模型时，我们看到一个示例文档包含了已过期的 *设计*术语。</span><span class="sxs-lookup"><span data-stu-id="854ff-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![术语库](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="854ff-112">术语集同义词</span><span class="sxs-lookup"><span data-stu-id="854ff-112">Term set synonyms</span></span> 

<span data-ttu-id="854ff-113">在 SharePoint 管理中心的 Managed Metadata services 术语库中配置术语集。</span><span class="sxs-lookup"><span data-stu-id="854ff-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="854ff-114">在下面的示例中，*合同服务*[术语集](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)配置为包含许多术语，包括*创造性*。</span><span class="sxs-lookup"><span data-stu-id="854ff-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="854ff-115">它的详细信息表明，术语包含三个同义词 (*设计*、 *图形*和 *拓扑*) ，并且应将同义词转换为 *创造性*。</span><span class="sxs-lookup"><span data-stu-id="854ff-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![术语集](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="854ff-117"><Mike，我不确定如何描述此内容。</span><span class="sxs-lookup"><span data-stu-id="854ff-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="854ff-118">什么操作告诉模型当我创建提取程序以提取并显示合同服务列时，该专栏是如何 "标记" 以将 managed metadata 术语集用于创造性服务？ ></span><span class="sxs-lookup"><span data-stu-id="854ff-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="854ff-119">为托管元数据字段配置文档库网站栏</span><span class="sxs-lookup"><span data-stu-id="854ff-119">Configure your document library site column for a managed metadata field</span></span>


   ![创建托管元数据](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="854ff-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="854ff-121">See Also</span></span>
[<span data-ttu-id="854ff-122">托管元数据简介</span><span class="sxs-lookup"><span data-stu-id="854ff-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="854ff-123">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="854ff-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="854ff-124">创建托管元数据列</span><span class="sxs-lookup"><span data-stu-id="854ff-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





