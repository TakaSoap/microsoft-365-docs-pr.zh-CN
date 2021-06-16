---
title: 管理审核日志保留策略
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 审核日志保留策略是 Microsoft 365 中新增的高级审核功能的一部分。 通过审核日志保留策略，可指定组织中审核日志的保留时间。
ms.openlocfilehash: 8df2e240440ad33ac82d926b63cc495d1aaef692
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925147"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="f3c1e-104">管理审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-104">Manage audit log retention policies</span></span>

<span data-ttu-id="f3c1e-105">可在安全与合规中心创建和管理审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="f3c1e-106">审核日志保留策略是 Microsoft 365 中新增的高级审核功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="f3c1e-107">通过审核日志保留策略，可指定组织中审核日志的保留时间。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="f3c1e-108">可将审核日志保留长达 10 年时间。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-108">You can retain audit logs for up to 10 years.</span></span> <span data-ttu-id="f3c1e-109">可以根据以下标准创建策略：</span><span class="sxs-lookup"><span data-stu-id="f3c1e-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="f3c1e-110">一个或多个 Microsoft 365 服务中的所有活动</span><span class="sxs-lookup"><span data-stu-id="f3c1e-110">All activities in one or more Microsoft 365 services</span></span>
- <span data-ttu-id="f3c1e-111">所有用户或特定用户执行的特定活动（在 Microsoft 365 服务中）</span><span class="sxs-lookup"><span data-stu-id="f3c1e-111">Specific activities (in a Microsoft 365 service) performed by all users or by specific users</span></span>
- <span data-ttu-id="f3c1e-112">优先级，用于指定当组织中有多个策略时优先使用哪个策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="f3c1e-113">默认审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-113">Default audit log retention policy</span></span>

<span data-ttu-id="f3c1e-114">Microsoft 365 中的高级审核功能为所有组织提供默认审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="f3c1e-115">此策略将所有的 Exchange Online、SharePoint Online、OneDrive for Business 和 Azure Active Directory 审核记录保留一年。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-115">This policy retains all Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="f3c1e-116">此默认策略将保留审核记录，其中包含针对 **工作负载** 属性（即活动所发生的服务）的 **Exchange**、**SharePoint**、**OneDrive**、**AzureActiveDirectory** 的值。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-116">This default policy retains audit records that contain the value of **Exchange**, **SharePoint**, **OneDrive**, **AzureActiveDirectory** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="f3c1e-117">无法修改默认策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-117">The default policy can't be modified.</span></span> <span data-ttu-id="f3c1e-118">请参阅本文的[详细信息](#more-information)部分，以获取默认策略中包含的每个工作负载的记录类型列表。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="f3c1e-119">默认审核日志保留策略仅适用于分配了 Office 365 或 Microsoft 365 E5 许可证或具有 Microsoft 365 E5 合规版或 E5 电子数据展示和审核加载项许可证的用户执行的活动审核记录。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="f3c1e-120">如果你的组织中有非 E5 用户或来宾用户，则其相应的审核记录将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-120">If you have non-E5 users or guest users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="f3c1e-121">在创建审核日志保留策略之前</span><span class="sxs-lookup"><span data-stu-id="f3c1e-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="f3c1e-122">必须在安全与合规中心为你分配了“组织配置”角色，这样才能创建或修改审核保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="f3c1e-123">在组织中，你最多可以拥有 50 个审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="f3c1e-124">若要将审核日志保留超过 90 天（以及最多 1 年），必须为生成审核日志的用户（通过执行审核活动）分配 Office 365 E5 或 Microsoft 365 E5 许可证，或者该用户必须具有 Microsoft 365 E5 合规或 E5 电子数据展示和审核加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-124">To retain an audit log for longer than 90 days (and up to 1 year), the user who generates the audit log (by performing an audited activity) must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="f3c1e-125">若要将审核日志保留 10 年，除 E5 许可证外，还必须向生成审核日志的用户分配 10 年审核日志保留附加产品许可证以及 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-125">To retain audit logs for 10 years, the user who generates the audit log must also be assigned a 10-year audit log retention add-on license in addition to an E5 license.</span></span>

