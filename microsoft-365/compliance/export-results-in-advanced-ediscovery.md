---
title: 在高级电子数据展示中导出结果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: '了解如何定义用于从高级电子数据展示导出结果的选项，包括指定导出批处理的参数的过程。 '
ms.openlocfilehash: 2929b183c7c0f3f132cc40738c18e2b4859a49a6
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662907"
---
# <a name="export-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="2f423-103">在高级电子数据展示和经典 (导出) </span><span class="sxs-lookup"><span data-stu-id="2f423-103">Export results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="2f423-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2f423-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2f423-106">本主题介绍高级电子数据展示导出设置选项。</span><span class="sxs-lookup"><span data-stu-id="2f423-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="2f423-107">**在本主题中：**</span><span class="sxs-lookup"><span data-stu-id="2f423-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="2f423-108">定义导出批处理和会话</span><span class="sxs-lookup"><span data-stu-id="2f423-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="2f423-109">增量导出和其他导出</span><span class="sxs-lookup"><span data-stu-id="2f423-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="2f423-110">设置批处理导出参数</span><span class="sxs-lookup"><span data-stu-id="2f423-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="2f423-111">导出报告输出文件</span><span class="sxs-lookup"><span data-stu-id="2f423-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="2f423-112">定义导出批处理和会话</span><span class="sxs-lookup"><span data-stu-id="2f423-112">Defining export batches and sessions</span></span>
<span data-ttu-id="2f423-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="2f423-113"><a name="BK_Define"> </a></span></span>

<span data-ttu-id="2f423-114">导出批处理允许使用一组定义的参数进行导出处理。</span><span class="sxs-lookup"><span data-stu-id="2f423-114">An export batch allows export processing using a set of defined parameters.</span></span> <span data-ttu-id="2f423-115">利用高级电子数据展示，您可以定义批处理以自定义每个导出。</span><span class="sxs-lookup"><span data-stu-id="2f423-115">Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="2f423-116">参数是按导出批处理定义的。</span><span class="sxs-lookup"><span data-stu-id="2f423-116">Parameters are defined per export batch.</span></span> <span data-ttu-id="2f423-117">默认情况下，会为第一批案例创建名为"Export batch 01"的批次。</span><span class="sxs-lookup"><span data-stu-id="2f423-117">A batch named "Export batch 01" is created by default for the first batch of a case.</span></span> <span data-ttu-id="2f423-118">还可以编辑批处理名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2f423-118">You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="2f423-119">导出会话是在导出批处理中执行高级电子数据展示导出。</span><span class="sxs-lookup"><span data-stu-id="2f423-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="2f423-120">增量导出和其他导出</span><span class="sxs-lookup"><span data-stu-id="2f423-120">Incremental and additional exports</span></span>
<span data-ttu-id="2f423-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="2f423-121"><a name="BK_IncrementalReports"> </a></span></span>

<span data-ttu-id="2f423-122">您可以在导出批处理中运行多个导出会话，以确保基于相同导出模板和参数的结果一致。</span><span class="sxs-lookup"><span data-stu-id="2f423-122">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters.</span></span> <span data-ttu-id="2f423-123">对于批处理内的每个会话，您可以导出新处理案例数据的分析并"增量"处理每个数据。</span><span class="sxs-lookup"><span data-stu-id="2f423-123">For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="2f423-124">若要使用一组不同的参数进行导出，首先需要创建新的批处理。</span><span class="sxs-lookup"><span data-stu-id="2f423-124">In order to export using a different set of parameters, you first need to create a new batch.</span></span> <span data-ttu-id="2f423-125">新批处理中的第一个会话将生成到目前为止处理的文件的结果，无论这些文件是否通过一个或多个导入导入导入和处理。</span><span class="sxs-lookup"><span data-stu-id="2f423-125">The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports.</span></span> <span data-ttu-id="2f423-126">每批重新计算透视表、相似性、包含值等。会话使用为批处理定义的参数，并且不会重新计算每个会话执行的数据透视、相似性、包含值等。</span><span class="sxs-lookup"><span data-stu-id="2f423-126">Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="2f423-127">例如，假定已导入案例并分析其数据。</span><span class="sxs-lookup"><span data-stu-id="2f423-127">For example, assume a case was imported and its data analyzed.</span></span> <span data-ttu-id="2f423-128">若要检索增量数据的近重复项和电子邮件线程结果，请单击之前用于导出数据的同一批次中的"创建导出会话"。</span><span class="sxs-lookup"><span data-stu-id="2f423-128">In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="2f423-129">设置批处理导出参数</span><span class="sxs-lookup"><span data-stu-id="2f423-129">Set up batch export parameters</span></span>
<span data-ttu-id="2f423-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="2f423-130"><a name="BK_SetUpExport"> </a></span></span>

