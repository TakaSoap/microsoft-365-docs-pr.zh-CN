---
title: 将非 custodial 数据源添加到高级电子数据展示事例
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
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以将非 custodial 数据源添加到高级电子数据展示事例，并在数据源中放置保留。 未 custodial 的数据源将被重新编制索引，因此被视为部分索引的所有内容都将被重新处理，以使其完全和快速地可搜索。
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695495"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="442d0-104">将非 custodial 数据源添加到高级电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="442d0-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="442d0-105">在高级电子数据展示事例中，它并不总是满足将 Microsoft 365 数据源与事例中的管理员相关联的需求。</span><span class="sxs-lookup"><span data-stu-id="442d0-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="442d0-106">但您可能仍需要将该数据与大小写相关联，以便对其进行搜索、将其添加到审阅集并进行查看。</span><span class="sxs-lookup"><span data-stu-id="442d0-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="442d0-107">称为 "*非 custodial" 数据源*的新功能使您可以向事例添加数据，而无需将数据与保管人进行关联。</span><span class="sxs-lookup"><span data-stu-id="442d0-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="442d0-108">它还将相同的高级电子数据展示功能应用于可用于与保管人关联的数据的非 custodial 数据。</span><span class="sxs-lookup"><span data-stu-id="442d0-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="442d0-109">可应用于非 custodial 数据的两个最有用的功能是将其置于保留状态，并使用[高级索引](indexing-custodian-data.md)进行处理。</span><span class="sxs-lookup"><span data-stu-id="442d0-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="442d0-110">添加非 custodial 数据源</span><span class="sxs-lookup"><span data-stu-id="442d0-110">Add a non-custodial data source</span></span>

<span data-ttu-id="442d0-111">按照以下步骤在高级电子数据展示事例中添加和管理非 custodial 数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="442d0-112">在**高级电子数据展示**主页上，单击要向其添加数据的事例。</span><span class="sxs-lookup"><span data-stu-id="442d0-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="442d0-113">在 "**源**" 页上，单击 "**数据位置**" 选项卡，然后单击 "**添加数据位置**"。</span><span class="sxs-lookup"><span data-stu-id="442d0-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="442d0-114">单击 "**添加数据位置**"，然后选择要添加到该事例的数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="442d0-115">您可以添加多个邮箱和网站。</span><span class="sxs-lookup"><span data-stu-id="442d0-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="442d0-116">在向导的 "**选择位置**" 页上，将邮箱或网站（或两者）添加为事例中的非 custodial 数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="442d0-117">添加数据源后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="442d0-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="442d0-118">在 "**就地保留**" 页上，选择或取消选择关联的复选框，以选择要置于保留状态的数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="442d0-119">验证保留选择，然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="442d0-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="442d0-120">您添加的每个非 custodial 数据源都列在 "**数据源**" 页上。</span><span class="sxs-lookup"><span data-stu-id="442d0-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="442d0-121">此外，将创建一个名为 "*重新编制索引*" 的作业，并显示在该案例的 "**作业**" 选项卡上的 "custodial" 数据。</span><span class="sxs-lookup"><span data-stu-id="442d0-121">Also, a job named *Re-indexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="442d0-122">在创建作业之后，启动中的高级索引过程，并对数据源重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="442d0-122">After the job is created, the Advanced indexing process in initiated and the data sources are re-indexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="442d0-123">管理对非 custodial 数据源的保留</span><span class="sxs-lookup"><span data-stu-id="442d0-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="442d0-124">在非 custodial 数据源上放置保留后，将自动创建包含该事例的所有非 custodial 数据源的保留策略。</span><span class="sxs-lookup"><span data-stu-id="442d0-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="442d0-125">将其他非 custodial 数据源置于保留状态时，它们将被添加到此保留策略中。</span><span class="sxs-lookup"><span data-stu-id="442d0-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="442d0-126">在该事例的**主页**上，单击 "**保留**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="442d0-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="442d0-127">在 "**保留**" 页上，单击 " \*\*NCDSHold- \<GUID\> \*\*"，其中 GUID 值对事例是唯一的。</span><span class="sxs-lookup"><span data-stu-id="442d0-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="442d0-128">在弹出页面上，单击 "**编辑保留**" 以查看置于保留状态的所有非 custodial 数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="442d0-129">您可以在非 custodial 数据源上执行以下管理任务：</span><span class="sxs-lookup"><span data-stu-id="442d0-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="442d0-130">您可以编辑保留以创建一个应用于该情况下的所有非 custodial 数据源的基于查询的保留。</span><span class="sxs-lookup"><span data-stu-id="442d0-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="442d0-131">您可以从保留中释放非 custodial 数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="442d0-132">释放数据源不会从事例中删除非 custodial 数据源。</span><span class="sxs-lookup"><span data-stu-id="442d0-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="442d0-133">它仅删除在数据源上放置的保留。</span><span class="sxs-lookup"><span data-stu-id="442d0-133">It only removes the hold that was placed on the data source.</span></span>
