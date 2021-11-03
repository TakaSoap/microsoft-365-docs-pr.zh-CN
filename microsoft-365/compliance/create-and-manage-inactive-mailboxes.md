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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
description: 使用邮箱中的非活动邮箱功能保留已删除邮箱Microsoft 365。
ms.openlocfilehash: bbc110aae12a233357f23f94cf2600b3079a3666
ms.sourcegitcommit: 7791c519bd8b68fc23433e13e1ecbdbeaddbebfa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60725570"
---
# <a name="create-and-manage-inactive-mailboxes"></a>创建和管理非活动邮箱

Microsoft 365，您可以保留已删除邮箱的内容。 此功能称为“非活动邮箱”[](inactive-mailboxes-in-office-365.md)。 非活动邮箱允许您在前员工离开组织后保留其电子邮件。 当在 Office 365 或 Microsoft 365) 的安全与合规中心中创建的诉讼保留或保留策略应用于邮箱后，邮箱将变为非活动状态，然后再删除相应的用户帐户。 ( 在非活动邮箱变为非活动邮箱之前，非活动邮箱的内容将在邮箱上置于保留状态期间保留。 这允许管理员、合规部主管和记录管理员使用内容搜索来搜索和导出非活动邮箱的内容。 非活动状态的邮箱无法接收电子邮件且不在组织的共享通讯簿或其他列表中显示。
  
> [!IMPORTANT]
> 由于我们将继续以不同方式投资来保留邮箱内容，因此我们将宣布停用 In-Place 管理中心中的 Exchange 保留。 这意味着您应使用诉讼保留和保留策略来创建非活动邮箱。 从 2020 年 7 月 1 日开始，将无法在 Exchange Online 中创建新的 In-Place 保留。 但你仍然可以更改非活动邮箱上In-Place保留的保留期。 但是，从 2020 年 10 月 1 日起，将不能更改保留期。 仅能删除非活动邮箱，即删除"In-Place保留"。 在删除保留之前，In-Place处于保留状态的现有非活动邮箱仍将保留。 有关停用保留In-Place，请参阅 [停用旧版电子数据展示工具](legacy-ediscovery-retirement.md)。
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>创建非活动邮箱之前的准备

- 若要使邮箱处于非活动状态，必须为其分配Exchange Online计划 2 许可证，以便可以在删除邮箱之前将诉讼保留或保留策略应用于邮箱。 Exchange Online计划 2 许可证是 E3 Office 365 企业版 E5 订阅的一部分。 如果为邮箱分配了 Exchange Online 计划 1 或 Exchange Online Kiosk 许可证 (分别属于 Office 365 E1 和 F1 订阅的) ，您必须为其分配单独的 Exchange Online Archiving 许可证，以便可以将保留应用于邮箱。e 它已删除。 有关详细信息，请参阅 [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153)。

- 删除相应的用户帐户后Exchange Online已删除邮箱关联的许可证将可用。 然后， [可以将这些许可证分配给其他用户](../admin/manage/assign-licenses-to-users.md)。

- 如果配置为保留或保留然后删除内容 (在删除之前未将诉讼保留或保留策略) 应用于邮箱，则邮箱的内容将不会保留或可发现。 但是，已删除的邮箱可以在删除后的 30 天内恢复，但如果未恢复，则邮箱及其内容将在 30 天后永久删除。

- 有关诉讼保留详细信息，请参阅 [诉讼保留](/exchange/security-and-compliance/in-place-and-litigation-holds)。 有关保留策略详细信息，请参阅 [了解保留策略和保留标签](retention.md)。
  
## <a name="create-an-inactive-mailbox"></a>创建非活动邮箱

使邮箱变为非活动包含两个步骤：1) 将邮箱置于诉讼保留或应用保留策略，2) 删除邮箱或相应的用户帐户。 邮箱处于非活动状态后，其内容将一直保留，直到删除保留或保留策略。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>步骤 1：将邮箱置于诉讼保留或应用保留策略

将邮箱置于诉讼保留或应用配置为保留 (然后删除内容的保留策略) 在删除邮箱之前保留邮箱中的内容。 这两种类型的保留将保留所有邮箱内容，包括已删除项目和已修改项目的原始版本。 已删除和修改的项目将在非活动邮箱中保留一段指定时间，或者直到您通过删除应用于非活动邮箱的保留或保留策略来永久删除非活动邮箱。
  
如果邮箱上已设置保留，或者保留策略已应用于邮箱，则所必须执行的所有操作就是删除相应的用户帐户，如步骤 2 中介绍。
  
有关将邮箱置于诉讼保留或应用保留策略的分步过程，请参阅：
  
- [将邮箱置于诉讼保留状态](create-a-litigation-hold.md)

- [了解保留策略和保留标签](retention.md)

> [!NOTE]
> 对于诉讼保留和保留策略，可以创建无限期保留或基于时间保留。 在无限期保留中，非活动邮箱的内容将永久保留，或者一直保留到删除保留或直到保留期更改。 删除保留或保留策略后，邮箱将再保留 183 天，此后邮箱将被标记为永久删除，并且不再保留或发现邮箱的内容。 在基于时间保留或保留策略中，指定保留的持续时间。 这个时间段以每个项目为基础，从邮箱项目接收或创建之日算起。 在邮箱项目的保留过期，且该项目移动到非活动邮箱的"可恢复的项目"文件夹或位于非活动邮箱中的"可恢复的项目"文件夹中后，将在已删除项目保留期过期后从非活动邮箱中永久删除 () 。 
  
