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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d1ec22febe0c0072a4eed2a9b8fece3687762d7
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754279"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>使用 go hunt 快速搜寻实体或事件信息

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

借助 *智能寻线* 操作，可以使用强大的基于查询的高级搜寻功能快速调查事件 [和各种实体](advanced-hunting-overview.md) 类型。 此操作将自动运行高级搜寻查询，以查找有关所选事件或实体的信息。

The *go hunt* action is available in various sections of the Defender for Cloud. 显示事件或实体详细信息后，此操作可供查看。 例如，您可以使用以下 *部分中的"* 去寻线"选项：

- 在 [事件页面中](investigate-incidents.md#summary)，你可以查看有关用户、设备和与事件关联的许多其他实体的详细信息。 选择实体时，您将获得其他信息以及可针对该实体执行的各种操作。 在下面的示例中，选择了一个邮箱，其中显示有关邮箱的详细信息以及用于搜寻邮箱的详细信息的选项。

    :::image type="content" source="../../media/go-hunt-1-incident.png" alt-text="The Mailboxes page with the Go hunt option in the Microsoft 365 Defender portal" lightbox="../../media/go-hunt-1-incident.png":::

- 在事件页面中，您还可以访问"证据"选项卡下 **的实体列表。** 选择其中一个实体可提供快速搜寻有关该实体的信息的选项。

    :::image type="content" source="../../media/go-hunt-2-entity.png" alt-text="Microsoft 365 Defender 门户中&quot;事件&quot;页中用于一条证据的&quot;Microsoft 365 Defender选项" lightbox="../../media/go-hunt-2-entity.png":::


- 查看设备的时间线时，可以选择时间线中的事件以查看有关该事件的其他信息。 选择事件后，可选择在高级搜寻中搜寻其他相关事件。

    :::image type="content" source="../../media/go-hunt-3-event.png" alt-text="门户中&quot;日程表&quot;选项卡中事件页面上的&quot;搜寻相关Microsoft 365 Defender选项" lightbox="../../media/go-hunt-3-event.png":::

选择 **"搜寻****"或**"搜寻"进行相关事件将传递不同的查询，具体取决于你选择了实体还是事件。

## <a name="query-for-entity-information"></a>查询实体信息
您可以使用 *go hunt* 查询有关用户、设备或任何任何类型的实体的信息;查询将检查所有相关架构表，以检查是否有涉及该实体的事件返回信息。 若要使结果易于管理，查询为：
- 范围为与过去 30 天内涉及实体的最早活动相同的时间段
- 与事件关联。

下面是设备的去寻线查询示例：

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
### <a name="supported-entity-types"></a>支持的实体类型
选择以下实体 *类型* 之一后，可以使用"去寻线"选项：

- 文件
- 电子邮件
- 电子邮件群集
- 邮箱
- 用户
- 设备
- IP 地址
- URL

## <a name="query-for-event-information"></a>查询事件信息
当 *使用寻线* 查询有关时间线事件的信息时，该查询会检查所有相关架构表，以检查选定事件的时间周围的其他事件。 例如，以下查询列出在同一设备上同一时间段期间发生的各种架构表中的事件：

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

## <a name="adjust-the-query"></a>调整查询
由于对查询语言 [有一定的](advanced-hunting-query-language.md)了解，因此可以根据你的偏好调整查询。 例如，您可以调整此行，这确定时间窗口的大小：

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

除了修改查询以获得更多相关结果之外，您还可以：
- [以图表查看结果](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [创建自定义检测规则](custom-detection-rules.md)

>[!NOTE]
>本文中的某些表在 Microsoft Defender for Endpoint 中可能不可用。 [打开"Microsoft 365 Defender](m365d-enable.md)，以使用更多数据源搜寻威胁。 你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤Microsoft 365 Defender Microsoft Defender for Endpoint 中的步骤将高级搜寻[工作流从 Microsoft Defender for Endpoint 移动到其他位置](advanced-hunting-migrate-from-mde.md)。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [自定义检测规则](custom-detection-rules.md)
