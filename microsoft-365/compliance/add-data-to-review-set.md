---
title: 将搜索结果添加到审阅集
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
description: 添加与高级电子数据展示事例相关的搜索结果。 将项目从其原始位置复制并复制到 Microsoft 提供的 Azure 存储位置。 此外，还会重新编制项索引，高级电子数据展示将对图像文件执行光学字符识别（OCR），并上传图像文本以供审阅和分析。
ms.openlocfilehash: 5e4eaa5e83bbca3a80abe0026f3880ce8d3c85c4
ms.sourcegitcommit: 0b2c41dad19da5f0513097c36a4ff32a5868836c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2020
ms.locfileid: "42588815"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="bef6a-105">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="bef6a-105">Add search results to a review set</span></span>

<span data-ttu-id="bef6a-106">当您对搜索结果感到满意并准备好查看和分析这些搜索结果时，您可以将其添加到审阅集（在案例中）。</span><span class="sxs-lookup"><span data-stu-id="bef6a-106">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="bef6a-107">将原始数据复制到评审集还可为您提供高级分析工具，如主题检测、接近重复检测和电子邮件线程标识，从而促进评审和分析过程。</span><span class="sxs-lookup"><span data-stu-id="bef6a-107">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="bef6a-108">您还可以将非 Office 365 数据源中的数据添加到检查集，以便除了从 Office 365 收集的数据之外，还可以查看数据。</span><span class="sxs-lookup"><span data-stu-id="bef6a-108">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span> 

<span data-ttu-id="bef6a-109">将搜索结果添加到审阅集时（在 "**审阅集**" 选项卡上列出了一个事例中的审阅集）时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="bef6a-109">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="bef6a-110">将再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="bef6a-110">The search is run again.</span></span> <span data-ttu-id="bef6a-111">这意味着复制到评审集的实际搜索结果可能与上次运行搜索时返回的估计结果不同。</span><span class="sxs-lookup"><span data-stu-id="bef6a-111">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="bef6a-112">搜索结果中的所有项目都将从 live Office 365 服务中的原始数据源复制，并复制到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="bef6a-112">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="bef6a-113">将对所有项目（包括内容和元数据）进行重新编制索引，以便审核集中的所有数据在对事例数据的审阅期间完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="bef6a-113">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="bef6a-114">当您在案例调查过程中搜索评审集中的数据时，对数据进行重新编制索引将导致彻底且快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="bef6a-114">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="bef6a-115">若要将数据添加到审阅集，请单击 "**搜索**" 选项卡上的搜索，然后单击浮出控件页面上的 "**将结果添加到审阅集**"。</span><span class="sxs-lookup"><span data-stu-id="bef6a-115">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![向评审集添加数据](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="bef6a-117">您可以添加到现有的审阅集，也可以创建新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="bef6a-117">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="bef6a-118">如果添加到新的审阅集，请指定名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="bef6a-118">If adding to a new review set, specify the name and then click **Add**.</span></span>

![选择评审集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="bef6a-120">向评审集添加数据是一个长期运行的过程。</span><span class="sxs-lookup"><span data-stu-id="bef6a-120">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="bef6a-121">此过程包括从 Office 365 中的原始数据源（例如，从邮箱和网站）中收集项目，将它们复制到 Azure 存储位置（此复制过程也称为 "*摄取*"），然后对项目重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="bef6a-121">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="bef6a-122">您可以在 "**作业**" 选项卡或 "**搜索**" 选项卡上通过监视 "添加的**数据到评审集**" 列中的状态来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="bef6a-122">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="bef6a-123">完成审阅集处理后，单击该事例中的 "**查看集**" 选项卡，然后单击 "检查设置" 以启动筛选、查看、标记和导出评审集中数据的过程。</span><span class="sxs-lookup"><span data-stu-id="bef6a-123">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="bef6a-124">向评审集添加示例</span><span class="sxs-lookup"><span data-stu-id="bef6a-124">Add a sample to a review set</span></span>

<span data-ttu-id="bef6a-125">如果要在将所有搜索结果添加到审阅集之前更全面地验证搜索结果，您可以将搜索结果的示例添加到审阅集，而不是添加所有内容。</span><span class="sxs-lookup"><span data-stu-id="bef6a-125">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="bef6a-126">若要向审阅集添加示例，请单击 "**搜索**" 选项卡上的搜索，然后单击浮出控件页面上的 "**示例**"。</span><span class="sxs-lookup"><span data-stu-id="bef6a-126">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="bef6a-127">在 "**采样参数**" 页上，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="bef6a-127">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="bef6a-128">**可信度百分比**和**可信度间隔百分比**-添加到审阅集的项目将由您设置的统计参数决定。</span><span class="sxs-lookup"><span data-stu-id="bef6a-128">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="bef6a-129">如果您通常在采样结果时使用置信度和间隔，请在下拉框中进行指定。</span><span class="sxs-lookup"><span data-stu-id="bef6a-129">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="bef6a-130">否则，使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="bef6a-130">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="bef6a-131">**随机样本百分比**-添加到审阅集的项目基于由搜索返回的总项目数的指定百分比的随机选择。</span><span class="sxs-lookup"><span data-stu-id="bef6a-131">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="bef6a-132">选择并配置前面的选项之一后，选择要向其中添加示例的审阅集，然后单击 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="bef6a-132">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="bef6a-133">同样，您可以在 "**作业**" 选项卡或 "**搜索**" 选项卡上通过监视 "添加的**数据到评审集**" 列中的状态来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="bef6a-133">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="bef6a-134">光学字符识别</span><span class="sxs-lookup"><span data-stu-id="bef6a-134">Optical character recognition</span></span>

<span data-ttu-id="bef6a-135">将搜索结果添加到审阅集时，高级电子数据展示中的光学字符识别（OCR）功能会自动从图像中提取文本，并包括包含添加到评审集的数据的图像文本。</span><span class="sxs-lookup"><span data-stu-id="bef6a-135">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="bef6a-136">您可以在审阅集中的选定图像文件的文本查看器中查看提取的文本。</span><span class="sxs-lookup"><span data-stu-id="bef6a-136">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="bef6a-137">这样，您就可以对图像中的文本进行进一步的审阅和分析。</span><span class="sxs-lookup"><span data-stu-id="bef6a-137">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="bef6a-138">稀疏文件、电子邮件附件和嵌入图像支持 OCR。</span><span class="sxs-lookup"><span data-stu-id="bef6a-138">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="bef6a-139">有关 OCR 支持的图像文件格式的列表，请参阅[高级电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="bef6a-139">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="bef6a-140">您必须为在高级电子数据展示中创建的每个事例启用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="bef6a-140">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="bef6a-141">有关详细信息，请参阅[配置搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="bef6a-141">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
