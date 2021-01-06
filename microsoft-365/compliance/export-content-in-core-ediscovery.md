---
title: 从核心电子数据展示案例中导出和下载内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文介绍如何从核心电子数据展示案例导出和下载内容。
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760296"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="2a412-103">从核心电子数据展示案例中导出内容</span><span class="sxs-lookup"><span data-stu-id="2a412-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="2a412-104">成功运行搜索后，可以导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="2a412-105">导出搜索结果时，邮箱项目将下载到 PST 文件或单个邮件中。</span><span class="sxs-lookup"><span data-stu-id="2a412-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="2a412-106">从 SharePoint 和 OneDrive for Business 网站导出内容时，将导出本机 Office 文档和其他文档的副本。</span><span class="sxs-lookup"><span data-stu-id="2a412-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="2a412-107">一Results.csv导出的每个项目的信息的一个文档文件，以及一个包含每个搜索结果信息的 (清单文件) 包含每个搜索结果的信息。</span><span class="sxs-lookup"><span data-stu-id="2a412-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="2a412-108">可以导出与案例关联的 [单个](#export-the-results-of-a-single-search) 搜索的结果，也可以导出与案例关联的多个 [搜索的结果](#export-the-results-of-multiple-searches)。</span><span class="sxs-lookup"><span data-stu-id="2a412-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="2a412-109">导出单个搜索的结果</span><span class="sxs-lookup"><span data-stu-id="2a412-109">Export the results of a single search</span></span>

