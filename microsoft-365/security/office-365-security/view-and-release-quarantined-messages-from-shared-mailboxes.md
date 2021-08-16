---
title: 查看并释放共享邮箱中的隔离邮件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 用户可以了解如何查看和操作发送到他们有权访问的共享邮箱的隔离邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 90c4476d2c882c98b6b24a738adc2d9e2a9d6244994bd8f82c36b0d1f544c488
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53883861"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>查看并释放共享邮箱中的隔离邮件

> [!NOTE]
> 本文中介绍的功能目前处于预览阶段，不可供所有人使用，并且可能会更改。

用户可以管理隔离邮件，其中他们是收件人之一，如在 EOP 中以用户方式查找并释放隔离 [邮件中所述](find-and-release-quarantined-messages-as-a-user.md)。 但是，用户 **对** 邮箱具有"完全访问"和"代理发送"或"代表发送"权限的共享邮箱 [呢，如](/exchange/collaboration-exo/shared-mailboxes)共享邮箱Exchange Online？

以前，用户能够管理发送到共享邮箱的隔离邮件，这要求管理员为共享邮箱启用自动映射 (管理员向用户授予对另一个邮箱) 的访问权限时，将默认启用自动映射。 但是，根据用户有权访问的邮箱的大小和数量，Outlook 尝试打开用户有权访问的所有邮箱时，性能可能会受到影响。  因此，许多管理员选择 [删除共享邮箱的自动映射](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。

现在，用户不再需要自动映射来管理发送到共享邮箱的隔离邮件。 它只起作用。 有两种不同的方法来访问发送到共享邮箱的隔离邮件：

- 如果管理员已启用反[](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)垃圾邮件策略中的最终用户垃圾邮件通知，则有权访问共享邮箱中的最终用户垃圾邮件通知的任何用户都可以单击通知中的"审阅"按钮，以转到 Microsoft 365 Defender门户中的隔离邮箱。 请注意，此方法仅允许用户管理发送到共享邮箱的隔离邮件。 用户无法在此上下文中管理自己的隔离邮件。
- 用户可以转到[Microsoft 365 Defender 门户中的隔离。](find-and-release-quarantined-messages-as-a-user.md) 默认情况下，只显示发送给用户的邮件。 但是，用户可以将"排序结果" ("邮件 **ID"** 按钮（默认为) ）更改为"收件人电子邮件地址"，输入共享邮箱电子邮件地址，然后单击"刷新"查看发送到共享邮箱的隔离邮件。

  ![按收件人电子邮件地址对隔离邮件进行排序。](../../media/quarantine-sort-results-by-recipient-email-address.png)

无论使用哪种方法，用户都可以通过包含隔离邮件的 **"收件人** "列来避免混淆。 要显示的最大列数为 7，因此用户需要单击"修改列"，删除现有列 (例如，"策略类型 **) "，** 选择"收件人"，然后单击"保存"或"另存为 **默认值"。** 

  ![删除"策略类型"列，并添加"收件人"列以隔离。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>要记住的事项

- 第一个处理隔离邮件的用户决定使用共享邮箱的所有人的邮件的传递。 例如，如果 10 个用户访问共享邮箱，而用户决定删除隔离邮件，则删除所有 10 个用户的邮件。 同样，如果用户决定释放邮件，邮件将释放到共享邮箱，并且共享邮箱的所有其他用户访问。

- 目前，"**阻止发件人**"按钮在发送到共享邮箱的隔离邮件的"详细信息"飞出控件中不可用。

- 对于共享邮箱的隔离操作，如果使用嵌套安全组授予对共享邮箱的访问权限，建议嵌套组不要超过两个级别。 例如，组 A 是组 B 的成员，它是组 C 的成员。若要向共享邮箱分配权限，请勿将用户添加到组 A，然后将组 C 分配给共享邮箱。  

- 若要在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中管理共享邮箱的隔离邮件，最终用户需要将 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) cmdlet 与共享邮箱电子邮件地址一同用于 _RecipientAddress_ 参数的值，以标识这些邮件。 例如：

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  然后，最终用户可以从列表中选择隔离邮件进行查看或采取措施。

  本示例显示发送到共享邮箱的所有隔离邮件，然后从隔离邮箱中释放列表中的第一封邮件 (列表中的第一封邮件为 0，第二封邮件为 1，以) 等。

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  有关语法和参数的详细信息，请参阅下列主题：

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
