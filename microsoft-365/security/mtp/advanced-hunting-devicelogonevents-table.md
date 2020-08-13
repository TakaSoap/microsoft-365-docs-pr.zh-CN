---
title: 高级搜寻架构中的 DeviceLogonEvents 表
description: 了解高级搜寻架构的 DeviceLogonEvents 表中的身份验证或登录事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、logonevents、DeviceLogonEvents、身份验证、登录、登录
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
ms.openlocfilehash: 0f93199fa23a422e82019730b38fcf407e8503a3
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649411"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**适用于：**
- Microsoft 威胁防护



`DeviceLogonEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关设备上的用户登录和其他身份验证事件的信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string |触发事件的活动类型 |
| `AccountDomain` | string | 帐户的域 |
| `AccountName` | string | 帐户的用户名 |
| `AccountSid` | string | 帐户的安全标识符 (SID)  |
| `LogonType` | string | 登录会话的类型，特别是：<br><br> - **交互式**用户使用本地键盘和屏幕与计算机进行物理交互<br><br> - **远程交互 (RDP) 登录**-用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端远程与计算机交互<br><br> - **网络**-在使用 PsExec 访问计算机时或在访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话<br><br> - 由计划任务启动的**批处理**会话<br><br> - **服务**-服务会话启动时启动<br> |
| `LogonId` | string | 登录会话的标识符。 此标识符仅在重启之间的同一台计算机上是唯一的 |
| `RemoteDeviceName` | string | 在受影响的计算机上执行远程操作的计算机的名称。 根据报告的事件，此名称可以是完全限定的域名 (FQDN) 、NetBIOS 名称或不包含域信息的主机名 |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemoteIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、环回、Teredo、FourToSixMapping 和广播 |
| `RemotePort` | int | 要连接到的远程设备上的 TCP 端口 |
| `AdditionalFields` | string | 有关 JSON 数组格式事件的其他信息 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 运行负责事件的进程的帐户 (SID) 的安全标识符 |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的进程的完整性级别。 Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动该事件的进程 |
| `InitiatingProcessSHA1` | string | 启动事件的过程 (图像文件) 的 SHA-1 |
| `InitiatingProcessSHA256` | string | SHA-256 启动事件的过程 (图像文件) 。 通常不填充此字段—使用 SHA1 列（如果可用） |
| `InitiatingProcessMD5` | string | 启动事件的过程 (映像文件) 的 MD5 哈希值 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 启动事件的进程的进程 ID (PID)  |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动启动事件的进程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件的过程 (图像文件) 的文件夹 |
| `InitiatingProcessParentId` | int | 生成负责事件的进程的父进程 (PID) 的进程 ID |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 负责启动事件的进程的父项的日期和时间 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |
| `IsLocalAdmin` | boolean | 指示用户是否为计算机上的本地管理员的布尔指示符 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识的智能寻线](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
