---
title: Microsoft 365 客户端应用程序支持：新式验证
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
description: 在本文中，了解哪些平台、客户端和 PowerShell 模块支持适用于 Microsoft 365 的新式验证。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 290a151e127b05e984b9d262c3b429b561201545
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806655"
---
# <a name="microsoft-365-client-app-support-modern-authentication"></a>Microsoft 365 客户端应用程序支持：新式验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

新式验证为不同平台上的 Office 客户端应用程序启用 Active Directory 身份验证库 (基于) 的基于 ADAL 的登录。 这将启用多因素身份验证 (MFA) 、智能卡和基于证书的身份验证等登录功能。

了解有关 [多因素身份验证](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication) 和 [基于证书的身份验证](https://docs.microsoft.com/azure/active-directory/active-directory-certificate-based-authentication-get-started)的详细信息。

## <a name="supported-clients--platforms"></a>支持的客户端 & 平台

以下客户端和平台的最新版本支持新式身份验证。 有关 Microsoft 365 中平台支持的详细信息，请参阅 [microsoft 365 的系统要求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Azure 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| 公司门户 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Delve | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Microsoft Edge | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Excel | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Exchange Online 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Forms | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Office 365 Admin | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |  |
| Kaizala | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office Lens| ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Office mobile | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office 门户 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| OneDrive | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
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
| SharePoint Online 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| 粘滞便笺 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Stream | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Sway | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Teams | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) |
| 待办事项 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Visio | 不适用 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Whiteboard | 相同 | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| 工作区分析 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)