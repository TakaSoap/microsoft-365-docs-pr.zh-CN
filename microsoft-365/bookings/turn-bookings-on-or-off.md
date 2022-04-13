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
description: 了解如何在Microsoft 365中获取对Microsoft Bookings的访问权限。
ms.openlocfilehash: 28398faba7c21b6d3cce84063934268dad11fd64
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823071"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>打开或关闭 Microsoft Bookings

> [!NOTE]
> 本文可帮助你与最新版本的Microsoft Bookings交互。 以前的版本将在未来几个月内停用。

本文适用于管理员。 

可以为整个组织或特定用户打开或关闭Bookings。 为用户打开Bookings时，他们可以创建Bookings页、创建日历，并允许其他人与他们一起预订时间。

> [!NOTE]
> 这些部分中所述的管理控件不适用于由 21Vianet (中国) 客户运营的Office 365。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>使用Microsoft 365 管理中心为组织打开或关闭Bookings

1. 以全局管理员身份登录到Microsoft 365 管理中心。

2. 在管理中心，转到 **设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**组织设置**</a>。

3. 选中 **“允许组织使用Bookings** 为组织启用或禁用Bookings的复选框。

   > [!NOTE]
   > 关闭Bookings将禁用对服务的所有访问，包括创建和管理Bookings页。

4. 选择“保存更改”。

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>使用 PowerShell 为组织打开或关闭Bookings

若要使用 PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) 为组织打开或关闭Bookings，[请连接Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 并运行以下命令：

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="granular-controls"></a>粒度控件

使用以下设置控制谁可以使用Bookings，确定共享哪些Bookings信息，以及员工是否需要审批才能添加到预订日历。

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="屏幕截图：设置，用于控制谁可以使用Bookings、确定共享哪些Bookings信息以及员工批准":::

### <a name="block-bookings-from-outside-your-organization"></a>阻止组织外部的预订

可以设置Bookings以便只有组织中的人员才能预订约会。 只有组织中已登录并经过身份验证的用户才能预订约会。

### <a name="block-social-sharing-options"></a>阻止社交共享选项

你可以控制预订页面在社交网络上的共享方式。 此设置在 设置 **Org 设置** -> 下 **的Microsoft 365 管理中心** -> 中可用 **Bookings**。

### <a name="block-sharing-staff-details-with-customers"></a>阻止与客户共享员工详细信息

员工详细信息（如联系人信息）永远不会通过电子邮件或任何其他通信发送给客户。

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>在共享忙/闲信息之前，需要员工批准

你可以要求组织中的员工在通过Bookings共享可用性信息之前选择加入，然后才能通过预订页面预订。

启用此设置后，在预订日历中添加为工作人员的用户将收到一封电子邮件，其中包含“ **批准/拒绝** 请求”链接。

## <a name="restrict-collection-of-customer-data"></a>限制客户数据的收集

出于符合性原因，你可能不想收集一些客户信息。 如果选中上述任一选项的复选框，这些字段将不会包含在向客户端或客户显示的任何表单上。

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="屏幕截图：选择复选框以帮助防止客户与你共享敏感数据":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>为单个用户打开或关闭Bookings

可以为单个用户禁用Bookings。

1. 转到Microsoft 365 管理中心，然后选择 **“用户** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**活动用户**</a>”。

1. 选择所需的用户，然后选择 **“许可证”和“应用**”。

1. 展开 **应用** 并清除Microsoft Bookings复选框。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>仅允许所选用户创建Bookings日历

通过使用策略限制，可以限制许可用户创建Bookings日历。 必须首先为整个组织启用Bookings。 组织中的所有用户都将拥有Bookings许可证，但只有策略中包含的用户才能创建Bookings日历，并完全控制谁可以访问他们创建的日历。

此策略中包含的用户可以创建新的Bookings日历，并且可以添加为任何容量 (（包括现有Bookings日历) 管理员角色）中的工作人员。 未包含在此策略中的用户将无法创建新的Bookings日历，如果尝试这样做，则会收到错误消息。

需要使用 Exchange Online PowerShell 运行以下命令。 有关运行Exchange Online cmdlet 的详细信息，请[参阅连接Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

> [!IMPORTANT]
> 以下步骤假定组织中未创建其他Outlook Web App (OWA) 邮箱策略。

1. 为应允许创建Bookings日历的用户创建新的邮箱策略。 默认情况下，新邮箱策略允许创建 (Bookings日历。) 

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   有关详细信息，请参阅 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy)。

2. 通过为要授予创建Bookings日历的权限的每个用户运行此命令，将此策略分配给相关用户。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   有关详细信息，请参阅 [Set-CASMailbox](/powershell/module/exchange/set-casmailbox)。

3. 可选：如果要为组织中所有其他用户禁用Bookings，请运行此命令。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   有关详细信息，请参阅 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。

有关 OWA 邮箱策略的详细信息，请查看以下主题：

- [在Exchange Online中创建Outlook 网页版邮箱策略](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [在邮箱中应用或删除Outlook 网页版邮箱策略Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
