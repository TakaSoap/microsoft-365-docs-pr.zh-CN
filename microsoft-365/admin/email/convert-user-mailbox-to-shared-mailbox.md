---
title: 将用户邮箱转换为共享邮箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '了解如何将专用邮箱转换为可由多个用户访问的共享邮箱。 '
ms.openlocfilehash: 51817001b02c1dd5dd0e82f5795ef1a3f66bf7c7
ms.sourcegitcommit: 9ffa2fd25776726475e10148940987fa076bbd91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44162694"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>将用户邮箱转换为共享邮箱

将用户的邮箱转换为共享邮箱时，所有现有的电子邮件和日历都将保留。 只有在共享邮箱中，多个用户才能访问它，而不是一个人。 稍后，您可以将共享邮箱转换回用户（专用）邮箱。

**下面是您需要了解的一些真正重要的事项：**

- 在转换为共享邮箱之前，要转换的用户邮箱需要分配有许可证。 否则，将看不到用于转换邮箱的选项。 如果已删除许可证，请将其添加回来，以便可以转换邮箱。 将邮箱转换为共享邮箱后，可以从用户帐户中删除该许可证。

- 共享邮箱最高可包含50GB 的数据，而无需向其分配许可证。 若要保留的数据多于该数据，你需要分配给它的许可证。 您可能需要删除共享邮箱中的一组大型电子邮件（称为附件），以便将其缩小，以便您可以删除该许可证。

- 请勿删除旧用户的帐户。 这是锁定共享邮箱所必需的。 如果已删除用户帐户，请参阅[转换已删除用户的邮箱](#convert-the-mailbox-of-a-deleted-user)。

- 将邮箱转换为共享邮箱后，规则将保持不变。

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>使用 Exchange 管理中心转换邮箱
 
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 选择 "**收件人** \> " "**邮箱**"。

3. 选择用户邮箱。 在 "**转换为共享邮箱**" 下，选择 "**转换**"。

4. 如果邮箱小于50GB，则可以[从用户处删除许可证](../manage/remove-licenses-from-users.md)，然后停止付款。 请勿删除用户帐户。 共享邮箱需要将其作为定位点。 如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。 请参阅[从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。
    
5. 有关共享邮箱需要了解的其他信息，请参阅[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱](create-a-shared-mailbox.md)。

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a>使用 Microsoft 365 管理中心转换邮箱

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。

2. 选择要转换其邮箱的用户的名称。

3. 重置用户的密码。

> [!NOTE]
> 在邮箱转换过程中，不需要重置用户的密码。 但是，如果未重置密码，则在邮箱转换完成后，**原始用户名和密码将继续正常工作**。

4. 在 "**邮件**" 选项卡上的 "**其他操作**" 下，选择 "**转换为共享邮箱**"。 

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">活动用户</a>”页面。

2. 选择要转换其邮箱的用户。

3. 在右窗格中，展开 "**邮件设置**"。 在 "**更多设置**" 旁边，选择 "**转换为共享邮箱**"。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">活动用户</a>”页面。

2. 选择要转换其邮箱的用户。

3. 在右窗格中，展开 "**邮件设置**"。 在 "**更多设置**" 旁边，选择 "**转换为共享邮箱**"。

::: moniker-end


如果邮箱小于50GB，则可以[从用户处删除许可证](../manage/remove-licenses-from-users.md)，然后停止付款。 请勿删除用户的旧邮箱。 共享邮箱需要将其作为定位点。 如果要转换离开组织的员工的邮箱，则应执行其他步骤以确保他们无法再登录。 请参阅[从 Microsoft 365 删除以前的员工](../add-users/remove-former-employee.md)。
    
有关共享邮箱需要了解的其他信息，请参阅[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱](create-a-shared-mailbox.md)。


## <a name="convert-the-mailbox-of-a-deleted-user"></a>转换已删除用户的邮箱

假设您已删除用户帐户，现在想要将其旧邮箱转换为共享邮箱。 您需要执行以下操作：

1. [还原用户的帐户](../add-users/restore-user.md)。

2. 请确保向其分配了 Microsoft 365 许可证。

3. 重置用户的密码。
    
4. 等待20-30 分钟，以便重新创建其邮箱。
    
5. 现在，按照此页面上的说明将其邮箱转换为共享邮箱。
    
6. 完成此操作后，您可以从用户的邮箱中删除许可证。 请勿删除用户的旧邮箱。 共享邮箱需要将其作为定位点。
    
7. 将成员添加到共享邮箱。

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>将共享邮箱转换回用户的（专用）邮箱

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
   
2. 选择 "**共享****收件人** \> "。

3. 选择共享邮箱。 在 "**转换为常规邮箱**" 下，选择 "**转换**"。

4. 返回到管理中心。 在 "**用户**" 下，选择与旧共享邮箱相关联的用户帐户。 将许可证分配给帐户，然后重置密码。

   设置邮箱需要几分钟时间，但在此之后，将使用该帐户的人员可以转到。 登录时，他们将看到已在共享邮箱中使用的电子邮件和日历项目。

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>在混合环境中转换用户的邮箱

如果此共享邮箱位于混合环境中，**强烈建议**（几乎需要！）将用户邮箱移回本地，将用户邮箱转换为共享邮箱，然后将共享邮箱移回云。

原因如下：如果您在云中转换邮箱，可以对其进行转换，但本地仍认为邮箱是用户邮箱，因为新的现实不会同步回本地。

通常情况下，这并不是问题，但在某些情况下，本地属性（可能会认为邮箱是用户邮箱）可能会覆盖这些属性的新云版本，因此邮箱可能会转换回来。 这是一个问题，因为用户邮箱需要许可证**或在30天后软删除**！

我们解决了这种情况的大部分原因，但仍可能会发生，尽管不常这样做。 最好是安全的，并将邮箱移回本地。

> [!NOTE]
> 如果您是组织管理或收件人管理的一部分，则可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。 例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。

> [!TIP]
> 如果[共享邮箱意外转换为用户邮箱](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)，请参阅此支持解决方案中针对实例的解决方法
  
## <a name="related-articles"></a>相关文章

[关于共享邮箱](about-shared-mailboxes.md)

[创建共享邮箱](create-a-shared-mailbox.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)

[解决共享邮箱问题](resolve-issues-with-shared-mailboxes.md)
