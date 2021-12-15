---
title: 高级搜寻架构中的 IdentityInfo 表
description: 了解高级搜寻架构的 IdentityInfo 表中的用户帐户信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， AccountInfo， IdentityInfo， 帐户
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
ms.openlocfilehash: b09d1774ab35dbca9119deb98864d6c6f78051a9
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531431"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级 `IdentityInfo` 搜寻[架构中的](advanced-hunting-overview.md)表包含有关从各种服务（包括Azure Active Directory）获取的用户帐户的信息。 使用此参考来构建从此表返回信息的查询。

>[!NOTE]
>此表被重命名为 `AccountInfo` 。 在重命名过程中，门户中保存的所有查询将自动更新。 检查已保存在其他位置的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `AccountObjectId` | `string` | Azure AD |
| `AccountUpn` | `string` | 帐户 (UPN) 的用户主体名称 |
| `OnPremSid` | `string` | 帐户的 SID (本地) 标识符 |
| `CloudSid` | `string` | 帐户的云安全标识符 |
| `GivenName` | `string` | 帐户用户的给定名称或名字 |
| `Surname` | `string` | 帐户用户的姓氏、姓氏 |
| `AccountDisplayName` | `string` | 通讯簿中显示的帐户用户的名称。 通常是给定或名字、中间启动和姓氏或姓氏的组合。 |
| `Department` | `string` | 帐户用户所属的部门的名称 |
| `JobTitle` | `string` | 帐户用户职务 |
| `AccountName` | `string` | 帐户的用户名 |
| `AccountDomain` | `string` | 帐户的域 |
| `EmailAddress` | `string` | 帐户的 SMTP 地址 |
| `SipProxyAddress` | `string` | IP 语音 (VOIP) 会话初始 (SIP) 地址 |
| `City` | `string` | 帐户用户所在的城市 |
| `Country` | `string` | 帐户用户所在的国家/地区 |
| `IsAccountEnabled` | `boolean` | 指示帐户是否已启用 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
