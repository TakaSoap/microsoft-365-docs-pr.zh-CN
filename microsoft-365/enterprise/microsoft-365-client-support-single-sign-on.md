---
title: Microsoft 365 客户端应用程序支持：单个 Sign-On
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
description: 在本文中，了解哪些平台、客户端和 PowerShell 模块支持 Microsoft 365 的单一登录。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b70f0c1ec4a6e94651b987830c8b29993732a3c2
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806656"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365 客户端应用程序支持：单个 Sign-On

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

单一登录 (SSO) 在用户登录到 Azure Active Directory 中的应用程序时，会增加安全性和方便性。 通过单一登录，用户可以使用一个帐户登录一次，以访问本地 Active Directory 域服务 (AD DS) 加入域的设备、软件作为服务 (SaaS) 应用程序和 web 应用程序。

了解有关 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)的详细信息。

## <a name="supported-clients--platforms"></a>支持的客户端 & 平台

以下客户端和平台的最新版本支持单一登录。 有关 Microsoft 365 中平台支持的详细信息，请参阅 [microsoft 365 的系统要求](https://products.office.com/office-system-requirements)。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| 公司门户 | 不适用 | ![支持](../media/check-mark.png) | 相同 | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Delve | 相同 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Microsoft Edge | ![支持](../media/check-mark.png) | 相同 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Excel | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Kaizala | ![支持](../media/check-mark.png) | 相同 | 不适用 | 不适用 | 不适用 |
| Office Lens| ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office mobile | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office 门户 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| OneDrive | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 | ![支持](../media/check-mark.png) | 相同 |
| OneNote | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 |
| Outlook | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 | ![支持](../media/check-mark.png) |
| Planner | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power Apps | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 相同 | 不适用 |
| Power Automate | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power BI | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 相同 |
| PowerPoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Project | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Publisher | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Skype for Business | 相同 | 相同 | 不适用 | 不适用 | 不适用 |
| SharePoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| 粘滞便笺 | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Stream | 相同 | 相同 | 不适用 | 不适用 | 不适用 |
| Sway | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Teams | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 相同 | 不适用 | 相同 |
| 待办事项 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Visio | 不适用 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Whiteboard | 不适用 | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 相同 |

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
