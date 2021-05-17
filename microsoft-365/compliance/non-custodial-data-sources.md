---
title: 将非安全数据源添加到Advanced eDiscovery案例
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
description: 您可以将非安全数据源添加到Advanced eDiscovery案例，并保留该数据源。 非索引数据源会重新编制索引，因此将重新处理标记为部分索引的任何内容，使其完全且快速可搜索。
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740349"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="dfdcb-104">将非安全数据源添加到Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="dfdcb-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="dfdcb-105">在这种情况下Advanced eDiscovery，并不一定满足将Microsoft 365数据源与事例保管人相关联的需求。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="dfdcb-106">但是，您可能仍然需要将该数据与案例关联，以便可以对其进行搜索、将其添加到审阅集，并分析和审阅数据。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="dfdcb-107">Advanced eDiscovery中的功能称为"*非* 托管数据源"，允许您向案例添加数据，而无需将其与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="dfdcb-108">它还将相同的Advanced eDiscovery功能应用于可用于与保管人关联的数据的非托管数据。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="dfdcb-109">可应用于非存储数据的两个最有用的内容是将其置于保留状态，然后使用 [高级索引处理它](indexing-custodian-data.md)。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="dfdcb-110">添加非安全数据源</span><span class="sxs-lookup"><span data-stu-id="dfdcb-110">Add a non-custodial data source</span></span>

<span data-ttu-id="dfdcb-111">按照以下步骤添加和管理非托管数据源，以在Advanced eDiscovery数据源。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="dfdcb-112">在 **Advanced eDiscovery** 主页上，单击要将数据添加到的大小写。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="dfdcb-113">单击"**数据源"** 选项卡，然后单击"**添加数据源**  >  **""添加数据位置"。**</span><span class="sxs-lookup"><span data-stu-id="dfdcb-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="dfdcb-114">在 **"新建非空** 数据位置"飞出页上，选择要添加到案例的数据源。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="dfdcb-115">可以添加多个邮箱和网站，方法是展开 **SharePoint或Exchange\*\*\*\*部分，** 然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="dfdcb-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![将SharePoint网站Exchange邮箱添加为非安全数据源](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="dfdcb-117">**SharePoint** - 单击 **"编辑"** 添加网站。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="dfdcb-118">在列表中选择网站，或者可以通过在搜索栏中键入网站的 URL 来搜索网站。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="dfdcb-119">选择要添加为非保管人数据源的网站，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="dfdcb-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="dfdcb-120">**Exchange** - 单击 **"编辑**"添加邮箱。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="dfdcb-121">键入名称或别名 (在邮箱或通讯组的) 搜索框中键入至少三个字符。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="dfdcb-122">选择要添加为非保管人数据源的邮箱，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="dfdcb-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dfdcb-123">可以使用"SharePoint"Exchange"部分，将与"团队"或"Yammer组关联的网站和邮箱添加为非安全数据源。 </span><span class="sxs-lookup"><span data-stu-id="dfdcb-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="dfdcb-124">必须单独添加与团队或组关联的邮箱Yammer网站。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="dfdcb-125">添加非安全数据源后，您可以选择是否保留这些位置。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="dfdcb-126">选中或取消 **选中数据源旁边的** "保留"复选框以将其保留。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="dfdcb-127">单击 **"** 新建非安全数据位置"飞出页底部的"添加"，将数据源添加到案例。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="dfdcb-128">您添加的每个非安全数据源都列在"数据源 **"页上** 。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="dfdcb-129">非当前数据源由"源类型"列中 **的"数据位置** " **值** 标识。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   !["数据源"选项卡上的非主要数据源](../media/NonCustodialDataSources2.png)

<span data-ttu-id="dfdcb-131">向案例添加非安全数据源后，将创建名为 *"重新* 索引非索引数据"的作业，并显示在案例的"作业"选项卡上。 </span><span class="sxs-lookup"><span data-stu-id="dfdcb-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="dfdcb-132">创建作业后，将启动高级索引过程，并重新编制数据源索引。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="dfdcb-133">管理非托管数据源的保留</span><span class="sxs-lookup"><span data-stu-id="dfdcb-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="dfdcb-134">将非托管数据源放在保留状态后，将自动创建包含案例的非托管数据源的保留策略。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="dfdcb-135">当您将其他非安全数据源放在保留状态时，它们将被添加到此保留策略。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="dfdcb-136">打开Advanced eDiscovery案例并选择"保留 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="dfdcb-137">单击 **NCDSHold- \<GUID\>**，其中 GUID 值对大小写是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="dfdcb-138">该飞出页显示有关非保留数据源的信息和统计信息。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![非报表数据源保留的飞出页显示统计信息](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="dfdcb-140">单击 **"编辑** 保留"以查看置于保留状态的非托管数据源并执行以下管理任务：</span><span class="sxs-lookup"><span data-stu-id="dfdcb-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="dfdcb-141">在 **"位置"** 页上，可以通过从保留项中删除非托管数据源来释放该数据源。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="dfdcb-142">释放数据源不会从案例中删除非安全数据源。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="dfdcb-143">它仅删除对数据源的保留。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="dfdcb-144">在 **"查询** "页上，可以编辑保留以创建应用于所有非查询数据源的基于查询的保留。</span><span class="sxs-lookup"><span data-stu-id="dfdcb-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
