---
title: 高级搜寻架构中的 DeviceFileEvents 表
description: 了解高级搜寻架构的 DeviceFileEvents 表中与文件相关的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、filecreationevents、DeviceFileEvents、md5、md5
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
ms.openlocfilehash: e4534967ca6e9563f802cdf49385b46790d56932
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198185"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

`DeviceFileEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关文件创建、修改和其他文件系统事件的信息。 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `FolderPath` | string | 包含录制的操作所应用于的文件的文件夹 |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `SHA256` | string | 录制操作所应用到的文件的 SHA-256。 通常不会填充此字段 — 可用时使用 SHA1 列。 |
| `MD5` | string | 将录制的操作应用于的文件的 MD5 哈希值 |
| `FileOriginUrl` | string | 从中下载文件的 URL |
| `FileOriginReferrerUrl` | string | 链接到下载文件的网页的 URL |
| `FileOriginIP` | string | 从中下载文件的 IP 地址 |
| `InitiatingProcessAccountDomain` | string | 运行负责事件的进程的帐户的域 |
| `InitiatingProcessAccountName` | string | 运行负责事件的进程的帐户的用户名 |
| `InitiatingProcessAccountSid` | string | 运行负责事件的进程的帐户 (SID) 的安全标识符 |
| `InitiatingProcessMD5` | string | 启动事件的过程 (映像文件) 的 MD5 哈希值 |
| `InitiatingProcessSHA1` | string | 启动事件的过程 (图像文件) 的 SHA-1 |
| `InitiatingProcessSHA256` | string | SHA-256 启动事件的过程 (图像文件) 。 通常不会填充此字段 — 可用时使用 SHA1 列。 |
| `InitiatingProcessFolderPath` | string | 包含启动事件的过程 (图像文件) 的文件夹 |
| `InitiatingProcessFileName` | string | 启动事件的进程的名称 |
| `InitiatingProcessId` | int | 启动事件的进程的进程 ID (PID)  |
| `InitiatingProcessCommandLine` | string | 用于运行启动事件的进程的命令行 |
| `InitiatingProcessCreationTime` | datetime | 启动启动事件的进程的日期和时间 |
| `InitiatingProcessIntegrityLevel` | string | 启动事件的进程的完整性级别。 Windows 根据某些特征（如从 internet 下载启动）将完整性级别分配给流程。 这些完整性级别会影响对资源的权限 |
| `InitiatingProcessTokenElevation` | string | 指示是否存在用户访问控制的令牌类型 (UAC) 权限提升应用于启动该事件的进程 |
| `InitiatingProcessParentId` | int | 生成负责事件的进程的父进程 (PID) 的进程 ID |
| `InitiatingProcessParentFileName` | string | 生成负责事件的进程的父进程的名称 |
| `InitiatingProcessParentCreationTime` | datetime | 负责启动事件的进程的父项的日期和时间 |
| `RequestProtocol` | string | 用于启动活动的网络协议（如果适用）：未知、本地、SMB 或 NFS |
| `ShareName` | string | 包含该文件的共享文件夹的名称 |
| `RequestSourceIP` | string | 启动活动的远程设备的 IPv4 或 IPv6 地址 |
| `RequestSourcePort` | string | 启动活动的远程设备上的源端口 |
| `RequestAccountName` | string | 远程启动活动时使用的帐户的用户名 |
| `RequestAccountDomain` | string | 用于远程启动活动的帐户的域 |
| `RequestAccountSid` | string | 用于远程启动活动的帐户 (SID) 的安全标识符 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用 |
| `AppGuardContainerId` | string | 应用程序防护用于隔离浏览器活动的虚拟化容器的标识符 |
| `SensitivityLabel` | string | 应用于电子邮件、文件或其他内容的标签以对其进行分类以实现信息保护 |
| `SensitivitySubLabel` | string | 选项应用于电子邮件、文件或其他内容以对其进行分类以进行信息保护;敏感度子标签按敏感度标签分组，但单独处理 |
| `IsAzureInfoProtectionApplied` | boolean | 指示文件是否由 Azure 信息保护进行加密 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
