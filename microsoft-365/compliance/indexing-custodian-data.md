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
description: 将保管人添加到高级电子数据展示案例时，会重新处理被视为部分索引的任何内容，使其完全可搜索。
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750753"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="5c407-103">保管人数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="5c407-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="5c407-104">将保管人添加到高级电子数据展示案例后，将重新处理被视为部分索引的任何内容，使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="5c407-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="5c407-105">此过程称为 *高级索引*。</span><span class="sxs-lookup"><span data-stu-id="5c407-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="5c407-106">内容可能由于多种原因（包括存在图像、不支持的文件类型或遇到索引文件大小限制）而部分编制索引。</span><span class="sxs-lookup"><span data-stu-id="5c407-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="5c407-107">若要了解有关处理支持和部分索引项的更多信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="5c407-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="5c407-108">高级电子数据展示中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="5c407-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="5c407-109">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="5c407-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="5c407-110">由 Exchange 搜索编制索引的文件格式</span><span class="sxs-lookup"><span data-stu-id="5c407-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="5c407-111">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="5c407-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="5c407-112">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="5c407-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="5c407-113">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="5c407-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="5c407-114">在案例的"处理"选项卡上的"高级索引结果"视图中，图形列出了添加到混合索引 *中的项目数*。</span><span class="sxs-lookup"><span data-stu-id="5c407-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="5c407-115">混合索引是高级电子数据展示存储重新处理的内容的位置。</span><span class="sxs-lookup"><span data-stu-id="5c407-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="5c407-116">此视图还包括需要修正的项目数和按文件类型显示的另一个错误图。</span><span class="sxs-lookup"><span data-stu-id="5c407-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="5c407-117">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="5c407-117">For more information, see:</span></span>

- [<span data-ttu-id="5c407-118">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="5c407-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="5c407-119">单个项目错误更正</span><span class="sxs-lookup"><span data-stu-id="5c407-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="5c407-120">更新保管人的高级索引</span><span class="sxs-lookup"><span data-stu-id="5c407-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="5c407-121">将保管人添加到高级电子数据展示案例时，将重新处理所有部分索引项。</span><span class="sxs-lookup"><span data-stu-id="5c407-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="5c407-122">但是，随着时间的推移，可能会向用户的邮箱或 OneDrive 帐户添加更多的部分索引项目。</span><span class="sxs-lookup"><span data-stu-id="5c407-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="5c407-123">如有必要，可以更新特定保管人索引。</span><span class="sxs-lookup"><span data-stu-id="5c407-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="5c407-124">有关详细信息，请参阅 ["管理高级电子数据展示"案例中的保管人](manage-new-custodians.md#re-index-custodian-data)。</span><span class="sxs-lookup"><span data-stu-id="5c407-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="5c407-125">您还可以通过单击"处理"选项卡上的"更新索引"来更新情况下所有保管人 **索引**。</span><span class="sxs-lookup"><span data-stu-id="5c407-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="5c407-126">更新保管人索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="5c407-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="5c407-127">建议您在一种情况下每天更新索引不要超过一次。</span><span class="sxs-lookup"><span data-stu-id="5c407-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
