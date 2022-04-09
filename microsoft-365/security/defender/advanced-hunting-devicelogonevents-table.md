---
title: 高级搜寻架构中的 DeviceLogonEvents 表
description: 了解高级搜寻架构的 DeviceLogonEvents 表中的身份验证或登录事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、Microsoft 365 Defender、microsoft 365、m365、搜索、查询、遥测、架构引用、kusto、表、列、数据类型、说明、logonevents、DeviceLogonEvents、身份验证、登录、登录
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
ms.openlocfilehash: 516b74eb8d1e62194718e0ad3234b3269e07fb83
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731364"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高级`DeviceLogonEvents`[搜寻](advanced-hunting-overview.md)架构中的表包含有关设备上的用户登录和其他身份验证事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持的) 的事件类型 (`ActionType`值的详细信息，请使用Defender for Cloud中提供的内置架构引用。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | 记录事件的日期和时间 |
| `DeviceId` | `string` | 服务中的计算机的唯一标识符 |
| `DeviceName` | `string` | 计算机的完全限定域名 (FQDN) |
| `ActionType` | `string` |触发事件的活动类型 |
| `LogonType` | `string` | 登录会话的类型，具体而言：<br><br> - **交互式** - 用户使用本地键盘和屏幕与计算机进行物理交互<br><br> - **远程交互式 (RDP) 登录** - 用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端远程与计算机交互<br><br> - **网络** - 使用 PsExec 访问计算机或访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话<br><br> - **Batch** - 由计划任务启动的会话<br><br> - **服务** - 服务启动时由服务启动的会话<br> |
| `AccountDomain` | `string` | 帐户的域 |
| `AccountName` | `string` | 帐户的用户名 |
| `AccountSid` | `string` | 帐户的 SID)  (安全标识符 |
| `Protocol` | `string` | 通信期间使用的协议 |
| `FailureReason` | `string` | 解释记录操作失败的原因的信息 |
| `IsLocalAdmin` | `boolean` | 指示用户是否是计算机上的本地管理员的布尔指示器 |
| `LogonId` | `string` | 登录会话的标识符。 此标识符仅在重启之间在同一台计算机上是唯一的 |
| `RemoteDeviceName` | `string` | 在受影响的计算机上执行远程操作的计算机的名称。 根据所报告的事件，此名称可以是完全限定的域名 (FQDN) 、NetBIOS 名称或没有域信息的主机名 |
| `RemoteIP` | `string` | 连接到的 IP 地址 |
| `RemoteIPType` | `string` | IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `RemotePort` | `int` | 正在连接到的远程设备上的 TCP 端口 |
| `InitiatingProcessAccountDomain` | `string` | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | `string` | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | `string` | 运行负责事件的进程的帐户的安全标识符 (SID)  |
| `InitiatingProcessAccountUpn` | `string` | 运行负责事件的进程的帐户的用户主体名称 (UPN)  |
| ` InitiatingProcessAccountObjectId` | `string` | Azure AD运行负责事件的进程的用户帐户的对象 ID |
| `InitiatingProcessIntegrityLevel` | `string` | 启动事件的进程的完整性级别。 Windows根据某些特征（例如从 Internet 下载启动）为进程分配完整性级别。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | `string` | 指示用户访问控制 (UAC 是否存在) 权限提升应用于启动事件的进程的令牌类型 |
| `InitiatingProcessSHA1` | `string` | 启动事件的进程的 SHA-1 (图像文件)  |
| `InitiatingProcessSHA256` | `string` | 启动事件的进程的 SHA-256 (映像文件) 。 此字段通常不会填充 - 可用时使用 SHA1 列 |
| `InitiatingProcessMD5` | `string` | 启动事件的进程的 MD5 哈希 (图像文件)  |
| `InitiatingProcessFileName` | `string` | 启动事件的进程的名称 |
| `InitiatingProcessFileSize` | `long` | 运行负责事件的进程的文件的大小 |
| `InitiatingProcessVersionInfoCompanyName` | `string` | 进程的版本信息中的公司名称 (负责事件的映像文件)  |
| `InitiatingProcessVersionInfoProductName` | `string` | 进程的版本信息中的产品名称 (负责事件的映像文件)  |
| `InitiatingProcessVersionInfoProductVersion` | `string` | 进程的版本信息中的产品版本 (负责事件的映像文件)  |
| `InitiatingProcessVersionInfoInternalFileName` | `string` | 进程的版本信息中的内部文件名 (负责事件的映像文件)  |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | 进程的版本信息中的原始文件名 (负责事件的映像文件)  |
| `InitiatingProcessVersionInfoFileDescription` | `string` | 进程的版本信息的说明 (负责事件的映像文件)  |
| `InitiatingProcessId` | `int` | 启动事件的进程的进程 ID (PID)  |
| `InitiatingProcessCommandLine` | `string` | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | `datetime` | 启动事件的进程的日期和时间 |
| `InitiatingProcessFolderPath` | `string` | 包含启动事件的进程 (图像文件) 的文件夹 |
| `InitiatingProcessParentId` | `int` | 生成负责事件的进程的父进程的进程 ID (PID)  |
| `InitiatingProcessParentFileName` | `string` | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | `datetime` | 负责事件的进程的父级启动的日期和时间 |
| `ReportId` | `long` | 基于重复计数器的事件标识符。 若要标识唯一事件，必须将此列与 DeviceName 和 Timestamp 列结合使用 |
| `AppGuardContainerId` | `string` | Application Guard 用于隔离浏览器活动的虚拟化容器的标识符 |
| `AdditionalFields` | `string` | 有关 JSON 数组格式的事件的其他信息 |

>[!NOTE]
>载入到 Defender for Endpoint 的 Windows 7 或 Windows Server 2008R2 设备上不支持 DeviceLogonEvents 的集合。 我们建议升级到最近的操作系统，以获得用户登录活动的最佳可见性。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