### <a name="step-2-delete-the-mailbox"></a>步骤 2：删除邮箱

将邮箱置于保留状态或应用保留策略后，下一步是删除邮箱。 删除邮箱的最佳方法就是删除邮箱中的相应<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心。</a> 有关删除用户帐户的信息，请参阅 [从组织中删除用户](../admin/add-users/delete-a-user.md)。
  
> [!NOTE]
> 您还可以使用 PowerShell 中的 **Remove-Mailbox** cmdlet 删除Exchange Online邮箱。 有关详细信息，请参阅删除[或还原用户邮箱Exchange Online。](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 
  
## <a name="view-a-list-of-inactive-mailboxes"></a>查看非活动邮箱列表

若要查看组织中非活动邮箱的列表，请进行以下选择：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>然后使用组织中全局管理员或合规性管理员帐户的凭据登录。

2. 在左侧导航窗格中，单击"**全部显示**"，然后单击"**信息治理""保留**  >  **"。**

   ![单击"保留"页上的"非活动邮箱"按钮。](../media/MCCInactiveMailboxes1.png)

3. 在" **保留"** 页上，单击" **非** 活动邮箱"以显示非活动邮箱的列表。

4. 选择非活动邮箱以显示包含非活动邮箱相关信息的飞出页面。

   ![该飞出页面显示有关非活动邮箱的详细信息。](../media/MCCInactiveMailboxes2.png)  

可以单击" ![ 导出搜索结果"图标。](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **导出** 以查看或下载包含有关组织中非活动邮箱的其他信息的 CSV 文件。

或者，可以在 PowerShell 中运行Exchange Online，以显示非活动邮箱的列表。

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

还可以运行以下命令，将非活动邮箱列表和其他信息导出到 CSV 文件。 本示例在当前目录中创建 CSV 文件。

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> 非活动邮箱可能与活动用户邮箱具有相同的 SMTP 地址。 在这种情况下 **，DistinguishedName** 或 **ExchangeGuid** 属性的值可用于唯一标识非活动邮箱。
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>搜索和导出非活动邮箱的内容

您可以使用活动邮箱中的内容搜索工具访问非活动Microsoft 365 合规中心。 搜索非活动邮箱时，可以创建关键字搜索查询搜索特定的项目或者返回整个非活动邮箱的内容。 可以预览搜索结果或将搜索结果导出到 PST Outlook 数据 () 单个电子邮件。 有关搜索邮箱和导出搜索结果的分步过程，请参阅下列主题：
  
- [内容搜索](content-search.md)

- [导出搜索结果](export-search-results.md)

以下是在搜索非活动邮箱时应记住的一些事项。
  
- 如果内容搜索包括用户邮箱并且该邮箱变为非活动邮箱，则当您在非活动邮箱变为非活动状态后重新运行搜索时，内容搜索将继续搜索该邮箱。

- 在某些情况下，用户可能拥有一个活动邮箱和一个 SMTP 地址相同的非活动邮箱。 在这种情况下，将仅搜索选择作为内容搜索位置的特定邮箱。 换句话说，如果将用户的邮箱添加到搜索中，则不能假定将搜索其活动邮箱和非活动邮箱;将仅搜索您显式添加到搜索中的邮箱。

- 强烈建议避免活动邮箱和非活动邮箱具有相同的 SMTP 地址。 如果您需要重用当前分配给非活动邮箱的 SMTP 地址，建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱 (或活动邮箱) 的存档，然后删除非活动邮箱。

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>更改非活动邮箱的保留期

邮箱变为非活动邮箱后，可以更改保留期或应用于非活动邮箱的保留策略。 有关分步过程，请参阅 Change [the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)。
  
## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

如果以前的员工回到您的组织，或者如果聘用了一位新员工来承担离职员工的工作职责，您可以恢复非活动邮箱的内容。 恢复非活动邮箱时，邮箱会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在。 有关恢复非活动邮箱时发生的分步过程和详细信息，请参阅恢复邮箱中的非[活动Office 365。](recover-an-inactive-mailbox.md)
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>将非活动邮箱的内容还原到另一个邮箱

如果另一名员工承担以前员工的工作职责，或者如果其他人需要访问非活动邮箱的内容，您可以还原 (或将) 非活动邮箱的内容合并到现有邮箱。 还原非活动邮箱时，内容将复制到另一个邮箱。 非活动邮箱将保留并保留为非活动邮箱。 仍可以使用电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。 有关分步过程，请参阅 Restore [an inactive mailbox in Office 365](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>删除非活动邮箱

如果您不再需要保留非活动邮箱的内容，则可以通过删除非活动邮箱的保留或删除应用于非活动邮箱的保留策略来永久删除非活动邮箱。 在您删除保留策略或保留策略后，邮箱将保留 183 天，并且在此期间可恢复。 183 天后，邮箱将标记为永久删除，并且该邮箱将不可恢复。 有关删除保留或保留策略以永久删除非活动邮箱的分步过程，请参阅删除 [非活动邮箱](delete-an-inactive-mailbox.md)。
