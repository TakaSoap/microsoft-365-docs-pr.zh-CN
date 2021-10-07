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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 了解如何将 (邮箱) 邮箱的内容还原到非活动邮箱中的现有邮箱Office 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b57a309ed686f2fe2aaee34fb3b89264a2de9812
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159774"
---
# <a name="restore-an-inactive-mailbox"></a>还原非活动邮箱

非活动 (邮箱邮箱是一种软删除) ，用于在前员工离开组织后保留其电子邮件。 如果另一名员工接替离职员工的工作职责，或者该员工回到您的组织，有两种方法可以将非活动邮箱的内容提供给用户：

- **还原非活动邮箱** 如果另一名员工接替离职员工的工作职责，或者如果另一个用户需要访问非活动邮箱的内容，您可以将非活动邮箱的内容还原（或 合并）到某个现有邮箱。您还可以从非活动邮箱还原存档。还原后，非活动邮箱将保留，并仍保留为非活动状态。本主题介绍还原非活动邮箱的过程。

- **恢复非活动邮箱** 如果离职的员工回到您的组织，或者如果某位新员工要接替离职员工的工作职责，则可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。 恢复后，非活动邮箱不再存在。 有关分步过程，请参阅恢复邮箱中的[非活动Office 365。](recover-an-inactive-mailbox.md)

有关 [还原和恢复](#more-information) 非活动邮箱之间的差异的更多详细信息，请参阅本文中的详细信息部分。

> [!NOTE]
> 无法恢复或还原使用自动扩展存档配置的非活动邮箱。 如果需要从具有自动扩展存档的非活动邮箱恢复数据，请使用内容搜索从邮箱导出数据，然后导入另一个邮箱。 有关说明，请参阅下列主题：
>
> - [内容搜索](content-search.md)
> - [导出内容搜索结果](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>还原非活动邮箱的要求

- 您必须使用 PowerShell Exchange Online还原非活动邮箱。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在 PowerShell Exchange Online以下命令，获取组织中非活动邮箱的标识信息。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  使用此命令返回的信息来还原特定的非活动邮箱。

- 有关非活动邮箱的信息，请参阅非活动[Office 365。](inactive-mailboxes-in-office-365.md)

## <a name="restore-inactive-mailboxes"></a>还原非活动邮箱

将 **New-MailboxRestoreRequest** cmdlet 与  _SourceMailbox_ 和  _TargetMailbox_ 参数一起使用，将非活动邮箱的内容还原到现有邮箱。有关使用此 cmdlet 的详细信息，请参阅 [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)。

1. 创建包含非活动邮箱的属性的变量。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。

2. 将非活动邮箱的内容还原到现有邮箱。非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   或者，可以指定要从非活动邮箱还原内容的目标邮箱中的顶级文件夹。如果指定的目标文件夹或目标文件夹结构在目标邮箱中不存在，将在还原过程中创建。

   本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中一个名为"非活动邮箱"的文件夹。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>从非活动邮箱还原存档

如果非活动邮箱具有存档邮箱，您还可以将其还原到现有邮箱的存档邮箱。 若要从非活动邮箱还原存档，您必须将 _SourceIsArchive_ 和 _TargetIsArchive_ 开关添加到用于还原非活动邮箱的命令。

1. 创建包含非活动邮箱的属性的变量。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。

2. 将非活动邮箱的存档（源存档）内容还原到现有邮箱的存档（目标存档）。在此示例中，将源存档的内容复制到目标邮箱的存档中一个名为"非活动邮箱存档"的文件夹。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>详细信息

- **恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。 相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。 非活动邮箱将保留，并且仍保留非活动状态。 对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。 仍可以使用内容搜索工具搜索非活动邮箱，其内容[](content-search.md)可以还原到另一个邮箱，也可以稍后恢复或删除。

- **如何查找非活动邮箱？** 要获取您组织中的非活动邮箱的列表，并显示可用于恢复非活动邮箱的信息，可以运行此命令。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **使用诉讼保留或Microsoft 365保留策略保留非活动邮箱内容。** 如果要在还原后保留非活动邮箱的状态，可以将目标邮箱置于诉讼保留状态，或在还原非活动邮箱之前应用[](create-a-litigation-hold.md)Microsoft 365[保留](retention.md)策略。 这样可以防止在将非活动邮箱还原到目标邮箱之后，永久删除非活动邮箱中的任何项目。

- **在还原非活动邮箱之前，在目标邮箱上启用保留挂起功能。** 由于非活动邮箱中的邮箱项目可能已过时，您可能会考虑在还原非活动邮箱之前在目标邮箱上启用保留挂起功能。 将邮箱置于保留挂起状态时，在移除保留挂起或保留挂起期到期之前，将不会处理向其分配的保留策略。 这使目标邮箱的所有者有时间管理非活动邮箱中的邮件。 否则，保留策略可能会删除根据为目标邮箱配置的保留设置已到期的旧项目，或将项目移动到存档邮箱（如果已启用）中。 有关详细信息，请参阅在邮箱[中将邮箱置于保留Exchange Online。](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)

- **AllowLegacyDNMismatch 开关有什么作用？** 在前面还原非活动邮箱的示例中， **AllowLegacyDNMismatch** 开关用来允许将非活动邮箱还原到不同的目标邮箱。 在典型的还原方案中，目标是还原源邮箱和目标邮箱为同一个邮箱的内容。 因此，默认情况下 **，New-MailboxRestoreRequest** cmdlet 会进行检查以确保源邮箱和目标邮箱上的 **LegacyExchangeDN** 属性的值相同。 此检查可防止您将源邮箱意外还原到错误的目标邮箱中。 如果您尝试在不使用 **AllowLegacyDNMismatch** 开关的情况下还原非活动邮箱，则当源邮箱和目标邮箱具有不同的 **LegacyExchangeDN** 属性值时，该命令可能会失败。

- **可以使用 New-MailboxRestoreRequest cmdlet 与其他参数实现非活动邮箱的其他还原方案。** 例如，您可以运行此命令，将非活动邮箱的存档还原到目标邮箱的主邮箱。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  通过运行此命令，还可以将非活动的主邮箱还原到目标邮箱的存档中。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **TargetRootFolder 参数有什么作用？** 如前面所述，您可以使用 **TargetRootFolder** 参数指定将向其还原非活动邮箱内容的目标邮箱中文件夹结构顶部的一个文件夹（也称为 根）。如果不使用此参数，非活动邮箱中的邮箱项目将合并到目标邮箱相应的默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。下图重点说明不使用和使用 **TargetRootFolder** 参数的区别。

  **不使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**

  ![使用 TargetRootFolder 参数时屏幕截图。](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**

  ![使用 TargetRootFolder 参数时屏幕截图。](../media/300da592-7323-48db-b8a4-07012259d113.png)