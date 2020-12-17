---
title: 将用户邮箱转换为共享邮箱
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: '了解如何将专用邮箱转换为多个用户访问的共享邮箱。 '
ms.openlocfilehash: fa8e37b5e924f1b38755a953f40d8b70011213d0
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698275"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>将用户邮箱转换为共享邮箱

将用户的邮箱转换为共享邮箱时，将保留所有现有电子邮件和日历。 现在，它才在一个共享邮箱中，多个用户将能够访问该邮箱，而不是一个人。 稍后，可以将共享邮箱转换回专用 (用户) 邮箱。

**以下是您需要了解的一些非常重要的事情：**

- 要转换的用户邮箱需要分配有许可证，然后才能将其转换为共享邮箱。 否则，你将看不到转换邮箱的选项。 如果已删除许可证，请重新添加它，以便转换邮箱。 将邮箱转换为共享邮箱后，可以从用户帐户中删除许可证。

- 共享邮箱可具有多达 50 GB 的数据，而无需分配许可证。 要保留的数据超过此限制，需要为其分配许可证。 你可能需要从共享邮箱中删除一 (电子邮件，例如) 附件的电子邮件，以便你可以删除许可证。

- 不要删除旧用户的帐户。 这是定位共享邮箱所需的。 如果已删除用户帐户，请参阅"转换已删除[用户的邮箱"。](#convert-the-mailbox-of-a-deleted-user)

- 将邮箱转换为共享邮箱后，规则将保持不变。

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>使用 Exchange 管理中心转换邮箱
 
1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 选择 **"** \> **收件人邮箱"。**

3. 选择用户邮箱。 在 **"转换为共享邮箱"下，** 选择"**转换"。**

4. 如果邮箱小于 50 GB，可以从用户中删除许可证，[](../manage/remove-licenses-from-users.md)并停止付费。 不要删除用户帐户。 共享邮箱需要它作为定位标记。 如果要转换要离开组织的员工的邮箱，则应该采取其他步骤以确保他们不能再登录。 请参阅 [从 Microsoft 365 中删除以前的员工](../add-users/remove-former-employee.md)。
    
> [!NOTE]
> 无需在邮箱转换期间重置用户密码。 但是，如果未重置密码，则完成邮箱转换后，原始用户名和密码将继续工作。

有关共享邮箱需要了解的一切信息，请参阅"[关于共享](about-shared-mailboxes.md)邮箱和[创建共享邮箱"。](create-a-shared-mailbox.md)

> [!NOTE]
> 共享邮箱不需要单独的许可证。 但是，如果你想要启用就地存档或将就地保留或诉讼保留置于共享邮箱，则必须向邮箱分配带有 Exchange Online Archiving 的 Exchange Online 计划 1 或 Exchange Online 计划 2 许可证。


## <a name="convert-the-mailbox-of-a-deleted-user"></a>转换已删除用户的邮箱

假设你已删除用户帐户，现在你想要将其旧邮箱转换为共享邮箱。 以下是你需要执行哪些工作：

1. [还原用户帐户](../add-users/restore-user.md)。

2. 确保已为其分配 Microsoft 365 许可证。

3. 重置用户密码。
    
4. 等待 20-30 分钟，以重新创建其邮箱。
    
5. 现在按照此页面上的说明将其邮箱转换为共享邮箱。
    
6. 完成后，可以从用户的邮箱中删除许可证。 不要删除用户的旧邮箱。 共享邮箱需要它作为定位标记。
    
7. 向共享邮箱添加成员。


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>将共享邮箱转换回用户的专用 () 邮箱

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
   
2. 选择 **"收件人** \> **共享"。**

3. 选择共享邮箱。 在 **"转换为常规邮箱"下**，选择"**转换"。**

4. 返回到管理中心。 在 **"** 用户"下，选择与旧共享邮箱关联的用户帐户。 向帐户分配许可证，并重置密码。

   设置邮箱需要几分钟时间，但之后，将使用该帐户的人就可以了。 登录后，他们将看到共享邮箱中过去的电子邮件和日历项目。

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>在混合环境中转换用户邮箱

> [!NOTE] 
> 从 2018 年 10 月 11 日起，Exchange 混合部署支持在本地 Exchange Server 环境中从 Exchange Server 2013 累积更新 21 和 Exchange Server 2016 累积更新 10 开始创建远程共享邮箱。 可以使用新的 _-shared_ 参数直接创建或修改远程共享邮箱。 有关详细信息，请访问 [Cmdlet 创建或修改](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange)本地 Exchange 环境中远程共享邮箱。

如果此共享邮箱位于混合环境中，并且未属于上述方案，我们强烈建议 **(** 几乎需要！) 将用户邮箱移回本地，将用户邮箱转换为共享邮箱，然后将共享邮箱移回云。 

原因包括：如果你在云中转换邮箱，它可以被转换，但本地仍认为邮箱是用户邮箱，因为新现实不会同步回本地。

通常这不是问题，但在某些情况下，本地属性 (认为邮箱是用户邮箱) 可能会覆盖这些属性的新云版本，因此邮箱可能会转换回。 这是一个问题，因为用户邮箱需要许可证或在 **30** 天后软删除！

我们已解决出现此情况的原因，但仍可能发生此情况，尽管这种情况很少发生。 最好是安全的，并将邮箱移回本地，转换它，然后将共享邮箱移回云。 此建议的解决方案不会违反混合环境的许可协议，因为本地用户邮箱的存在只是临时的。 如果在内部部署组织中维护用户邮箱或共享邮箱，并且未将其移回云，则违反了许可证。


> [!NOTE]
> 如果您是组织管理或收件人管理角色组的成员，可以使用 Exchange 命令行管理程序将用户邮箱更改为本地共享邮箱。 例如，`Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`。

> [!TIP]
> 有关共享邮箱意外转换为用户邮箱的情况，请参阅此支持 [解决方案中的解决方法](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)。
  
## <a name="related-articles"></a>相关文章

[关于共享邮箱](about-shared-mailboxes.md)

[创建共享邮箱](create-a-shared-mailbox.md)

[配置共享邮箱](configure-a-shared-mailbox.md)

[从共享邮箱删除许可证](remove-license-from-shared-mailbox.md)

[解决共享邮箱问题](resolve-issues-with-shared-mailboxes.md)
