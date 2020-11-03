---
title: 高级搜寻架构中的 AlertEvidence 表
description: 了解与高级搜寻架构的 AlertEvidence 表中的通知关联的信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AlertInfo、设备、实体、证据、文件、IP 地址、设备、计算机、用户、帐户
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
ms.openlocfilehash: 549eed005e06a7d52ce2f881820ae9fdeffdfea7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847676"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

`AlertEvidence`[高级搜寻](advanced-hunting-overview.md)架构中的表格包含有关各种实体（文件、IP 地址、url、用户或设备）的信息，这些信息与 Microsoft defender For Endpoint、Microsoft defender for Office 365、Microsoft 云应用安全性和 Microsoft defender for Identity 相关联的警报相关联。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `AlertId` | string | 警报的唯一标识符 |
| `ServiceSource` | string | 提供通知信息的产品或服务 |
| `EntityType` | string | 对象的类型，如文件、进程、设备或用户 |
| `EvidenceRole` | string | 如何将实体包含在警报中，以指示它是受影响的还是只是相关的 |
| `EvidenceDirection` | string | 指示实体是否为网络连接的源或目标 |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `FolderPath` | string | 包含录制的操作所应用于的文件的文件夹 |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `SHA256` | string | 录制操作所应用到的文件的 SHA-256。 通常不填充此字段—使用 SHA1 列（如果可用）。 |
| `FileSize` | int | 文件大小（以字节为单位） |
| `ThreatFamily` | string | 已在其下对可疑或恶意文件或流程进行了分类的恶意软件系列 |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemoteUrl` | string | 连接到的 URL 或完全限定域名 (FQDN) |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `AccountSid` | string | 帐户的安全标识符 (SID)  |
| `AccountObjectId` | string | Azure Active Directory 中的帐户的唯一标识符 |
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `LocalIP` | string | 分配给在通信期间使用的本地设备的 IP 地址 |
| `NetworkMessageId` | string | 由 Office 365 生成的电子邮件的唯一标识符 |
| `EmailSubject` | string | 电子邮件主题 |
| `ApplicationId` | string | 应用程序的唯一标识符 |
| `Application` | string | 执行录制操作的应用程序 |
| `ProcessCommandLine` | string | 用于创建新进程的命令行 |
| `AdditionalFields` | string | 有关 JSON 数组格式事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
