---
title: 高级搜寻架构中的 EmailUrlInfo 表
description: 在高级搜寻架构的 EmailUrlInfo 表中，了解 URL 或链接信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， EmailUrlInfo， 网络消息 ID， url， 链接
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d0c9a8f1456aaeedbc8d296a1f738d0b2c57a156
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531539"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `EmailUrlInfo` 搜寻[架构中的](advanced-hunting-overview.md)表包含有关由 Microsoft Defender for Office 365 处理的电子邮件和附件的 URL。 使用此参考来构建从此表返回信息的查询。 

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | 记录事件的日期和时间 |
| `NetworkMessageId` | `string` | 由用户生成的电子邮件的唯一Microsoft 365 |
| `Url` | `string` | 电子邮件主题、正文或附件中的完整 URL |
| `UrlDomain` | `string` | URL 的域名或主机名 |
| `ReportId` | `long` | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
