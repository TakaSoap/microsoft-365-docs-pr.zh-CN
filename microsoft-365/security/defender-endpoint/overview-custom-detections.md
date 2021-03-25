---
title: Microsoft Defender ATP 中的自定义检测概述
ms.reviewer: ''
description: 了解如何使用高级搜寻创建自定义检测和生成警报
keywords: 自定义检测， 警报， 检测规则， 高级搜寻， 智能寻线， 查询， 响应操作， 间隔， mdatp， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c5de642d2fd22301b5cef1cf3674e60529455d5e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186913"
---
# <a name="custom-detections-overview"></a>自定义检测概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


通过自定义检测，你可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的设备。 为此，可以使用可自动触发警报和响应操作且可自定义的检测规则。

自定义 [检测与高级](advanced-hunting-overview.md)搜寻一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的广泛事件和系统信息。 你可以将它们设置为定期运行，从而在有匹配项时生成警报并执行响应操作。

自定义检测提供：
- 针对从高级搜寻查询构建的基于规则的检测的警报
- 适用于文件和设备的自动响应操作

## <a name="related-topics"></a>相关主题
- [创建检测规则](custom-detection-rules.md)
- [查看和管理检测规则](custom-detections-manage.md)
- [高级搜寻概述](advanced-hunting-overview.md)
