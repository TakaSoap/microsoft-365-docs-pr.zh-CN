---
title: 导出内容搜索报告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 您可以导出搜索结果报告，而不是在 Office 365 安全与合规&导出内容搜索的实际结果。 该报告包含搜索结果摘要和一个文档，其中包含有关将导出的每个项目的详细信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311565"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="58abe-104">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="58abe-104">Export a Content search report</span></span>

<span data-ttu-id="58abe-105">您可以导出导出与导出实际搜索结果时生成的相同报告，而不是从 Microsoft 365 合规中心 (中的内容搜索或与核心电子数据展示案例) 关联的搜索导出完整的搜索结果集。</span><span class="sxs-lookup"><span data-stu-id="58abe-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="58abe-106">导出报告时，报告文件将下载到本地计算机上与内容搜索同名的文件夹中，但附加有 *_ReportsOnly。*</span><span class="sxs-lookup"><span data-stu-id="58abe-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="58abe-107">例如，如果内容搜索名为 *ContosoCase0815*，则报告下载到名为 ContosoCase0815_ReportsOnly *。*</span><span class="sxs-lookup"><span data-stu-id="58abe-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="58abe-108">有关报告中包含的文档列表，请参阅 [报告中包含的内容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="58abe-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="58abe-109">导出搜索报告之前</span><span class="sxs-lookup"><span data-stu-id="58abe-109">Before you export a search report</span></span>

