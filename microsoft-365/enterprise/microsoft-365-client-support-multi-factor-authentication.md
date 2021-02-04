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
description: 本文将了解哪些平台、客户端和 PowerShell 模块支持 Microsoft 365 的多重身份验证。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fdec611fc595cdc15abb0fc1fb7a998f7a615ff7
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097455"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 客户端应用支持：多重身份验证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

若要为登录提供额外的安全级别，客户端可以配置为使用多重身份验证 (MFA) ，它同时使用用户密码和基于：

- 其拥有中无法轻松复制的项，例如智能手机。
- 用户具有独特和独特特征的一些内容，例如其指纹、面部或其他生物识别属性

了解有关多重 [身份验证的更多信息](/azure/active-directory/authentication/multi-factor-authentication)。

## <a name="supported-clients--platforms"></a>支持的客户端&平台

以下客户端和平台的最新版本支持多重身份验证。 有关 Microsoft 365 中的平台支持详细信息，请参阅 [Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)的系统要求。
<br>
<br>

| 客户端 | Android | iOS | Mac| Windows 10 <br> 新式应用| Windows 10 <br> 桌面 |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Access | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Azure 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| 公司门户 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Cortana | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Delve | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Microsoft Edge | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Excel | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| Exchange Online 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Forms | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Office 365 Admin | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |  |
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
| Project | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Publisher | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Skype for Business | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![受支持](../media/check-mark.png) |
| Skype for Business 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| SharePoint | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| SharePoint Online 管理员 | 不适用 | 不适用 | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| 便笺 | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Stream | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | 不适用 | 不适用 |
| Sway | 不适用 | 不适用 | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Teams | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![受支持](../media/check-mark.png) |
| 待办事项 | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 |
| Visio | 不适用 | ![支持](../media/check-mark.png) | 不适用 | 不适用 | ![受支持](../media/check-mark.png) |
| Whiteboard | 计划 | ![支持](../media/check-mark.png) | 不适用 | ![支持](../media/check-mark.png) | 不适用 |
| Word | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) |
| 工作区分析 | 不适用 | 不适用 | 不适用 | 不适用 | 不适用 |
| Yammer | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | ![支持](../media/check-mark.png) | 不适用 | ![受支持](../media/check-mark.png) |

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)