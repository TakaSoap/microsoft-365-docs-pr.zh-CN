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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在独立 Exchange Online Protection (EOP) 中运行管理员角色组报告。 当管理员向管理员角色组添加成员或从中删除成员时，此报告将记录日志。
ms.openlocfilehash: 95b216b41d1c83ba36bcc00e1f571e08c8bd1f73
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920616"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="1d445-104">在独立 EOP 中运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="1d445-104">Run an administrator role group report in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1d445-105">在独立 Exchange Online Protection 中 (EOP) 不含 Exchange Online 邮箱的组织，当管理员向管理角色组添加成员或从中删除成员时，该服务会记录每个事件。</span><span class="sxs-lookup"><span data-stu-id="1d445-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="1d445-106">有关独立 EOP 中的角色组的详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="1d445-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="1d445-107">在 Exchange 管理中心 (EAC) 中运行管理员角色组报告时，条目将显示为搜索结果，并包括受影响的角色组、更改角色组成员身份的用户以及进行成员身份更新的用户。</span><span class="sxs-lookup"><span data-stu-id="1d445-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="1d445-108">使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。</span><span class="sxs-lookup"><span data-stu-id="1d445-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1d445-109">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="1d445-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1d445-110">若要打开 Exchange 管理中心，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="1d445-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="1d445-111">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="1d445-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1d445-112">具体来说，您需要 "审核日志" 或 "View-Only 审核日志" 角色，默认情况下这些角色分配给 ComplianceManagement、OrganizationManagement (global admins) 和 SecurityAdministrator 角色组。</span><span class="sxs-lookup"><span data-stu-id="1d445-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="1d445-113">有关详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="1d445-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="1d445-114">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="1d445-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="1d445-115">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="1d445-115">Having problems?</span></span> <span data-ttu-id="1d445-116">请在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="1d445-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="1d445-117">使用 EAC 运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="1d445-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="1d445-118">运行管理员角色组报告，以查找在特定时间段内对管理角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1d445-118">Run the administrator role group report to find the changes to management role groups within a particular time frame.</span></span>

1. <span data-ttu-id="1d445-119">在 EAC 中，转到 " **合规性管理** \> **审核** "，然后选择 " **运行管理员角色组报告** "。</span><span class="sxs-lookup"><span data-stu-id="1d445-119">In the EAC, go to **Compliance management** \> **Auditing** , and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="1d445-120">在打开的 " **搜索对管理员角色组的更改** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="1d445-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1d445-121">" **开始日期** " 和 " **结束日期** "：输入日期范围。</span><span class="sxs-lookup"><span data-stu-id="1d445-121">**Start date** and **End date** : Enter a date range.</span></span> <span data-ttu-id="1d445-122">默认情况下，报告将搜索在过去两周内对管理员角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1d445-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="1d445-123">**选择角色组** ：默认情况下，搜索所有角色组。</span><span class="sxs-lookup"><span data-stu-id="1d445-123">**Select role groups** : By default, all role groups are searched.</span></span> <span data-ttu-id="1d445-124">若要按特定角色组筛选结果，请单击 " **选择角色组** "。</span><span class="sxs-lookup"><span data-stu-id="1d445-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="1d445-125">在出现的对话框中，选择一个角色组，然后单击 " **加载项 >** "。</span><span class="sxs-lookup"><span data-stu-id="1d445-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="1d445-126">根据需要重复此步骤多次，然后在完成后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="1d445-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="1d445-127">完成后，请单击 " **搜索** "。</span><span class="sxs-lookup"><span data-stu-id="1d445-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="1d445-p108">如果使用指定的条件找到了所有更改，则这些更改会显示在结果窗格中。单击搜索结果中的角色组可在详细信息窗格中查看更改。</span><span class="sxs-lookup"><span data-stu-id="1d445-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1d445-130">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="1d445-130">How do you know this worked?</span></span>

