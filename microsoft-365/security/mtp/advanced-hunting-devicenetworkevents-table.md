---
title: 高级搜寻架构中的 DeviceNetworkEvents 表
description: 了解可以从高级搜寻架构的 DeviceNetworkEvents 表中查询的网络连接事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、devicenetworkevents、NetworkCommunicationEvents、网络连接、远程 ip、本地 ip
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
ms.openlocfilehash: 2e7999fef43adb372947d9edf92b84ac67f347fe
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235001"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

**适用于：**
- Microsoft 威胁防护



`DeviceNetworkEvents` [高级搜寻](advanced-hunting-overview.md)架构中的表包含有关网络连接和相关事件的信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string | 触发事件的活动类型 |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemotePort` | int | 要连接到的远程设备上的 TCP 端口 |
| `RemoteUrl` | string | 连接到的 URL 或完全限定域名 (FQDN) |
| `LocalIP` | string | 分配给在通信期间使用的本地计算机的 IP 地址 |
| `LocalPort` | int | 通信期间使用的本地计算机上的 TCP 端口 |
| `Protocol` | string | 使用的 IP 协议，无论是 TCP 还是 UDP |
| `LocalIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播 |
| `RemoteIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播 |
| `InitiatingProcessSHA1` | string | 启动事件的过程（图像文件）的 SHA-1 |
| `InitiatingProcessMD5` | string | 启动事件的进程（图像文件）的 MD5 哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 启动事件的进程的进程 ID （PID） |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动启动事件的进程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件的进程（图像文件）的文件夹 |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentId` | int | 生成负责事件的进程的父进程的进程 ID （PID） |
| `InitiatingProcessParentCreationTime` | datetime | 负责启动事件的进程的父项的日期和时间 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 运行负责事件的进程的帐户的安全标识符（SID） |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的进程的完整性级别。 Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在应用于启动事件的进程的用户访问控制（UAC）权限提升的标记类型 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
