---
title: Microsoft 365 客户端应用支持：单Sign-On
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
description: 本文将了解哪些平台、客户端和 PowerShell 模块支持 Microsoft 365 的单一登录。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a685f04ed64a89cda026ff9380aac7c6c2b3ea4
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097194"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a>Microsoft 365 客户端应用支持：单Sign-On

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

SSO (单一) 在用户登录 Azure Active Directory 中的应用程序时，可增加安全性和便利性。 通过单一登录，用户可以使用一个帐户登录一次，以访问本地 Active Directory 域服务 (AD DS) 已加入域的设备、软件即服务 (SaaS) 应用程序和 Web 应用程序。

了解有关单 [一登录的更多信息](/azure/active-directory/manage-apps/what-is-single-sign-on)。

## <a name="supported-clients--platforms"></a>支持的客户端&平台

以下客户端和平台的最新版本支持单一登录。 有关 Microsoft 365 中的平台支持详细信息，请参阅 [Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)的系统要求。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| 公司门户 | 不适用 | ![受支持](../media/check-mark.png) | 计划 | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Delve | 计划 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Microsoft Edge | ![受支持](../media/check-mark.png) | 计划 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Excel | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Kaizala | ![受支持](../media/check-mark.png) | 计划 | 不适用 | 不适用 | 不适用 |
| Office Lens| ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office mobile | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Office 门户 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| OneDrive | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 计划 | ![受支持](../media/check-mark.png) | 计划 |
| OneNote | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 计划 |
| Outlook | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 计划 | ![受支持](../media/check-mark.png) |
| Planner | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power Apps | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 计划 | 不适用 |
| Power Automate | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Power BI | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![受支持](../media/check-mark.png) | 计划 |
| PowerPoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Project | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Publisher | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Skype for Business | 计划 | 计划 | 不适用 | 不适用 | 不适用 |
| SharePoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| 便笺 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Stream | 计划 | 计划 | 不适用 | 不适用 | 不适用 |
| Sway | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Teams | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 计划 | 不适用 | 计划 |
| 待办事项 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Visio | 不适用 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Whiteboard | 不适用 | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 计划 |

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