- <span data-ttu-id="58abe-110">若要导出搜索报告，您必须在安全与合规中心内&合规性搜索管理角色。</span><span class="sxs-lookup"><span data-stu-id="58abe-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="58abe-111">默认情况下，此角色分配给内置电子数据展示管理员和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="58abe-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="58abe-112">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="58abe-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="58abe-113">导出报告时，数据会临时存储在 microsoft 云Azure 存储位置，然后再下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="58abe-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="58abe-114">请确保你的组织可以连接到 Azure 中的终结点，即 **\* .blob.core.windows.net** (通配符表示导出服务的唯一) 。</span><span class="sxs-lookup"><span data-stu-id="58abe-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="58abe-115">搜索结果数据在创建后的两Azure 存储从搜索位置删除。</span><span class="sxs-lookup"><span data-stu-id="58abe-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="58abe-116">用于导出搜索结果的计算机必须满足以下系统要求：</span><span class="sxs-lookup"><span data-stu-id="58abe-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="58abe-117">最新版 Windows (32 位或 64 位) </span><span class="sxs-lookup"><span data-stu-id="58abe-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="58abe-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="58abe-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="58abe-119">您必须使用以下受支持的浏览器之一运行电子数据展示导出工具<sup>1：</sup></span><span class="sxs-lookup"><span data-stu-id="58abe-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="58abe-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="58abe-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="58abe-121">OR</span><span class="sxs-lookup"><span data-stu-id="58abe-121">OR</span></span>

  - <span data-ttu-id="58abe-122">Microsoft Internet Explorer 10及更高版本</span><span class="sxs-lookup"><span data-stu-id="58abe-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="58abe-123"><sup>1</sup> Microsoft 不会为应用程序制作第三方扩展ClickOnce加载项。</span><span class="sxs-lookup"><span data-stu-id="58abe-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="58abe-124">不支持使用不支持的浏览器和第三方扩展或加载项导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="58abe-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="58abe-125"><sup>2</sup>由于最近对 Microsoft Edge 所做的更改，ClickOnce不再启用支持。</span><span class="sxs-lookup"><span data-stu-id="58abe-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="58abe-126">有关在 Edge 中ClickOnce支持的说明，请参阅使用 Edge 中的电子数据展示[导出Microsoft Edge。](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="58abe-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="58abe-127">如果搜索返回的结果的估计总大小超过 2 TB，则导出报告将失败。</span><span class="sxs-lookup"><span data-stu-id="58abe-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="58abe-128">若要成功导出报告，请尝试缩小范围并重新运行搜索，以便结果的估计大小小于 2 TB。</span><span class="sxs-lookup"><span data-stu-id="58abe-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="58abe-129">如果搜索结果超过 7 天，并且您提交导出报告作业，则会显示一条错误消息，提示您重新运行搜索以更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="58abe-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="58abe-130">如果发生这种情况，请取消导出，重新运行搜索，然后再次开始导出。</span><span class="sxs-lookup"><span data-stu-id="58abe-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="58abe-131">导出搜索报告将计算同时运行的导出的最大数量和单个用户可以运行的最大导出数。</span><span class="sxs-lookup"><span data-stu-id="58abe-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="58abe-132">有关导出限制的信息，请参阅导出 [内容搜索结果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="58abe-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="58abe-133">步骤 1：生成报告进行导出</span><span class="sxs-lookup"><span data-stu-id="58abe-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="58abe-134">第一步是准备报告以下载到计算机导出。</span><span class="sxs-lookup"><span data-stu-id="58abe-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="58abe-135">导出报告时，报告文档将上载到 Microsoft Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="58abe-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="58abe-136">在Microsoft 365中心，选择要导出报告的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="58abe-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="58abe-137">在搜索 **弹出** 页底部的"操作"菜单上，单击"导出 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="58abe-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   !["操作"菜单中的"导出报告"选项](../media/ActionMenuExportReport.png)

   <span data-ttu-id="58abe-139">将显示 **"导出报告** "飞出页。</span><span class="sxs-lookup"><span data-stu-id="58abe-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="58abe-140">导出报告选项可用于导出有关搜索的信息取决于搜索结果位于邮箱或站点中还是两者的组合。</span><span class="sxs-lookup"><span data-stu-id="58abe-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="58abe-141">在 **"输出选项**"下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="58abe-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![导出输出选项](../media/ExportOutputOptions.png)

    - <span data-ttu-id="58abe-143">**所有项目（不包括无法识别** 的格式的项目）都经过加密，或者出于其他原因未编制索引。</span><span class="sxs-lookup"><span data-stu-id="58abe-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="58abe-144">此选项仅导出有关索引项的信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="58abe-145">**所有项目（包括无法识别的格式** 的项目）都经过加密，或者出于其他原因未编制索引。</span><span class="sxs-lookup"><span data-stu-id="58abe-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="58abe-146">此选项导出有关已编制索引和未编制索引的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="58abe-147">**只有具有无法识别的格式**、已加密或出于其他原因未编制索引的项。</span><span class="sxs-lookup"><span data-stu-id="58abe-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="58abe-148">此选项仅导出有关未索引项的信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="58abe-149">配置"**为内容启用Exchange复制"** 选项。</span><span class="sxs-lookup"><span data-stu-id="58abe-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="58abe-150">如果选择此选项，导出摘要报告中 (重复数据删除前和重复数据) 重复邮件数。</span><span class="sxs-lookup"><span data-stu-id="58abe-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="58abe-151">此外，邮件文件仅包含邮件manifest.xml副本。</span><span class="sxs-lookup"><span data-stu-id="58abe-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="58abe-152">但导出结果报告将包含重复邮件每个副本的一行，以便您可以标识包含重复邮件副本的邮箱。</span><span class="sxs-lookup"><span data-stu-id="58abe-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="58abe-153">有关导出的报告详细信息，请参阅 [报告中包含的内容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="58abe-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="58abe-154">如果未选择此选项，导出报告将包含有关搜索返回的所有邮件的信息，包括重复项。</span><span class="sxs-lookup"><span data-stu-id="58abe-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="58abe-155">有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中 [的重复数据删除](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="58abe-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="58abe-156">单击 **"生成报告"。**</span><span class="sxs-lookup"><span data-stu-id="58abe-156">Click **Generate report**.</span></span>

   <span data-ttu-id="58abe-157">搜索报告已做好下载准备，这意味着报告文档将上载到 Microsoft Azure 存储中的位置。</span><span class="sxs-lookup"><span data-stu-id="58abe-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="58abe-158">这可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="58abe-158">This may take several minutes.</span></span>

<span data-ttu-id="58abe-159">有关下载导出的搜索报告的说明，请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="58abe-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="58abe-160">步骤 2：下载报告</span><span class="sxs-lookup"><span data-stu-id="58abe-160">Step 2: Download the report</span></span>

<span data-ttu-id="58abe-161">下一步是将报告从 Azure 存储 下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="58abe-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="58abe-162">在合规性 **中心的"** 内容搜索"Microsoft 365，选择"导出 **"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="58abe-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="58abe-163">您可能必须 **单击"刷新** "来更新导出作业的列表，以便它显示您创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="58abe-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="58abe-164">导出报告作业的名称与相应的搜索同名，_ReportsOnly搜索名称后面。</span><span class="sxs-lookup"><span data-stu-id="58abe-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="58abe-165">选择在步骤 1 中创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="58abe-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="58abe-166">在"**导出报告**"飞出页面的"**导出密钥"下**，单击 **"复制到剪贴板"。**</span><span class="sxs-lookup"><span data-stu-id="58abe-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="58abe-167">在步骤 6 中使用此密钥下载搜索结果。</span><span class="sxs-lookup"><span data-stu-id="58abe-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="58abe-168">因为任何人都可以安装和启动电子数据展示导出工具，然后使用此密钥下载搜索报告，所以一定要采取预防措施来保护此密钥，就像保护密码或其他与安全有关的信息一样。</span><span class="sxs-lookup"><span data-stu-id="58abe-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="58abe-169">在飞出页面顶部，单击"**下载结果"。**</span><span class="sxs-lookup"><span data-stu-id="58abe-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="58abe-170">如果系统提示安装电子 **数据展示导出工具，请单击**"安装 **"。**</span><span class="sxs-lookup"><span data-stu-id="58abe-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="58abe-171">在 **电子数据展示导出工具中**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="58abe-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![电子数据展示导出工具](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="58abe-173">将步骤 3 中复制的导出密钥粘贴到相应的框中。</span><span class="sxs-lookup"><span data-stu-id="58abe-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="58abe-174">单击 **"** 浏览"以指定要下载搜索报告文件的位置。</span><span class="sxs-lookup"><span data-stu-id="58abe-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="58abe-175">单击“启动”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="58abe-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="58abe-176">**电子数据展示工具** 显示有关导出过程的状态信息，包括要下载的剩余项的估计数量（和大小）。</span><span class="sxs-lookup"><span data-stu-id="58abe-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="58abe-177">导出过程完成后，您可以在下载文件的位置访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="58abe-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="58abe-178">报告中包含的内容</span><span class="sxs-lookup"><span data-stu-id="58abe-178">What's included in the report</span></span>

<span data-ttu-id="58abe-179">生成和导出有关内容搜索结果的报告时，将下载以下文档：</span><span class="sxs-lookup"><span data-stu-id="58abe-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="58abe-180">**导出摘要：** 包含Excel摘要的一个文档。</span><span class="sxs-lookup"><span data-stu-id="58abe-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="58abe-181">其中包括搜索的内容源数量、每个内容位置的搜索结果数、估计的项目数、将导出的实际项目数以及将导出的项目的估计大小和实际大小等信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="58abe-182">如果您在导出报告时包括未索引的项目，则当您导出导出摘要报告中列出的搜索结果) 时，未索引项目的数量将包括在估计的搜索结果总数和下载的搜索结果 (总数中。</span><span class="sxs-lookup"><span data-stu-id="58abe-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="58abe-183">换句话说，将下载的项目总数等于估计结果总数和未索引项目总数。</span><span class="sxs-lookup"><span data-stu-id="58abe-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="58abe-184">**清单：** 清单文件 (XML 格式) ，其中包含有关搜索结果中包括的每个项目的信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="58abe-185">如果启用"重复数据删除"选项，则重复邮件不会包含在清单文件中。</span><span class="sxs-lookup"><span data-stu-id="58abe-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="58abe-186">**结果：** 一Excel包含一行的索引文档，其中包含有关每个将随搜索结果导出的索引项的信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="58abe-187">对于电子邮件，结果日志包含有关每封邮件的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="58abe-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="58abe-188">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="58abe-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="58abe-189">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="58abe-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="58abe-190">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="58abe-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="58abe-191">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="58abe-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="58abe-192">对于来自SharePoint和OneDrive for Business的文档，结果日志包含有关每个文档的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="58abe-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="58abe-193">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="58abe-193">The URL for the document.</span></span>

  - <span data-ttu-id="58abe-194">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="58abe-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="58abe-195">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="58abe-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="58abe-196">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="58abe-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="58abe-197">"结果"报告中的行数应等于搜索结果总数减去"未索引项目"报告中列出的 **项目总数**。</span><span class="sxs-lookup"><span data-stu-id="58abe-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="58abe-198">**Trace.log：** 跟踪日志，包含有关导出过程的详细日志记录信息，有助于在导出过程中发现问题。</span><span class="sxs-lookup"><span data-stu-id="58abe-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="58abe-199">如果向 Microsoft 支持人员打开有关导出搜索报告相关问题的票证，系统可能会要求您提供此跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="58abe-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="58abe-200">**未索引的项目：** 一Excel一个文档，其中包含有关搜索结果中包括的任何未建立索引的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="58abe-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="58abe-201">如果在生成搜索结果报告时未包括未索引的项目，此报告仍将下载，但将为空。</span><span class="sxs-lookup"><span data-stu-id="58abe-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
