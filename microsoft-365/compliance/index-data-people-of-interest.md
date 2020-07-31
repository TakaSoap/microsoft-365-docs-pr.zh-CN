---
title: 调查数据的高级索引
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何使用高级索引以确保您的搜索能够捕获您要调查的所有数据。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6e72ec4a41d5b32ef3837e52f21836207c6f66e1
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527574"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="8bfe8-103">调查数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="8bfe8-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="8bfe8-104">可以对实时系统中的内容进行部分索引，其中包括映像的存在、不受支持的文件类型或在遇到索引文件大小限制时遇到的多种原因。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="8bfe8-105">当处理高风险数据溢出时，您需要确保您的搜索捕获了要调查的所有数据。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="8bfe8-106">当向数据调查中添加了感兴趣的人时，被视为部分索引的任何内容将重新处理，以使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span> <span data-ttu-id="8bfe8-107">此过程称为 "*高级索引*"。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="8bfe8-108">若要了解有关处理支持和部分索引项目的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="8bfe8-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="8bfe8-109">数据调查中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="8bfe8-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="8bfe8-110">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="8bfe8-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="8bfe8-111">由 Exchange 搜索编制索引的文件格式</span><span class="sxs-lookup"><span data-stu-id="8bfe8-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="8bfe8-112">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="8bfe8-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="8bfe8-113">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="8bfe8-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="8bfe8-114">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="8bfe8-115">在感兴趣的 "索引" 视图中，图形列出了添加到*混合索引*中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="8bfe8-116">混合索引是数据调查（预览）存储重新处理内容的位置。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-116">The hybrid index is where Data Investigations (Preview) stores the reprocessed content.</span></span>

<span data-ttu-id="8bfe8-117">该图还包括需要修正的项目数，以及按文件类型列出的错误的另一个关系图。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="8bfe8-118">有关详细信息，请参阅[处理数据时的错误修正](error-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="8bfe8-119">为感兴趣的人员更新高级索引</span><span class="sxs-lookup"><span data-stu-id="8bfe8-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="8bfe8-120">当向数据调查中添加了感兴趣的人时，将重新处理所有部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-120">When a person of interest is added to a data investigation, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="8bfe8-121">但是，随着时间的推移，可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="8bfe8-122">如果需要，可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="8bfe8-123">更新感兴趣的人员索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="8bfe8-124">建议在调查中每日更新索引不超过一次。</span><span class="sxs-lookup"><span data-stu-id="8bfe8-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
