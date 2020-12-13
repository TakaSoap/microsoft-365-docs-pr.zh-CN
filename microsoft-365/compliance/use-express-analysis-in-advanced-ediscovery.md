---
title: 在高级电子数据展示中使用快速分析
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 了解如何运行高级电子数据展示的 Express 分析模式，然后导出结果。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de637df426d38da2863a65eea67c65a3f66953a7
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663321"
---
# <a name="use-express-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="ebc99-103">在高级电子数据展示和经典 (快速) </span><span class="sxs-lookup"><span data-stu-id="ebc99-103">Use Express Analysis in Advanced eDiscovery (classic)</span></span> 

> [!NOTE]
> <span data-ttu-id="ebc99-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ebc99-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ebc99-106">您可以使用快速 **分析** 快速分析案例并导出结果。</span><span class="sxs-lookup"><span data-stu-id="ebc99-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="ebc99-107">您可以使用快速分析来计算近重复项和电子邮件线程并计算主题。</span><span class="sxs-lookup"><span data-stu-id="ebc99-107">You can use express analysis to calculate near-duplicates and email threads and calculate themes.</span></span> <span data-ttu-id="ebc99-108">还可以在 Express 分析的高级设置中设置主题、文档相似性和导出文件 [的某些参数](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)。</span><span class="sxs-lookup"><span data-stu-id="ebc99-108">You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="ebc99-109">运行快速分析</span><span class="sxs-lookup"><span data-stu-id="ebc99-109">Run Express analysis</span></span>

1. <span data-ttu-id="ebc99-110">在 **"快速** 分析 (1) "选项卡中，选择一个容器以启用\*\* Express analysis \*\* (2) 和 **高级** 设置按钮。</span><span class="sxs-lookup"><span data-stu-id="ebc99-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![快速分析页面的屏幕截图](../media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="ebc99-112">在 **"分析参数"下**：</span><span class="sxs-lookup"><span data-stu-id="ebc99-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="ebc99-113">如果要 **运行分析，** 请检查"计算近重复项"和"电子邮件线程"。</span><span class="sxs-lookup"><span data-stu-id="ebc99-113">Check **Calculate near-duplicates and email threads** if you want to run the analysis.</span></span> <span data-ttu-id="ebc99-114">默认情况下选中此选项。</span><span class="sxs-lookup"><span data-stu-id="ebc99-114">It is selected by default.</span></span> 
    
  - <span data-ttu-id="ebc99-115">选中 **"计算主题** "可处理所有文件并为其分配主题。</span><span class="sxs-lookup"><span data-stu-id="ebc99-115">Check **Calculate Themes** to process all files and assign themes to them.</span></span> <span data-ttu-id="ebc99-116">默认情况下选中此选项。</span><span class="sxs-lookup"><span data-stu-id="ebc99-116">It is selected by default.</span></span> 
    
