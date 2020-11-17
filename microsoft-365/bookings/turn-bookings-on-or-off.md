---
title: 打开或关闭 Microsoft 预订
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: 了解如何在 Microsoft 365 中获取 Microsoft 预订的访问权限。
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126587"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="f305a-103">打开或关闭 Microsoft 预订</span><span class="sxs-lookup"><span data-stu-id="f305a-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="f305a-104">可以为您的整个组织或特定用户打开或关闭预订。</span><span class="sxs-lookup"><span data-stu-id="f305a-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="f305a-105">为用户启用预订时，他们可以创建预订页面，创建日历，并允许其他人与他们一起预订时间。</span><span class="sxs-lookup"><span data-stu-id="f305a-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="f305a-106">这些部分中所述的管理控件不适用于由世纪互联运营的 Office 365 (中国) 客户。</span><span class="sxs-lookup"><span data-stu-id="f305a-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="f305a-107">使用 Microsoft 365 管理中心为你的组织打开或关闭预订</span><span class="sxs-lookup"><span data-stu-id="f305a-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f305a-108">以全局管理员身份登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="f305a-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="f305a-109">在管理中心中，转到 " **设置**   \> **组织设置**"，然后选择 "**预订**"。</span><span class="sxs-lookup"><span data-stu-id="f305a-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="f305a-110">选中 " **允许您的组织使用预订** 为您的组织启用或禁用预订" 的复选框。</span><span class="sxs-lookup"><span data-stu-id="f305a-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f305a-111">关闭预订将禁用对该服务的所有访问，包括创建和管理预订页面。</span><span class="sxs-lookup"><span data-stu-id="f305a-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="f305a-112">选择 " **保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="f305a-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="f305a-113">使用 PowerShell 为你的组织启用或禁用预订</span><span class="sxs-lookup"><span data-stu-id="f305a-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="f305a-114">若要使用 PowerShell cmdlet [set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)为您的组织打开或关闭预订，请 [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f305a-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="f305a-115">为单个用户打开或关闭预订</span><span class="sxs-lookup"><span data-stu-id="f305a-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="f305a-116">您可以为单个用户禁用预订。</span><span class="sxs-lookup"><span data-stu-id="f305a-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="f305a-117">转到 "Microsoft 365 管理中心"，然后选择 " **用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="f305a-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="f305a-118">选择所需的用户，然后选择 " **许可证和应用**"。</span><span class="sxs-lookup"><span data-stu-id="f305a-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="f305a-119">展开 " **应用程序** "，并清除 Microsoft 预定的复选框。</span><span class="sxs-lookup"><span data-stu-id="f305a-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="f305a-120">在共享忙/闲信息之前需要员工批准</span><span class="sxs-lookup"><span data-stu-id="f305a-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="f305a-121">管理员可以要求组织中的员工在通过预订共享其可用性信息之前进行选择，然后才能通过预定页面 bookable。</span><span class="sxs-lookup"><span data-stu-id="f305a-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="f305a-122">此设置在 Microsoft 365 管理中心的 " **设置** \> **设置** \> **预订**" 下提供。</span><span class="sxs-lookup"><span data-stu-id="f305a-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="f305a-123">如果启用此设置，则在预订日历中添加为员工的员工将在收到的电子邮件通知中找到 "批准/拒绝" 链接。</span><span class="sxs-lookup"><span data-stu-id="f305a-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="f305a-124">此功能将从全球范围向 Microsoft 365 客户逐步推出。</span><span class="sxs-lookup"><span data-stu-id="f305a-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="f305a-125">如果在 Microsoft 365 管理中心中未看到此选项，请稍后再查看。</span><span class="sxs-lookup"><span data-stu-id="f305a-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="f305a-126">阻止社交共享选项</span><span class="sxs-lookup"><span data-stu-id="f305a-126">Block social sharing options</span></span>

<span data-ttu-id="f305a-127">管理员可以控制如何在社交网络中共享预订页面。</span><span class="sxs-lookup"><span data-stu-id="f305a-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="f305a-128">此设置在 Microsoft 365 管理中心的 " **设置** \> **设置** \> **预订**" 下提供。</span><span class="sxs-lookup"><span data-stu-id="f305a-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="f305a-129">此功能将从全球范围向 Microsoft 365 客户逐步推出。</span><span class="sxs-lookup"><span data-stu-id="f305a-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="f305a-130">如果在 Microsoft 365 管理中心中未看到此选项，请稍后再查看。</span><span class="sxs-lookup"><span data-stu-id="f305a-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="f305a-131">仅允许所选用户创建预定日历</span><span class="sxs-lookup"><span data-stu-id="f305a-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="f305a-132">通过使用策略限制，可以限制许可用户能够创建预定日历。</span><span class="sxs-lookup"><span data-stu-id="f305a-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="f305a-133">您必须首先为您的整个组织启用预订。</span><span class="sxs-lookup"><span data-stu-id="f305a-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="f305a-134">您组织中的所有用户都将拥有预订许可证，但只有策略中包括的用户才可以创建预订日历，并对可以访问他们所创建的日历的人员拥有完全控制权限。</span><span class="sxs-lookup"><span data-stu-id="f305a-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="f305a-135">此策略中包含的用户可以创建新的预订日历，并可作为员工添加到任何容量 (包括管理员角色) 现有的预订日历中。</span><span class="sxs-lookup"><span data-stu-id="f305a-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="f305a-136">不包含在此策略中的用户将不能创建新的预订日历，并将在尝试执行此操作时收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="f305a-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="f305a-137">您需要使用 Exchange Online PowerShell 运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f305a-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="f305a-138">有关运行 Exchange Online cmdlet 的详细信息，请参阅 [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f305a-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f305a-139">下面的步骤假定您的组织中没有创建任何其他 Outlook Web App (OWA) 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="f305a-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="f305a-140">为应允许创建预订日历的用户创建新的邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="f305a-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="f305a-141">默认情况下，默认情况下允许创建 (的预订日历：新的邮箱策略。 ) </span><span class="sxs-lookup"><span data-stu-id="f305a-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="f305a-142">有关详细信息，请参阅 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f305a-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="f305a-143">通过对要授予其创建预订日历的权限的每个用户运行此命令，将此策略分配给相关用户。</span><span class="sxs-lookup"><span data-stu-id="f305a-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="f305a-144">有关详细信息，请参阅 [set-casmailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)。</span><span class="sxs-lookup"><span data-stu-id="f305a-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="f305a-145">可选：如果要对组织中的所有其他用户禁用预订，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="f305a-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="f305a-146">有关详细信息，请参阅 [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f305a-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="f305a-147">有关 OWA 邮箱策略的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="f305a-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="f305a-148">在 Exchange Online 中创建 web 邮箱策略的 Outlook</span><span class="sxs-lookup"><span data-stu-id="f305a-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="f305a-149">在 Exchange Online 中的邮箱上应用或删除 Outlook web 上的 Outlook 邮箱策略</span><span class="sxs-lookup"><span data-stu-id="f305a-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
