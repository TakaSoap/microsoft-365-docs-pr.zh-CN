---
title: 删除预订日历
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: 使用 Microsoft 365 管理中心或 Windows PowerShell删除 Bookings 日历。
ms.openlocfilehash: 21fc7b9994ffd7f76ed04000a50bd0ee8f7f167e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034087"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="f19f2-103">删除 Bookings 中的预订日历</span><span class="sxs-lookup"><span data-stu-id="f19f2-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="f19f2-104">本文介绍如何删除不需要的预订日历。</span><span class="sxs-lookup"><span data-stu-id="f19f2-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="f19f2-105">可以在 Microsoft 365 管理中心中删除预订日历，或使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f19f2-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="f19f2-106">Bookings 日历是 Exchange Online 中的邮箱，因此删除相应的用户帐户以删除预订日历。</span><span class="sxs-lookup"><span data-stu-id="f19f2-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f19f2-107">必须使用本主题中的 PowerShell 说明删除在 2017 年或之前创建的所有预订日历。</span><span class="sxs-lookup"><span data-stu-id="f19f2-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="f19f2-108">在 2018 年或之后创建的所有预订日历都可以在 Microsoft 365 管理中心中删除。</span><span class="sxs-lookup"><span data-stu-id="f19f2-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f19f2-109">预订日历是存储有关该预订日历和数据的所有相关信息的位置，包括：</span><span class="sxs-lookup"><span data-stu-id="f19f2-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="f19f2-110">创建预订日历时添加的业务信息、徽标和工作时间</span><span class="sxs-lookup"><span data-stu-id="f19f2-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="f19f2-111">创建预订日历时添加的相关员工和服务</span><span class="sxs-lookup"><span data-stu-id="f19f2-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="f19f2-112">创建预订日历后添加到预订日历的所有预订和请假约会。</span><span class="sxs-lookup"><span data-stu-id="f19f2-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="f19f2-113">一旦删除了预订日历，此其他信息也会永久删除且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="f19f2-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f19f2-114">删除 Microsoft 365 管理中心中的预订日历</span><span class="sxs-lookup"><span data-stu-id="f19f2-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f19f2-115">转到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="f19f2-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="f19f2-116">在管理中心，选择" **用户** "。</span><span class="sxs-lookup"><span data-stu-id="f19f2-116">In the Admin center, select **Users**.</span></span>

   ![Microsoft 365 管理中心中用户 UI 的图像](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="f19f2-118">在" **活动用户**"页面上，选择要删除的用户的姓名，然后选择" **删除用户**"。</span><span class="sxs-lookup"><span data-stu-id="f19f2-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Microsoft 365 管理中心中删除用户 UI 的图像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="f19f2-120">使用 Exchange Online PowerShell 删除预订日历</span><span class="sxs-lookup"><span data-stu-id="f19f2-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="f19f2-121">有关 [连接到 Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) 的先决条件和指南，请参阅连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f19f2-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="f19f2-122">若要执行这些步骤，您必须使用活动的 Microsoft PowerShell 命令窗口，通过选择"以管理员方式运行"选项运行。</span><span class="sxs-lookup"><span data-stu-id="f19f2-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="f19f2-123">在 Windows PowerShell 窗口中，通过运行以下命令加载 EXO V2 模块：</span><span class="sxs-lookup"><span data-stu-id="f19f2-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="f19f2-124">如果已[安装 EXO V2 模块](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)，则上一个命令将按书面工作。</span><span class="sxs-lookup"><span data-stu-id="f19f2-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="f19f2-125">需要运行的命令使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="f19f2-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="f19f2-126">_\<UPN\>_ 是采用用户主体名称格式的帐户（例如 `john@contoso.com`）。</span><span class="sxs-lookup"><span data-stu-id="f19f2-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="f19f2-127">系统提示时，使用租户管理员凭据登录托管要永久删除的预订日历的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="f19f2-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="f19f2-128">处理完此命令后，输入以下命令，获取租户中的预订邮箱列表：</span><span class="sxs-lookup"><span data-stu-id="f19f2-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="f19f2-129">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f19f2-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="f19f2-130">请注意，键入要永久删除的预订邮箱别名的确切名称。</span><span class="sxs-lookup"><span data-stu-id="f19f2-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="f19f2-131">若要验证日历是否已删除，请输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="f19f2-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="f19f2-132">已删除的日历不会显示在输出中。</span><span class="sxs-lookup"><span data-stu-id="f19f2-132">The deleted calendar will not appear in the output.</span></span>
