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
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422438"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>在预订中删除预定日历

本文介绍如何删除不需要的预订日历。 您可以删除 Microsoft 365 管理中心中的预定日历，也可以使用 PowerShell。 预订日历是 Exchange Online 中的邮箱，因此您可以删除相应的用户帐户以删除预定日历。

> [!IMPORTANT]
> 您在2017或之前创建的所有预订日历必须使用本主题的 PowerShell 说明删除。 可以在 Microsoft 365 管理中心中删除在2018或之后创建的所有预订日历。

预订日历是存储有关该预订日历和数据的所有相关信息，包括：

- 创建预订日历时添加的业务信息、徽标和工作时间
- 创建预订日历时添加的相关人员和服务
- 在创建预订日历后添加到该预订日历的所有预订和休息时间的约会。

> [!WARNING]
> 一旦删除预订日历，此附加信息也会永久删除且无法恢复。

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中删除预定日历

1. 转到 Microsoft 365 管理中心。

1. 在管理中心，选择" **用户** "。

   ![Microsoft 365 管理中心中的用户 UI 的图像](../media/bookings-admin-center-users.png)

1. 在" **活动用户**"页面上，选择要删除的用户的姓名，然后选择" **删除用户**"。

   ![Microsoft 365 管理中心中的 Delete User UI 的图像](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>使用 Exchange Online PowerShell 删除预定日历

有关连接到 Exchange Online PowerShell 的先决条件和指南，请参阅 [连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 。

若要执行这些步骤，您必须使用通过选择 "以管理员身份运行" 选项运行的活动 Microsoft PowerShell 命令窗口。

1. 输入以下命令：

   ```PowerShell
    $user = get-credential
   ```

1. 出现提示时，请使用租户管理员凭据登录到托管要永久删除的预定日历的 Microsoft 365 租户。

1. 在 PowerShell 命令提示符处，输入以下命令：

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. 输入以下命令：

   ```PowerShell
    Import-PSSession $s
   ```

1. 完成此命令的处理后，输入以下命令以获取租户中的预订邮箱列表：

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. 键入以下命令：

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > 请注意键入要永久删除的预定邮箱别名的确切名称。

1. 若要验证是否已删除日历，请输入以下命令：

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   已删除的日历不会显示在输出中。
