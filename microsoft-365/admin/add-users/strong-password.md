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
ms.localizationpriority: medium
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
ms.openlocfilehash: 25e0db3da797fbcaa78dbf91bd81abce0104d725
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370580"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>为用户关闭强密码要求

本文介绍如何为用户关闭强密码要求。 默认情况下，在适用于企业组织的 Microsoft 365启用强密码要求。 您的组织可能要求禁用强密码。 请按照以下步骤关闭强密码要求。 您必须使用 PowerShell 完成这些步骤。

## <a name="before-you-begin"></a>准备工作

本文适用于管理企业、学校或非营利组织的密码策略的用户。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？] ([概述Microsoft 365 管理中心](../admin-overview/admin-center-overview.md)必须是全局[管理员或密码管理员](about-admin-roles.md)才能执行这些步骤。

还必须使用 PowerShell Microsoft 365客户端。

## <a name="set-strong-passwords"></a>设置强密码

1. [连接 PowerShell Microsoft 365 。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. 使用 PowerShell，可以使用以下命令关闭所有用户的强密码要求：

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn **OFF** strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> userPrincipalName 必须采用 Internet 样式的登录格式，其中用户名后跟 at 符号 (@) 和域名。 例如：user@contoso.com。

## <a name="related-content"></a>相关内容

[如何使用 PowerShell Microsoft 365客户端](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[有关 PowerShell MsolUser 命令详细信息](/powershell/azure/active-directory/install-adv2)

[有关密码策略详细信息](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
