---
title: 管理高级电子数据展示案例中的保管人
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
description: 了解如何在高级电子数据展示案例中查看详细信息、编辑和批量编辑保管人列表。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739865"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="58ce9-103">管理高级电子数据展示案例中的保管人</span><span class="sxs-lookup"><span data-stu-id="58ce9-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="58ce9-104">高级电子数据展示案例的"来源"选项卡上的"保管人"页包含已添加到案例的所有保管人的列表。</span><span class="sxs-lookup"><span data-stu-id="58ce9-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="58ce9-105">向案例添加保管人后，会自动从 Azure Active Directory 收集每个保管人的详细信息，并可以在高级电子数据展示中查看。</span><span class="sxs-lookup"><span data-stu-id="58ce9-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![管理保管人](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="58ce9-107">查看保管人详细信息</span><span class="sxs-lookup"><span data-stu-id="58ce9-107">View custodian details</span></span>

<span data-ttu-id="58ce9-108">若要查看有关保管人的详细信息，请单击"保管人"选项卡上列表中的 **保管** 人。将显示一个飞出页，其中包含有关保管人以下信息：</span><span class="sxs-lookup"><span data-stu-id="58ce9-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="58ce9-109">联系人信息</span><span class="sxs-lookup"><span data-stu-id="58ce9-109">Contact information</span></span>

  - <span data-ttu-id="58ce9-110">**显示名称** - 在保管人通讯簿中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="58ce9-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="58ce9-111">这通常是保管人的名字、中间名首字母和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="58ce9-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="58ce9-112">**邮件/SMTP** - 保管人的主 SMTP 地址，例如brianj@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="58ce9-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="58ce9-113">保管人的用户主体名称 (UPN) 列出。</span><span class="sxs-lookup"><span data-stu-id="58ce9-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="58ce9-114">**职务** - 保管人职务。</span><span class="sxs-lookup"><span data-stu-id="58ce9-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="58ce9-115">**部门** - 保管人工作部门的名称。</span><span class="sxs-lookup"><span data-stu-id="58ce9-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="58ce9-116">**经理** - 保管人经理。</span><span class="sxs-lookup"><span data-stu-id="58ce9-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="58ce9-117">指定的经理将收到此保管人的任何上报通信。</span><span class="sxs-lookup"><span data-stu-id="58ce9-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="58ce9-118">位置信息</span><span class="sxs-lookup"><span data-stu-id="58ce9-118">Location information</span></span>

  - <span data-ttu-id="58ce9-119">**城市** - 保管人所在的城市。</span><span class="sxs-lookup"><span data-stu-id="58ce9-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="58ce9-120">**State** - 保管人地址中的州或省。</span><span class="sxs-lookup"><span data-stu-id="58ce9-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="58ce9-121">**国家/地区** - 保管人所在的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="58ce9-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="58ce9-122">**Office** - 保管人业务地点的办公地点。</span><span class="sxs-lookup"><span data-stu-id="58ce9-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="58ce9-123">案例信息</span><span class="sxs-lookup"><span data-stu-id="58ce9-123">Case information</span></span>

  - <span data-ttu-id="58ce9-124">**保留状态** - 指示保管人是否已被置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="58ce9-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="58ce9-125">**通信状态**：指示保管人是否已发出保留通知。</span><span class="sxs-lookup"><span data-stu-id="58ce9-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="58ce9-126">如果保管人已发出通知，则此属性的此值为 **Published**。</span><span class="sxs-lookup"><span data-stu-id="58ce9-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="58ce9-127">如果保管人尚未发出通知，则状态为 **"未发布"。**</span><span class="sxs-lookup"><span data-stu-id="58ce9-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="58ce9-128">**Status** - 案例内保管人的状态。</span><span class="sxs-lookup"><span data-stu-id="58ce9-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="58ce9-129">" **活动"** 状态表示保管人是案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="58ce9-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="58ce9-130">如果从案例释放保管人，则状态更改为"**已释放"。**</span><span class="sxs-lookup"><span data-stu-id="58ce9-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="58ce9-131">数据源和索引信息</span><span class="sxs-lookup"><span data-stu-id="58ce9-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="58ce9-132">**数据源** - 显示与保管人关联的 (邮箱、网站和 Teams) 数据源的计数和类型。</span><span class="sxs-lookup"><span data-stu-id="58ce9-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="58ce9-133">**索引更新** 时间 - 指示上次触发高级索引作业的时间和日期。</span><span class="sxs-lookup"><span data-stu-id="58ce9-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="58ce9-134">此属性还将指示当前正在进行高级索引编制过程。</span><span class="sxs-lookup"><span data-stu-id="58ce9-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="58ce9-135">编辑保管人</span><span class="sxs-lookup"><span data-stu-id="58ce9-135">Edit a custodian</span></span>

<span data-ttu-id="58ce9-136">随着你的案例的进行，你可能会发现，可能有与特定保管人相关的其他数据源&您的案例。</span><span class="sxs-lookup"><span data-stu-id="58ce9-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="58ce9-137">在其他方案中，您可能需要删除已审阅并被视为不相关的某些数据源。</span><span class="sxs-lookup"><span data-stu-id="58ce9-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="58ce9-138">更新与保管人关联的数据源：</span><span class="sxs-lookup"><span data-stu-id="58ce9-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="58ce9-139">转到  **电子数据展示>电子数据展示并** 打开案例。</span><span class="sxs-lookup"><span data-stu-id="58ce9-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="58ce9-140">单击 **"源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="58ce9-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="58ce9-141">在"**保管人**"页上，从列表中选择保管人，然后单击飞出页上的"编辑"。</span><span class="sxs-lookup"><span data-stu-id="58ce9-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![编辑数据源](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="58ce9-143">单击 **"选择数据源"** 选项卡以更改保管人 Exchange 邮箱和 OneDrive 帐户的设置，然后单击"**选择数据源"。**</span><span class="sxs-lookup"><span data-stu-id="58ce9-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="58ce9-144">单击 **"选择其他数据源"** 选项卡，添加或删除与保管人关联的 Teams、SharePoint 或 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="58ce9-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="58ce9-145">有关与保管人关联的数据源详细信息，请参阅"将[保管人添加到案例"。](add-custodians-to-case.md)</span><span class="sxs-lookup"><span data-stu-id="58ce9-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="58ce9-146">单击 **"下一级** 保留"以启用或禁用保管人保留。</span><span class="sxs-lookup"><span data-stu-id="58ce9-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="58ce9-147">重新索引保管人数据</span><span class="sxs-lookup"><span data-stu-id="58ce9-147">Re-index custodian data</span></span>

<span data-ttu-id="58ce9-148">在大多数法律调查电子数据展示工作流中，在将保管人添加到法律案件之后，将搜索保管人数据的子集。</span><span class="sxs-lookup"><span data-stu-id="58ce9-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="58ce9-149">由于文件大小很大或数据可能损坏，与保管人关联的数据源中的某些项目可能会部分编制索引。</span><span class="sxs-lookup"><span data-stu-id="58ce9-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="58ce9-150">使用 [高级电子数据](indexing-custodian-data.md) 展示中的高级索引功能，大多数部分索引项都可以按需重新编制索引来自动修正。</span><span class="sxs-lookup"><span data-stu-id="58ce9-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="58ce9-151">向案例添加保管人时，由高级索引过程自动对位于与保管人关联的数据源 (数据重新编制) 。</span><span class="sxs-lookup"><span data-stu-id="58ce9-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="58ce9-152">这意味着您可以将数据留在就地，而不必下载并修正数据，然后脱机搜索) 。</span><span class="sxs-lookup"><span data-stu-id="58ce9-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="58ce9-153">但是，在法律案件生命周期内，新数据源可能与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="58ce9-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="58ce9-154">在这种情况下，可以通过重新运行高级索引过程来重新编制保管人数据的索引，以修正任何部分索引项并更新保管人数据的索引。</span><span class="sxs-lookup"><span data-stu-id="58ce9-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="58ce9-155">若要触发重新编制索引的过程以处理部分索引项，</span><span class="sxs-lookup"><span data-stu-id="58ce9-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="58ce9-156">转到  **电子数据展示>高级电子数据展示并** 打开案例。</span><span class="sxs-lookup"><span data-stu-id="58ce9-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="58ce9-157">单击 **"源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="58ce9-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="58ce9-158">在" **保管人** "页上，选择其数据必须重新索引的保管人。</span><span class="sxs-lookup"><span data-stu-id="58ce9-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="58ce9-159">在飞出页上，单击 **"更新索引"。**</span><span class="sxs-lookup"><span data-stu-id="58ce9-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="58ce9-160">将显示一个对话框，指出已创建索引作业。</span><span class="sxs-lookup"><span data-stu-id="58ce9-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="58ce9-161">重新编制保管人数据的索引是一个长期运行的过程;所创建的相应作业名为 **"重新索引保管人数据"。**</span><span class="sxs-lookup"><span data-stu-id="58ce9-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="58ce9-162">您可以通过监视"索引作业状态"列中的状态来跟踪"作业"选项卡或"保管人 **"选项卡上** 的进度。</span><span class="sxs-lookup"><span data-stu-id="58ce9-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="58ce9-163">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="58ce9-163">For more information, see:</span></span>

- [<span data-ttu-id="58ce9-164">解决处理错误</span><span class="sxs-lookup"><span data-stu-id="58ce9-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="58ce9-165">管理作业</span><span class="sxs-lookup"><span data-stu-id="58ce9-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="58ce9-166">从案例释放保管人</span><span class="sxs-lookup"><span data-stu-id="58ce9-166">Release a custodian from a case</span></span>

<span data-ttu-id="58ce9-167">在案例关闭、保管人不再承担保留案例内容的义务，或认为保管人不再与案例相关时，将释放保管人。</span><span class="sxs-lookup"><span data-stu-id="58ce9-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="58ce9-168">如果在发布保留通知后释放保管人，则向保管人发送发行通知。</span><span class="sxs-lookup"><span data-stu-id="58ce9-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="58ce9-169">此外，将删除对与保管人关联的数据源的任何保留。</span><span class="sxs-lookup"><span data-stu-id="58ce9-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="58ce9-170">如果保管人处于静默保留状态，其中未向他们发送任何法定保留通知，将不会发送释放通知，但会删除对与该保管人关联的数据源的任何保留。</span><span class="sxs-lookup"><span data-stu-id="58ce9-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="58ce9-171">释放保管人：</span><span class="sxs-lookup"><span data-stu-id="58ce9-171">To release a custodian:</span></span> 

1. <span data-ttu-id="58ce9-172">转到  **电子数据展示>电子数据展示并** 打开案例。</span><span class="sxs-lookup"><span data-stu-id="58ce9-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="58ce9-173">单击 **"源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="58ce9-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="58ce9-174">在 **"保管人** "页上，然后选择从案例释放的保管人。</span><span class="sxs-lookup"><span data-stu-id="58ce9-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="58ce9-175">在飞出页面上，单击 **"发布保管人"。**</span><span class="sxs-lookup"><span data-stu-id="58ce9-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="58ce9-176">将显示一个警告页，说明如果对与保管人关联的数据源设置保留，将删除保留，并且与其他高级电子数据展示案例关联的任何其他保留仍将适用。</span><span class="sxs-lookup"><span data-stu-id="58ce9-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="58ce9-177">这包括其他类型的保留和保留功能 (如 Microsoft 365 保留策略) 。</span><span class="sxs-lookup"><span data-stu-id="58ce9-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="58ce9-178">单击 **"** 是"以确认要释放保管人。</span><span class="sxs-lookup"><span data-stu-id="58ce9-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="58ce9-179">"保管人"选项卡上此用户的状态设置为"已释放"，并且飞出页上的"保留"状态更改为 **False。** </span><span class="sxs-lookup"><span data-stu-id="58ce9-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="58ce9-180">保管人可能同时涉及多个法律案件。</span><span class="sxs-lookup"><span data-stu-id="58ce9-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="58ce9-181">当保管人从案例释放时，其他事项的保留和通知不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="58ce9-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="58ce9-182">批量编辑保管人</span><span class="sxs-lookup"><span data-stu-id="58ce9-182">Bulk-edit custodians</span></span>

<span data-ttu-id="58ce9-183">您可以使用批量编辑器同时编辑多个保管人。</span><span class="sxs-lookup"><span data-stu-id="58ce9-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="58ce9-184">为此，只需在"保管人"选项卡上选择两个或多个保管人即可显示批量编辑器，然后单击其中一个任务。</span><span class="sxs-lookup"><span data-stu-id="58ce9-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![用于编辑多个保管人设置的飞出页](../media/AeDBulkEditCustodians.png)