<span data-ttu-id="2f423-131">电子数据展示导出工具用于将搜索结果从高级电子数据展示导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2f423-131">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer.</span></span>
  
1. <span data-ttu-id="2f423-132">在高级电子数据展示中，选择一个案例，然后单击 **"导出** \> **设置"。**</span><span class="sxs-lookup"><span data-stu-id="2f423-132">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="2f423-133">从 **"导出批处理** "列表中，选择批处理名称或将结果导出到"导出批处理 01"， (默认批处理) 。</span><span class="sxs-lookup"><span data-stu-id="2f423-133">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="2f423-134">若要导出添加到现有案例的新文件的结果，请继续执行当前批处理。</span><span class="sxs-lookup"><span data-stu-id="2f423-134">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="2f423-135">若要在批处理中创建会话，请选择相同的批处理号并单击"创建导出会话"。可以使用此选项以增量方式导出与上一批次相同的参数。</span><span class="sxs-lookup"><span data-stu-id="2f423-135">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="2f423-136">若要导出到新批处理，请单击"添加"图标，在批处理名称中输入新名称 (或接受"批处理) 中的默认名称和 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) **说明**。 </span><span class="sxs-lookup"><span data-stu-id="2f423-136">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="2f423-137">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="2f423-137">Click **OK**.</span></span>
    
    - <span data-ttu-id="2f423-138">若要编辑批处理名称或说明，请选择"导出批处理"中的名称 **，单击"** 编辑编辑" ![ 图标， ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) 然后修改字段。</span><span class="sxs-lookup"><span data-stu-id="2f423-138">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="2f423-139">为导出批处理运行会话后，将无法删除这些会话。</span><span class="sxs-lookup"><span data-stu-id="2f423-139">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="2f423-140">此外，运行第一个会话后，只能编辑某些参数。</span><span class="sxs-lookup"><span data-stu-id="2f423-140">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="2f423-141">若要创建重复的导出批处理，请选择 **"重复** 导出批处理 创建重复导出批处理"图标，然后输入面板中重复批处理 ![ ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) 的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2f423-141">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="2f423-142">若要删除导出批处理，请选择 **"删除** ![ 导出批处理"图标 ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="2f423-142">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="2f423-143">若要查看批处理的历史记录，请选择"批处理 **历史记录** 视图 ![ 历史记录"图标 ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="2f423-143">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="2f423-144">在 **"填充**"下，如果要微调导出批处理的设置，请选择"仅包含相关性截止分数上方的文件"和/或"优化导出批处理"。</span><span class="sxs-lookup"><span data-stu-id="2f423-144">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="2f423-145">如果选择" **仅包含相关性截止** 分数上方的文件"，则 **启用** "问题"。</span><span class="sxs-lookup"><span data-stu-id="2f423-145">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled.</span></span> <span data-ttu-id="2f423-146">如果文件的相关性分数高于选定问题的截止分数，则除非"评价"筛选器将文件排除，否则将导出该文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-146">If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="2f423-147">如果选择" **精简导出批处理**"，则启用"禁用 **"** 和"按'审阅'筛选"字段单选按钮。</span><span class="sxs-lookup"><span data-stu-id="2f423-147">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled.</span></span> <span data-ttu-id="2f423-148">如果选择"取消重复"，则重复文件将按照定义的策略筛选掉 [案例级别 (默认) ：从整个情况下的每组重复文件，除一个文件外，所有其他文件都将取消删除。</span><span class="sxs-lookup"><span data-stu-id="2f423-148">If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="2f423-149">保管人级别：从同一保管人的每组重复文件中，除一个文件外的所有文件都将取消删除。]导出输出包含所有重复文件的记录。</span><span class="sxs-lookup"><span data-stu-id="2f423-149">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files.</span></span> <span data-ttu-id="2f423-150">If you choose **Filter by 'For review'** field， select **Modify under Metadata** to enter your **'For review'** field settings.</span><span class="sxs-lookup"><span data-stu-id="2f423-150">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="2f423-151">选择 **"包括输入文件** "以在包内容中包括源文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-151">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="2f423-152">您可以清除此设置以加快导出过程。</span><span class="sxs-lookup"><span data-stu-id="2f423-152">You can clear this setting to speed up the export process.</span></span> <span data-ttu-id="2f423-153">请注意，将在任何情况下导出本机文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-153">Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="2f423-154">在 **"元数据**"下，从"导出模板"列表中的以下选项 (每个会话一次) 。</span><span class="sxs-lookup"><span data-stu-id="2f423-154">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="2f423-155">**标准**：数据项、元数据和属性的基本集。</span><span class="sxs-lookup"><span data-stu-id="2f423-155">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="2f423-156">如果导入数据已在高级电子数据展示中处理，并且导出数据已上载到已包含这些文件的系统，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="2f423-156">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="2f423-157">默认情况下，创建并填充导出模板列。</span><span class="sxs-lookup"><span data-stu-id="2f423-157">By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="2f423-158">**全部**：包括所有处理数据在内的一整套标准元数据，以及分析和相关性分数。</span><span class="sxs-lookup"><span data-stu-id="2f423-158">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="2f423-159">当高级电子数据展示执行处理且文件数据首次上载到外部系统时，此模板是必需的。</span><span class="sxs-lookup"><span data-stu-id="2f423-159">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="2f423-160">**问题**： **选择"所有** 问题"或选择已创建的特定问题。</span><span class="sxs-lookup"><span data-stu-id="2f423-160">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="2f423-161">在 **"目标"下**：</span><span class="sxs-lookup"><span data-stu-id="2f423-161">Under **Destination**:</span></span>
    
    - <span data-ttu-id="2f423-162">**下载到本地计算机**</span><span class="sxs-lookup"><span data-stu-id="2f423-162">**Download to local machine**</span></span>
    
    - <span data-ttu-id="2f423-163">**导出到用户定义的 Azure blob：** 如果选中此选项，可以指定容器 URL 和 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="2f423-163">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="2f423-164">将导出包存储到用户定义的 Azure blob 后，数据将不再由高级电子数据展示管理;它由 Azure blob 管理。</span><span class="sxs-lookup"><span data-stu-id="2f423-164">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob.</span></span> <span data-ttu-id="2f423-165">这意味着，如果删除案例，导出的文件仍将保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="2f423-165">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="2f423-166">**保存 SAS 令牌以用于将来的导出会话**：如果选中，SAS 令牌将在高级电子数据展示的内部数据库中进行加密，供将来使用。</span><span class="sxs-lookup"><span data-stu-id="2f423-166">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="2f423-167">目前，SAS 令牌将在一个月后过期。</span><span class="sxs-lookup"><span data-stu-id="2f423-167">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="2f423-168">如果尝试在一个月后下载，您必须撤消上一个会话，然后再次导出。</span><span class="sxs-lookup"><span data-stu-id="2f423-168">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="2f423-169">单击 **"** 修改"以设置"供审阅"字段设置。</span><span class="sxs-lookup"><span data-stu-id="2f423-169">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    !["设置" 查看导出批处理的字段设置](../media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="2f423-171">在 **"查看字段设置"** 下的 **"选择方案** "下拉列表中，选择评价的方案和范围。</span><span class="sxs-lookup"><span data-stu-id="2f423-171">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review.</span></span> <span data-ttu-id="2f423-172">根据您的选择显示设置。</span><span class="sxs-lookup"><span data-stu-id="2f423-172">The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="2f423-173">**查看所有** (默认) ：默认情况下选择所有电子邮件、附件和文档。</span><span class="sxs-lookup"><span data-stu-id="2f423-173">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="2f423-174">**查看一组内容的所有** 唯一内容：非独占副本和唯一非独占副本、电子邮件集级别的唯一附件、每组完全重复项中的代表。</span><span class="sxs-lookup"><span data-stu-id="2f423-174">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="2f423-175">**查看集合中所有** 唯一的内容 - 无非独占副本：电子邮件集级别中的非独占附件、唯一附件，代表每组完全重复项。</span><span class="sxs-lookup"><span data-stu-id="2f423-175">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="2f423-176">**查看所有唯一内容和相关的系列** 文件：电子邮件集级别中的非独占附件、唯一附件、每个精确重复项集的代表文件，展开以包含系列文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-176">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="2f423-177">**自定义** (允许你在对话框中定义选项) ：默认值是保留当前选择并启用所有对话框选项，以允许其选择。</span><span class="sxs-lookup"><span data-stu-id="2f423-177">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection.</span></span> <span data-ttu-id="2f423-178">如果选择此选项，可以自定义电子邮件、文档、附件和杂项设置。</span><span class="sxs-lookup"><span data-stu-id="2f423-178">If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="2f423-179">在 **"电子邮件**"下，选择要导出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2f423-179">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="2f423-180">**所有电子邮件**： (选择) 所有电子邮件的默认选项。</span><span class="sxs-lookup"><span data-stu-id="2f423-180">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="2f423-181">**非独占**：非独占电子邮件是线索的最后一封电子邮件，它包含来自线索的所有其他电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2f423-181">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="2f423-182">**非独占副本和唯一非** 独占副本：包含同一主题、正文和附件的包含副本和非独占副本;唯一的包含副本是这些电子邮件的唯一副本。</span><span class="sxs-lookup"><span data-stu-id="2f423-182">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="2f423-183">在 **"** 文档"下，选择要导出的文档。</span><span class="sxs-lookup"><span data-stu-id="2f423-183">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="2f423-184">**所有文档**： (所有) 所有文档。</span><span class="sxs-lookup"><span data-stu-id="2f423-184">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="2f423-185">**透视：** 选择为近重复集代表的文件，它通常在查看集合时用作基线。</span><span class="sxs-lookup"><span data-stu-id="2f423-185">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="2f423-186">**每组精确重复项** 中的代表：唯一的近重复 (包括透视表) 。</span><span class="sxs-lookup"><span data-stu-id="2f423-186">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="2f423-187">在 **"** 附件"下，选择要导出的附件。</span><span class="sxs-lookup"><span data-stu-id="2f423-187">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="2f423-188">**所有附件**： (所有) 所有附件。</span><span class="sxs-lookup"><span data-stu-id="2f423-188">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="2f423-189">**大小写级别的唯一附件**：指定案例内的唯一附件文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-189">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="2f423-190">**电子邮件集级别的唯一附件**：指定电子邮件案例内的唯一附件文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-190">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="2f423-191">在 **Micellaneous** 下，可以选择将附件视为 **文档**、将 **电子邮件视为文档** 或展开以 **包含系列文件**。</span><span class="sxs-lookup"><span data-stu-id="2f423-191">Under **Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**.</span></span> <span data-ttu-id="2f423-192">选择" **展开"以包含系列** 文件时，对于标记为要审阅的每个文件，也将标记同一系列的所有文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-192">When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="2f423-193">选择 **"保存** "以保存设置。</span><span class="sxs-lookup"><span data-stu-id="2f423-193">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="2f423-194">指定导出参数后，若要开始导出批处理，请单击 **"创建导出会话"。**</span><span class="sxs-lookup"><span data-stu-id="2f423-194">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="2f423-195">导出期间，状态显示在"任务 **"状态中**。</span><span class="sxs-lookup"><span data-stu-id="2f423-195">During export, the status is displayed in **Task status**.</span></span> <span data-ttu-id="2f423-196">结果将显示在导出 **摘要中**。</span><span class="sxs-lookup"><span data-stu-id="2f423-196">The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="2f423-197">在 **"下载文件"** 窗口中 **，单击"复制到剪贴板** "以复制导出密钥。</span><span class="sxs-lookup"><span data-stu-id="2f423-197">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![下载文件](../media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="2f423-199">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="2f423-199">Click **Close**.</span></span> 
    
    <span data-ttu-id="2f423-200">电子数据展示导出工具已启动。</span><span class="sxs-lookup"><span data-stu-id="2f423-200">The eDiscovery Export Tool is started.</span></span>
    
    ![电子数据展示导出工具](../media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="2f423-202">在 **电子数据展示导出工具中**：</span><span class="sxs-lookup"><span data-stu-id="2f423-202">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="2f423-203">在 **"粘贴将用于连接到** 源的共享访问签名"中，粘贴步骤 7 中复制到剪贴板的导出密钥。</span><span class="sxs-lookup"><span data-stu-id="2f423-203">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that you copied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="2f423-204">单击 **"** 浏览"以选择用于在本地计算机上存储下载的导出文件的目标位置。</span><span class="sxs-lookup"><span data-stu-id="2f423-204">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="2f423-205">单击 **"开始"。** 导出文件将下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2f423-205">Click **Start**.The export files are downloaded to the local machine.</span></span> <span data-ttu-id="2f423-206">如果在步骤 4 中选择了"导出到用户定义的 **Azure blob"，** 会话将导出到您选择的 Blob 存储 URL 目标。</span><span class="sxs-lookup"><span data-stu-id="2f423-206">If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="2f423-207">有关导出报告中字段的完整说明，请参阅" [导出报告"字段](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="2f423-207">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="2f423-208">导出报告输出文件</span><span class="sxs-lookup"><span data-stu-id="2f423-208">Export report output files</span></span>
<span data-ttu-id="2f423-209"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="2f423-209"><a name="BK_ExportOutputFIles"> </a></span></span>

<span data-ttu-id="2f423-210">下表列出了运行导出批处理时生成的输出文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-210">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="2f423-211">**文件名**</span><span class="sxs-lookup"><span data-stu-id="2f423-211">**File name**</span></span>|<span data-ttu-id="2f423-212">**文件类型**</span><span class="sxs-lookup"><span data-stu-id="2f423-212">**File type**</span></span>|<span data-ttu-id="2f423-213">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f423-213">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f423-214">导出摘要</span><span class="sxs-lookup"><span data-stu-id="2f423-214">Export summary</span></span>  <br/> |<span data-ttu-id="2f423-215">csv</span><span class="sxs-lookup"><span data-stu-id="2f423-215">csv</span></span>  <br/> |<span data-ttu-id="2f423-216">由日志文件导出工具生成的一个数据展示。</span><span class="sxs-lookup"><span data-stu-id="2f423-216">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="2f423-217">跟踪</span><span class="sxs-lookup"><span data-stu-id="2f423-217">Trace</span></span>  <br/> |<span data-ttu-id="2f423-218">txt</span><span class="sxs-lookup"><span data-stu-id="2f423-218">txt</span></span>  <br/> |<span data-ttu-id="2f423-219">由日志文件导出工具生成的一个数据展示。</span><span class="sxs-lookup"><span data-stu-id="2f423-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="2f423-220">提取的文本文件</span><span class="sxs-lookup"><span data-stu-id="2f423-220">Extracted text files</span></span>  <br/> |<span data-ttu-id="2f423-221">文件文件夹</span><span class="sxs-lookup"><span data-stu-id="2f423-221">File folder</span></span>  <br/> |<span data-ttu-id="2f423-222">包含已导出文件的提取文本文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f423-222">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="2f423-223">输入或本机文件</span><span class="sxs-lookup"><span data-stu-id="2f423-223">Input or native files</span></span>  <br/> |<span data-ttu-id="2f423-224">文件文件夹</span><span class="sxs-lookup"><span data-stu-id="2f423-224">File folder</span></span>  <br/> |<span data-ttu-id="2f423-225">包含导出文件的本机文件和输入文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f423-225">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="2f423-226">导出列表</span><span class="sxs-lookup"><span data-stu-id="2f423-226">Export list</span></span>  <br/> |<span data-ttu-id="2f423-227">xlsx</span><span class="sxs-lookup"><span data-stu-id="2f423-227">xlsx</span></span>  <br/> |<span data-ttu-id="2f423-228">以 xlsx 格式导出文件元数据。</span><span class="sxs-lookup"><span data-stu-id="2f423-228">Exported files metadata in xlsx format.</span></span> <span data-ttu-id="2f423-229">文件中字段根据用户选择要导出的模板进行。</span><span class="sxs-lookup"><span data-stu-id="2f423-229">Fields in files are according to template user selects to export.</span></span> <span data-ttu-id="2f423-230">如果需要，将创建多个文件，每个包含 100-150，000 行。</span><span class="sxs-lookup"><span data-stu-id="2f423-230">If needed, several files are created, each contains 100-150K rows.</span></span> <span data-ttu-id="2f423-231">如果特定值包含的字符数超过 Excel 单元格可包含的字符数 (当前限制为 32，767 个字符) ，则该值将剪裁为允许的最大长度。</span><span class="sxs-lookup"><span data-stu-id="2f423-231">If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed.</span></span> <span data-ttu-id="2f423-232">如果已剪裁值，则单元格的背景色为红色，以向用户指示这一点。"电子邮件参与者"是一个字段示例，如果电子邮件发送到大型分发，则该字段可能会超出长度限制。</span><span class="sxs-lookup"><span data-stu-id="2f423-232">If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution.</span></span> <span data-ttu-id="2f423-233">有关 [输出字段的详细信息](export-report-fields-in-advanced-ediscovery.md) ，请参阅"导出报告"字段。</span><span class="sxs-lookup"><span data-stu-id="2f423-233">See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.</span></span>  <br/> |
|<span data-ttu-id="2f423-234">加载文件</span><span class="sxs-lookup"><span data-stu-id="2f423-234">Load file</span></span>  <br/> |<span data-ttu-id="2f423-235">csv</span><span class="sxs-lookup"><span data-stu-id="2f423-235">csv</span></span>  <br/> |<span data-ttu-id="2f423-236">以 csv 格式导出文件元数据，以加载到其他应用程序中。</span><span class="sxs-lookup"><span data-stu-id="2f423-236">Exported files metadata in csv format for loading into a different application.</span></span> <span data-ttu-id="2f423-237">文件中字段根据用户选择要导出的模板进行。</span><span class="sxs-lookup"><span data-stu-id="2f423-237">Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="2f423-238">成功指示器</span><span class="sxs-lookup"><span data-stu-id="2f423-238">Success indicator</span></span>  <br/> |<span data-ttu-id="2f423-239">txt</span><span class="sxs-lookup"><span data-stu-id="2f423-239">txt</span></span>  <br/> |<span data-ttu-id="2f423-240">仅在导出到第三方 Azure blob 时创建。</span><span class="sxs-lookup"><span data-stu-id="2f423-240">Only created when exporting to a 3rd party Azure blob.</span></span> <span data-ttu-id="2f423-241">如果导出完全成功，将创建该文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-241">If export succeed completely, the file will be created.</span></span> <span data-ttu-id="2f423-242">如果失败或部分成功，将不会创建文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-242">In case of failure, or partial success the file will not be created.</span></span> <span data-ttu-id="2f423-243">将在根文件夹中创建文件，从而允许对不同的导出批处理/会话状态进行自动跟踪。</span><span class="sxs-lookup"><span data-stu-id="2f423-243">File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses.</span></span> <span data-ttu-id="2f423-244">这是一个空文件。</span><span class="sxs-lookup"><span data-stu-id="2f423-244">This is an empty file.</span></span> <span data-ttu-id="2f423-245">其名称为：TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。</span><span class="sxs-lookup"><span data-stu-id="2f423-245">Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2f423-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f423-246">See also</span></span>

[<span data-ttu-id="2f423-247">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="2f423-247">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2f423-248">查看批处理历史记录和导出过去的结果</span><span class="sxs-lookup"><span data-stu-id="2f423-248">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="2f423-249">快速设置高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="2f423-249">Quick setup for Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="2f423-250">导出报告字段</span><span class="sxs-lookup"><span data-stu-id="2f423-250">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
