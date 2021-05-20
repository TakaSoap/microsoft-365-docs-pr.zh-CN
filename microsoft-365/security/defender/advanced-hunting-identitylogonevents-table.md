---
title: 高级搜寻架构中的 IdentityLogonEvents 表
description: 了解 Active Directory 在高级搜寻架构的 IdentityLogonEvents 表中记录的身份验证事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， IdentityLogonEvents， Azure AD， Active Directory， Microsoft Defender for Identity， 标识
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572749"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级搜寻架构中的表包含有关通过 Microsoft Defender 捕获本地 Active Directory 进行身份验证活动的信息，以及 Microsoft Defender 捕获的与 Microsoft 联机服务相关的身份验证 `IdentityLogonEvents` Microsoft Cloud App Security。 [](advanced-hunting-overview.md) 使用此参考来构建从此表返回信息的查询。

>[!TIP]
> 有关表支持的事件类型 () ，请使用安全中心中提供的内置架构 `ActionType` 参考。

>[!NOTE]
>此表Azure Active Directory (Azure AD) 由 云应用安全 跟踪的登录活动，特别是使用 ActiveSync 和其他旧协议的交互式登录和身份验证活动。 此表中不可用的非交互式登出可以在 Azure AD 审核日志。 [详细了解如何连接云应用安全Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `ActionType` | string | 触发事件的活动类型。 有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考 |
| `Application` | 字符串 | 执行录制的操作的应用程序 |
| `LogonType` | 字符串 | 登录会话的类型，特别是：<br><br> - **交互式** - 用户使用本地键盘和屏幕与计算机进行物理交互<br><br> - **远程交互式 (RDP) 登录** - 用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与计算机远程交互<br><br> - **网络** - 使用 PsExec 访问计算机或访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话<br><br> - **Batch** - 由计划任务启动的会话<br><br> - **服务** - 服务启动时启动的会话 |
| `Protocol` | 字符串 | 使用的网络协议 |
| `FailureReason` | 字符串 | 说明所记录操作失败原因的信息 |
| `AccountName` | 字符串 | 帐户的用户名 |
| `AccountDomain` | 字符串 | 帐户的域 |
| `AccountUpn` | 字符串 | 帐户 (UPN) 用户主体名称 |
| `AccountSid` | 字符串 | 帐户 (SID) 安全标识符 |
| `AccountObjectId` | 字符串 | Azure AD 中帐户的唯一标识符 |
| `AccountDisplayName` | 字符串 | 通讯簿中显示的帐户用户的名称。 通常是给定或名字、中间启动和姓氏或姓氏的组合。 |
| `DeviceName` | 字符串 | 设备的完全限定 (FQDN) FQDN |
| `DeviceType` | 字符串 | 设备类型 |
| `OSPlatform` | string | 计算机上运行的操作系统平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `IPAddress` | string | 分配给终结点的 IP 地址，在相关的网络通信期间使用 |
| `Port` | 字符串 | 通信期间使用的 TCP 端口 |
| `DestinationDeviceName` | 字符串 | 运行处理所记录操作的服务器应用程序的设备的名称 |
| `DestinationIPAddress` | 字符串 | 运行处理所记录操作的服务器应用程序的设备的 IP 地址 |
| `DestinationPort` | 字符串 | 相关网络通信的目标端口 |
| `TargetDeviceName` | 字符串 | 已记录 (的) 的设备的完全限定域名和 FQDN |
| `TargetAccountDisplayName` | 字符串 | 已记录操作应用于的帐户的显示名称 |
| `Location` | 字符串 | 与事件关联的城市、国家/地区或其他地理位置 |
| `Isp` | 字符串 | Internet 服务提供商 (ISP) 与终结点 IP 地址关联 |
| `ReportId` | long | 事件的唯一标识符 |
| `AdditionalFields` | 字符串 | 有关实体或事件的其他信息 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)