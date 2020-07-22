---
title: 高级搜寻架构中的 IdentityQueryEvents 表
description: 了解高级搜寻架构的 IdentityQueryEvents 表中的 Active Directory 查询事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、IdentityQueryEvents、Azure AD、Active Directory、Azure ATP、标识、LDAP 查询
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204871"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**适用于：**
- Microsoft 威胁防护

`IdentityQueryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含针对 Active Directory 对象（如用户、组、设备和域）执行的查询的相关信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型 |
| `Application` | 字符串 | 执行录制操作的应用程序 |
| `QueryType` | 字符串 | 查询类型，如 QueryGroup、QueryUser 或 EnumerateUsers |
| `QueryTarget` | 字符串 | 要查询的用户、组、设备、域或任何其他实体类型的名称 |
| `Query` | 字符串 | 用于运行查询的字符串 |
| `Protocol` | 字符串 | 通信过程中使用的协议 |
| `AccountName` | 字符串 | 帐户的用户名 |
| `AccountDomain` | 字符串 | 帐户的域 |
| `AccountUpn` | 字符串 | 帐户的用户主体名称（UPN） |
| `AccountSid` | 字符串 | 帐户的安全标识符（SID） |
| `AccountObjectId` | 字符串 | Azure AD 中的帐户的唯一标识符 |
| `AccountDisplayName` | 字符串 | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `DeviceName` | 字符串 | 终结点的完全限定的域名（FQDN） |
| `IPAddress` | 字符串 | 分配给终结点的 IP 地址，并在相关的网络通信过程中使用 |
| `DestinationDeviceName` | 字符串 | 运行处理录制操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | 字符串 | 运行用于处理录制操作的服务器应用程序的设备的 IP 地址 |
| `TargetDeviceName` | 字符串 | 应用录制的操作的设备的完全限定的域名（FQDN） |
| `TargetAccountUpn` | 字符串 | 应用录制的操作的帐户的用户主体名称（UPN） |
| `TargetAccountDisplayName` | 字符串 | 将录制的操作应用于的帐户的显示名称 |
| `Location` | 字符串 | 与事件关联的城市、国家或其他地理位置 |
| `ReportId` | long | 事件的唯一标识符 |
| `AdditionalFields` | 字符串 | 有关实体或事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
