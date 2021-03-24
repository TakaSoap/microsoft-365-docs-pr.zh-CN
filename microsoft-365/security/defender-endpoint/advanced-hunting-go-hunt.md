---
title: 通过搜寻获取有关实体的信息
description: 了解如何使用 go hunt 工具快速查询有关使用高级搜寻的实体或事件的信息。
keywords: 高级搜寻， 事件， 透视， 实体， 搜寻， 相关事件， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-maave
author: martyav
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fe3c204fe49f008cf5d9dd18b5066fa91dc6196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056381"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="0ba96-104">使用 go hunt 快速搜寻实体或事件信息</span><span class="sxs-lookup"><span data-stu-id="0ba96-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ba96-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0ba96-105">**Applies to:**</span></span>
- [<span data-ttu-id="0ba96-106">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ba96-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="0ba96-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="0ba96-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0ba96-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0ba96-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


<span data-ttu-id="0ba96-109">借助 *智能寻* 线操作，可以使用强大的基于查询的高级搜寻功能快速调查事件 [和各种实体](advanced-hunting-overview.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="0ba96-109">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="0ba96-110">此操作将自动运行高级搜寻查询，以查找有关所选事件或实体的信息。</span><span class="sxs-lookup"><span data-stu-id="0ba96-110">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="0ba96-111">每当 *显示事件* 或实体详细信息时，安全中心的各个部分都提供寻线操作。</span><span class="sxs-lookup"><span data-stu-id="0ba96-111">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="0ba96-112">例如，你可以从以下 *部分使用去* 寻线：</span><span class="sxs-lookup"><span data-stu-id="0ba96-112">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="0ba96-113">在 [事件页面中](investigate-incidents.md)，你可以查看有关用户、设备和与事件关联的许多其他实体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ba96-113">In the [incident page](investigate-incidents.md), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="0ba96-114">选择实体时，您将获得其他信息以及可针对该实体执行的各种操作。</span><span class="sxs-lookup"><span data-stu-id="0ba96-114">When you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="0ba96-115">在下面的示例中，选择设备，显示有关设备的详细信息，以及用于搜寻有关设备的详细信息的选项。</span><span class="sxs-lookup"><span data-stu-id="0ba96-115">In the example below, a device is selected, showing details about the device as well the option to hunt for more information about the device.</span></span>

    ![显示具有"开始"寻线选项的设备详细信息的图像](./images/go-hunt-device.png)

- <span data-ttu-id="0ba96-117">在事件页面中，您还可以访问"证据"选项卡下的实体列表。选择其中一个实体可提供快速搜寻有关该实体的信息的选项。</span><span class="sxs-lookup"><span data-stu-id="0ba96-117">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![显示"证据"选项卡中带"去寻线"选项的选定 URL 的图像](./images/go-hunt-evidence-url.png)

- <span data-ttu-id="0ba96-119">查看设备的时间线时，可以选择时间线中的事件以查看有关该事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0ba96-119">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="0ba96-120">选择事件后，可选择在高级搜寻中搜寻其他相关事件。</span><span class="sxs-lookup"><span data-stu-id="0ba96-120">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![显示事件详细信息（使用"开始"寻线选项）的图像](./images/go-hunt-event.png)

<span data-ttu-id="0ba96-122">选择 **"搜寻** " **或** "搜寻"进行相关事件将传递不同的查询，具体取决于你选择了实体还是事件。</span><span class="sxs-lookup"><span data-stu-id="0ba96-122">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="0ba96-123">查询实体信息</span><span class="sxs-lookup"><span data-stu-id="0ba96-123">Query for entity information</span></span>

<span data-ttu-id="0ba96-124">当 *使用"搜寻* "查询有关用户、设备或任何任何类型的实体的信息时，该查询将检查所有相关架构表，以检查是否有涉及该实体的任何事件。</span><span class="sxs-lookup"><span data-stu-id="0ba96-124">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="0ba96-125">若要使结果可管理，查询的范围为与过去 30 天内最早活动（涉及实体且与事件关联）的时间段。</span><span class="sxs-lookup"><span data-stu-id="0ba96-125">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="0ba96-126">下面是设备的去寻线查询示例：</span><span class="sxs-lookup"><span data-stu-id="0ba96-126">Here is an example of the go hunt query for a device:</span></span>

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

### <a name="supported-entity-types"></a><span data-ttu-id="0ba96-127">支持的实体类型</span><span class="sxs-lookup"><span data-stu-id="0ba96-127">Supported entity types</span></span>

<span data-ttu-id="0ba96-128">在选择 *以下实体类型* 之一后，可以使用 go hunt：</span><span class="sxs-lookup"><span data-stu-id="0ba96-128">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="0ba96-129">文件</span><span class="sxs-lookup"><span data-stu-id="0ba96-129">Files</span></span>
- <span data-ttu-id="0ba96-130">用户</span><span class="sxs-lookup"><span data-stu-id="0ba96-130">Users</span></span>
- <span data-ttu-id="0ba96-131">设备</span><span class="sxs-lookup"><span data-stu-id="0ba96-131">Devices</span></span>
- <span data-ttu-id="0ba96-132">IP 地址</span><span class="sxs-lookup"><span data-stu-id="0ba96-132">IP addresses</span></span>
- <span data-ttu-id="0ba96-133">URL</span><span class="sxs-lookup"><span data-stu-id="0ba96-133">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="0ba96-134">查询事件信息</span><span class="sxs-lookup"><span data-stu-id="0ba96-134">Query for event information</span></span>

<span data-ttu-id="0ba96-135">当 *使用寻线* 查询有关时间线事件的信息时，该查询会检查所有相关架构表，以检查选定事件的时间周围的其他事件。</span><span class="sxs-lookup"><span data-stu-id="0ba96-135">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="0ba96-136">例如，以下查询列出在同一设备上同一时间段期间发生的各种架构表中的事件：</span><span class="sxs-lookup"><span data-stu-id="0ba96-136">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected RegistryValueSet event
let selectedEventTimestamp = datetime(2020-10-06T21:40:25.3466868Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "a305b52049c4658ec63ae8b55becfe5954c654a4"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="0ba96-137">调整查询</span><span class="sxs-lookup"><span data-stu-id="0ba96-137">Adjust the query</span></span>

<span data-ttu-id="0ba96-138">在了解查询 [语言之后](advanced-hunting-query-language.md)，可以根据你的偏好调整查询。</span><span class="sxs-lookup"><span data-stu-id="0ba96-138">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="0ba96-139">例如，您可以调整此行，这确定时间窗口的大小：</span><span class="sxs-lookup"><span data-stu-id="0ba96-139">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="0ba96-140">除了修改查询以获得更多相关结果之外，您还可以：</span><span class="sxs-lookup"><span data-stu-id="0ba96-140">In addition to modifying the query to get more relevant results, you can also:</span></span>

- [<span data-ttu-id="0ba96-141">以图表查看结果</span><span class="sxs-lookup"><span data-stu-id="0ba96-141">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="0ba96-142">创建自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="0ba96-142">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="0ba96-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="0ba96-143">Related topics</span></span>

- [<span data-ttu-id="0ba96-144">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="0ba96-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0ba96-145">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="0ba96-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0ba96-146">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="0ba96-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="0ba96-147">自定义检测规则</span><span class="sxs-lookup"><span data-stu-id="0ba96-147">Custom detection rules</span></span>](custom-detection-rules.md)
