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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: '了解如何在 Microsoft 365 管理中心为组织设置密码过期策略。 '
ms.openlocfilehash: b5836fb1a9bf7c1a9820214916f4c6158bc44852
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139657"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="4cf49-103">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="4cf49-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4cf49-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="4cf49-104">The admin center is changing.</span></span> <span data-ttu-id="4cf49-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="4cf49-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="4cf49-106">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="4cf49-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="4cf49-107">如果你是用户，则你不没有将密码设置为永不过期的权限。</span><span class="sxs-lookup"><span data-stu-id="4cf49-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="4cf49-108">让你的工作单位或学校的技术支持人员代你执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="4cf49-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="4cf49-109">作为管理员，可让用户密码在特定天数后过期，或设置密码永不过期。</span><span class="sxs-lookup"><span data-stu-id="4cf49-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="4cf49-110">默认情况下，密码设置为在 90 天后过期。</span><span class="sxs-lookup"><span data-stu-id="4cf49-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="4cf49-111">当前研究强烈表明，强制实施的密码更改弊大于利。</span><span class="sxs-lookup"><span data-stu-id="4cf49-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="4cf49-112">它们会导致用户选择安全性更弱的密码、重复使用密码，或者以很容易被黑客猜出的方式更新旧密码。</span><span class="sxs-lookup"><span data-stu-id="4cf49-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="4cf49-113">如果将密码设为永不过期，则建议启用[多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="4cf49-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="4cf49-114">如果希望用户密码在特定时段后过期，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="4cf49-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="4cf49-115">只有[全局管理员](../add-users/about-admin-roles.md)可执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="4cf49-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="4cf49-116">在管理中心，转到“**设置**”\>“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="4cf49-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="4cf49-117">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全和隐私</a>页面。</span><span class="sxs-lookup"><span data-stu-id="4cf49-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="4cf49-118">只有全局管理员能看到“安全和隐私”选项。</span><span class="sxs-lookup"><span data-stu-id="4cf49-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="4cf49-119">选择“**密码过期策略**”。</span><span class="sxs-lookup"><span data-stu-id="4cf49-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="4cf49-120">如果不希望强制用户更改密码，请选择“**将用户密码设置为以下天数后过期**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="4cf49-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="4cf49-121">输入密码过期频率。</span><span class="sxs-lookup"><span data-stu-id="4cf49-121">Type how often passwords should expire.</span></span> <span data-ttu-id="4cf49-122">请在 14 到 730 之间选择一个天数。</span><span class="sxs-lookup"><span data-stu-id="4cf49-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="4cf49-123">在第二个框中键入通知用户其密码将过期的时间，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4cf49-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="4cf49-124">选择从 1 到 30 的天数。</span><span class="sxs-lookup"><span data-stu-id="4cf49-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="4cf49-125">用户的密码到期后会收到通知，通知会出现在其屏幕右下角。</span><span class="sxs-lookup"><span data-stu-id="4cf49-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="4cf49-126">密码到期功能重要事项须知</span><span class="sxs-lookup"><span data-stu-id="4cf49-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="4cf49-127">下面是自 2018 年 1 月起有关此功能运行原理的一些注意事项须知：</span><span class="sxs-lookup"><span data-stu-id="4cf49-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="4cf49-p107">对于仅使用 Outlook 应用的用户，在其密码在缓存中过期之前，不会强制其重置 Microsoft 365 密码。这一到期时间有可能在实际到期日期数天后抵达。这一情况在管理级别尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="4cf49-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="4cf49-p108">用户不会收到提示其密码将在 X 天后过期的电子邮件通知。是否需要此功能？ **[在此处投票！](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="4cf49-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="4cf49-134">防止再次使用上一次使用过的密码</span><span class="sxs-lookup"><span data-stu-id="4cf49-134">Prevent last password from being used again</span></span>

<span data-ttu-id="4cf49-135">如果要防止用户重新使用旧密码，可在 Azure AD 中进行阻止。</span><span class="sxs-lookup"><span data-stu-id="4cf49-135">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="4cf49-136">请参阅[强制实施密码历史记录](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history)。</span><span class="sxs-lookup"><span data-stu-id="4cf49-136">See [Enforce password history](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span></span>

<span data-ttu-id="4cf49-137">此外，如果某员工曾使用移动设备访问 Microsoft 365，你可擦除该设备，确保密码不再存储且不再从此处回收。</span><span class="sxs-lookup"><span data-stu-id="4cf49-137">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="4cf49-138">要了解详细信息，请参阅[擦除并阻止前任员工的移动设备](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)。</span><span class="sxs-lookup"><span data-stu-id="4cf49-138">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="4cf49-139">将用户密码哈希从本地 Active Directory 同步到 Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="4cf49-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="4cf49-140">本文适用于为仅限云的用户 (Azure AD) 设置过期策略。</span><span class="sxs-lookup"><span data-stu-id="4cf49-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="4cf49-141">它不适用于使用密码哈希同步、直通身份验证或本地联合身份验证（如 ADFS）的混合标识用户。</span><span class="sxs-lookup"><span data-stu-id="4cf49-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="4cf49-142">要了解如何将用户密码哈希从本地 AD 同步到 Azure AD，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="4cf49-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
