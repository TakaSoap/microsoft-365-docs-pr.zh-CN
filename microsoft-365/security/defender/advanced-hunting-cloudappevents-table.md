---
title: 高级搜寻架构中的 CloudAppEvents 表
description: 了解高级搜寻架构的 CloudAppEvents 表中云应用和服务的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、Microsoft 365 Defender、microsoft 365、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、CloudAppEvents、Defender for Cloud应用
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 77b4ebd42a8c105340d6d965380aa42b64ae6734
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664955"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

高级`CloudAppEvents`[搜寻](advanced-hunting-overview.md)架构中的表包含有关Microsoft Defender for Cloud Apps涵盖的各种云应用和服务中的活动的信息。 有关完整列表，请跳转到 [涵盖的应用和服务](#apps-and-services-covered)。 使用此参考来构建从此表返回信息的查询。

> [!IMPORTANT]
> 此表包含表中 `AppFileEvents` 以前可用的信息。 从 2021 年 3 月 7 日开始，在此日期及以后通过云服务中与文件相关的活动进行搜寻的用户应改用该 `CloudAppEvents` 表。 <br><br>确保搜索仍使用 `AppFileEvents` 表的查询和自定义检测规则，并编辑它们以使用表 `CloudAppEvents` 。 有关转换受影响查询的更多指南，可在 Hunt 中通过[高级搜寻Microsoft 365 Defender云应用活动](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)找到。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | 记录事件的日期和时间 |
| `ActionType` | `string` | 触发事件的活动类型 |
| `Application` | `string` | 执行记录操作的应用程序 |
| `ApplicationId` | `string` | 应用程序的唯一标识符 |
| `AccountObjectId` | `string` | Azure Active Directory中帐户的唯一标识符 |
| `AccountId` | `string` | Microsoft Defender for Cloud Apps找到的帐户的标识符。 可以是Azure Active Directory ID、用户主体名称或其他标识符。 |
| `AccountDisplayName` | `string` | 通讯簿中显示的帐户用户的名称。 通常是给定或名字、中间发起和姓氏或姓氏的组合。 |
| `IsAdminOperation` | `string` | 指示活动是否由管理员执行 |
| `DeviceType` | `string` | 基于用途和功能的设备类型，例如"网络设备"、"工作站"、"服务器"、"移动"、"游戏控制台"或"打印机" |
| `OSPlatform` | `string` | 在设备上运行的操作系统的平台。 此列指示特定操作系统，包括同一系列中的变体，例如Windows 11、Windows 10和Windows 7。 |
| `IPAddress` | `string` | 分配给终结点并在相关网络通信期间使用的 IP 地址 |
| `IsAnonymousProxy` | `string` | 指示 IP 地址是否属于已知匿名代理 |
| `CountryCode` | `string` | 两个字母代码，指示客户端 IP 地址地理位置所在的国家/地区 |
| `City` | `string` | 客户端 IP 地址地理位置所在的城市 |
| `Isp` | `string` | 与 IP 地址关联的 Internet 服务提供商 (ISP)  |
| `UserAgent` | `string` | 来自 Web 浏览器或其他客户端应用程序的用户代理信息 |
| `ActivityType` | `string` | 触发事件的活动类型 |
| `ActivityObjects` | `dynamic` | 记录活动中涉及的对象列表，例如文件或文件夹 |
| `ObjectName` | `string` | 已记录操作应用于的对象的名称 |
| `ObjectType` | `string` | 应用了记录操作的对象类型，例如文件或文件夹 |
| `ObjectId` | `string` | 已记录操作应用于的对象的唯一标识符 |
| `ReportId` | `string` | 事件的唯一标识符 |
| `RawEventData` | `string` | 源应用程序或服务的原始事件信息，采用 JSON 格式 |
| `AdditionalFields` | `dynamic` | 有关实体或事件的其他信息 |
| `AccountType` | `string` | 用户帐户的类型，指示其常规角色和访问级别，如 Regular、System、Admin、DcAdmin、System、Application |
| `IsExternalUser` | `boolean` | 指示网络中的用户是否不属于组织的域 |
| `IsImpersonated` | `boolean` | 指示活动是否由一个用户为另一个 (模拟) 用户执行 |
| `IPTags` | `dynamic` | 应用于特定 IP 地址和 IP 地址范围的客户定义信息 |
| `IPCategory` | `string` | 有关 IP 地址的其他信息 |
| `UserAgentTags` | `dynamic` | 用户代理字段中标记中的Microsoft Defender for Cloud Apps提供的详细信息。 可以具有以下任一值：本机客户端、过时的浏览器、过时的操作系统、机器人 |

## <a name="apps-and-services-covered"></a>涵盖的应用和服务

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- OneDrive for Business
- Power Automate
- Power BI
- SharePoint Online
- Skype for Business
- Office 365
- Yammer

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
