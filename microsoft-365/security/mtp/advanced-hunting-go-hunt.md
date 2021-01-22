---
title: 使用搜寻功能获取有关实体的相关信息
description: 了解如何使用搜寻工具快速查询有关使用高级搜寻的实体或事件的相关信息。
keywords: 高级搜寻， 事件， 透视， 实体， 搜寻， 相关事件， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， Microsoft 365， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929498"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>使用 Go hunt 快速搜寻实体或事件信息

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

借助 *智能寻线* 操作，可以使用基于查询的高级智能寻线功能快速调查事件 [和各种实体](advanced-hunting-overview.md) 类型。 此操作将自动运行高级搜寻查询，以查找有关所选事件或实体的相关信息。

每当 *显示* 事件或实体详细信息时，安全中心的各个部分都提供搜寻操作。 例如，你可以从以下 *部分使用寻* 线：

- 在 [事件页面中](investigate-incidents.md#incident-overview)，你可以查看有关用户、设备和与事件关联的许多其他实体的详细信息。 选择实体时，您将获得其他信息以及可针对该实体执行的各种操作。 在下面的示例中，选择一个邮箱，显示有关邮箱的详细信息，以及用于搜寻有关邮箱的详细信息的选项。

    ![显示具有"寻线"选项的邮箱详细信息的图像](../../media/mtp-ah/go-hunt-email.png)

- 在事件页面中，您还可以访问"证据"选项卡下的实体列表。选择其中一个实体可提供快速搜寻有关该实体的信息的选项。

    ![显示"证据"选项卡中具有"去寻线"选项的选定文件的图像](../../media/mtp-ah/go-hunt-evidence-file.png)


- 查看设备的时间线时，可以选择时间线中的事件以查看有关该事件的其他信息。 选择事件后，可以选择在高级搜寻中搜寻其他相关事件。

    ![显示使用"开始"寻线选项的事件详细信息的图像](../../media/mtp-ah/go-hunt-event.png)

选择 **"搜寻** " **或** "搜寻"进行相关事件将传递不同的查询，具体取决于你选择了实体还是事件。

## <a name="query-for-entity-information"></a>查询实体信息
当 *使用寻线* 查询有关用户、设备或任何类型的实体的信息时，该查询将检查所有相关架构表，以检查是否有涉及该实体的任何事件。 若要使结果易于管理，查询的范围为与过去 30 天内的最早活动（涉及实体且与事件关联）的同一时间段。

下面是设备的寻线查询示例：

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
选择以下 *任一实体* 类型后，即可使用寻线：

- 文件
- 电子邮件
- 电子邮件群集
- 邮箱
- 用户
- 设备
- IP 地址
- URL

## <a name="query-for-event-information"></a>查询事件信息
当 *使用寻线* 查询有关日程表事件的信息时，该查询将检查所有相关架构表，以检查选定事件的时间周围的其他事件。 例如，以下查询列出了在同一设备上同一时间段发生的各种架构表中的事件：

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
对查询语言 [有一些了解](advanced-hunting-query-language.md)后，就可以根据你的偏好调整查询。 例如，您可以调整此行，这确定时间窗口的大小：

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

除了修改查询以获得更多相关结果之外，您还可以：
- [以图表查看结果](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [创建自定义检测规则](custom-detection-rules.md)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [自定义检测规则](custom-detection-rules.md)
