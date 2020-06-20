---
title: 还原非活动邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 了解如何将非活动邮箱的内容还原（或合并）到 Office 365 中的现有邮箱。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ae3927aaaba64711cdcc3362399b109f228cb12
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818932"
---
# <a name="restore-an-inactive-mailbox"></a>还原非活动邮箱

非活动邮箱（一种软删除的邮箱类型）用于在离开组织后保留前一个员工的电子邮件。 如果另一名员工接替离职员工的工作职责，或者该员工回到您的组织，有两种方法可以将非活动邮箱的内容提供给用户：
  
- **Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.

- **恢复非活动邮箱** 如果离职的员工回到您的组织，或者如果某位新员工要接替离职员工的工作职责，则可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。 恢复后，非活动邮箱不再存在。 有关分步过程，请参阅[在 Office 365 中恢复非活动邮箱](recover-an-inactive-mailbox.md)。

有关还原和恢复非活动邮箱之间的差异的更多详细信息，请参阅本文中的**详细信息**一节。
  
## <a name="requirements-to-restore-an-inactive-mailbox"></a>还原非活动邮箱的要求

- 您必须使用 Exchange Online PowerShell 来还原非活动邮箱。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。

- 在 Exchange Online PowerShell 中运行以下命令，以获取组织中非活动邮箱的标识信息。

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     使用此命令返回的信息来还原特定的非活动邮箱。

- 有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。

## <a name="restore-an-inactive-mailbox"></a>还原非活动邮箱

Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. 创建包含非活动邮箱的属性的变量。

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.
  
2. Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process. 

    本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中一个名为"非活动邮箱"的文件夹。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>从非活动邮箱还原存档

If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.
  
1. 创建包含非活动邮箱的属性的变量。

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a>详细信息

- **恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。 相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。 非活动邮箱将保留，并且仍保留非活动状态。 对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。 仍然可以使用[内容搜索工具](content-search.md)搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后恢复或删除它。

- **How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **使用诉讼保留或 Microsoft 365 保留策略保留非活动邮箱内容。** 如果要在还原非活动邮箱后保留该邮箱的状态，可以在还原非活动邮箱之前将目标邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)或应用[Microsoft 365 保留策略](retention-policies.md)。 这样可以防止在将非活动邮箱还原到目标邮箱之后，永久删除非活动邮箱中的任何项目。

- **在还原非活动邮箱之前，在目标邮箱上启用保留挂起功能。** 由于非活动邮箱中的邮箱项目可能已过时，您可能会考虑在还原非活动邮箱之前在目标邮箱上启用保留挂起功能。 将邮箱置于保留挂起状态时，在移除保留挂起或保留挂起期到期之前，将不会处理向其分配的保留策略。 这使目标邮箱的所有者有时间管理非活动邮箱中的邮件。 否则，保留策略可能会删除根据为目标邮箱配置的保留设置已到期的旧项目，或将项目移动到存档邮箱（如果已启用）中。 有关详细信息，请参阅[在 Exchange Online 中将邮箱置于保留挂起](https://go.microsoft.com/fwlink/?linkid=856300)状态。

- **AllowLegacyDNMismatch 开关有什么作用？** 在前面还原非活动邮箱的示例中， **AllowLegacyDNMismatch** 开关用来允许将非活动邮箱还原到不同的目标邮箱。 在典型的还原方案中，目标是还原源邮箱和目标邮箱为同一个邮箱的内容。 因此，默认情况下， **new-mailboxrestorerequest** cmdlet 会进行检查以确保源邮箱和目标邮箱上的**LegacyExchangeDN**属性值相同。 此检查可防止您将源邮箱意外还原到错误的目标邮箱中。 如果您尝试在不使用 **AllowLegacyDNMismatch** 开关的情况下还原非活动邮箱，则当源邮箱和目标邮箱具有不同的 **LegacyExchangeDN** 属性值时，该命令可能会失败。

- **You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox. 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  通过运行此命令，还可以将非活动的主邮箱还原到目标邮箱的存档中。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.

    **不使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**

    ![不使用 TargetRootFolder 参数时的屏幕截图](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**

    ![使用 TargetRootFolder 参数时的屏幕截图](../media/300da592-7323-48db-b8a4-07012259d113.png)