3. <span data-ttu-id="ebc99-117">在 **"导出目标"下**：</span><span class="sxs-lookup"><span data-stu-id="ebc99-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="ebc99-118">选中 **"下载到本地计算机** "以下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ebc99-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="ebc99-119">如果选中" **导出到用户定义的 Azure blob"，** 则还可以指定容器 URL 和 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="ebc99-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ebc99-120">将导出包存储到用户定义的 Azure blob 后，数据将不再由高级电子数据展示管理。</span><span class="sxs-lookup"><span data-stu-id="ebc99-120">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery.</span></span> <span data-ttu-id="ebc99-121">它由 Azure blob 管理。</span><span class="sxs-lookup"><span data-stu-id="ebc99-121">it is managed by the Azure blob.</span></span> <span data-ttu-id="ebc99-122">这意味着，如果删除案例，导出的文件仍将保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="ebc99-122">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="ebc99-123">**保存 SAS 令牌以用于将来的导出会话**：如果选中，SAS 令牌将在高级电子数据展示的内部数据库中进行加密，供将来使用。</span><span class="sxs-lookup"><span data-stu-id="ebc99-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebc99-124">目前，SAS 令牌将在一个月后过期。</span><span class="sxs-lookup"><span data-stu-id="ebc99-124">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="ebc99-125">如果尝试在一个月后下载，您必须撤消上一个会话，然后再次导出。</span><span class="sxs-lookup"><span data-stu-id="ebc99-125">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="ebc99-126">若要使用默认设置启动快速分析，请选择 **"快速** 分析"，并显示" **任务状态** "页</span><span class="sxs-lookup"><span data-stu-id="ebc99-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="ebc99-127">在"**任务状态**"页上，可以展开"进程"、"分析和导出 **"选项卡以显示** 有关快速运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebc99-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![高级电子数据展示快速分析任务状态页的屏幕截图](../media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="ebc99-129">选择 **"快速分析摘要** "页以列出有关运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebc99-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="ebc99-130">在" **快速** 分析摘要"页面底部 **，选择"** 下载最后一个会话"以下载分析文件 tp 本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ebc99-130">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer.</span></span> <span data-ttu-id="ebc99-131">您首先必须下载电子数据展示导出工具，然后将导出密钥粘贴到电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="ebc99-131">You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="ebc99-132">Express 分析的高级设置</span><span class="sxs-lookup"><span data-stu-id="ebc99-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="ebc99-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc99-133"><a name="BK_AdvancedSettings"> </a></span></span>

<span data-ttu-id="ebc99-134">可以选择设置高级 **设置来** 更改默认的 Express 分析参数。</span><span class="sxs-lookup"><span data-stu-id="ebc99-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="ebc99-135">在" **分析"** 部分：</span><span class="sxs-lookup"><span data-stu-id="ebc99-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="ebc99-136">在 **"近重复项"和"电子邮件线程**"中，输入 **"文档相似性** "值，或接受默认值 65%。</span><span class="sxs-lookup"><span data-stu-id="ebc99-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="ebc99-137">在 **"最大主题数"中** ，输入或选择要创建的主题数的值。</span><span class="sxs-lookup"><span data-stu-id="ebc99-137">In the **Max number of themes** enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="ebc99-138">默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="ebc99-138">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ebc99-139">增加主题数量会影响性能以及主题的一般化能力。</span><span class="sxs-lookup"><span data-stu-id="ebc99-139">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="ebc99-140">主题数量越高，主题越精细。</span><span class="sxs-lookup"><span data-stu-id="ebc99-140">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="ebc99-141">例如，如果一组 50 个主题包含主题，如"Basketball、Clipps、Clippers、Lakers";300 个主题可能包含单独的主题："小马"、"Clippers"、"Lakers"。</span><span class="sxs-lookup"><span data-stu-id="ebc99-141">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="ebc99-142">如果你对主题"Basketball"没有了解，并且对 ECA 使用此功能，则看到主题"Basketball"可能很有用。</span><span class="sxs-lookup"><span data-stu-id="ebc99-142">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="ebc99-143">但是，如果处理主题过多，你可能永远不会看到单词"Basketball"，并且可能不知道"小球"和"Clippers"是需要审阅的优秀"篮球"主题，而不是启动和用于发的项目。</span><span class="sxs-lookup"><span data-stu-id="ebc99-143">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="ebc99-144">在 **"建议的主题"中** ， **选择"修改** "以建议主题词以控制主题处理。</span><span class="sxs-lookup"><span data-stu-id="ebc99-144">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing.</span></span> <span data-ttu-id="ebc99-145">高级电子数据展示将侧重于这些建议词语，并尝试基于"主题最大数量"设置创建一个或多个相关主题。</span><span class="sxs-lookup"><span data-stu-id="ebc99-145">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="ebc99-146">例如，如果建议的单词是"computer"，并且你指定"2"作为"最大主题数"，则高级电子数据展示将尝试生成与单词"computer"相关的两个主题。</span><span class="sxs-lookup"><span data-stu-id="ebc99-146">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="ebc99-147">例如，这两个主题可能是"计算机软件"和"计算机硬件"。</span><span class="sxs-lookup"><span data-stu-id="ebc99-147">The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![添加建议的主题](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="ebc99-149">**模式** 从下拉列表中，选择" **主题"** 选项：</span><span class="sxs-lookup"><span data-stu-id="ebc99-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="ebc99-150">**创建和应用模型**：按一段文件按模型计算主题，然后分发其中的文件。</span><span class="sxs-lookup"><span data-stu-id="ebc99-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="ebc99-151">**创建模型**：从文件段计算主题模型。</span><span class="sxs-lookup"><span data-stu-id="ebc99-151">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="ebc99-152">划分文件的"应用"过程在另一个时间单独完成。</span><span class="sxs-lookup"><span data-stu-id="ebc99-152">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="ebc99-153">**应用模型**：此选项仅在之前创建且尚未应用模型时显示。</span><span class="sxs-lookup"><span data-stu-id="ebc99-153">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="ebc99-154">这将基于主题划分文件。</span><span class="sxs-lookup"><span data-stu-id="ebc99-154">This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="ebc99-155">在" **导出"** 部分：</span><span class="sxs-lookup"><span data-stu-id="ebc99-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="ebc99-156">在 **"选择导出批处理"中**：</span><span class="sxs-lookup"><span data-stu-id="ebc99-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="ebc99-157">从 **"导出批处理** "列表中，选择批处理名称或将结果导出到"导出批处理 01"， (默认批处理) 。</span><span class="sxs-lookup"><span data-stu-id="ebc99-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="ebc99-158">若要导出添加到现有案例的新文件的结果，请继续执行当前批处理。</span><span class="sxs-lookup"><span data-stu-id="ebc99-158">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="ebc99-159">若要在批处理中创建会话，请选择相同的批处理号并单击"创建导出会话"。可以使用此选项以增量方式导出与上一批次相同的参数。</span><span class="sxs-lookup"><span data-stu-id="ebc99-159">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="ebc99-160">若要导出到新批处理，请单击"添加"图标，在批处理名称中输入新名称 (或接受"批处理) 中的默认名称和 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) **说明**。 </span><span class="sxs-lookup"><span data-stu-id="ebc99-160">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="ebc99-161">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="ebc99-161">Click **OK**.</span></span>
    
  - <span data-ttu-id="ebc99-162">若要编辑批处理名称或说明，请选择"导出批处理"中的名称 **，单击"** 编辑编辑" ![ 图标， ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) 然后修改字段。</span><span class="sxs-lookup"><span data-stu-id="ebc99-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebc99-163">为导出批处理运行会话后，将无法删除这些会话。</span><span class="sxs-lookup"><span data-stu-id="ebc99-163">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="ebc99-164">此外，运行第一个会话后，只能编辑某些参数。</span><span class="sxs-lookup"><span data-stu-id="ebc99-164">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="ebc99-165">若要创建重复的导出批处理，请选择 **"重复** 导出批处理 创建重复导出批处理"图标，然后输入面板中重复批处理 ![ ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) 的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="ebc99-165">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="ebc99-166">若要删除导出批处理，请选择 **"删除** ![ 导出批处理"图标 ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="ebc99-166">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="ebc99-167">若要查看批处理的历史记录，请选择"批处理 **历史记录** 视图 ![ 历史记录"图标 ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="ebc99-167">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="ebc99-168">在"定义 p **opulation：** Select **Include only files above Relevance cut-off score** and/or Refine export **batch** if you want to fine-tune the settings for your export batch.</span><span class="sxs-lookup"><span data-stu-id="ebc99-168">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> <span data-ttu-id="ebc99-169">如果选择"仅包含相关性截止分数上方的文件"，则启用"问题"，如果文件的相关性分数高于选定问题的截止分数，则导出文件。 </span><span class="sxs-lookup"><span data-stu-id="ebc99-169">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported.</span></span> <span data-ttu-id="ebc99-170">文件将被导出，除非它已被'审阅筛选器 **'** 排除。</span><span class="sxs-lookup"><span data-stu-id="ebc99-170">The file will be exported unless it's excluded by the ' **For review** filter.</span></span> <span data-ttu-id="ebc99-171">如果选择" **精简导出批处理**"，则启用"禁用 **"** 和"按'审阅'筛选" **字段** 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="ebc99-171">If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled.</span></span> <span data-ttu-id="ebc99-172">如果选择"删除"，则重复文件将按照定义的策略进行筛选：[案例级别 (默认) ：从整个情况下的每组重复文件删除除一个文件外的所有重复文件。</span><span class="sxs-lookup"><span data-stu-id="ebc99-172">If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="ebc99-173">保管人级别：从同一保管人的每组重复文件中，除一个文件外的所有文件都将取消删除。</span><span class="sxs-lookup"><span data-stu-id="ebc99-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span></span> <span data-ttu-id="ebc99-174">导出输出中提供了所有重复文件的记录。</span><span class="sxs-lookup"><span data-stu-id="ebc99-174">A record of all duplicate files is available in export output.</span></span> <span data-ttu-id="ebc99-175">If you choose **Filter by 'For review'** field， select **Modify under Metadata** to enter your **'For review'** field settings.</span><span class="sxs-lookup"><span data-stu-id="ebc99-175">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="ebc99-176">选择 **"包括输入文件**"以在包内容中包括源文件。</span><span class="sxs-lookup"><span data-stu-id="ebc99-176">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="ebc99-177">可以清除此选项以加快导出过程。</span><span class="sxs-lookup"><span data-stu-id="ebc99-177">You can clear this option to speed up the export process.</span></span> <span data-ttu-id="ebc99-178">请注意，将在任何情况下导出本机文件。</span><span class="sxs-lookup"><span data-stu-id="ebc99-178">Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="ebc99-179">在 **"定义元数据**"下，从导出模板列表中的以下选项 (每个会话一次) 。</span><span class="sxs-lookup"><span data-stu-id="ebc99-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="ebc99-180">**标准**：数据项、元数据和属性的基本集。</span><span class="sxs-lookup"><span data-stu-id="ebc99-180">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="ebc99-181">如果导入数据已在高级电子数据展示中处理，并且导出数据已上载到已包含这些文件的系统，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ebc99-181">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="ebc99-182">默认情况下，创建并填充导出模板列。</span><span class="sxs-lookup"><span data-stu-id="ebc99-182">By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="ebc99-183">**全部**：包括所有处理数据在内的一整套标准元数据，以及分析和相关性分数。</span><span class="sxs-lookup"><span data-stu-id="ebc99-183">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="ebc99-184">当高级电子数据展示执行处理且文件数据首次上载到外部系统时，此模板是必需的。</span><span class="sxs-lookup"><span data-stu-id="ebc99-184">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="ebc99-185">**问题**： **选择"所有** 问题"或选择已创建的特定问题。</span><span class="sxs-lookup"><span data-stu-id="ebc99-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="ebc99-186">选择 **"** 确定"保存高级设置，"**还原** 默认值"以使用默认值，或选择"取消"取消设置高级设置。</span><span class="sxs-lookup"><span data-stu-id="ebc99-186">Choose **OK** to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebc99-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebc99-187">See also</span></span>
<span data-ttu-id="ebc99-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="ebc99-188"><a name="BK_AdvancedSettings"> </a></span></span>

[<span data-ttu-id="ebc99-189">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="ebc99-189">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)

