---
title: Microsoft 365 客户端应用支持：基于证书的身份验证
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
description: 本文查找有关 Microsoft 365 客户端应用对基于证书的身份验证的支持的详细信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097254"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 客户端应用支持：基于证书的身份验证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

新式验证是一个综合身份验证和授权方法的术语。 具体包括：

- **身份验证方法**：多重身份验证;基于客户端证书的身份验证。
- **授权方法**：Microsoft 的 Open Authorization (OAuth) 。

使用身份验证库（如 Active Directory 身份验证库 (ADAL) 或 Microsoft 身份验证库 (MSAL) ）启用新式身份验证。 新式身份验证是客户端用于对 Microsoft 365 资源进行身份验证和授权访问的客户端。 新式身份验证利用 OAuth，为客户端提供了访问 Microsoft 365 服务的安全机制，而无需访问用户凭据。 登录时，用户直接使用 Azure Active Directory 进行身份验证，并接收访问/刷新令牌对作为返回。 访问令牌授予客户端对 Microsoft 365 租户中相应资源的访问权限。 刷新令牌用于在当前访问令牌过期时获取新的访问令牌或刷新令牌对。

新式身份验证支持不同的身份验证机制，如基于证书的身份验证。 Windows、Android 或 iOS 设备上的客户端可以使用基于证书的身份验证 (CBA) 使用设备上的客户端证书向 Azure Active Directory 进行身份验证。 证书用于从 Azure Active Directory 获取访问/刷新令牌对，而不是典型的用户名/密码。

了解有关基于 [证书的身份验证的更多信息](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。

## <a name="supported-clients--platforms"></a>支持的客户端&平台

以下客户端和平台的最新版本支持在客户端 (内登录 Azure Active Directory 帐户时进行基于证书的身份验证，例如，将帐户添加到应用) 。 有关 Microsoft 365 中的平台支持详细信息，请参阅 [Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)的系统要求。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Azure 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| 公司门户 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | 计划 | 计划 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Delve | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| 边缘<sup>1</sup> | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Excel | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Exchange Online 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Forms | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Office 365 Admin | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |  |
| Kaizala | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office Lens| ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Office mobile | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office 门户 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| OneDrive | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 计划 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| OneNote | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Outlook | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Planner | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power Apps | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Power Automate | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power BI | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| PowerPoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Project | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Publisher | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Skype for Business | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![受支持](../media/check-mark.png) |
| Skype for Business 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| SharePoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| SharePoint Online 管理员 | 计划 | 计划 | 不适用 | 不适用 | 不适用 |
| 便笺 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Stream | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Sway | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Teams | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 计划 |
| 待办事项 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Visio | 不适用 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Whiteboard | 计划 | 计划 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| 工作区分析 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 计划 | 不适用 | 计划 |

>[!NOTE]
><sup>1</sup> Edge for iOS 和 Android 支持帐户添加流期间基于证书的身份验证。 对通常为 Intranet 网站的网站执行身份验证时，iOS 和 Android 的边缘不支持基于证书的身份验证。 <br><br>  在此方案中，用户通常 (Intranet) ，其中网站需要用户通过证书进行身份验证。 这完全不涉及新式验证，也不利用 Microsoft 身份验证库。 这是由于 iOS 的限制：iOS 阻止第三方应用访问存储证书的系统密钥链 (只有 Apple 应用和 [Safari Webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 控制器可以访问系统密钥链) 。 <br><br> 由于 Edge 依赖 [WebKit](https://developer.apple.com/documentation/webkit) 框架来呈现网站，因此 Edge 无法访问系统密钥链，也无法向用户显示证书选择。 遗憾的是，这是由于 Apple 的体系结构而设计。

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

