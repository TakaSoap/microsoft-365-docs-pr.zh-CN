---
title: 高级电子数据展示报告
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
description: ''
ms.openlocfilehash: c3bd87f6a6b06cf6fc75705073df5a95a1025a31
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079943"
---
# <a name="advanced-ediscovery-reports-preview"></a><span data-ttu-id="f693a-102">高级电子数据展示报告（预览）</span><span class="sxs-lookup"><span data-stu-id="f693a-102">Advanced eDiscovery reports (preview)</span></span>

<span data-ttu-id="f693a-103">高级电子数据展示报告可帮助您在整个组织中聚合事例数据，以优化数据分析和组织报告。</span><span class="sxs-lookup"><span data-stu-id="f693a-103">Advanced eDiscovery reports help you aggregate case data across your organization to streamline data analysis and organizational reporting.</span></span> <span data-ttu-id="f693a-104">高级电子数据展示报告功能包括几个内置报告，可帮助您解答类似的问题：</span><span class="sxs-lookup"><span data-stu-id="f693a-104">The Advanced eDiscovery reports feature includes several built-in reports to help you answer questions like:</span></span>

- <span data-ttu-id="f693a-105">对于我的组织中的所有案例，有多少活动保管人？</span><span class="sxs-lookup"><span data-stu-id="f693a-105">How many active custodians are there for all cases in my organization?</span></span>

- <span data-ttu-id="f693a-106">对于组织中的所有案例，有多少数据源处于保留状态？</span><span class="sxs-lookup"><span data-stu-id="f693a-106">How many data sources are on hold for all cases in my organization?</span></span>

- <span data-ttu-id="f693a-107">在上个月内为组织中的所有案例颁发了多少保留通知？</span><span class="sxs-lookup"><span data-stu-id="f693a-107">How many hold notifications have been issued in the last month for all cases in my organization?</span></span>

- <span data-ttu-id="f693a-108">在我的组织中有多少个活动和已关闭的事例？</span><span class="sxs-lookup"><span data-stu-id="f693a-108">How many active and closed cases are there in my organization?</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f693a-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="f693a-109">Before you begin</span></span>

- <span data-ttu-id="f693a-110">若要访问高级电子数据展示报告，您必须是电子数据展示管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="f693a-110">To access Advanced eDiscovery reports, you must be a member of the eDiscovery Admin role group.</span></span> <span data-ttu-id="f693a-111">作为此角色组的成员，将为你提供查看、筛选和导出报告中的数据所需的权限。</span><span class="sxs-lookup"><span data-stu-id="f693a-111">Being a member of this role group provides you with the necessary permissions to view, filter, and export the data in the reports.</span></span> <span data-ttu-id="f693a-112">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f693a-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f693a-113">每日更新一次高级电子数据展示报告。</span><span class="sxs-lookup"><span data-stu-id="f693a-113">Advanced eDiscovery reports are refreshed daily.</span></span> <span data-ttu-id="f693a-114">因此，在创建新事例、保管人、数据源和通信以及它们出现在相应报告中时，可能会有延迟。</span><span class="sxs-lookup"><span data-stu-id="f693a-114">As a result, there may be a delay when new cases, custodians, data sources, and communications are created and when they appear in the corresponding report.</span></span>

<span data-ttu-id="f693a-115">访问高级电子数据展示报告：</span><span class="sxs-lookup"><span data-stu-id="f693a-115">To access the Advanced eDiscovery reports:</span></span>

1. <span data-ttu-id="f693a-116">转到 https://protection.office.com</span><span class="sxs-lookup"><span data-stu-id="f693a-116">Go to https://protection.office.com</span></span>
  
2. <span data-ttu-id="f693a-117">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f693a-117">Sign into Office 365 using your work or school account.</span></span>
  
3. <span data-ttu-id="f693a-118">在安全 & 合规性中心中，单击 "**电子数据展示 > 高级电子数据展示**"。</span><span class="sxs-lookup"><span data-stu-id="f693a-118">In the Security & Compliance Center, click **eDiscovery > Advanced eDiscovery**.</span></span>
  
   <span data-ttu-id="f693a-119">在**高级电子数据展示**主页上，将在页面顶部显示事例、保管人、数据源和通信报告选项卡。</span><span class="sxs-lookup"><span data-stu-id="f693a-119">On the **Advanced eDiscovery** home page, the Case, Custodian, Data Source, and Communications report tabs are displayed across the top of the page.</span></span> 
  
   ![主页上的高级电子数据展示报告](../media/report-home.png)

