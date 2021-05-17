---
title: 查看Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解对话中的对话重建功能Advanced eDiscovery (对话线程) ，以重新构建、查看和导出 Microsoft Teams 和 Yammer 对话。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838301"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a><span data-ttu-id="50a36-103">对话线程Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="50a36-103">Conversation threading in Advanced eDiscovery</span></span>

<span data-ttu-id="50a36-104">即时消息是一种在大型受众中提问、分享想法或快速沟通的便捷方式。</span><span class="sxs-lookup"><span data-stu-id="50a36-104">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="50a36-105">由于即时消息平台（如 Microsoft Teams 和 Yammer 组）成为企业协作的核心，组织必须评估其电子数据展示工作流如何处理这些新的通信和协作形式。</span><span class="sxs-lookup"><span data-stu-id="50a36-105">As instant messaging platforms, like Microsoft Teams and Yammer groups, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span>

<span data-ttu-id="50a36-106">对话重建功能Advanced eDiscovery旨在帮助您识别上下文内容并生成不同的对话视图。</span><span class="sxs-lookup"><span data-stu-id="50a36-106">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="50a36-107">此功能使您可以高效快速地查看完整的即时消息对话 (也称为线程) 对话，这些对话是在 Microsoft Teams等平台中生成的。</span><span class="sxs-lookup"><span data-stu-id="50a36-107">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="50a36-108">通过对话重建，可以使用内置功能来重新构造、审阅和导出线程对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-108">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="50a36-109">使用Advanced eDiscovery对话重建来：</span><span class="sxs-lookup"><span data-stu-id="50a36-109">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="50a36-110">保留对话中所有邮件的唯一消息级别元数据。</span><span class="sxs-lookup"><span data-stu-id="50a36-110">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="50a36-111">收集与搜索结果相关的上下文消息。</span><span class="sxs-lookup"><span data-stu-id="50a36-111">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="50a36-112">查看、注释和修订线程对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-112">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="50a36-113">导出单个消息或线程对话</span><span class="sxs-lookup"><span data-stu-id="50a36-113">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="50a36-114">术语</span><span class="sxs-lookup"><span data-stu-id="50a36-114">Terminology</span></span>

<span data-ttu-id="50a36-115">下面是帮助您开始使用对话重建的一些定义。</span><span class="sxs-lookup"><span data-stu-id="50a36-115">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="50a36-116">**邮件：** 表示对话中最小的单元。</span><span class="sxs-lookup"><span data-stu-id="50a36-116">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="50a36-117">邮件的大小、结构和元数据可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="50a36-117">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="50a36-118">**对话：** 表示一个或多个邮件的分组。</span><span class="sxs-lookup"><span data-stu-id="50a36-118">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="50a36-119">跨不同的应用程序，对话可能以不同方式表示。</span><span class="sxs-lookup"><span data-stu-id="50a36-119">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="50a36-120">在某些应用程序中，有一个显式操作会导致答复现有邮件。</span><span class="sxs-lookup"><span data-stu-id="50a36-120">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="50a36-121">对话是此用户操作显式形成的。</span><span class="sxs-lookup"><span data-stu-id="50a36-121">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="50a36-122">例如，下面是当前频道对话的屏幕截图Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="50a36-122">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft Teams频道对话](../media/threadedchat.png)

   <span data-ttu-id="50a36-124">在其他应用 (例如 Teams) 中的 1xN 聊天消息，没有正式的回复链，而是消息在单个线程中显示为"消息的平面流"。</span><span class="sxs-lookup"><span data-stu-id="50a36-124">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="50a36-125">在这些类型的应用中，对话从特定时间发生的一组消息中推断得出。</span><span class="sxs-lookup"><span data-stu-id="50a36-125">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="50a36-126">这种消息"软分组" (而不是回复链) 表示有关特定关注主题的"来回"对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-126">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span>

## <a name="step-1-create-a-draft-collection"></a><span data-ttu-id="50a36-127">步骤 1：创建草稿集合</span><span class="sxs-lookup"><span data-stu-id="50a36-127">Step 1: Create a draft collection</span></span>

