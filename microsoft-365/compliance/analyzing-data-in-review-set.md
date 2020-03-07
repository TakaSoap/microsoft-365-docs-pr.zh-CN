---
title: 在高级电子数据展示中分析评审集中的数据
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
ms.openlocfilehash: 0f9cb386ce57d6581ade5caa05e029511100d9b3
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42556780"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="1edae-102">在高级电子数据展示中分析评审集中的数据</span><span class="sxs-lookup"><span data-stu-id="1edae-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="1edae-103">收集的文档数较大时，可能很难查看所有文档。</span><span class="sxs-lookup"><span data-stu-id="1edae-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="1edae-104">高级电子数据展示提供了大量工具来分析文档，以减少要查看的文档量而不丢失任何信息，并帮助您以一致的方式组织文档。</span><span class="sxs-lookup"><span data-stu-id="1edae-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="1edae-105">若要了解有关这些功能的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1edae-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="1edae-106">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="1edae-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="1edae-107">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="1edae-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="1edae-108">主题</span><span class="sxs-lookup"><span data-stu-id="1edae-108">Themes</span></span>](themes.md)

<span data-ttu-id="1edae-109">若要分析审阅集中的数据，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1edae-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="1edae-110">为你的事例配置分析设置。</span><span class="sxs-lookup"><span data-stu-id="1edae-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="1edae-111">有关详细信息，请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1edae-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="1edae-112">打开要分析的审阅集。</span><span class="sxs-lookup"><span data-stu-id="1edae-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="1edae-113">单击 "**管理审阅集**"。</span><span class="sxs-lookup"><span data-stu-id="1edae-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="1edae-114">单击**评审集的 "运行分析"**。</span><span class="sxs-lookup"><span data-stu-id="1edae-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="1edae-115">可以在案例的 "**作业**" 选项卡上检查分析进度。</span><span class="sxs-lookup"><span data-stu-id="1edae-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="1edae-116">完成分析后，您可以查看分析报告，在审核的输出集内运行查询（请参阅[评审集内的查询](review-set-search.md)），并查看给定文档的相关文档（请参阅[审阅集中的数据](reviewing-data-in-review-set.md)）。</span><span class="sxs-lookup"><span data-stu-id="1edae-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="1edae-117">分析报告</span><span class="sxs-lookup"><span data-stu-id="1edae-117">Analytics report</span></span>

<span data-ttu-id="1edae-118">查看审阅集的分析报告：</span><span class="sxs-lookup"><span data-stu-id="1edae-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="1edae-119">打开评审集。</span><span class="sxs-lookup"><span data-stu-id="1edae-119">Open the review set.</span></span>

2. <span data-ttu-id="1edae-120">单击 "**管理审阅集**"。</span><span class="sxs-lookup"><span data-stu-id="1edae-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="1edae-121">单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="1edae-121">Click **View report**.</span></span>

<span data-ttu-id="1edae-122">此报告包含来自分析的七个组件：</span><span class="sxs-lookup"><span data-stu-id="1edae-122">The report has seven components from analysis:</span></span>

- <span data-ttu-id="1edae-123">**目标填充：** 在审阅集中找到的电子邮件、附件和松散文档的数量。</span><span class="sxs-lookup"><span data-stu-id="1edae-123">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="1edae-124">**文档（不包括附件）：** 要进行透视的松散文档的数量、数据透视表的重复的唯一性或另一个文档的完全相同的数量。</span><span class="sxs-lookup"><span data-stu-id="1edae-124">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="1edae-125">**电子邮件：** Inclusives 的电子邮件数、包含的副本、包含的 minuses 或以上任何内容。</span><span class="sxs-lookup"><span data-stu-id="1edae-125">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="1edae-126">**附件：** 审阅集中其他电子邮件附件的唯一或重复的电子邮件附件数。</span><span class="sxs-lookup"><span data-stu-id="1edae-126">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="1edae-127">**按类型的文件数：** 由文件扩展名标识的文件数。</span><span class="sxs-lookup"><span data-stu-id="1edae-127">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="1edae-128">**按源的文档：** 按其原始数据源的内容摘要。</span><span class="sxs-lookup"><span data-stu-id="1edae-128">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="1edae-129">**按进程聚合的文档：** 按评审过程集的内容摘要。</span><span class="sxs-lookup"><span data-stu-id="1edae-129">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
