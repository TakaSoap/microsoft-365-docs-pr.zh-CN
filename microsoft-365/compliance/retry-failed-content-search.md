---
title: 重试内容搜索以解决内容位置错误
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在调查过程中，可以使用 "重试" 按钮来解析包含内容位置错误的内容搜索。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3aed9c1d2d1fe3c40adb64b4854ef359f931bcb
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357552"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="810c9-103">重试内容搜索以解决内容位置错误</span><span class="sxs-lookup"><span data-stu-id="810c9-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="810c9-104">当您在安全与合规中心中使用内容搜索来搜索大量邮箱时，可能会收到类似于错误的搜索错误：</span><span class="sxs-lookup"><span data-stu-id="810c9-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="810c9-105">这些错误 (CS001-002、CS003-002、CS008-009、CS012-002 和的其他) 错误的错误代码，这表示内容搜索无法搜索特定的内容位置;在此示例中，未搜索两个邮箱。</span><span class="sxs-lookup"><span data-stu-id="810c9-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="810c9-106">这些错误显示在内容搜索的 "状态详细信息" 飞出页面上。</span><span class="sxs-lookup"><span data-stu-id="810c9-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="810c9-107">内容位置错误的原因</span><span class="sxs-lookup"><span data-stu-id="810c9-107">Cause of content location errors</span></span>

<span data-ttu-id="810c9-108">搜索大量邮箱时，会在 Microsoft 数据中心的数千台服务器之间分发搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="810c9-109">在任意时刻，特定服务器可能处于重新启动状态或在故障转移到冗余副本的过程中。</span><span class="sxs-lookup"><span data-stu-id="810c9-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="810c9-110">在上述任一情况下，内容搜索检索数据的请求都将超时。在上面的示例中，失败的邮箱的错误是搜索超时的结果。</span><span class="sxs-lookup"><span data-stu-id="810c9-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="810c9-111">解决内容位置错误</span><span class="sxs-lookup"><span data-stu-id="810c9-111">Resolving content location errors</span></span>

<span data-ttu-id="810c9-112">重新启动搜索通常会在不同的服务器上产生类似的错误。</span><span class="sxs-lookup"><span data-stu-id="810c9-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="810c9-113">请单击 "搜索结果" 页顶部显示的 " **重试** " 按钮，而不是重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![单击 "重试" 按钮解决内容位置错误](../media/retrycontentsearch3.png)

<span data-ttu-id="810c9-115">这将导致仅对失败的邮箱重试搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="810c9-116">当您重试搜索时，将保留已成功返回的其他结果。</span><span class="sxs-lookup"><span data-stu-id="810c9-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="810c9-117">避免内容位置错误的提示</span><span class="sxs-lookup"><span data-stu-id="810c9-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="810c9-118">以下是内容位置错误的一些其他原因，以及一些提示，可帮助您在搜索大量邮箱时避免出现这些错误。</span><span class="sxs-lookup"><span data-stu-id="810c9-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="810c9-119">正在搜索的邮箱可能因用户活动而繁忙。</span><span class="sxs-lookup"><span data-stu-id="810c9-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="810c9-120">在这种情况下，搜索服务可能会对自身进行限制以阻止邮箱变得不可用。</span><span class="sxs-lookup"><span data-stu-id="810c9-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="810c9-121">若要避免这种情况，请尝试在非工作时间运行搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="810c9-122">搜索查询可能会从邮箱中检索过多的内容。</span><span class="sxs-lookup"><span data-stu-id="810c9-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="810c9-123">如果可能，请尝试使用关键字、日期范围和搜索条件来缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="810c9-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="810c9-124">使用 [关键字列表](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)创建搜索查询时，关键字或关键字短语过多。</span><span class="sxs-lookup"><span data-stu-id="810c9-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="810c9-125">当您运行使用关键字列表的搜索查询时，该服务实质上会对关键字列表中的每一行运行单独的搜索，以便可以生成统计信息。</span><span class="sxs-lookup"><span data-stu-id="810c9-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="810c9-126">如果要在搜索查询中使用关键字列表，请最大限度地减少关键字列表中的行数，或将数字关键字分成较小的列表，并为每个关键字列表创建不同的搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="810c9-127">为了帮助减少由大型关键字列表导致的问题，您现在限制为搜索查询的关键字列表中的最多20行。</span><span class="sxs-lookup"><span data-stu-id="810c9-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="810c9-128">同时对同一邮箱执行的搜索过多。</span><span class="sxs-lookup"><span data-stu-id="810c9-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="810c9-129">如果可能，请尝试一次在任何一个邮箱上运行一次搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="810c9-130">在一次搜索中搜索的邮箱过多。</span><span class="sxs-lookup"><span data-stu-id="810c9-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="810c9-131">搜索大量邮箱时，会增加内容位置错误的可能性。</span><span class="sxs-lookup"><span data-stu-id="810c9-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="810c9-132">如果可能，请尝试运行多个搜索，以便每个搜索都包含组织中的一部分邮箱。</span><span class="sxs-lookup"><span data-stu-id="810c9-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="810c9-133">对邮箱执行必需的维护。</span><span class="sxs-lookup"><span data-stu-id="810c9-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="810c9-134">尽管此原因可能很少发生，请在收到内容位置错误后稍等片刻，然后重试搜索。</span><span class="sxs-lookup"><span data-stu-id="810c9-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
