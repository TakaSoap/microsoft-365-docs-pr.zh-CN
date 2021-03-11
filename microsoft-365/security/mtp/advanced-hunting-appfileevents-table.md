---
title: 高级搜寻架构中的 AppFileEvents 表
description: 在高级搜寻架构的 AppFileEvents 表中了解与云应用和服务关联的文件相关事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， AppFileEvents， Cloud App Security， MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9eb2f195959409ad25b9a401a44425cc4af7f97e
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712494"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `AppFileEvents` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关 Microsoft Cloud App Security 监视的云应用和服务中的文件相关活动的信息。 使用此参考来构建从此表返回信息的查询。

>[!WARNING]
>此表将很快停用。 自 2021 年 3 月 7 日起， `AppFileEvents` 该表不再记录记录。 用户应改为使用 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表，以在超过该日期的云服务中搜寻与文件相关的活动。 <br><br>请确保搜索仍在使用该表的查询和自定义检测规则， `AppFileEvents` 并编辑它们以使用 `CloudAppEvents` 该表。 有关转换受影响的查询的更多指南，可在 [使用 Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)高级搜寻的云应用活动中找到 Hunt。


有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `Application` | string | 执行录制的操作的应用程序 |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `FolderPath` | string | 包含已记录操作所应用到的文件的文件夹 |
| `PreviousFileName` | string | 由于操作而重命名的文件的原始名称 |
| `PreviousFolderPath` | string | 应用录制的操作之前包含文件的原始文件夹 |
| `Protocol` | string | 使用的网络协议 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountSid` | string | 帐户 (SID) 安全标识符 |
| `AccountUpn` | string | 帐户 (UPN) 用户主体名称 |
| `AccountObjectId` | string | Azure AD 中帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户的名称。 通常，给定或名字、中间初始和姓氏或姓氏的组合。 |
| `DeviceName` | string | 设备的 FQDN (完全) 域名 |
| `DeviceType` | string | 设备类型 | 
| `OSPlatform` | string | 在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，在相关网络通信期间使用 |
| `Port` | string | 通信期间使用的 TCP 端口  |
| `DestinationDeviceName` | string | 运行处理所记录操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | string | 运行处理所记录操作的服务器应用程序的设备的 IP 地址 |
| `DestinationPort` | string | 相关网络通信的目标端口 |
| `Location` | string | 与事件关联的城市、国家/地区或其他地理位置 |
| `Isp` | string | Internet 服务提供商 (ISP) 与终结点 IP 地址关联 |
| `ReportId` | long | 事件的唯一标识符 |
| `AdditionalFields` | string | 有关实体或事件的其他信息 |

>[!TIP]
> 有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构引用。


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
