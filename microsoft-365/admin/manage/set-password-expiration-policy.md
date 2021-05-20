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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 了解管理员如何在 Microsoft 365 管理中心中针对你的企业、学校或非营利组织设置密码过期策略。
ms.openlocfilehash: 5469d4dcd75bee2e6f8a188aa6f50d18ce6e06c4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537483"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="a3897-103">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="a3897-103">Set the password expiration policy for your organization</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a3897-104">准备工作</span><span class="sxs-lookup"><span data-stu-id="a3897-104">Before you begin</span></span>

<span data-ttu-id="a3897-105">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="a3897-105">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a3897-106">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a3897-106">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="a3897-107">[什么是管理员帐户？](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a3897-107">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="a3897-108">作为管理员，可让用户密码在特定天数后过期，或将密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="a3897-108">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> <span data-ttu-id="a3897-109">默认情况下，密码设置为对组织永不过期。</span><span class="sxs-lookup"><span data-stu-id="a3897-109">By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="a3897-110">当前研究强烈表明，强制实施的密码更改弊大于利。</span><span class="sxs-lookup"><span data-stu-id="a3897-110">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="a3897-111">它们会导致用户选择安全性更弱的密码、重复使用密码，或者以很容易被黑客猜出的方式更新旧密码。</span><span class="sxs-lookup"><span data-stu-id="a3897-111">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="a3897-112">我们已建议启用 [多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="a3897-112">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="a3897-113">要了解有关密码策略的详细信息，请查看[密码策略建议](../misc/password-policy-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="a3897-113">To learn more about password policy, check out [Password policy recommendations](../misc/password-policy-recommendations.md).</span></span>

<span data-ttu-id="a3897-114">必须是 [全局管理员](../add-users/about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="a3897-114">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a3897-p104">如果你是用户，则你不具有将密码设置为永不过期的权限。让你的工作单位或学校的技术支持人员为你执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="a3897-p104">If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="a3897-117">设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="a3897-117">Set password expiration policy</span></span>

<span data-ttu-id="a3897-118">如果希望用户密码在特定时段后过期，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a3897-118">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="a3897-119">在管理中心，转到“**设置**”\>“**组织设置**”。</span><span class="sxs-lookup"><span data-stu-id="a3897-119">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="a3897-120">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全和隐私</a>页面。</span><span class="sxs-lookup"><span data-stu-id="a3897-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="a3897-121">只有全局管理员能看到“安全和隐私”选项。</span><span class="sxs-lookup"><span data-stu-id="a3897-121">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="a3897-122">选择“**密码过期策略**”。</span><span class="sxs-lookup"><span data-stu-id="a3897-122">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="a3897-123">如果不希望强制用户更改密码，请取消选择“**将用户密码设置为以下天数后过期**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a3897-123">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="a3897-124">输入密码过期频率。</span><span class="sxs-lookup"><span data-stu-id="a3897-124">Type how often passwords should expire.</span></span> <span data-ttu-id="a3897-125">请在 14 到 730 之间选择一个天数。</span><span class="sxs-lookup"><span data-stu-id="a3897-125">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="a3897-126">在第二个框中键入通知用户其密码将过期的时间，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a3897-126">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="a3897-127">选择从 1 到 30 的天数。</span><span class="sxs-lookup"><span data-stu-id="a3897-127">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="a3897-128">密码到期功能重要事项须知</span><span class="sxs-lookup"><span data-stu-id="a3897-128">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="a3897-p108">对于仅使用 Outlook 应用的用户，在其密码在缓存中过期之前，不会强制其重置 Microsoft 365 密码。这一到期时间有可能在实际到期日期数天后抵达。这一情况在管理级别尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="a3897-p108">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="a3897-132">防止再次使用上一次使用过的密码</span><span class="sxs-lookup"><span data-stu-id="a3897-132">Prevent last password from being used again</span></span>

<span data-ttu-id="a3897-133">如果要防止用户重新使用旧密码，可通过在本地 Active Directory (AD) 中强制实施密码历史记录来实现。</span><span class="sxs-lookup"><span data-stu-id="a3897-133">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="a3897-134">请参阅[创建自定义密码策略](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)。</span><span class="sxs-lookup"><span data-stu-id="a3897-134">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="a3897-135">在 Azure AD 中，当用户更改密码后，不能再次使用上一个密码。</span><span class="sxs-lookup"><span data-stu-id="a3897-135">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="a3897-136">密码策略适用于直接在 Azure AD 中创建和管理的所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a3897-136">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="a3897-137">无法修改此密码策略。</span><span class="sxs-lookup"><span data-stu-id="a3897-137">This password policy can't be modified.</span></span> <span data-ttu-id="a3897-138">请参阅 [Azure AD 密码策略](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)。</span><span class="sxs-lookup"><span data-stu-id="a3897-138">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="a3897-139">将用户密码哈希从本地 Active Directory 同步到 Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="a3897-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="a3897-140">本文适用于为仅限云的用户 (Azure AD) 设置过期策略。</span><span class="sxs-lookup"><span data-stu-id="a3897-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="a3897-141">它不适用于使用密码哈希同步、直通身份验证或本地联合身份验证（如 ADFS）的混合标识用户。</span><span class="sxs-lookup"><span data-stu-id="a3897-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="a3897-142">要了解如何将用户密码哈希从本地 AD 同步到 Azure AD，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="a3897-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="a3897-143">Azure Active Directory 中的密码策略和账户限制</span><span class="sxs-lookup"><span data-stu-id="a3897-143">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="a3897-144">可在 Azure Active Directory 中设置更多密码策略和限制。</span><span class="sxs-lookup"><span data-stu-id="a3897-144">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="a3897-145">有关详细信息，请参阅[ Azure Active Directory 中的密码策略和帐户限制](/azure/active-directory/authentication/concept-sspr-policy)。</span><span class="sxs-lookup"><span data-stu-id="a3897-145">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="a3897-146">更新密码策略</span><span class="sxs-lookup"><span data-stu-id="a3897-146">Update password Policy</span></span>

<span data-ttu-id="a3897-p113">Set-MsolPasswordPolicy cmdlet 将更新指定域或租户的密码策略。需要两个设置：第一个用于指示密码在必须更改之前的有效时长，第二个用于指示在用户收到第一封显示其密码即将过期的通知时将触发的密码过期日期之前的剩余天数。</span><span class="sxs-lookup"><span data-stu-id="a3897-p113">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant. Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="a3897-149">若要了解如何更新特定域或租户的密码策略，请参阅 [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="a3897-149">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="a3897-150">相关内容</span><span class="sxs-lookup"><span data-stu-id="a3897-150">Related content</span></span>

<span data-ttu-id="a3897-151">[允许用户重置自己的密码](../add-users/let-users-reset-passwords.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="a3897-151">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="a3897-152">[重置密码](../add-users/reset-passwords.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="a3897-152">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>