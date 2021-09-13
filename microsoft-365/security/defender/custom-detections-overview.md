---
title: 自定义检测在Microsoft 365 Defender
description: 了解如何使用高级搜寻创建自定义检测和生成警报
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59175386"
---
# <a name="custom-detections-overview"></a>自定义检测概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

通过自定义检测，您可以主动监视和响应各种事件和系统状态，包括可疑的泄露活动和错误配置的终结点。 这通过可自定义的检测规则实现，这些规则可自动触发警报和响应操作。

自定义 [检测与高级](advanced-hunting-overview.md)搜寻一起运行，提供一种功能强大、灵活的查询语言，涵盖来自网络的广泛事件和系统信息。 可以将它们设置为在匹配时定期运行、生成警报以及执行响应操作。

自定义检测提供：
- 根据高级搜寻查询构建的基于规则的检测警报
- 自动响应操作

## <a name="see-also"></a>另请参阅
- [创建和管理自定义检测规则](custom-detection-rules.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [从 Microsoft Defender for Endpoint 迁移高级搜寻查询](advanced-hunting-migrate-from-mde.md)
