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
ms.openlocfilehash: 87ba9e0323c379d8c2589dbb82c38c531dd9d047
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286261"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>为用户关闭强密码要求

本文介绍如何为用户关闭强密码要求。 默认情况下，在适用于企业组织的 Microsoft 365启用强密码要求。 您的组织可能要求禁用强密码。 请按照以下步骤关闭强密码要求。 您必须使用 PowerShell 完成这些步骤。

## <a name="before-you-begin"></a>开始之前

本文适用于管理企业、学校或非营利组织的密码策略的用户。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](/microsoft-365/business-video/admin-center-overview) 您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

还必须使用 PowerShell Microsoft 365客户端。

## <a name="set-strong-passwords"></a>设置强密码

1. [连接 PowerShell Microsoft 365 。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

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

[如何使用 PowerShell Microsoft 365客户端](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[有关 PowerShell MsolUser 命令详细信息](/powershell/azure/active-directory/install-adv2)

[有关密码策略详细信息](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
