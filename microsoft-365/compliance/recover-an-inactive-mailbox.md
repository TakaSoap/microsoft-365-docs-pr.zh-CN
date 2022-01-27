---
title: 恢复非活动邮箱
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: 了解如何通过将其转换为包含非活动邮箱内容的新邮箱Office 365恢复非活动邮箱的内容。
ms.openlocfilehash: ce09d218d86e7cd949da1df80cc75a19fce64159
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241499"
---
# <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

非活动邮箱（一种软删除的邮箱）用于在之前员工离开您的组织后保留他/她的电子邮件。 如果该员工回到您的组织，或者如果另一名员工承担以前员工的工作职责，则有两种方法可以使非活动邮箱的内容可供用户使用：

- **恢复非活动邮箱。** 如果以前的员工回到您的组织，或者如果聘用了一位新员工来承担前员工的工作职责，您可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为包含非活动邮箱内容的新活动邮箱。 恢复后，非活动邮箱不再存在。 本主题中的过程描述了此方法。

- **还原非活动邮箱。** 如果另一名员工承担以前员工的工作职责，或者另一个用户需要访问非活动邮箱的内容，您可以还原 (或将) 非活动邮箱的内容合并到现有邮箱。 您还可以从非活动邮箱还原存档。 有关此方法的过程，请参阅 Restore [an inactive mailbox in Office 365](restore-an-inactive-mailbox.md)。

