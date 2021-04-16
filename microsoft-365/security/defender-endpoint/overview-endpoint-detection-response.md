---
title: 终结点检测和响应功能概述
ms.reviewer: ''
description: 了解 Microsoft Defender for Endpoint 中的终结点检测和响应功能
keywords: 适用于终结点的 microsoft defender， 终结点检测和响应， 响应， 检测， 网络安全， 保护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 138a6afde9e8c601fd41811928580644b85bf2e2
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861715"
---
# <a name="overview-of-endpoint-detection-and-response"></a>终结点检测和响应概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable. 安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。

检测到威胁时，将在系统中创建警报以供分析人员进行调查。 使用相同攻击技术或归属于同一攻击者的警报会被聚合到名为 _“事件”_ 的实体中。 以此方式聚合警报可便于分析员更轻松地综合调查和响应威胁。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

受"假设泄露"意识启发，Defender for Endpoint 持续收集行为网络遥测。 其中包括流程信息、网络活动、内核和内存管理程序的深入信息、用户登录活动、注册表和文件系统更改等。 此类信息存储六个月，这样分析员可以追溯到攻击开始的时间。 然后，分析员可以对各种视图进行透视，并通过多个攻击途径展开调查。

借助响应功能，可以对受影响的实体采取行动，从而快速修正威胁。


## <a name="related-topics"></a>相关主题
- [安全操作仪表板](security-operations-dashboard.md)
- [事件队列](view-incidents-queue.md)
- [警报队列](alerts-queue.md)
- [设备列表](machines-view-overview.md)

