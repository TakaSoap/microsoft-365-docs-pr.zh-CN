---
title: 查看过程模块在高级电子数据展示中的结果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 了解如何在高级电子数据展示中查找进程模块运行的结果，包括任务状态和流程摘要。
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663255"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="b916d-103">View Process module results in Advanced eDiscovery (classic) </span><span class="sxs-lookup"><span data-stu-id="b916d-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="b916d-104">启动 **"** \> **准备** 过程"后，可以查看进度和结果。</span><span class="sxs-lookup"><span data-stu-id="b916d-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b916d-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="b916d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="b916d-107">处理任务状态</span><span class="sxs-lookup"><span data-stu-id="b916d-107">Process task status</span></span>

<span data-ttu-id="b916d-108">在 **"准备** 进程结果"中， (如果进程当前正在运行) 或上一个进程状态任务状态，如以下示例 \>  \> 所示。</span><span class="sxs-lookup"><span data-stu-id="b916d-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![进程模块任务状态](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="b916d-110">显示的任务可能因所选的"进程"选项而异。</span><span class="sxs-lookup"><span data-stu-id="b916d-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="b916d-111">**清单**：高级电子数据展示会访问为 Process 选择的所有文件，并执行基本数据收集。</span><span class="sxs-lookup"><span data-stu-id="b916d-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="b916d-112">**计算签名**：计算 MD5 数字签名。</span><span class="sxs-lookup"><span data-stu-id="b916d-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="b916d-113">**复合提取**：以递归方式从复合文件（如 PST、ZIP、MSG (）中以递归方式提取内部或包含) 。</span><span class="sxs-lookup"><span data-stu-id="b916d-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="b916d-114">解压缩的文件存储在大小写文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b916d-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="b916d-115">**同步数据库：内部** 数据库进程。</span><span class="sxs-lookup"><span data-stu-id="b916d-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="b916d-116">**文件副本**：复制进程文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="b916d-117">此任务始终显示，即使选择了高级复制文件选项。</span><span class="sxs-lookup"><span data-stu-id="b916d-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="b916d-118">**文本提取**：存在本机文件时，高级电子数据展示使用 DTSearch 从这些文件中提取文本。</span><span class="sxs-lookup"><span data-stu-id="b916d-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="b916d-119">这些文件的提取文本作为文本文件存储在 case 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b916d-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="b916d-120">**更新元数据**：处理加载的元数据。</span><span class="sxs-lookup"><span data-stu-id="b916d-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="b916d-121">**完成：** 完成内部处理，以完成已加载 (文件的数据，例如，标识错误和成功) 。</span><span class="sxs-lookup"><span data-stu-id="b916d-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="b916d-122">任务状态：在任务完成之后显示。</span><span class="sxs-lookup"><span data-stu-id="b916d-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="b916d-123">任务正在运行时，将显示运行持续时间。</span><span class="sxs-lookup"><span data-stu-id="b916d-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b916d-124">已完成的任务可能还包括已完成处理的文件或出现错误的文件的总计。</span><span class="sxs-lookup"><span data-stu-id="b916d-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="b916d-125">"Cancel"提供了一个回滚选项，用于停止进程执行，然后回滚到以前的数据填充或保存的已处理数据。</span><span class="sxs-lookup"><span data-stu-id="b916d-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="b916d-126">回滚将清除所有已处理的数据。</span><span class="sxs-lookup"><span data-stu-id="b916d-126">Rollback clears all processed data.</span></span> <span data-ttu-id="b916d-127">例如，如果您不希望已处理的数据丢失 (，则计划重新加载这些文件) ，请在此窗口中选择"取消"选项，以选择不回滚。</span><span class="sxs-lookup"><span data-stu-id="b916d-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="b916d-128">流程摘要</span><span class="sxs-lookup"><span data-stu-id="b916d-128">Process summary</span></span>

<span data-ttu-id="b916d-129">在" \> 准备进程结果流程"摘要中，根据成功的文件处理和错误结果显示已加载文件结果 \> \> 的细目。</span><span class="sxs-lookup"><span data-stu-id="b916d-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="b916d-130">这些窗格以图形方式显示导入的文件统计信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b916d-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="b916d-131">**进程摘要累计** d：案例内的所有文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-131">**Process summary accumulate** d: All files in the case.</span></span>
    
- <span data-ttu-id="b916d-132">**最后一个进程摘要**：从最后一个会话或操作加载的文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="b916d-133">**最后一个** 系列：如果有任何数据， (家庭) 。</span><span class="sxs-lookup"><span data-stu-id="b916d-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="b916d-134">如果 **添加了种子** 文件，则针对为文件定义的每个问题列出种子文件的数量。</span><span class="sxs-lookup"><span data-stu-id="b916d-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="b916d-135">如果" **种子"文件的** 标记失败，也会说明这一点。</span><span class="sxs-lookup"><span data-stu-id="b916d-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="b916d-136">如果 **添加了预标记** 文件，则针对为文件定义的每个问题列出预标记文件的数量。</span><span class="sxs-lookup"><span data-stu-id="b916d-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="b916d-137">如果预标记 **文件的** 标记失败，则说明这一点。</span><span class="sxs-lookup"><span data-stu-id="b916d-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![进程模块摘要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="b916d-139">流程摘要累计和最后一个图表</span><span class="sxs-lookup"><span data-stu-id="b916d-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="b916d-140">左侧栏包括源 + 解压缩的文件：即找到的所有文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="b916d-141">右侧栏"已处理"包括：</span><span class="sxs-lookup"><span data-stu-id="b916d-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="b916d-142">加载错误的文件</span><span class="sxs-lookup"><span data-stu-id="b916d-142">Files with load errors</span></span>
    
- <span data-ttu-id="b916d-143">已成功加载文件，其中可能包括：</span><span class="sxs-lookup"><span data-stu-id="b916d-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="b916d-144">**现有**：之前加载且现在重新加载的文件 (包括重复) 。</span><span class="sxs-lookup"><span data-stu-id="b916d-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="b916d-145">**文本**：具有文本的唯一文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="b916d-146">**非文本**：空文本文件、空本机文本文件、本机非文本文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="b916d-147">**重复** 项：包含文本的重复文件。</span><span class="sxs-lookup"><span data-stu-id="b916d-147">**Duplicate** s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="b916d-148">上一个进程错误</span><span class="sxs-lookup"><span data-stu-id="b916d-148">Last process errors</span></span>

<span data-ttu-id="b916d-149">在"准备进程结果最后一个进程错误"中，将显示上一个 \> \> 会话或 \> 执行的操作中错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b916d-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![进程模块错误](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="b916d-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b916d-151">See also</span></span>

[<span data-ttu-id="b916d-152">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="b916d-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b916d-153">运行进程模块并加载数据</span><span class="sxs-lookup"><span data-stu-id="b916d-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

