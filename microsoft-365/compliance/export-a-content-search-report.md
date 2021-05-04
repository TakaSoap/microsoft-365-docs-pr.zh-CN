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
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760150"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="8353a-104">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="8353a-104">Export a Content Search report</span></span>

<span data-ttu-id="8353a-105">您可以导出导出搜索结果时生成的相同报告，而不是从安全 & 合规中心 (中的内容搜索和与电子数据展示案例) 关联的内容搜索导出完整的搜索结果集。</span><span class="sxs-lookup"><span data-stu-id="8353a-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="8353a-106">导出报告时，会下载到与内容搜索同名的文件夹，但会随"内容搜索 *"* 一起_ReportsOnly。</span><span class="sxs-lookup"><span data-stu-id="8353a-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="8353a-107">例如，如果内容搜索名为 *ContosoCase0815*，则报告下载到名为 ContosoCase0815_ReportsOnly *。*</span><span class="sxs-lookup"><span data-stu-id="8353a-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="8353a-108">有关报告中包含的文档列表，请参阅 [报告中包含的内容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="8353a-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="8353a-109">分配角色并检查系统要求</span><span class="sxs-lookup"><span data-stu-id="8353a-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="8353a-110">若要导出内容搜索报告，您必须在安全与合规中心内分配合规性搜索&角色。</span><span class="sxs-lookup"><span data-stu-id="8353a-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="8353a-111">默认情况下，此角色分配给内置电子数据展示管理员和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="8353a-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="8353a-112">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8353a-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="8353a-113">导出报告时，数据临时存储在 Microsoft 云中Azure 存储一个唯一的区域，然后再下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8353a-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="8353a-114">请确保你的组织可以连接到 Azure 中的终结点，即 **\* .blob.core.windows.net** (通配符表示导出服务的唯一) 。</span><span class="sxs-lookup"><span data-stu-id="8353a-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="8353a-115">搜索结果数据在创建后的两Azure 存储从区域中删除。</span><span class="sxs-lookup"><span data-stu-id="8353a-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="8353a-116">用于导出搜索结果的计算机必须满足以下系统要求：</span><span class="sxs-lookup"><span data-stu-id="8353a-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="8353a-117">最新版 Windows (32 位或 64 位) </span><span class="sxs-lookup"><span data-stu-id="8353a-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="8353a-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8353a-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="8353a-119">您必须使用以下受支持的浏览器之一运行电子数据展示导出工具<sup>1：</sup></span><span class="sxs-lookup"><span data-stu-id="8353a-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="8353a-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8353a-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="8353a-121">OR</span><span class="sxs-lookup"><span data-stu-id="8353a-121">OR</span></span>

  - <span data-ttu-id="8353a-122">Microsoft Internet Explorer 10及更高版本</span><span class="sxs-lookup"><span data-stu-id="8353a-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="8353a-123"><sup>1</sup> Microsoft 不会为应用程序制作第三方扩展ClickOnce加载项。</span><span class="sxs-lookup"><span data-stu-id="8353a-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="8353a-124">不支持使用不支持的浏览器和第三方扩展或加载项导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8353a-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="8353a-125"><sup>2</sup>由于最近对 Microsoft Edge 所做的更改，ClickOnce不再启用支持。</span><span class="sxs-lookup"><span data-stu-id="8353a-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="8353a-126">有关在 Edge 中ClickOnce支持的说明，请参阅使用 Edge 中的电子数据展示[导出Microsoft Edge。](configure-edge-to-export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="8353a-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="8353a-127">如果内容搜索返回的结果的估计总大小超过 2 TB，则导出报告将失败。</span><span class="sxs-lookup"><span data-stu-id="8353a-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="8353a-128">若要成功导出报告，请尝试缩小范围并重新运行搜索，以便结果的估计大小小于 2 TB。</span><span class="sxs-lookup"><span data-stu-id="8353a-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="8353a-129">导出内容搜索报告根据同时运行的导出的最大数量和单个用户可以运行的最大导出数进行计数。</span><span class="sxs-lookup"><span data-stu-id="8353a-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="8353a-130">有关导出限制的信息，请参阅导出 [内容搜索结果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="8353a-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="8353a-131">生成和下载内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="8353a-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="8353a-132">生成和下载内容搜索报告的步骤与实际导出搜索结果的步骤类似。</span><span class="sxs-lookup"><span data-stu-id="8353a-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="8353a-133">步骤 1：生成报告进行导出</span><span class="sxs-lookup"><span data-stu-id="8353a-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="8353a-134">第一步是准备报告以下载到计算机导出。</span><span class="sxs-lookup"><span data-stu-id="8353a-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="8353a-135">当你报告时，报告文档将上载到 microsoft 云Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="8353a-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="8353a-136">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="8353a-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8353a-137">使用工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="8353a-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="8353a-138">在安全与合规中心的左&，单击"**搜索内容** \> **搜索"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="8353a-139">在" **内容搜索"** 页上，选择一个搜索。</span><span class="sxs-lookup"><span data-stu-id="8353a-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="8353a-140">在详细信息窗格中的"**将报告导出到计算机"下，** 单击"**生成报告"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8353a-141">如果搜索结果超过 7 天，将提示你更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8353a-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="8353a-142">如果发生这种情况，请取消导出，在所选搜索的详细信息窗格中单击"更新搜索结果"，然后在更新结果后再次开始报告导出。</span><span class="sxs-lookup"><span data-stu-id="8353a-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="8353a-143">在" **导出报告"页上** 的" **从搜索中包括这些项目"下**，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="8353a-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="8353a-144">仅导出索引项</span><span class="sxs-lookup"><span data-stu-id="8353a-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="8353a-145">导出索引和未编制索引项</span><span class="sxs-lookup"><span data-stu-id="8353a-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="8353a-146">仅导出未编制索引项</span><span class="sxs-lookup"><span data-stu-id="8353a-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="8353a-147">有关未编制索引的项目的信息，请参阅内容搜索中的部分 [索引项](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="8353a-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="8353a-148">选择包含文档的所有版本的搜索SharePoint统计信息。</span><span class="sxs-lookup"><span data-stu-id="8353a-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="8353a-149">此选项仅在搜索的内容源包括网站或网站SharePoint OneDrive for Business显示。</span><span class="sxs-lookup"><span data-stu-id="8353a-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="8353a-150">单击 **"生成报告"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="8353a-151">搜索结果报告已准备下载，这意味着报告文档将上载到 Microsoft 云Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="8353a-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="8353a-152">当报告可供下载时，将在详细信息窗格中的"将报告导出 **到计算机**"下显示"下载报告"链接。</span><span class="sxs-lookup"><span data-stu-id="8353a-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8353a-153">还可以导出与电子数据展示案例关联的内容搜索报告。</span><span class="sxs-lookup"><span data-stu-id="8353a-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="8353a-154">为此，请转到电子 **数据展示** \> **电子数据展示**，选择一个案例，然后单击编辑 **编辑** ![ 图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8353a-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="8353a-155">在"**搜索"** 页上，选择搜索，然后单击 **"导出** ![ 导出搜索结果"图标" ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **导出报告"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="8353a-156">步骤 2：下载报告</span><span class="sxs-lookup"><span data-stu-id="8353a-156">Step 2: Download the report</span></span>

<span data-ttu-id="8353a-157">下一步是将报告从 Azure 存储 下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8353a-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="8353a-158">在生成报告的搜索的详细信息窗格中，在"将报告导出 **到计算机**"下，单击"**下载报告"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="8353a-159">将显示 **"** 下载报告"页，其中包含有关下载到计算机的报告的以下信息。</span><span class="sxs-lookup"><span data-stu-id="8353a-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="8353a-160">将下载的项的数目。</span><span class="sxs-lookup"><span data-stu-id="8353a-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="8353a-161">将下载的项的预计总大小。</span><span class="sxs-lookup"><span data-stu-id="8353a-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="8353a-162">是否导出索引或未编制索引。</span><span class="sxs-lookup"><span data-stu-id="8353a-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="8353a-163">未编制索引的项目是具有可识别格式、已加密或由于其他原因未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="8353a-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="8353a-164">是否下载SharePoint版本的文档。</span><span class="sxs-lookup"><span data-stu-id="8353a-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="8353a-165">报告导出过程的状态。</span><span class="sxs-lookup"><span data-stu-id="8353a-165">The status of the report export process.</span></span> <span data-ttu-id="8353a-166">即使报告准备未完成，也可以开始下载报告。</span><span class="sxs-lookup"><span data-stu-id="8353a-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="8353a-167">在“**导出密钥**”下，单击“**复制到剪贴板**”。</span><span class="sxs-lookup"><span data-stu-id="8353a-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="8353a-168">在步骤 5 中使用此密钥下载报告。</span><span class="sxs-lookup"><span data-stu-id="8353a-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8353a-169">因为任何人都可以安装和启动电子数据展示导出工具，然后使用此密钥下载搜索报告，所以一定要采取预防措施来保护此密钥，就像保护密码或其他与安全有关的信息一样。</span><span class="sxs-lookup"><span data-stu-id="8353a-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="8353a-170">单击 **"下载报告"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="8353a-171">如果系统提示安装电子 **数据展示导出工具，请单击**"安装 **"。**</span><span class="sxs-lookup"><span data-stu-id="8353a-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="8353a-172">在“电子数据展示导出工具”中，将你在步骤 2 中复制的导出密钥粘贴在相应的框中。</span><span class="sxs-lookup"><span data-stu-id="8353a-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="8353a-173">单击 **"** 浏览"以指定要下载报告的位置。</span><span class="sxs-lookup"><span data-stu-id="8353a-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="8353a-174">单击“启动”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="8353a-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="8353a-175">**电子数据展示工具** 显示有关导出过程的状态信息，包括要下载的剩余项的估计数量（和大小）。</span><span class="sxs-lookup"><span data-stu-id="8353a-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="8353a-176">导出过程完成后，您可以在下载文件的位置访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="8353a-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8353a-177">您可以下载与电子数据展示案例关联的内容搜索报告。</span><span class="sxs-lookup"><span data-stu-id="8353a-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="8353a-178">为此，请转到电子 **数据展示** \> **电子数据展示**，选择一个案例，然后单击编辑 **编辑** ![ 图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="8353a-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="8353a-179">在" **导出"** 页上，选择报告导出， **然后单击详细信息窗格中** 的"下载报告"。</span><span class="sxs-lookup"><span data-stu-id="8353a-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="8353a-180">报告中包含的内容</span><span class="sxs-lookup"><span data-stu-id="8353a-180">What's included in the report</span></span>

<span data-ttu-id="8353a-181">生成和导出有关内容搜索结果的报告时，将下载以下文档：</span><span class="sxs-lookup"><span data-stu-id="8353a-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="8353a-182">**导出摘要：** 包含Excel摘要的一个文档。</span><span class="sxs-lookup"><span data-stu-id="8353a-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="8353a-183">其中包括搜索的内容源数量、每个内容位置的搜索结果数、估计的项目数、将导出的实际项目数以及将导出的项目的估计大小和实际大小等信息。</span><span class="sxs-lookup"><span data-stu-id="8353a-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8353a-184">如果在导出报告时包括未索引的项目，则当您导出导出摘要报告中列出的搜索结果) 时，未索引项目的数量将包括在估计的搜索结果总数和下载的搜索结果 (总数中。</span><span class="sxs-lookup"><span data-stu-id="8353a-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="8353a-185">换句话说，将下载的项目总数等于估计结果总数和未索引项目总数。</span><span class="sxs-lookup"><span data-stu-id="8353a-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="8353a-186">**清单：** 清单文件 (XML 格式) ，其中包含有关搜索结果中包括的每个项目的信息。</span><span class="sxs-lookup"><span data-stu-id="8353a-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="8353a-187">**结果：** 一Excel包含一行的索引文档，其中包含有关每个将随搜索结果导出的索引项的信息。</span><span class="sxs-lookup"><span data-stu-id="8353a-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="8353a-188">对于电子邮件，结果日志包含有关每封邮件的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="8353a-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="8353a-189">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="8353a-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="8353a-190">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="8353a-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="8353a-191">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="8353a-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="8353a-192">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="8353a-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="8353a-193">对于来自SharePoint和OneDrive for Business的文档，结果日志包含有关每个文档的信息，包括：</span><span class="sxs-lookup"><span data-stu-id="8353a-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="8353a-194">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="8353a-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="8353a-195">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="8353a-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="8353a-196">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="8353a-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="8353a-197">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="8353a-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8353a-198">"结果"报告中的行数应等于搜索结果总数减去"未索引项目"报告中列出的 **项目总数**。</span><span class="sxs-lookup"><span data-stu-id="8353a-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="8353a-199">**未索引项目：** 一Excel一个文档，其中包含有关搜索结果中包括的任何未建立索引的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="8353a-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="8353a-200">如果在生成搜索结果报告时未包括未索引的项目，此报告仍将下载，但将为空。</span><span class="sxs-lookup"><span data-stu-id="8353a-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