<span data-ttu-id="1d445-p109">如果您已成功运行管理员角色组报告，那么在此日期范围内更改的角色组将显示在搜索结果窗格中。如果没有显示任何结果，那么在指定日期范围内没有发生对角色组的任何更改。如果您认为应该显示结果，请更改日期范围，然后再次运行报告。</span><span class="sxs-lookup"><span data-stu-id="1d445-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="1d445-134">监视角色组成员身份的更改</span><span class="sxs-lookup"><span data-stu-id="1d445-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="1d445-p110">向某个角色组添加成员或删除其中的成员时，在详细信息窗格中显示的搜索结果将会指示角色组成员身份已进行更新，并列出当前的成员。但搜索结果并不会明确地指出已添加或已删除的用户。</span><span class="sxs-lookup"><span data-stu-id="1d445-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="1d445-137">若要确定是否添加或删除了某个用户，则必须对报告中的两个不同条目进行比较。</span><span class="sxs-lookup"><span data-stu-id="1d445-137">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="1d445-138">例如，让我们来看看 " **支持人员** " 角色组的以下日志条目：</span><span class="sxs-lookup"><span data-stu-id="1d445-138">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="1d445-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="1d445-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="1d445-140">Administrator</span><span class="sxs-lookup"><span data-stu-id="1d445-140">Administrator</span></span> <br> <span data-ttu-id="1d445-141">Updated members: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="1d445-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="1d445-142">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="1d445-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="1d445-143">Administrator</span><span class="sxs-lookup"><span data-stu-id="1d445-143">Administrator</span></span> <br> <span data-ttu-id="1d445-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="1d445-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="1d445-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="1d445-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="1d445-146">Administrator</span><span class="sxs-lookup"><span data-stu-id="1d445-146">Administrator</span></span> <br> <span data-ttu-id="1d445-147">Updated members: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="1d445-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="1d445-148">在本示例中，Administrator 用户帐户做出了以下更改：</span><span class="sxs-lookup"><span data-stu-id="1d445-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="1d445-149">在2/06/2018 上，他们添加了用户 tonip。</span><span class="sxs-lookup"><span data-stu-id="1d445-149">On 2/06/2018, they added the user tonip.</span></span>
- <span data-ttu-id="1d445-150">在2/19/2018 上，他们删除了用户 pilarp。</span><span class="sxs-lookup"><span data-stu-id="1d445-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="1d445-151">使用独立 Exchange Online PowerShell 搜索审核日志条目</span><span class="sxs-lookup"><span data-stu-id="1d445-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="1d445-152">您可以使用 Exchange Online PowerShell 搜索符合指定条件的审核日志条目。</span><span class="sxs-lookup"><span data-stu-id="1d445-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="1d445-153">有关搜索条件的列表，请参阅 [search-adminauditlog 搜索条件](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="1d445-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="1d445-154">此过程使用 **search-adminauditlog** cmdlet 并在 Exchange Online PowerShell 中显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="1d445-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="1d445-155">如果需要返回超出在 **New-AdminAuditLogSearch** cmdlet 或 EAC"审核报告"报告中定义的限制的一组结果时，可使用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1d445-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="1d445-156">若要搜索满足指定条件的审核日志，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="1d445-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="1d445-157">默认情况下， **Search-AdminAuditLog** cmdlet 最多可返回 1,000 个日志条目。</span><span class="sxs-lookup"><span data-stu-id="1d445-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="1d445-158">使用 _ResultSize_ 参数可以指定最长250000个日志条目。</span><span class="sxs-lookup"><span data-stu-id="1d445-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="1d445-159">或者，使用值 `Unlimited` 返回所有条目。</span><span class="sxs-lookup"><span data-stu-id="1d445-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="1d445-160">本示例将使用以下条件执行对所有审核日志条目的搜索：</span><span class="sxs-lookup"><span data-stu-id="1d445-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="1d445-161">**开始日期** ：08/04/2018</span><span class="sxs-lookup"><span data-stu-id="1d445-161">**Start date** : 08/04/2018</span></span>
- <span data-ttu-id="1d445-162">**结束日期** ：10/03/2018</span><span class="sxs-lookup"><span data-stu-id="1d445-162">**End date** : 10/03/2018</span></span>
- <span data-ttu-id="1d445-163">**用户 id** ： `davids` 、 `chrisd` 、 `kima`</span><span class="sxs-lookup"><span data-stu-id="1d445-163">**User IDs** : `davids`, `chrisd`, `kima`</span></span>
- <span data-ttu-id="1d445-164">**Cmdlet** ： **Set-邮箱**</span><span class="sxs-lookup"><span data-stu-id="1d445-164">**Cmdlets** : **Set-Mailbox**</span></span>
- <span data-ttu-id="1d445-165">**参数** ： _ProhibitSendQuota_ 、 _ProhibitSendReceiveQuota_ 、 _IssueWarningQuota_ 、 _MaxSendSize_ 、 _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="1d445-165">**Parameters** : _ProhibitSendQuota_ , _ProhibitSendReceiveQuota_ , _IssueWarningQuota_ , _MaxSendSize_ , _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="1d445-p114">本示例将搜索对特定邮箱所做的更改。此操作在进行故障排除或需要为调查提供信息时很有用。使用以下条件：</span><span class="sxs-lookup"><span data-stu-id="1d445-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="1d445-169">**开始日期** ：05/01/2018</span><span class="sxs-lookup"><span data-stu-id="1d445-169">**Start date** : 05/01/2018</span></span>
- <span data-ttu-id="1d445-170">**结束日期** ：10/03/2018</span><span class="sxs-lookup"><span data-stu-id="1d445-170">**End date** : 10/03/2018</span></span>
- <span data-ttu-id="1d445-171">**对象 ID** ： contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="1d445-171">**Object ID** : contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="1d445-172">如果您的搜索返回了多个日志条目，我们建议使用 Exchange Online PowerShell 中提供的过程 **来搜索审核日志条目，并** 在本文后面的内容中将结果发送给收件人。</span><span class="sxs-lookup"><span data-stu-id="1d445-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article.</span></span> <span data-ttu-id="1d445-173">该部分提供的过程将 XML 文件以电子邮件附件的形式发送给指定的收件人，从而使您更易于提取您感兴趣的数据。</span><span class="sxs-lookup"><span data-stu-id="1d445-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="1d445-174">有关详细的语法和参数信息，请参阅 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)。</span><span class="sxs-lookup"><span data-stu-id="1d445-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="1d445-175">查看审核日志条目的详细信息</span><span class="sxs-lookup"><span data-stu-id="1d445-175">View details of audit log entries</span></span>

