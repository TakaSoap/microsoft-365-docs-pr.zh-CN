---
title: 将草稿集合提交到审阅集中
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 创建并访问草稿集合后，可以提交到审阅集。 提交草稿集合时，收集的项目将添加到案例的审阅集中。 收集的项目在审阅集内后，可以分析、审阅和导出它们。
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838839"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="90cc3-105">将草稿集合提交到审阅集中Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="90cc3-105">Commit a draft collection to a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="90cc3-106">如果你对在草稿集合中收集的项目感到满意，并且已准备好分析、标记和审阅这些项目，可以在这种情况中向审阅集添加集合。</span><span class="sxs-lookup"><span data-stu-id="90cc3-106">When you're satisfied with the items you've collected in a draft collection and are ready to analyze, tag, and review them, you can add a collection to a review set in the case.</span></span> <span data-ttu-id="90cc3-107">将草稿集合提交到审阅集时，收集的项目会从审阅集中的原始Microsoft 365复制到审阅集。</span><span class="sxs-lookup"><span data-stu-id="90cc3-107">When you commit a draft collection to a review set, collected items are copied from their original content location in Microsoft 365 to a review set.</span></span> <span data-ttu-id="90cc3-108">审阅集是 Microsoft 提供的安全Azure 存储 Microsoft 云中的位置。</span><span class="sxs-lookup"><span data-stu-id="90cc3-108">A review set is a secure, Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>

## <a name="commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="90cc3-109">将草稿集合提交到审阅集中</span><span class="sxs-lookup"><span data-stu-id="90cc3-109">Commit a draft collection to a review set</span></span>

1. <span data-ttu-id="90cc3-110">在Microsoft 365中心，打开"Advanced eDiscovery"案例，然后选择"集合"选项卡以显示该案例的集合列表。 </span><span class="sxs-lookup"><span data-stu-id="90cc3-110">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, and then select the **Collections** tab to display a list of the collections in the case.</span></span>

   ![一种情况下的集合列表](../media/CommitDraftCollections1.png)

   > [!TIP]
   > <span data-ttu-id="90cc3-112">"状态 `Estimated` "列中的值标识可添加到审阅集的草稿集合。</span><span class="sxs-lookup"><span data-stu-id="90cc3-112">A value of `Estimated` in the **Status** column identifies the draft collections that can be added to a review set.</span></span> <span data-ttu-id="90cc3-113">状态 `Committed` 表示集合已添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="90cc3-113">A status of `Committed` indicates that a collection has already been added to a review set.</span></span>

2. <span data-ttu-id="90cc3-114">在 **"集合** "页上，选择要提交到审阅集的草稿集合。</span><span class="sxs-lookup"><span data-stu-id="90cc3-114">On the **Collections** page, select the draft collection that you want to commit to a review set.</span></span>

3. <span data-ttu-id="90cc3-115">在飞出页面的底部，选择 **操作**  >  **编辑集合**。</span><span class="sxs-lookup"><span data-stu-id="90cc3-115">On the bottom of the flyout page, select **Actions** > **Edit collection**.</span></span>

4. <span data-ttu-id="90cc3-116">在编辑集合向导中，单击 **"下** 一步"，直到显示" **保存草稿或收集"** 页。</span><span class="sxs-lookup"><span data-stu-id="90cc3-116">In the edit collection wizard, click **Next** until the **Save draft or collect** page is displayed.</span></span>

