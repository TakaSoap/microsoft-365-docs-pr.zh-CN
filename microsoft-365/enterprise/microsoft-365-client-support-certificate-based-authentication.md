---
title: Microsoft 365客户端应用支持：基于证书的身份验证
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 本文详细介绍了如何Microsoft 365基于证书的身份验证提供客户端应用支持。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81643c6f3b693fe447b29ecc6dc5d11e65da0533
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195361"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365客户端应用支持：基于证书的身份验证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

新式验证是一个综合术语，用于组合身份验证和授权方法。 这些方法包括：

- **身份验证方法**：多重身份验证;基于客户端证书的身份验证。
- **授权方法**：Microsoft 的 Open Authorization (OAuth) 。

使用身份验证库启用新式验证，如 Active Directory 身份验证库 (ADAL) 或 Microsoft 身份验证库 (MSAL) 。 新式验证是客户端用于验证和授权访问 Microsoft 365资源。 新式验证使用 OAuth，并提供一种安全机制，使客户端无需访问Microsoft 365即可访问服务。 登录时，用户直接使用 Azure Active Directory进行身份验证，并接收访问/刷新令牌对。 访问令牌向客户端授予对租户中相应资源Microsoft 365权限。 刷新令牌用于在当前访问令牌过期时获取新的访问令牌或刷新令牌对。

新式身份验证支持不同的身份验证机制，如基于证书的身份验证。 Windows、Android 或 iOS 设备上的客户端可以使用基于证书的身份验证 (CBA) 使用设备上的客户端证书Azure Active Directory向 Azure Active Directory 进行身份验证。 证书不是典型的用户名/密码，而是用于从用户获取访问/刷新Azure Active Directory。

详细了解基于 [证书的身份验证](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>受支持的客户端&平台

在客户端 (中登录 Azure Active Directory 帐户时，以下客户端和平台的最新版本支持基于证书的身份验证) 。 有关应用程序平台支持Microsoft 365，请参阅 system [requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

> [!NOTE]
> iOS 和 Android 的边缘支持帐户添加流期间基于证书的身份验证。 对通常为 Intranet 网站的网站执行身份验证时，iOS 和 Android 边缘不支持基于证书的身份验证。 <br><br>  在此方案中，用户导航到通常 (Intranet) 网站需要用户通过证书进行身份验证的网站。 这完全不涉及新式验证，也不利用 Microsoft 身份验证库。 这是由于 iOS 的限制：iOS 阻止第三方应用访问存储证书的系统密钥链 (只有 Apple 应用和 [Safari Webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 控制器可以访问系统密钥链) 。 <br><br> 由于 Edge 依赖 [WebKit](https://developer.apple.com/documentation/webkit) 框架来呈现网站，因此 Edge 无法访问系统密钥链，也无法向用户显示证书选择。 遗憾的是，这是由 Apple 的体系结构设计的。

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active DirectoryPowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
