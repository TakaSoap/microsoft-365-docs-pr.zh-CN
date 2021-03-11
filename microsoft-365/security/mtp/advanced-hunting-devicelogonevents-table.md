---
title: 高级搜寻架构中的 DeviceLogonEvents 表
description: 了解高级搜寻架构的 DeviceLogonEvents 表中的身份验证或登录事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， logonevents， DeviceLogonEvents， 身份验证， 登录， 登录
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
ms.openlocfilehash: 4b47d27855876eaec8512ecaa060875ad8d52a80
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712434"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender



高级 `DeviceLogonEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关设备上用户登录和其他身份验证事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构引用。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string |触发事件的活动类型 |
| `AccountDomain` | string | 帐户的域 |
| `AccountName` | string | 帐户的用户名 |
| `AccountSid` | string | 帐户 (SID) 安全标识符 |
| `Protocol` | string | 通信期间使用的协议 |
| `FailureReason` | string | 说明所记录操作失败的原因的信息 |
| `LogonType` | string | 登录会话的类型，具体而言：<br><br> - **交互** - 用户使用本地键盘和屏幕与计算机进行物理交互<br><br> - **远程交互式 (RDP)** 登录 - 用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与计算机进行远程交互<br><br> - **网络** - 使用 PsExec 访问计算机或访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话<br><br> - **批处理** - 由计划任务启动的会话<br><br> - **服务** - 服务启动时启动的会话<br> |
| `LogonId` | string | 登录会话的标识符。 此标识符仅在重新启动之间在同一计算机上是唯一的 |
| `RemoteDeviceName` | string | 在受影响的计算机上执行远程操作计算机的名称。 根据报告的事件，此名称可以是完全限定的域名 (FQDN) 、NetBIOS 名称或没有域信息的主机名 |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemoteIPType` | string | IP 地址类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `RemotePort` | int | 连接到的远程设备的 TCP 端口 |
| `AdditionalFields` | string | 有关 JSON 数组格式的事件的其他信息 |
| `InitiatingProcessFileSize` | long | 运行负责事件的进程的文件的大小 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessAccountUpn` | string | 运行 (进程的帐户) UPN 帐户的用户主体名称 |
| ` InitiatingProcessAccountObjectId` | string | 运行负责事件的进程的用户帐户的 Azure AD 对象 ID |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的过程的完整性级别。 Windows 根据某些特征（例如是否从 Internet 下载启动）为进程分配完整性级别。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动事件的进程 |
| `InitiatingProcessSHA1` | string | 启动事件 (映像) 的 SHA-1 |
| `InitiatingProcessSHA256` | string | 进程 SHA-256 (启动) 映像文件。 此字段通常不填充 - 可用时使用 SHA1 列 |
| `InitiatingProcessMD5` | string | 启动事件 (映像) 的 MD5 哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 进程 ID (PID) 启动事件的进程的 PID |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动事件过程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动 (文件) 进程的文件夹 |
| `InitiatingProcessParentId` | int | 生成 () 的父进程的 PID 进程 ID |
| `InitiatingProcessParentFileName` | string | 生成负责该事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 启动负责事件的进程的父级的日期和时间 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，必须将此列与 DeviceName 和时间戳列结合使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |
| `IsLocalAdmin` | boolean | 指示用户是否是计算机上本地管理员的布尔指示器 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