- <span data-ttu-id="f3c1e-p106">所有自定义审核日志保留策略（由组织创建）均优先于默认保留策略。例如，如果为具有短于一年保留期的 Exchange 邮箱活动创建审核日志保留策略，则 Exchange 邮箱活动的审核记录将按照自定义策略所指定的较短期限保留。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-p106">All custom audit log retention policies (created by your organization) take priority over the default retention policy. For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy"></a><span data-ttu-id="f3c1e-128">创建审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-128">Create an audit log retention policy</span></span>

1. <span data-ttu-id="f3c1e-129">转到 <https://compliance.microsoft.com>，然后使用在安全与合规中心的“权限”页上分配了“组织配置”角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-129">Go to <https://compliance.microsoft.com> and sign in with a user account that's assigned the Organization Configuration role on the Permissions page in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f3c1e-130">在 Microsoft 365 合规中心的左窗格中，单击“**显示所有**”，然后单击“**审核**”。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-130">In the left pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

3. <span data-ttu-id="f3c1e-131">点击“**审核保留保留策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-131">Click the **Audit retention policies** tab.</span></span>

4. <span data-ttu-id="f3c1e-132">单击“**创建审核保留策略**”，然后在弹出页面上填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="f3c1e-132">Click **Create audit retention policy**, and then complete the following fields on the flyout page:</span></span>

   ![新审核保留策略弹出页面](../media/CreateAuditLogRetentionPolicy.png)

   1. <span data-ttu-id="f3c1e-134">**原则名称**：审核日志保留策略的名称。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-134">**Policy name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="f3c1e-135">此名称在你的组织中必须是唯一的，并且在创建策略后不能更改。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-135">This name must be unique in your organization, and it can't be change after the policy is created.</span></span>

   2. <span data-ttu-id="f3c1e-136">**说明**：可选，但有助于提供有关策略的信息，例如记录类型或工作负载、策略中指定的用户以及期限。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-136">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   3. <span data-ttu-id="f3c1e-137">**用户**：选择一个或多个要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-137">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="f3c1e-138">如果将此框留空，则该策略将应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-138">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="f3c1e-139">如果将“**记录类型**”留空，则必须选择用户。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-139">If you leave the **Record type** blank, then you must select a user.</span></span>

   4. <span data-ttu-id="f3c1e-140">**记录类型**：将为其应用策略的审核记录类型。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-140">**Record type:** The audit record type the policy applies to.</span></span> <span data-ttu-id="f3c1e-141">如果将此属性留空，则必须在“**用户**”框中选择用户。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-141">If you leave this property blank, you must select a user in the **Users** box.</span></span> <span data-ttu-id="f3c1e-142">可选择一种记录类型或多个记录类型：</span><span class="sxs-lookup"><span data-stu-id="f3c1e-142">You can select a single record type or multiple record types:</span></span>
      - <span data-ttu-id="f3c1e-143">如果选择一条记录类型，将动态显示“**活动**”字段。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-143">If you select a single record type, the **Activities** field is dynamically displayed.</span></span> <span data-ttu-id="f3c1e-144">可使用下拉列表从所选记录类型中选择活动，以便对其应用策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-144">You can use the drop-down list to select activities from the selected record type to apply the policy to.</span></span> <span data-ttu-id="f3c1e-145">如果未选择特定活动，则该策略将应用于所选记录类型的所有活动。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-145">If you don't choose specific activities, the policy will apply to all activities of the selected record type.</span></span>
      - <span data-ttu-id="f3c1e-146">如果选择多个记录类型，则不能选择活动。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-146">If you select multiple record types, you don't have the ability to select activities.</span></span> <span data-ttu-id="f3c1e-147">该策略将应用于所选记录类型的所有活动。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-147">The policy will apply to all activities of the selected record types.</span></span>

   5. <span data-ttu-id="f3c1e-148">**期限**：保留符合策略条件的审核日志的时间。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-148">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   6. <span data-ttu-id="f3c1e-149">**优先级**：此值确定处理组织中的审核日志保留策略的顺序。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-149">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="f3c1e-150">该值越小，表示优先级越高。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-150">A lower value indicates a higher priority.</span></span> <span data-ttu-id="f3c1e-151">有效优先级为 **1** 到 **10000** 之间的数值。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-151">Valid priorities are numerical values between **1** and **10000**.</span></span> <span data-ttu-id="f3c1e-152">值 **1** 优先级最高，值为 **10000** 则优先级最低。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-152">A value of **1** is the highest priority, and a value of **10000** is the lowest priority.</span></span> <span data-ttu-id="f3c1e-153">例如，如果策略的值为 **5**，则优先于值为 **10** 的策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-153">For example, a policy with a value of **5** takes priority over a policy with a value of **10**.</span></span> <span data-ttu-id="f3c1e-154">如前文所述，任何自定义审核日志保留策略都优先于组织的默认策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-154">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

