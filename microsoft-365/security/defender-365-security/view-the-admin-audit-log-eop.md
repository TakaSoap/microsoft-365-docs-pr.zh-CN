---
title: 在独立 EOP 中查看管理员审核日志
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理员可以了解如何在独立 Exchange Online Protection 审核日志 EOP (中查看和搜索) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055119"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>在独立 EOP 中查看管理员审核日志

**适用对象**
- [独立 Exchange Online Protection](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，可以使用 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 搜索和查看管理 审核日志 中的条目。

管理员审核日志管理员和分配了管理权限的用户基于独立 EOP PowerShell cmdlet 记录特定操作。 管理中心中的条目审核日志有关运行的 cmdlet、使用的参数、运行 cmdlet 的用户以及受影响的对象的信息。

> [!NOTE]
>
> - 管理员审核日志记录默认启用，你无法禁用它。
>
> - 管理员审核日志不记录基于以谓词 **Get、Search** 或 Test 开头的 cmdlet **的操作**。 
>
> - 审核日志条目将保留 90 天。 当条目超过 90 天时，它将被删除

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。 具体来说，您需要"**审核日志**"或"仅查看审核日志"角色，默认情况下会将其分配给组织管理、合规性管理和安全 **管理员** 角色组。 有关详细信息，请参阅 [Permissions in standalone EOP](feature-permissions-in-eop.md) 和 [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅[Keyboard shortcuts for the Exchange admin center in Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>使用 EAC 查看管理员审核日志

1. 在 EAC 中，转到"**合规性** \> 管理""审核"，然后选择"运行 **管理员审核日志报告"。**

2. 在打开 **的"** 搜索对管理员角色组的更改"页中，选择"开始日期"和"**结束日期 (默认** 范围是过去两周) ，然后选择"搜索 **"。** 在指定期间进行的所有配置更改都将显示并且可以使用以下信息进行排序：

   - **日期**：进行配置更改的日期和时间。 日期和时间存储为协调世界时 (UTC) 格式。

   - **Cmdlet：** 用于更改配置 cmdlet 的名称。

   - **用户**：进行配置更改的用户的用户帐户的名称。

     将分多页显示多达 5000 个条目。如果您需要缩小结果范围，请指定一个较小的日期范围。如果您选择单个搜索结果，将在详细信息窗格中显示以下附加信息：

   - **修改的对象**：由 cmdlet 修改的对象。

   - **Parameters (Parameter：Value)**：使用的 cmdlet 参数，以及参数指定的任何值。

3. 如果要打印特定的项目审核日志， **请选择详细信息窗格中** 的"打印"按钮。

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>使用独立 EOP PowerShell 查看管理员审核日志

可以使用独立 EOP PowerShell 搜索满足审核日志条件的电子邮件条目。 使用以下语法：

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**注意**：

- 只能将 _Parameters_ 参数与 _Cmdlets_ 参数一同使用。

- _ObjectIds_ 参数按 cmdlet 修改的对象筛选结果。 有效值取决于对象在对象类型中的审核日志。 例如：

  - 名称
  - 规范可分辨名称 (例如，contoso.com/Users/Akia Al-Zuhairi) 

  您可能需要使用此 cmdlet 上的其他筛选参数来缩小结果范围并确定您感兴趣的对象类型。

- _UserIds_ 参数按对运行 cmdlet (的用户筛选) 。

- 对于 _StartDate_ 和 _EndDate_ 参数，如果指定不带时区的日期/时间值，则该值使用协调世界时 (UTC) 。 若要指定此参数的日期/时间值，请使用下列方法之一：

  - 以 UTC 格式指定日期/时间值：例如，"2016-05-06 14:30:00z"。

  - 将日期/时间值指定为将本地时区中的日期/时间转换为 UTC 的公式：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。 有关详细信息，请参阅 [Get-Date](/powershell/module/microsoft.powershell.utility/get-date)。

- 默认情况下，此 cmdlet 最多返回 1，000 个日志条目。 使用 _ResultSize_ 参数可指定最多 250，000 个日志条目。 或者，使用 `Unlimited` 值返回所有条目。

本示例将使用以下条件执行对所有审核日志条目的搜索：

- **开始日期**：2019 年 8 月 4 日
- **结束日期**：2019 年 10 月 3 日
- **Cmdlet ：** Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)。

### <a name="view-details-of-audit-log-entries"></a>查看审核日志条目的详细信息

**Search-AdminAuditLog** cmdlet 返回本文稍后的 [审核](#audit-log-contents)日志内容部分中介绍的字段。 在 cmdlet 返回的字段中 **，CmdletParameters** 和 **ModifiedProperties** 这两个字段包含默认情况下不返回的其他信息。

若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。

1. 确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 每个审核日志项都存储为变量 中的数组元素 `$Results` 。 可以通过指定其数组元素索引来选择数组元素。 数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。 例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。

    ```PowerShell
    $Results[4]
    ```

3. 上述命令将返回数组元素 4 中存储的日志条目。若要查看此日志条目的 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请使用以下命令。

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. 若要查看其他日志条目的 **CmdletParameters** 或 **ModifiedParameters** 字段的内容，请更改数组元素索引。

## <a name="audit-log-contents"></a>审核日志内容

每个审核日志条目都包含下表所述的信息。 审核日志包含一个或多个审核日志条目。

****

|字段|说明|
|---|---|
|`RunspaceId`|此字段由 EOP 在内部使用。|
|`ObjectModified`|此字段包含由字段中指定的 cmdlet 修改 `CmdletName` 的对象。|
|`CmdletName`|此字段包含字段中用户运行的 cmdlet `Caller` 的名称。|
|`CmdletParameters`|此字段包含运行字段中的 cmdlet 时 `CmdletName` 指定的参数。 使用参数指定的值（如果有）也存储在此字段中，但是在默认输出中不可见。|
|`ModifiedProperties`|此字段包含对字段中的对象修改 `ObjectModified` 的属性。 此属性的旧值和存储的新值也存储在此字段中，但在默认输出中不可见。|
|`Caller`|此字段包含字段中运行 cmdlet 的用户的 `CmdletName` 用户帐户。|
|`ExternalAccess`|此字段由 EOP 在内部使用。|
|`Succeeded`|此字段指定字段中的 cmdlet 是否 `CmdletName` 成功运行。 值为 或 `True` `False` 。|
|`Error`|此字段包含在字段中的 cmdlet 未能成功完成时 `CmdletName` 生成的错误消息。|
|`RunDate`|此字段包含运行字段中的 cmdlet 的 `CmdletName` 日期和时间。 日期和时间存储为协调世界时 (UTC) 格式。|
|`OriginatingServer`|此字段指示运行字段中指定的 cmdlet `CmdletName` 的服务器。|
|`ClientIP`|此字段由 EOP 在内部使用。|
|`SessionId`|此字段由 EOP 在内部使用。|
|`AppId`|此字段由 EOP 在内部使用。|
|`ClientAppId`|此字段由 EOP 在内部使用。|
|`Identity`|此字段由 EOP 在内部使用。|
|`IsValid`|此字段由 EOP 在内部使用。|
|`ObjectState`|此字段由 EOP 在内部使用。|
|