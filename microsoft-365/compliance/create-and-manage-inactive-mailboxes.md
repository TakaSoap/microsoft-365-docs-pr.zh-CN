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
description: 创建和管理非活动邮箱，这些邮箱将已删除邮箱的内容保留在Microsoft 365。
ms.openlocfilehash: 13b6d883c6c74b2bc674c4f0fd2bd84316d95179
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283469"
---
# <a name="create-and-manage-inactive-mailboxes"></a>创建和管理非活动邮箱

非活动邮箱使您可以在之前员工离开组织后保留其电子邮件，并且出于合规性或法律原因被授予电子数据展示权限的授权人员可以访问[](assign-ediscovery-permissions.md)这些邮箱。 例如，管理员、合规部主管和记录管理员随后可以使用内容搜索来搜索和导出非活动邮箱的内容。 非活动状态的邮箱无法接收电子邮件且不在组织的共享通讯簿或其他列表中显示。

有关非活动邮箱的信息，请参阅 [了解非活动邮箱](inactive-mailboxes-in-office-365.md)。

## <a name="create-an-inactive-mailbox"></a>创建非活动邮箱

使邮箱变为非活动状态需要保留邮箱，然后删除邮箱或相应的用户帐户。

若要使邮箱变为非活动状态，必须为其分配 Exchange Online 计划 2 许可证 (或具有 Exchange Online Archiving 附加许可证) 的 Exchange Online 计划 1 许可证，以便可以在删除邮箱之前将保留应用于邮箱。 删除用户帐户后，Exchange Online用户帐户的任何许可证将可用于分配给新用户。

我们建议你使用Microsoft 365保留来对邮箱应用保留。 了解非活动 [邮箱中介绍了其他方法](inactive-mailboxes-in-office-365.md)。

删除邮箱的最佳方法就是删除邮箱中的相应<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心。</a> 有关删除用户帐户的信息，请参阅 [从组织中删除用户](../admin/add-users/delete-a-user.md)。 但是，您也可以使用 PowerShell 中的 **Remove-Mailbox** cmdlet 删除Exchange Online邮箱。 有关详细信息，请参阅删除[或还原用户邮箱Exchange Online。](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)

下表总结了为不同保留方案创建非活动邮箱的过程。

<br/>

|自。。。|为此...|结果|
|---|---|---|
|员工离开组织后无限期保留邮箱内容|1. Microsoft 365保留设置，同时对邮箱应用保留 (保留策略) 或特定电子邮件 (保留标签) 。 <br /><br> 2. 等待应用保留设置。 <br /><br> 3. 删除用户Microsoft 365帐户。|已应用保留设置的非活动邮箱中所有内容（包括"可恢复的项目"文件夹中的项目）将无限期保留。|
|在员工离开组织后，将所有邮箱内容保留一段特定时间，然后删除邮箱|1. 将Microsoft 365保留策略应用于保留设置保留的邮箱，然后在保留期到期时删除项目。 <br /><br> 2. 等待应用保留设置。 <br /><br> 3. 删除用户Microsoft 365帐户。|当邮箱项目的保留期过期时，该项目将移动到"可恢复的项目"文件夹，然后当 Exchange 邮箱) 的已删除邮件保留期 (过期时，该项目将从非活动邮箱中永久删除 (清除) 。 邮箱保留策略Microsoft 365保留期始终基于接收或创建邮箱项目的原始日期。|


> [!NOTE]
> 如果Microsoft 365保留或保留然后删除内容的保留设置已应用于邮箱或邮箱项目，或者邮箱上已设置诉讼保留，或者创建非活动邮箱所必须执行的所有操作就是删除相应的用户帐户。


## <a name="view-a-list-of-inactive-mailboxes"></a>查看非活动邮箱列表

若要查看组织中非活动邮箱的列表，请进行以下选择：

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心，</a>然后使用组织中全局管理员或合规性管理员帐户的凭据登录。

2. 在左侧导航窗格中，单击"**全部显示**"，然后单击"**信息治理""保留**  >  **"。**

   ![单击"保留"页上的"非活动邮箱"按钮。](../media/MCCInactiveMailboxes1.png)

3. 在" **保留** "页上，单击" **非** 活动邮箱"以显示非活动邮箱的列表。

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

您可以使用活动邮箱中的内容搜索工具访问非活动Microsoft 365 合规中心。 搜索非活动邮箱时，可以创建关键字搜索查询搜索特定的项目或者返回整个非活动邮箱的内容。 您可以预览搜索结果，或将搜索结果导出到 PST Outlook或 (PST) 文件或作为单个电子邮件。 有关搜索邮箱和导出搜索结果的分步过程，请参阅下列主题：
  
- [内容搜索](content-search.md)

- [导出搜索结果](export-search-results.md)

以下是在搜索非活动邮箱时应记住的一些事项。
  
- 如果内容搜索包括用户邮箱并且该邮箱变为非活动邮箱，则当您在非活动邮箱变为非活动状态后重新运行搜索时，内容搜索将继续搜索该邮箱。

- 在某些情况下，用户可能拥有一个活动邮箱和一个 SMTP 地址相同的非活动邮箱。 在这种情况下，将仅搜索选择作为内容搜索位置的特定邮箱。 换句话说，如果将用户的邮箱添加到搜索中，则不能假定将搜索其活动邮箱和非活动邮箱;将仅搜索您显式添加到搜索中的邮箱。

- 强烈建议避免活动邮箱和非活动邮箱具有相同的 SMTP 地址。 如果您需要重用当前分配给非活动邮箱的 SMTP 地址，建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱 (或活动邮箱) 的存档，然后删除非活动邮箱。

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>更改非活动邮箱的保留期

邮箱变为非活动邮箱后，您可以更改应用于非活动邮箱的保留的持续时间。

有关分步过程，请参阅更改非活动邮箱 [的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)。
  
## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

如果以前的员工回到您的组织，或者如果聘用了一位新员工来承担离职员工的工作职责，您可以恢复非活动邮箱的内容。 

恢复非活动邮箱时，邮箱会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。 恢复后，非活动邮箱不再存在。 

有关恢复非活动邮箱时发生的分步过程和详细信息，请参阅 [恢复非活动邮箱](recover-an-inactive-mailbox.md)。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>将非活动邮箱的内容还原到另一个邮箱

如果另一名员工承担以前员工的工作职责，或者如果其他人需要访问非活动邮箱的内容，您可以还原 (或将) 非活动邮箱的内容合并到现有邮箱。 

还原非活动邮箱时，内容将复制到另一个邮箱。 非活动邮箱将保留并保留为非活动邮箱。 仍可以使用电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。 

有关分步过程，请参阅 [还原非活动邮箱](restore-an-inactive-mailbox.md)。
  
## <a name="delete-an-inactive-mailbox"></a>删除非活动邮箱

如果不再需要保留非活动邮箱的内容，可以通过删除应用于非活动邮箱的保留来永久删除非活动邮箱。 在您删除保留策略或保留策略后，邮箱将保留 183 天，并且在此期间可恢复。 183 天后，邮箱将标记为永久删除，并且该邮箱将不可恢复。 

有关删除保留或保留策略以永久删除非活动邮箱的分步过程，请参阅删除 [非活动邮箱](delete-an-inactive-mailbox.md)。
