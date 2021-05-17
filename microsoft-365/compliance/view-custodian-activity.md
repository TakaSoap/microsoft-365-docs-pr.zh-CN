---
title: 查看保管审核活动
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用 Advanced eDiscovery保管人管理工具轻松访问和搜索你案例内保管人的活动。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024762"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="95b9d-103">查看保管审核活动</span><span class="sxs-lookup"><span data-stu-id="95b9d-103">View custodian audit activity</span></span>

<span data-ttu-id="95b9d-104">需要了解用户是否查看了特定文档或从其邮箱中清除了某项？</span><span class="sxs-lookup"><span data-stu-id="95b9d-104">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="95b9d-105">Advanced eDiscovery现在与安全与合规审核日志中的现有 & 搜索工具集成。</span><span class="sxs-lookup"><span data-stu-id="95b9d-105">Advanced eDiscovery is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="95b9d-106">通过使用此嵌入体验，Advanced eDiscovery保管人管理工具，通过轻松访问和搜索你案例内保管人的活动来加快调查。</span><span class="sxs-lookup"><span data-stu-id="95b9d-106">Using this embedded experience, you can use the Advanced eDiscovery Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="get-permissions"></a><span data-ttu-id="95b9d-107">获取权限</span><span class="sxs-lookup"><span data-stu-id="95b9d-107">Get permissions</span></span>

<span data-ttu-id="95b9d-108">必须分配有 Exchange Online 中的“仅供查看审核日志”或“审核日志”角色才能搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="95b9d-108">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="95b9d-109">默认情况下，在 Exchange 管理中心中的“权限”页上将这些角色分配给“合规性管理”和“组织管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="95b9d-109">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="95b9d-110">若要让用户能够使用最低权限级别搜索审核日志，可以在 Exchange Online 中创建自定义角色组，添加“仅供查看审核日志”或“审核日志”角色，然后将用户添加为新角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="95b9d-110">To give a user the ability to search the Advanced eDiscovery audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="95b9d-111">有关详细信息，请参阅在 Exchange Online 中管理角色组。</span><span class="sxs-lookup"><span data-stu-id="95b9d-111">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95b9d-112">如果在安全 & 合规中心的"权限"页上为用户分配"View-Only审核日志"或"审核日志"角色，他们将无法搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="95b9d-112">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the audit log.</span></span> <span data-ttu-id="95b9d-113">必须在 Exchange Online 中分配权限。</span><span class="sxs-lookup"><span data-stu-id="95b9d-113">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="95b9d-114">这是因为用于搜索审核日志的基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95b9d-114">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a><span data-ttu-id="95b9d-115">步骤 1：在审核日志搜索由保管人执行的活动</span><span class="sxs-lookup"><span data-stu-id="95b9d-115">Step 1: Search the audit log for activities performed by a custodian</span></span>

1. <span data-ttu-id="95b9d-116">转到 **电子数据展示> Advanced eDiscovery** 并打开案例。</span><span class="sxs-lookup"><span data-stu-id="95b9d-116">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="95b9d-117">单击" **源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="95b9d-117">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="95b9d-118">在" **保管人"** 页上，从列表中选择保管人，然后单击飞出页面上的" **查看保管人** 活动"。</span><span class="sxs-lookup"><span data-stu-id="95b9d-118">On the **Custodians** page, select a custodian from the list, and then click **View custodian activity** on the flyout page.</span></span>

    <span data-ttu-id="95b9d-119">将显示 Custodian 活动搜索页。</span><span class="sxs-lookup"><span data-stu-id="95b9d-119">The Custodian activities search page is displayed.</span></span> <span data-ttu-id="95b9d-120">请注意，在上一步中选择的保管人显示在 **"保管人** "下拉框中。</span><span class="sxs-lookup"><span data-stu-id="95b9d-120">Note the custodian you selected in the previous step is displayed in the **Custodian** drop-down box.</span></span> <span data-ttu-id="95b9d-121">可以在下拉框中选择不同的保管人，但一次只能搜索一个保管人的活动。</span><span class="sxs-lookup"><span data-stu-id="95b9d-121">You can select different custodians in the drop-down box, but you can only search for activities for one custodian at a time.</span></span>

    ![保管活动搜索页面](../media/AeDCustodianActivities1.png)
   
