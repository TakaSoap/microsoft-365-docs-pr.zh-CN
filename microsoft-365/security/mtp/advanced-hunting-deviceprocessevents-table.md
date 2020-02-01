---
title: 高级搜寻架构中的 DeviceProcessEvents 表
description: 了解高级搜寻架构的 DeviceProcessEventstable 中的过程生成或创建事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、processcreationevents、DeviceProcessEvents、进程 id、命令line，DeviceProcessEvents
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 460c1e76020457fb4f640c32df39c09adaaba32a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600399"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceProcessEvents` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关进程创建和相关事件的信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string | 触发事件的活动类型 |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `FolderPath` | string | 包含录制的操作所应用于的文件的文件夹 |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `SHA256` | string | 录制操作所应用到的文件的 SHA-256。 通常不填充此字段—使用 SHA1 列（如果可用）。 |
| `MD5` | string | 将录制的操作应用于的文件的 MD5 哈希值 |
| `ProcessId` | int | 新创建的进程的进程 ID （PID） |
| `ProcessCommandLine` | string | 用于创建新进程的命令行 |
| `ProcessIntegrityLevel` | string | 新创建的进程的完整性级别。 Windows 根据某些特征（如从已下载的 internet 启动）将完整性级别分配给流程。 这些完整性级别会影响对资源的权限 |
| `ProcessTokenElevation` | string | 指示是否存在应用于新创建的进程的用户访问控制（UAC）权限提升的标记类型 |
| `ProcessCreationTime` | datetime | 过程的创建日期和时间 |
| `AccountDomain` | string | 帐户的域 |
| `AccountName` | string | 帐户的用户名 |
| `AccountSid` | string | 帐户的安全标识符（SID） |
| `LogonId` | string | 登录会话的标识符。 此标识符仅在重启之间的同一台计算机上是唯一的 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 运行负责事件的进程的帐户的安全标识符（SID） |
| `InitiatingProcessLogonId` | string | 启动事件的进程的登录会话的标识符。 此标识符仅在重启之间的同一台计算机上是唯一的。 |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的进程的完整性级别。 Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型 |
| `InitiatingProcessSHA1` | string | 启动事件的过程（图像文件）的 SHA-1 |
| `InitiatingProcessSHA256` | string | SHA-256，其中启动了事件的进程（图像文件）。 通常不填充此字段—使用 SHA1 列（如果可用） |
| `InitiatingProcessMD5` | string | 启动事件的进程（图像文件）的 MD5 哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 启动事件的进程的进程 ID （PID） |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动启动事件的进程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件的进程（图像文件）的文件夹 |
| `InitiatingProcessParentId` | int | 生成负责事件的进程的父进程的进程 ID （PID） |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 负责启动事件的进程的父项的日期和时间 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
