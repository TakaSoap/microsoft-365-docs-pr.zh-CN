---
title: Microsoft 365 Defender美国政府客户
description: 了解适用于美国政府Microsoft 365 Defender的要求和功能
keywords: government， gcc， high， requirements， capabilities， defender， Microsoft 365 Defender， xdr， dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3e8f6e523a5483de99beb0af7d01ab96951b7a3e
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374871"
---
# <a name="microsoft-365-defender-for-us-government-customers"></a>Microsoft 365 Defender美国政府客户

**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender在 Azure 美国政府环境中构建的美国政府客户计划使用与 Azure 商业Microsoft 365 Defender相同的基础技术。

此产品/服务GCC、GCC高和 DoD 客户，并且基于与商业版相同的预防、检测、调查和修正。 但是，此产品/服务的功能可用性存在一些差异。

> [!NOTE]
> 如果你是使用GCC应用、Defender for Endpoint 或商业版中 Identity 的 Defender for Identity 的客户，你需要将这些服务转换到 GCC 版本，才有资格使用 Microsoft 365 Defender GCC。

## <a name="licensing-requirements"></a>许可要求

Microsoft 365 Defender美国政府客户需要以下 Microsoft 批量许可产品/服务之一：

### <a name="desktop-licensing"></a>桌面许可

<br />

****

|GCC|GCC 高|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5高GCC|Microsoft 365 G5 for DOD|
|Microsoft 365 G5 安全GCC|Microsoft 365高GCC G5 安全性|Microsoft 365 DOD 的 G5 安全性|
|企业移动性 + 安全性 G5 GCC|企业移动性 + 安全性 E5 for GCC High|企业移动性 + 安全性 E5 for DOD|
|Office 365 G5 GCC|Office 365 E5高GCC|Office 365 E5 DOD|
|Microsoft Defender for Cloud Apps GCC|Microsoft Defender for Cloud Apps for GCC High|Microsoft Defender for Cloud Apps for DOD|
|Microsoft Defender for Endpoint - GCC|Microsoft Defender for Endpoint for GCC High|Microsoft Defender for Endpoint for DOD|
|Microsoft Defender for Identity - GCC|Microsoft Defender for Identity for GCC High|Microsoft Defender for Identity for DOD|
|Microsoft Defender for Office 365 (计划 2) GCC|Microsoft Defender for Office 365 (Plan 2) for GCC High|Microsoft Defender for Office 365 (Plan 2) for DOD|
|Windows 10 企业版 E5 GCC|Windows 10 企业版 E5 for GCC High|Windows 10 企业版 E5 for DOD|
|

### <a name="server-licensing"></a>服务器许可

<br />

****

|GCC|GCC 高|DoD|
|---|---|---|
|Microsoft Defender for Endpoint Server GCC|Microsoft Defender for Endpoint Server for GCC High|Microsoft Defender for Endpoint Server for DOD|
|Microsoft Defender for servers|Microsoft Defender for servers - 政府|Microsoft Defender for servers - 政府|
|

## <a name="portal-urls"></a>门户 URL

以下是美国政府客户Microsoft 365 Defender门户 URL：

<br />

****

|客户类型|门户 URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC 高|即将推出|
|DoD|即将推出|
|
> [!NOTE]
> 如果你是客户GCC从 Microsoft Defender for Endpoint 商业移动到 GCC，请使用 访问 Microsoft Defender for https://transition.security.microsoft.com Endpoint 商业数据。

## <a name="api"></a>API

你需要使用以下 URI，而不是我们的 [API](api-overview.md)文档中列出的公共 URI：

<br />

****

|终结点类型|GCC|GCC High & DoD|
|---|---|---|
|登录|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Microsoft 365 Defender API|`https://api-gcc.security.microsoft.us`|`https://api-gov.security.microsoft.us`|
|

## <a name="feature-parity-with-commercial"></a>功能与商业奇偶校验

Microsoft 365 Defender美国政府客户的服务与商业产品/服务完全对等。 尽管我们的目标是向美国政府客户提供所有商业特性和功能，但我们要重点说明一些功能。

这些就是已知差距：

<br />

****

|功能名称|GCC|GCC 高|DoD|
|---|:---:|:---:|:---:|
|集成：Microsoft Sentinel (事件&原始数据) |![是](../defender-endpoint/images/svg/check-yes.svg)|![是](../defender-endpoint/images/svg/check-yes.svg) 在个人预览版中|![是](../defender-endpoint/images/svg/check-yes.svg) 在个人预览版中|
|Microsoft 威胁专家|![否](../defender-endpoint/images/svg/check-no.svg) 工程积压工作|![否](../defender-endpoint/images/svg/check-no.svg) 工程积压工作|![否](../defender-endpoint/images/svg/check-no.svg) 工程积压工作|

## <a name="more-details"></a>更多详细信息

有关详细信息，请参阅各个工作负载美国 Gov 页面：
- [Microsoft Defender for Cloud Apps](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description)。
- [Microsoft Defender for Identity](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description)。
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/gov)。
