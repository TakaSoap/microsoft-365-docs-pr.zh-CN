---
title: 为用户关闭强密码要求
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何使用 Windows PowerShell 为用户设置强密码Windows PowerShell。
ms.openlocfilehash: de2f47bb88fe4cb3d00e45698fe006035faa4e5c
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222069"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>为用户关闭强密码要求

本文介绍如何为用户关闭强密码要求。 Microsoft 365 商业版组织中默认启用强密码要求。 您的组织可能要求禁用强密码。 请按照以下步骤关闭强密码要求。 您必须使用 PowerShell 完成这些步骤。

## <a name="before-you-begin"></a>准备工作

本文适用于管理企业、学校或非营利组织的密码策略的用户。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview) 您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

还必须使用 PowerShell 连接到 Microsoft 365。

## <a name="set-strong-passwords"></a>设置强密码

1. [使用 PowerShell 连接到 Microsoft 365。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. 使用 PowerShell，可以使用以下命令关闭所有用户的强密码要求：

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> userPrincipalName 必须采用 Internet 样式的登录格式，其中用户名后跟 at 符号 (@) 和域名。 例如：user@contoso.com。

## <a name="related-content"></a>相关内容

[如何使用 PowerShell 连接到 Microsoft 365](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[有关 PowerShell MsolUser 命令详细信息](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[有关密码策略详细信息](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)