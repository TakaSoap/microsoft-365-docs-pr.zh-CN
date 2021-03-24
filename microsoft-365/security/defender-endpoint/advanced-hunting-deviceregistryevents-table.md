---
title: 高级搜寻架构中的 DeviceRegistryEvents 表
description: 了解可以从高级搜寻架构的 DeviceRegistryEvents 表查询的注册表事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， deviceregistryevents， 注册表， 键， 子项， 值， RegistryEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 39ea04e2faa43d230ecdc281967b6a9e8f8c9abe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056146"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高级 `DeviceRegistryEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关创建和修改注册表项的信息。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `ActionType` | string | 触发事件的活动类型 |
| `RegistryKey` | string | 已记录操作所应用到的注册表项 |
| `RegistryValueType` | string | 已记录操作所应用到的注册表值的数据类型（如二进制或字符串） |
| `RegistryValueName` | string | 已记录操作所应用到的注册表值的名称 |
| `RegistryValueData` | string | 已记录操作应用于的注册表值的数据 |
| `PreviousRegistryValueName` | string | 修改前注册表值的原始名称 |
| `PreviousRegistryValueData` | string | 修改前注册表值的原始数据 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 安全 (SID) 运行负责事件的进程的帐户的 SID 标识符 |
| `InitiatingProcessSHA1` | string | 启动事件 (映像) 的 SHA-1 |
| `InitiatingProcessMD5` | string | 启动事件的进程 (MD5) 文件哈希 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 进程 ID (PID) 启动事件的过程的 PID |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动事件的过程的日期和时间 |
| `InitiatingProcessFolderPath` | string | 包含启动事件 (进程) 文件的文件夹 |
| `InitiatingProcessParentId` | int | 进程 ID (PID) 生成负责事件的进程的父进程的 PID |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 启动负责事件的进程的父级的日期和时间 |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的过程的完整性级别。 Windows 根据某些特征（例如是否从 Internet 下载启动）将完整性级别分配给进程。 这些完整性级别影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 启动事件的进程应用的特权提升 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
