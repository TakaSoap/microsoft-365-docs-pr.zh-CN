---
title: 高级搜寻架构中的 DeviceNetworkEvents 表
description: 了解可以从高级搜寻架构的 DeviceNetworkEvents 表查询的网络连接事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， devicenetworkevents， NetworkCommunicationEvents， 网络连接， 远程 ip， 本地 ip
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
ms.openlocfilehash: 874a8256506cc5d66b16c3c927faf7794f62ffff
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60664450"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高级 `DeviceNetworkEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关网络连接和相关事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持 (类型的事件) ，请使用安全中心中提供的内置架构 `ActionType` 参考。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemotePort` | int | 连接到的远程设备的 TCP 端口 |
| `RemoteUrl` | string | 连接到的 URL 或完全限定域名 (FQDN) |
| `LocalIP` | string | 分配给通信期间使用的本地计算机 IP 地址 |
| `LocalPort` | int | 通信过程中使用的本地计算机上 TCP 端口 |
| `Protocol` | string | 通信期间使用的协议 |
| `LocalIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `RemoteIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `InitiatingProcessSHA1` | string | 启动事件 (映像文件) SHA-1 |
| `InitiatingProcessSHA256` | string | 启动事件 (映像文件) SHA-256。 通常不会填充此字段 — 可用时使用 SHA1 列。 |
| `InitiatingProcessMD5` | string | 启动事件的进程和 (文件的 MD5) 哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessFileSize` | long | 运行负责事件的进程的文件的大小 |
| `InitiatingProcessVersionInfoCompanyName` | string | 进程版本信息中的公司名称 (负责) 文件 |
| `InitiatingProcessVersionInfoProductName` | string | 进程版本信息中的产品名称 (负责) 文件 |
| `InitiatingProcessVersionInfoProductVersion` | string | 进程版本信息中的产品版本 (负责) 文件 |
| `InitiatingProcessVersionInfoInternalFileName` | string | 进程版本信息中的内部文件名 (负责) 文件的内部文件名 |
| `InitiatingProcessVersionInfoOriginalFileName` | string | 进程版本信息的原始文件名 (负责) 文件 |
| `InitiatingProcessVersionInfoFileDescription` | string | 负责事件的进程版本信息 (映像) 说明 |
| `InitiatingProcessId` | int | 进程 ID (PID) 启动事件的进程的 PID |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动事件的过程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件 (进程) 文件的文件夹 |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentId` | int | 进程 ID (PID) 生成负责事件的进程的父进程的 PID |
| `InitiatingProcessParentCreationTime` | datetime | 启动负责事件的进程的父级的日期和时间 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessAccountUpn` | string | 用户主体 (UPN) 负责事件的进程的帐户的名称 |
| `InitiatingProcessAccountObjectId` | string | Azure AD事件的进程的用户帐户的对象 ID |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的过程的完整性级别。 Windows根据某些特征（例如是否从 Internet 下载中启动）为进程分配完整性级别。 这些完整性级别影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |
| `AdditionalFields` | string | 有关 JSON 数组格式的事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
