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
description: 管理员可以了解如何在独立 Exchange Online Protection (EOP) 中运行管理员角色组) 。 此报告记录管理员向管理员角色组添加或删除成员时。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d778e807a087a5e29b31645457d4a81bd05c5649
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288015"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="51a9e-104">在独立 EOP 中运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="51a9e-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="51a9e-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="51a9e-105">**Applies to**</span></span>
-  [<span data-ttu-id="51a9e-106">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="51a9e-106">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="51a9e-107">在独立 Exchange Online Protection (EOP) 组织中，当管理员向 管理角色 组添加或删除成员时，该服务将记录每次事件。</span><span class="sxs-lookup"><span data-stu-id="51a9e-107">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="51a9e-108">有关独立 EOP 中的角色组详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-108">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="51a9e-109">在 Exchange 管理中心 (EAC) 中运行管理员角色组报告时，条目将显示为搜索结果，并包括受影响的角色组、更改角色组成员身份的用户、更改时间以及进行了哪些成员身份更新。</span><span class="sxs-lookup"><span data-stu-id="51a9e-109">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="51a9e-110">使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。</span><span class="sxs-lookup"><span data-stu-id="51a9e-110">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51a9e-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="51a9e-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51a9e-112">若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="51a9e-113">您需要在 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="51a9e-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="51a9e-114">具体来说，您需要"审核 **日志**"或"仅查看审核 **日志**"角色，该角色默认分配给"组织管理"、"合规性管理"和"**安全** 管理员"角色组。 </span><span class="sxs-lookup"><span data-stu-id="51a9e-114">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="51a9e-115">有关详细信息，请参阅独立 [EOP 中](feature-permissions-in-eop.md) 的权限和使用 [EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="51a9e-116">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 Exchange Online 中 [Exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="51a9e-117">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="51a9e-117">Having problems?</span></span> <span data-ttu-id="51a9e-118">请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="51a9e-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="51a9e-119">使用 EAC 运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="51a9e-119">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="51a9e-120">运行管理员角色组报告以查找特定时间范围内对管理角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="51a9e-120">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="51a9e-121">在 EAC 中，转到 **"合规性管理** \> **审核**"，然后选择"运行 **管理员角色组报告"。**</span><span class="sxs-lookup"><span data-stu-id="51a9e-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="51a9e-122">在 **打开的"搜索管理员角色** 组更改"页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="51a9e-122">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="51a9e-123">**开始日期和\*\*\*\*结束日期**：输入日期范围。</span><span class="sxs-lookup"><span data-stu-id="51a9e-123">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="51a9e-124">默认情况下，报告将搜索在过去两周内对管理员角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="51a9e-124">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="51a9e-125">**选择角色组**：默认情况下，搜索所有角色组。</span><span class="sxs-lookup"><span data-stu-id="51a9e-125">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="51a9e-126">若要按特定角色组筛选结果，请单击 **"选择角色组"。**</span><span class="sxs-lookup"><span data-stu-id="51a9e-126">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="51a9e-127">在出现的对话框中，选择一个角色组，然后单击 **>。**</span><span class="sxs-lookup"><span data-stu-id="51a9e-127">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="51a9e-128">根据需要多次重复此步骤，然后在 **完成后单击"** 确定"。</span><span class="sxs-lookup"><span data-stu-id="51a9e-128">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="51a9e-129">完成后，单击"搜索 **"。**</span><span class="sxs-lookup"><span data-stu-id="51a9e-129">When you're finished, click **Search**.</span></span>

<span data-ttu-id="51a9e-p108">如果使用指定的条件找到了所有更改，则这些更改会显示在结果窗格中。单击搜索结果中的角色组可在详细信息窗格中查看更改。</span><span class="sxs-lookup"><span data-stu-id="51a9e-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="51a9e-132">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="51a9e-132">How do you know this worked?</span></span>

<span data-ttu-id="51a9e-p109">如果您已成功运行管理员角色组报告，那么在此日期范围内更改的角色组将显示在搜索结果窗格中。如果没有显示任何结果，那么在指定日期范围内没有发生对角色组的任何更改。如果您认为应该显示结果，请更改日期范围，然后再次运行报告。</span><span class="sxs-lookup"><span data-stu-id="51a9e-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="51a9e-136">监视角色组成员身份的更改</span><span class="sxs-lookup"><span data-stu-id="51a9e-136">Monitor changes to role group membership</span></span>

<span data-ttu-id="51a9e-p110">向某个角色组添加成员或删除其中的成员时，在详细信息窗格中显示的搜索结果将会指示角色组成员身份已进行更新，并列出当前的成员。但搜索结果并不会明确地指出已添加或已删除的用户。</span><span class="sxs-lookup"><span data-stu-id="51a9e-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="51a9e-139">若要确定是否添加或删除了某个用户，则必须对报告中的两个不同条目进行比较。</span><span class="sxs-lookup"><span data-stu-id="51a9e-139">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="51a9e-140">例如，让我们看一下 **HelpDesk** 角色组的以下日志条目：</span><span class="sxs-lookup"><span data-stu-id="51a9e-140">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="51a9e-141">1/27/2018 4：43 PM</span><span class="sxs-lookup"><span data-stu-id="51a9e-141">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="51a9e-142">Administrator</span><span class="sxs-lookup"><span data-stu-id="51a9e-142">Administrator</span></span> <br> <span data-ttu-id="51a9e-143">Updated members: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="51a9e-143">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="51a9e-144">2/06/2018 10：09 AM</span><span class="sxs-lookup"><span data-stu-id="51a9e-144">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="51a9e-145">Administrator</span><span class="sxs-lookup"><span data-stu-id="51a9e-145">Administrator</span></span> <br> <span data-ttu-id="51a9e-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="51a9e-146">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="51a9e-147">2018 年 2 月 19 日下午 2：12</span><span class="sxs-lookup"><span data-stu-id="51a9e-147">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="51a9e-148">Administrator</span><span class="sxs-lookup"><span data-stu-id="51a9e-148">Administrator</span></span> <br> <span data-ttu-id="51a9e-149">Updated members: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="51a9e-149">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="51a9e-150">在本示例中，Administrator 用户帐户做出了以下更改：</span><span class="sxs-lookup"><span data-stu-id="51a9e-150">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="51a9e-151">在 2018 年 2 月 6 日，他们添加了用户提示。</span><span class="sxs-lookup"><span data-stu-id="51a9e-151">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="51a9e-152">2018 年 2 月 19 日，他们删除了用户 pilarp。</span><span class="sxs-lookup"><span data-stu-id="51a9e-152">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="51a9e-153">使用独立的 Exchange Online PowerShell 搜索审核日志条目</span><span class="sxs-lookup"><span data-stu-id="51a9e-153">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="51a9e-154">您可以使用 Exchange Online PowerShell 搜索满足审核日志条件的电子邮件条目。</span><span class="sxs-lookup"><span data-stu-id="51a9e-154">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="51a9e-155">有关搜索条件的列表，请参阅 [Search-AdminAuditLog 搜索条件](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-155">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="51a9e-156">此过程使用 **Search-AdminAuditLog** cmdlet，并显示 Exchange Online PowerShell 中的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="51a9e-156">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="51a9e-157">如果需要返回超出在 **New-AdminAuditLogSearch** cmdlet 或 EAC"审核报告"报告中定义的限制的一组结果时，可使用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51a9e-157">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="51a9e-158">若要搜索满足指定条件的审核日志，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="51a9e-158">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="51a9e-159">默认情况下， **Search-AdminAuditLog** cmdlet 最多可返回 1,000 个日志条目。</span><span class="sxs-lookup"><span data-stu-id="51a9e-159">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="51a9e-160">使用 _ResultSize_ 参数可以指定最多 250，000 个日志条目。</span><span class="sxs-lookup"><span data-stu-id="51a9e-160">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="51a9e-161">或者，使用 `Unlimited` 该值返回所有条目。</span><span class="sxs-lookup"><span data-stu-id="51a9e-161">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="51a9e-162">本示例将使用以下条件执行对所有审核日志条目的搜索：</span><span class="sxs-lookup"><span data-stu-id="51a9e-162">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="51a9e-163">**开始日期**：08/04/2018</span><span class="sxs-lookup"><span data-stu-id="51a9e-163">**Start date**: 08/04/2018</span></span>
- <span data-ttu-id="51a9e-164">**结束日期**：2018 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="51a9e-164">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="51a9e-165">**用户 ID：** `davids` ， `chrisd` ， `kima`</span><span class="sxs-lookup"><span data-stu-id="51a9e-165">**User IDs**: `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="51a9e-166">**Cmdlet：Set-Mailbox** </span><span class="sxs-lookup"><span data-stu-id="51a9e-166">**Cmdlets**: **Set-Mailbox**</span></span>
- <span data-ttu-id="51a9e-167">**参数 ：** _ProhibitSendQuota_、 _ProhibitSendReceiveQuota_、 _IssueWarningQuota_、 _MaxSendSize_、 _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="51a9e-167">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="51a9e-p114">本示例将搜索对特定邮箱所做的更改。此操作在进行故障排除或需要为调查提供信息时很有用。使用以下条件：</span><span class="sxs-lookup"><span data-stu-id="51a9e-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="51a9e-171">**开始日期**：05/01/2018</span><span class="sxs-lookup"><span data-stu-id="51a9e-171">**Start date**: 05/01/2018</span></span>
- <span data-ttu-id="51a9e-172">**结束日期**：2018 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="51a9e-172">**End date**: 10/03/2018</span></span>
- <span data-ttu-id="51a9e-173">**对象 ID**：contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="51a9e-173">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="51a9e-174">如果搜索返回许多日志条目，我们建议您使用 **使用 Exchange Online PowerShell 中** 提供的过程搜索 审核日志 条目，并将结果发送给本文稍后介绍的收件人。</span><span class="sxs-lookup"><span data-stu-id="51a9e-174">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="51a9e-175">该部分提供的过程将 XML 文件以电子邮件附件的形式发送给指定的收件人，从而使您更易于提取您感兴趣的数据。</span><span class="sxs-lookup"><span data-stu-id="51a9e-175">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="51a9e-176">有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-176">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="51a9e-177">查看审核日志条目的详细信息</span><span class="sxs-lookup"><span data-stu-id="51a9e-177">View details of audit log entries</span></span>

<span data-ttu-id="51a9e-178">**Search-AdminAuditLog** cmdlet 返回审核日志 [内容中描述的字段](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)。</span><span class="sxs-lookup"><span data-stu-id="51a9e-178">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="51a9e-179">在此 cmdlet 返回的字段中， **CmdletParameters** 和 **ModifiedProperties** 两个字段包含默认情况下不可见的附加信息。</span><span class="sxs-lookup"><span data-stu-id="51a9e-179">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="51a9e-180">若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="51a9e-180">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="51a9e-181">或者，您可以使用 Exchange Online **PowerShell 中** 的过程搜索审核日志条目，并将结果发送给本文稍后介绍的收件人以创建 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="51a9e-181">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="51a9e-182">此过程将使用以下概念：</span><span class="sxs-lookup"><span data-stu-id="51a9e-182">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="51a9e-183">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="51a9e-183">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="51a9e-184">about_Variables</span><span class="sxs-lookup"><span data-stu-id="51a9e-184">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="51a9e-185">确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。</span><span class="sxs-lookup"><span data-stu-id="51a9e-185">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="51a9e-186">每个审核日志项都存储为变量中的数组元素 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="51a9e-186">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="51a9e-187">可以通过指定其数组元素索引来选择数组元素。</span><span class="sxs-lookup"><span data-stu-id="51a9e-187">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="51a9e-188">数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。</span><span class="sxs-lookup"><span data-stu-id="51a9e-188">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="51a9e-189">例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。</span><span class="sxs-lookup"><span data-stu-id="51a9e-189">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="51a9e-p119">上述命令将返回数组元素 4 中存储的日志条目。若要查看此日志条目的 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="51a9e-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="51a9e-192">若要查看其他日志条目的 **CmdletParameters** 或 **ModifiedParameters** 字段的内容，请更改数组元素索引。</span><span class="sxs-lookup"><span data-stu-id="51a9e-192">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
