---
title: 使用设备控制保护组织的数据
description: 通过设备控制报告监视组织的数据安全性。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 952363dfa689ea20e1ca1fcd97da4a79cfa66062
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212990"
---
# <a name="protect-your-organizations-data-with-device-control"></a>使用设备控制保护组织的数据

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint 设备控制通过监视和控制组织中设备的媒体使用（如使用可移动存储设备和 USB 驱动器）防止数据丢失。

借助设备控件报告，可以查看与媒体使用情况相关的事件，例如：

- **审核事件：** 显示连接外部媒体时发生的审核事件数。
- **策略事件：** 显示触发设备控制策略时发生的策略事件数。

> [!NOTE]
> 默认情况下，会为载入到 Microsoft Defender for Endpoint 的设备启用跟踪媒体使用情况的审核事件。

## <a name="understanding-the-audit-events"></a>了解审核事件

审核事件包括：

- **USB 驱动器装入和卸载：** 装载或卸载 USB 驱动器时生成的审核事件。
- **PnP：** 即插即用审核事件在连接可移动存储、打印机或蓝牙时生成。

## <a name="monitor-device-control-security"></a>监视设备控制安全性

Microsoft Defender for Endpoint 中的设备控制使安全管理员能够使用工具通过报告跟踪其组织的设备控制安全性。 你可以访问报告设备保护Microsoft 365安全中心中的设备>**报告**。

"报告"仪表板上的设备保护卡片显示过去 180 天内媒体类型生成的审核事件数。

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](images/devicecontrolcard.png)

" **查看详细信息** "按钮在设备控件报告页中显示 **更多媒体使用情况** 数据。

该页面提供一个仪表板，其中包含每种类型的聚合事件数和一个事件列表。 管理员可以根据时间范围、媒体类名称和设备 ID 进行筛选。

> [!div class="mx-imgBorder"]
> ![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)

选择事件时，将显示一个显示详细信息的飞出图：

- **一般详细信息：** 日期、操作模式和此事件的策略。
- **媒体信息：** 媒体信息包括媒体名称、类名称、类 GUID、设备 ID、供应商 ID、卷、序列号和总线类型。
- **位置详细信息：** 设备名称和 MDATP 设备 ID。

> [!div class="mx-imgBorder"]
> ![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)

若要查看组织中此媒体实时活动，请选择"打开高级搜寻 **"** 按钮。 这包括嵌入的预定义查询。

> [!div class="mx-imgBorder"]
> ![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)

To see the security of the device， select the **Open device page** button on the flyout. 此按钮将打开设备实体页面。

> [!div class="mx-imgBorder"]
> ![DeviceEntityPage](images/Devicesecuritypage.png)

## <a name="reporting-delays"></a>报告延迟

设备控制报告可以有 12 小时延迟，从媒体连接发生到事件反映在卡片或域列表中。