<span data-ttu-id="1d445-176">**Search-adminauditlog** Cmdlet 返回 [审核日志内容](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)中所述的字段。</span><span class="sxs-lookup"><span data-stu-id="1d445-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="1d445-177">在此 cmdlet 返回的字段中， **CmdletParameters** 和 **ModifiedProperties** 两个字段包含默认情况下不可见的附加信息。</span><span class="sxs-lookup"><span data-stu-id="1d445-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties** , contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="1d445-178">若要查看 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1d445-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="1d445-179">或者，您可以使用 Exchange Online PowerShell 中的过程来 **搜索审核日志条目，并在下文中将结果发送到收件人** ，以创建 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1d445-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this article to create an XML file.</span></span>

<span data-ttu-id="1d445-180">此过程将使用以下概念：</span><span class="sxs-lookup"><span data-stu-id="1d445-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="1d445-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="1d445-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="1d445-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="1d445-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="1d445-183">确定搜索时要使用的条件，然后运行 **Search-AdminAuditLog** cmdlet，并使用以下命令将结果存储在一个变量中。</span><span class="sxs-lookup"><span data-stu-id="1d445-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. <span data-ttu-id="1d445-184">每个审核日志条目都作为数组元素存储在变量中 `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="1d445-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="1d445-185">可以通过指定其数组元素索引来选择数组元素。</span><span class="sxs-lookup"><span data-stu-id="1d445-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="1d445-186">数组元素索引以零 (0) 开始，即第一个数组元素的索引为 0。</span><span class="sxs-lookup"><span data-stu-id="1d445-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="1d445-187">例如，如果要检索第 5 个数组元素，其索引为 4，则应使用以下命令进行检索。</span><span class="sxs-lookup"><span data-stu-id="1d445-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

   ```PowerShell
   $Results[4]
   ```

3. <span data-ttu-id="1d445-p119">上述命令将返回数组元素 4 中存储的日志条目。若要查看此日志条目的 **CmdletParameters** 和 **ModifiedProperties** 字段的内容，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="1d445-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. <span data-ttu-id="1d445-190">若要查看其他日志条目的 **CmdletParameters** 或 **ModifiedParameters** 字段的内容，请更改数组元素索引。</span><span class="sxs-lookup"><span data-stu-id="1d445-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