5. <span data-ttu-id="f3c1e-155">单击“**保存**”以创建新的审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-155">Click **Save** to create the new audit log retention policy.</span></span>

<span data-ttu-id="f3c1e-156">新策略将显示在“**审核保留策略**”选项卡上的列表中。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-156">The new policy is displayed in the list on the **Audit retention policies** tab.</span></span>

## <a name="manage-audit-log-retention-policies-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="f3c1e-157">在 Microsoft 365 合规中心管理审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-157">Manage audit log retention policies in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="f3c1e-158">审核日志保留策略列在“**审核保留策略**”选项卡（也称为 *仪表板*）上。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-158">Audit log retention policies are listed on the **Audit retention policies** tab (also called the *dashboard*).</span></span> <span data-ttu-id="f3c1e-159">可使用仪表板查看、编辑和删除审核保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-159">You can use the dashboard to view, edit, and delete audit retention policies.</span></span>

### <a name="view-policies-in-the-dashboard"></a><span data-ttu-id="f3c1e-160">在仪表板中查看策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-160">View policies in the dashboard</span></span>

<span data-ttu-id="f3c1e-161">审核日志保留策略列在仪表板中。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-161">Audit log retention policies are listed in the dashboard.</span></span> <span data-ttu-id="f3c1e-162">在仪表板中查看策略的一个优点是，可以单击“**优先级**”列以按它们应用的优先级列出策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-162">One advantage of viewing policies in the dashboard is that you can click the **Priority** column to list the policies in the priority in which they are applied.</span></span> <span data-ttu-id="f3c1e-163">如前所述，值越大表示优先级越高。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-163">As previously explained, a higher value indicates a higher priority.</span></span>

![“审核保留策略”仪表板中的“优先级”列](../media/AuditLogRetentionDashboardPriority.png)

<span data-ttu-id="f3c1e-165">也可以选择一个策略以在浮出页面上显示其设置。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-165">You can also select a policy to display its settings on the flyout page.</span></span>

> [!NOTE]
> <span data-ttu-id="f3c1e-166">仪表板中不显示你的组织的默认审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-166">The default audit log retention policy for your organization isn't displayed in the dashboard.</span></span>

### <a name="edit-policies-in-the-dashboard"></a><span data-ttu-id="f3c1e-167">在仪表板中编辑策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-167">Edit policies in the dashboard</span></span>

<span data-ttu-id="f3c1e-168">要编辑策略，请选择它以显示浮出页面。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-168">To edit a policy, select it to display the flyout page.</span></span> <span data-ttu-id="f3c1e-169">可以修改一个或多个设置，然后保存更改。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-169">You can modify one or more setting and then save your changes.</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="f3c1e-170">如果使用 **New UnifiedAuditLogRetentionPolicy** cmdlet，则可以为仪表板中“**创建审核保留策略**”工具中不可用的记录类型或活动创建审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-170">If you use the **New-UnifiedAuditLogRetentionPolicy** cmdlet, it's possible to create an audit log retention policy for record types or activities that aren't available in the **Create audit retention policy** tool in the dashboard.</span></span> <span data-ttu-id="f3c1e-171">在这种情况下，你将无法从“**审核保留策略**”仪表板编辑策略（例如，更改保留期或添加和删除活动）。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-171">In this case, you won't be able to edit the policy (for example, change the retention duration or add and remove activities) from the **Audit retention policies** dashboard.</span></span> <span data-ttu-id="f3c1e-172">只能在合规中心中查看和删除策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-172">You'll only be able to view and delete the policy in the compliance center.</span></span> <span data-ttu-id="f3c1e-173">若要编辑策略，必须在安全与合规中心 PowerShell 中使用 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet。></span><span class="sxs-lookup"><span data-stu-id="f3c1e-173">To edit the policy, you'll have to use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell.></span></span>
>
> <span data-ttu-id="f3c1e-174">**提示**：对于必须使用 PowerShell 编辑的策略，浮出页面顶部会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-174">**Tip:** A message is displayed at the top of the flyout page for policies that have to be edited using PowerShell.</span></span>

