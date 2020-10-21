---
title: 为用户设置强密码要求
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
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626139"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="b3db6-103">为用户设置强密码要求</span><span class="sxs-lookup"><span data-stu-id="b3db6-103">Set strong password requirement for users</span></span>

<span data-ttu-id="b3db6-104">本文说明如何为用户设置强密码要求。</span><span class="sxs-lookup"><span data-stu-id="b3db6-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="b3db6-105">您必须使用 PowerShell 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b3db6-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b3db6-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="b3db6-106">Before you begin</span></span>

<span data-ttu-id="b3db6-107">本文适用于为企业、学校或非盈利性管理密码策略的用户。</span><span class="sxs-lookup"><span data-stu-id="b3db6-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="b3db6-108">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b3db6-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="b3db6-109">[什么是管理员帐户？](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b3db6-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="b3db6-110">您必须是 [全局管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b3db6-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="b3db6-111">此外，还必须使用 PowerShell 连接到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b3db6-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="b3db6-112">设置强密码</span><span class="sxs-lookup"><span data-stu-id="b3db6-112">Set strong passwords</span></span>

1. <span data-ttu-id="b3db6-113">[使用 PowerShell 连接到 Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b3db6-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="b3db6-114">使用 PowerShell，可以通过以下命令为所有用户启用强密码要求：</span><span class="sxs-lookup"><span data-stu-id="b3db6-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="b3db6-115">UserPrincipalName 必须采用 Internet 样式登录格式，其中用户名后面跟有 "at" 符号 ( @ ) 和域名称。</span><span class="sxs-lookup"><span data-stu-id="b3db6-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="b3db6-116">例如： user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b3db6-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="b3db6-117">相关内容</span><span class="sxs-lookup"><span data-stu-id="b3db6-117">Related content</span></span>

[<span data-ttu-id="b3db6-118">如何使用 PowerShell 连接到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3db6-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="b3db6-119">有关 PowerShell Get-msoluser 命令的详细信息</span><span class="sxs-lookup"><span data-stu-id="b3db6-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="b3db6-120">密码策略的详细信息</span><span class="sxs-lookup"><span data-stu-id="b3db6-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)