4. <span data-ttu-id="95b9d-123">配置以下搜索条件：</span><span class="sxs-lookup"><span data-stu-id="95b9d-123">Configure the following search criteria:</span></span>
      
   1. <span data-ttu-id="95b9d-124">**活动** - 单击下拉列表以显示可搜索的活动。</span><span class="sxs-lookup"><span data-stu-id="95b9d-124">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="95b9d-125">运行搜索后，仅将显示所选活动的审核日志项目。</span><span class="sxs-lookup"><span data-stu-id="95b9d-125">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="95b9d-126">选择 **"显示所有活动的结果** "将显示保管人执行的所有匹配其他搜索条件的活动的结果。</span><span class="sxs-lookup"><span data-stu-id="95b9d-126">Selecting **Show results for all activities** will display results for all activities performed by the custodian that match the other search criteria.</span></span>

      ![活动列表](../media/CustodianActivityAudit.PNG)
      
   1. <span data-ttu-id="95b9d-128">**开始日期和结束日期** - 选择日期和时间范围以显示该时段内发生的事件。</span><span class="sxs-lookup"><span data-stu-id="95b9d-128">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="95b9d-129">默认情况下选择最近七天。</span><span class="sxs-lookup"><span data-stu-id="95b9d-129">The last seven days are selected by default.</span></span> <span data-ttu-id="95b9d-130">日期和时间将以协调世界时 (UTC) 格式显示。</span><span class="sxs-lookup"><span data-stu-id="95b9d-130">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="95b9d-131">可以指定的最大日期范围是一年。</span><span class="sxs-lookup"><span data-stu-id="95b9d-131">The maximum date range that you can specify is one year.</span></span>
      
   1. <span data-ttu-id="95b9d-132">**保管人** - 单击此框，然后选择要显示其搜索结果的特定保管人。</span><span class="sxs-lookup"><span data-stu-id="95b9d-132">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="95b9d-133">在此框中选择的用户执行的选定活动的审核记录将显示在结果列表中。</span><span class="sxs-lookup"><span data-stu-id="95b9d-133">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
5. <span data-ttu-id="95b9d-134">单击</span><span class="sxs-lookup"><span data-stu-id="95b9d-134">Click</span></span> ![搜索按钮](../media/SearchButton.PNG)  <span data-ttu-id="95b9d-136">以使用搜索条件运行搜索。</span><span class="sxs-lookup"><span data-stu-id="95b9d-136">to run the search using your search criteria.</span></span> <span data-ttu-id="95b9d-137">将加载搜索结果，片刻后，它们将显示在"保管人活动"搜索页上的"结果"下。</span><span class="sxs-lookup"><span data-stu-id="95b9d-137">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="95b9d-138">步骤 2：查看审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="95b9d-138">Step 2: View the audit log search results</span></span>

<span data-ttu-id="95b9d-139">"保管人审核"审核日志页上的"结果"下显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="95b9d-139">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="95b9d-140">最多 5，000 个 (事件) 事件以 150 个事件为增量显示。</span><span class="sxs-lookup"><span data-stu-id="95b9d-140">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="95b9d-141">若要显示更多事件，可以使用“结果”窗格中的滚动条，或按 Shift+End 显示随后的 150 个事件。</span><span class="sxs-lookup"><span data-stu-id="95b9d-141">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="95b9d-142">结果包含有关搜索返回的每个事件的以下信息。</span><span class="sxs-lookup"><span data-stu-id="95b9d-142">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="95b9d-143">“**日期**”：事件发生的日期和时间（采用 UTC 格式）。</span><span class="sxs-lookup"><span data-stu-id="95b9d-143">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="95b9d-144">“**IP 地址**”：记录活动时所用设备的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="95b9d-144">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="95b9d-145">IP 地址显示为 IPv4 或 IPv6 地址格式。</span><span class="sxs-lookup"><span data-stu-id="95b9d-145">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="95b9d-146">**用户**：执行触发事件的操作的用户（或服务帐户）。</span><span class="sxs-lookup"><span data-stu-id="95b9d-146">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="95b9d-147">“**活动**”：用户执行的活动。</span><span class="sxs-lookup"><span data-stu-id="95b9d-147">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="95b9d-148">此值对应于你在"活动"下拉列表中选定的活动。</span><span class="sxs-lookup"><span data-stu-id="95b9d-148">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="95b9d-149">对于来自 Exchange 管理员审核日志的事件，此列中的值为 Exchange cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95b9d-149">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="95b9d-150">“**项目**”：由于相应活动而创建或修改的对象。</span><span class="sxs-lookup"><span data-stu-id="95b9d-150">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="95b9d-151">例如已查看或修改的文件或已更新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="95b9d-151">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="95b9d-152">并非所有活动在此列中都具有值。</span><span class="sxs-lookup"><span data-stu-id="95b9d-152">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="95b9d-153">**详细信息**：有关活动的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="95b9d-153">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="95b9d-154">同样，并非所有活动均具有此值。</span><span class="sxs-lookup"><span data-stu-id="95b9d-154">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="95b9d-155">步骤 3：筛选搜索结果</span><span class="sxs-lookup"><span data-stu-id="95b9d-155">Step 3: Filter the search results</span></span>

