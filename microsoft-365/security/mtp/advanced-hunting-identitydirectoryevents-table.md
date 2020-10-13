---
title: 高级搜寻架构中的 IdentityDirectoryEvents 表
description: 了解高级搜寻架构的 IdentityDirectoryEvents 表中的域控制器和 Active Directory 事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、IdentityDirectoryEvents、域控制器、Active Directory、Azure ATP、标识
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: d93ef3eb3bbf6def0f633aa0f69032e37d10c4c9
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430369"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

`IdentityDirectoryEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含与运行 ACTIVE Directory (AD) 的本地域控制器有关的事件。 此表捕获各种与标识相关的事件，如密码更改、密码过期和用户主体名称 (UPN) 更改。 它还捕获域控制器上的系统事件，如计划任务和 PowerShell 活动。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | string | 执行录制操作的应用程序 |
| `TargetAccountUpn` | string | 应用了录制的操作的帐户 (UPN) 的用户主体名称 |
| `TargetAccountDisplayName` | string | 将录制的操作应用于的帐户的显示名称 |
| `TargetDeviceName` | string | 应用录制的操作的设备的完全限定的域名 (FQDN)  |
| `DestinationDeviceName` | string | 运行处理录制操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | string | 运行用于处理录制操作的服务器应用程序的设备的 IP 地址 |
| `DestinationPort` | string | 活动的目标端口 |
| `Protocol` | string | 通信过程中使用的协议 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountUpn` | string | 帐户的用户主体名称 (UPN)  |
| `AccountSid` | string | 帐户的安全标识符 (SID)  |
| `AccountObjectId` | string | Azure Active Directory 中的帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `DeviceName` | string | 设备 (FQDN) 的完全限定的域名称 |
| `IPAddress` | string | 通信期间分配给设备的 IP 地址 |
| `Port` | string | 通信过程中使用的 TCP 端口 |
| `Location` | string | 与事件关联的城市、国家或其他地理位置 |
| `ISP` | string | 与 IP 地址关联的 Internet 服务提供商 |
| `ReportId` | long | 事件的唯一标识符 |
| `AdditionalFields` | string | 有关实体或事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
