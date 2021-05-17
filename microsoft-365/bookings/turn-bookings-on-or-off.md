---
title: 打开或关闭 Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: 了解如何在 Microsoft 365 中访问 Microsoft Bookings。
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913762"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="0d4e3-103">打开或关闭 Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="0d4e3-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="0d4e3-104">可以针对整个组织或特定用户打开或关闭预订。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="0d4e3-105">当你为用户打开 Bookings 时，他们可以创建 Bookings 页面、创建日历并允许其他人预订时间。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="0d4e3-106">这些部分中所述的管理控制措施不适用于由世纪Office 365中国 (运营) 客户。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="0d4e3-107">使用管理中心打开或关闭Microsoft 365预订</span><span class="sxs-lookup"><span data-stu-id="0d4e3-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="0d4e3-108">以全局管理员Microsoft 365登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="0d4e3-109">在管理中心，转到"设置  \*\*\*\*   \> **组织设置** 并选择 **"预订"。**</span><span class="sxs-lookup"><span data-stu-id="0d4e3-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="0d4e3-110">选中"允许 **组织使用 Bookings** 为组织启用或禁用 Bookings"复选框。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0d4e3-111">关闭 Bookings 将禁用对服务的所有访问，包括创建和管理 Bookings 页面。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="0d4e3-112">选择 **"保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="0d4e3-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="0d4e3-113">使用 PowerShell 为组织打开或关闭 Bookings</span><span class="sxs-lookup"><span data-stu-id="0d4e3-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="0d4e3-114">若要使用 PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)为组织打开或关闭 Bookings，连接 Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0d4e3-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="0d4e3-115">为单个用户打开或关闭 Bookings</span><span class="sxs-lookup"><span data-stu-id="0d4e3-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="0d4e3-116">你可以为单个用户禁用 Bookings。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="0d4e3-117">转到管理Microsoft 365，**然后选择"用户**"" \> **活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="0d4e3-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="0d4e3-118">选择所需的用户，然后选择许可证 **和应用**。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="0d4e3-119">展开 **应用** 并清除 Microsoft Bookings 的复选框。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="0d4e3-120">共享忙/闲信息之前需要员工批准</span><span class="sxs-lookup"><span data-stu-id="0d4e3-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="0d4e3-121">管理员可以要求其组织的员工在通过 Bookings 共享其可用性信息之前以及可以通过预订页面进行预订之前选择加入。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="0d4e3-122">This setting is available in the Microsoft 365 admin center under **设置** \> **设置** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="0d4e3-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="0d4e3-123">启用此设置后，在预订日历中作为员工添加的员工将在他们收到的电子邮件通知中查找"批准/拒绝"链接。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="0d4e3-124">此功能将逐步向全球Microsoft 365推出。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="0d4e3-125">如果在管理中心中看不到此选项Microsoft 365，请尽快重新查看。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="0d4e3-126">阻止社交共享选项</span><span class="sxs-lookup"><span data-stu-id="0d4e3-126">Block social sharing options</span></span>

<span data-ttu-id="0d4e3-127">管理员可以控制如何在社交网络上共享预订页面。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="0d4e3-128">This setting is available in the Microsoft 365 admin center under **设置** \> **设置** \> **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="0d4e3-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="0d4e3-129">此功能将逐步向全球Microsoft 365推出。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="0d4e3-130">如果在管理中心中看不到此选项Microsoft 365，请尽快重新查看。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="0d4e3-131">仅允许所选用户创建 Bookings 日历</span><span class="sxs-lookup"><span data-stu-id="0d4e3-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="0d4e3-132">通过使用策略限制，您可以限制许可用户创建 Bookings 日历。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="0d4e3-133">必须先为整个组织启用 Bookings。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="0d4e3-134">你组织中所有用户都将拥有 Bookings 许可证，但只有策略中包含的用户才能创建 Bookings 日历，并完全控制谁可以访问他们创建的日历。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="0d4e3-135">此策略中包含的用户可以创建新的 Bookings 日历，并可以添加为任何容量的用户 (包括管理员角色) 现有 Bookings 日历。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="0d4e3-136">未包含在此策略中的用户将无法创建新的 Bookings 日历，并且如果他们尝试这样做，将收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="0d4e3-137">你需要使用 PowerShell 运行Exchange Online命令。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="0d4e3-138">有关运行 cmdlet Exchange Online，请参阅 连接[Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0d4e3-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d4e3-139">以下步骤假定尚未在组织中Outlook Web App (其他) OWA 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="0d4e3-140">为应允许其创建 Bookings 日历的用户创建新的邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="0d4e3-141"> (新邮箱策略默认允许创建 Bookings 日历) </span><span class="sxs-lookup"><span data-stu-id="0d4e3-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="0d4e3-142">有关详细信息，请参阅 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="0d4e3-143">通过为要授予创建 Bookings 日历权限的每个用户运行此命令，将此策略分配给相关用户。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="0d4e3-144">有关详细信息，请参阅 [Set-CASMailbox](/powershell/module/exchange/set-casmailbox)。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="0d4e3-145">可选：如果要为组织中所有其他用户禁用 Bookings，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="0d4e3-146">有关详细信息，请参阅 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="0d4e3-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="0d4e3-147">有关 OWA 邮箱策略详细信息，请查看以下主题：</span><span class="sxs-lookup"><span data-stu-id="0d4e3-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="0d4e3-148">在Outlook Web 邮箱策略上创建Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0d4e3-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="0d4e3-149">应用或删除Outlook邮箱的 Web 邮箱策略Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0d4e3-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)