<span data-ttu-id="95b9d-156">除排序外，你还可以筛选审核日志搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="95b9d-156">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="95b9d-157">这可以帮助您快速筛选特定用户或活动的结果。</span><span class="sxs-lookup"><span data-stu-id="95b9d-157">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="95b9d-158">若要筛选结果，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95b9d-158">To filter the results:</span></span>

 1. <span data-ttu-id="95b9d-159">创建并运行审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="95b9d-159">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="95b9d-160">结果显示后，单击“**筛选结果**”。</span><span class="sxs-lookup"><span data-stu-id="95b9d-160">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="95b9d-161">每个列标题下将显示关键字框。</span><span class="sxs-lookup"><span data-stu-id="95b9d-161">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="95b9d-162">根据要筛选的列，单击列标题下的其中一个框并键入字词。</span><span class="sxs-lookup"><span data-stu-id="95b9d-162">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="95b9d-163">结果将动态重新调整以显示符合筛选条件的事件。</span><span class="sxs-lookup"><span data-stu-id="95b9d-163">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="95b9d-164">若要清除筛选器，请单击筛选器框中的 **X** 或仅单击"隐藏 **筛选"。**</span><span class="sxs-lookup"><span data-stu-id="95b9d-164">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="95b9d-165">将搜索结果导出到文件</span><span class="sxs-lookup"><span data-stu-id="95b9d-165">Export the search results to a file</span></span>

<span data-ttu-id="95b9d-166">可以将搜索的结果导出到审核日志本地计算机上的 CSV (CSV) 逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="95b9d-166">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="95b9d-167">可以在文件包中打开Microsoft Excel并使用搜索、排序、筛选和拆分包含多值单元格的单个列 (等功能，) 多个列。</span><span class="sxs-lookup"><span data-stu-id="95b9d-167">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="95b9d-168">运行审核日志搜索，然后修订搜索条件直到获得所需结果。</span><span class="sxs-lookup"><span data-stu-id="95b9d-168">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="95b9d-169">单击“导出结果”，然后选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="95b9d-169">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="95b9d-170">**保存加载的结果：** 选择此选项可仅导出在保管人审核日志搜索页上的结果 **下显示的** 条目。 </span><span class="sxs-lookup"><span data-stu-id="95b9d-170">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="95b9d-171">下载的 CSV 文件包含（“日期”、“用户”、“活动”、“项目”和“详细信息”）页面上显示的相同列（和数据）。</span><span class="sxs-lookup"><span data-stu-id="95b9d-171">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="95b9d-172">CSV 文件中 (标题为"more **) "** 的附加列，其中包含来自该条目审核日志详细信息。</span><span class="sxs-lookup"><span data-stu-id="95b9d-172">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="95b9d-173">由于你将导出“审核日志搜索”页上已加载（且可查看）的相同结果，因此最多可导出 5,000 个条目。</span><span class="sxs-lookup"><span data-stu-id="95b9d-173">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="95b9d-174">**下载所有结果：** 选择此选项可导出来自满足搜索条件的审核日志条目。</span><span class="sxs-lookup"><span data-stu-id="95b9d-174">**Download all results:** Choose this option to export all entries from the audit log that meet the search criteria.</span></span> <span data-ttu-id="95b9d-175">对于一大组搜索结果，选择此选项可从 审核日志 下载所有条目，以及可在保管人审核日志搜索页上显示的 5，000 个结果。 </span><span class="sxs-lookup"><span data-stu-id="95b9d-175">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="95b9d-176">此选项将原始数据从 审核日志 CSV 文件，并包含名为 AuditData 的列中 审核日志 条目的其他信息。</span><span class="sxs-lookup"><span data-stu-id="95b9d-176">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="95b9d-177">如果选择此导出选项，下载该文件可能需要更长时间，因为文件可能比选择其他选项下载的文件大得多。</span><span class="sxs-lookup"><span data-stu-id="95b9d-177">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="95b9d-178">你可以将最多 50,000 个条目从单个审核日志搜索中下载到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="95b9d-178">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="95b9d-179">如果下载了 50,000 个条目到 CSV 文件，则可以假定可能存在超过 50,000 个符合搜索条件的事件。</span><span class="sxs-lookup"><span data-stu-id="95b9d-179">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="95b9d-180">若要导出的条目超出此限制，请尝试使用日期范围以减少审核日志项目。</span><span class="sxs-lookup"><span data-stu-id="95b9d-180">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="95b9d-181">你可能需要使用更小日期范围运行多个搜索来导出超过 50,000 个条目。</span><span class="sxs-lookup"><span data-stu-id="95b9d-181">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="95b9d-182">选择导出选项后，窗口底部会显示一条消息，提示您打开 CSV 文件、将其保存到"下载"文件夹或将其保存到特定文件夹</span><span class="sxs-lookup"><span data-stu-id="95b9d-182">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="95b9d-183">有关查看、筛选或导出搜索结果审核日志，请参阅在安全与合规审核日志搜索&[搜索。](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="95b9d-183">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
