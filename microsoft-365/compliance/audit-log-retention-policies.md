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
ms.openlocfilehash: b07965800c1258c03e3e7615fa88a0ed4e453c40
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845874"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="fc827-104">管理审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="fc827-104">Manage audit log retention policies</span></span>

<span data-ttu-id="fc827-105">可在安全与合规中心创建和管理审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="fc827-106">审核日志保留策略是 Microsoft 365 中新增的高级审核功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="fc827-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="fc827-107">通过审核日志保留策略，可指定组织中审核日志的保留时间。</span><span class="sxs-lookup"><span data-stu-id="fc827-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="fc827-108">可将审核日志保留长达一年时间。</span><span class="sxs-lookup"><span data-stu-id="fc827-108">You can retain audit logs for up to one year.</span></span> <span data-ttu-id="fc827-109">可以根据以下标准创建策略：</span><span class="sxs-lookup"><span data-stu-id="fc827-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="fc827-110">一个或多个 Microsoft 365 服务中的所有活动</span><span class="sxs-lookup"><span data-stu-id="fc827-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="fc827-111">所有用户或特定用户执行的特定活动（在特定服务中）</span><span class="sxs-lookup"><span data-stu-id="fc827-111">Specific activities (in a specific service) performed by all users or by specific users</span></span>

- <span data-ttu-id="fc827-112">优先级，用于指定当组织中有多个策略时优先使用哪个策略</span><span class="sxs-lookup"><span data-stu-id="fc827-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="fc827-113">默认审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="fc827-113">Default audit log retention policy</span></span>

<span data-ttu-id="fc827-114">Microsoft 365 中的高级审核功能为所有组织提供默认审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="fc827-115">此策略将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。</span><span class="sxs-lookup"><span data-stu-id="fc827-115">This policy retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="fc827-116">此默认策略将保留审核记录，其中包含**工作负载**属性（活动发生的服务）的 **AzureActiveDirectory**、**Exchange** 或 **SharePoint** 的值。</span><span class="sxs-lookup"><span data-stu-id="fc827-116">This default policy retains audit records that contain the value of **AzureActiveDirectory**, **Exchange**, or **SharePoint** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="fc827-117">无法修改默认策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-117">The default policy can't be modified.</span></span> <span data-ttu-id="fc827-118">请参阅本文的[详细信息](#more-information)部分，以获取默认策略中包含的每个工作负载的记录类型列表。</span><span class="sxs-lookup"><span data-stu-id="fc827-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="fc827-119">默认审核日志保留策略仅适用于分配了 Office 365 或 Microsoft 365 E5 许可证或具有 Microsoft 365 E5 合规版加载项许可证的用户执行的活动审核记录。</span><span class="sxs-lookup"><span data-stu-id="fc827-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance add-on license.</span></span> <span data-ttu-id="fc827-120">如果你的组织中有非 E5 用户，则其相应的审核记录将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="fc827-120">If you have non-E5 users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="fc827-121">在创建审核日志保留策略之前</span><span class="sxs-lookup"><span data-stu-id="fc827-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="fc827-122">必须在安全与合规中心为你分配了“组织配置”角色，这样才能创建或修改审核保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="fc827-123">在组织中，你最多可以拥有 50 个审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="fc827-124">若要将审核日志保留超过 90 天，必须为生成审核日志的用户分配 Office 365 E5 或 Microsoft 365 E5 许可证，或者该用户必须具有 Microsoft 365 E5 合规版或 E5 电子数据展示和审核加载项许可证。</span><span class="sxs-lookup"><span data-stu-id="fc827-124">To retain an audit log for longer than 90 days, the user who generated the audit log must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span>

- <span data-ttu-id="fc827-125">所有自定义审核日志保留策略（由组织创建）都优先于默认保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-125">All custom audit log retention policies (created by your organization) take priority over the default retention policy.</span></span> <span data-ttu-id="fc827-126">例如，如果为保留期短于一年的 Exchange 邮箱活动创建审核日志保留策略，则 Exchange 邮箱活动的审核记录将在自定义策略指定的较短期限内保留。</span><span class="sxs-lookup"><span data-stu-id="fc827-126">For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy-in-the-compliance-center"></a><span data-ttu-id="fc827-127">在合规中心创建审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="fc827-127">Create an audit log retention policy in the compliance center</span></span>

