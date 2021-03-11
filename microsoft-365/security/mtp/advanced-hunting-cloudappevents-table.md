---
title: 高级搜寻架构中的 CloudAppEvents 表
description: 了解高级搜寻架构的 CloudAppEvents 表中的云应用和服务事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， CloudAppEvents， Cloud App Security， MCAS
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
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712482"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender



高级搜寻架构中的表包含有关 Microsoft Cloud App Security 涵盖的各种云应用和服务中的活动的信息，特别是 `CloudAppEvents` Dropbox、Exchange [](advanced-hunting-overview.md) Online、OneDrive、Microsoft Teams 和 SharePoint。 使用此参考来构建从此表返回信息的查询。

>[!IMPORTANT]
>此表包含以前在表中可用的 `AppFileEvents` 信息。 从 2021 年 3 月 7 开始，在此日期及之后，在云服务中搜寻与文件相关的活动的用户应改为使用 `CloudAppEvents` 该表。 <br><br>请确保搜索仍在使用该表的查询和自定义检测规则， `AppFileEvents` 并编辑它们以使用 `CloudAppEvents` 该表。 有关转换受影响的查询的更多指南，可在 [使用 Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)高级搜寻的云应用活动中找到 Hunt。


有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型 |
| `Application` | string | 执行录制的操作的应用程序 |
| `ApplicationId` | string | 应用程序的唯一标识符 |
| `AccountObjectId` | string | Azure Active Directory 中帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户的名称。 通常，给定或名字、中间初始和姓氏或姓氏的组合。 |
| `IsAdminOperation` | string | 指示活动是否由管理员执行 |
| `DeviceType` | string | 基于用途和功能的设备类型，例如"网络设备"、"工作站"、"服务器"、"移动"、"游戏控制台"或"打印机" | 
| `OSPlatform` | string | 在设备上运行的操作系统的平台。 此列指示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，在相关网络通信期间使用 |
| `IsAnonymousProxy` | string | 指示 IP 地址是否属于已知匿名代理 |
| `CountryCode` | string | 两个字母的代码，指示客户端 IP 地址被异地分配的国家/地区 |
| `City` | string | 客户端 IP 地址被异地分配的城市 |
| `Isp` | string | 与 IP 地址 (ISP) 服务提供商 |
| `UserAgent` | string | 来自 Web 浏览器或其他客户端应用程序的用户代理信息 |
| `ActivityType` | string | 触发事件的活动类型 |
| `ActivityObjects` | string | 记录的活动所涉及的对象列表，如文件或文件夹 |
| `ObjectName` | string | 记录的操作应用于的对象的名称 |
| `ObjectType` | string | 已记录操作应用于的对象类型，如文件或文件夹 |
| `ObjectId` | string | 记录的操作应用于的对象的唯一标识符 |
| `ReportId` | string | 事件的唯一标识符 |
| `RawEventData` | string | 来自源应用程序或服务的原始事件信息，格式为 JSON |
| `AdditionalFields` | string | 有关实体或事件的其他信息 |


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
