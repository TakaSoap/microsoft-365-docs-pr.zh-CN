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
ms.custom:
- seo-marvel-apr2020
description: 了解如何将这些搜索结果的搜索结果或示例添加到高级电子数据展示案例审阅集中。
ms.openlocfilehash: 687cc33c0e7e6a09fb352e9c13058a6fcac30053
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814524"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="6158b-103">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="6158b-103">Add search results to a review set</span></span>

<span data-ttu-id="6158b-104">如果对搜索结果有信要求，并且准备审阅和分析这些搜索结果，可以将这些结果添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="6158b-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="6158b-105">将原始数据复制到审阅集还通过为你提供高级分析工具（如主题检测、空闲重复检测和电子邮件线程标识）帮助审阅和分析过程。</span><span class="sxs-lookup"><span data-stu-id="6158b-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="6158b-106">你还可以将来自非 Microsoft 365 数据源的数据添加到审阅集中，以便查看这些数据，以及从 Microsoft 365 收集的数据。</span><span class="sxs-lookup"><span data-stu-id="6158b-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span> 

<span data-ttu-id="6158b-107">将搜索结果添加到审阅集 (审阅集中会列在 **案** 例) ，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="6158b-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="6158b-108">再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="6158b-108">The search is run again.</span></span> <span data-ttu-id="6158b-109">这意味着复制到审阅集的实际搜索结果可能不同于上次运行搜索时返回的结果估计结果。</span><span class="sxs-lookup"><span data-stu-id="6158b-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="6158b-110">搜索结果中的所有项目都从实时服务中的原始数据源复制，并复制到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="6158b-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="6158b-111">所有项目 (内容和元数据文件) 重新编制索引，以便审阅集中的所有数据在查看事例数据期间可以完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="6158b-111">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="6158b-112">当您在事例调查期间，如果在审阅集中搜索数据，重新为数据重新编制索引会进行全面而快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="6158b-112">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="6158b-113">若要将数据添加到审阅集，请单击"搜索"选项卡上 **的搜索** ，然后单击"添加 **结果以查看** 浮出控件"页面上的集。</span><span class="sxs-lookup"><span data-stu-id="6158b-113">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![将数据添加到审阅集](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="6158b-115">可以添加到现有审阅集，也可以创建新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="6158b-115">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="6158b-116">如果添加到新的审阅集，请指定名称，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="6158b-116">If adding to a new review set, specify the name and then click **Add**.</span></span>