### <a name="delete-policies-in-the-dashboard"></a><span data-ttu-id="f3c1e-175">在仪表板中删除策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-175">Delete policies in the dashboard</span></span>

<span data-ttu-id="f3c1e-176">若要删除策略，单击“**删除**”“![删除图标](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)”图标，然后确认要删除该策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-176">To delete a policy, click the **Delete** ![Delete icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) icon and then confirm that you want to delete the policy.</span></span> <span data-ttu-id="f3c1e-177">已从仪表板中删除策略，但从组织中删除策略最长可能需要 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-177">The policy is removed from the dashboard, but it might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a><span data-ttu-id="f3c1e-178">在 PowerShell 中创建和管理审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-178">Create and manage audit log retention policies in PowerShell</span></span>

<span data-ttu-id="f3c1e-179">还可以使用安全与合规中心 PowerShell 来创建和管理审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-179">You can also use Security & Compliance Center PowerShell to create and manage audit log retention policies.</span></span> <span data-ttu-id="f3c1e-180">使用 PowerShell 的一个原因是为 UI 中不可用的记录类型或活动创建策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-180">One reason to use PowerShell is to create a policy for a record type or activity that isn't available in the UI.</span></span>

### <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="f3c1e-181">在 PowerShell 中创建审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-181">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="f3c1e-182">请按照以下步骤在 PowerShell 中创建审核日志保留策略：</span><span class="sxs-lookup"><span data-stu-id="f3c1e-182">Follow these steps to create an audit log retention policy in PowerShell:</span></span>

