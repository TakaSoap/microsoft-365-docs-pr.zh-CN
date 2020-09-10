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
ms.openlocfilehash: 815aa3a859db15364aa18d3550001a28d085b711
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419268"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>打开或关闭 Microsoft 预订

可以为您的整个组织或特定用户打开或关闭预订。 为用户启用预订时，他们可以创建预订页面，创建日历，并允许其他人与他们一起预订时间。

> [!NOTE]
> 这些部分中所述的管理控件不适用于由世纪互联运营的 Office 365 (中国) 客户。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心为你的组织打开或关闭预订

1. 以全局管理员身份登录到 Microsoft 365 管理中心。

2. 在管理中心中，转到 " **设置**" "设置"   \> **Settings** ，然后选择 "**预订**"。

3. 选中 " **允许您的组织使用预订** 为您的组织启用或禁用预订" 的复选框。

   > [!NOTE]
   > 关闭预订将禁用对该服务的所有访问，包括创建和管理预订页面。

4. 选择 " **保存更改**"。

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>使用 PowerShell 为你的组织启用或禁用预订

若要使用 PowerShell cmdlet [set-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)为您的组织打开或关闭预订，请 [连接到 Exchange Online PowerShell]() 并运行以下命令：

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>为单个用户打开或关闭预订

您可以为单个用户禁用预订。

1. 转到 "Microsoft 365 管理中心"，然后选择 " **用户** \> **活动用户**"。

1. 选择所需的用户，然后选择 " **许可证和应用**"。

1. 展开 " **应用程序** "，并清除 Microsoft 预定的复选框。

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>在共享忙/闲信息之前需要员工批准

管理员可以要求组织中的员工在通过预订共享其可用性信息之前进行选择，然后才能通过预定页面 bookable。 此设置在 Microsoft 365 管理中心的 " **设置** \> **设置** \> **预订**" 下提供。

如果启用此设置，则在预订日历中添加为员工的员工将在收到的电子邮件通知中找到 "批准/拒绝" 链接。

此功能将从全球范围向 Microsoft 365 客户逐步推出。 如果在 Microsoft 365 管理中心中未看到此选项，请稍后再查看。

## <a name="block-social-sharing-options"></a>阻止社交共享选项

管理员可以控制如何在社交网络中共享预订页面。 此设置在 Microsoft 365 管理中心的 " **设置** \> **设置** \> **预订**" 下提供。

此功能将从全球范围向 Microsoft 365 客户逐步推出。 如果在 Microsoft 365 管理中心中未看到此选项，请稍后再查看。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>仅允许所选用户创建预定日历

通过使用策略限制，可以限制许可用户能够创建预定日历。 您必须首先为您的整个组织启用预订。 您组织中的所有用户都将拥有预订许可证，但只有策略中包括的用户才可以创建预订日历，并对可以访问他们所创建的日历的人员拥有完全控制权限。

此策略中包含的用户可以创建新的预订日历，并可作为员工添加到任何容量 (包括管理员角色) 现有的预订日历中。 不包含在此策略中的用户将不能创建新的预订日历，并将在尝试执行此操作时收到错误消息。

您需要使用 Exchange Online PowerShell 运行以下命令。 有关运行 Exchange Online cmdlet 的详细信息，请参阅 [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

> [!IMPORTANT]
> 下面的步骤假定您的组织中没有创建任何其他 Outlook Web App (OWA) 邮箱策略。

1. 为应允许创建预订日历的用户创建新的邮箱策略。 默认情况下，默认情况下允许创建 (的预订日历：新的邮箱策略。 ) 

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   有关详细信息，请参阅 [set-owamailboxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)。

2. 通过对要授予其创建预订日历的权限的每个用户运行此命令，将此策略分配给相关用户。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   有关详细信息，请参阅 [set-casmailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)。

3. 可选：如果要对组织中的所有其他用户禁用预订，请运行此命令。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   有关详细信息，请参阅 [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)。

有关 OWA 邮箱策略的详细信息，请参阅以下主题：

- [在 Exchange Online 中创建 web 邮箱策略的 Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [在 Exchange Online 中的邮箱上应用或删除 Outlook web 上的 Outlook 邮箱策略](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)