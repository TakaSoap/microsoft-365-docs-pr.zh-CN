---
title: 高级搜寻架构中的 DeviceRegistryEvents 表
description: 了解可以从高级搜寻架构的 DeviceRegistryEvents 表查询的注册表事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 注册表， 注册表， DeviceRegistryEvents， 密钥， 子项， 值
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
ms.openlocfilehash: 1102f16249841779fd5b7293f89fb0955f14a496
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712398"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `DeviceRegistryEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关注册表项的创建和修改的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构引用。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `RegistryKey` | string | 记录的操作已应用到的注册表项 |
| `RegistryValueType` | string | 记录的操作应用于的注册表值的数据类型（如二进制或字符串） |
| `RegistryValueName` | string | 记录的操作应用于的注册表值的名称 |
| `RegistryValueData` | string | 记录的操作应用于的注册表值的数据 |
| `PreviousRegistryKey` | string | 修改前注册表值的原始注册表项 |
| `PreviousRegistryValueName` | string | 修改前注册表值的原始名称 |
| `PreviousRegistryValueData` | string | 修改前注册表值的原始数据 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessAccountUpn` | string | 运行 (进程的帐户) UPN 帐户的用户主体名称 |
| `InitiatingProcessAccountObjectId` | string | 运行负责事件的进程的用户帐户的 Azure AD 对象 ID |
| `InitiatingProcessSHA1` | string | 启动事件 (映像) 的 SHA-1 |
| `InitiatingProcessSHA256` | string | 进程 SHA-256 (启动) 映像文件。 通常不会填充此字段 — 可用时使用 SHA1 列。 |
| `InitiatingProcessMD5` | string | 启动事件 (映像) 的 MD5 哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessFileSize` | long | 运行负责事件的进程的文件的大小 |
| `InitiatingProcessId` | int | 进程 ID (PID) 启动事件的进程的 PID |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动事件过程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动 (文件) 进程的文件夹 |
| `InitiatingProcessParentId` | int | 生成 () 的父进程的 PID 进程 ID |
| `InitiatingProcessParentFileName` | string | 生成负责该事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 启动负责事件的进程的父级的日期和时间 |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的过程的完整性级别。 Windows 根据某些特征（例如是否从 Internet 下载启动）为进程分配完整性级别。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动事件的进程 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，必须将此列与 DeviceName 和时间戳列结合使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
