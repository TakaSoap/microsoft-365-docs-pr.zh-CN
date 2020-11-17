---
title: 删除预定日历
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: 使用 Microsoft 365 管理中心或 Windows PowerShell 删除预定日历。
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126645"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="88b4e-103">在预订中删除预定日历</span><span class="sxs-lookup"><span data-stu-id="88b4e-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="88b4e-104">本文介绍如何删除不需要的预订日历。</span><span class="sxs-lookup"><span data-stu-id="88b4e-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="88b4e-105">您可以删除 Microsoft 365 管理中心中的预定日历，也可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="88b4e-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="88b4e-106">预订日历是 Exchange Online 中的邮箱，因此您可以删除相应的用户帐户以删除预定日历。</span><span class="sxs-lookup"><span data-stu-id="88b4e-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88b4e-107">您在2017或之前创建的所有预订日历必须使用本主题的 PowerShell 说明删除。</span><span class="sxs-lookup"><span data-stu-id="88b4e-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="88b4e-108">可以在 Microsoft 365 管理中心中删除在2018或之后创建的所有预订日历。</span><span class="sxs-lookup"><span data-stu-id="88b4e-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="88b4e-109">预订日历是存储有关该预订日历和数据的所有相关信息，包括：</span><span class="sxs-lookup"><span data-stu-id="88b4e-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="88b4e-110">创建预订日历时添加的业务信息、徽标和工作时间</span><span class="sxs-lookup"><span data-stu-id="88b4e-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="88b4e-111">创建预订日历时添加的相关人员和服务</span><span class="sxs-lookup"><span data-stu-id="88b4e-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="88b4e-112">在创建预订日历后添加到该预订日历的所有预订和休息时间的约会。</span><span class="sxs-lookup"><span data-stu-id="88b4e-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="88b4e-113">一旦删除预订日历，此附加信息也会永久删除且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="88b4e-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="88b4e-114">在 Microsoft 365 管理中心中删除预定日历</span><span class="sxs-lookup"><span data-stu-id="88b4e-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="88b4e-115">转到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="88b4e-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="88b4e-116">在管理中心，选择" **用户** "。</span><span class="sxs-lookup"><span data-stu-id="88b4e-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 管理中心中的用户 UI 的图像](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="88b4e-118">在" **活动用户**"页面上，选择要删除的用户的姓名，然后选择" **删除用户**"。</span><span class="sxs-lookup"><span data-stu-id="88b4e-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 管理中心中的 Delete User UI 的图像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="88b4e-120">使用 Exchange Online PowerShell 删除预定日历</span><span class="sxs-lookup"><span data-stu-id="88b4e-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="88b4e-121">有关连接到 Exchange Online PowerShell 的先决条件和指南，请参阅 [连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="88b4e-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="88b4e-122">若要执行这些步骤，您必须使用通过选择 "以管理员身份运行" 选项运行的活动 Microsoft PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="88b4e-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="88b4e-123">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="88b4e-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="88b4e-124">出现提示时，请使用租户管理员凭据登录到托管要永久删除的预定日历的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="88b4e-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="88b4e-125">在 PowerShell 命令提示符处，输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="88b4e-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="88b4e-126">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="88b4e-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="88b4e-127">完成此命令的处理后，输入以下命令以获取租户中的预订邮箱列表：</span><span class="sxs-lookup"><span data-stu-id="88b4e-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="88b4e-128">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="88b4e-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="88b4e-129">请注意键入要永久删除的预定邮箱别名的确切名称。</span><span class="sxs-lookup"><span data-stu-id="88b4e-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="88b4e-130">若要验证是否已删除日历，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="88b4e-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="88b4e-131">已删除的日历不会显示在输出中。</span><span class="sxs-lookup"><span data-stu-id="88b4e-131">The deleted calendar will not appear in the output.</span></span>
