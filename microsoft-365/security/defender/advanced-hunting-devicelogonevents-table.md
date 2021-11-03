---
title: 高级搜寻架构中的 DeviceLogonEvents 表
description: 了解高级搜寻架构的 DeviceLogonEvents 表中的身份验证或登录事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， logonevents， DeviceLogonEvents， 身份验证， 登录， 登录
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
ms.openlocfilehash: b3c878c40c742c22401b9180d202da472d9e2f35
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60671357"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高级 `DeviceLogonEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关设备上用户登录和其他身份验证事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持 (事件) 类型的详细信息，请使用安全中心中提供的内置 `ActionType` 架构参考。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string |触发事件的活动类型 |
| `LogonType` | string | 登录会话的类型，特别是：<br><br> - **交互式** - 用户使用本地键盘和屏幕与计算机进行物理交互<br><br> - **远程交互式 (RDP)** 登录 - 用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与计算机远程交互<br><br> - **网络** - 使用 PsExec 访问计算机或访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话<br><br> - **Batch** - 由计划任务启动的会话<br><br> - **服务** - 服务启动时启动的会话<br> |
| `AccountDomain` | string | 帐户的域 |
| `AccountName` | string | 帐户的用户名 |
| `AccountSid` | string | 帐户 (SID) 安全标识符 |
| `Protocol` | string | 通信期间使用的协议 |
| `FailureReason` | string | 说明所记录操作失败原因的信息 |
| `IsLocalAdmin` | boolean | 用于指示用户是否是计算机上本地管理员的布尔指示器 |
| `LogonId` | string | 登录会话的标识符。 此标识符仅在重新启动之间的同一计算机上是唯一的 |
| `RemoteDeviceName` | string | 在受影响的计算机上执行远程操作计算机的名称。 根据报告的事件，此名称可以是完全限定的域名 (FQDN) 、NetBIOS 名称或主机名（不含域信息） |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemoteIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `RemotePort` | int | 连接到的远程设备的 TCP 端口 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessAccountUpn` | string | 用户主体 (UPN) 负责事件的进程的帐户的名称 |
| ` InitiatingProcessAccountObjectId` | string | Azure AD事件的进程的用户帐户的对象 ID |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的过程的完整性级别。 Windows根据某些特征（例如是否从 Internet 下载中启动）为进程分配完整性级别。 这些完整性级别影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升 |
| `InitiatingProcessSHA1` | string | 启动事件 (映像文件) SHA-1 |
| `InitiatingProcessSHA256` | string | 启动事件 (映像文件) SHA-256。 通常不填充此字段 -使用 SHA1 列（如果可用） |
| `InitiatingProcessMD5` | string | 启动事件的进程 (MD5) 文件哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessFileSize` | long | 运行负责事件的进程的文件的大小 |
| `InitiatingProcessVersionInfoCompanyName` | string | 进程版本信息中的公司名称 (负责) 文件 |
| `InitiatingProcessVersionInfoProductName` | string | 进程版本信息中的产品名称 (负责) 文件 |
| `InitiatingProcessVersionInfoProductVersion` | string | 进程版本信息中的产品版本 (负责) 文件 |
| `InitiatingProcessVersionInfoInternalFileName` | string | 进程版本信息中的内部文件名 (负责) 文件 |
| `InitiatingProcessVersionInfoOriginalFileName` | string | 进程版本信息的原始文件名 (负责) 文件 |
| `InitiatingProcessVersionInfoFileDescription` | string | 负责事件的进程版本信息 (映像) 说明 |
| `InitiatingProcessId` | int | 进程 ID (PID) 启动事件的进程的 PID |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动事件的过程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件 (进程) 文件的文件夹 |
| `InitiatingProcessParentId` | int | 进程 ID (PID) 生成负责事件的进程的父进程的 PID |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 启动负责事件的进程的父级的日期和时间 |
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
