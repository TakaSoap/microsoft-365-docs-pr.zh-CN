---
title: 通过搜寻获取有关实体的信息
description: 了解如何使用上线搜寻工具快速查询有关使用高级搜寻的实体或事件的信息。
keywords: 高级搜寻， 事件， 透视， 实体， 搜寻， 相关事件， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952652"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="d14f8-104">使用 go hunt 快速搜寻实体或事件信息</span><span class="sxs-lookup"><span data-stu-id="d14f8-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d14f8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d14f8-105">**Applies to:**</span></span>
- <span data-ttu-id="d14f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d14f8-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d14f8-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d14f8-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d14f8-108">借助 *智能寻* 线操作，可以使用强大的基于查询的高级搜寻功能快速调查事件 [和各种实体](advanced-hunting-overview.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="d14f8-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="d14f8-109">此操作将自动运行高级搜寻查询，以查找有关所选事件或实体的信息。</span><span class="sxs-lookup"><span data-stu-id="d14f8-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="d14f8-110">每当 *显示事件* 或实体详细信息时，安全中心的各个部分都提供寻线操作。</span><span class="sxs-lookup"><span data-stu-id="d14f8-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="d14f8-111">例如，你可以从以下 *部分使用去* 寻线：</span><span class="sxs-lookup"><span data-stu-id="d14f8-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="d14f8-112">在 [事件页面中](investigate-incidents.md#summary)，你可以查看有关用户、设备和与事件关联的许多其他实体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d14f8-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="d14f8-113">选择实体时，您将获得其他信息以及可针对该实体执行的各种操作。</span><span class="sxs-lookup"><span data-stu-id="d14f8-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="d14f8-114">在下面的示例中，选择一个邮箱，其中显示有关邮箱的详细信息，以及用于搜寻有关邮箱的详细信息的选项。</span><span class="sxs-lookup"><span data-stu-id="d14f8-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![显示具有"开始"寻线选项的邮箱详细信息的图像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="d14f8-116">在事件页面中，您还可以访问"证据"选项卡下的实体列表。选择其中一个实体可提供快速搜寻有关该实体的信息的选项。</span><span class="sxs-lookup"><span data-stu-id="d14f8-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![显示"证据"选项卡中带"去寻线"选项的选定文件的图像](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="d14f8-118">查看设备的时间线时，可以选择时间线中的事件以查看有关该事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="d14f8-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="d14f8-119">选择事件后，可选择在高级搜寻中搜寻其他相关事件。</span><span class="sxs-lookup"><span data-stu-id="d14f8-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![显示事件详细信息（使用"开始"寻线选项）的图像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="d14f8-121">选择 **"搜寻** " **或** "搜寻"进行相关事件将传递不同的查询，具体取决于你选择了实体还是事件。</span><span class="sxs-lookup"><span data-stu-id="d14f8-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="d14f8-122">查询实体信息</span><span class="sxs-lookup"><span data-stu-id="d14f8-122">Query for entity information</span></span>
<span data-ttu-id="d14f8-123">当 *使用"搜寻* "查询有关用户、设备或任何任何类型的实体的信息时，该查询将检查所有相关架构表，以检查是否有涉及该实体的任何事件。</span><span class="sxs-lookup"><span data-stu-id="d14f8-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="d14f8-124">若要使结果可管理，查询的范围为与过去 30 天内最早活动（涉及实体且与事件关联）的时间段。</span><span class="sxs-lookup"><span data-stu-id="d14f8-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="d14f8-125">下面是设备的去寻线查询示例：</span><span class="sxs-lookup"><span data-stu-id="d14f8-125">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="d14f8-126">支持的实体类型</span><span class="sxs-lookup"><span data-stu-id="d14f8-126">Supported entity types</span></span>
<span data-ttu-id="d14f8-127">在选择 *以下实体类型* 之一后，可以使用 go hunt：</span><span class="sxs-lookup"><span data-stu-id="d14f8-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="d14f8-128">文件</span><span class="sxs-lookup"><span data-stu-id="d14f8-128">Files</span></span>
- <span data-ttu-id="d14f8-129">电子邮件</span><span class="sxs-lookup"><span data-stu-id="d14f8-129">Emails</span></span>
- <span data-ttu-id="d14f8-130">电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="d14f8-130">Email clusters</span></span>
- <span data-ttu-id="d14f8-131">邮箱</span><span class="sxs-lookup"><span data-stu-id="d14f8-131">Mailboxes</span></span>
- <span data-ttu-id="d14f8-132">用户</span><span class="sxs-lookup"><span data-stu-id="d14f8-132">Users</span></span>
- <span data-ttu-id="d14f8-133">设备</span><span class="sxs-lookup"><span data-stu-id="d14f8-133">Devices</span></span>
- <span data-ttu-id="d14f8-134">IP 地址</span><span class="sxs-lookup"><span data-stu-id="d14f8-134">IP addresses</span></span>
- <span data-ttu-id="d14f8-135">URL</span><span class="sxs-lookup"><span data-stu-id="d14f8-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="d14f8-136">查询事件信息</span><span class="sxs-lookup"><span data-stu-id="d14f8-136">Query for event information</span></span>
<span data-ttu-id="d14f8-137">当 *使用寻线* 查询有关时间线事件的信息时，该查询会检查所有相关架构表，以检查选定事件的时间周围的其他事件。</span><span class="sxs-lookup"><span data-stu-id="d14f8-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="d14f8-138">例如，以下查询列出在同一设备上同一时间段期间发生的各种架构表中的事件：</span><span class="sxs-lookup"><span data-stu-id="d14f8-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="d14f8-139">调整查询</span><span class="sxs-lookup"><span data-stu-id="d14f8-139">Adjust the query</span></span>
<span data-ttu-id="d14f8-140">在了解查询 [语言之后](advanced-hunting-query-language.md)，可以根据你的偏好调整查询。</span><span class="sxs-lookup"><span data-stu-id="d14f8-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="d14f8-141">例如，您可以调整此行，这确定时间窗口的大小：</span><span class="sxs-lookup"><span data-stu-id="d14f8-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="d14f8-142">除了修改查询以获得更多相关结果之外，您还可以：</span><span class="sxs-lookup"><span data-stu-id="d14f8-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="d14f8-143">以图表查看结果</span><span class="sxs-lookup"><span data-stu-id="d14f8-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="d14f8-144">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="d14f8-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="d14f8-145">本文中的某些表在 Microsoft Defender for Endpoint 中可能不可用。</span><span class="sxs-lookup"><span data-stu-id="d14f8-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="d14f8-146">[打开 Microsoft 365 Defender](m365d-enable.md)以使用更多数据源搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="d14f8-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="d14f8-147">你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤，将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到 Microsoft 365 [Defender。](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="d14f8-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d14f8-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="d14f8-148">Related topics</span></span>
- [<span data-ttu-id="d14f8-149">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d14f8-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d14f8-150">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d14f8-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d14f8-151">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="d14f8-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d14f8-152">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="d14f8-152">Custom detection rules</span></span>](custom-detection-rules.md)
