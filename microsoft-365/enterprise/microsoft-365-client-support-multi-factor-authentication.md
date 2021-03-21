---
title: Microsoft 365 客户端应用支持：多重身份验证
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 本文介绍支持 Microsoft 365 多重身份验证的平台、客户端和 PowerShell 模块。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927553"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 客户端应用支持：多重身份验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

为了提供登录的额外安全级别，客户端可以配置为使用多重身份验证 (MFA) ，它使用用户密码和基于：

- 其拥有中无法轻松复制的一些内容，例如智能手机。
- 用户具有唯一且唯一的一些内容，例如其指纹、面部或其他生物识别属性

了解有关多重 [身份验证的更多信息](/azure/active-directory/authentication/multi-factor-authentication)。

## <a name="supported-clients--platforms"></a>受支持的客户端&平台

以下客户端和平台的最新版本支持多重身份验证。 有关 Microsoft 365 中的平台支持详细信息，请参阅 [Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)的系统要求。
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)