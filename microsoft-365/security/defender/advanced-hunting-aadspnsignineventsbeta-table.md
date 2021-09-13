---
title: 高级搜寻架构中的 AADSpnSignInEventsBeta 表
description: 了解与高级搜寻架构Azure Active Directory服务主体和托管标识登录事件表关联的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， AlertInfo， 警报， 实体， 证据， 文件， IP 地址， 设备， 计算机， 用户， 帐户， 标识， AAD
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
ms.openlocfilehash: a148e2fb1cc0e8fb88797b44ee4d08745728aa34
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196001"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**适用于：**
- Microsoft 365 Defender

> [!IMPORTANT]
> 该表当前处于 beta 版本，并短期提供，以便你可以通过 Azure Active Directory (AAD) 服务主体和托管身份登录事件进行 `AADSpnSignInEventsBeta` 搜寻。 我们最终将所有登录架构信息移动到 `IdentityLogonEvents` 表中。

高级 `AADSpnSignInEventsBeta` 搜寻架构中的表包含有关Azure Active Directory主体和托管标识登录的信息。可以在登录活动报表 -预览 中了解有关不同类型的Azure Active Directory[的详细信息](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。

<br>

****

|列名称|数据类型|说明|
|---|---|---|
|`Timestamp`|datetime|生成记录的日期和时间|
|`Application`|string|执行录制的操作的应用程序|
|`ApplicationId`|字符串|应用程序的唯一标识符|
|`IsManagedIdentity`|boolean|指示登录是否由托管标识启动|
|`ErrorCode`|int|包含登录错误时的错误代码。 若要查找特定错误代码的说明，请访问 <https://aka.ms/AADsigninsErrorCodes> 。|
|`CorrelationId`|字符串|登录事件的唯一标识符|
|`ServicePrincipalName`|字符串|启动登录的服务主体的名称|
|`ServicePrincipalId`|字符串|启动登录的服务主体的唯一标识符|
|`ResourceDisplayName`|字符串|访问的资源的显示名称|
|`ResourceId`|字符串|访问的资源的唯一标识符|
|`ResourceTenantId`|字符串|访问的资源的租户的唯一标识符|
|`IPAddress`|字符串|分配给终结点的 IP 地址，在相关的网络通信期间使用|
|`Country`|字符串|指示客户端 IP 地址已异地地理位置的两个字母的代码|
|`State`|字符串|登录发生的位置（如果可用）|
|`City`|字符串|帐户用户所在的城市|
|`Latitude`|字符串|登录位置的北向南部坐标|
|`Longitude`|字符串|登录位置的从西到西坐标|
|`RequestId`|字符串|请求的唯一标识符|
|`ReportId`|字符串|事件的唯一标识符|
||||

## <a name="related-articles"></a>相关文章

- [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
- [高级搜寻概述](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [了解查询语言](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [了解架构](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
