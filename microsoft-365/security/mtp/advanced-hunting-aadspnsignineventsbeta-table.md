---
title: 高级搜寻架构中的 AADSpnSignInEventsBeta 表
description: 了解与高级搜寻架构的 Azure Active Directory 服务主体和托管标识登录事件表关联的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， AlertInfo， 警报， 实体， 证据， 文件， IP 地址， 设备， 计算机， 用户， 帐户， 标识， AAD
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928614"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**适用于：**

- Microsoft 365 Defender

>[!IMPORTANT]
> 该表当前处于 beta 版，并短期提供，以便你可以通过 `AADSpnSignInEventsBeta` Azure Active Directory (AAD) 服务主体和托管身份登录事件进行搜寻。 我们最终将所有登录架构信息移动到 `IdentityLogonEvents` 表中。<br><br>
> 可以通过 Azure 安全中心集成的 Microsoft Defender for Endpoint 解决方案访问 Microsoft 365 Defender，但没有 Microsoft Defender for Office、Microsoft Defender for Identity 或 Microsoft Cloud App Security 许可证的客户将无法查看此架构。 



高级 `AADSpnSignInEventsBeta` 搜寻架构中的表包含有关 Azure Active Directory 服务主体和托管标识登录的信息。你可以了解有关 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)登录活动报告中不同类型的登录的详细信息 - 预览。

使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。





| 列名称     | 数据类型 | 说明   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | 生成记录的日期和时间                                                                                                     |
| `Application`          | string        | 执行录制的操作的应用程序                                                                                                   |
| `ApplicationId`        | string        | 应用程序的唯一标识符                                                                                                           |
| `IsManagedIdentity`    | boolean       | 指示登录是否由托管标识启动                                                                               |
| `ErrorCode`            | int        | 包含登录错误时的错误代码。 若要查找特定错误代码的说明，请访问 <https://aka.ms/AADsigninsErrorCodes> 。 |
| `CorrelationId`        | string        | 登录事件的唯一标识符                                                                                                          |
| `ServicePrincipalName` | string        | 启动登录的服务主体的名称                                                                                        |
| `ServicePrincipalId`   | string        | 启动登录的服务主体的唯一标识符                                                                           |
| `ResourceDisplayName`  | string        | 访问的资源的显示名称                                                                                                           |
| `ResourceId`           | string        | 访问的资源的唯一标识符                                                                                                      |
| `ResourceTenantId`     | string        | 访问的资源的租户的唯一标识符                                                                                        |
| `IPAddress`            | string        | 分配给终结点的 IP 地址，在相关的网络通信期间使用                                                              |
| `CountryCode`          | string        | 指示客户端 IP 地址已异地分配的国家/地区两个字母的代码                                                                |
| `State`                | string        | 登录发生位置的状态（如果可用）                                                                                                  |
| `City`                 | string        | 帐户用户所在的城市                                                                                                          |
| `Latitude`             | string        | 登录位置的北向南坐标                                                                                          |
| `Longitude`            | string        | 登录位置的从上到下坐标                                                                                            |
| `RequestId`            | string        | 请求的唯一标识符                                                                                                                |
|`ReportId` | string | 事件的唯一标识符 | 

 

## <a name="related-articles"></a>相关文章

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [高级搜寻概述](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [了解查询语言](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [了解架构](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

