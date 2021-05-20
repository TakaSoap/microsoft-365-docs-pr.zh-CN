---
title: 预览电子数据展示搜索结果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 预览 Microsoft 365 合规中心中内容搜索或核心电子数据展示搜索返回的结果示例。
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538578"
---
# <a name="preview-ediscovery-search-results"></a><span data-ttu-id="e645c-103">预览电子数据展示搜索结果</span><span class="sxs-lookup"><span data-stu-id="e645c-103">Preview eDiscovery search results</span></span>

<span data-ttu-id="e645c-104">运行内容搜索或与核心电子数据展示案例关联的搜索后，可以预览搜索返回的结果示例。</span><span class="sxs-lookup"><span data-stu-id="e645c-104">After you run a Content search or a search associated with a Core eDiscovery case, you can preview a sample of the results returned by the search.</span></span> <span data-ttu-id="e645c-105">预览由搜索查询返回的项目可以帮助你确定搜索是否返回希望的结果，或者是否需要更改搜索查询并重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="e645c-105">Previewing items returned by the search query can help you determine if the search is returning the results you hope for or if you need to change the search query and rerun the search.</span></span>

<span data-ttu-id="e645c-106">预览由搜索返回的结果示例：</span><span class="sxs-lookup"><span data-stu-id="e645c-106">To preview a sample of results returned by a search:</span></span>

1. <span data-ttu-id="e645c-107">在 Microsoft 365 合规中心，转到内容搜索页面或核心电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="e645c-107">In the Microsoft 365 compliance center, go to the Content search page or a Core eDiscovery case.</span></span>

2. <span data-ttu-id="e645c-108">选择搜索以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="e645c-108">Select search to display the flyout page.</span></span>

3. <span data-ttu-id="e645c-109">在飞出页的底部，单击 **审阅示例**。</span><span class="sxs-lookup"><span data-stu-id="e645c-109">On the bottom of the flyout page, click **Review sample**.</span></span>

   ![单击飞出页面上的“审阅示例”来预览结果](../media/PreviewSearchResults1.png)

   <span data-ttu-id="e645c-111">将显示一个包含搜索结果示例的页面。</span><span class="sxs-lookup"><span data-stu-id="e645c-111">A page is displayed containing a sample of the search results.</span></span>

4. <span data-ttu-id="e645c-112">选择一个项以在阅读窗格中查看其内容。</span><span class="sxs-lookup"><span data-stu-id="e645c-112">Select an item to view its contents in the reading pane.</span></span>

   ![在阅读窗格中预览这些项。](../media/PreviewSearchResults2.png)

   <span data-ttu-id="e645c-114">在上一个屏幕截图中，请注意，预览项目时，将突出显示搜索查询中的关键字。</span><span class="sxs-lookup"><span data-stu-id="e645c-114">In the previous screenshot, notice that keywords from the search query are highlighted when you preview items.</span></span>

## <a name="how-the-search-result-samples-are-selected"></a><span data-ttu-id="e645c-115">如何选择搜索结果示例</span><span class="sxs-lookup"><span data-stu-id="e645c-115">How the search result samples are selected</span></span>

<span data-ttu-id="e645c-116">最多有 1,000 个随机选择的项目可供预览。</span><span class="sxs-lookup"><span data-stu-id="e645c-116">A maximum of 1,000 randomly selected items are available to preview.</span></span> <span data-ttu-id="e645c-117">除随机选择外，可供预览的项目还必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="e645c-117">In addition to being randomly selected, items available for preview must also meet the following criteria:</span></span>