有关恢复和还原非活动邮箱之间的差异的详细信息，以及恢复非活动邮箱后所发生情况的描述，请参阅[详细信息](#more-information)部分。

> [!NOTE]
> 无法恢复或还原使用自动扩展存档配置的非活动邮箱。 如果需要从具有自动扩展存档的非活动邮箱恢复数据，请使用内容搜索从邮箱导出数据，然后导入另一个邮箱。 有关说明，请参阅下列主题：
>
> - [内容搜索](content-search.md)
> - [导出内容搜索结果](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>恢复非活动邮箱的要求

- 您必须使用 PowerShell Exchange Online恢复非活动邮箱。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 运行以下命令获取组织中非活动邮箱的标识信息。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  使用此命令返回的信息来恢复特定的非活动邮箱。

## <a name="recover-inactive-mailboxes"></a>恢复非活动邮箱

使用 **New-Mailbox** cmdlet 和  *InactiveMailbox*  参数恢复非活动邮箱。

1. 创建包含非活动邮箱的属性的变量。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。

2. 此示例使用在上一个命令中获取的属性，并将非活动邮箱恢复到用户 Ann Beebe 的活动邮箱。 请确保为  *Name*  和  *MicrosoftOnlineServicesID*  参数指定的值在组织中是唯一的。

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   恢复的非活动邮箱的主 SMTP 地址的值与  *MicrosoftOnlineServicesID*  参数指定的值相同。

恢复非活动邮箱后，还会创建一个新的用户帐户。 您需要通过分配许可证来激活此用户帐户。 若要在许可证分配Microsoft 365 管理中心，请参阅同时[添加用户和分配许可证](../admin/add-users/add-users.md)。

## <a name="more-information"></a>详细信息

- **恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。 相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。 非活动邮箱将保留，并且仍保留非活动状态。 对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。 仍可以使用就地电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。

- **恢复非活动邮箱时，会发生什么情况？** 恢复非活动邮箱时，将发生以下事件：

  - 已应用于非活动邮箱的保留将基于恢复之前应用于非活动邮箱的保留类型进行更改或删除。

    - **诉讼保留。** 如果对非活动邮箱启用了诉讼保留，将从恢复的邮箱中删除诉讼保留。

    - **就地保留** In-Place从恢复的邮箱中删除保留。 这意味着恢复的邮箱将从任何保留或电子数据展示In-Place中删除In-Place源邮箱。

    - **Microsoft 365保留锁定设置保留策略。** 如果非活动邮箱已分配给保留锁定策略 (保留策略 *) ，* 则恢复的邮箱将分配到同一锁定保留策略。 有关锁定的保留策略详细信息，请参阅 [使用保留锁定来限制对保留策略[和保留标签策略的更改](retention-preservation-lock.md)。

    - **Microsoft 365保留策略，而不使用保留锁定。** 非活动邮箱将从任何已Microsoft 365的保留策略中删除。 但是，恢复的邮箱上启用了诉讼保留，以防止基于删除超过特定期限的内容的任何组织范围的保留策略删除邮箱内容。 您可以保留诉讼保留或删除诉讼保留。 有关详细信息，请参阅创建 [诉讼保留](create-a-litigation-hold.md)。

  - 单个项目恢复期间（由 **RetainDeletedItemsFor** 邮箱属性定义）设置为 30 天。通常情况下，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。将此值设置为最大值 30 天，可留出更多时间从非活动邮箱中恢复任何已永久删除（或清除）的数据。您也可以禁用单个项目恢复，或将单个项目恢复期设置为默认的 14 天。有关详细信息，请参阅 [Enable or disable single item recovery for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)。

  - 保留挂起已启用，保留挂起持续时间设置为 30 天。 这意味着，分配给新邮箱的默认 Exchange 保留策略以及任何组织范围内或 Exchange 范围的 Microsoft 365 保留策略将不会在 30 天内得到处理。 这使复职员工或恢复的非活动邮箱的新所有者有时间来管理旧邮件。 否则，Exchange 或 Microsoft 365 保留策略可能会删除旧邮箱项目 (或将项目移动到存档邮箱（如果已启用) ，根据为 Exchange 或 Microsoft 365 保留策略配置的设置已过期）。 30 天后，保留过期 **，RetentionHoldEnabled** 邮箱属性设置为 **False，** 托管文件夹助理开始处理分配给邮箱的策略。 如果您不需要此额外的时间，则可以删除保留挂起。 您也可以使用 **Set-Mailbox -EndDateForRetentionHold** 命令，增加保留挂起的持续时间。 有关详细信息，请参阅 [Place a mailbox on retention hold](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)。

- **如果您需要保留非活动邮箱的原始状态，请将恢复的邮箱置于保留状态。** 若要防止新邮箱所有者或保留策略永久删除恢复的非活动邮箱的任何邮件，可以将邮箱置于诉讼保留状态。 有关详细信息，请参阅创建 [诉讼保留](./create-a-litigation-hold.md)。

- **恢复非活动邮箱时可以使用哪些用户 ID？** 恢复非活动邮箱时，为  *MicrosoftOnlineServicesID*  参数指定的值可以不同于与非活动邮箱关联的原始值。 您还可以使用原始用户 ID。 但如前所述，恢复非活动邮箱时，请确保  *用于 Name*  和  *MicrosoftOnlineServicesID*  的值在组织中是唯一的。

- **如果非活动邮箱的邮箱保留期尚未过期该怎么办？** 如果非活动邮箱是在 30 天内进行软删除的，则不能使用 **New-Mailbox -InactiveMailbox** 命令对其进行恢复。 您需要通过还原相应的用户帐户来恢复它。 有关详细信息，请参阅 [从组织中删除用户](../admin/add-users/delete-a-user.md)。

- **如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 运行以下命令。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  如果不存在 **ExternalDirectoryObjectId** 属性的值，则说明邮箱保留期已过期，您可以通过运行 **New-Mailbox -InactiveMailbox** 命令恢复非活动邮箱。 如果存在 **ExternalDirectoryObjectId** 属性的值，则软删除邮箱的保留期尚未过期，您必须通过还原用户帐户来恢复邮箱。 请参阅[从组织中删除用户](../admin/add-users/delete-a-user.md)。

- **请考虑在恢复非活动邮箱后启用存档邮箱。** 这样，复职用户或新员工就可以将旧邮件移动到存档邮箱。 当保留保留期过期时，作为分配给 Exchange Online 邮箱的默认 Exchange 保留策略的一部分的存档策略将两年或两年以上的项目移动到存档邮箱。 如果未启用存档邮箱，早于两年的项目将保留在用户的主邮箱中。 有关详细信息，请参阅启用 [存档邮箱](enable-archive-mailboxes.md)。