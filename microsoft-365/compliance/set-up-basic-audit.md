---
title: 在"管理"中设置Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文介绍如何设置基本审核，以便您可以开始搜索组织中用户和管理员执行的审核活动。
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564819"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a><span data-ttu-id="5a7b7-103">在"管理"中设置Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a7b7-103">Set up Basic Audit in Microsoft 365</span></span>

<span data-ttu-id="5a7b7-104">使用"Microsoft 365基本审核"，可以搜索用户和管理员在不同 Microsoft 365 服务中执行的活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-104">Basic Audit in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="5a7b7-105">由于默认情况下为大多数 Microsoft 365 Office 365 组织启用了基本审核，因此只有一些操作需要执行，您和您的组织中的其他人才能搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-105">Because Basic Audit is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="5a7b7-106">本文讨论设置基本审核所需的以下步骤。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-106">This article discusses the following steps necessary to set up Basic Audit.</span></span>

![设置基本审核的步骤](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="5a7b7-108">这些步骤包括确保生成和保留审核记录所需的正确组织订阅和用户许可，以及向安全操作、IT、合规性和法律团队的团队成员分配权限，以便搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="5a7b7-109">有关详细信息，请参阅 Microsoft 365 中的基本[审核](auditing-solutions-overview.md#basic-audit)。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-109">For more information, see [Basic Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="5a7b7-110">步骤 1：验证组织订阅和用户许可</span><span class="sxs-lookup"><span data-stu-id="5a7b7-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="5a7b7-111">基本审核许可需要适当的组织订阅，该订阅提供对 审核日志 搜索工具和每用户许可的访问权限，这是记录并保留审核记录所需的。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-111">Licensing for Basic Audit requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="5a7b7-112">当用户或管理员执行审核活动时，将生成审核记录并将其存储在组织的审核日志中。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="5a7b7-113">在基本审核中，审核记录在审核记录中保留审核日志搜索 90 天。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-113">In Basic Audit, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="5a7b7-114">有关基本审核的订阅和许可要求的列表，请参阅审核[Microsoft 365。](auditing-solutions-overview.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="5a7b7-114">For a list of subscription and licensing requirements for Basic Audit, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="5a7b7-115">步骤 2：分配搜索搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="5a7b7-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="5a7b7-116">必须为管理员和调查团队的成员分配View-Only审核日志或审核日志Exchange Online搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="5a7b7-117">默认情况下，在 Exchange 管理中心中的“**权限**”页上将这些角色分配给“合规性管理”和“组织管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="5a7b7-118">Office 365 和 Microsoft 365 中的全局管理员将自动添加为组织中组织管理角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="5a7b7-119">若要让用户能够使用最低权限级别搜索审核日志，可以在 Exchange Online 中创建自定义角色组，添加“仅供查看审核日志”或“审核日志”角色，然后将用户添加为新角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="5a7b7-120">有关详细信息，请参阅[在 Exchange Online 中管理角色组](/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="5a7b7-121">以下屏幕截图显示了分配给管理中心内"组织管理"角色组的两个Exchange角色。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![审核分配给角色组中角色Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="5a7b7-123">步骤 3：搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="5a7b7-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="5a7b7-124">现在，你已准备好在合规性审核日志搜索Microsoft 365搜索。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="5a7b7-125">转到 <https://compliance.microsoft.com> ，然后使用已分配有相应审核权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="5a7b7-126">在合规性中心的左侧导航窗格中，Microsoft 365 **全部显示**"，然后单击"审核 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a7b7-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="5a7b7-127">在" **审核** "页上，使用"搜索"选项卡上的以下条件 **配置搜索** 。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![用于搜索的配置审核日志设置](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="5a7b7-129">**日期和时间范围**。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-129">**Date and time range**.</span></span> <span data-ttu-id="5a7b7-130">选择日期和时间范围，以显示在这段时间内发生的事件。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="5a7b7-131">日期和时间以本地时间显示。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-131">The date and time are presented in local time.</span></span> <span data-ttu-id="5a7b7-132">默认情况下选择最近七天。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="5a7b7-133">**活动**。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-133">**Activities**.</span></span> <span data-ttu-id="5a7b7-134">选择要搜索的活动。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-134">Select the activities to search for.</span></span> <span data-ttu-id="5a7b7-135">使用搜索框搜索要添加到列表中的活动。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="5a7b7-136">有关审核的活动的部分列表，请参阅 [审核的活动](search-the-audit-log-in-security-and-compliance.md#audited-activities)。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="5a7b7-137">保留此框为空可返回所有审核的活动的条目。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="5a7b7-138">**用户**。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-138">**Users**.</span></span>  <span data-ttu-id="5a7b7-139">单击此框并开始键入要显示其搜索结果的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="5a7b7-140">在此审核日志中选择的用户执行的选定活动的条目将显示在结果列表中。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="5a7b7-141">将此框留空以返回组织中所有用户（和服务帐户）的条目。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="5a7b7-142">**文件、文件夹或网站**。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-142">**File, folder, or site**.</span></span> <span data-ttu-id="5a7b7-143">键入部分或所有文件或文件夹名称，以搜索与包含指定关键字的文件夹文件相关的活动。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="5a7b7-144">你还可以指定文件或文件夹的 URL。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="5a7b7-145">如果使用文件或文件夹的 URL，请确保键入完整 URL 路径，或者键入 URL 的一部分时，请勿包含任何特殊字符或空格。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="5a7b7-146">将此框留空以返回组织中所有文件和文件夹的条目。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="5a7b7-147">单击 **"** 搜索"运行搜索。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="5a7b7-148">将显示一个新页面，审核日志搜索正在运行的时间。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="5a7b7-149">搜索完成后，审核记录将显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="5a7b7-150">单击记录以显示具有详细属性的飞出页。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="5a7b7-151">有关更详细的说明，请参阅在审核日志 [搜索策略](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7b7-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
