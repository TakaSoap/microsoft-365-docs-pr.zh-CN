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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理员可以了解如何在独立 Exchange Online Protection (EOP) 中查看和搜索管理员审核日志。
ms.openlocfilehash: 9fe2c742083cde1ca36f6a04cd357a473a10aeac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196539"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>在独立 EOP 中查看管理员审核日志

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在独立 Exchange Online Protection (EOP) 没有 Exchange Online 邮箱的组织中，您可以使用 Exchange 管理中心 (EAC) 或独立的 EOP PowerShell 搜索和查看管理员审核日志中的条目。

管理员审核日志根据独立的 EOP PowerShell cmdlet （由管理员和已分配了管理权限的用户）来记录特定的操作。 管理员审核日志中的条目提供了有关运行的 cmdlet、使用的参数、运行 cmdlet 的用户以及受影响对象的信息。

> [!NOTE]
>
> - 管理员审核日志记录默认情况下处于启用状态，并且您无法禁用它。
>
> - 管理员审核日志不会根据以谓词 **Get**、 **Search**或 **Test**开头的 cmdlet 来记录操作。
>
> - 审核日志条目将保留 90 天。 当条目的时间超过90天时，它将被删除

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 具体来说，您需要默认情况下，您需要审核日志或仅查看审核日志角色，这些角色分配给 ComplianceManagement、OrganizationManagement (全局管理员) 和 SecurityAdministrator 角色组。 有关详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>使用 EAC 查看管理员审核日志

1. 在 EAC 中，转到 " **合规性管理** \> **审核**"，然后选择 " **运行管理员审核日志报告**"。

2. 在打开的 " **搜索对管理员角色组的更改** " 页上，选择 " **开始日期** " 和 " **结束日期** " (默认范围为 "过去两周) "，然后选择 " **搜索**"。 在指定期间进行的所有配置更改都将显示并且可以使用以下信息进行排序：

   - **日期**：进行配置更改的日期和时间。 日期和时间存储为协调世界时 (UTC) 格式。

   - **Cmdlet**：用于进行配置更改的 Cmdlet 的名称。

   - **User**：进行配置更改的用户的用户帐户的名称。

     将分多页显示多达 5000 个条目。如果您需要缩小结果范围，请指定一个较小的日期范围。如果您选择单个搜索结果，将在详细信息窗格中显示以下附加信息：

   - **对象已修改**： cmdlet 修改的对象。

   - **参数 (参数： Value) **：所使用的 cmdlet 参数以及参数指定的任何值。

3. 如果要打印特定的审核日志条目，请在详细信息窗格中选择 " **打印** " 按钮。

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>使用独立 EOP PowerShell 查看管理员审核日志

您可以使用独立的 EOP PowerShell 搜索符合指定条件的审核日志条目。 使用以下语法：

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**注意**：

- 只能将 _Parameters_ 参数与 _cmdlet_ 参数一起使用。

- _ObjectIds_参数按 cmdlet 修改的对象筛选结果。 有效的值取决于对象在审核日志中的表示方式。 例如：

  - 名称
  - 规范可分辨名称 (例如，contoso.com/Users/Akia Al-Zuhairi) 

  您可能需要使用此 cmdlet 上的其他筛选参数来缩小结果范围，并确定您感兴趣的对象的类型。

- _UserIds_参数按执行 cmdlet) 的用户进行更改的用户筛选结果 (。

- 对于 "开始日期 _" 和 "_ _结束_ 日期" 参数，如果指定不包含时区的日期/时间值，则该值 (UTC) 的协调通用时间。 若要指定此参数的日期/时间值，请使用下列方法之一：

  - 以 UTC 格式指定日期/时间值：例如，"2016-05-06 14:30:00z"。

  - 将 "日期/时间" 值指定为将本地时区中的日期/时间转换为 UTC 的公式：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。 有关详细信息，请参阅 [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)。

- 默认情况下，cmdlet 返回的日志条目最多为1000个。 使用 _ResultSize_ 参数可以指定最长250000个日志条目。 或者，使用值 `Unlimited` 返回所有条目。

本示例将使用以下条件执行对所有审核日志条目的搜索：

- **开始日期**：2019年8月4日
- **结束日期**：2019年10月3日
- **Cmdlet**：更新-add-rolegroupmember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。

### <a name="view-details-of-audit-log-entries"></a>查看审核日志条目的详细信息

**Search-adminauditlog** cmdlet 返回本主题后面的[审核日志内容](#audit-log-contents)部分中所述的字段。 在 cmdlet 返回的字段中，两个字段： **CmdletParameters** 和 **ModifiedProperties**包含默认情况下不返回的其他信息。

若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。

1. 确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 每个审核日志条目都作为数组元素存储在变量中 `$Results` 。 可以通过指定其数组元素索引来选择数组元素。 数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。 例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。

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
|`ObjectModified`|此字段包含由字段中指定的 cmdlet 修改的对象 `CmdletName` 。|
|`CmdletName`|此字段包含由用户在字段中运行的 cmdlet 的名称 `Caller` 。|
|`CmdletParameters`|此字段包含在运行字段中的 cmdlet 时指定的参数 `CmdletName` 。 使用参数指定的值（如果有）也存储在此字段中，但是在默认输出中不可见。|
|`ModifiedProperties`|此字段包含在字段中的对象上修改的属性 `ObjectModified` 。 也存储在此字段中，但在默认输出中不可见，是属性的旧值和存储的新值。|
|`Caller`|此字段包含在字段中运行 cmdlet 的用户的用户帐户 `CmdletName` 。|
|`ExternalAccess`|此字段由 EOP 在内部使用。|
|`Succeeded`|此字段指定字段中的 cmdlet 是否 `CmdletName` 成功运行。 该值可以是 `True` 或 `False` 。|
|`Error`|如果字段中的 cmdlet 未能成功完成，则此字段包含生成的错误消息 `CmdletName` 。|
|`RunDate`|此字段包含运行字段中的 cmdlet 时的日期和时间 `CmdletName` 。 日期和时间存储为协调世界时 (UTC) 格式。|
|`OriginatingServer`|此字段指示在其中运行字段中指定的 cmdlet 的服务器 `CmdletName` 。|
|`ClientIP`|此字段由 EOP 在内部使用。|
|`SessionId`|此字段由 EOP 在内部使用。|
|`AppId`|此字段由 EOP 在内部使用。|
|`ClientAppId`|此字段由 EOP 在内部使用。|
|`Identity`|此字段由 EOP 在内部使用。|
|`IsValid`|此字段由 EOP 在内部使用。|
|`ObjectState`|此字段由 EOP 在内部使用。|
|
