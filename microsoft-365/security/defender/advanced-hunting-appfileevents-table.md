---
title: 高级搜寻架构中的 AppFileEvents 表
description: 在高级搜寻架构的 AppFileEvents 表中了解与云应用和服务关联的文件相关事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， AppFileEvents， Cloud App Security， MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 861a04eb168190f2bb64bbb0258de6767c619e1b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934713"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `AppFileEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关 Microsoft Cloud App Security 监视的云应用和服务中与文件相关的活动的信息。 使用此参考来构建从此表返回信息的查询。

>[!WARNING]
>此表将很快停用。 截至 2021 年 3 月 7 日 `AppFileEvents` ，该表不再记录记录。 在超过该日期的云服务中搜寻与文件相关的活动的用户应改为使用 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表。 <br><br>请确保搜索仍使用表的查询和自定义检测规则，并 `AppFileEvents` 编辑它们以使用 `CloudAppEvents` 该表。 有关转换受影响查询的更多指南，可在 [使用 Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)高级搜寻的云应用活动中找到。


有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `Application` | string | 执行录制的操作的应用程序 |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `FolderPath` | string | 包含已记录操作所应用到的文件的文件夹 |
| `PreviousFileName` | string | 作为操作结果重命名的文件的原始名称 |
| `PreviousFolderPath` | string | 应用录制的操作之前包含文件的原始文件夹 |
| `Protocol` | string | 使用的网络协议 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountSid` | string | 帐户 (SID) 安全标识符 |
| `AccountUpn` | string | 帐户 (UPN) 用户主体名称 |
| `AccountObjectId` | string | Azure AD 中帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定或名字、中间启动和姓氏或姓氏的组合。 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `DeviceType` | string | 设备类型 | 
| `OSPlatform` | string | 在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，在相关的网络通信期间使用 |
| `Port` | string | 通信期间使用的 TCP 端口  |
| `DestinationDeviceName` | string | 运行处理所记录操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | string | 运行处理所记录操作的服务器应用程序的设备的 IP 地址 |
| `DestinationPort` | string | 相关网络通信的目标端口 |
| `Location` | string | 与事件关联的城市、国家/地区或其他地理位置 |
| `Isp` | string | Internet 服务提供商 (ISP) 与终结点 IP 地址关联 |
| `ReportId` | long | 事件的唯一标识符 |
| `AdditionalFields` | string | 有关实体或事件的其他信息 |

>[!TIP]
> 有关表支持的事件类型 () ，请使用安全中心中提供的内置架构 `ActionType` 参考。


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
