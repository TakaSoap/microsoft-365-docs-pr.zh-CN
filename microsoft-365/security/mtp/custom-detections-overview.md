---
title: Microsoft 威胁防护中的自定义检测概述
description: 了解如何使用高级搜寻来创建自定义检测并生成警报
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、microsoft 365、Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498347"
---
# <a name="custom-detections-overview"></a>自定义检测概述

**适用于：**
- Microsoft 威胁防护

使用自定义检测，可以主动监视和响应各种事件和系统状态，包括可疑的入侵活动和错误配置的终结点。 这可通过可自定义的检测规则（自动触发警报和响应操作）实现。

自定义检测适用于[高级搜寻](advanced-hunting-overview.md)，它提供一种功能强大的灵活的查询语言，可覆盖网络中的一组大量事件和系统信息。 您可以将其设置为定期运行，并在存在匹配项时生成警报和采取响应操作。

自定义检测提供：
- 从高级搜寻查询生成的基于规则的检测的警报
- 自动响应操作

## <a name="related-topic"></a>相关主题
- [创建和管理自定义检测规则](custom-detection-rules.md)
- [高级搜寻概述](advanced-hunting-overview.md)