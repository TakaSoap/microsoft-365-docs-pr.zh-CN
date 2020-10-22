---
title: 对用户关闭强密码要求
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
description: 了解如何使用 Windows PowerShell 为用户设置强密码要求。
ms.openlocfilehash: f9a0b76d024cc18552657144e4ccf8de8a72f0d9
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655731"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>对用户关闭强密码要求

本文介绍如何为用户关闭强密码要求。 默认情况下，在 Microsoft 365 for business 组织中启用强密码要求。 您的组织可能需要禁用强密码。 按照下面的步骤关闭强密码要求。 您必须使用 PowerShell 完成这些步骤。

## <a name="before-you-begin"></a>准备工作

本文适用于为企业、学校或非盈利性管理密码策略的用户。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../admin-overview/admin-overview.md) 您必须是 [全局管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

此外，还必须使用 PowerShell 连接到 Microsoft 365。

## <a name="set-strong-passwords"></a>设置强密码

1. [使用 PowerShell 连接到 Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. 使用 PowerShell，你可以使用以下命令为所有用户关闭强密码要求：

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName 必须采用 Internet 样式登录格式，其中用户名后面跟有 "at" 符号 ( @ ) 和域名称。 例如： user@contoso.com。

## <a name="related-content"></a>相关内容

[如何使用 PowerShell 连接到 Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[有关 PowerShell Get-msoluser 命令的详细信息](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[密码策略的详细信息](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)