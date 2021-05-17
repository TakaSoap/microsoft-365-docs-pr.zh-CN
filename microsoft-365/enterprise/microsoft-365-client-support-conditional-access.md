---
title: Microsoft 365客户端应用支持：条件访问
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
description: 本文将了解哪些平台、客户端和 PowerShell 模块支持条件Microsoft 365 专属 Access。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904957"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a>Microsoft 365客户端应用支持：条件访问

在现代工作场所中，用户可以从任何位置使用各种设备和应用访问组织的资源。 因此，只关注谁可以访问资源已不够用。 您的组织还必须支持在访问控制基础结构中访问资源以及如何访问资源。

使用Azure Active Directory、位置和基于多重身份验证的条件访问，你可以满足此新要求。 条件访问是一项Azure Active Directory，它使你能够强制执行对环境中应用的访问权限控制，所有这些操作都基于特定条件，并且从一个中心位置进行管理。

详细了解条件Azure Active Directory[访问](/azure/active-directory/conditional-access/)。

## <a name="supported-clients--platforms"></a>受支持的客户端&平台

以下客户端和平台的最新版本支持条件访问。 有关应用程序平台支持Microsoft 365，请参阅 system [requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)。
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a>支持的 PowerShell 模块

- [Azure Active DirectoryPowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
