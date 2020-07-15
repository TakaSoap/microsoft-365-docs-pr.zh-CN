---
title: 查看文档的标签活动
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 了解如何使用 Microsoft 365 安全与合规中心中的标签活动浏览器来搜索和查看标签活动。
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127269"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="3a19a-103">查看文档的标签活动</span><span class="sxs-lookup"><span data-stu-id="3a19a-103">View label activity for documents</span></span>

<span data-ttu-id="3a19a-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span><span class="sxs-lookup"><span data-stu-id="3a19a-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="3a19a-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span><span class="sxs-lookup"><span data-stu-id="3a19a-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span></span> <span data-ttu-id="3a19a-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span><span class="sxs-lookup"><span data-stu-id="3a19a-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="3a19a-107">例如，标签活动资源管理器可用于：</span><span class="sxs-lookup"><span data-stu-id="3a19a-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="3a19a-108">查看每个标签每天应用多少次（最多查看 30 天的应用次数）。</span><span class="sxs-lookup"><span data-stu-id="3a19a-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="3a19a-109">查看谁在哪天标记了哪个文件（其中还提供指向文件驻留网站的链接）。</span><span class="sxs-lookup"><span data-stu-id="3a19a-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="3a19a-110">查看哪些文件的标签已变更或遭删除、新旧标签分别是什么，以及更改者是谁。</span><span class="sxs-lookup"><span data-stu-id="3a19a-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="3a19a-111">Filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="3a19a-111">Filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="3a19a-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="3a19a-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="3a19a-113">View label activity for folders as well as individual documents.</span><span class="sxs-lookup"><span data-stu-id="3a19a-113">View label activity for folders as well as individual documents.</span></span> <span data-ttu-id="3a19a-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span><span class="sxs-lookup"><span data-stu-id="3a19a-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="3a19a-115">要查找标签活动资源管理器，可访问安全 &amp; 合规中心 >“**信息管理**” > “**标签活动资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="3a19a-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="3a19a-116">请注意，必须有 Office 365 企业版 E5 订阅，才能使用标签活动资源管理器。</span><span class="sxs-lookup"><span data-stu-id="3a19a-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![标签活动资源管理器](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="3a19a-118">查看文件或文件夹的标签活动</span><span class="sxs-lookup"><span data-stu-id="3a19a-118">View label activities for files or folders</span></span>

<span data-ttu-id="3a19a-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span><span class="sxs-lookup"><span data-stu-id="3a19a-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span></span> <span data-ttu-id="3a19a-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span><span class="sxs-lookup"><span data-stu-id="3a19a-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="3a19a-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span><span class="sxs-lookup"><span data-stu-id="3a19a-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span></span> <span data-ttu-id="3a19a-122">Therefore, labeling folders might affect a significant number of files.</span><span class="sxs-lookup"><span data-stu-id="3a19a-122">Therefore, labeling folders might affect a significant number of files.</span></span> <span data-ttu-id="3a19a-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="3a19a-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![用于显示文件和文件夹的标签活动的下拉菜单](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="3a19a-125">标签活动</span><span class="sxs-lookup"><span data-stu-id="3a19a-125">Label activities</span></span>

 <span data-ttu-id="3a19a-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="3a19a-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span></span> <span data-ttu-id="3a19a-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span><span class="sxs-lookup"><span data-stu-id="3a19a-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="3a19a-128">标签更改</span><span class="sxs-lookup"><span data-stu-id="3a19a-128">Label changes</span></span>

 <span data-ttu-id="3a19a-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="3a19a-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span></span> <span data-ttu-id="3a19a-130">You can use this view to quickly see such risky actions and the user who performed them.</span><span class="sxs-lookup"><span data-stu-id="3a19a-130">You can use this view to quickly see such risky actions and the user who performed them.</span></span> <span data-ttu-id="3a19a-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span><span class="sxs-lookup"><span data-stu-id="3a19a-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![标签活动的细节窗格](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="3a19a-133">筛选标签活动</span><span class="sxs-lookup"><span data-stu-id="3a19a-133">Filter label activity</span></span>

<span data-ttu-id="3a19a-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="3a19a-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="3a19a-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="3a19a-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![标签活动筛选器](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