5. <span data-ttu-id="f693a-121">若要查看报告，请单击 "报告" 选项卡，然后，如果需要，可以执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f693a-121">To view a report, click a report tab, and then if necessary you can do one of the following things:</span></span>

   ![您可以筛选或下载报告数据](../media/AeDReportsFilterDownload.png)

   <span data-ttu-id="f693a-123">a.</span><span class="sxs-lookup"><span data-stu-id="f693a-123">a.</span></span> <span data-ttu-id="f693a-124">单击 "**筛选**" 以缩小报告数据。</span><span class="sxs-lookup"><span data-stu-id="f693a-124">Click **Filter** to narrow the report data.</span></span> <span data-ttu-id="f693a-125">您可以对每个报告的不同属性进行筛选。</span><span class="sxs-lookup"><span data-stu-id="f693a-125">You can filter on different properties for each report.</span></span>
  
   <span data-ttu-id="f693a-126">b.</span><span class="sxs-lookup"><span data-stu-id="f693a-126">b.</span></span> <span data-ttu-id="f693a-127">单击 "**下载到 csv** " 将报告数据导出到 csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f693a-127">Click **Download to CSV** to export the report data to a CSV file.</span></span>

## <a name="case-report"></a><span data-ttu-id="f693a-128">案例报告</span><span class="sxs-lookup"><span data-stu-id="f693a-128">Case report</span></span>

<span data-ttu-id="f693a-129">事例报告聚合了组织中活动和已关闭的预先展示的电子数据展示事例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f693a-129">The Case report aggregates information about active and closed Advance eDiscovery cases in your organization.</span></span>

|<span data-ttu-id="f693a-130">列</span><span class="sxs-lookup"><span data-stu-id="f693a-130">Column</span></span>        |<span data-ttu-id="f693a-131">说明</span><span class="sxs-lookup"><span data-stu-id="f693a-131">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="f693a-132">事例 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-132">Case ID</span></span> | <span data-ttu-id="f693a-133">每个事例的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-133">The unique identifier for each case.</span></span>| 
|<span data-ttu-id="f693a-134">案例名称</span><span class="sxs-lookup"><span data-stu-id="f693a-134">Case name</span></span> | <span data-ttu-id="f693a-135">用户定义的事例名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-135">User-defined name of the case.</span></span>|
|<span data-ttu-id="f693a-136">状态</span><span class="sxs-lookup"><span data-stu-id="f693a-136">Status</span></span> | <span data-ttu-id="f693a-137">指示该事例是处于活动状态还是已关闭状态。</span><span class="sxs-lookup"><span data-stu-id="f693a-137">Indicates if the case is active or closed.</span></span>|
|<span data-ttu-id="f693a-138">创建日期</span><span class="sxs-lookup"><span data-stu-id="f693a-138">Date created</span></span> |<span data-ttu-id="f693a-139">创建事例的第一天。</span><span class="sxs-lookup"><span data-stu-id="f693a-139">Th date when the case was created.</span></span> <span data-ttu-id="f693a-140">日期采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f693a-140">Dates are in UTC format.</span></span>|
|<span data-ttu-id="f693a-141">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="f693a-141">Last modified</span></span> |<span data-ttu-id="f693a-142">案例结束或最后更新的日期。</span><span class="sxs-lookup"><span data-stu-id="f693a-142">The date when the case was closed or last updated.</span></span> <span data-ttu-id="f693a-143">日期采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f693a-143">Dates are in UTC format.</span></span>| 
|||

## <a name="custodian-report"></a><span data-ttu-id="f693a-144">保管人报告</span><span class="sxs-lookup"><span data-stu-id="f693a-144">Custodian report</span></span>

<span data-ttu-id="f693a-145">在电子数据展示工作流中，属于法律案件或调查主题的个人称为*数据保管人*（或仅是*保管人*），并定义为 "具有文档或电子文件的管理控制的人员"。</span><span class="sxs-lookup"><span data-stu-id="f693a-145">In the eDiscovery workflow, individuals who are the subject of a legal case or investigation are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="f693a-146">保管人报告可帮助您识别组织中所有案例的数据源处于保留状态的所有保管人。</span><span class="sxs-lookup"><span data-stu-id="f693a-146">The Custodian report helps you identify all the custodians whose data sources are placed on hold for all cases in your organization.</span></span>

