---
title: 设置负载以在高级电子数据展示中添加导入的文件
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 在高级电子数据展示中执行相关性培训之前，请查看将导入的文件添加到上次定义的加载或批量文件的步骤。
ms.openlocfilehash: 7cd244ba1ba516c2b7376b71e809b4c01ff5df8b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663477"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a><span data-ttu-id="f71a3-103">设置负载以在高级电子数据展示和经典 (中添加) </span><span class="sxs-lookup"><span data-stu-id="f71a3-103">Set up loads to add imported files in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="f71a3-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="f71a3-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f71a3-106">在高级电子数据展示中，负载是添加到案例的新文件批处理。</span><span class="sxs-lookup"><span data-stu-id="f71a3-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="f71a3-107">默认情况下，定义一个负载，并添加所有导入的文件。</span><span class="sxs-lookup"><span data-stu-id="f71a3-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="f71a3-108">在执行相关性培训之前，必须将导入的文件添加到加载中。</span><span class="sxs-lookup"><span data-stu-id="f71a3-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="f71a3-109">请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="f71a3-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="f71a3-110">新文件已知类似于之前加载到案例数据库的文件，或者以前的文件加载是文件集合中的随机集。</span><span class="sxs-lookup"><span data-stu-id="f71a3-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="f71a3-111">在此实例中，将导入的文件添加到当前文件加载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="f71a3-112">新文件不同于以前的 (，例如，来自不同的源) ，或者你之前不知道它们与以前的加载相似或不同。</span><span class="sxs-lookup"><span data-stu-id="f71a3-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="f71a3-113">在此方案中，将导入的文件添加到新的文件加载中。</span><span class="sxs-lookup"><span data-stu-id="f71a3-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="f71a3-114">高级电子数据展示将此功能识别为滚动加载方案，调用捕获过程，锁定相关性培训和批计算，直到完成跟进，并且集成并训练新的负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="f71a3-115">将导入的文件添加到当前负载</span><span class="sxs-lookup"><span data-stu-id="f71a3-115">Adding imported files to the current load</span></span>

