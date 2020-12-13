---
title: 查看高级电子数据展示中的分析结果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 了解在何处查看高级电子数据展示中分析过程的结果，包括显示的任务选项的定义。
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663252"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="f8762-103">View Analyze results in Advanced eDiscovery (classic) </span><span class="sxs-lookup"><span data-stu-id="f8762-103">View Analyze results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="f8762-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="f8762-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f8762-106">在高级电子数据展示中，可在各种显示器中查看分析过程的进度和结果，如下所述。</span><span class="sxs-lookup"><span data-stu-id="f8762-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="f8762-107">查看"分析任务状态"</span><span class="sxs-lookup"><span data-stu-id="f8762-107">View Analyze task status</span></span>

<span data-ttu-id="f8762-108">在 **" \> 准备 \> 分析结果 \> 任务"状态** 中，状态在分析进程执行期间和之后显示。</span><span class="sxs-lookup"><span data-stu-id="f8762-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![分析任务状态](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="f8762-110">显示的任务可能因所选选项而异。</span><span class="sxs-lookup"><span data-stu-id="f8762-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="f8762-111">**ND/ET： setup：** Prepares for the run， for example， sets run and case parameters.</span><span class="sxs-lookup"><span data-stu-id="f8762-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="f8762-112">**ND/ET：ND 计算**：处理文件的几乎重复分析。</span><span class="sxs-lookup"><span data-stu-id="f8762-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="f8762-113">**ND/ET：ET 计算**：对整个电子邮件集执行电子邮件线程分析。</span><span class="sxs-lookup"><span data-stu-id="f8762-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="f8762-114">**ND/ET：透视和相似性**：执行透视和文件相似性处理。</span><span class="sxs-lookup"><span data-stu-id="f8762-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="f8762-115">**ND/ET：元数据更新**：完成对数据库中的文件收集的新数据。</span><span class="sxs-lookup"><span data-stu-id="f8762-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="f8762-116">**主题：主题计算**：运行主题分析。</span><span class="sxs-lookup"><span data-stu-id="f8762-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="f8762-117"> (选中时显示) </span><span class="sxs-lookup"><span data-stu-id="f8762-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="f8762-118">**任务状态**：此行在任务完成之后显示。</span><span class="sxs-lookup"><span data-stu-id="f8762-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="f8762-119">任务正在运行时，将显示运行持续时间。</span><span class="sxs-lookup"><span data-stu-id="f8762-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f8762-120">ND 和 ED (的") "结果适用于要处理的文档数。</span><span class="sxs-lookup"><span data-stu-id="f8762-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="f8762-121">它不包含完全相同的文件。</span><span class="sxs-lookup"><span data-stu-id="f8762-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="f8762-122">查看"近重复项"和"电子邮件线程"状态</span><span class="sxs-lookup"><span data-stu-id="f8762-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="f8762-123">目标 **总体** 结果显示目标总体中的文档、电子邮件、附件和错误数。</span><span class="sxs-lookup"><span data-stu-id="f8762-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="f8762-124">" **文档** "结果显示透视表的数量、唯一的近重复项和确切的重复文件。</span><span class="sxs-lookup"><span data-stu-id="f8762-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="f8762-125">" **电子邮件"** 结果显示非独占、非独占减号、唯一非独占副本数以及电子邮件的其余部分数。</span><span class="sxs-lookup"><span data-stu-id="f8762-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="f8762-126">不同类型的电子邮件结果包括：</span><span class="sxs-lookup"><span data-stu-id="f8762-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="f8762-127">**非** 独占：非独占电子邮件是电子邮件线程中的终止节点，包含该线程之前的所有历史记录。</span><span class="sxs-lookup"><span data-stu-id="f8762-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="f8762-128">因此，审阅者可以安全地关注非独占电子邮件，而无需阅读线程中的之前邮件。</span><span class="sxs-lookup"><span data-stu-id="f8762-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="f8762-129">**非独占减**：如果包含邮件的父邮件有一个或多个不同的附件，则非独占电子邮件被指定为非独占邮件减号。</span><span class="sxs-lookup"><span data-stu-id="f8762-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="f8762-130">在此上下文中，术语 Parent 用于位于电子邮件线程上向上的邮件或该特定非独占电子邮件中包含的对话。</span><span class="sxs-lookup"><span data-stu-id="f8762-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="f8762-131">审阅者可以使用非独占减号指示作为一个信号，指示尽管可能不需要查看非独占电子邮件父项的内容，但查看与非独占路径父项关联的附件可能很有用。</span><span class="sxs-lookup"><span data-stu-id="f8762-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="f8762-132">**非独占副本**：如果包含电子邮件是标记为非独占或非独占减号的另一封邮件的副本，则非独占电子邮件被指定为非独占副本。</span><span class="sxs-lookup"><span data-stu-id="f8762-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="f8762-133">换句话说，此消息的主题和正文与另一个包含邮件的主题和正文相同，因此，共同驻留在同一节点中。</span><span class="sxs-lookup"><span data-stu-id="f8762-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="f8762-134">由于非独占副本邮件包含相同的内容，因此通常可以在审阅过程中跳过这些内容。</span><span class="sxs-lookup"><span data-stu-id="f8762-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="f8762-135">**其余** 部分：这表示不包含任何唯一内容的电子邮件，因此不会属于前三个类别的任何类别。</span><span class="sxs-lookup"><span data-stu-id="f8762-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="f8762-136">无需查看这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f8762-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="f8762-137">如果邮件包含的附件不在以后包含的电子邮件中，可能需要查看附件。</span><span class="sxs-lookup"><span data-stu-id="f8762-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="f8762-138">这由主题中是否存在非独占减号电子邮件表示。</span><span class="sxs-lookup"><span data-stu-id="f8762-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="f8762-139">附件 **结果** 根据唯一和重复的类型显示附件数。</span><span class="sxs-lookup"><span data-stu-id="f8762-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![近似重复和电子邮件线程](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="f8762-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8762-141">See also</span></span>

[<span data-ttu-id="f8762-142">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="f8762-142">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f8762-143">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="f8762-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f8762-144">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="f8762-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f8762-145">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="f8762-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="f8762-146">设置 分析高级设置</span><span class="sxs-lookup"><span data-stu-id="f8762-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

