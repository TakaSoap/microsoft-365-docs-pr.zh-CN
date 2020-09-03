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
description: 了解如何将搜索结果的搜索结果或示例添加到高级电子数据展示事例评审集。
ms.openlocfilehash: 6eed13c2096ad3cd33fbc7af93399824866b17c2
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336646"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="f8587-103">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="f8587-103">Add search results to a review set</span></span>

<span data-ttu-id="f8587-104">当您对搜索结果感到满意并准备好查看和分析这些搜索结果时，您可以将其添加到审阅集（在案例中）。</span><span class="sxs-lookup"><span data-stu-id="f8587-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="f8587-105">将原始数据复制到评审集还可为您提供高级分析工具，如主题检测、接近重复检测和电子邮件线程标识，从而促进评审和分析过程。</span><span class="sxs-lookup"><span data-stu-id="f8587-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="f8587-106">您还可以将非 Microsoft 365 数据源中的数据添加到审查集，以便除了从 Microsoft 365 收集的数据之外，还可以查看数据。</span><span class="sxs-lookup"><span data-stu-id="f8587-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span>

<span data-ttu-id="f8587-107">在将搜索结果添加到审阅集时 \*\* (审阅集选项卡\*\* 上列出了一个事例中的审阅集) ，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="f8587-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="f8587-108">将再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="f8587-108">The search is run again.</span></span> <span data-ttu-id="f8587-109">这意味着复制到评审集的实际搜索结果可能与上次运行搜索时返回的估计结果不同。</span><span class="sxs-lookup"><span data-stu-id="f8587-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="f8587-110">搜索结果中的所有项目都将从 live services 中的原始数据源复制，并复制到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="f8587-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="f8587-111">包含内容和元数据) 的所有项目 (编制索引，以便审阅集中的所有数据在对事例数据的审阅期间完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="f8587-111">All items (including the content and metadata) are reindexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="f8587-112">当您在案例调查过程中搜索评审集中的数据时，对数据进行索引编制将导致彻底且快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="f8587-112">Reindexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="f8587-113">若要将数据添加到审阅集，请单击 " **搜索** " 选项卡上的搜索，然后单击浮出控件页面上的 " **将结果添加到审阅集** "。</span><span class="sxs-lookup"><span data-stu-id="f8587-113">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

<span data-ttu-id="f8587-114">您可以添加到现有的审阅集，也可以创建新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="f8587-114">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="f8587-115">如果添加到新的审阅集，请指定名称，然后单击 " **添加** " 以显示弹出页面。</span><span class="sxs-lookup"><span data-stu-id="f8587-115">If adding to a new review set, specify the name and then click **Add** to display the flyout page.</span></span>

![选择审阅集和配置收集选项](../media/AeD_AddToReviewSet.png)

<span data-ttu-id="f8587-117">向评审集添加数据是一个长期运行的过程。</span><span class="sxs-lookup"><span data-stu-id="f8587-117">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="f8587-118">此过程包括从 Microsoft 365 (中收集原始数据源中的项例如，从邮箱和网站) ，将它们复制到 Azure 存储位置 (此复制过程也称为 *摄取*) ，然后重新索引项目。</span><span class="sxs-lookup"><span data-stu-id="f8587-118">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then reindexing the items.</span></span> <span data-ttu-id="f8587-119">您可以在 " **作业** " 选项卡或 " **搜索** " 选项卡上通过监视 "添加的 **数据到评审集** " 列中的状态来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="f8587-119">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="f8587-120">完成审阅集处理后，单击该事例中的 " **查看集** " 选项卡，然后单击 "检查设置" 以启动筛选、查看、标记和导出评审集中数据的过程。</span><span class="sxs-lookup"><span data-stu-id="f8587-120">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="f8587-121">定义用于查看集合范围的选项</span><span class="sxs-lookup"><span data-stu-id="f8587-121">Define options to scope your collection for review</span></span>

<span data-ttu-id="f8587-122">将搜索内容添加到现有或新的审阅集时，您可以使用以下选项来收集要审阅的内容：</span><span class="sxs-lookup"><span data-stu-id="f8587-122">When you add the content of a search to an existing or new review set, you have the following options for how to collect the content for review:</span></span>

