---
title: Microsoft 365 客户端应用程序支持：基于证书的身份验证
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
description: 在本文中，查找有关基于证书的身份验证的 Microsoft 365 客户端应用程序支持的详细信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fde124fcefdf3b949ec35a3b2ed99b15ee36f85e
ms.sourcegitcommit: 2beefb695cead03cc21d6066f589572d3ae029aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349676"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 客户端应用程序支持：基于证书的身份验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

新式验证是用于组合身份验证和授权方法的伞条款。 具体包括：

- **身份验证方法**：多因素身份验证;基于客户端证书的身份验证。
- **授权方法**： Microsoft 的开放授权 (OAuth) 实施。

通过使用身份验证库（如 Active Directory 身份验证库 (ADAL) 或 Microsoft Authentication Library (MSAL) ）启用新式验证。 新式验证是客户端用来对 Microsoft 365 资源进行身份验证和授权访问的客户端。 新式验证利用 OAuth，并为客户端提供一种安全机制来访问 Microsoft 365 服务，而无需访问用户凭据。 登录时，用户直接使用 Azure Active Directory 进行身份验证，并在 return 中接收访问/刷新令牌对。 访问令牌授予客户端对 Microsoft 365 租户中相应资源的访问权限。 在当前访问令牌过期时，将使用刷新令牌获取新的访问权限或刷新令牌对。

新式验证支持不同的身份验证机制，如基于证书的身份验证。 Windows、Android 或 iOS 设备上的客户端可以使用基于证书的身份验证 (CBA) 使用设备上的客户端证书对 Azure Active Directory 进行身份验证。 证书用于从 Azure Active Directory 中获取访问/刷新令牌对，而不是典型的用户名/密码。

了解有关 [基于证书的身份验证](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)的详细信息。

## <a name="supported-clients--platforms"></a>支持的客户端 & 平台

在客户端中登录到 Azure Active Directory 帐户时，以下客户端和平台的最新版本支持基于证书的身份验证 (例如，向应用程序) 添加帐户时。 有关 Microsoft 365 中平台支持的详细信息，请参阅 [microsoft 365 的系统要求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Azure 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| 公司门户 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | 相同 | 相同 | 无 | ![支持](../media/check-mark.png) | 不适用 |
| Delve | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Edge<sup>1</sup> | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Excel | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Exchange Online 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Forms | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Office 365 Admin | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |  |
| Kaizala | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office Lens| ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Office mobile | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office 门户 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| OneDrive | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| OneNote | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Outlook | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Planner | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power Apps | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Power Automate | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power BI | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| PowerPoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Project | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Publisher | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Skype for Business | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) |
| Skype for Business 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| SharePoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| SharePoint Online 管理员 | 相同 | 相同 | 不适用 | 不适用 | 不适用 |
| 粘滞便笺 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Stream | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Sway | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Teams | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 相同 |
| 待办事项 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Visio | 无 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Whiteboard | 相同 | 相同 | 无 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| 工作区分析 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 | 无 | 相同 |

>[!NOTE]
><sup>1</sup> Edge IOS 和 Android 支持在帐户添加流期间基于证书的身份验证。 在对网站（通常是 intranet 网站）执行身份验证时，iOS 和 Android 的边缘不支持基于证书的身份验证。 <br><br>  在此方案中，用户导航到某个网站 (通常位于 intranet) 上，web 站点要求用户通过证书进行身份验证。 这并不涉及新式身份验证，也不会利用 Microsoft 身份验证库。 这是由于 iOS 的限制导致： iOS 阻止第三方应用访问系统密钥链，其中证书存储在仅 (Apple 应用程序，并且 [Safari web 视图控制器](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 可以访问系统密钥链) 。 <br><br> 由于边缘依赖于用于呈现网站的 [WebKit](https://developer.apple.com/documentation/webkit) 框架，边缘无法访问系统密钥链，并向用户提供证书选择。 遗憾的是，由于 Apple 的体系结构而设计。

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