- <span data-ttu-id="e645c-118">最多可预览单个内容位置（邮箱或网站）的 100 个项目。</span><span class="sxs-lookup"><span data-stu-id="e645c-118">A maximum of 100 items from a single content location (a mailbox or a site) can be previewed.</span></span> <span data-ttu-id="e645c-119">这意味着，有可能只有不到 1,000 个项目可供预览。</span><span class="sxs-lookup"><span data-stu-id="e645c-119">This means that it's possible that less than 1,000 items might be available for preview.</span></span> <span data-ttu-id="e645c-120">例如，如果搜索 4 个邮箱，搜索返回 1,500 个估计项目，则只有 400 个可用于预览，因为每个邮箱只能预览 100 个项目。</span><span class="sxs-lookup"><span data-stu-id="e645c-120">For example, if you search four mailboxes and the search returns 1,500 estimated items, only 400 will be available for preview because only 100 items from each mailbox can be previewed.</span></span>

- <span data-ttu-id="e645c-121">对于邮箱项目，只有电子邮件信息可供预览。</span><span class="sxs-lookup"><span data-stu-id="e645c-121">For mailbox items, only email messages are available to preview.</span></span> <span data-ttu-id="e645c-122">无法预览任务、日历项目和联系人等项目。</span><span class="sxs-lookup"><span data-stu-id="e645c-122">Items like tasks, calendar items, and contacts can't be previewed.</span></span>

- <span data-ttu-id="e645c-123">对于网站项目，仅文档可供预览。</span><span class="sxs-lookup"><span data-stu-id="e645c-123">For site items, only documents are available to preview.</span></span> <span data-ttu-id="e645c-124">无法预览文件夹、列表或列表附件等项目。</span><span class="sxs-lookup"><span data-stu-id="e645c-124">Items like folders, lists, or list attachments can't be previewed.</span></span>

## <a name="file-types-supported-when-previewing-search-results"></a><span data-ttu-id="e645c-125">预览搜索结果时支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="e645c-125">File types supported when previewing search results</span></span>

<span data-ttu-id="e645c-126">可以在预览窗格中预览受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="e645c-126">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="e645c-127">如果文件类型不受支持，你需要将文件的副本下载到本地计算机（通过单击 **下载原始项目**）。</span><span class="sxs-lookup"><span data-stu-id="e645c-127">If a file type isn't supported, you have to download a copy of the file to your local computer (by clicking **Download original item**).</span></span> <span data-ttu-id="e645c-128">对于 .aspx Web 页面，尽管你可能没有访问该页面的权限，但该页面的 URL 将包括在内。</span><span class="sxs-lookup"><span data-stu-id="e645c-128">For .aspx Web pages, the URL for the page is included though you may not have permissions to access the page.</span></span> <span data-ttu-id="e645c-129">未编入索引的项目不提供预览。</span><span class="sxs-lookup"><span data-stu-id="e645c-129">Unindexed items aren't available for previewing.</span></span>

<span data-ttu-id="e645c-130">以下是受支持的文件类型，可以在搜索结果窗格中对其进行预览。</span><span class="sxs-lookup"><span data-stu-id="e645c-130">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="e645c-131">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="e645c-131">.txt, .html, .mhtml</span></span>

- <span data-ttu-id="e645c-132">.eml</span><span class="sxs-lookup"><span data-stu-id="e645c-132">.eml</span></span>

- <span data-ttu-id="e645c-133">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="e645c-133">.doc, .docx, .docm</span></span>

- <span data-ttu-id="e645c-134">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="e645c-134">.pptm, .pptx</span></span>

- <span data-ttu-id="e645c-135">.pdf</span><span class="sxs-lookup"><span data-stu-id="e645c-135">.pdf</span></span>

<span data-ttu-id="e645c-136">此外，还支持以下文件容器类型。</span><span class="sxs-lookup"><span data-stu-id="e645c-136">Also, the following file container types are supported.</span></span> <span data-ttu-id="e645c-137">可以在预览窗格中查看容器中的文件列表。</span><span class="sxs-lookup"><span data-stu-id="e645c-137">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="e645c-138">.zip</span><span class="sxs-lookup"><span data-stu-id="e645c-138">.zip</span></span>

- <span data-ttu-id="e645c-139">.gzip</span><span class="sxs-lookup"><span data-stu-id="e645c-139">.gzip</span></span>