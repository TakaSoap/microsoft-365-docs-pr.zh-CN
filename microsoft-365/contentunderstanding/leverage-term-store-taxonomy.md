---
title: 创建提取器时利用术语库分类
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
description: 使用 SharePoint Syntex 在文档理解模型中创建提取器时，请使用术语库分类。
ms.openlocfilehash: aff2df6a96fdfee7380651f68e647019e9485658
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975735"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="cf569-103">创建提取器时利用术语库分类</span><span class="sxs-lookup"><span data-stu-id="cf569-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="cf569-104">使用 SharePoint Syntex 在文档理解模型中创建提取器时，可利用 [术语库](https://docs.microsoft.com/sharepoint/managed-metadata) 中的全局性术语集显示提取数据的首选术语。</span><span class="sxs-lookup"><span data-stu-id="cf569-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](https://docs.microsoft.com/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="cf569-105">例如，你的模型标识并分类上传到文档库的所有 **合同** 文档。</span><span class="sxs-lookup"><span data-stu-id="cf569-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="cf569-106">此外，该模型还会提取每个合同中的 **合同服务** 值，并将其显示在库视图中的一列中。</span><span class="sxs-lookup"><span data-stu-id="cf569-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="cf569-107">在合同中的各种合同服务值之间，有一些你的公司不再使用且已重命名了的旧值。</span><span class="sxs-lookup"><span data-stu-id="cf569-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="cf569-108">例如，对术语 *Design*、*Graphics* 或 *Topography* 合同服务的所有引用现在都应称为 *创意*。</span><span class="sxs-lookup"><span data-stu-id="cf569-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="cf569-109">每当你的模型提取合同文档中的某个过时字词时，你都希望它在你的库视图中显示当前术语“Creative ”。</span><span class="sxs-lookup"><span data-stu-id="cf569-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="cf569-110">在下面的示例中，对模型进行训练时，我们看到的是一个示例文档，其中包含已过时的 *Design* 条款。</span><span class="sxs-lookup"><span data-stu-id="cf569-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![术语库](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="cf569-112">在提取器使用托管元数据列</span><span class="sxs-lookup"><span data-stu-id="cf569-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="cf569-113">在 SharePoint 管理中心的托管元数据服务术语库中配置术语集。</span><span class="sxs-lookup"><span data-stu-id="cf569-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="cf569-114">在下面的示例中，“*合同服务*”[术语集](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)被配置为包含多个术语，包括“*创意*”。</span><span class="sxs-lookup"><span data-stu-id="cf569-114">In the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include several terms, including *Creative*.</span></span>  <span data-ttu-id="cf569-115">它的详细信息显示该术语有三个同义词（*Design*、*Graphics* 和 *Topography*），并且同义词应翻译为 *创意*。</span><span class="sxs-lookup"><span data-stu-id="cf569-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![术语集](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="cf569-117">在术语集中使用同义词的原因可能有很多。</span><span class="sxs-lookup"><span data-stu-id="cf569-117">There could be many reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="cf569-118">例如，组织部门的命名中可能存在已过时的术语、已重命名的术语或差异。</span><span class="sxs-lookup"><span data-stu-id="cf569-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="cf569-119">若要确保在模型中创建提取器时托管元数据字段可供选择，需要[将其添加为托管元数据网站列](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)。</span><span class="sxs-lookup"><span data-stu-id="cf569-119">To make the managed metadata field available to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="cf569-120">添加该网站列后，便可以在为模型创建提取器时选择该字段。</span><span class="sxs-lookup"><span data-stu-id="cf569-120">After you add the site column, you can select it when you create the extractor for your model.</span></span>

   ![合同服务](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="cf569-122">将模型应用到文档库之后，将文档上传到库中时，当提取器发现任意同义词值（*Design*、*Graphics* 和 *Topography*）时，*创意服务* 列将显示首选术语（*创意*）。</span><span class="sxs-lookup"><span data-stu-id="cf569-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![合同服务列](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="cf569-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf569-124">See Also</span></span>
[<span data-ttu-id="cf569-125">托管元数据简介</span><span class="sxs-lookup"><span data-stu-id="cf569-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="cf569-126">创建提取器</span><span class="sxs-lookup"><span data-stu-id="cf569-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="cf569-127">创建托管元数据列</span><span class="sxs-lookup"><span data-stu-id="cf569-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