<span data-ttu-id="50a36-128">确定相关保管人和内容位置后，可以创建搜索以查找潜在相关内容。</span><span class="sxs-lookup"><span data-stu-id="50a36-128">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="50a36-129">在"**集合**"选项卡上的Advanced eDiscovery，可以通过单击"新建集合"并遵循向导来创建集合。</span><span class="sxs-lookup"><span data-stu-id="50a36-129">On the **Collections** tab in the Advanced eDiscovery case, you can create a collection by clicking **New collection** and following the wizard.</span></span> <span data-ttu-id="50a36-130">若要了解如何创建集合、生成搜索查询和预览搜索结果，请参阅 [创建草稿集合](create-draft-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="50a36-130">For information about how you can create a collection, build a search query, and preview the search results, see [Create a draft collection](create-draft-collection.md).</span></span>

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="50a36-131">步骤 2：将草稿集合提交到审阅集</span><span class="sxs-lookup"><span data-stu-id="50a36-131">Step 2: Commit a draft collection to a review set</span></span>

<span data-ttu-id="50a36-132">查看并完成集合中的搜索查询后，可以将搜索结果添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="50a36-132">After you have reviewed and finalized the search query in a collection, you can add the search results to a review set.</span></span> <span data-ttu-id="50a36-133">当您将搜索结果添加到审阅集时，原始数据将复制到Azure 存储区域以方便审阅和分析过程。</span><span class="sxs-lookup"><span data-stu-id="50a36-133">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="50a36-134">有关向审阅集添加搜索结果的信息，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md)。</span><span class="sxs-lookup"><span data-stu-id="50a36-134">For more information about adding search results to a review set, see [Commit a draft collection to a review set](commit-draft-collection.md).</span></span>

<span data-ttu-id="50a36-135">将对话中的项目添加到审阅集时，可以使用线程对话选项从包含与集合的搜索条件匹配的项目的对话中收集上下文消息。</span><span class="sxs-lookup"><span data-stu-id="50a36-135">When you add items from conversations to a review set, you can use the threaded conversations option to collect contextual messages from conversations that contain items that match the search criteria of the collection.</span></span> <span data-ttu-id="50a36-136">选择线程对话选项后，可能会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="50a36-136">After you select the thread conversations option, the following things can happen:</span></span>

  ![对话检索](../media/messagesandconversations.png)
  
1. <span data-ttu-id="50a36-138">使用关键字和日期范围查询，搜索返回了邮件 *3 的命中*。</span><span class="sxs-lookup"><span data-stu-id="50a36-138">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="50a36-139">此消息属于大型对话的一部分，如 *CRC1 所示*。</span><span class="sxs-lookup"><span data-stu-id="50a36-139">This message was part of a larger conversation, illustrated by *CRC1*.</span></span>
  
2. <span data-ttu-id="50a36-140">当你将数据添加到审阅集并启用对话检索选项时，Advanced eDiscovery返回并收集 *CRC1* 中的其他项目。</span><span class="sxs-lookup"><span data-stu-id="50a36-140">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span>
  
3. <span data-ttu-id="50a36-141">将项目添加到审阅集后，你可以查看来自 *CRC1* 的所有单个邮件。</span><span class="sxs-lookup"><span data-stu-id="50a36-141">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span>

<span data-ttu-id="50a36-142">若要启用线程对话选项，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="50a36-142">To enabled the threaded conversations option, see [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set).</span></span>
  
## <a name="step-3-review-and-export-threaded-conversations"></a><span data-ttu-id="50a36-143">步骤 3：查看和导出线程对话</span><span class="sxs-lookup"><span data-stu-id="50a36-143">Step 3: Review and export threaded conversations</span></span>

<span data-ttu-id="50a36-144">处理内容并添加到审阅集后，您可以开始查看审阅集内的数据。</span><span class="sxs-lookup"><span data-stu-id="50a36-144">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="50a36-145">根据内容是添加到标准审阅集还是对话审阅集，审阅功能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="50a36-145">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span>

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="50a36-146">查看标准审阅集内的对话</span><span class="sxs-lookup"><span data-stu-id="50a36-146">Reviewing conversations in a standard review set</span></span>