|<span data-ttu-id="f693a-147">列</span><span class="sxs-lookup"><span data-stu-id="f693a-147">Column</span></span>         |<span data-ttu-id="f693a-148">说明</span><span class="sxs-lookup"><span data-stu-id="f693a-148">Description</span></span>|
|:-------------|:-------------|
|<span data-ttu-id="f693a-149">保管人名称</span><span class="sxs-lookup"><span data-stu-id="f693a-149">Custodian name</span></span>| <span data-ttu-id="f693a-150">Active Directory 中的保管人的名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-150">The name of the custodian in Active Directory.</span></span>|
|<span data-ttu-id="f693a-151">保管人 UPN</span><span class="sxs-lookup"><span data-stu-id="f693a-151">Custodian UPN</span></span> | <span data-ttu-id="f693a-152">保管人的用户主体名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-152">The user principal name of the custodian.</span></span>|
|<span data-ttu-id="f693a-153">保管人 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-153">Custodian ID</span></span> | <span data-ttu-id="f693a-154">在给定事例中，管理员的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-154">The unique identifier for the custodian within a given case.</span></span> |
|<span data-ttu-id="f693a-155">案例名称</span><span class="sxs-lookup"><span data-stu-id="f693a-155">Case name</span></span> | <span data-ttu-id="f693a-156">用户定义的事例名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-156">The user-defined name of the case.</span></span>|
|<span data-ttu-id="f693a-157">保留状态</span><span class="sxs-lookup"><span data-stu-id="f693a-157">Hold status</span></span> | <span data-ttu-id="f693a-158">指示保管人当前是否处于保留状态，或者是否已从案例中释放。</span><span class="sxs-lookup"><span data-stu-id="f693a-158">Indicates if the custodian is currently on hold or if they have been released from the case.</span></span>|
|<span data-ttu-id="f693a-159">事例 Id</span><span class="sxs-lookup"><span data-stu-id="f693a-159">Case Id</span></span> | <span data-ttu-id="f693a-160">事例的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-160">The unique identifier for the case.</span></span>|
|<span data-ttu-id="f693a-161">通信状态</span><span class="sxs-lookup"><span data-stu-id="f693a-161">Communication status</span></span> |<span data-ttu-id="f693a-162">指示是否已向保管人颁发合法保留通知。</span><span class="sxs-lookup"><span data-stu-id="f693a-162">Indicates if the custodian was issued a legal hold notification or not.</span></span> |
|<span data-ttu-id="f693a-163">已添加保管人</span><span class="sxs-lookup"><span data-stu-id="f693a-163">Custodian added</span></span> | <span data-ttu-id="f693a-164">将管理员添加到案例的日期。</span><span class="sxs-lookup"><span data-stu-id="f693a-164">The date the custodian was added to the case.</span></span> <span data-ttu-id="f693a-165">日期采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f693a-165">Dates are in UTC format.</span></span>|
|||

## <a name="data-source-report"></a><span data-ttu-id="f693a-166">数据源报告</span><span class="sxs-lookup"><span data-stu-id="f693a-166">Data source report</span></span>

<span data-ttu-id="f693a-167">您可以使用高级电子数据展示事例来创建保留，以保留可能与事例相关的内容。</span><span class="sxs-lookup"><span data-stu-id="f693a-167">You can use an Advanced eDiscovery case to create holds to preserve content that may be relevant to the case.</span></span> <span data-ttu-id="f693a-168">使用高级电子数据展示保留功能，可以将保留在保管人及其数据源上。</span><span class="sxs-lookup"><span data-stu-id="f693a-168">Using the Advanced eDiscovery hold capabilities, you can place holds on custodians and their data sources.</span></span> <span data-ttu-id="f693a-169">此外，还可以对邮箱和 OneDrive for business 帐户设置非 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="f693a-169">Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business accounts.</span></span> <span data-ttu-id="f693a-170">您可以使用 "数据源报告" 在组织中的所有情况下聚合有关保留内容位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f693a-170">You can use the data sources report to aggregate details about content locations on hold for all cases in your organization.</span></span>

