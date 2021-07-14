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
description: 将保管人添加到Advanced eDiscovery案例时，任何被视为部分索引的内容将被重新处理，使其完全可搜索。
ms.openlocfilehash: f510b7e9c0fa2c5c181709c96907610066a4b1cf
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430500"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="df4d1-103">保管人数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="df4d1-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="df4d1-104">将保管人添加到Advanced eDiscovery案例时，任何被视为部分索引或具有索引错误的内容将被重新编制索引，使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="df4d1-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="df4d1-105">此重新编制索引的过程称为 *"高级索引"。*</span><span class="sxs-lookup"><span data-stu-id="df4d1-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="df4d1-106">内容部分编制索引或出现索引错误有很多原因。</span><span class="sxs-lookup"><span data-stu-id="df4d1-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="df4d1-107">这包括图像文件或文件中是否存在图像、不支持的文件类型或文件大小索引限制。</span><span class="sxs-lookup"><span data-stu-id="df4d1-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="df4d1-108">For SharePoint files， Advanced indexing runs only on items are marked as partially indexed or that have indexing errors.</span><span class="sxs-lookup"><span data-stu-id="df4d1-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="df4d1-109">在Exchange中，包含图像附件的电子邮件不会标记为部分索引或带有索引错误。</span><span class="sxs-lookup"><span data-stu-id="df4d1-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="df4d1-110">这意味着，高级索引过程不会对这些文件重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="df4d1-110">This means that those files will not be reindexed by Advanced indexing process.</span></span>

<span data-ttu-id="df4d1-111">若要详细了解处理支持和部分索引项，请参阅：</span><span class="sxs-lookup"><span data-stu-id="df4d1-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="df4d1-112">支持的文件类型Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="df4d1-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="df4d1-113">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="df4d1-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="df4d1-114">由 Exchange 搜索编制索引的文件格式</span><span class="sxs-lookup"><span data-stu-id="df4d1-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="df4d1-115">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="df4d1-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="df4d1-116">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="df4d1-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="df4d1-117">完成高级索引过程后，您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="df4d1-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="df4d1-118">在案例的"处理"选项卡上的"高级索引结果"视图中，图形列出了添加到混合索引 *中的项目数*。</span><span class="sxs-lookup"><span data-stu-id="df4d1-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="df4d1-119">混合索引是存储Advanced eDiscovery重新处理的内容的位置。</span><span class="sxs-lookup"><span data-stu-id="df4d1-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="df4d1-120">此视图还包括需要修正的项目数和按文件类型显示的另一个错误图表。</span><span class="sxs-lookup"><span data-stu-id="df4d1-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="df4d1-121">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="df4d1-121">For more information, see:</span></span>

- [<span data-ttu-id="df4d1-122">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="df4d1-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="df4d1-123">单个项目错误更正</span><span class="sxs-lookup"><span data-stu-id="df4d1-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="df4d1-124">更新保管人的高级索引</span><span class="sxs-lookup"><span data-stu-id="df4d1-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="df4d1-125">将保管人添加到一个Advanced eDiscovery案例时，将重新处理所有部分索引项。</span><span class="sxs-lookup"><span data-stu-id="df4d1-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="df4d1-126">但是，随着时间的推移，可能会将更多的部分索引项目添加到用户的邮箱或OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="df4d1-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="df4d1-127">如有必要，可以更新特定保管人索引。</span><span class="sxs-lookup"><span data-stu-id="df4d1-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="df4d1-128">有关详细信息，请参阅管理案例[的保管Advanced eDiscovery。](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="df4d1-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="df4d1-129">在一种情况下，您还可以通过单击"处理"选项卡上的 **"** 更新索引"来更新所有保管 **人** 索引。</span><span class="sxs-lookup"><span data-stu-id="df4d1-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="df4d1-130">更新保管人索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="df4d1-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="df4d1-131">建议您在一种情况下每天更新索引不要超过一次。</span><span class="sxs-lookup"><span data-stu-id="df4d1-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
