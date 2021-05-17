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
description: 了解如何将搜索结果或这些搜索结果的示例添加到Advanced eDiscovery审阅集。
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919974"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="5bce7-103">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="5bce7-103">Add search results to a review set</span></span>

<span data-ttu-id="5bce7-104">当您对搜索结果感到满意并且已准备好查看和分析这些搜索结果时，您可以将它们添加到案例的审阅集。</span><span class="sxs-lookup"><span data-stu-id="5bce7-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="5bce7-105">将原始数据复制到审阅集还通过为您提供高级分析工具（如主题检测、近重复检测和电子邮件线程标识）来简化审阅和分析过程。</span><span class="sxs-lookup"><span data-stu-id="5bce7-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="5bce7-106">您还可以将来自非Microsoft 365数据源的数据添加到审阅集，以便除了从审阅集收集的数据之外，您还可以查看Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5bce7-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span>

<span data-ttu-id="5bce7-107">当您将搜索结果添加到审阅集 ("审阅集"选项卡上的"审阅集"选项卡上 () ，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="5bce7-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="5bce7-108">再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="5bce7-108">The search is run again.</span></span> <span data-ttu-id="5bce7-109">这意味着复制到审阅集的实际搜索结果可能不同于上次运行搜索时返回的估计结果。</span><span class="sxs-lookup"><span data-stu-id="5bce7-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="5bce7-110">搜索结果中的所有项目都从实时服务中的原始数据源复制，并复制到 Microsoft 云中的Azure 存储安全位置。</span><span class="sxs-lookup"><span data-stu-id="5bce7-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="5bce7-111">所有 (包括内容和元数据) 重新建立索引，以便审阅集内的所有数据在审阅案例数据期间完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="5bce7-111">All items (including the content and metadata) are reindexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="5bce7-112">当您在案例调查期间搜索审阅集内的数据时，对数据重新建立索引会导致全面而快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="5bce7-112">Reindexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

- <span data-ttu-id="5bce7-113">使用 [Microsoft](encryption.md) 加密技术加密并附加到搜索结果中返回的电子邮件的文件在将电子邮件和附加文件添加到审阅集时将解密。</span><span class="sxs-lookup"><span data-stu-id="5bce7-113">A file encrypted with a [Microsoft encryption technology](encryption.md) and is attached to an email message that's returned in the search results is decrypted when the email message and attached file are added to the review set.</span></span> <span data-ttu-id="5bce7-114">可以在审阅集内查看和查询解密的文件。</span><span class="sxs-lookup"><span data-stu-id="5bce7-114">You can review and query the decrypted file in the review set.</span></span> <span data-ttu-id="5bce7-115">您必须分配有 RMS 解密角色，以将解密的电子邮件附件添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="5bce7-115">You have to be assigned the RMS Decrypt role to add decrypted email attachments to a review set.</span></span> <span data-ttu-id="5bce7-116">有关详细信息，请参阅解密[Microsoft 365电子数据展示工具。](ediscovery-decryption.md)</span><span class="sxs-lookup"><span data-stu-id="5bce7-116">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

<span data-ttu-id="5bce7-117">若要将数据添加到审阅集，请单击"搜索"选项卡上的搜索，然后单击飞出页面上的"添加要 **审阅** 的结果集"。</span><span class="sxs-lookup"><span data-stu-id="5bce7-117">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

<span data-ttu-id="5bce7-118">您可以添加到现有审阅集或创建新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="5bce7-118">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="5bce7-119">如果添加到新的审阅集，请指定名称，然后单击 **"添加"** 以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="5bce7-119">If adding to a new review set, specify the name and then click **Add** to display the flyout page.</span></span>

![选择审阅集并配置集合选项](../media/AeD_AddToReviewSet.png)

<span data-ttu-id="5bce7-121">向审阅集添加数据是一个长期运行流程。</span><span class="sxs-lookup"><span data-stu-id="5bce7-121">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="5bce7-122">此过程包括收集 Microsoft 365 (中原始数据源中的项目（例如，从邮箱和网站) 中收集项目、将它们复制到 Azure 存储 位置 (此复制过程也称为 *ingestion*) ，然后对项目重新建立索引。</span><span class="sxs-lookup"><span data-stu-id="5bce7-122">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then reindexing the items.</span></span> <span data-ttu-id="5bce7-123">通过监视"要审阅的数据"列中的状态，可以跟踪"作业"选项卡或"搜索"**选项卡** 上的进度。</span><span class="sxs-lookup"><span data-stu-id="5bce7-123">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="5bce7-124">完成审阅集处理后，单击案例的"审阅集"选项卡，然后单击审阅集以开始筛选、审阅、标记和导出审阅集数据的过程。</span><span class="sxs-lookup"><span data-stu-id="5bce7-124">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="5bce7-125">定义用于确定要审阅的集合范围的选项</span><span class="sxs-lookup"><span data-stu-id="5bce7-125">Define options to scope your collection for review</span></span>

<span data-ttu-id="5bce7-126">当您将搜索内容添加到现有或新的审阅集时，您具有以下用于收集要审阅的内容的选项：</span><span class="sxs-lookup"><span data-stu-id="5bce7-126">When you add the content of a search to an existing or new review set, you have the following options for how to collect the content for review:</span></span>

- <span data-ttu-id="5bce7-127">**包含** SharePoint (beta) 的版本：使用此选项可以按集合的版本限制和搜索参数启用 SharePoint 文档的所有版本的集合。</span><span class="sxs-lookup"><span data-stu-id="5bce7-127">**Include versions from SharePoint (beta)**: Use this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="5bce7-128">选择此选项将显著增加添加到审阅集的项目的大小。</span><span class="sxs-lookup"><span data-stu-id="5bce7-128">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

- <span data-ttu-id="5bce7-129">**对话检索选项**：为线程对话启用添加到审阅集的项目，以帮助查看来回对话上下文中的内容。</span><span class="sxs-lookup"><span data-stu-id="5bce7-129">**Conversation retrieval options**: Items added to the review set are enabled for threaded conversations to help review content in context of the back and forth conversation.</span></span> <span data-ttu-id="5bce7-130">有关详细信息，请参阅 [审阅高级 eDiscovery 中的对话](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="5bce7-130">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

- <span data-ttu-id="5bce7-131">**启用新式附件检索**：使用此选项在集合中包括新式附件或链接文件，以便进一步查看。</span><span class="sxs-lookup"><span data-stu-id="5bce7-131">**Enable retrieval for modern attachments**: Use this option to include modern attachments or linked files in the collection for further review.</span></span> <span data-ttu-id="5bce7-132">有关与新式附件相关的可搜索属性详细信息，请参阅文档[元数据字段Advanced eDiscovery。](document-metadata-fields-in-Advanced-eDiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5bce7-132">For more information about the searchable properties related to modern attachments, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="5bce7-133">向审阅集添加示例</span><span class="sxs-lookup"><span data-stu-id="5bce7-133">Add a sample to a review set</span></span>

<span data-ttu-id="5bce7-134">如果您希望在将搜索结果添加到审阅集之前更彻底地验证搜索结果，您可以将搜索结果的示例添加到审阅集，而不是添加所有内容。</span><span class="sxs-lookup"><span data-stu-id="5bce7-134">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="5bce7-135">若要将示例添加到审阅集，请单击"搜索"选项卡上的搜索，然后单击飞出页面上的"示例"。</span><span class="sxs-lookup"><span data-stu-id="5bce7-135">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="5bce7-136">在" **采样参数"** 页上，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="5bce7-136">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="5bce7-137">**可信度百分比** 和 **置信区间百** 分比 - 添加到审阅集的项目将由您设置的统计参数确定。</span><span class="sxs-lookup"><span data-stu-id="5bce7-137">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="5bce7-138">如果在采样结果时通常使用置信水平和间隔，请从下拉框中指定它们。</span><span class="sxs-lookup"><span data-stu-id="5bce7-138">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="5bce7-139">否则，请使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="5bce7-139">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="5bce7-140">**随机示例百** 分比 - 添加到审阅集的项目基于搜索返回的项目总数的指定百分比的随机选择。</span><span class="sxs-lookup"><span data-stu-id="5bce7-140">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="5bce7-141">选择并配置以上选项之一后，选择要将示例添加到的审阅集，然后单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="5bce7-141">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="5bce7-142">同样，通过监视"要审阅的数据"列中的状态，可以跟踪"作业"选项卡或"搜索"**选项卡** 上的进度。</span><span class="sxs-lookup"><span data-stu-id="5bce7-142">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="5bce7-143">光学字符识别</span><span class="sxs-lookup"><span data-stu-id="5bce7-143">Optical character recognition</span></span>

<span data-ttu-id="5bce7-144">将搜索结果添加到审阅集时，Advanced eDiscovery 中的光学字符识别 (OCR) 功能会自动从图像中提取文本，并包括图像文本以及已添加到审阅集的数据。</span><span class="sxs-lookup"><span data-stu-id="5bce7-144">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="5bce7-145">可以在审阅集内所选图像文件的文本查看器中查看提取的文本。</span><span class="sxs-lookup"><span data-stu-id="5bce7-145">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="5bce7-146">通过此功能，你可以对图像中的文本进行进一步审阅和分析。</span><span class="sxs-lookup"><span data-stu-id="5bce7-146">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="5bce7-147">OCR 支持松散文件、电子邮件附件和嵌入图像。</span><span class="sxs-lookup"><span data-stu-id="5bce7-147">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="5bce7-148">有关 OCR 支持的图像文件格式列表，请参阅[高级电子数据展示中受支持的文件类型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="5bce7-148">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="5bce7-149">必须针对在高级电子数据展示中创建的每个案例启用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="5bce7-149">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="5bce7-150">有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="5bce7-150">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
