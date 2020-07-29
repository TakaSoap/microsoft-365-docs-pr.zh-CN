---
title: 获取有关使用 go 搜索的实体的相关信息
description: 了解如何使用 "开始查找" 工具快速查询有关使用高级搜索的实体或事件的相关信息。
keywords: 高级搜索、事件、数据透视、实体、搜索、相关事件、威胁搜寻、网络威胁搜寻、搜索、查询、遥测、Microsoft 365、Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b9afecb3d0efce93ae5d5725bba71d8d9719d17f
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430407"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="414f6-104">使用 go 智能寻线快速查找实体或事件信息</span><span class="sxs-lookup"><span data-stu-id="414f6-104">Quickly hunt for entity or event information with go hunt</span></span>

<span data-ttu-id="414f6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="414f6-105">**Applies to:**</span></span>
- <span data-ttu-id="414f6-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="414f6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="414f6-107">通过 "*转智能*" 操作，您可以使用基于查询的强大[高级搜寻](advanced-hunting-overview.md)功能快速调查事件和各种实体类型。</span><span class="sxs-lookup"><span data-stu-id="414f6-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="414f6-108">此操作将自动运行高级的搜索查询，以查找有关所选事件或实体的相关信息。</span><span class="sxs-lookup"><span data-stu-id="414f6-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="414f6-109">无论何时显示事件或实体详细信息，都会在安全中心的各个部分中提供 "*转智能*" 操作。</span><span class="sxs-lookup"><span data-stu-id="414f6-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="414f6-110">例如，可以使用以下部分中的 "*转智能寻*线"：</span><span class="sxs-lookup"><span data-stu-id="414f6-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="414f6-111">在 "[事件" 页](investigate-incidents.md#incident-overview)中，您可以查看有关用户、设备以及与事件相关联的许多其他实体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="414f6-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="414f6-112">在您选择实体时，将获取其他信息，以及您可以对该 entitity 执行的各种操作。</span><span class="sxs-lookup"><span data-stu-id="414f6-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="414f6-113">在下面的示例中，选择了一个邮箱，显示有关邮箱的详细信息，以及用于查找有关邮箱的详细信息的选项。</span><span class="sxs-lookup"><span data-stu-id="414f6-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![显示具有 "转智能" 选项的邮箱详细信息的图像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="414f6-115">在 "事件" 页中，您还可以访问 "证据" 选项卡下的实体列表。选择其中一个实体可提供快速查找有关该实体的信息的选项。</span><span class="sxs-lookup"><span data-stu-id="414f6-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![显示 "证据" 选项卡中带有 "转智能" 选项的选定文件的图像](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="414f6-117">在查看设备的日程表时，您可以在时间轴中选择事件，以查看有关该事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="414f6-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="414f6-118">一旦选择了事件，您就可以选择在高级搜寻中查找其他相关事件。</span><span class="sxs-lookup"><span data-stu-id="414f6-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![显示使用 "转智能" 选项显示事件详细信息的图像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="414f6-120">选择 "**对相关事件的\*\*\*\*查找**或查寻" 将传递不同的查询，具体取决于您是否选择了实体或事件。</span><span class="sxs-lookup"><span data-stu-id="414f6-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="414f6-121">查询实体信息</span><span class="sxs-lookup"><span data-stu-id="414f6-121">Query for entity information</span></span>
<span data-ttu-id="414f6-122">使用 "*查寻*" 查询有关用户、设备或任何其他类型的实体的信息时，查询将检查涉及该实体的任何事件的所有相关架构表。</span><span class="sxs-lookup"><span data-stu-id="414f6-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="414f6-123">若要使结果保持可管理性，查询的范围为与过去30天中涉及实体并与事件相关联的最早活动的时间段相同。</span><span class="sxs-lookup"><span data-stu-id="414f6-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="414f6-124">下面的示例展示了设备的 "转智能" 查询：</span><span class="sxs-lookup"><span data-stu-id="414f6-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="414f6-125">支持的实体类型</span><span class="sxs-lookup"><span data-stu-id="414f6-125">Supported entity types</span></span>
<span data-ttu-id="414f6-126">选择以下任何实体类型后，可以使用 "*转到浏览*"：</span><span class="sxs-lookup"><span data-stu-id="414f6-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="414f6-127">文件</span><span class="sxs-lookup"><span data-stu-id="414f6-127">Files</span></span>
- <span data-ttu-id="414f6-128">电子邮件</span><span class="sxs-lookup"><span data-stu-id="414f6-128">Emails</span></span>
- <span data-ttu-id="414f6-129">电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="414f6-129">Email clusters</span></span>
- <span data-ttu-id="414f6-130">邮箱</span><span class="sxs-lookup"><span data-stu-id="414f6-130">Mailboxes</span></span>
- <span data-ttu-id="414f6-131">用户</span><span class="sxs-lookup"><span data-stu-id="414f6-131">Users</span></span>
- <span data-ttu-id="414f6-132">设备</span><span class="sxs-lookup"><span data-stu-id="414f6-132">Devices</span></span>
- <span data-ttu-id="414f6-133">IP 地址</span><span class="sxs-lookup"><span data-stu-id="414f6-133">IP addresses</span></span>
- <span data-ttu-id="414f6-134">URL</span><span class="sxs-lookup"><span data-stu-id="414f6-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="414f6-135">事件信息查询</span><span class="sxs-lookup"><span data-stu-id="414f6-135">Query for event information</span></span>
<span data-ttu-id="414f6-136">使用 "*查寻*" 查询有关日程表事件的信息时，查询将检查所选事件的时间周围的其他事件的所有相关架构表。</span><span class="sxs-lookup"><span data-stu-id="414f6-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="414f6-137">例如，下面的查询列出了在同一设备上的同一时间段内出现的各种架构表中的事件：</span><span class="sxs-lookup"><span data-stu-id="414f6-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="414f6-138">调整查询</span><span class="sxs-lookup"><span data-stu-id="414f6-138">Adjust the query</span></span>
<span data-ttu-id="414f6-139">在了解[查询语言](advanced-hunting-query-language.md)的情况下，可以根据您的喜好调整查询。</span><span class="sxs-lookup"><span data-stu-id="414f6-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="414f6-140">例如，您可以调整此行，以确定时间窗口的大小：</span><span class="sxs-lookup"><span data-stu-id="414f6-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="414f6-141">除了修改查询以获得更多相关结果之外，您还可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="414f6-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="414f6-142">以图表形式查看结果</span><span class="sxs-lookup"><span data-stu-id="414f6-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="414f6-143">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="414f6-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="414f6-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="414f6-144">Related topics</span></span>
- [<span data-ttu-id="414f6-145">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="414f6-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="414f6-146">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="414f6-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="414f6-147">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="414f6-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="414f6-148">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="414f6-148">Custom detection rules</span></span>](custom-detection-rules.md)