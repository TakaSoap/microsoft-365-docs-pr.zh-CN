---
title: 高级搜寻架构中的 AppFileEvents 表
description: 了解与高级搜寻架构的 AppFileEvents 表中的云应用和服务关联的与文件相关的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AppFileEvents、云应用安全性、MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899335"
---
# <a name="appfileevents"></a>AppFileEvents

**适用于：**
- Microsoft 威胁防护

`AppFileEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 Microsoft 云应用安全监视的云应用和服务中与文件相关的活动的信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型 |
| `Application` | string | 执行录制操作的应用程序 |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `FolderPath` | string | 包含录制的操作所应用于的文件的文件夹 |
| `PreviousFileName` | string | 作为操作的结果重命名的文件的原始名称 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountUpn` | string | 帐户的用户主体名称（UPN） |
| `AccountObjectId` | string | Azure AD 中的帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，并在相关的网络通信过程中使用 |
| `Location` | string | 与事件关联的城市、国家或其他地理位置 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
