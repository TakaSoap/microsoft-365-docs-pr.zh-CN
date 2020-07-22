---
title: 高级搜寻架构中的 IdentityLogonEvents 表
description: 了解高级搜寻架构的 IdentityLogonEvents 表中的 Active Directory 记录的身份验证事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、标识
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
ms.openlocfilehash: 19437caf4f3b0dcb6eb6ccad81d1ed3917df7996
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204907"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**适用于：**
- Microsoft 威胁防护

`IdentityLogonEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含通过 Azure ATP 和与 Microsoft 云应用安全捕获的 microsoft online 服务捕获的身份验证活动捕获的身份验证活动的相关信息。 使用此参考来构建从此表返回信息的查询。

>[!NOTE]
>此表介绍了云应用安全性跟踪的 Azure Active Directory （AD）登录活动，尤其是使用 ActiveSync 和其他旧协议的交互式登录和身份验证活动。 可以在 Azure AD 审核日志中查看此表中不可用的非交互式登录。 [了解有关将云应用安全连接到 Microsoft 365 的详细信息](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | 字符串 | 触发事件的活动类型 |
| `LogonType` | 字符串 | 登录会话的类型，特别是：<br><br> - **交互式**用户使用本地键盘和屏幕与计算机进行物理交互<br><br> - **远程交互（RDP）登录**-用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与计算机进行远程交互<br><br> - **网络**-在使用 PsExec 访问计算机时或在访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话<br><br> - 由计划任务启动的**批处理**会话<br><br> - **服务**-服务会话启动时启动 |
| `Application` | 字符串 | 执行录制操作的应用程序 |
| `Protocol` | 字符串 | 使用的网络协议 |
| `FailureReason` | 字符串 | 解释录制的操作失败原因的信息 |
| `AccountName` | 字符串 | 帐户的用户名 |
| `AccountDomain` | 字符串 | 帐户的域 |
| `AccountUpn` | 字符串 | 帐户的用户主体名称（UPN） |
| `AccountSid` | 字符串 | 帐户的安全标识符（SID） |
| `AccountObjectId` | 字符串 | Azure AD 中的帐户的唯一标识符 |
| `AccountDisplayName` | 字符串 | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `DeviceName` | 字符串 | 设备的完全限定的域名（FQDN） |
| `DeviceType` | 字符串 | 设备类型 |
| `OSPlatform` | string | 计算机上运行的操作系统平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，并在相关的网络通信过程中使用 |
| `DestinationDeviceName` | 字符串 | 运行处理录制操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | 字符串 | 运行用于处理录制操作的服务器应用程序的设备的 IP 地址 |
| `TargetDeviceName` | 字符串 | 应用录制的操作的设备的完全限定的域名（FQDN） |
| `TargetAccountDisplayName` | 字符串 | 将录制的操作应用于的帐户的显示名称 |
| `Location` | 字符串 | 与事件关联的城市、国家或其他地理位置 |
| `Isp` | 字符串 | 与终结点 IP 地址关联的 Internet 服务提供商（ISP） |
| `ReportId` | long | 事件的唯一标识符 |
| `AdditionalFields` | 字符串 | 有关实体或事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)