1. <span data-ttu-id="2a412-110">Go [https://compliance.microsoft.com](https://compliance.microsoft.com) to and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span><span class="sxs-lookup"><span data-stu-id="2a412-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="2a412-111">在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**核心。**</span><span class="sxs-lookup"><span data-stu-id="2a412-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="2a412-112">在 **"核心电子数据** 展示"页上，选择要导出搜索结果的大小写，然后单击"**打开案例"。**</span><span class="sxs-lookup"><span data-stu-id="2a412-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="2a412-113">在 **案例** 的主页上，单击"搜索 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2a412-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="2a412-114">在案例的搜索列表中，单击要导出搜索结果的搜索，然后在飞出上单击 **"导出结果** "。</span><span class="sxs-lookup"><span data-stu-id="2a412-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="2a412-115">将显示 **"导出结果** "页。</span><span class="sxs-lookup"><span data-stu-id="2a412-115">The **Export results** page is displayed.</span></span> 

    ![导出结果页](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="2a412-117">导出与核心电子数据展示案例关联的搜索结果的工作流与导出内容搜索页面上搜索的 **搜索结果相同** 。</span><span class="sxs-lookup"><span data-stu-id="2a412-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="2a412-118">有关分步说明，请参阅"[导出内容搜索结果"。](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="2a412-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a412-119">导出搜索结果时，可以选择启用重复数据删除，以便只导出电子邮件的一个副本，即使搜索到的邮箱中可能找到了同一邮件的多个实例。</span><span class="sxs-lookup"><span data-stu-id="2a412-119">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="2a412-120">有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中的重复 [数据删除](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="2a412-120">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="2a412-121">开始导出后，搜索结果准备下载，这意味着它们上传到 Microsoft 提供的 Microsoft 云中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2a412-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="2a412-122">单击 **"导出** "选项卡以显示案例的导出作业列表。</span><span class="sxs-lookup"><span data-stu-id="2a412-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="2a412-123">您可能必须单击 **"刷新"** 来更新导出作业的列表，以便它显示您创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="2a412-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="2a412-124">导出作业与相应的搜索具有相同的名称，_Export附加到搜索名称。</span><span class="sxs-lookup"><span data-stu-id="2a412-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="2a412-125">单击创建的导出作业，在飞出页上显示状态信息。</span><span class="sxs-lookup"><span data-stu-id="2a412-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="2a412-126">此信息包括已转移到 Azure 存储位置的项目百分比。</span><span class="sxs-lookup"><span data-stu-id="2a412-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="2a412-127">在转移所有项目后，单击"下载 **结果** "将搜索结果下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2a412-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="2a412-128">有关下载搜索结果的信息，请参阅"导出内容搜索结果的步骤 [2"](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="2a412-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="2a412-129">导出多个搜索的结果</span><span class="sxs-lookup"><span data-stu-id="2a412-129">Export the results of multiple searches</span></span>

<span data-ttu-id="2a412-130">作为导出与案例关联的单个搜索的结果的替代方法，您可以在单个导出作业中从同一案例导出多个搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="2a412-131">导出多个搜索的结果比一次导出一个搜索的结果更快、更容易。</span><span class="sxs-lookup"><span data-stu-id="2a412-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a412-132">如果其中一个搜索已配置为保留搜索位置，你无法导出多个搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="2a412-133">Go [https://compliance.microsoft.com](https://compliance.microsoft.com) to and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span><span class="sxs-lookup"><span data-stu-id="2a412-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="2a412-134">在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**核心。**</span><span class="sxs-lookup"><span data-stu-id="2a412-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="2a412-135">在 **"核心电子数据** 展示"页上，选择要导出搜索结果的大小写，然后单击"**打开案例"。**</span><span class="sxs-lookup"><span data-stu-id="2a412-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="2a412-136">在 **案例** 的主页上，单击"搜索 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2a412-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="2a412-137">在案例的搜索列表中，选中要导出搜索结果的两个或多个搜索旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="2a412-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="2a412-138">将显示 **"批量操作** "飞出页。</span><span class="sxs-lookup"><span data-stu-id="2a412-138">The **Bulk actions** flyout page appears.</span></span> 

    ![在"批量操作"页上，单击"导出结果"](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="2a412-140">单击 **"导出结果"。**</span><span class="sxs-lookup"><span data-stu-id="2a412-140">Click **Export results**.</span></span>

   <span data-ttu-id="2a412-141">将显示 **"导出结果** "页。</span><span class="sxs-lookup"><span data-stu-id="2a412-141">The **Export results** page is displayed.</span></span> 

    ![导出结果页](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="2a412-143">此时，导出与核心电子数据展示案例关联的多个搜索的结果的工作流与导出单个搜索的搜索结果相同。</span><span class="sxs-lookup"><span data-stu-id="2a412-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="2a412-144">请参阅上一节中的步骤 5。</span><span class="sxs-lookup"><span data-stu-id="2a412-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="2a412-145">有关导出多个搜索的结果详细信息</span><span class="sxs-lookup"><span data-stu-id="2a412-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="2a412-146">导出多个搜索的结果时，使用 **OR** 运算符组合来自所有搜索的搜索查询，然后启动组合搜索。</span><span class="sxs-lookup"><span data-stu-id="2a412-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="2a412-147">组合搜索的估计结果显示在所选导出作业的飞出页中。</span><span class="sxs-lookup"><span data-stu-id="2a412-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="2a412-148">搜索结果随后会复制到 Microsoft 云中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2a412-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="2a412-149">复制作业的状态也显示在飞出页上。</span><span class="sxs-lookup"><span data-stu-id="2a412-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="2a412-150">如前所述，复制所有搜索结果后，您可以将它们下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2a412-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="2a412-151">对于要导出的所有搜索，查询中的最大关键字数为 500。</span><span class="sxs-lookup"><span data-stu-id="2a412-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="2a412-152">这是单个搜索的相同限制。</span><span class="sxs-lookup"><span data-stu-id="2a412-152">This is the same limit for a single search.</span></span> <span data-ttu-id="2a412-153">这是因为导出作业使用 **OR** 运算符将所有搜索查询组合在一起。</span><span class="sxs-lookup"><span data-stu-id="2a412-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="2a412-154">如果超过此限制，将返回错误。</span><span class="sxs-lookup"><span data-stu-id="2a412-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="2a412-155">在这种情况下，您必须从较少的搜索中导出结果，或简化要导出的原始搜索的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="2a412-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="2a412-156">导出的搜索结果按找到项目的内容位置进行组织。</span><span class="sxs-lookup"><span data-stu-id="2a412-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="2a412-157">这意味着导出结果中的内容位置可能包含由不同搜索返回的项目。</span><span class="sxs-lookup"><span data-stu-id="2a412-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="2a412-158">例如，如果您选择在每个邮箱的一个 PST 文件中导出电子邮件，则 PST 文件可能包含来自多个搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="2a412-159">如果同一内容位置中的同一电子邮件项目或文档由您导出的多个搜索返回，则只导出该项目的一个副本。</span><span class="sxs-lookup"><span data-stu-id="2a412-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="2a412-160">创建多个搜索后，无法编辑导出。</span><span class="sxs-lookup"><span data-stu-id="2a412-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="2a412-161">例如，无法从导出作业中添加或删除搜索。</span><span class="sxs-lookup"><span data-stu-id="2a412-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="2a412-162">您必须创建导出作业以更改导出的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="2a412-163">创建导出作业后，只能将结果下载到计算机、重新启动导出或删除导出作业。</span><span class="sxs-lookup"><span data-stu-id="2a412-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="2a412-164">如果重新启动导出，则对包括导出作业的搜索查询的任何更改都不会影响检索到的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="2a412-165">重新启动导出时，将再次运行创建导出作业时运行的同一个组合搜索查询作业。</span><span class="sxs-lookup"><span data-stu-id="2a412-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="2a412-166">此外，如果重新启动导出，复制到 Azure 存储位置的搜索结果将覆盖以前的结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="2a412-167">无法下载之前复制的结果。</span><span class="sxs-lookup"><span data-stu-id="2a412-167">The previous results that were copied won't be available to be downloaded.</span></span>
