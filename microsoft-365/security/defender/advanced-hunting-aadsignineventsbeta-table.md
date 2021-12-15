---
title: 高级搜寻架构中的 AADSignInEventsBeta 表
description: 了解Azure Active Directory搜寻架构的登录事件表
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， 文件， IP 地址， 设备， 计算机， 用户， 帐户， 标识， AAD
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
ms.openlocfilehash: 5afa98c4455387be673186854528dcd776e151f2
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531845"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 该表当前处于 beta 版本，并短期提供，以便你可以Azure Active Directory (AAD) `AADSignInEventsBeta` 登录事件。 客户需要拥有一Azure Active Directory Premium P2许可证才能收集和查看此表的活动。 所有登录架构信息最终将移动到 `IdentityLogonEvents` 表中。

高级 `AADSignInEventsBeta` 搜寻架构中的表包含有关Azure Active Directory和非交互式登录的信息。了解有关登录活动报告中Azure Active Directory[登录的详细信息 - 预览](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。 

使用此参考来构建从该表返回信息的查询。 有关高级搜寻架构中其他表的信息，请参阅高级 [搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。

<br>

****

|列名称|数据类型|说明|
|---|---|---|
|`Timestamp`|`datetime`|生成记录的日期和时间|
|`Application`|`string`|执行录制的操作的应用程序|
|`ApplicationId`|`string`|应用程序的唯一标识符|
|`LogonType`|`string`|登录会话类型、交互式、远程交互式 (RDP) 、网络、批处理和服务|
|`ErrorCode`|`int`|包含登录错误时的错误代码。 若要查找特定错误代码的说明，请访问 <https://aka.ms/AADsigninsErrorCodes> 。|
|`CorrelationId`|`string`|登录事件的唯一标识符|
|`SessionId`|`string`|在访问或会话期间由网站服务器分配给用户的唯一号码|
|`AccountDisplayName`|`string`|通讯簿中显示的帐户用户的名称。 通常是给定或名字、中间名首字母和姓氏或姓氏的组合。|
|`AccountObjectId`|`string`|Azure AD|
|`AccountUpn`|`string`|帐户 (UPN) 的用户主体名称|
|`IsExternalUser`|`int`|指示登录的用户是否位于外部。 可能的值：-1 (未) ，0 (外部) ，1 (外部) 。|
|`IsGuestUser`|`boolean`|指示登录的用户是否是租户中的来宾|
|`AlternateSignInName`|`string`|本地用户主体名称 (UPN) 登录用户的 UPN Azure AD|
|`LastPasswordChangeTimestamp`|`datetime`|上次登录的用户更改其密码的日期和时间|
|`ResourceDisplayName`|`string`|访问的资源的显示名称|
|`ResourceId`|`string`|访问的资源的唯一标识符|
|`ResourceTenantId`|`string`|访问的资源的租户的唯一标识符|
|`DeviceName`|`string`|计算机的完全限定域名 (FQDN)|
|`AadDeviceId`|`string`|设备上设备的唯一Azure AD|
|`OSPlatform`|`string`|计算机上运行的操作系统平台。 指示特定操作系统，包括同一系列中的变体，如 Windows 11、Windows 10 和 Windows 7。|
|`DeviceTrustType`|`string`|指示登录设备的信任类型。 仅适用于托管设备方案。 可能的值是 Workplace、AzureAd 和 ServerAd。|
|`IsManaged`|`int`|指示启动登录的设备是否是托管设备 (1) 0 (托管) |
|`IsCompliant`|`int`|指示启动登录的设备是否符合 (1) 0 () |
|`AuthenticationProcessingDetails`|`string`|有关身份验证处理器的详细信息|
|`AuthenticationRequirement`|`string`|登录所需的身份验证类型。 可能的值：需要 multiFactorAuthentication (MFA，) singleFactorAuthentication (不需要 MFA) 。|
|`TokenIssuerType`|`int`|指示令牌颁发者是否Azure Active Directory (0) Active Directory 联合身份验证服务 (1) |
|`RiskLevelAggregated`|`int`|登录期间聚合的风险级别。 可能的值：0 (未设置) 、1 (无) 、10 (低) 、50 (medium) 或 100 (high) 。|
|`RiskDetails`|`int`|有关登录用户的风险状态的详细信息|
|`RiskState`|`int`|指示有风险的用户状态。 可能的值：0 (无) 、1 (确认安全) 、2 (已修复) 、3 (已消除) 、4 (存在风险) 或 5 (确认遭到入侵) 。|
|`UserAgent`|`string`|来自 Web 浏览器或其他客户端应用程序的用户代理信息|
|`ClientAppUsed`|`string`|指示使用的客户端应用|
|`Browser`|`string`|有关用于登录的浏览器版本的详细信息|
|`ConditionalAccessPolicies`|`string`|应用于登录事件的条件访问策略的详细信息|
|`ConditionalAccessStatus`|`int`|应用于登录的条件访问策略的状态。 可能的值是 0 (应用) ，1 (尝试应用策略失败) ，或 2 (策略未) 。|
|`IPAddress`|`string`|分配给终结点的 IP 地址，在相关的网络通信期间使用|
|`Country`|`string`|指示客户端 IP 地址已异地地理位置的两个字母的代码|
|`State`|`string`|登录发生的位置（如果可用）|
|`City`|`string`|帐户用户所在的城市|
|`Latitude`|`string`|登录位置的北向南部坐标|
|`Longitude`|`string`|登录位置的从西到西坐标|
|`NetworkLocationDetails`|`string`|登录事件的身份验证处理器的网络位置详细信息|
|`RequestId`|`string`|请求的唯一标识符|
|`ReportId`|`string`|事件的唯一标识符|

## <a name="related-articles"></a>相关文章

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [高级搜寻概述](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [了解查询语言](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [了解架构](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