<span data-ttu-id="50a36-147">在标准审阅集，处理邮件并显示为单个项目，类似于邮件存储在邮箱文件夹中的方式。</span><span class="sxs-lookup"><span data-stu-id="50a36-147">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="50a36-148">在此工作流中，每封邮件都作为单独的项目进行处理。</span><span class="sxs-lookup"><span data-stu-id="50a36-148">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="50a36-149">因此，按线索设置的摘要和导出选项在标准审阅集内不可用。</span><span class="sxs-lookup"><span data-stu-id="50a36-149">As a result, the threaded summary and export options aren't available in a standard review set.</span></span>

  ![标准审阅集](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="50a36-151">查看对话审阅集内的对话</span><span class="sxs-lookup"><span data-stu-id="50a36-151">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="50a36-152">在对话审阅集内，将各个消息进行线程处理，并呈现为对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-152">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="50a36-153">这样，你可以查看和导出上下文对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-153">This lets you review and export contextual conversations.</span></span> 

  ![对话审阅集](../media/ConversationRSOptions.PNG)

<span data-ttu-id="50a36-155">以下各节介绍审阅和导出对话审阅集内的对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-155">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="50a36-156">查看对话</span><span class="sxs-lookup"><span data-stu-id="50a36-156">Reviewing conversations</span></span>

<span data-ttu-id="50a36-157">在对话审阅集内，可以使用以下选项促进审阅过程。</span><span class="sxs-lookup"><span data-stu-id="50a36-157">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="50a36-158">**按对话分组：** 将同一对话中的邮件分组在一起，以帮助用户简化和加快审阅过程。</span><span class="sxs-lookup"><span data-stu-id="50a36-158">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span>

- <span data-ttu-id="50a36-159">**摘要视图：** 显示线程对话。</span><span class="sxs-lookup"><span data-stu-id="50a36-159">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="50a36-160">在此视图中，您可以查看整个对话，还可以访问每封邮件的元数据。</span><span class="sxs-lookup"><span data-stu-id="50a36-160">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="50a36-161">查看单个邮件的元数据</span><span class="sxs-lookup"><span data-stu-id="50a36-161">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="50a36-162">下载单个邮件</span><span class="sxs-lookup"><span data-stu-id="50a36-162">Download individual messages</span></span>

- <span data-ttu-id="50a36-163">**文本视图：** 提供整个对话的提取文本。</span><span class="sxs-lookup"><span data-stu-id="50a36-163">**Text view:** Provides the extracted text for the entire conversation.</span></span>

- <span data-ttu-id="50a36-164">**批注视图：** 允许你标记对话的线程视图。</span><span class="sxs-lookup"><span data-stu-id="50a36-164">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="50a36-165">对话中所有邮件共享同一批注文档。</span><span class="sxs-lookup"><span data-stu-id="50a36-165">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="50a36-166">**标记：** 查看审阅集内的对话时，可以通过单击"编码"面板中的"标记"面板 **来查看和应用** 标记。</span><span class="sxs-lookup"><span data-stu-id="50a36-166">**Tagging:** When viewing conversations in a review set, you can view and apply tags by clicking **Tagging panel** in the Coding panel.</span></span>

- <span data-ttu-id="50a36-167">**重新运行对话转换：** 将邮件添加到对话审阅集时，将自动运行转换作业以创建线程摘要并注释视图。</span><span class="sxs-lookup"><span data-stu-id="50a36-167">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="50a36-168">如果对话重建作业失败，可以通过单击"操作"> **审阅集创建** 对话 PDF 来重新运行此作业。</span><span class="sxs-lookup"><span data-stu-id="50a36-168">If the Conversation Reconstruction job fails, you can rerun this job by clicking **Action > Create conversation PDFs** in the review set.</span></span>

#### <a name="exporting-conversations"></a><span data-ttu-id="50a36-169">导出对话</span><span class="sxs-lookup"><span data-stu-id="50a36-169">Exporting conversations</span></span>

<span data-ttu-id="50a36-170">在对话审阅集内，可以设置以下选项来导出对话：</span><span class="sxs-lookup"><span data-stu-id="50a36-170">In a conversation review set, you can set the following options to export conversations:</span></span>

![导出对话选项](../media/export.png)

<span data-ttu-id="50a36-172">a.</span><span class="sxs-lookup"><span data-stu-id="50a36-172">a.</span></span> <span data-ttu-id="50a36-173">元数据选项</span><span class="sxs-lookup"><span data-stu-id="50a36-173">Metadata options</span></span>

   - <span data-ttu-id="50a36-174">**加载文件：** 每个单独的邮件、电子邮件和文档都包含元数据。</span><span class="sxs-lookup"><span data-stu-id="50a36-174">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="50a36-175">对话中每条消息有一行。</span><span class="sxs-lookup"><span data-stu-id="50a36-175">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="50a36-176">**标记：** 来自审阅过程的标记包含在元数据文件中。</span><span class="sxs-lookup"><span data-stu-id="50a36-176">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="50a36-177">对话中的邮件共享相同的标记。</span><span class="sxs-lookup"><span data-stu-id="50a36-177">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="50a36-178">b.</span><span class="sxs-lookup"><span data-stu-id="50a36-178">b.</span></span> <span data-ttu-id="50a36-179">对话选项</span><span class="sxs-lookup"><span data-stu-id="50a36-179">Conversation options</span></span>
  
   - <span data-ttu-id="50a36-180">**对话文件：** 导出对话文件时，批注视图将转换为 PDF 文件并下载到导出文件夹。</span><span class="sxs-lookup"><span data-stu-id="50a36-180">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="50a36-181">一个对话文件中的消息指向同一对话文件的 PDF 版本。</span><span class="sxs-lookup"><span data-stu-id="50a36-181">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="50a36-182">**单个聊天消息：** 导出单个邮件时，对话中每个唯一的邮件都导出为独立项目。</span><span class="sxs-lookup"><span data-stu-id="50a36-182">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="50a36-183">以与邮箱中相同的格式导出文件。</span><span class="sxs-lookup"><span data-stu-id="50a36-183">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="50a36-184">对于特定对话，您将收到多个 .msg 文件。</span><span class="sxs-lookup"><span data-stu-id="50a36-184">For a specific conversation, you receive multiple .msg files.</span></span>

     >[!NOTE]
     > <span data-ttu-id="50a36-185">如果对会话文件应用了批注，这些批注将不会传输到各个邮件。</span><span class="sxs-lookup"><span data-stu-id="50a36-185">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span>

<span data-ttu-id="50a36-186">c.</span><span class="sxs-lookup"><span data-stu-id="50a36-186">c.</span></span> <span data-ttu-id="50a36-187">其他选项</span><span class="sxs-lookup"><span data-stu-id="50a36-187">Other options</span></span>

   - <span data-ttu-id="50a36-188">**生成所有导出内容的文本文件：** 为从审阅集导出的每个对话生成一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="50a36-188">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span>

   - <span data-ttu-id="50a36-189">**将导出的内容替换为修订的 PDF：** 如果在审阅过程中生成修订的对话文件，则这些文件在导出过程中可用。</span><span class="sxs-lookup"><span data-stu-id="50a36-189">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="50a36-190">可以通过不选择此选项) 来决定是仅导出本机文件 (，还是将本机文件替换为已修订版本的本机文件 (，方法为选择此选项) （导出为 PDF 文件）。</span><span class="sxs-lookup"><span data-stu-id="50a36-190">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="50a36-191">详细信息</span><span class="sxs-lookup"><span data-stu-id="50a36-191">More information</span></span>

<span data-ttu-id="50a36-192">若要详细了解如何查看 Advanced eDiscovery中的情况数据，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="50a36-192">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="50a36-193">查看案例数据</span><span class="sxs-lookup"><span data-stu-id="50a36-193">View case data</span></span>](view-documents-in-review-set.md)

- [<span data-ttu-id="50a36-194">分析事例数据</span><span class="sxs-lookup"><span data-stu-id="50a36-194">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="50a36-195">导出事例数据</span><span class="sxs-lookup"><span data-stu-id="50a36-195">Export case data</span></span>](exporting-data-ediscover20.md)
