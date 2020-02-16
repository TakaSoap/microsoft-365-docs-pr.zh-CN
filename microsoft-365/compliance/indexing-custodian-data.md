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
description: 将管理员添加到高级电子数据展示事例时，将会重新处理 Office 365 中被视为部分索引的任何内容，以使其完全可搜索。
ms.openlocfilehash: 3c1bead5f853a39410a6a018f170ee637dfcf84e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072889"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="d3e83-103">保管人数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="d3e83-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="d3e83-104">将管理员添加到高级电子数据展示事例时，将会重新处理 Office 365 中被视为部分索引的任何内容，以使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="d3e83-104">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="d3e83-105">此过程称为 "*高级索引*"。</span><span class="sxs-lookup"><span data-stu-id="d3e83-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="d3e83-106">可以对内容进行部分索引，其中包括图像存在、不受支持的文件类型或在遇到索引文件大小限制时的原因。</span><span class="sxs-lookup"><span data-stu-id="d3e83-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="d3e83-107">若要了解有关 Office 365 中的处理支持和部分索引项目的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d3e83-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="d3e83-108">高级电子数据展示中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="d3e83-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="d3e83-109">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="d3e83-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="d3e83-110">由 Exchange 搜索编制索引的文件格式</span><span class="sxs-lookup"><span data-stu-id="d3e83-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="d3e83-111">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="d3e83-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="d3e83-112">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="d3e83-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="d3e83-113">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="d3e83-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="d3e83-114">在事例的 "**处理**" 选项卡上的 "高级索引结果" 视图中，图表列出了添加到*混合索引*中的项目数。</span><span class="sxs-lookup"><span data-stu-id="d3e83-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="d3e83-115">混合索引是指高级电子数据展示将重新处理的内容存储在其中。</span><span class="sxs-lookup"><span data-stu-id="d3e83-115">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="d3e83-116">此视图还包括需要修正的项目数，以及按文件类型显示的错误的另一个图形。</span><span class="sxs-lookup"><span data-stu-id="d3e83-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="d3e83-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="d3e83-117">For more information, see:</span></span>

- [<span data-ttu-id="d3e83-118">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="d3e83-118">Error remediation when processing data</span></span>](error-remediation.md)

- [<span data-ttu-id="d3e83-119">单个项目错误更正</span><span class="sxs-lookup"><span data-stu-id="d3e83-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="d3e83-120">更新保管人的高级索引</span><span class="sxs-lookup"><span data-stu-id="d3e83-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="d3e83-121">将管理员添加到高级电子数据展示事例中时，将重新处理所有部分索引项。</span><span class="sxs-lookup"><span data-stu-id="d3e83-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="d3e83-122">但是，随着时间的推移，可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="d3e83-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="d3e83-123">如有必要，可以为特定的保管人更新索引。</span><span class="sxs-lookup"><span data-stu-id="d3e83-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="d3e83-124">有关详细信息，请参阅[在高级电子数据展示事例中管理保管人](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="d3e83-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="d3e83-125">您还可以通过单击 "**处理**" 选项卡上的 "更新"**索引**来更新事例中所有保管人的索引。</span><span class="sxs-lookup"><span data-stu-id="d3e83-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="d3e83-126">更新保管人索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="d3e83-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="d3e83-127">建议您在一种情况下每日更新索引不超过一次。</span><span class="sxs-lookup"><span data-stu-id="d3e83-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
