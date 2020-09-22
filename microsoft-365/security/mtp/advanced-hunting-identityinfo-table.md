---
title: 高级搜寻架构中的 IdentityInfo 表
description: 了解高级搜寻架构的 IdentityInfo 表中的用户帐户信息
keywords: 高级搜索、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AccountInfo、IdentityInfo、帐户
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
ms.openlocfilehash: 6922f50906013cfbfa3bd63c69fff3e89ed46cd5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196817"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

`IdentityInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关从各种服务（包括 Azure Active Directory）获取的用户帐户的信息。 使用此参考来构建从此表返回信息的查询。

>[!NOTE]
>此表已重命名 `AccountInfo` 。 在重命名过程中，保存在门户中的所有查询都将自动更新。 检查已保存在其他位置的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Azure AD 中的帐户的唯一标识符 |
| `AccountUpn` | string | 帐户的用户主体名称 (UPN)  |
| `OnPremSid` | string | 帐户的本地安全标识符 (SID)  |
| `CloudSid` | string | 帐户的云安全标识符 |
| `GivenName` | string | 帐户用户的指定名称或名字 |
| `Surname` | string | 帐户用户的姓氏、系列名称或姓氏 |
| `AccountDisplayName` | string | 通讯簿中显示的帐户用户的名称。 通常是给定的或名的名称、中间初始名称和姓氏的组合。 |
| `Department` | string | 帐户用户所属部门的名称 |
| `JobTitle` | string | 帐户用户的职务 |
| `AccountName` | string | 帐户的用户名 |
| `AccountDomain` | string | 帐户的域 |
| `EmailAddress` | string | 帐户的 SMTP 地址 |
| `SipProxyAddress` | string | 帐户的 IP 语音 (VOIP) 会话初始协议 (SIP) 地址 |
| `City` | string | 帐户用户所在的城市 |
| `Country` | string | 帐户用户所在的国家/地区 |
| `IsAccountEnabled` | boolean | 指示帐户是否已启用 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
