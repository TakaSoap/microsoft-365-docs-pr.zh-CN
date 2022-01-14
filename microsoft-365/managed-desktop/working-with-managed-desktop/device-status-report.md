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
ms.openlocfilehash: 4071d3a76430dd34776b2d4df3eae2b32e350a11
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034841"
---
# <a name="device-status-report"></a>设备状态报告

此报告聚合所有注册设备的状态，以显示你使用 Microsoft 托管桌面 服务。 我们根据设备过去 28 天内的活动以及我们保持设备更新的能力对设备进行分类。 若要通过 Windows Update 尽快进行更新，设备必须连接到 Internet，并且不得休眠或暂停至少六个小时，其中两小时必须持续。 尽管可能会更新不满足这些要求的设备，但满足这些要求的设备更新的可能性最大。

:::image type="content" source="../../media/mmd-device-status.png" alt-text="显示左上方设备活动状态的 Donut 图的报告、右上方的视图筛选器以及用于生成报告的按钮，以及底部的详细信息表":::

我们使用这些标签报告设备状态： 

- **Ready for user**： 已在服务中成功注册并准备向用户提供的设备 
- **活动**：当前使用且已满足活动条件的设备 (六小时，两个连续) 用于最新的安全更新版本，并且已在过去的五天内使用 Microsoft Intune 至少签入一次。 
- **已同步**：过去 28 天内使用和已使用 Intune 签入的设备 
- **不同步**：过去 28 天内使用但尚未使用 Intune 签入的设备 
- **其他**：类别聚合一些通常发生在设备注册期间的错误状态。 有关更多详细信息，请参阅 [设备注册疑难解答](../get-started/register-devices-self.md#troubleshooting-device-registration)。