|<span data-ttu-id="f693a-171">列</span><span class="sxs-lookup"><span data-stu-id="f693a-171">Column</span></span>        |<span data-ttu-id="f693a-172">说明</span><span class="sxs-lookup"><span data-stu-id="f693a-172">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="f693a-173">事例 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-173">Case ID</span></span> |<span data-ttu-id="f693a-174">每个事例的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-174">The unique identifier for each case.</span></span> |
|<span data-ttu-id="f693a-175">Workload</span><span class="sxs-lookup"><span data-stu-id="f693a-175">Workload</span></span> |<span data-ttu-id="f693a-176">指示置于保留状态的内容位置的类型（例如，Exchange 或 SharePoint）。</span><span class="sxs-lookup"><span data-stu-id="f693a-176">Indicates the type of content location placed on hold (for example, Exchange or SharePoint).</span></span>
|<span data-ttu-id="f693a-177">位置名称</span><span class="sxs-lookup"><span data-stu-id="f693a-177">Location name</span></span> |<span data-ttu-id="f693a-178">指示内容位置的 SMTP 地址（对于 Exchange 邮箱）或 URL （对于 SharePoint 网站）。</span><span class="sxs-lookup"><span data-stu-id="f693a-178">Indicates the SMTP address (for Exchange mailboxes) or the URL (for SharePoint sites) of the content location.</span></span> | 
|<span data-ttu-id="f693a-179">保管人 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-179">Custodian ID</span></span> |<span data-ttu-id="f693a-180">如果数据源属于管理员，则此列显示在给定情况下保管人的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-180">If the data source belongs to a custodian, this column shows the unique identifier for the custodian in a given case.</span></span> <span data-ttu-id="f693a-181">对于非 custodial 位置，此列将为 null。</span><span class="sxs-lookup"><span data-stu-id="f693a-181">This column will be null for non-custodial locations.</span></span>|
|<span data-ttu-id="f693a-182">保管人名称</span><span class="sxs-lookup"><span data-stu-id="f693a-182">Custodian name</span></span> |<span data-ttu-id="f693a-183">Active Directory 中的保管人的名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-183">The name of the custodian in Active Directory.</span></span>| 
|<span data-ttu-id="f693a-184">案例名称</span><span class="sxs-lookup"><span data-stu-id="f693a-184">Case name</span></span> |<span data-ttu-id="f693a-185">用户定义的事例名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-185">The user-defined name of the case.</span></span>| 
|<span data-ttu-id="f693a-186">状态</span><span class="sxs-lookup"><span data-stu-id="f693a-186">Status</span></span> |<span data-ttu-id="f693a-187">指示内容位置当前是否处于保留状态。</span><span class="sxs-lookup"><span data-stu-id="f693a-187">Indicates if the content location is currently on hold.</span></span> | 
|<span data-ttu-id="f693a-188">保留策略 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-188">Hold policy ID</span></span> |<span data-ttu-id="f693a-189">包含内容位置的保留的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-189">The unique identifier for the hold that contains the content location.</span></span> | 
|<span data-ttu-id="f693a-190">保留创建日期</span><span class="sxs-lookup"><span data-stu-id="f693a-190">Hold created date</span></span> |<span data-ttu-id="f693a-191">指示创建保留策略的日期。</span><span class="sxs-lookup"><span data-stu-id="f693a-191">Indicates the date when the hold policy was created.</span></span> <span data-ttu-id="f693a-192">日期采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f693a-192">Dates are in UTC format.</span></span> | 
|<span data-ttu-id="f693a-193">保留策略名称</span><span class="sxs-lookup"><span data-stu-id="f693a-193">Hold policy name</span></span> |<span data-ttu-id="f693a-194">包含内容位置的保留的名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-194">The name of the hold that contains the content location.</span></span> |
|<span data-ttu-id="f693a-195">保留修改日期</span><span class="sxs-lookup"><span data-stu-id="f693a-195">Hold modified date</span></span> |<span data-ttu-id="f693a-196">上次修改保留的日期。</span><span class="sxs-lookup"><span data-stu-id="f693a-196">The date when the hold was last modified.</span></span> <span data-ttu-id="f693a-197">日期采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f693a-197">Dates are in UTC format.</span></span>| 
|<span data-ttu-id="f693a-198">保留上次修改者</span><span class="sxs-lookup"><span data-stu-id="f693a-198">Hold last modified by</span></span>|<span data-ttu-id="f693a-199">上次修改保留的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-199">The name of the user that last modified the hold.</span></span>| 
|||

