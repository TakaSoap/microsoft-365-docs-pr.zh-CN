---
title: 保管人数据的高级索引
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
description: ''
ms.openlocfilehash: 5ab54e84de7434a16bdf7eb7d04fad7b9af05440
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600629"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="1919b-102">保管人数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="1919b-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="1919b-103">将管理员添加到高级电子数据展示事例时，将会重新处理 Office 365 中被视为部分索引的任何内容，以使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="1919b-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="1919b-104">此过程称为 "*高级索引*"。</span><span class="sxs-lookup"><span data-stu-id="1919b-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="1919b-105">可以对内容进行部分索引，其中包括图像存在、不受支持的文件类型或在遇到索引文件大小限制时的原因。</span><span class="sxs-lookup"><span data-stu-id="1919b-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="1919b-106">若要了解有关 Office 365 中的处理支持和部分索引项目的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1919b-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="1919b-107">高级电子数据展示中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="1919b-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="1919b-108">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="1919b-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="1919b-109">由 Exchange 搜索编制索引的文件格式</span><span class="sxs-lookup"><span data-stu-id="1919b-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="1919b-110">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="1919b-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="1919b-111">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="1919b-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="1919b-112">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="1919b-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="1919b-113">在管理员索引视图中，图形列出了添加到*混合索引*中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="1919b-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="1919b-114">混合索引是指高级电子数据展示将重新处理的内容存储在其中。</span><span class="sxs-lookup"><span data-stu-id="1919b-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="1919b-115">该图还包括需要修正的项目数，以及按文件类型列出的错误的另一个关系图。</span><span class="sxs-lookup"><span data-stu-id="1919b-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="1919b-116">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1919b-116">For more information, see:</span></span>

- [<span data-ttu-id="1919b-117">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="1919b-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="1919b-118">单个项目错误更正</span><span class="sxs-lookup"><span data-stu-id="1919b-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="1919b-119">更新保管人的高级索引</span><span class="sxs-lookup"><span data-stu-id="1919b-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="1919b-120">将管理员添加到高级电子数据展示事例中时，将重新处理所有部分索引项。</span><span class="sxs-lookup"><span data-stu-id="1919b-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="1919b-121">但是，随着时间的推移，可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="1919b-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="1919b-122">如果需要，可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="1919b-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="1919b-123">更新保管人索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="1919b-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="1919b-124">建议您在一种情况下每天不将索引更新一次以上。</span><span class="sxs-lookup"><span data-stu-id="1919b-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
