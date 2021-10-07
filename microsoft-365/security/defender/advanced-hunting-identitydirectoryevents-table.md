---
title: 高级搜寻架构中的 IdentityDirectoryEvents 表
description: 了解高级搜寻架构的 IdentityDirectoryEvents 表中的域控制器和 Active Directory 事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， IdentityDirectoryEvents， 域控制器， Active Directory， Microsoft Defender for Identity， 标识
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 40f8804c40236e680543d199e3dc6294fefa1414
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159134"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `IdentityDirectoryEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含涉及运行 Active Directory 和 AD (本地域控制器) 。 此表捕获各种与标识相关的事件，如密码更改、密码过期和 UPN (用户) 名称。 它还捕获域控制器上的系统事件，如计划任务和 PowerShell 活动。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持 (事件) 类型的详细信息，请使用安全中心中提供的内置 `ActionType` 架构参考。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `Application` | string | 执行录制的操作的应用程序 |
| `TargetAccountUpn` | string | 用户主体 (UPN) 记录操作应用于的帐户的名称 |
| `TargetAccountDisplayName` | string | 已记录操作应用于的帐户的显示名称 |
| `TargetDeviceName` | string | 已记录 () 的设备的完全限定域名和 FQDN |
| `DestinationDeviceName` | string | 运行处理所记录操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | string | 运行处理所记录操作的服务器应用程序的设备的 IP 地址 |
| `DestinationPort` | string | 活动的目标端口 |
| `Protocol` | string | 通信期间使用的协议 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountUpn` | string | 帐户 (UPN) 的用户主体名称 |
| `AccountSid` | string | 帐户 (SID) 安全标识符 |
| `AccountObjectId` | string | Azure Active Directory |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定或名字、中间启动和姓氏或姓氏的组合。 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `IPAddress` | string | 通信期间分配给设备的 IP 地址 |
| `Port` | string | 通信期间使用的 TCP 端口 |
| `Location` | string | 与事件关联的城市、国家/地区或其他地理位置 |
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
