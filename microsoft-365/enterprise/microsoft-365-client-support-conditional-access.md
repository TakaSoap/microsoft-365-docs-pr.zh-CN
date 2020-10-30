---
title: Microsoft 365 客户端应用程序支持：条件访问
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: 在本文中，了解哪些平台、客户端和 PowerShell 模块支持对 Microsoft 365 进行条件访问。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc187a26cd3aa644888312327b07fc9a116950cc
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806678"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365 客户端应用程序支持：条件访问

在新式工作区中，用户可以使用各种设备和应用从任意位置访问你的组织的资源。 因此，仅侧重于可以访问资源的人士再也无法满足的要求。 您的组织还必须支持在访问控制基础结构中访问资源的方式和位置。

使用 Azure Active Directory 设备、位置和基于多重身份验证的条件访问，可以满足此新要求。 条件访问是 Azure Active Directory 的一项功能，使您能够在对环境中的应用程序的访问上强制实施控制，所有这些都基于特定条件并从一个中心位置进行管理。

了解有关 [Azure Active Directory 条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/)的详细信息。

## <a name="supported-clients--platforms"></a>支持的客户端 & 平台

以下客户端和平台的最新版本支持条件访问。 有关 Microsoft 365 中平台支持的详细信息，请参阅 [microsoft 365 的系统要求](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)。

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
| OneDrive | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| OneNote | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Outlook | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Planner | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power Apps | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 相同 | 不适用 |
| Power Automate | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power BI | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| PowerPoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Project | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Publisher | 不适用 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) |
| Skype for Business | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 ||
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
