---
title: 高级搜寻架构中的 EmailUrlInfo 表
description: 在高级搜寻架构的 EmailUrlInfo 表中，了解 URL 或链接信息
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, EmailUrlInfo, 网络消息 ID, URL, 链接
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 10cf82667fd97eebe66c376e0539db000f20b1c2
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910832"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**适用于：**
- Microsoft 威胁防护

[!include[Prerelease information](prerelease.md)]

[高级搜寻](advanced-hunting-overview.md)架构中的 `EmailUrlInfo` 表包含有关由 Office 365 ATP 处理的电子邮件和附件中的 URL 的信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `EventTime` | datetime | 记录事件的日期和时间 |
| `UrlId` | string | 电子邮件主题、正文或附件中 URL 的唯一标识符 |
| `NetworkMessageId` | string | 由 Office 365 生成的电子邮件的唯一标识符 |
| `Url` | string | 电子邮件主题、正文或附件中的完整 URL |

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)