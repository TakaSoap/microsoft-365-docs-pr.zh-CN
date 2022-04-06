---
title: 打开或关闭 Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: 了解如何访问 Microsoft Bookings 中的Microsoft 365。
ms.openlocfilehash: 09fba96265bc3d2b67db9152f0c6020e10183314
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634792"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>打开或关闭 Microsoft Bookings

Bookings为整个组织或特定用户打开或关闭。 为用户Bookings时，他们可以创建Bookings页面、创建日历并允许其他人预订时间。

> [!NOTE]
> 这些部分中所述的管理控制措施不适用于由世纪Office 365中国 (运营) 客户。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>使用Bookings为组织打开或关闭Microsoft 365 管理中心

1. 以全局管理员Microsoft 365 管理中心登录帐户。

2. 在管理中心， **转到设置** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**"组织设置"**</a>。

3. 选中"允许组织 **使用** Bookings"复选框为Bookings启用或禁用策略。

   > [!NOTE]
   > 关闭Bookings将禁用对服务的所有访问，包括创建和管理Bookings页面。

4. 选择“保存更改”。

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>使用 Bookings启用或关闭组织的启用功能

若要Bookings PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) 为组织启用或关闭 连接，Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 并运行以下命令：

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

使用下面的设置来控制谁可以使用Bookings、决定共享哪些Bookings以及员工是否需要审批才能添加到 Booking 日历。

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="Screenshot： 设置 that allow you to control who can use Bookings， decide what Bookings info is shared and staff approval":::

### <a name="block-bookings-from-outside-your-organization"></a>阻止组织外部的预订

您可以设置Bookings，以便只有贵组织的人才能预订约会。 只有组织中已登录且经过身份验证的用户才能预订约会。

### <a name="block-social-sharing-options"></a>阻止社交共享选项

你可以控制如何在社交网络上共享预订页面。 此设置在 Microsoft 365 管理中心 -> **Org 设置设置下Bookings** -> 。

### <a name="block-sharing-staff-details-with-customers"></a>阻止与客户共享员工详细信息

员工详细信息（如联系人信息）绝不会通过电子邮件或其他通信发送给客户。

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>共享忙/闲信息之前需要员工批准

你可以要求你组织的员工先选择加入，然后才能通过 Bookings 共享其可用性信息，然后他们才能通过预订页面进行预订。

启用此设置后，在预订日历中作为员工添加的人员将收到一封电子邮件，并包含" **批准/拒绝请求"** 链接。

## <a name="restrict-collection-of-customer-data"></a>限制客户数据收集

出于合规性原因，你可能不希望收集一些客户信息。 If you select a checkbox for any of these options， these fields won't be included on any forms shown to your clients or customers.

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="Screenshot： Select the checkboxes to help prevent customers from sharing sensitive data with you":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>为Bookings用户打开或关闭该设置

您可以为单个Bookings禁用此策略。

1. 转到"Microsoft 365 管理中心"，然后选择"**用户"** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**"活动用户"**</a>。

1. 选择所需的用户，然后选择" **许可证和应用"**。

1. 展开 **"应用**"并清除"应用Microsoft Bookings。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>仅允许所选用户创建Bookings日历

通过使用策略限制，您可以限制许可用户能够创建Bookings日历。 必须先为整个Bookings启用启用。 组织所有用户都将拥有Bookings许可证，但只有策略中包含的用户才能创建 Bookings 日历，并完全控制谁可以访问他们创建的日历。

此策略中包含的用户可以创建新的 Bookings 日历，并可以添加为任何容量 (包括管理员角色角色) 现有 Bookings 日历。 未包含在此策略中的用户将无法创建新的日历Bookings，并且如果他们尝试这样做，将收到错误消息。

你需要使用 PowerShell 运行Exchange Online命令。 有关运行 cmdlet Exchange Online，请参阅 连接 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

> [!IMPORTANT]
> 以下步骤假定尚未在组织中Outlook Web App (其他) OWA 邮箱策略。

1. 为应允许其创建日历的用户创建新的Bookings策略。  (Bookings新邮箱策略默认允许创建日历。) 

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   有关详细信息，请参阅 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy)。

2. 通过为要授予创建日历权限的每个用户运行此命令，向Bookings分配此策略。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   有关详细信息，请参阅 [Set-CASMailbox](/powershell/module/exchange/set-casmailbox)。

3. 可选：如果要禁用组织中所有其他用户Bookings，请运行此命令。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   有关详细信息，请参阅 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。

有关 OWA 邮箱策略详细信息，请查看以下主题：

- [在Outlook 网页版邮箱策略Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [对邮箱中的Outlook 网页版应用或删除邮箱策略Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
