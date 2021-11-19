---
title: 将就地保留置于 Exchange Online 中的软删除邮箱上
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: 了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。
ms.openlocfilehash: 67eacbd3b702f35fc8d71680238037d87ae529c8
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110819"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>将就地保留置于 Exchange Online 中的软删除邮箱上

了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。

> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，因此我们将宣布停用 In-Place Holds 在 Exchange 管理中心 (EAC) 。 从 2020 年 7 月 1 日开始，将无法在 Exchange Online 中创建新的 In-Place 保留。 但你仍然可以在 EAC 中In-Place或通过使用 PowerShell 中的 **Set-MailboxSearch** cmdlet 管理Exchange Online保留。 但是，从 2020 年 10 月 1 日起，你将无法管理In-Place保留。 您将仅在 EAC 中或通过使用 **Remove-MailboxSearch** cmdlet 删除它们。 有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。

You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? 如果已删除邮箱的保留期尚未过期，您可以将名为"软删除邮箱" (的已删除邮箱In-Place"保留"，) 使其变为非活动邮箱。 An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. 邮箱变为非活动状态后，可以使用邮箱中的电子数据展示工具搜索Microsoft 365 合规中心。

> [!NOTE]
> 在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着该邮箱可以在删除后 30 天内进行恢复（或变为非活动邮箱）。30 天后，软删除邮箱将标记为永久删除并且无法恢复或变为非活动邮箱。

## <a name="requirements-for-in-place-holds"></a>保留In-Place要求

- 您必须使用 **New-MailboxSearch** cmdlet 在Windows PowerShell软删除In-Place保留邮箱。 不能使用 SharePoint Online 中的 Exchange 管理中心 (EAC) 或电子数据展示中心。

- 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 运行以下命令获取组织中软删除邮箱的标识信息。

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 有关非活动邮箱的信息，请参阅 [了解非活动邮箱](inactive-mailboxes-in-office-365.md)。

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>将就地保留置于软删除邮箱以使其变为非活动邮箱

使用 **New-MailboxSearch** cmdlet 将软删除邮箱变为非活动邮箱。有关详细信息，请参阅 [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)。

1. 创建包含软删除邮箱的属性的变量。

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 在上一个命令中，使用 **DistinguishedName** 或 **ExchangeGuid** 属性的值来标识软删除的邮箱。 这些属性对于组织中的每个邮箱都是唯一的，但活动邮箱和软删除邮箱可能具有相同的主 SMTP 地址。

2. 创建就地保留并将其置于软删除邮箱上。在此示例中，未指定保留持续时间。这意味着项目将被无限期保留或一直保留到将该保留从非活动邮箱中删除为止。

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   还可以在创建就地保留时指定保留持续时间。此示例保留非活动邮箱中的项目近 7 年。

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 一段时间后，运行下列命令之一，验证软删除邮箱是否为非活动邮箱。

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    或

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>详细信息

在将软删除邮箱变为非活动邮箱后，有多种方法可以管理该邮箱。有关详细信息，请参阅：

- [更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)

- [恢复非活动邮箱](recover-an-inactive-mailbox.md)

- [还原非活动邮箱](restore-an-inactive-mailbox.md)

- [通过删除保留 (](delete-an-inactive-mailbox.md) 删除非活动邮箱) 