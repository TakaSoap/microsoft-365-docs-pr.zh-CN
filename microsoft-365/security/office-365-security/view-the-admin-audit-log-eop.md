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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908122"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="92bd6-103">在独立 EOP 中查看管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="92bd6-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="92bd6-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="92bd6-104">**Applies to**</span></span>
- [<span data-ttu-id="92bd6-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="92bd6-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="92bd6-106">在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，可以使用 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 搜索和查看管理 审核日志 中的条目。</span><span class="sxs-lookup"><span data-stu-id="92bd6-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="92bd6-107">管理员审核日志管理员和分配了管理权限的用户基于独立 EOP PowerShell cmdlet 记录特定操作。</span><span class="sxs-lookup"><span data-stu-id="92bd6-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="92bd6-108">管理中心中的条目审核日志有关运行的 cmdlet、使用的参数、运行 cmdlet 的用户以及受影响的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="92bd6-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="92bd6-109">管理员审核日志记录默认启用，你无法禁用它。</span><span class="sxs-lookup"><span data-stu-id="92bd6-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="92bd6-110">管理员审核日志不记录基于以谓词 **Get、Search** 或 Test 开头的 cmdlet **的操作**。 </span><span class="sxs-lookup"><span data-stu-id="92bd6-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="92bd6-111">审核日志条目将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="92bd6-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="92bd6-112">当条目超过 90 天时，它将被删除</span><span class="sxs-lookup"><span data-stu-id="92bd6-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="92bd6-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="92bd6-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="92bd6-114">若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="92bd6-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="92bd6-115">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="92bd6-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="92bd6-116">您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="92bd6-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="92bd6-117">具体来说，您需要"**审核日志**"或"仅查看审核日志"角色，默认情况下会将其分配给组织管理、合规性管理和安全 **管理员** 角色组。</span><span class="sxs-lookup"><span data-stu-id="92bd6-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="92bd6-118">有关详细信息，请参阅 [Permissions in standalone EOP](feature-permissions-in-eop.md) 和 [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="92bd6-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="92bd6-119">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅[Keyboard shortcuts for the Exchange admin center in Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="92bd6-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="92bd6-120">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="92bd6-120">Having problems?</span></span> <span data-ttu-id="92bd6-121">请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="92bd6-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="92bd6-122">使用 EAC 查看管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="92bd6-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="92bd6-123">在 EAC 中，转到"**合规性** \> 管理""审核"，然后选择"运行 **管理员审核日志报告"。**</span><span class="sxs-lookup"><span data-stu-id="92bd6-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="92bd6-124">在打开 **的"** 搜索对管理员角色组的更改"页中，选择"开始日期"和"**结束日期 (默认** 范围是过去两周) ，然后选择"搜索 **"。**</span><span class="sxs-lookup"><span data-stu-id="92bd6-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="92bd6-125">在指定期间进行的所有配置更改都将显示并且可以使用以下信息进行排序：</span><span class="sxs-lookup"><span data-stu-id="92bd6-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="92bd6-126">**日期**：进行配置更改的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="92bd6-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="92bd6-127">日期和时间存储为协调世界时 (UTC) 格式。</span><span class="sxs-lookup"><span data-stu-id="92bd6-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="92bd6-128">**Cmdlet：** 用于更改配置 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="92bd6-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="92bd6-129">**用户**：进行配置更改的用户的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="92bd6-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="92bd6-p107">将分多页显示多达 5000 个条目。如果您需要缩小结果范围，请指定一个较小的日期范围。如果您选择单个搜索结果，将在详细信息窗格中显示以下附加信息：</span><span class="sxs-lookup"><span data-stu-id="92bd6-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="92bd6-133">**修改的对象**：由 cmdlet 修改的对象。</span><span class="sxs-lookup"><span data-stu-id="92bd6-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="92bd6-134">**Parameters (Parameter：Value)**：使用的 cmdlet 参数，以及参数指定的任何值。</span><span class="sxs-lookup"><span data-stu-id="92bd6-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="92bd6-135">如果要打印特定的项目审核日志， **请选择详细信息窗格中** 的"打印"按钮。</span><span class="sxs-lookup"><span data-stu-id="92bd6-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="92bd6-136">使用独立 EOP PowerShell 查看管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="92bd6-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="92bd6-137">可以使用独立 EOP PowerShell 搜索满足审核日志条件的电子邮件条目。</span><span class="sxs-lookup"><span data-stu-id="92bd6-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="92bd6-138">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="92bd6-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="92bd6-139">**注意**：</span><span class="sxs-lookup"><span data-stu-id="92bd6-139">**Notes**:</span></span>

- <span data-ttu-id="92bd6-140">只能将 _Parameters_ 参数与 _Cmdlets_ 参数一同使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="92bd6-141">_ObjectIds_ 参数按 cmdlet 修改的对象筛选结果。</span><span class="sxs-lookup"><span data-stu-id="92bd6-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="92bd6-142">有效值取决于对象在对象类型中的审核日志。</span><span class="sxs-lookup"><span data-stu-id="92bd6-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="92bd6-143">例如：</span><span class="sxs-lookup"><span data-stu-id="92bd6-143">For example:</span></span>

  - <span data-ttu-id="92bd6-144">名称</span><span class="sxs-lookup"><span data-stu-id="92bd6-144">Name</span></span>
  - <span data-ttu-id="92bd6-145">规范可分辨名称 (例如，contoso.com/Users/Akia Al-Zuhairi) </span><span class="sxs-lookup"><span data-stu-id="92bd6-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="92bd6-146">您可能需要使用此 cmdlet 上的其他筛选参数来缩小结果范围并确定您感兴趣的对象类型。</span><span class="sxs-lookup"><span data-stu-id="92bd6-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="92bd6-147">_UserIds_ 参数按对运行 cmdlet (的用户筛选) 。</span><span class="sxs-lookup"><span data-stu-id="92bd6-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="92bd6-148">对于 _StartDate_ 和 _EndDate_ 参数，如果指定不带时区的日期/时间值，则该值使用协调世界时 (UTC) 。</span><span class="sxs-lookup"><span data-stu-id="92bd6-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="92bd6-149">若要指定此参数的日期/时间值，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="92bd6-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="92bd6-150">以 UTC 格式指定日期/时间值：例如，"2016-05-06 14:30:00z"。</span><span class="sxs-lookup"><span data-stu-id="92bd6-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="92bd6-151">将日期/时间值指定为将本地时区中的日期/时间转换为 UTC 的公式：例如， `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="92bd6-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="92bd6-152">有关详细信息，请参阅 [Get-Date](/powershell/module/microsoft.powershell.utility/get-date)。</span><span class="sxs-lookup"><span data-stu-id="92bd6-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="92bd6-153">默认情况下，此 cmdlet 最多返回 1，000 个日志条目。</span><span class="sxs-lookup"><span data-stu-id="92bd6-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="92bd6-154">使用 _ResultSize_ 参数可指定最多 250，000 个日志条目。</span><span class="sxs-lookup"><span data-stu-id="92bd6-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="92bd6-155">或者，使用 `Unlimited` 值返回所有条目。</span><span class="sxs-lookup"><span data-stu-id="92bd6-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="92bd6-156">本示例将使用以下条件执行对所有审核日志条目的搜索：</span><span class="sxs-lookup"><span data-stu-id="92bd6-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="92bd6-157">**开始日期**：2019 年 8 月 4 日</span><span class="sxs-lookup"><span data-stu-id="92bd6-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="92bd6-158">**结束日期**：2019 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="92bd6-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="92bd6-159">**Cmdlet ：** Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="92bd6-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="92bd6-160">有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="92bd6-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="92bd6-161">查看审核日志条目的详细信息</span><span class="sxs-lookup"><span data-stu-id="92bd6-161">View details of audit log entries</span></span>

<span data-ttu-id="92bd6-162">**Search-AdminAuditLog** cmdlet 返回本文稍后的 [审核](#audit-log-contents)日志内容部分中介绍的字段。</span><span class="sxs-lookup"><span data-stu-id="92bd6-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="92bd6-163">在 cmdlet 返回的字段中 **，CmdletParameters** 和 **ModifiedProperties** 这两个字段包含默认情况下不返回的其他信息。</span><span class="sxs-lookup"><span data-stu-id="92bd6-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="92bd6-164">若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="92bd6-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="92bd6-165">确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。</span><span class="sxs-lookup"><span data-stu-id="92bd6-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="92bd6-166">每个审核日志项都存储为变量 中的数组元素 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="92bd6-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="92bd6-167">可以通过指定其数组元素索引来选择数组元素。</span><span class="sxs-lookup"><span data-stu-id="92bd6-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="92bd6-168">数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。</span><span class="sxs-lookup"><span data-stu-id="92bd6-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="92bd6-169">例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。</span><span class="sxs-lookup"><span data-stu-id="92bd6-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="92bd6-p115">上述命令将返回数组元素 4 中存储的日志条目。若要查看此日志条目的 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="92bd6-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="92bd6-172">若要查看其他日志条目的 **CmdletParameters** 或 **ModifiedParameters** 字段的内容，请更改数组元素索引。</span><span class="sxs-lookup"><span data-stu-id="92bd6-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="92bd6-173">审核日志内容</span><span class="sxs-lookup"><span data-stu-id="92bd6-173">Audit log contents</span></span>

<span data-ttu-id="92bd6-174">每个审核日志条目都包含下表所述的信息。</span><span class="sxs-lookup"><span data-stu-id="92bd6-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="92bd6-175">审核日志包含一个或多个审核日志条目。</span><span class="sxs-lookup"><span data-stu-id="92bd6-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="92bd6-176">字段</span><span class="sxs-lookup"><span data-stu-id="92bd6-176">Field</span></span>|<span data-ttu-id="92bd6-177">说明</span><span class="sxs-lookup"><span data-stu-id="92bd6-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="92bd6-178">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="92bd6-179">此字段包含由字段中指定的 cmdlet 修改 `CmdletName` 的对象。</span><span class="sxs-lookup"><span data-stu-id="92bd6-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="92bd6-180">此字段包含字段中用户运行的 cmdlet `Caller` 的名称。</span><span class="sxs-lookup"><span data-stu-id="92bd6-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="92bd6-181">此字段包含运行字段中的 cmdlet 时 `CmdletName` 指定的参数。</span><span class="sxs-lookup"><span data-stu-id="92bd6-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="92bd6-182">使用参数指定的值（如果有）也存储在此字段中，但是在默认输出中不可见。</span><span class="sxs-lookup"><span data-stu-id="92bd6-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="92bd6-183">此字段包含对字段中的对象修改 `ObjectModified` 的属性。</span><span class="sxs-lookup"><span data-stu-id="92bd6-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="92bd6-184">此属性的旧值和存储的新值也存储在此字段中，但在默认输出中不可见。</span><span class="sxs-lookup"><span data-stu-id="92bd6-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="92bd6-185">此字段包含字段中运行 cmdlet 的用户的 `CmdletName` 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="92bd6-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="92bd6-186">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="92bd6-187">此字段指定字段中的 cmdlet 是否 `CmdletName` 成功运行。</span><span class="sxs-lookup"><span data-stu-id="92bd6-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="92bd6-188">值为 或 `True` `False` 。</span><span class="sxs-lookup"><span data-stu-id="92bd6-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="92bd6-189">此字段包含在字段中的 cmdlet 未能成功完成时 `CmdletName` 生成的错误消息。</span><span class="sxs-lookup"><span data-stu-id="92bd6-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="92bd6-190">此字段包含运行字段中的 cmdlet 的 `CmdletName` 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="92bd6-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="92bd6-191">日期和时间存储为协调世界时 (UTC) 格式。</span><span class="sxs-lookup"><span data-stu-id="92bd6-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="92bd6-192">此字段指示运行字段中指定的 cmdlet `CmdletName` 的服务器。</span><span class="sxs-lookup"><span data-stu-id="92bd6-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="92bd6-193">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="92bd6-194">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="92bd6-195">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="92bd6-196">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="92bd6-197">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="92bd6-198">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="92bd6-199">此字段由 EOP 在内部使用。</span><span class="sxs-lookup"><span data-stu-id="92bd6-199">This field is used internally by EOP.</span></span>|
|