---
title: 高级搜寻架构中的 DeviceFileEvents 表
description: 了解高级搜寻架构的 DeviceFileEvents 表中与文件相关的事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， 文件创建事件， DeviceFileEvents， 文件， 路径， 哈希， sha1， sha256， md5
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2350e2dfd4736743f23d181d4fc2c6de0d82ccc0
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531869"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

高级 `DeviceFileEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关文件创建、修改和其他文件系统事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持的事件 (值) ，请使用 Defender for Cloud 中提供的内置 `ActionType` 架构参考。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | 记录事件的日期和时间 |
| `DeviceId` | `string` | 服务中的计算机的唯一标识符 |
| `DeviceName` | `string` | 计算机的完全限定域名 (FQDN) |
| `ActionType` | `string` | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `FileName` | `string`| 录制操作所应用到的文件的名称 |
| `FolderPath` | `string` | 包含已记录操作所应用到的文件的文件夹 |
| `SHA1` | `string` | 录制操作所应用到的文件的 SHA-1 |
| `SHA256` | `string` | 录制操作所应用到的文件的 SHA-256。 通常不会填充此字段 — 可用时使用 SHA1 列。 |
| `MD5` | `string` | 已记录操作所应用到的文件的 MD5 哈希 |
| `FileOriginUrl` | `string` | 下载文件的 URL |
| `FileOriginReferrerUrl` | `string` | 链接到已下载文件的网页的 URL |
| `FileOriginIP` | `string` | 从其中下载文件的 IP 地址 |
| `PreviousFolderPath` | `string` | 应用录制的操作之前包含文件的原始文件夹 |
| `PreviousFileName` | `string` | 作为操作结果重命名的文件的原始名称 |
| `FileSize` | `long` | 文件大小（以字节为单位） |
| `InitiatingProcessAccountDomain` | `string` | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | `string` | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessAccountUpn` | `string` | 用户主体 (UPN) 运行负责事件的进程的帐户的名称 |
| `InitiatingProcessAccountObjectId` | `string` | Azure AD负责事件的进程的用户帐户的对象 ID |
| `InitiatingProcessMD5` | `string` | 启动事件的进程和 (文件的 MD5) 哈希 |
| `InitiatingProcessSHA1` | `string` | 启动事件 (映像文件) SHA-1 |
| `InitiatingProcessSHA256` | `string` | 启动事件 (映像文件) SHA-256。 通常不会填充此字段 — 可用时使用 SHA1 列。 |
| `InitiatingProcessFolderPath` | `string` | 包含启动事件 (进程) 文件的文件夹 |
| `InitiatingProcessFileName` | `string` | 启动事件的进程的名称 |
| `InitiatingProcessFileSize` | `long` | 启动事件 (进程) 文件的大小 |
| `InitiatingProcessVersionInfoCompanyName` | `string` | 进程版本信息中的公司名称 (负责) 文件 |
| `InitiatingProcessVersionInfoProductName` | `string` | 进程版本信息中的产品名称 (负责) 文件 |
|` InitiatingProcessVersionInfoProductVersion` | `string` | 进程版本信息中的产品版本 (负责) 文件 |
|` InitiatingProcessVersionInfoInternalFileName` | `string` | 进程版本信息的内部文件名 (负责) 文件 |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | 负责事件的进程版本信息 (文件) 文件的原始文件名 |
| `InitiatingProcessVersionInfoFileDescription` | `string` | 来自负责事件的进程 (文件) 说明 |
| `InitiatingProcessId` | `int` | 进程 ID (PID) 启动事件的进程的 PID |
| `InitiatingProcessCommandLine` | `string` | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | `datetime` | 启动事件的过程的日期和时间 |
| `InitiatingProcessIntegrityLevel` | `string` | 启动事件的过程的完整性级别。 Windows某些特征（例如是否从 Internet 下载启动）为进程分配完整性级别。 这些完整性级别影响对资源的权限 |
| `InitiatingProcessTokenElevation` | `string` | 指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升 |
| `InitiatingProcessParentId` | `int` | 进程 ID (PID) 生成负责事件的进程的父进程的 PID |
| `InitiatingProcessParentFileName` | `string` | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | `datetime` | 启动负责事件的进程的父级的日期和时间 |
| `RequestProtocol` | `string` | 网络协议（如果适用）用于启动活动：Unknown、Local、SMB 或 NFS |
| `RequestSourceIP` | `string` | 发起活动的远程设备的 IPv4 或 IPv6 地址 |
| `RequestSourcePort` | `string` | 启动活动的远程设备的源端口 |
| `RequestAccountName` | `string` | 用于远程启动活动的帐户的用户名 |
| `RequestAccountDomain` | `string` | 用于远程启动活动的帐户的域 |
| `RequestAccountSid` | `string` | 安全 (用于) 启动活动的帐户的 SID 标识符 |
| `ShareName` | `string` | 包含文件的共享文件夹的名称 |
| `InitiatingProcessFileSize` | `long` | 运行负责事件的进程的文件的大小 |
| `SensitivityLabel` | `string` | 应用于电子邮件、文件或其他内容的标签，用于将其分类以用于信息保护 |
| `SensitivitySubLabel` | `string` | 应用于电子邮件、文件或其他内容的子标签，用于将其分类以用于信息保护;敏感度子标签按敏感度标签分组，但单独处理 |
| `IsAzureInfoProtectionApplied` | `boolean` | 指示文件是否由 Azure 信息保护进行加密 |
| `ReportId` | `long` | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。 |
| `AppGuardContainerId` | `string` | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |
| `AdditionalFields` | `string` | 有关实体或事件的其他信息 |
>[!NOTE]
> 文件哈希信息将始终在可用时显示。 但是，无法计算 SHA1、SHA256 或 MD5 的原因有多种。 例如，该文件可能位于远程存储中、由另一个进程锁定、已压缩或标记为虚拟。 在这些情况下，文件哈希信息显示为空。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