<span data-ttu-id="f71a3-116">所有导入的文件都必须添加到负载中，以在高级电子数据展示中进行处理。</span><span class="sxs-lookup"><span data-stu-id="f71a3-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="f71a3-117">导入的文件将添加到上次定义的负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="f71a3-118">如果稍后导入其他文件，还必须将其添加到加载中。</span><span class="sxs-lookup"><span data-stu-id="f71a3-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="f71a3-119">在 **"相关性 \> 相关性设置"选项卡** 中，选择"加载 **"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![相关性设置加载选项卡](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="f71a3-121">**包括文件**：选择要包含的文件的选项。</span><span class="sxs-lookup"><span data-stu-id="f71a3-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="f71a3-122">默认情况下，将文件添加到当前负载基于"所有文件"总体。</span><span class="sxs-lookup"><span data-stu-id="f71a3-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f71a3-123">将所有可用的剔除文件加载到相关性中。</span><span class="sxs-lookup"><span data-stu-id="f71a3-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="f71a3-124">如果计划仅加载可用文件的子集，请先咨询支持人员，因为加载子集可能会对相关性培训产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="f71a3-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="f71a3-125">在 **"加载管理**"中，选择一个负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="f71a3-126">单击 **"添加文件"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-126">Click **Add files**.</span></span> <span data-ttu-id="f71a3-127">文件将添加到加载中，并显示确认消息。</span><span class="sxs-lookup"><span data-stu-id="f71a3-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="f71a3-128">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="f71a3-128">Click **OK**.</span></span>
    
<span data-ttu-id="f71a3-129">现在可以在高级电子数据展示相关性中处理文件，以培训文件。</span><span class="sxs-lookup"><span data-stu-id="f71a3-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="f71a3-130">编辑案例内的加载名称</span><span class="sxs-lookup"><span data-stu-id="f71a3-130">Editing a load name within a case</span></span>

<span data-ttu-id="f71a3-131">如果更改加载名称，建议使用对情况重要的名称。</span><span class="sxs-lookup"><span data-stu-id="f71a3-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="f71a3-132">在 **"相关性 \> 相关性设置"选项卡** 中，选择"加载 **"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="f71a3-133">从 **"加载管理** "列表中，选择一个加载并单击 **"编辑"** 图标。</span><span class="sxs-lookup"><span data-stu-id="f71a3-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="f71a3-134">将显示"编辑加载"窗口。</span><span class="sxs-lookup"><span data-stu-id="f71a3-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="f71a3-135">输入更改，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="f71a3-136">将导入的文件添加到新负载</span><span class="sxs-lookup"><span data-stu-id="f71a3-136">Adding imported files to a new load</span></span>

<span data-ttu-id="f71a3-137">开始相关性培训或执行批量计算后，您可能需要导入并处理一组额外的文件。</span><span class="sxs-lookup"><span data-stu-id="f71a3-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="f71a3-138">在"捕获"期间，可以创建、标记和分析"捕获"集。</span><span class="sxs-lookup"><span data-stu-id="f71a3-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="f71a3-139">高级电子数据展示将其新负载中相关和非相关文件的评估与之前加载中的评估进行比较。</span><span class="sxs-lookup"><span data-stu-id="f71a3-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="f71a3-140">根据结果，系统将提示你在必要时做出跟进决策，高级电子数据展示根据累积的相关性信息提供建议。</span><span class="sxs-lookup"><span data-stu-id="f71a3-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="f71a3-141">滚动加载和跟进功能会有所不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f71a3-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="f71a3-142">在批计算后导入新文件负载时，高级电子数据展示将确定文件属于以下类别之一的程度：</span><span class="sxs-lookup"><span data-stu-id="f71a3-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="f71a3-143">类似 (同类) ：不需要新的自定义相关性培训轮，从上一负载中累积的知识可以"按如下方式"应用到新负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="f71a3-144">不同的 (异) ：需要新的自定义相关性培训轮，并且无法应用从上一负载获得的知识。</span><span class="sxs-lookup"><span data-stu-id="f71a3-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="f71a3-145">这些术语是指在加载之间而不是在加载内的文件的相似性级别。</span><span class="sxs-lookup"><span data-stu-id="f71a3-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="f71a3-146">在批量计算之前，在相关性 (导入新文件) ，利用"捕获"功能，可以继续联合文件集的相关性培训。</span><span class="sxs-lookup"><span data-stu-id="f71a3-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="f71a3-147">高级电子数据展示不会估计新负载是类似于还是不同于以前的负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="f71a3-148">它仅收集有关新负载的信息，并启用相关性培训以继续处理新的和以前的文件集。</span><span class="sxs-lookup"><span data-stu-id="f71a3-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="f71a3-149">当相关性培训中出现多个问题以及批计算后的问题时，将针对所有问题执行一次跟进过程，并计算并显示每个问题的结果。</span><span class="sxs-lookup"><span data-stu-id="f71a3-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f71a3-150">向上捕获示例的大小可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f71a3-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="f71a3-151">这取决于新负载相对于上一次加载的大小，以及添加新负载之前完成的示例数。</span><span class="sxs-lookup"><span data-stu-id="f71a3-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="f71a3-152">向上捕获示例通常是新负载中的一组 200 到 2，000 个文件。</span><span class="sxs-lookup"><span data-stu-id="f71a3-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f71a3-153">"向上捕获"将停止任何其他任务，并且需要单独的文件标记和审阅。</span><span class="sxs-lookup"><span data-stu-id="f71a3-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="f71a3-154">因此，可以在批量添加新文件时减少开销。</span><span class="sxs-lookup"><span data-stu-id="f71a3-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="f71a3-155">使用"向上跟进"和"滚动"加载添加新的文件负载</span><span class="sxs-lookup"><span data-stu-id="f71a3-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="f71a3-156">在 **"相关性 \> 相关性设置"选项卡** 中，选择"加载 **"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="f71a3-157">在 **"加载** 管理"下 **+** ，单击图标以添加负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="f71a3-158">将显示确认消息。</span><span class="sxs-lookup"><span data-stu-id="f71a3-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="f71a3-159">单击" **是**"即可继续。</span><span class="sxs-lookup"><span data-stu-id="f71a3-159">Click **Yes** to continue.</span></span> <span data-ttu-id="f71a3-160">将显示 **"添加新加载** "对话框。</span><span class="sxs-lookup"><span data-stu-id="f71a3-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f71a3-161">只有在对上一次加载执行了操作时，才能添加新负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="f71a3-162">在"**添加新加载"对话框中**，在 **"** 加载名称和说明"中键入信息，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="f71a3-163">高级电子数据展示可添加新负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="f71a3-164">若要导入新的加载文件，请单击"**添加文件"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="f71a3-165">所有新文件将添加到此加载中。</span><span class="sxs-lookup"><span data-stu-id="f71a3-165">All new files are added to this load.</span></span> <span data-ttu-id="f71a3-166">高级电子数据展示导入文件后，它将识别滚动加载方案，并指示下一步进行跟进。</span><span class="sxs-lookup"><span data-stu-id="f71a3-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="f71a3-167">单击 **对话框底部的** "向上捕获"以运行方案。</span><span class="sxs-lookup"><span data-stu-id="f71a3-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="f71a3-168">为允许并发文件标记的所有问题创建一个捕获集（通常包含新负载中的 200 至 2，000 个文件）。</span><span class="sxs-lookup"><span data-stu-id="f71a3-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="f71a3-169">详细介绍了负载是相似还是不同、高级电子数据展示是自动合并还是拆分负载，以及下一步中有关处理的信息。</span><span class="sxs-lookup"><span data-stu-id="f71a3-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="f71a3-170">然后，您可以标记文件并运行计算操作。</span><span class="sxs-lookup"><span data-stu-id="f71a3-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="f71a3-171">通过标记，相关性可以确定负载是相似还是不同，并使您能够继续处理新文件集。</span><span class="sxs-lookup"><span data-stu-id="f71a3-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="f71a3-172">查看"捕获"集后，查看" **相关性 \> 跟踪** "以查看"跟进"结果。</span><span class="sxs-lookup"><span data-stu-id="f71a3-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="f71a3-173">如果在相关性培训期间添加了新的文件负载 (这意味着问题尚未经过批计算 **) ，则** 继续培训是下一步，无论跟进结果如何。</span><span class="sxs-lookup"><span data-stu-id="f71a3-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="f71a3-174">新的和以前的负载作为一个负载进行处理，相关性培训在统一集合上继续。</span><span class="sxs-lookup"><span data-stu-id="f71a3-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="f71a3-175">现在已完成此过程，可以继续相关性培训。</span><span class="sxs-lookup"><span data-stu-id="f71a3-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="f71a3-176">如果在批计算后添加了新负载，请继续执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f71a3-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="f71a3-177">对于批计算后添加的新负载，高级电子数据展示将确定新负载是类似于还是不同于以前的负载，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f71a3-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="f71a3-178">如果发现负载相似：无需其他相关性培训。</span><span class="sxs-lookup"><span data-stu-id="f71a3-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="f71a3-179">仪表板显示建议的下一步是再次运行 \*\* 批处理计算 \*\* 以计算新负载的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="f71a3-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="f71a3-180">发现负载相似，因此可以在新文件上运行上一个分类器分析。</span><span class="sxs-lookup"><span data-stu-id="f71a3-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="f71a3-181">如果发现负载不同：需要更多相关性培训，下一步是"跟进"决策。</span><span class="sxs-lookup"><span data-stu-id="f71a3-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="f71a3-182">选择跟进决策，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f71a3-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="f71a3-183">如果选择" **合并加载"，** 则高级电子数据展示会合并培训集的上一个负载和新负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="f71a3-184">尽管第一个负载经过批计算，但需要更多培训。</span><span class="sxs-lookup"><span data-stu-id="f71a3-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="f71a3-185">继续同时培训新的和以前的负载。</span><span class="sxs-lookup"><span data-stu-id="f71a3-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="f71a3-186">然后，批处理计算将再次运行，并且应忽略以前的批处理计算分数。</span><span class="sxs-lookup"><span data-stu-id="f71a3-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="f71a3-187">在可以重新计算现有负载的相关性分数时（例如，当尚未开始查看现有文件加载时）选择此选择。</span><span class="sxs-lookup"><span data-stu-id="f71a3-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="f71a3-188">如果选择" **拆分加载"，** 请仅在新负载上继续相关性培训。</span><span class="sxs-lookup"><span data-stu-id="f71a3-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="f71a3-189">在此实例中，以前的批处理计算分数将保持不变。</span><span class="sxs-lookup"><span data-stu-id="f71a3-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="f71a3-190">当无法重新计算现有负载的现有相关性分数时（例如，如果已启动对现有负载的审阅）时，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="f71a3-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="f71a3-191">相关性分数从此时间点开始单独管理，不能合并。</span><span class="sxs-lookup"><span data-stu-id="f71a3-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="f71a3-192">单击 **"继续培训"。**</span><span class="sxs-lookup"><span data-stu-id="f71a3-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f71a3-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f71a3-193">See also</span></span>

[<span data-ttu-id="f71a3-194">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="f71a3-194">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f71a3-195">定义问题和分配用户</span><span class="sxs-lookup"><span data-stu-id="f71a3-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="f71a3-196">定义突出显示的关键字和高级选项</span><span class="sxs-lookup"><span data-stu-id="f71a3-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