1. <span data-ttu-id="f3c1e-183">[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-183">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f3c1e-184">运行以下命令以创建审核日志保留策略：</span><span class="sxs-lookup"><span data-stu-id="f3c1e-184">Run the following command to create an audit log retention policy:</span></span>

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

   <span data-ttu-id="f3c1e-185">本示例使用以下设置创建名为“Microsoft Teams 审核策略”的审核日志保留策略：</span><span class="sxs-lookup"><span data-stu-id="f3c1e-185">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="f3c1e-186">策略说明。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-186">A description of the policy.</span></span>
   - <span data-ttu-id="f3c1e-187">保留所有 Microsoft Teams 活动（由 *RecordType* 参数定义）。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-187">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>
   - <span data-ttu-id="f3c1e-188">将 Microsoft Teams 审核日志保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-188">Retains Microsoft Teams audit logs for 10 years.</span></span>
   - <span data-ttu-id="f3c1e-189">优先级为 100。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-189">A priority of 100.</span></span>

<span data-ttu-id="f3c1e-190">下面是创建审核日志保留策略的另一个示例。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-190">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="f3c1e-191">此策略将用户 admin@contoso.onmicrosoft.com 的“用户登录”活动的审核日志保留六个月。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-191">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="f3c1e-192">有关详细信息，请参阅 [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-192">For more information, see [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

### <a name="view-policies-in-powershell"></a><span data-ttu-id="f3c1e-193">在 PowerShell 中查看策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-193">View policies in PowerShell</span></span>

<span data-ttu-id="f3c1e-194">使用安全与合规中心 PowerShell 中的 [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet 查看审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-194">Use the [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to view audit log retention policies.</span></span>

<span data-ttu-id="f3c1e-195">下面是用于显示组织中所有审核日志保留策略的设置的示例命令。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-195">Here's a sample command to display the settings for all audit log retention policies in your organization.</span></span> <span data-ttu-id="f3c1e-196">此命令从最高优先级到最低优先级对策略进行排序。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-196">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="f3c1e-197">**Get-UnifiedAuditLogRetentionPolicy** cmdlet 不会返回组织的默认审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-197">The **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log retention policy for your organization.</span></span>

### <a name="edit-policies-in-powershell"></a><span data-ttu-id="f3c1e-198">在 PowerShell 中编辑策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-198">Edit policies in PowerShell</span></span>

<span data-ttu-id="f3c1e-199">使用安全与合规中心 PowerShell 中的 [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet 编辑现有审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-199">Use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to edit an existing audit log retention policy.</span></span>

### <a name="delete-policies-in-powershell"></a><span data-ttu-id="f3c1e-200">在 PowerShell 中删除策略</span><span class="sxs-lookup"><span data-stu-id="f3c1e-200">Delete policies in PowerShell</span></span>

<span data-ttu-id="f3c1e-201">使用安全与合规中心 PowerShell 中的 [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet 删除审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-201">Use the [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="f3c1e-202">从组织中删除策略最长可能需要 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-202">It might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="f3c1e-203">详细信息</span><span class="sxs-lookup"><span data-stu-id="f3c1e-203">More information</span></span>

<span data-ttu-id="f3c1e-204">如前文所述，Azure Active Directory，Exchange Online, SharePoint Online 和 OneDrive for Business 中针对操作的审核记录将默认保留一年。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-204">As previously stated, audit records for operations in Azure Active Directory, Exchange Online, SharePoint Online, and OneDrive for Business, are retained for one year by default.</span></span> <span data-ttu-id="f3c1e-205">下表列出了默认审核日志保留策略中包括的所有记录类型（针对每个服务）。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-205">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="f3c1e-206">这意味着具有此记录类型的任何操作的审核日志都将保留一年，除非自定义审核日志保留策略对特定的记录类型、操作或用户具有优先权。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-206">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="f3c1e-207">括号中显示了每种记录类型的枚举值（在审核记录中显示为 RecordType 属性值）。</span><span class="sxs-lookup"><span data-stu-id="f3c1e-207">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

<br>

****

|<span data-ttu-id="f3c1e-208">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="f3c1e-208">AzureActiveDirectory</span></span>|<span data-ttu-id="f3c1e-209">Exchange</span><span class="sxs-lookup"><span data-stu-id="f3c1e-209">Exchange</span></span> |<span data-ttu-id="f3c1e-210">SharePoint 或 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f3c1e-210">SharePoint or OneDrive</span></span>|
|---|---|---|
|<span data-ttu-id="f3c1e-211">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-211">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="f3c1e-212">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-212">ExchangeAdmin (1)</span></span>|<span data-ttu-id="f3c1e-213">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-213">ComplianceDLPSharePoint (11)</span></span>|
|<span data-ttu-id="f3c1e-214">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-214">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="f3c1e-215">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-215">ExchangeItem (2)</span></span>|<span data-ttu-id="f3c1e-216">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-216">ComplianceDLPSharePointClassification (33)</span></span>|
|<span data-ttu-id="f3c1e-217">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-217">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="f3c1e-218">Campaign (62)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-218">Campaign (62)</span></span>|<span data-ttu-id="f3c1e-219">Project (35)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-219">Project (35)</span></span>|
||<span data-ttu-id="f3c1e-220">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-220">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="f3c1e-221">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-221">SharePoint (4)</span></span>|
||<span data-ttu-id="f3c1e-222">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-222">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="f3c1e-223">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-223">SharePointCommentOperation (37)</span></span>|
||<span data-ttu-id="f3c1e-224">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-224">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="f3c1e-225">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-225">SharePointContentTypeOperation (55)</span></span>|
||<span data-ttu-id="f3c1e-226">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-226">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="f3c1e-227">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-227">SharePointFieldOperation (56)</span></span>|
||<span data-ttu-id="f3c1e-228">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-228">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="f3c1e-229">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-229">SharePointFileOperation (6)</span></span>|
||<span data-ttu-id="f3c1e-230">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-230">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="f3c1e-231">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-231">SharePointListOperation (36)</span></span>|
||<span data-ttu-id="f3c1e-232">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-232">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="f3c1e-233">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="f3c1e-233">SharePointSharingOperation (14)</span></span>|
||||
