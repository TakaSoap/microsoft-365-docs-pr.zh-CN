---
title: 创建和管理非活动邮箱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用 Office 365 中的非活动邮箱功能保留已删除邮箱的内容。
ms.openlocfilehash: 45de882cf0931b85d3acd6368f619f94fce636d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908376"
---
# <a name="create-and-manage-inactive-mailboxes"></a>创建和管理非活动邮箱

Microsoft 365 使你能够保留已删除邮箱的内容。 此功能称为“非活动邮箱”[](inactive-mailboxes-in-office-365.md)。 非活动邮箱允许您在前员工离开组织后保留其电子邮件。 当在 Office 365 或 Microsoft 365 () 的安全与合规中心中创建的诉讼保留或保留策略) 在删除相应用户帐户之前，邮箱将变为非活动状态。 在非活动邮箱变为非活动邮箱之前，非活动邮箱的内容将在邮箱上置于保留状态期间保留。 这允许管理员、合规部主管和记录管理员使用内容搜索来搜索和导出非活动邮箱的内容。 非活动状态的邮箱无法接收电子邮件且不在组织的共享通讯簿或其他列表中显示。
  
> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，因此我们将宣布在 Exchange 管理中心停用 In-Place 保留。 这意味着您应该使用诉讼保留和保留策略来创建非活动邮箱。 从 2020 年 7 月 1 日开始，将无法在 Exchange Online In-Place保留。 但你仍然可以更改非活动邮箱上In-Place保留的保留期。 但是，从 2020 年 10 月 1 日起，将不能更改保留期。 仅能删除非活动邮箱，即删除"In-Place保留"。 在删除保留之前，In-Place处于保留状态的现有非活动邮箱仍将保留。 有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>创建非活动邮箱之前的准备

- 若要使邮箱变为非活动邮箱，必须为其分配 Exchange Online 计划 2 许可证，以便可以在删除邮箱之前对邮箱应用诉讼保留或保留策略。 Exchange Online 计划 2 许可证是 Office 365 企业版 E3 和 E5 订阅的一部分。 如果为邮箱分配了分别属于 Office 365 E1 和 F1 订阅的 Exchange Online 计划 1 或 Exchange Online Kiosk 许可证 (（分别属于 Office 365 E1 和 F1 订阅的一部分) 则你必须为其分配单独的 Exchange Online Archiving 许可证，以便保留可以在删除邮箱之前应用于邮箱。 有关详细信息，请参阅 [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153)。

- 删除相应的用户帐户后，与已删除的 Exchange Online 邮箱关联的许可证将可用。 然后， [可以将这些许可证分配给其他用户](../admin/manage/assign-licenses-to-users.md)。

- 如果配置为保留 (然后删除内容) 的诉讼保留或保留策略未在删除之前应用于邮箱，则邮箱的内容将不会保留或可发现。 但是，已删除的邮箱可以在删除后的 30 天内恢复，但如果未恢复，则邮箱及其内容将在 30 天后永久删除。

- 有关诉讼保留详细信息，请参阅 [就地保留和诉讼保留](/exchange/security-and-compliance/in-place-and-litigation-holds)。 有关保留策略详细信息，请参阅 [了解保留策略和保留标签](retention.md)。
  
## <a name="create-an-inactive-mailbox"></a>创建非活动邮箱

使邮箱变为非活动包含两个步骤：1) 将邮箱置于诉讼保留或应用保留策略，2) 删除邮箱或相应的用户帐户。 邮箱处于非活动状态后，其内容将一直保留，直到删除保留或保留策略。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>步骤 1：将邮箱置于诉讼保留或应用保留策略

将邮箱置于诉讼保留或应用配置为保留或保留的保留策略 (，然后删除内容) 在删除邮箱之前保留邮箱中的内容。 这两种类型的保留将保留所有邮箱内容，包括已删除项目和已修改项目的原始版本。 已删除和修改的项目将在非活动邮箱中保留一段指定时间，或者直到您通过删除应用于非活动邮箱的保留或保留策略来永久删除非活动邮箱。
  
如果邮箱上已设置保留，或者保留策略已应用于邮箱，则所必须执行的所有操作就是删除相应的用户帐户，如步骤 2 中介绍。
  
有关将邮箱置于诉讼保留或应用保留策略的分步过程，请参阅：
  
- [将邮箱置于诉讼保留状态](./create-a-litigation-hold.md)
    
- [了解 Office 365 中的保留策略和保留标签](retention.md)
    
> [!NOTE]
> 对于诉讼保留和保留策略，可以创建无限期保留或基于时间保留。 在无限期保留中，非活动邮箱的内容将永久保留，或者一直保留到删除保留或直到保留期更改。 删除保留策略或保留策略 (假定邮箱在) 之前已删除，非活动邮箱将被标记为永久删除，并且不再保留或发现邮箱的内容。 在基于时间保留或保留策略中，指定保留的持续时间。 这个时间段以每个项目为基础，从邮箱项目接收或创建之日算起。 在邮箱项目的保留过期，并且该项目移动到非活动邮箱的"可恢复的项目"文件夹或位于非活动邮箱中的"可恢复的项目"文件夹中后，该项目将在已删除项目保留期过期后从非活动邮箱中永久删除 () 。 
  
