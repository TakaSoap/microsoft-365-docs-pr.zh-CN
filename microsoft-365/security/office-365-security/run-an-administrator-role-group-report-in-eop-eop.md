---
title: 在独立 EOP 中运行管理员角色组报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在独立 Exchange Online Protection 和 EOP (运行管理员) 。 此报告记录管理员向管理员角色组添加或删除成员时。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 507fbe6fb6c99677cf91b6eb824bf110f1c826f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166623"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>在独立 EOP 中运行管理员角色组报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
-  [独立 Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

在独立 Exchange Online Protection (EOP) 组织中，当管理员向 管理角色 组添加或删除成员时，该服务将记录每次事件。 有关独立 EOP 中的角色组详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md)。

在 Exchange 管理中心 (EAC) 中运行管理员角色组报告时，条目将显示为搜索结果，并包括受影响的角色组、更改角色组成员身份的用户、时间以及进行了哪些成员身份更新。 使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。 具体来说，您需要审核 **日志** 或仅查看审核 **日志** 角色，默认情况下，该角色分配给组织管理、合规性管理和 **安全** 管理员角色组。 有关详细信息，请参阅独立 [EOP 中的权限](feature-permissions-in-eop.md) 和使用 [EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 Exchange Online 中 [Exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>使用 EAC 运行管理员角色组报告

运行管理员角色组报告以查找特定时间范围内对管理角色组所做的更改。

1. 在 EAC 中，转到 **"合规性管理** \> **审核**"，然后选择"运行 **管理员角色组报告"。**

2. 在 **打开的"搜索管理员角色** 组更改"页中，配置以下设置：

   - **开始日期和****结束日期：** 输入日期范围。 默认情况下，报告将搜索在过去两周内对管理员角色组所做的更改。

   - **选择角色组**：默认情况下，将搜索所有角色组。 若要按特定角色组筛选结果，请单击 **"选择角色组"。** 在出现的对话框中，选择一个角色组，然后单击 **>。** 根据需要多次重复此步骤，然后在完成后单击"确定"。 

3. 完成后，单击"搜索 **"。**

如果使用指定的条件找到了所有更改，则这些更改会显示在结果窗格中。单击搜索结果中的角色组可在详细信息窗格中查看更改。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

如果您已成功运行管理员角色组报告，那么在此日期范围内更改的角色组将显示在搜索结果窗格中。如果没有显示任何结果，那么在指定日期范围内没有发生对角色组的任何更改。如果您认为应该显示结果，请更改日期范围，然后再次运行报告。

## <a name="monitor-changes-to-role-group-membership"></a>监视角色组成员身份的更改

向某个角色组添加成员或删除其中的成员时，在详细信息窗格中显示的搜索结果将会指示角色组成员身份已进行更新，并列出当前的成员。但搜索结果并不会明确地指出已添加或已删除的用户。

若要确定是否添加或删除了某个用户，则必须对报告中的两个不同条目进行比较。 例如，让我们看一下 **HelpDesk** 角色组的以下日志条目：

> 1/27/2018 4：43 PM <br> Administrator <br> Updated members: Administrator;annb,florencef;pilarp <br> 2/06/2018 10：09 AM <br> Administrator <br> Updated members: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2：12 PM <br> Administrator <br> Updated members: Administrator;annb;florencef;tonip

在本示例中，Administrator 用户帐户做出了以下更改：

- 在 2018 年 2 月 6 日，他们添加了用户 tonip。
- 在 2018 年 2 月 19 日，他们删除了用户 pilarp。

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>使用独立 Exchange Online PowerShell 搜索审核日志条目

您可以使用 Exchange Online PowerShell 搜索满足审核日志条件的电子邮件条目。 有关搜索条件的列表，请参阅 [Search-AdminAuditLog 搜索条件](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。 此过程使用 **Search-AdminAuditLog** cmdlet，并显示 Exchange Online PowerShell 中的搜索结果。 如果需要返回超出在 **New-AdminAuditLogSearch** cmdlet 或 EAC"审核报告"报告中定义的限制的一组结果时，可使用此 cmdlet。

若要搜索满足指定条件的审核日志，请使用以下语法。

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> 默认情况下， **Search-AdminAuditLog** cmdlet 最多可返回 1,000 个日志条目。 使用 _ResultSize_ 参数可指定最多 250，000 个日志条目。 或者，使用 `Unlimited` 该值返回所有条目。

本示例将使用以下条件执行对所有审核日志条目的搜索：

- **开始日期**：08/04/2018
- **结束日期**：2018 年 10 月 3 日
- **用户 ID**： `davids` ， `chrisd` ， `kima`
- **Cmdlet：Set-Mailbox** 
- **参数 ：** _ProhibitSendQuota_、 _ProhibitSendReceiveQuota_、 _IssueWarningQuota_、 _MaxSendSize_、 _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

本示例将搜索对特定邮箱所做的更改。此操作在进行故障排除或需要为调查提供信息时很有用。使用以下条件：

- **开始日期**：05/01/2018
- **结束日期**：2018 年 10 月 3 日
- **对象 ID**：contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

如果搜索返回许多日志条目，建议您使用 **使用 Exchange Online PowerShell 中** 提供的过程搜索 审核日志 条目，并将结果发送给本文稍后介绍的收件人。 该部分提供的过程将 XML 文件以电子邮件附件的形式发送给指定的收件人，从而使您更易于提取您感兴趣的数据。

有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。

### <a name="view-details-of-audit-log-entries"></a>查看审核日志条目的详细信息

**Search-AdminAuditLog** cmdlet 返回审核日志 [内容中描述的字段](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)。 在此 cmdlet 返回的字段中， **CmdletParameters** 和 **ModifiedProperties** 两个字段包含默认情况下不可见的附加信息。

若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。 或者，您可以使用 **使用 Exchange Online PowerShell** 中的过程来搜索审核日志条目，并将结果发送给本文稍后介绍的收件人以创建 XML 文件。

此过程将使用以下概念：

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. 确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. 每个审核日志项都存储为变量中的数组元素 `$Results` 。 可以通过指定其数组元素索引来选择数组元素。 数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。 例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。

   ```PowerShell
   $Results[4]
   ```

3. 上述命令将返回数组元素 4 中存储的日志条目。若要查看此日志条目的 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请使用以下命令。

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. 若要查看其他日志条目的 **CmdletParameters** 或 **ModifiedParameters** 字段的内容，请更改数组元素索引。