![选择审阅集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="6158b-118">定义查看限制集合的选项</span><span class="sxs-lookup"><span data-stu-id="6158b-118">Define options to scope your collection for review</span></span>

<span data-ttu-id="6158b-119">在将搜索内容添加到现有评审集或创建新评价内容时，您可以选择选择如何收集要审阅的内容：</span><span class="sxs-lookup"><span data-stu-id="6158b-119">As you add the content of a search to an existing review set or create a new one you have options for how to collect the content for review:</span></span>

- <span data-ttu-id="6158b-120">**对话审阅集** - 将对已加入审阅集的项目启用按线索组织，以帮助查看后来和出发对话上下文中的内容，请参阅本文中 [对话审阅集]</span><span class="sxs-lookup"><span data-stu-id="6158b-120">**Conversational review set** - the items added to the review set will be enabled for threaded conversations to help review content in context of the back and forth conversation, see more in this article [conversation review sets]</span></span>

- <span data-ttu-id="6158b-121">**为新式附件启用检索** - 使用此控件在集合中加入新式附件或链接的文件，以供进一步审阅;阅读有关可用于对此内容进行分组的新可搜索字段名称的详细信息，请参阅 [高级电子数据展示中的文档元数据字段]</span><span class="sxs-lookup"><span data-stu-id="6158b-121">**Enable retrieval for modern attachment** - use this control to include modern attachments or linked files in the collection for further review; read more about the new searchable field names that are available to group this content, see [document metadata fields in advanced ediscovery]</span></span>

- <span data-ttu-id="6158b-122">\*\*将 SharePoint 2016 (版本) \*\* - 此控件按集合的版本限制和搜索参数启用 SharePoint 文件的所有版本集合;注意：控件将显著增加集合的大小</span><span class="sxs-lookup"><span data-stu-id="6158b-122">**Include versions from SharePoint (beta)** - this control enables collection of all version of a SharePoint file per the version limits and search parameters of the collection; note: this control will increase the size of the collection significantly</span></span>

<span data-ttu-id="6158b-123">将数据添加到审阅集是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="6158b-123">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="6158b-124">此过程包括从 Microsoft 365 (中的原始数据源收集项，例如从邮箱和网站) 收集项目，将它们复制到 Azure 存储位置 (此复制过程也称为 *) ，* 然后重新编制项目索引。</span><span class="sxs-lookup"><span data-stu-id="6158b-124">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="6158b-125">您可以通过监视新增数据**中查看查看集**列的状态来**Searches**跟踪"作业"选项卡上或"**搜索"选项卡上的进**度。</span><span class="sxs-lookup"><span data-stu-id="6158b-125">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="6158b-126">在完成审阅集处理后，单击 **案例中的"审阅集** "选项卡，然后单击评审集以开始执行审阅集中的数据的筛选、审核、标记和导出过程。</span><span class="sxs-lookup"><span data-stu-id="6158b-126">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="6158b-127">向审阅集添加示例</span><span class="sxs-lookup"><span data-stu-id="6158b-127">Add a sample to a review set</span></span>

<span data-ttu-id="6158b-128">如果要在将所有搜索结果添加到审阅集之前更为详细地验证搜索的结果，可以向审阅集添加搜索结果的示例，而不是添加所有内容。</span><span class="sxs-lookup"><span data-stu-id="6158b-128">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="6158b-129">若要将示例添加到审阅集，请单击"搜索"选项卡上 **的搜索** ，然后单击" **浮** 出控件"页上的示例。</span><span class="sxs-lookup"><span data-stu-id="6158b-129">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="6158b-130">在" **采样参数"页上** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="6158b-130">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="6158b-131">**可信度 % 和\*\*\*\*可信度间隔 %** - 添加到审阅集的项目将由您设置的统计参数确定。</span><span class="sxs-lookup"><span data-stu-id="6158b-131">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="6158b-132">如果在对结果进行采样时，通常使用可信度和间隔，请在下拉框中指定它们。</span><span class="sxs-lookup"><span data-stu-id="6158b-132">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="6158b-133">否则，请使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="6158b-133">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="6158b-134">**随机采样百** 分比 - 添加到审阅集中的项目基于由搜索返回的项目总数指定百分比的随机选择。</span><span class="sxs-lookup"><span data-stu-id="6158b-134">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="6158b-135">选择并配置以上选项之一后，选择要向其添加示例的审阅集，然后单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="6158b-135">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="6158b-136">同样，您可以通过监视"已添加的数据 **"列**中的状态来跟踪"**Searches**作业"选项卡或"搜索 **"选项卡上的进**度。</span><span class="sxs-lookup"><span data-stu-id="6158b-136">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="6158b-137">光学字符识别</span><span class="sxs-lookup"><span data-stu-id="6158b-137">Optical character recognition</span></span>

<span data-ttu-id="6158b-138">向审阅集添加搜索结果时，高级电子数据展示中的 OCR) 功能的光学字符识别 (自动从图像中提取文本，并且包括图像文本以及添加到审阅集中的数据。</span><span class="sxs-lookup"><span data-stu-id="6158b-138">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="6158b-139">您可以在查看集中所选图像文件的文本查看器中查看提取的文本。</span><span class="sxs-lookup"><span data-stu-id="6158b-139">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="6158b-140">这使你可以对图像中的文本进行进一步审阅和分析。</span><span class="sxs-lookup"><span data-stu-id="6158b-140">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="6158b-141">松散文件、电子邮件附件和嵌入式图像支持 OCR。</span><span class="sxs-lookup"><span data-stu-id="6158b-141">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="6158b-142">有关 OCR 支持的图像文件格式列表，请参阅高级 [电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="6158b-142">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="6158b-143">您必须为您在高级电子数据展示中创建的每种案例都启用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="6158b-143">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="6158b-144">有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="6158b-144">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