- <span data-ttu-id="f8587-123">\*\*包含来自 sharepoint (beta) 的版本 \*\*：使用此选项可按集合的版本限制和搜索参数启用 SharePoint 文档的所有版本的集合。</span><span class="sxs-lookup"><span data-stu-id="f8587-123">**Include versions from SharePoint (beta)**: Use this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="f8587-124">选择此选项会显著增加添加到审阅集的项目的大小。</span><span class="sxs-lookup"><span data-stu-id="f8587-124">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

- <span data-ttu-id="f8587-125">**对话检索选项**：已为线程对话启用添加到评审集的项，以帮助查看前后对话的上下文中的内容。</span><span class="sxs-lookup"><span data-stu-id="f8587-125">**Conversation retrieval options**: Items added to the review set are enabled for threaded conversations to help review content in context of the back and forth conversation.</span></span> <span data-ttu-id="f8587-126">有关详细信息，请参阅 [在高级电子数据展示中查看对话](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="f8587-126">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

- <span data-ttu-id="f8587-127">**启用对新式附件的检索**：使用此选项可包括集合中新式附件或链接的文件，以供进一步审阅。</span><span class="sxs-lookup"><span data-stu-id="f8587-127">**Enable retrieval for modern attachments**: Use this option to include modern attachments or linked files in the collection for further review.</span></span> <span data-ttu-id="f8587-128">有关与新式附件相关的可搜索属性的详细信息，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="f8587-128">For more information about the searchable properties related to modern attachments, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="f8587-129">向评审集添加示例</span><span class="sxs-lookup"><span data-stu-id="f8587-129">Add a sample to a review set</span></span>

<span data-ttu-id="f8587-130">如果要在将所有搜索结果添加到审阅集之前更全面地验证搜索结果，您可以将搜索结果的示例添加到审阅集，而不是添加所有内容。</span><span class="sxs-lookup"><span data-stu-id="f8587-130">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="f8587-131">若要向审阅集添加示例，请单击 " **搜索** " 选项卡上的搜索，然后单击浮出控件页面上的 " **示例** "。</span><span class="sxs-lookup"><span data-stu-id="f8587-131">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="f8587-132">在 " **采样参数** " 页上，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="f8587-132">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="f8587-133">**可信度百分比** 和 **可信度间隔百分比** -添加到审阅集的项目将由您设置的统计参数决定。</span><span class="sxs-lookup"><span data-stu-id="f8587-133">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="f8587-134">如果您通常在采样结果时使用置信度和间隔，请在下拉框中进行指定。</span><span class="sxs-lookup"><span data-stu-id="f8587-134">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="f8587-135">否则，使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="f8587-135">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="f8587-136">**随机样本百分比** -添加到审阅集的项目基于由搜索返回的总项目数的指定百分比的随机选择。</span><span class="sxs-lookup"><span data-stu-id="f8587-136">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="f8587-137">选择并配置前面的选项之一后，选择要向其中添加示例的审阅集，然后单击 " **发送**"。</span><span class="sxs-lookup"><span data-stu-id="f8587-137">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="f8587-138">同样，您可以在 " **作业** " 选项卡或 " **搜索** " 选项卡上通过监视 "添加的 **数据到评审集** " 列中的状态来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="f8587-138">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="f8587-139">光学字符识别</span><span class="sxs-lookup"><span data-stu-id="f8587-139">Optical character recognition</span></span>

<span data-ttu-id="f8587-140">将搜索结果添加到审阅集时，"高级电子数据展示" 中的 "光学字符识别 (OCR) 功能将自动从图像中提取文本，并在图像文本中包含添加到审阅集的数据。</span><span class="sxs-lookup"><span data-stu-id="f8587-140">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="f8587-141">您可以在审阅集中的选定图像文件的文本查看器中查看提取的文本。</span><span class="sxs-lookup"><span data-stu-id="f8587-141">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="f8587-142">这样，您就可以对图像中的文本进行进一步的审阅和分析。</span><span class="sxs-lookup"><span data-stu-id="f8587-142">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="f8587-143">稀疏文件、电子邮件附件和嵌入图像支持 OCR。</span><span class="sxs-lookup"><span data-stu-id="f8587-143">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="f8587-144">有关 OCR 支持的图像文件格式的列表，请参阅 [高级电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="f8587-144">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="f8587-145">您必须为在高级电子数据展示中创建的每个事例启用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="f8587-145">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="f8587-146">有关详细信息，请参阅 [配置搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="f8587-146">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
