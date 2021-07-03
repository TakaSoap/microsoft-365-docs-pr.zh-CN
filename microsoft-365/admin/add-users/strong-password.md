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
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="4db91-103">为用户关闭强密码要求</span><span class="sxs-lookup"><span data-stu-id="4db91-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="4db91-104">本文介绍如何为用户关闭强密码要求。</span><span class="sxs-lookup"><span data-stu-id="4db91-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="4db91-105">默认情况下，在适用于企业组织的 Microsoft 365启用强密码要求。</span><span class="sxs-lookup"><span data-stu-id="4db91-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="4db91-106">您的组织可能要求禁用强密码。</span><span class="sxs-lookup"><span data-stu-id="4db91-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="4db91-107">请按照以下步骤关闭强密码要求。</span><span class="sxs-lookup"><span data-stu-id="4db91-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="4db91-108">您必须使用 PowerShell 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="4db91-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4db91-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="4db91-109">Before you begin</span></span>

<span data-ttu-id="4db91-110">本文适用于管理企业、学校或非营利组织的密码策略的用户。</span><span class="sxs-lookup"><span data-stu-id="4db91-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="4db91-111">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4db91-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="4db91-112">什么是管理员帐户？</span><span class="sxs-lookup"><span data-stu-id="4db91-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="4db91-113">您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="4db91-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="4db91-114">还必须使用 PowerShell Microsoft 365客户端。</span><span class="sxs-lookup"><span data-stu-id="4db91-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="4db91-115">设置强密码</span><span class="sxs-lookup"><span data-stu-id="4db91-115">Set strong passwords</span></span>

1. <span data-ttu-id="4db91-116">[连接 PowerShell Microsoft 365 。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="4db91-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="4db91-117">使用 PowerShell，可以使用以下命令关闭所有用户的强密码要求：</span><span class="sxs-lookup"><span data-stu-id="4db91-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="4db91-118">userPrincipalName 必须采用 Internet 样式的登录格式，其中用户名后跟 at 符号 (@) 和域名。</span><span class="sxs-lookup"><span data-stu-id="4db91-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="4db91-119">例如：user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="4db91-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="4db91-120">相关内容</span><span class="sxs-lookup"><span data-stu-id="4db91-120">Related content</span></span>

[<span data-ttu-id="4db91-121">如何使用 PowerShell Microsoft 365客户端</span><span class="sxs-lookup"><span data-stu-id="4db91-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="4db91-122">有关 PowerShell MsolUser 命令详细信息</span><span class="sxs-lookup"><span data-stu-id="4db91-122">More information on PowerShell MsolUser commands</span></span>](/powershell/azure/active-directory/install-adv2)

[<span data-ttu-id="4db91-123">有关密码策略详细信息</span><span class="sxs-lookup"><span data-stu-id="4db91-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