### <a name="step-2-delete-the-mailbox"></a>步骤 2：删除邮箱

将邮箱置于保留状态或应用保留策略后，下一步是删除邮箱。 删除邮箱的最佳方法就是删除 Microsoft 365 管理中心中的相应用户帐户。 有关删除用户帐户的信息，请参阅 [从组织中删除用户](../admin/add-users/delete-a-user.md)。
  
> [!NOTE]
> 您还可以使用 Exchange Online PowerShell 中的 **Remove-Mailbox** cmdlet 删除邮箱。 有关详细信息，请参阅删除 [或还原 Exchange Online 中的用户邮箱](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)。 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>查看非活动邮箱列表

若要查看组织中非活动邮箱的列表，请进行以下选择：
  
1. 转到 [https://protection.office.com](https://protection.office.com)，然后使用你组织中的管理员帐户的凭据进行登录。 
    
2. 单击 **"信息治理**  >  **""保留"。**
    
3. 在"**保留"** 页上，单击 **"更多** ![ 导航栏省略号 ](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) "，然后单击"非 **活动邮箱"。**
    
    ![在"保留"页上，单击"更多"，然后单击"非活动邮箱"以显示非活动邮箱的列表](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    将显示 **"非活动邮箱** "页。 请注意，将显示组织中非活动邮箱的总数。 
    
    ![将显示组织中所有非活动邮箱的列表](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
或者，您可以在 Exchange Online PowerShell 中运行以下命令来显示非活动邮箱的列表。

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

You can click ![ Export search results icon ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export** to view or download a CSV file that contains additional information about the inactive mailboxes in your organization. 
  
还可以运行以下命令，将非活动邮箱列表和其他信息导出到 CSV 文件。 本示例在当前目录中创建 CSV 文件。

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> 非活动邮箱可能与活动用户邮箱具有相同的 SMTP 地址。 在这种情况下 **，DistinguishedName** 或 **ExchangeGuid** 属性的值可用于唯一标识非活动邮箱。 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜索和导出非活动邮箱的内容

您可以使用安全与合规中心内的内容搜索工具访问非活动&内容。 搜索非活动邮箱时，可以创建关键字搜索查询搜索特定的项目或者返回整个非活动邮箱的内容。 您可以预览搜索结果或将搜索结果导出到 Outlook Data (PST) 文件或作为单个电子邮件。 有关搜索邮箱和导出搜索结果的分步过程，请参阅下列主题：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [导出内容搜索结果](export-search-results.md)
    
以下是在搜索非活动邮箱时应记住的一些事项。
  
- 如果内容搜索包括用户邮箱并且该邮箱变为非活动邮箱，则当您在非活动邮箱变为非活动状态后重新运行搜索时，内容搜索将继续搜索该邮箱。
    
- 在某些情况下，用户可能拥有一个活动邮箱和一个 SMTP 地址相同的非活动邮箱。 在这种情况下，将仅搜索选择作为内容搜索位置的特定邮箱。 换句话说，如果将用户的邮箱添加到搜索中，则不能假定将搜索其活动邮箱和非活动邮箱;将仅搜索您显式添加到搜索中的邮箱。
    
- 强烈建议避免活动邮箱和非活动邮箱具有相同的 SMTP 地址。 如果您需要重用当前分配给非活动邮箱的 SMTP 地址，建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱 (或活动邮箱) 的存档，然后删除非活动邮箱。
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>更改非活动邮箱的保留期

邮箱变为非活动邮箱后，可以更改保留期或应用于非活动邮箱的保留策略。 有关分步过程，请参阅更改 [Office 365 中非活动](change-the-hold-duration-for-an-inactive-mailbox.md)邮箱的保留期。
  
## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

如果以前的员工回到您的组织，或者如果聘用了一位新员工来承担离职员工的工作职责，您可以恢复非活动邮箱的内容。 恢复非活动邮箱时，邮箱会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在。 有关恢复非活动邮箱时发生的分步过程和详细信息，请参阅恢复 [Office 365](recover-an-inactive-mailbox.md)中的非活动邮箱。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>将非活动邮箱的内容还原到另一个邮箱

如果另一名员工承担以前员工的工作职责，或者如果其他人需要访问非活动邮箱的内容，您可以还原 (或将) 非活动邮箱的内容合并到现有邮箱。 还原非活动邮箱时，内容将复制到另一个邮箱。 非活动邮箱将保留并保留为非活动邮箱。 仍可以使用电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。 有关分步过程，请参阅 [在 Office 365 中还原非活动邮箱](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>删除非活动邮箱

如果您不再需要保留非活动邮箱的内容，则可以通过删除非活动邮箱的保留或删除应用于非活动邮箱的保留策略来永久删除非活动邮箱。 如果距离邮箱删除日期已过去 30 多天，则此邮箱会在您删除保留设置后标记为永久删除，并且无法恢复。 如果邮箱是过去 30 天内删除的，则仍可在删除保留或保留策略后恢复邮箱。 有关删除保留或保留策略以永久删除非活动邮箱的分步过程，请参阅删除 [非活动邮箱](delete-an-inactive-mailbox.md)。