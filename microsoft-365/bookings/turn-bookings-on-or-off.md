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
ms.openlocfilehash: cc0352166bf7cd20cfa10542d57da9fbd5b160f7
ms.sourcegitcommit: c41e3f48451e2d7b45901faee21b1e1d19a16688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2021
ms.locfileid: "58823813"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>打开或关闭 Microsoft Bookings

可以针对整个组织或特定用户打开或关闭预订。 当你为用户打开 Bookings 时，他们可以创建 Bookings 页面、创建日历并允许其他人预订时间。

> [!NOTE]
> 这些部分中所述的管理控制不适用于由世纪Office 365中国 (运营) 客户。

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>使用"设置"功能为组织打开或关闭Microsoft 365 管理中心

1. 以全局管理员Microsoft 365 管理中心登录帐户。

2. 在管理中心，转到"设置  ****   \> **组织设置** 并选择 **"预订"。**

3. 选中"允许 **组织使用 Bookings** 为组织启用或禁用 Bookings"复选框。

   > [!NOTE]
   > 关闭 Bookings 将禁用对服务的所有访问，包括创建和管理 Bookings 页面。

4. 选择“保存更改”。

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>使用 PowerShell 为组织打开或关闭 Bookings

若要使用 PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)为组织打开或关闭 Bookings，连接 Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)并运行以下命令：

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>为单个用户打开或关闭 Bookings

你可以为单个用户禁用 Bookings。

1. 转到"Microsoft 365 管理中心"，**然后选择"用户** \> **""活动用户"。**

1. 选择所需的用户，然后选择许可证 **和应用**。

1. 展开 **应用** 并清除 Microsoft Bookings 的复选框。

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>共享忙/闲信息之前需要员工批准

管理员可以要求其组织的员工在通过 Bookings 共享其可用性信息之前以及可以通过预订页面进行预订之前选择加入。 此设置在 Bookings Microsoft 365 管理中心下 \> **设置设置** \> **可用**。

启用此设置后，在预订日历中作为员工添加的员工将在他们收到的电子邮件通知中查找"批准/拒绝"链接。

## <a name="block-social-sharing-options"></a>阻止社交共享选项

管理员可以控制如何在社交网络上共享预订页面。 此设置在 Bookings Microsoft 365 管理中心下 \> **设置设置** \> **可用**。

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>仅允许所选用户创建 Bookings 日历

通过使用策略限制，你可以限制许可用户创建 Bookings 日历。 必须先为整个组织启用 Bookings。 你组织中所有用户都将拥有 Bookings 许可证，但只有策略中包含的用户才能创建 Bookings 日历，并完全控制谁可以访问他们创建的日历。

此策略中包含的用户可以创建新的 Bookings 日历，并可以添加为任何容量的用户 (包括管理员角色) 现有 Bookings 日历。 未包含在此策略中的用户将无法创建新的 Bookings 日历，并且如果他们尝试这样做，将收到错误消息。

你需要使用 PowerShell 运行以下Exchange Online。 有关运行 cmdlet Exchange Online，请参阅 连接 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> 以下步骤假定尚未在组织中Outlook Web App (其他) OWA 邮箱策略。

1. 为应允许其创建 Bookings 日历的用户创建新的邮箱策略。  (新邮箱策略默认情况下允许创建 Bookings 日历。) 

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   有关详细信息，请参阅 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy)。

2. 通过为要授予创建 Bookings 日历权限的每个用户运行此命令，将此策略分配给相关用户。

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   有关详细信息，请参阅 [Set-CASMailbox](/powershell/module/exchange/set-casmailbox)。

3. 可选：如果要为组织中所有其他用户禁用 Bookings，请运行此命令。

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   有关详细信息，请参阅 [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)。

有关 OWA 邮箱策略详细信息，请查看以下主题：

- [在Outlook 网页版邮箱策略Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [应用或删除Outlook 网页版邮箱的邮箱策略Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)