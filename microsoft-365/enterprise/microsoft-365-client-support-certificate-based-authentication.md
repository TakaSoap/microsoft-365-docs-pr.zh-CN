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
description: 在本文中，查找有关基于证书的身份验证的 Microsoft 365 客户端应用程序支持的详细信息。。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 49ed1e329e83b73441c89de9a142bfb9dcac5395
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806690"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 客户端应用程序支持：基于证书的身份验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

通过基于证书的身份验证，您可以使用 Windows、Android 或 iOS 设备上的客户端证书对 Azure Active Directory 进行身份验证。 配置此功能后，无需在移动设备上将用户名和密码组合输入到某些邮件和 Microsoft Office 应用程序中。

了解有关 [基于证书的身份验证](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)的详细信息。

## <a name="supported-clients--platforms"></a>支持的客户端 & 平台

以下客户端和平台的最新版本支持基于证书的身份验证。 有关 Microsoft 365 中平台支持的详细信息，请参阅 [microsoft 365 的系统要求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Azure 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| 公司门户 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | 相同 | 相同 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
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
| Visio | 不适用 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Whiteboard | 相同 | 相同 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| 工作区分析 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 | 不适用 | 相同 |

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