1. <span data-ttu-id="fc827-128">转到 [https://protection.office.com](https://protection.office.com)，然后使用在安全与合规中心分配了“组织配置”角色的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="fc827-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with user account that's assigned the Organization Configuration role in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="fc827-129">在安全与合规中心的左侧窗格中，单击“**搜索**” > “**审核日志搜索**”。</span><span class="sxs-lookup"><span data-stu-id="fc827-129">In the left pane of the Security & Compliance Center, click **Search** > **Audit log search**.</span></span>

    <span data-ttu-id="fc827-130">此时将显示“**审核日志搜索**”页面。</span><span class="sxs-lookup"><span data-stu-id="fc827-130">The **Audit log search** page is displayed.</span></span>

    ![“审核日志搜索”页面](../media/AuditLogRetentionPolicy1.png)

3. <span data-ttu-id="fc827-132">单击“**新建审核保留策略**”，然后在弹出页面上填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="fc827-132">Click **New audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![审核保留策略弹出页面](../media/AuditLogRetentionPolicy2.png)

   <span data-ttu-id="fc827-134">a.</span><span class="sxs-lookup"><span data-stu-id="fc827-134">a.</span></span> <span data-ttu-id="fc827-135">**名称**：审核日志保留策略的名称。</span><span class="sxs-lookup"><span data-stu-id="fc827-135">**Name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="fc827-136">此名称必须在你的组织中保持唯一。</span><span class="sxs-lookup"><span data-stu-id="fc827-136">This name must be unique in your organization.</span></span>

   <span data-ttu-id="fc827-137">b.</span><span class="sxs-lookup"><span data-stu-id="fc827-137">b.</span></span> <span data-ttu-id="fc827-138">**说明**：可选，但有助于提供有关策略的信息，例如记录类型或工作负载、策略中指定的用户以及期限。</span><span class="sxs-lookup"><span data-stu-id="fc827-138">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   <span data-ttu-id="fc827-139">c.</span><span class="sxs-lookup"><span data-stu-id="fc827-139">c.</span></span> <span data-ttu-id="fc827-140">**记录类型**：将为其应用策略的审核记录类型。</span><span class="sxs-lookup"><span data-stu-id="fc827-140">**Record types:** The audit record type the policy applies to.</span></span> <span data-ttu-id="fc827-141">如果选择多个记录类型，则不能选择活动，因为该策略将应用于所选记录类型的所有活动。</span><span class="sxs-lookup"><span data-stu-id="fc827-141">If you select more than one record type, you can't select activities because the policy will apply to all activities for the selected record types.</span></span> <span data-ttu-id="fc827-142">此外，如果将此属性留空，则必须在“**用户**”框中选择用户。</span><span class="sxs-lookup"><span data-stu-id="fc827-142">Also, if you leave this property blank, you must select a user in the **Users** box.</span></span>

   <span data-ttu-id="fc827-143">d.</span><span class="sxs-lookup"><span data-stu-id="fc827-143">d.</span></span> <span data-ttu-id="fc827-144">**活动**：使用此框从所选的记录类型中选择活动。</span><span class="sxs-lookup"><span data-stu-id="fc827-144">**Activities:** Use this box to choose activities from the record type that you selected.</span></span> <span data-ttu-id="fc827-145">你可以选择要为其应用策略的特定活动。</span><span class="sxs-lookup"><span data-stu-id="fc827-145">You can choose specific activities to apply the policy to.</span></span> <span data-ttu-id="fc827-146">如果未选择特定活动，则该策略将应用于所选记录类型的所有活动。</span><span class="sxs-lookup"><span data-stu-id="fc827-146">If you don't choose specific activities, then the policy will apply to all activities of the selected record type.</span></span>

   <span data-ttu-id="fc827-147">e.</span><span class="sxs-lookup"><span data-stu-id="fc827-147">e.</span></span> <span data-ttu-id="fc827-148">**用户**：选择一个或多个要为其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="fc827-148">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="fc827-149">如果将此框留空，则该策略将应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="fc827-149">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="fc827-150">如果将“**记录类型**”留空，则必须选择用户。</span><span class="sxs-lookup"><span data-stu-id="fc827-150">If you leave the **Record types** blank, then you must select a user.</span></span>

   <span data-ttu-id="fc827-151">f.</span><span class="sxs-lookup"><span data-stu-id="fc827-151">f.</span></span> <span data-ttu-id="fc827-152">**期限**：保留符合策略条件的审核日志的时间。</span><span class="sxs-lookup"><span data-stu-id="fc827-152">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   <span data-ttu-id="fc827-153">g.</span><span class="sxs-lookup"><span data-stu-id="fc827-153">g.</span></span> <span data-ttu-id="fc827-154">**优先级**：此值确定处理组织中的审核日志保留策略的顺序。</span><span class="sxs-lookup"><span data-stu-id="fc827-154">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="fc827-155">该值越大，表示优先级越高。</span><span class="sxs-lookup"><span data-stu-id="fc827-155">A higher value indicates a higher priority.</span></span> <span data-ttu-id="fc827-156">例如，优先级值为 **5** 的策略将优先于优先级值为 **0** 的策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-156">For example, a policy with a priority value of **5** would take priority over a policy with a priority value of **0**.</span></span> <span data-ttu-id="fc827-157">如前文所述，任何自定义审核日志保留策略都优先于组织的默认策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-157">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

4. <span data-ttu-id="fc827-158">单击“**保存**”以创建新的审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-158">Click **Save** to create the new audit log retention policy.</span></span>

<span data-ttu-id="fc827-159">目前，不会指示已成功创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-159">At this time, there's no indication that the retention policy was successfully created.</span></span> <span data-ttu-id="fc827-160">有关查看审核日志保留策略的属性，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="fc827-160">See the next section on viewing the properties of the audit log retention policies.</span></span>

## <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="fc827-161">在 PowerShell 中创建审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="fc827-161">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="fc827-162">还可以使用安全与合规中心 PowerShell 来创建审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-162">You can also use Security & Compliance Center PowerShell to create audit log retention policies.</span></span> 

1. <span data-ttu-id="fc827-163">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fc827-163">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="fc827-164">运行以下命令以创建审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-164">Run the following command to create an audit log retention policy.</span></span> 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```

    <span data-ttu-id="fc827-165">本示例使用以下设置创建名为“Microsoft Teams 审核策略”的审核日志保留策略：</span><span class="sxs-lookup"><span data-stu-id="fc827-165">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="fc827-166">策略说明。</span><span class="sxs-lookup"><span data-stu-id="fc827-166">A description of the policy.</span></span>

   - <span data-ttu-id="fc827-167">保留所有 Microsoft Teams 活动（由 *RecordType* 参数定义）。</span><span class="sxs-lookup"><span data-stu-id="fc827-167">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="fc827-168">将 Microsoft Teams 审核日志保留一年。</span><span class="sxs-lookup"><span data-stu-id="fc827-168">Retains Microsoft Teams audit logs for one year.</span></span>

   - <span data-ttu-id="fc827-169">优先级为 100。</span><span class="sxs-lookup"><span data-stu-id="fc827-169">A priority of 100.</span></span>

<span data-ttu-id="fc827-170">下面是创建审核日志保留策略的另一个示例。</span><span class="sxs-lookup"><span data-stu-id="fc827-170">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="fc827-171">此策略将用户 admin@contoso.onmicrosoft.com 的“用户登录”活动的审核日志保留六个月。</span><span class="sxs-lookup"><span data-stu-id="fc827-171">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="fc827-172">有关详细信息，请参阅 [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fc827-172">For more information, see [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

## <a name="view-audit-log-retention-policies"></a><span data-ttu-id="fc827-173">查看审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="fc827-173">View audit log retention policies</span></span>

<span data-ttu-id="fc827-174">目前，查看自定义审核日志保留策略的唯一方法是在安全与合规中心 PowerShell 中使用 **Get-UnifiedAuditRetentionPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc827-174">At this time, the only way to view custom audit log retention policies is to use the **Get-UnifiedAuditRetentionPolicy** cmdlet in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="fc827-175">下面是一个示例命令，用于显示组织中的审核日志保留策略的设置（在上一步中配置）。</span><span class="sxs-lookup"><span data-stu-id="fc827-175">Here's a sample command to display the settings (that you configured in the previous step) for the audit log retention policies in your organization.</span></span> <span data-ttu-id="fc827-176">此命令从最高优先级到最低优先级对策略进行排序。</span><span class="sxs-lookup"><span data-stu-id="fc827-176">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="fc827-177">目前，**Get-UnifiedAuditLogRetentionPolicy** cmdlet 不会返回组织的默认审核日志策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-177">At this time, the **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log policy for your organization.</span></span>

<span data-ttu-id="fc827-178">有关详细信息，请参阅 [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fc827-178">For more information, see [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy).</span></span>

## <a name="more-information"></a><span data-ttu-id="fc827-179">详细信息</span><span class="sxs-lookup"><span data-stu-id="fc827-179">More information</span></span>

- <span data-ttu-id="fc827-180">使用安全与合规中心 PowerShell 中的 **Set-UnifiedAuditLogRetentionPolicy** cmdlet 可修改现有审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-180">Use the **Set-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to modify an existing audit log retention policy.</span></span> <span data-ttu-id="fc827-181">有关详细信息，请参阅 [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fc827-181">For more information, see [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="fc827-182">使用安全与合规中心 PowerShell 中的 **Remove-UnifiedAuditLogRetentionPolicy** cmdlet 可删除审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-182">Use the **Remove-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="fc827-183">最长可能需要 30 分钟才能删除策略。</span><span class="sxs-lookup"><span data-stu-id="fc827-183">It might take up to 30 minutes for the policy to be removed.</span></span> <span data-ttu-id="fc827-184">有关详细信息，请参阅 [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fc827-184">For more information, see [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="fc827-185">如前文所述，Azure Active Directory，Exchange 和 SharePoint 中针对操作的审核记录将保留一年。</span><span class="sxs-lookup"><span data-stu-id="fc827-185">As previously stated, audit records for operations in Azure Active Directory, Exchange, and SharePoint are retained for one year.</span></span> <span data-ttu-id="fc827-186">下表列出了默认审核日志保留策略中包括的所有记录类型（针对每个服务）。</span><span class="sxs-lookup"><span data-stu-id="fc827-186">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="fc827-187">这意味着具有此记录类型的任何操作的审核日志都将保留一年，除非自定义审核日志保留策略对特定的记录类型、操作或用户具有优先权。</span><span class="sxs-lookup"><span data-stu-id="fc827-187">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="fc827-188">括号中显示了每种记录类型的枚举值（在审核记录中显示为 RecordType 属性值）。</span><span class="sxs-lookup"><span data-stu-id="fc827-188">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

   |<span data-ttu-id="fc827-189">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="fc827-189">AzureActiveDirectory</span></span> |<span data-ttu-id="fc827-190">Exchange</span><span class="sxs-lookup"><span data-stu-id="fc827-190">Exchange</span></span>  |<span data-ttu-id="fc827-191">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc827-191">SharePoint</span></span>|
   |:---------|:---------|:---------|
   |<span data-ttu-id="fc827-192">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="fc827-192">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="fc827-193">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="fc827-193">ExchangeAdmin (1)</span></span>|<span data-ttu-id="fc827-194">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="fc827-194">ComplianceDLPSharePoint (11)</span></span>|
   |<span data-ttu-id="fc827-195">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="fc827-195">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="fc827-196">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="fc827-196">ExchangeItem (2)</span></span>|<span data-ttu-id="fc827-197">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="fc827-197">ComplianceDLPSharePointClassification (33)</span></span>|
   |<span data-ttu-id="fc827-198">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="fc827-198">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="fc827-199">Campaign (62)</span><span class="sxs-lookup"><span data-stu-id="fc827-199">Campaign (62)</span></span>|<span data-ttu-id="fc827-200">Project (35)</span><span class="sxs-lookup"><span data-stu-id="fc827-200">Project (35)</span></span>|
   ||<span data-ttu-id="fc827-201">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="fc827-201">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="fc827-202">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="fc827-202">SharePoint (4)</span></span>|
   ||<span data-ttu-id="fc827-203">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="fc827-203">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="fc827-204">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="fc827-204">SharePointCommentOperation (37)</span></span>|
   ||<span data-ttu-id="fc827-205">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="fc827-205">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="fc827-206">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="fc827-206">SharePointContentTypeOperation (55)</span></span>|
   ||<span data-ttu-id="fc827-207">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="fc827-207">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="fc827-208">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="fc827-208">SharePointFieldOperation (56)</span></span>|
   ||<span data-ttu-id="fc827-209">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="fc827-209">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="fc827-210">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="fc827-210">SharePointFileOperation (6)</span></span>|
   ||<span data-ttu-id="fc827-211">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="fc827-211">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="fc827-212">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="fc827-212">SharePointListOperation (36)</span></span>|
   ||<span data-ttu-id="fc827-213">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="fc827-213">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="fc827-214">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="fc827-214">SharePointSharingOperation (14)</span></span>|
   ||||
