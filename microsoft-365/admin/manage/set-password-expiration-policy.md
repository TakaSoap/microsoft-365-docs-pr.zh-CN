---
title: 为组织设置密码过期策略
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 了解如何在 Microsoft 365 管理中心为组织设置密码过期策略。
ms.openlocfilehash: 96e9159f3228fb6b7725f2f0d6eb515b108bc32e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751497"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="dc4ec-103">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="dc4ec-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="dc4ec-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-104">The admin center is changing.</span></span> <span data-ttu-id="dc4ec-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="dc4ec-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="dc4ec-106">Before you begin</span></span>

<span data-ttu-id="dc4ec-107">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="dc4ec-108">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="dc4ec-109">[什么是管理员帐户？](../admin-overview/admin-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dc4ec-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span>

<span data-ttu-id="dc4ec-110">只有[全局管理员或密码管理员](../add-users/about-admin-roles.md)才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-110">You must be a [global admin or password admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="dc4ec-111">如果你是用户，则你不没有将密码设置为永不过期的权限。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-111">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="dc4ec-112">让你的工作单位或学校的技术支持人员代你执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-112">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="dc4ec-113">作为管理员，可让用户密码在特定天数后过期，或设置密码永不过期。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-113">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="dc4ec-114">设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="dc4ec-114">Set password expiration policy</span></span>

> [!Tip]
> <span data-ttu-id="dc4ec-115">默认情况下，密码设置为在 90 天后过期。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-115">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="dc4ec-116">当前研究强烈表明，强制实施的密码更改弊大于利。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-116">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="dc4ec-117">它们会导致用户选择安全性更弱的密码、重复使用密码，或者以很容易被黑客猜出的方式更新旧密码。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-117">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="dc4ec-118">如果将密码设为永不过期，则建议启用[多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-118">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="dc4ec-119">如果希望用户密码在特定时段后过期，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="dc4ec-120">只有[全局管理员](../add-users/about-admin-roles.md)可执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-120">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="dc4ec-121">在管理中心，转到“**设置**”\>“**组织设置**”。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-121">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="dc4ec-122">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全和隐私</a>页面。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-122">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="dc4ec-123">只有全局管理员能看到“安全和隐私”选项。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-123">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="dc4ec-124">选择“**密码过期策略**”。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-124">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="dc4ec-125">如果不希望强制用户更改密码，请取消选择“**将用户密码设置为以下天数后过期**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-125">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="dc4ec-126">输入密码过期频率。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-126">Type how often passwords should expire.</span></span> <span data-ttu-id="dc4ec-127">请在 14 到 730 之间选择一个天数。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-127">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="dc4ec-128">在第二个框中键入通知用户其密码将过期的时间，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-128">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="dc4ec-129">选择从 1 到 30 的天数。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-129">Choose a number of days from 1 to 30.</span></span>

7. <span data-ttu-id="dc4ec-130">用户的密码到期后会收到通知，通知会出现在其屏幕右下角。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-130">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="dc4ec-131">密码到期功能重要事项须知</span><span class="sxs-lookup"><span data-stu-id="dc4ec-131">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="dc4ec-p108">对于仅使用 Outlook 应用的用户，在其密码在缓存中过期之前，不会强制其重置 Microsoft 365 密码。这一到期时间有可能在实际到期日期数天后抵达。这一情况在管理级别尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="dc4ec-135">防止再次使用上一次使用过的密码</span><span class="sxs-lookup"><span data-stu-id="dc4ec-135">Prevent last password from being used again</span></span>

<span data-ttu-id="dc4ec-136">如果要防止用户重新使用旧密码，可通过在本地 Active Directory (AD) 中强制实施密码历史记录来实现。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-136">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="dc4ec-137">请参阅[创建自定义密码策略](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-137">See [Create a custom password policy](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="dc4ec-138">在 Azure AD 中，当用户更改密码后，不能再次使用上一个密码。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-138">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="dc4ec-139">密码策略适用于直接在 Azure AD 中创建和管理的所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-139">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="dc4ec-140">无法修改此密码策略。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-140">This password policy can't be modified.</span></span> <span data-ttu-id="dc4ec-141">请参阅 [Azure AD 密码策略](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-141">See [Azure AD password policies](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="dc4ec-142">将用户密码哈希从本地 Active Directory 同步到 Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="dc4ec-142">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="dc4ec-143">本文适用于为仅限云的用户 (Azure AD) 设置过期策略。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-143">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="dc4ec-144">它不适用于使用密码哈希同步、直通身份验证或本地联合身份验证（如 ADFS）的混合标识用户。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-144">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="dc4ec-145">要了解如何将用户密码哈希从本地 AD 同步到 Azure AD，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-145">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="dc4ec-146">Azure Active Directory 中的密码策略和账户限制</span><span class="sxs-lookup"><span data-stu-id="dc4ec-146">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="dc4ec-147">可在 Azure Active Directory 中设置更多密码策略和限制。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-147">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="dc4ec-148">有关详细信息，请参阅[ Azure Active Directory 中的密码策略和帐户限制](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-148">Check out [Password policies and account restrictions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="dc4ec-149">更新密码策略</span><span class="sxs-lookup"><span data-stu-id="dc4ec-149">Update password Policy</span></span>

<span data-ttu-id="dc4ec-150">Set-MsolPasswordPolicy cmdlet 会更新指定的域或租户的密码策略。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-150">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="dc4ec-151">需要两个设置：第一个用于指示密码在必须更改之前的有效时长，第二个用于指示在用户收到第一封显示其密码即将过期的通知时将触发的密码过期日期之前的剩余天数。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-151">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="dc4ec-152">若要了解如何更新特定域或租户的密码策略，请参阅 [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="dc4ec-152">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="dc4ec-153">相关内容</span><span class="sxs-lookup"><span data-stu-id="dc4ec-153">Related content</span></span>

[<span data-ttu-id="dc4ec-154">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="dc4ec-154">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="dc4ec-155">重置密码</span><span class="sxs-lookup"><span data-stu-id="dc4ec-155">Reset passwords</span></span>](../add-users/reset-passwords.md)
