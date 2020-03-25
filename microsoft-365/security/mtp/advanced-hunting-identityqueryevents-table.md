---
title: 高级搜寻架构中的 IdentityQueryEvents 表
description: 了解高级搜寻架构的 IdentityQueryEvents 表中的 Active Directory 查询事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、IdentityQueryEvents、Azure AD、Active Directory、AzureATP、标识、LDAP 查询
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929109"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

**适用于：**
- Microsoft 威胁防护

`IdentityQueryEvents` [高级搜寻](advanced-hunting-overview.md)架构中的表包含针对 Active Directory 对象（如用户、组、设备和域）执行的查询的相关信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型 |
| `Application` | string | 执行录制操作的应用程序 |
| `Query` | string | 查询类型： QueryGroup、QueryUser 或 EnumerateUsers |
| `QueryObject` | string | 要查询的用户、组、设备、域或任何其他实体类型的名称 |
| `Protocol` | string | 通信过程中使用的协议 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountUpn` | string | 帐户的用户主体名称（UPN） |
| `AccountSid` | string | 帐户的安全标识符（SID） |
| `AccountObjectId` | string | Azure AD 中的帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `DeviceName` | string | 终结点的完全限定的域名（FQDN） |
| `IPAddress` | string | 分配给终结点的 IP 地址，并在相关的网络通信过程中使用 |
| `Location` | string | 与事件关联的城市、国家或其他地理位置 |

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
