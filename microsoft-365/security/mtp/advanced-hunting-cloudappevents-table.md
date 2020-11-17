---
title: 高级搜寻架构中的 CloudAppEvents 表
description: 了解高级搜寻架构的 CloudAppEvents 表中的云应用和服务中的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、CloudAppEvents、云应用安全性、MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087760"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

当前在预览中， `CloudAppEvents` [高级搜寻](advanced-hunting-overview.md) 架构中的表格包含有关各种云应用和服务（尤其是 Microsoft 团队和 Exchange Online）中的活动的信息。 使用此参考来构建从此表返回信息的查询。

此表将展开以包含 Microsoft 云应用安全监视的更多活动。 最终，此表将包含当前存储在 [AppFileEvents](advanced-hunting-appfileevents-table.md) 表中的文件活动。 当更多数据移动到此表中时，Microsoft 将提供其他指导。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型 |
| `Application` | string | 执行录制操作的应用程序 |
| `ApplicationId` | string | 应用程序的唯一标识符 |
| `AccountObjectId` | string | Azure Active Directory 中的帐户的唯一标识符 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `IsAdminOperation` | string | 指示活动是否由管理员执行 |
| `DeviceType` | string | 基于用途和功能的设备类型，如 "网络设备"、"工作站"、"服务器"、"移动"、"游戏控制台" 或 "打印机" | 
| `OSPlatform` | string | 设备上运行的操作系统的平台。 此列指示特定操作系统，包括同一系列内的变体，如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，并在相关的网络通信过程中使用 |
| `IsAnonymousProxy` | string | 指示 IP 地址是否属于已知的匿名代理 |
| `CountryCode` | string | 指示客户端 IP 地址所在国家/地区的两个字母的代码 geolocated |
| `City` | string | 客户端 IP 地址为 "geolocated" 的城市 |
| `Isp` | string | Internet 服务提供商 (与 IP 地址关联的 ISP)  |
| `UserAgent` | string | 来自 web 浏览器或其他客户端应用程序的用户代理信息 |
| `ActivityType` | string | 触发事件的活动类型 |
| `ActivityObjects` | string | 录制的活动中涉及的对象（如文件或文件夹）的列表 |
| `ObjectName` | string | 将录制的操作应用于的对象的名称 |
| `ObjectType` | string | 将录制的操作应用于的对象的类型（如文件或文件夹） |
| `ObjectId` | string | 应用录制的操作的对象的唯一标识符 |
| `ReportId` | string | 事件的唯一标识符 |
| `RawEventData` | string | 来自 JSON 格式的源应用程序或服务的原始事件信息 |
| `AdditionalFields` | string | 有关实体或事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
