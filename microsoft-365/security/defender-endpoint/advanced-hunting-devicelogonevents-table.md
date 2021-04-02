---
title: 高级搜寻架构中的 DeviceLogonEvents 表
description: 了解高级搜寻架构的 DeviceLogonEvents 表中的身份验证或登录事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， devicelogonevents， 身份验证， 登录， 登录， 登录， LogonEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c270f54c856c1ed504533c826ca884786c784549
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499155"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高级 `DeviceLogonEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关用户登录和其他身份验证事件的信息。 使用此参考来构建从该表返回信息的查询。

> [!NOTE]
> DeviceLogonEvents 集合在 Windows 7 或 Windows Server 2008 R2 上不受支持。
> 我们建议升级到 Windows 10 或 Windows Server 2019，以获得最佳的用户登录活动可见性。

有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `ActionType` | string |触发事件的活动类型 |
| `AccountDomain` | string | 帐户的域 |
| `AccountName` | string | 帐户的用户名 |
| `AccountSid` | string | 帐户 (SID) 安全标识符 |
| `LogonType` | string | 登录会话的类型，特别是：<br><br> - **交互式** - 用户使用本地键盘和屏幕与设备进行物理交互<br><br> - **远程交互式 (RDP)** 登录 - 用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与设备远程交互<br><br> - **网络** - 使用 PsExec 访问设备或访问设备共享资源（如打印机和共享文件夹）时启动的会话<br><br> - **Batch** - 由计划任务启动的会话<br><br> - **服务** - 服务启动时启动的会话<br> |
| `LogonId` | string | 登录会话的标识符。 此标识符仅在重新启动之间在同一设备上是唯一的 |
| `RemoteDeviceName` | string | 在受影响的设备上执行远程操作的设备的名称。 根据报告的事件，此名称可以是完全限定的域名 (FQDN) 、NetBIOS 名称或主机名（不含域信息） |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `RemoteIPType` | string | IP 地址的类型，例如 Public、Private、Reserved、Loopback、Teredo、FourToSixMapping 和 Broadcast |
| `RemotePort` | int | 连接到的远程设备的 TCP 端口 |
| `AdditionalFields` | string | 有关 JSON 数组格式的事件的其他信息 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的过程的完整性级别。 Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。 这些完整性级别影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升 |
| `InitiatingProcessSHA1` | string | 启动事件 (映像) 的 SHA-1 |
| `InitiatingProcessSHA256` | string | 启动事件 (映像文件) SHA-256。 通常不填充此字段 -使用 SHA1 列（如果可用） |
| `InitiatingProcessMD5` | string | 启动事件的进程 (MD5) 文件哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 进程 ID (PID) 启动事件的过程的 PID |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动事件的过程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件 (进程) 文件的文件夹 |
| `InitiatingProcessParentId` | int | 进程 ID (PID) 生成负责事件的进程的父进程的 PID |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 启动负责事件的进程的父级的日期和时间 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |
| `IsLocalAdmin` | boolean | 用于指示用户是否是设备的本地管理员的布尔指示器 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
