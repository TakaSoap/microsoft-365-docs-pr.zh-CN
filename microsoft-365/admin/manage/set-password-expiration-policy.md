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
ms.openlocfilehash: 88953317bea2b96c04c291dd028a4e9131b9a83e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361657"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="039f9-103">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="039f9-103">Set the password expiration policy for your organization</span></span>

<span data-ttu-id="039f9-104">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="039f9-104">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="039f9-105">如果你是用户，则你不没有将密码设置为永不过期的权限。</span><span class="sxs-lookup"><span data-stu-id="039f9-105">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="039f9-106">让你的工作单位或学校的技术支持人员代你执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="039f9-106">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="039f9-107">作为管理员，可让用户密码在特定天数后过期，或设置密码永不过期。</span><span class="sxs-lookup"><span data-stu-id="039f9-107">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="039f9-108">默认情况下，密码设置为在 90 天后过期。</span><span class="sxs-lookup"><span data-stu-id="039f9-108">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="039f9-109">当前研究强烈表明，强制实施的密码更改弊大于利。</span><span class="sxs-lookup"><span data-stu-id="039f9-109">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="039f9-110">它们会导致用户选择安全性更弱的密码、重复使用密码，或者以很容易被黑客猜出的方式更新旧密码。</span><span class="sxs-lookup"><span data-stu-id="039f9-110">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="039f9-111">如果将密码设为永不过期，则建议启用[多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="039f9-111">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="039f9-112">如果希望用户密码在特定时段后过期，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="039f9-112">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="039f9-113">只有 [Office 365 全局管理员](../add-users/about-admin-roles.md)可执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="039f9-113">Only [Office 365 global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="039f9-114">在管理中心，转到“**设置**”\>“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="039f9-114">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="039f9-115">转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全和隐私</a>页面。</span><span class="sxs-lookup"><span data-stu-id="039f9-115">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="039f9-116">只有 Office 365 全局管理员能看到“安全和隐私”选项。</span><span class="sxs-lookup"><span data-stu-id="039f9-116">If you aren't an Office 365 global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="039f9-117">选择“**密码过期策略**”。</span><span class="sxs-lookup"><span data-stu-id="039f9-117">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="039f9-118">如果不希望强制用户更改密码，请选择“**将用户密码设置为以下天数后过期**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="039f9-118">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="039f9-119">输入密码过期频率。</span><span class="sxs-lookup"><span data-stu-id="039f9-119">Type how often passwords should expire.</span></span> <span data-ttu-id="039f9-120">请在 14 到 730 之间选择一个天数。</span><span class="sxs-lookup"><span data-stu-id="039f9-120">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="039f9-121">在第二个框中键入通知用户其密码将过期的时间，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="039f9-121">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="039f9-122">选择从 1 到 30 的天数。</span><span class="sxs-lookup"><span data-stu-id="039f9-122">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="039f9-123">用户的密码到期后会收到通知，通知会出现在其屏幕右下角。</span><span class="sxs-lookup"><span data-stu-id="039f9-123">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="039f9-124">密码到期功能重要事项须知</span><span class="sxs-lookup"><span data-stu-id="039f9-124">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="039f9-125">下面是自 2018 年 1 月起有关此功能运行原理的一些注意事项须知：</span><span class="sxs-lookup"><span data-stu-id="039f9-125">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="039f9-p106">对于仅使用 Outlook 应用的用户，在其密码在缓存中过期之前，不会强制其重置 Office 365 密码。这一到期时间有可能在实际到期日期数天后抵达。这一情况在管理级别尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="039f9-p106">People who only use the Outlook app won't be forced to reset their Office 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="039f9-p107">用户不会收到提示其密码将在 X 天后过期的电子邮件通知。是否需要此功能？ **[在此处投票！](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="039f9-p107">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="039f9-132">防止再次使用上一次使用过的密码</span><span class="sxs-lookup"><span data-stu-id="039f9-132">Prevent last password from being used again</span></span>

<span data-ttu-id="039f9-133">如果要防止用户重新使用旧密码，可在 Azure AD 中进行阻止。</span><span class="sxs-lookup"><span data-stu-id="039f9-133">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="039f9-134">参见“[为组织设置密码过期策略](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide)”。</span><span class="sxs-lookup"><span data-stu-id="039f9-134">See [Set the password expiration policy for your organization](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span></span>

<span data-ttu-id="039f9-135">此外，如果某员工曾使用移动设备访问 Office 365，你可擦除该设备，确保密码不再存储且不再从此处回收。</span><span class="sxs-lookup"><span data-stu-id="039f9-135">In addition, if an employee used a mobile device to access Office 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="039f9-136">要了解详细信息，请参阅[擦除并阻止前任员工的移动设备](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)。</span><span class="sxs-lookup"><span data-stu-id="039f9-136">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-office-365"></a><span data-ttu-id="039f9-137">将用户密码哈希从本地 Active Directory 同步到 Azure AD (Office 365)</span><span class="sxs-lookup"><span data-stu-id="039f9-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Office 365)</span></span>

<span data-ttu-id="039f9-138">本文适用于为仅限云的用户 (Azure AD) 设置过期策略。</span><span class="sxs-lookup"><span data-stu-id="039f9-138">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="039f9-139">它不适用于使用密码哈希同步、直通身份验证或本地联合身份验证（如 ADFS）的混合标识用户。</span><span class="sxs-lookup"><span data-stu-id="039f9-139">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="039f9-140">要了解如何将用户密码哈希从本地 AD 同步到 Azure AD，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="039f9-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
