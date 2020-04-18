---
title: 从核心电子数据展示事例导出和下载内容
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
description: 本文介绍如何从核心电子数据展示事例导出和下载内容。
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551367"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="5dc9e-103">从核心电子数据展示事例导出内容</span><span class="sxs-lookup"><span data-stu-id="5dc9e-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="5dc9e-104">成功运行搜索后，您可以导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="5dc9e-105">当您导出搜索结果时，邮箱项目会下载到 PST 文件或单个邮件中。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="5dc9e-106">当您从 SharePoint 和 OneDrive for business 网站导出内容时，会导出本机 Office 文档和其他文档的副本。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="5dc9e-107">包含有关每个导出的每个项目的信息的结果 .csv 文件和包含有关每个搜索结果的信息的清单文件（以 XML 格式）也将被导出。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="5dc9e-108">您可以导出[与事例关联的单个搜索](#export-the-results-of-a-single-search)的结果，也可以导出[与事例相关联的多个搜索](#export-the-results-of-multiple-searches)的结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="5dc9e-109">导出单个搜索的结果</span><span class="sxs-lookup"><span data-stu-id="5dc9e-109">Export the results of a single search</span></span>

1. <span data-ttu-id="5dc9e-110">转到[https://compliance.microsoft.com](https://compliance.microsoft.com)并使用已为其分配了相应电子数据展示权限的用户帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="5dc9e-111">在 Microsoft 365 合规性中心的左侧导航窗格中，单击 "**全部显示**"，然后单击 "**电子数据展示 > 核心**"。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="5dc9e-112">在 "**核心电子数据展示**" 页上，选择要从中导出搜索结果的事例，然后单击 "**打开事例**"。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="5dc9e-113">在该案例的**主页**上，单击 "**搜索**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="5dc9e-114">在案例的搜索列表中，单击要从中导出搜索结果的搜索，然后单击浮出控件上的 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="5dc9e-115">将显示 "**导出结果**" 页。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-115">The **Export results** page is displayed.</span></span> 

    !["导出结果" 页](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="5dc9e-117">导出与核心电子数据展示事例关联的搜索结果的工作流与导出 "**内容搜索**" 页上的搜索的搜索结果相同。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="5dc9e-118">有关分步说明，请参阅[导出内容搜索结果](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5dc9e-119">当您导出搜索结果时，您可以选择启用重复数据删除，以便即使在搜索的邮箱中找到同一邮件的多个实例，也只导出电子邮件的一个副本。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-119">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="5dc9e-120">有关重复数据删除和标识重复项目的详细信息，请参阅[电子数据展示搜索结果中的重复数据](de-duplication-in-ediscovery-search-results.md)消除。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-120">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="5dc9e-121">在您开始导出后，搜索结果将准备好下载，这意味着它们会被上载到 Microsoft 云中的 Microsoft 提供的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="5dc9e-122">单击 "**导出**" 选项卡以显示事例的导出作业列表。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="5dc9e-123">您可能需要单击 "**刷新**" 以更新导出作业的列表，以便显示您创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="5dc9e-124">导出作业与对应的搜索具有相同的名称，并将 **_Export**追加到搜索名称。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="5dc9e-125">单击您创建的导出作业以在弹出页面上显示状态信息。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="5dc9e-126">此信息包括已转移到 Azure 存储位置的项目的百分比。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="5dc9e-127">在转移所有项目后，单击 "**下载结果**" 将搜索结果下载到您的本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="5dc9e-128">有关下载搜索结果的详细信息，请参阅[Export content search results](export-search-results.md#step-2-download-the-search-results)中的步骤2</span><span class="sxs-lookup"><span data-stu-id="5dc9e-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="5dc9e-129">导出多个搜索的结果</span><span class="sxs-lookup"><span data-stu-id="5dc9e-129">Export the results of multiple searches</span></span>

<span data-ttu-id="5dc9e-130">作为导出与事例相关联的单个搜索结果的替代方法，可以在单个导出作业中从同一事例导出多个搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="5dc9e-131">导出多个搜索的结果比一次性导出搜索结果更快、更轻松。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5dc9e-132">如果其中一个搜索配置为在保留时搜索位置，则不能导出多个搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="5dc9e-133">转到[https://compliance.microsoft.com](https://compliance.microsoft.com)并使用已为其分配了相应电子数据展示权限的用户帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="5dc9e-134">在 Microsoft 365 合规性中心的左侧导航窗格中，单击 "**全部显示**"，然后单击 "**电子数据展示 > 核心**"。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="5dc9e-135">在 "**核心电子数据展示**" 页上，选择要从中导出搜索结果的事例，然后单击 "**打开事例**"。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="5dc9e-136">在该案例的**主页**上，单击 "**搜索**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="5dc9e-137">在案例的搜索列表中，选中要从中导出搜索结果的两个或多个搜索旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="5dc9e-138">将显示 "**批量操作**" 弹出页面。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-138">The **Bulk actions** flyout page appears.</span></span> 

    ![在 "批量操作" 页面上，单击 "导出结果"](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="5dc9e-140">单击 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-140">Click **Export results**.</span></span>

   <span data-ttu-id="5dc9e-141">将显示 "**导出结果**" 页。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-141">The **Export results** page is displayed.</span></span> 

    !["导出结果" 页](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="5dc9e-143">在这种情况下，导出与核心电子数据展示事例相关联的多个搜索结果的工作流与导出单个搜索的搜索结果相同。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="5dc9e-144">请参阅上一节中的步骤5。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="5dc9e-145">有关导出多个搜索结果的详细信息</span><span class="sxs-lookup"><span data-stu-id="5dc9e-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="5dc9e-146">当您导出多个搜索的结果时，将使用**OR**运算符组合来自所有搜索的搜索查询，然后启动组合搜索。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="5dc9e-147">组合搜索的估计结果将显示在所选导出作业的飞出页面中。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="5dc9e-148">然后，将搜索结果复制到 Microsoft 云中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="5dc9e-149">复制作业的状态也会显示在弹出页面上。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="5dc9e-150">如前所述，在复制所有搜索结果后，可以将其下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="5dc9e-151">要导出的所有搜索的查询中的最大关键字数为500。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="5dc9e-152">这与单个搜索的限制相同。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-152">This is the same limit for a single search.</span></span> <span data-ttu-id="5dc9e-153">这是因为导出作业通过使用**OR**运算符组合了所有搜索查询。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="5dc9e-154">如果超过此限制，将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="5dc9e-155">在这种情况下，您必须从较少的搜索中导出结果或简化要导出的原始搜索的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="5dc9e-156">导出的搜索结果按在中找到该项目的内容位置进行组织。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="5dc9e-157">这意味着导出结果中的内容位置可能会有不同搜索返回的项目。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="5dc9e-158">例如，如果选择在一个 PST 文件中为每个邮箱导出电子邮件，则 PST 文件可能会有来自多个搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="5dc9e-159">如果您导出的多个搜索返回相同内容位置中的同一电子邮件项目或文档，将只导出该项目的一个副本。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="5dc9e-160">在创建多个搜索后，不能编辑该导出。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="5dc9e-161">例如，不能在导出作业中添加或删除搜索。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="5dc9e-162">您必须创建导出作业来更改要导出的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="5dc9e-163">在创建导出作业之后，您只可以将结果下载到计算机，重新启动导出，或删除导出作业。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="5dc9e-164">如果重新启动导出，则对构成导出作业的搜索的查询所做的任何更改都不会影响检索到的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="5dc9e-165">当您重新启动导出时，在创建导出作业时运行的相同组合搜索查询作业将会重新运行。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="5dc9e-166">此外，如果您重新启动导出，则复制到 Azure 存储位置的搜索结果会覆盖以前的结果。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="5dc9e-167">以前复制的结果将不能下载。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-167">The previous results that were copied won't be available to be downloaded.</span></span>

- <span data-ttu-id="5dc9e-168">在高级电子数据展示（经典）中准备多个搜索搜索的结果不可用。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-168">Preparing the results of multiple searches for analysis in Advanced eDiscovery (classic) isn't available.</span></span> <span data-ttu-id="5dc9e-169">您只能在高级电子数据展示（经典）中准备单次搜索的结果以进行分析。</span><span class="sxs-lookup"><span data-stu-id="5dc9e-169">You can only prepare the results of a single search for analysis in Advanced eDiscovery (classic).</span></span>