5. <span data-ttu-id="90cc3-117">配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="90cc3-117">Configure the following settings:</span></span>

   1. <span data-ttu-id="90cc3-118">选择 **"收集项目并添加到审阅集"。**</span><span class="sxs-lookup"><span data-stu-id="90cc3-118">Select **Collect items and add to review set**.</span></span>

   2. <span data-ttu-id="90cc3-119">决定是否将集合添加到新的审阅 (，该审阅集是在将集合提交到) 或现有审阅集之后创建的。</span><span class="sxs-lookup"><span data-stu-id="90cc3-119">Decide whether to add the collection to a new review set (which is created after you submit the collection) or to an existing review set.</span></span> <span data-ttu-id="90cc3-120">根据你的决定完成此部分。</span><span class="sxs-lookup"><span data-stu-id="90cc3-120">Complete this section based on your decision.</span></span>

   3. <span data-ttu-id="90cc3-121">配置其他集合设置：</span><span class="sxs-lookup"><span data-stu-id="90cc3-121">Configure the additional collection settings:</span></span>

       - <span data-ttu-id="90cc3-122">**Teams和Yammer** 消息：选择此选项可以将对话线程添加到集合中，该集合包含搜索查询在集合中返回的聊天项目。</span><span class="sxs-lookup"><span data-stu-id="90cc3-122">**Teams and Yammer messages**: Select this option to add conversation threads to the collection that include the chat items returned by the search query in the collection.</span></span> <span data-ttu-id="90cc3-123">这意味着将重新构造包含与搜索条件匹配的项目的聊天对话。</span><span class="sxs-lookup"><span data-stu-id="90cc3-123">This means that the chat conversation that contains items that match the search criteria is reconstructed.</span></span> <span data-ttu-id="90cc3-124">这允许你在来回对话的上下文中查看聊天项目。</span><span class="sxs-lookup"><span data-stu-id="90cc3-124">This lets you review chat items in the context of the back and forth conversation.</span></span> <span data-ttu-id="90cc3-125">有关详细信息，请参阅对话[线程Advanced eDiscovery。](conversation-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="90cc3-125">For more information, see [Conversation threading in Advanced eDiscovery](conversation-review-sets.md).</span></span>

       - <span data-ttu-id="90cc3-126">**云附件**：选择此选项以在将集合结果添加到审阅集时包含新式附件或链接文件。</span><span class="sxs-lookup"><span data-stu-id="90cc3-126">**Cloud attachments**: Select this option to include modern attachments or linked files when the collection results are added to the review set.</span></span> <span data-ttu-id="90cc3-127">这意味着新式附件或链接文件的目标文件将添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="90cc3-127">This means that the target file of a modern attachment or linked file is added to the review set.</span></span>

       - <span data-ttu-id="90cc3-128">**SharePoint版本**：选择此选项可以按集合的版本限制和搜索参数启用 SharePoint 文档的所有版本的集合。</span><span class="sxs-lookup"><span data-stu-id="90cc3-128">**SharePoint versions**: Select this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="90cc3-129">选择此选项将显著增加添加到审阅集的项目的大小。</span><span class="sxs-lookup"><span data-stu-id="90cc3-129">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

   4. <span data-ttu-id="90cc3-130">配置设置以定义要添加到审阅集的集合规模：</span><span class="sxs-lookup"><span data-stu-id="90cc3-130">Configure the settings to define the scale of the collection to add to the review set:</span></span>

      - <span data-ttu-id="90cc3-131">**添加所有集合结果**：选择此选项可以将与集合的搜索条件匹配的所有项目添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="90cc3-131">**Add all collection results**: Select this option to add all the items that match the search criteria of the collection to the review set.</span></span>

      - <span data-ttu-id="90cc3-132">**添加集合结果的示例**：选择此选项以将集合结果的示例添加到审阅集，而不是添加所有结果。</span><span class="sxs-lookup"><span data-stu-id="90cc3-132">**Add a sample of the collection results**: Select this option to add a sample of the collection results to the review set instead of adding all results.</span></span> <span data-ttu-id="90cc3-133">如果选择此选项，请单击" **编辑示例参数** "并选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="90cc3-133">If you select this option, click **Edit sample parameters** and choose one of the following options:</span></span>

         - <span data-ttu-id="90cc3-134">**基于置信** 度的示例：集合中的项目将添加到审阅集，由您设置的统计参数确定。</span><span class="sxs-lookup"><span data-stu-id="90cc3-134">**Sample based on confidence**: Items from the collection are added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="90cc3-135">如果在采样结果时通常使用置信水平和间隔，请从下拉框中指定它们。</span><span class="sxs-lookup"><span data-stu-id="90cc3-135">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="90cc3-136">否则，请使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="90cc3-136">Otherwise, use the default settings.</span></span>

         - <span data-ttu-id="90cc3-137">**随机示例**：根据搜索返回的项目总数指定百分比的随机选择，将集合中的项目添加到审阅集中。</span><span class="sxs-lookup"><span data-stu-id="90cc3-137">**Randomly sample**: Items from the collection are added to the review set based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

6. <span data-ttu-id="90cc3-138">在 **"查看集合"** 页上，您可以查看在上一页上配置的集合设置。</span><span class="sxs-lookup"><span data-stu-id="90cc3-138">On the **Review your collection** page, you can review the collection settings that you configured on the previous page.</span></span> <span data-ttu-id="90cc3-139">如果要 **更改** 它们，请单击"编辑"。</span><span class="sxs-lookup"><span data-stu-id="90cc3-139">Click **Edit** if you want to change them.</span></span>

7. <span data-ttu-id="90cc3-140">单击 **"提交** "创建草稿集合。</span><span class="sxs-lookup"><span data-stu-id="90cc3-140">Click **Submit** to create the draft collection.</span></span> <span data-ttu-id="90cc3-141">将显示一个页面，确认已创建集合。</span><span class="sxs-lookup"><span data-stu-id="90cc3-141">A page is displayed confirming that the collection was created.</span></span>

## <a name="what-happens-after-you-commit-a-draft-collection"></a><span data-ttu-id="90cc3-142">提交草稿集合后会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="90cc3-142">What happens after you commit a draft collection</span></span>

<span data-ttu-id="90cc3-143">将草稿集合提交到审阅集时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="90cc3-143">When you commit a draft collection to a review set, the following things happen:</span></span>

- <span data-ttu-id="90cc3-144">再次运行集合搜索查询。</span><span class="sxs-lookup"><span data-stu-id="90cc3-144">The collection search query is run again.</span></span> <span data-ttu-id="90cc3-145">这意味着复制到审阅集的实际搜索结果可能不同于上次运行集合搜索时返回的估计结果。</span><span class="sxs-lookup"><span data-stu-id="90cc3-145">This means the actual search results copied to the review set may be different than the estimated results that were returned when the collection search was last run.</span></span>

- <span data-ttu-id="90cc3-146">搜索结果中的所有项目都从实时服务中的原始数据源复制，并复制到 Microsoft 云中的Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="90cc3-146">All items in the search results are copied from the original data source in the live service, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="90cc3-147">所有项目 (包括不在保管人或非保管人数据源中的内容和元数据 *)* 在名为深度索引) 的过程中对 (重新编制索引，以便审阅集内的所有数据在审查案例数据期间完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="90cc3-147">All items (including the content and metadata) that aren't located in custodian or non-custodian data sources are reindexed (in a process called *deep indexing*) so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="90cc3-148">当您在案例调查期间搜索或筛选审阅集中的内容时，对集合中的内容重新建立索引会导致全面而快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="90cc3-148">Reindexing the content in a collection results in thorough and fast searches when you search or filter the content in the review set during the case investigation.</span></span>

- <span data-ttu-id="90cc3-149">在SharePoint OneDrive审阅集时，将解密在搜索结果中返回的加密文档和加密文件以及附加电子邮件的文档和加密文件。</span><span class="sxs-lookup"><span data-stu-id="90cc3-149">Encrypted SharePoint and OneDrive documents and encrypted files attached email messages that's returned in the search results are decrypted when you commit the collection to a review set.</span></span> <span data-ttu-id="90cc3-150">可以在审阅集内查看和查询解密的文件。</span><span class="sxs-lookup"><span data-stu-id="90cc3-150">You can review and query the decrypted files in the review set.</span></span> <span data-ttu-id="90cc3-151">有关详细信息，请参阅解密[Microsoft 365电子数据展示工具。](ediscovery-decryption.md)</span><span class="sxs-lookup"><span data-stu-id="90cc3-151">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

- <span data-ttu-id="90cc3-152">光学字符识别 (OCR) 功能从图像中提取文本，并包括图像文本以及已添加到审阅集的内容。</span><span class="sxs-lookup"><span data-stu-id="90cc3-152">Optical character recognition (OCR) functionality extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="90cc3-153">有关详细信息，请参阅本文 [中的光学](#optical-character-recognition) 字符识别部分。</span><span class="sxs-lookup"><span data-stu-id="90cc3-153">For more information, see the [Optical character recognition](#optical-character-recognition) section in this article.</span></span>

- <span data-ttu-id="90cc3-154">成功完成提交后，"集合"选项卡上 **的状态列的值** 将更改为 `Committed` 。</span><span class="sxs-lookup"><span data-stu-id="90cc3-154">After the commit is successfully completed, the value of the status column of on the **Collections** tab is changed to `Committed`.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="90cc3-155">光学字符识别</span><span class="sxs-lookup"><span data-stu-id="90cc3-155">Optical character recognition</span></span>

<span data-ttu-id="90cc3-156">将集合提交到审阅集时，Advanced eDiscovery 中的光学字符识别 (OCR) 功能会自动从图像中提取文本，并包括图像文本以及添加到审阅集中的内容。</span><span class="sxs-lookup"><span data-stu-id="90cc3-156">When you commit a collection to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="90cc3-157">可以在审阅集内所选图像文件的文本查看器中查看提取的文本。</span><span class="sxs-lookup"><span data-stu-id="90cc3-157">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="90cc3-158">通过此功能，你可以对图像中的文本进行进一步审阅和分析。</span><span class="sxs-lookup"><span data-stu-id="90cc3-158">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="90cc3-159">OCR 支持松散文件、电子邮件附件和嵌入图像。</span><span class="sxs-lookup"><span data-stu-id="90cc3-159">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="90cc3-160">有关 OCR 支持的图像文件格式列表，请参阅[高级电子数据展示中受支持的文件类型](supported-filetypes-ediscovery20.md#image)。</span><span class="sxs-lookup"><span data-stu-id="90cc3-160">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="90cc3-161">必须针对在高级电子数据展示中创建的每个案例启用 OCR 功能。</span><span class="sxs-lookup"><span data-stu-id="90cc3-161">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="90cc3-162">有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="90cc3-162">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
