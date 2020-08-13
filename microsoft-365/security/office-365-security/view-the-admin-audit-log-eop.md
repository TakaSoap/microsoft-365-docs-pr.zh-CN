---
title: 在独立 EOP 中查看管理员审核日志
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理员可以了解如何在独立 Exchange Online Protection (EOP) 中查看和搜索管理员审核日志。
ms.openlocfilehash: 171f3ec531b232ca796232ab26caefbee8afc75c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653493"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="21554-103">在独立 EOP 中查看管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="21554-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="21554-104">在独立 Exchange Online Protection (EOP) 没有 Exchange Online 邮箱的组织中，您可以使用 Exchange 管理中心 (EAC) 或独立的 EOP PowerShell 搜索和查看管理员审核日志中的条目。</span><span class="sxs-lookup"><span data-stu-id="21554-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="21554-105">管理员审核日志根据独立的 EOP PowerShell cmdlet （由管理员和已分配了管理权限的用户）来记录特定的操作。</span><span class="sxs-lookup"><span data-stu-id="21554-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="21554-106">管理员审核日志中的条目提供了有关运行的 cmdlet、使用的参数、运行 cmdlet 的用户以及受影响对象的信息。</span><span class="sxs-lookup"><span data-stu-id="21554-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="21554-107">管理员审核日志记录默认情况下处于启用状态，并且您无法禁用它。</span><span class="sxs-lookup"><span data-stu-id="21554-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="21554-108">管理员审核日志不会根据以谓词**Get**、 **Search**或**Test**开头的 cmdlet 来记录操作。</span><span class="sxs-lookup"><span data-stu-id="21554-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="21554-109">审核日志条目将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="21554-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="21554-110">当条目的时间超过90天时，它将被删除</span><span class="sxs-lookup"><span data-stu-id="21554-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21554-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="21554-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="21554-112">若要打开 Exchange 管理中心，请参阅[独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="21554-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="21554-113">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="21554-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="21554-114">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="21554-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="21554-115">具体来说，您需要默认情况下，您需要审核日志或仅查看审核日志角色，这些角色分配给 ComplianceManagement、OrganizationManagement (全局管理员) 和 SecurityAdministrator 角色组。</span><span class="sxs-lookup"><span data-stu-id="21554-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="21554-116">有关详细信息，请参阅[独立 EOP 中的权限](feature-permissions-in-eop.md)和[使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="21554-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="21554-117">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="21554-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="21554-118">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="21554-118">Having problems?</span></span> <span data-ttu-id="21554-119">在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="21554-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="21554-120">使用 EAC 查看管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="21554-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="21554-121">在 EAC 中，转到 "**合规性管理** \> **审核**"，然后选择 "**运行管理员审核日志报告**"。</span><span class="sxs-lookup"><span data-stu-id="21554-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="21554-122">在打开的 "**搜索对管理员角色组的更改**" 页上，选择 "**开始日期**" 和 "**结束日期**" (默认范围为 "过去两周) "，然后选择 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="21554-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="21554-123">在指定期间进行的所有配置更改都将显示并且可以使用以下信息进行排序：</span><span class="sxs-lookup"><span data-stu-id="21554-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="21554-124">**日期**：进行配置更改的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="21554-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="21554-125">日期和时间存储为协调世界时 (UTC) 格式。</span><span class="sxs-lookup"><span data-stu-id="21554-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="21554-126">**Cmdlet**：用于进行配置更改的 Cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="21554-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="21554-127">**User**：进行配置更改的用户的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="21554-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="21554-p107">将分多页显示多达 5000 个条目。如果您需要缩小结果范围，请指定一个较小的日期范围。如果您选择单个搜索结果，将在详细信息窗格中显示以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="21554-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="21554-131">**对象已修改**： cmdlet 修改的对象。</span><span class="sxs-lookup"><span data-stu-id="21554-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="21554-132">\*\*参数 (参数： Value) \*\*：所使用的 cmdlet 参数以及参数指定的任何值。</span><span class="sxs-lookup"><span data-stu-id="21554-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="21554-133">如果要打印特定的审核日志条目，请在详细信息窗格中选择 "**打印**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="21554-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="21554-134">使用独立 EOP PowerShell 查看管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="21554-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="21554-135">您可以使用独立的 EOP PowerShell 搜索符合指定条件的审核日志条目。</span><span class="sxs-lookup"><span data-stu-id="21554-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="21554-136">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="21554-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="21554-137">**注意**：</span><span class="sxs-lookup"><span data-stu-id="21554-137">**Notes**:</span></span>

- <span data-ttu-id="21554-138">只能将_Parameters_参数与_cmdlet_参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="21554-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="21554-139">_ObjectIds_参数按 cmdlet 修改的对象筛选结果。</span><span class="sxs-lookup"><span data-stu-id="21554-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="21554-140">有效的值取决于对象在审核日志中的表示方式。</span><span class="sxs-lookup"><span data-stu-id="21554-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="21554-141">例如：</span><span class="sxs-lookup"><span data-stu-id="21554-141">For example:</span></span>

  - <span data-ttu-id="21554-142">名称</span><span class="sxs-lookup"><span data-stu-id="21554-142">Name</span></span>
  - <span data-ttu-id="21554-143">规范可分辨名称 (例如，contoso.com/Users/Akia Al-Zuhairi) </span><span class="sxs-lookup"><span data-stu-id="21554-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="21554-144">您可能需要使用此 cmdlet 上的其他筛选参数来缩小结果范围，并确定您感兴趣的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="21554-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="21554-145">_UserIds_参数按执行 cmdlet) 的用户进行更改的用户筛选结果 (。</span><span class="sxs-lookup"><span data-stu-id="21554-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="21554-146">对于 "开始日期 _" 和 "_ _结束_日期" 参数，如果指定不包含时区的日期/时间值，则该值 (UTC) 的协调通用时间。</span><span class="sxs-lookup"><span data-stu-id="21554-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="21554-147">若要指定此参数的日期/时间值，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="21554-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="21554-148">以 UTC 格式指定日期/时间值：例如，"2016-05-06 14:30:00z"。</span><span class="sxs-lookup"><span data-stu-id="21554-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="21554-149">将 "日期/时间" 值指定为将本地时区中的日期/时间转换为 UTC 的公式：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="21554-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="21554-150">有关详细信息，请参阅 [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)。</span><span class="sxs-lookup"><span data-stu-id="21554-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="21554-151">默认情况下，cmdlet 返回的日志条目最多为1000个。</span><span class="sxs-lookup"><span data-stu-id="21554-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="21554-152">使用_ResultSize_参数可以指定最长250000个日志条目。</span><span class="sxs-lookup"><span data-stu-id="21554-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="21554-153">或者，使用值 `Unlimited` 返回所有条目。</span><span class="sxs-lookup"><span data-stu-id="21554-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="21554-154">本示例将使用以下条件执行对所有审核日志条目的搜索：</span><span class="sxs-lookup"><span data-stu-id="21554-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="21554-155">**开始日期**：2019年8月4日</span><span class="sxs-lookup"><span data-stu-id="21554-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="21554-156">**结束日期**：2019年10月3日</span><span class="sxs-lookup"><span data-stu-id="21554-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="21554-157">**Cmdlet**：更新-add-rolegroupmember</span><span class="sxs-lookup"><span data-stu-id="21554-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="21554-158">有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="21554-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="21554-159">查看审核日志条目的详细信息</span><span class="sxs-lookup"><span data-stu-id="21554-159">View details of audit log entries</span></span>

<span data-ttu-id="21554-160">**Search-adminauditlog** cmdlet 返回本主题后面的[审核日志内容](#audit-log-contents)部分中所述的字段。</span><span class="sxs-lookup"><span data-stu-id="21554-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="21554-161">在 cmdlet 返回的字段中，两个字段： **CmdletParameters**和**ModifiedProperties**包含默认情况下不返回的其他信息。</span><span class="sxs-lookup"><span data-stu-id="21554-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="21554-162">若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="21554-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="21554-163">确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。</span><span class="sxs-lookup"><span data-stu-id="21554-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="21554-164">每个审核日志条目都作为数组元素存储在变量中 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="21554-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="21554-165">可以通过指定其数组元素索引来选择数组元素。</span><span class="sxs-lookup"><span data-stu-id="21554-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="21554-166">数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。</span><span class="sxs-lookup"><span data-stu-id="21554-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="21554-167">例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。</span><span class="sxs-lookup"><span data-stu-id="21554-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="21554-p115">上述命令将返回数组元素 4 中存储的日志条目。若要查看此日志条目的 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="21554-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="21554-170">若要查看其他日志条目的 **CmdletParameters** 或 **ModifiedParameters** 字段的内容，请更改数组元素索引。</span><span class="sxs-lookup"><span data-stu-id="21554-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="21554-171">审核日志内容</span><span class="sxs-lookup"><span data-stu-id="21554-171">Audit log contents</span></span>

<span data-ttu-id="21554-172">每个审核日志条目都包含下表所述的信息。</span><span class="sxs-lookup"><span data-stu-id="21554-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="21554-173">审核日志包含一个或多个审核日志条目。</span><span class="sxs-lookup"><span data-stu-id="21554-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="21554-174">字段</span><span class="sxs-lookup"><span data-stu-id="21554-174">Field</span></span>|<span data-ttu-id="21554-175">说明</span><span class="sxs-lookup"><span data-stu-id="21554-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="21554-176">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="21554-177">此字段包含由字段中指定的 cmdlet 修改的对象 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="21554-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="21554-178">此字段包含由用户在字段中运行的 cmdlet 的名称 `Caller` 。</span><span class="sxs-lookup"><span data-stu-id="21554-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="21554-179">此字段包含在运行字段中的 cmdlet 时指定的参数 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="21554-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="21554-180">使用参数指定的值（如果有）也存储在此字段中，但是在默认输出中不可见。</span><span class="sxs-lookup"><span data-stu-id="21554-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="21554-181">此字段包含在字段中的对象上修改的属性 `ObjectModified` 。</span><span class="sxs-lookup"><span data-stu-id="21554-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="21554-182">也存储在此字段中，但在默认输出中不可见，是属性的旧值和存储的新值。</span><span class="sxs-lookup"><span data-stu-id="21554-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="21554-183">此字段包含在字段中运行 cmdlet 的用户的用户帐户 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="21554-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="21554-184">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="21554-185">此字段指定字段中的 cmdlet 是否 `CmdletName` 成功运行。</span><span class="sxs-lookup"><span data-stu-id="21554-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="21554-186">该值可以是 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="21554-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="21554-187">如果字段中的 cmdlet 未能成功完成，则此字段包含生成的错误消息 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="21554-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="21554-188">此字段包含运行字段中的 cmdlet 时的日期和时间 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="21554-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="21554-189">日期和时间存储为协调世界时 (UTC) 格式。</span><span class="sxs-lookup"><span data-stu-id="21554-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="21554-190">此字段指示在其中运行字段中指定的 cmdlet 的服务器 `CmdletName` 。</span><span class="sxs-lookup"><span data-stu-id="21554-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="21554-191">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="21554-192">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="21554-193">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="21554-194">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="21554-195">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="21554-196">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="21554-197">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="21554-197">This field is used internally by EOP.</span></span>|
|