## <a name="communication-report"></a><span data-ttu-id="f693a-200">通信报告</span><span class="sxs-lookup"><span data-stu-id="f693a-200">Communication report</span></span>

<span data-ttu-id="f693a-201">您的组织可以发出法律封存通知，以通知保管人在法律案例或调查过程中保留相关信息的义务。</span><span class="sxs-lookup"><span data-stu-id="f693a-201">Your organization may issue legal hold notices to notify custodians of their obligation to preserve relevant information as part of legal case or investigation.</span></span> <span data-ttu-id="f693a-202">您可以使用通信报告查看确认、提醒、升级和其他类型的通信的聚合数据。</span><span class="sxs-lookup"><span data-stu-id="f693a-202">You can use the communications report to view aggregate data on acknowledgments, reminders, escalations, and other types of communications.</span></span>

|<span data-ttu-id="f693a-203">列</span><span class="sxs-lookup"><span data-stu-id="f693a-203">Column</span></span>         |<span data-ttu-id="f693a-204">说明</span><span class="sxs-lookup"><span data-stu-id="f693a-204">Description</span></span>|
| -------------|-------------|
|<span data-ttu-id="f693a-205">事例 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-205">Case ID</span></span> | <span data-ttu-id="f693a-206">事例的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-206">The unique identifier for the case.</span></span>|
|<span data-ttu-id="f693a-207">案例名称</span><span class="sxs-lookup"><span data-stu-id="f693a-207">Case name</span></span> | <span data-ttu-id="f693a-208">用户定义的事例名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-208">User-defined name of the case.</span></span>|
|<span data-ttu-id="f693a-209">保管人 ID</span><span class="sxs-lookup"><span data-stu-id="f693a-209">Custodian ID</span></span> |<span data-ttu-id="f693a-210">在给定情况下，保管人的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f693a-210">The unique identifier for the custodian in a given case.</span></span>|
|<span data-ttu-id="f693a-211">保管人名称</span><span class="sxs-lookup"><span data-stu-id="f693a-211">Custodian name</span></span> |<span data-ttu-id="f693a-212">保管人的名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-212">The name of the custodian.</span></span>|
|<span data-ttu-id="f693a-213">通知类型</span><span class="sxs-lookup"><span data-stu-id="f693a-213">Notice type</span></span> |<span data-ttu-id="f693a-214">指示颁发给保管人的声明类型。</span><span class="sxs-lookup"><span data-stu-id="f693a-214">Indicates the type of notice that was issued to the custodian.</span></span>|
|<span data-ttu-id="f693a-215">签发专员</span><span class="sxs-lookup"><span data-stu-id="f693a-215">Issuing officer</span></span> |<span data-ttu-id="f693a-216">发出合法保留通知的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="f693a-216">The name of the user that issued the legal hold notification.</span></span>|
|<span data-ttu-id="f693a-217">通知事件</span><span class="sxs-lookup"><span data-stu-id="f693a-217">Notification event</span></span>|<span data-ttu-id="f693a-218">指示发送给用户的合法保留通知消息。</span><span class="sxs-lookup"><span data-stu-id="f693a-218">Indicates the legal hold notification message sent to the user.</span></span> <span data-ttu-id="f693a-219">可能的值包括：提醒、升级、确认和保留发布。</span><span class="sxs-lookup"><span data-stu-id="f693a-219">Possible values include: Reminder, Escalation, Acknowledgment, and Hold Issuance.</span></span>|
|<span data-ttu-id="f693a-220">发送日期</span><span class="sxs-lookup"><span data-stu-id="f693a-220">Date sent</span></span> |<span data-ttu-id="f693a-221">发出通信的日期。</span><span class="sxs-lookup"><span data-stu-id="f693a-221">The date when the communication was issued.</span></span> <span data-ttu-id="f693a-222">对于确认，此列指示管理员确认通知的时间。</span><span class="sxs-lookup"><span data-stu-id="f693a-222">For acknowledgments, this column indicates the time that the notice was acknowledged by the custodian.</span></span> <span data-ttu-id="f693a-223">日期采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="f693a-223">Dates are in UTC format.</span></span>|
|||
