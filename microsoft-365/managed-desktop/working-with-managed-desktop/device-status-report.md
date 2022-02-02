---
title: 设备状态报告
description: 说明设备状态
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 14c83d007d2506e0e85c156f4d738f78f91fad75
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321023"
---
# <a name="device-status-report"></a>设备状态报告

此报告聚合所有注册设备的状态，以显示你使用 Microsoft 托管桌面 服务。

我们将根据设备过去 28 天内的活动以及我们保持设备更新的能力对设备进行分类。

若要通过更新Windows更新，设备必须：

- 连接到 Internet。
- 不休眠。
- 至少不要暂停六个小时，其中两个小时必须连续。

尽管可能会更新不满足这些要求的设备。 满足要求的设备具有最高更新可能性。

:::image type="content" source="../../media/mmd-device-status.png" alt-text="显示左上方设备活动状态的 Donut 图的报告、右上方的视图筛选器以及用于生成报告的按钮，以及底部的详细信息表":::

## <a name="device-status-labels"></a>设备状态标签

我们将使用下列标签报告设备状态：

| 设备状态标签 | 说明 |
| ------ | ------ |
| 为用户准备就绪 | 已在服务中成功注册并准备向用户提供的设备。|
| 活动 | 使用的设备。 <ul><li>他们满足最新的安全更新 (六小时两) 活动条件。</li> <li>在过去五天内，他们Microsoft Intune至少签入了一次。</li></ul> |
| 已同步 | 过去 28 天内使用且已使用 Intune 签入的设备。
| 不同步 | 使用的设备，但过去 28 天内未使用 Intune 签入。 |
| 其他 | 标签聚合了通常发生在设备注册期间发生的多个错误状态。 有关详细信息，请参阅 [设备注册疑难解答](../get-started/register-devices-self.md#troubleshooting-device-registration)。 |
