---
title: Microsoft 365 审核解决方案
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
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: 了解如何审核 Microsoft 365 组织中用户和管理员的活动。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 214ea43348a4a33e6ce1b754cbaf9be6a43b2c70
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314263"
---
# <a name="auditing-solutions-in-microsoft-365"></a><span data-ttu-id="4157a-103">Microsoft 365 中的审核解决方案</span><span class="sxs-lookup"><span data-stu-id="4157a-103">Auditing solutions in Microsoft 365</span></span>

<span data-ttu-id="4157a-104">Microsoft 365 审核解决方案提供集成解决方案，帮助组织有效响应安全事件、调查、内部调查和合规责任。</span><span class="sxs-lookup"><span data-stu-id="4157a-104">Microsoft 365 auditing solutions provide an integrated solution to help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations.</span></span> <span data-ttu-id="4157a-105">数千名 Microsoft 365 服务和解决方案中执行的用户和管理员操作被捕获、记录并保留在组织的统一审核日志中。</span><span class="sxs-lookup"><span data-stu-id="4157a-105">Thousands of user and admin operations performed in dozens of Microsoft 365 services and solutions are captured, recorded, and retained in your organization's unified audit log.</span></span> <span data-ttu-id="4157a-106">这些事件的审核记录通过安全运营、IT 管理员、预览体验计划团队以及合规与法律支持人员进行搜索。</span><span class="sxs-lookup"><span data-stu-id="4157a-106">Audit records for these events are searchable by security ops, IT admins, insider risk teams, and compliance and legal investigators in your organization.</span></span> <span data-ttu-id="4157a-107">此功能可跨 Microsoft 365 组织查看执行的活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-107">This capability provides visibility into the activities performed across your Microsoft 365 organization.</span></span>

## <a name="microsoft-365-auditing-solutions"></a><span data-ttu-id="4157a-108">Microsoft 365 审核解决方案</span><span class="sxs-lookup"><span data-stu-id="4157a-108">Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="4157a-109">Microsoft 365 提供两个审核解决方案：基本审核和高级审核。</span><span class="sxs-lookup"><span data-stu-id="4157a-109">Microsoft 365 provides two auditing solutions: Basic auditing and Advanced Audit.</span></span>

### <a name="basic-auditing"></a><span data-ttu-id="4157a-110">基本审核</span><span class="sxs-lookup"><span data-stu-id="4157a-110">Basic auditing</span></span>

<span data-ttu-id="4157a-111">基本审核让你能够记录和搜索经审核的活动，并支持你的文件、IT、合规性和法律调查。</span><span class="sxs-lookup"><span data-stu-id="4157a-111">Basic auditing provides with you with the ability to log and search for audited activities and power your forensic, IT, compliance, and legal investigations.</span></span>

- <span data-ttu-id="4157a-112">**默认情况下启用**。</span><span class="sxs-lookup"><span data-stu-id="4157a-112">**Enabled by default**.</span></span> <span data-ttu-id="4157a-113">默认为具有相应订阅的所有组织启用基本审核。</span><span class="sxs-lookup"><span data-stu-id="4157a-113">Basic auditing is turned on by default for all organizations with the appropriate subscription.</span></span> <span data-ttu-id="4157a-114">这意味着将捕获并搜索经审核的活动的记录。</span><span class="sxs-lookup"><span data-stu-id="4157a-114">That means records for audited activities will be captured and searchable.</span></span> <span data-ttu-id="4157a-115">只需分配访问审核日志搜索工具（及相应 cmdlet）所需的权限，并确保用户获得使用高级审核功能的相应许可证。</span><span class="sxs-lookup"><span data-stu-id="4157a-115">The only setup that required is to assign the necessary permissions to access the audit log search tool (and the corresponding cmdlet) and make sure that user's are assigned the right license for Advanced Audit features.</span></span>
- <span data-ttu-id="4157a-116">**数以千计的可搜索审计事件**。</span><span class="sxs-lookup"><span data-stu-id="4157a-116">**Thousands of searchable audit events**.</span></span> <span data-ttu-id="4157a-117">可搜索组织中大多数 Microsoft 365 服务中经审核的活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-117">You can search for a wide-range of audited activities that occur is most of the Microsoft 365 services in your organization.</span></span> <span data-ttu-id="4157a-118">有关可搜索的活动的部分列表，请参阅 [经审核活动](search-the-audit-log-in-security-and-compliance.md#audited-activities)。</span><span class="sxs-lookup"><span data-stu-id="4157a-118">For a partial list of the activities you can search for, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="4157a-119">有关支持经审核活动的服务和功能的列表，请参阅 [审核日志记录类型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。</span><span class="sxs-lookup"><span data-stu-id="4157a-119">For a list of the services and features that support audited activities, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span>
- <span data-ttu-id="4157a-120">**Microsoft 365 合规中心内审核**。</span><span class="sxs-lookup"><span data-stu-id="4157a-120">**Audit search tool in the Microsoft 365 compliance center**.</span></span> <span data-ttu-id="4157a-121">使用 Microsoft 365 合规中心中的审核日志搜索工具搜索审核记录。</span><span class="sxs-lookup"><span data-stu-id="4157a-121">Use the Audit log search tool in the Microsoft 365 compliance center to search for audit records.</span></span> <span data-ttu-id="4157a-122">可以搜索特定活动、特定用户执行的活动以及按日期范围发生的活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-122">You can search for specific activities, for activities performed by specific users, and activities that occurred with a date range.</span></span> <span data-ttu-id="4157a-123">下面是合规中心中审核搜索工具的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4157a-123">Here's a screenshot of the Audit search tool in the compliance center.</span></span>

   ![Microsoft 365 合规中心中的审核日志搜索工具](../media/AuditLogSearchToolMCC.png)

- <span data-ttu-id="4157a-125">**Search-UnifiedAuditLog cmdlet**.</span><span class="sxs-lookup"><span data-stu-id="4157a-125">**Search-UnifiedAuditLog cmdlet**.</span></span> <span data-ttu-id="4157a-126">您也可以在 Exchange Online PowerShell（搜索工具的基础 cmdlet）中使用 **Search-UnifiedAuditLog** cmdlet 来搜索审核事件或在脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="4157a-126">You can also use the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell (the underlying cmdlet for the search tool) to search for audit events or to use in a script.</span></span> <span data-ttu-id="4157a-127">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="4157a-127">For more information, see:</span></span>

  - [<span data-ttu-id="4157a-128">Search-UnifiedAuditLog</span><span class="sxs-lookup"><span data-stu-id="4157a-128">Search-UnifiedAuditLog</span></span>](/powershell/module/exchange/search-unifiedauditlog)
  - [<span data-ttu-id="4157a-129">使用 PowerShell 脚本搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="4157a-129">Use a PowerShell script to search the audit log</span></span>](audit-log-search-script.md)

- <span data-ttu-id="4157a-130">**将审核记录导出为 CSV 文件**。</span><span class="sxs-lookup"><span data-stu-id="4157a-130">**Export audit records to a CSV file**.</span></span> <span data-ttu-id="4157a-131">在合规中心运行审核日志搜索工具后，可以将搜索返回的审核记录导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="4157a-131">After run the Audit log search tool in the compliance center, you can export the audit records returned by the search to a CSV file.</span></span> <span data-ttu-id="4157a-132">这将允许对不同的审核记录属性使用 Microsoft Excel 排序和筛选。</span><span class="sxs-lookup"><span data-stu-id="4157a-132">This lets you use Microsoft Excel sort and filter on different audit record properties.</span></span> <span data-ttu-id="4157a-133">还可使用 Excel Power Query 转换功能将 AuditData JSON 对象中的每个属性拆分为其自己的列。</span><span class="sxs-lookup"><span data-stu-id="4157a-133">You can also use Excel Power Query transform functionality to split each property in the AuditData JSON object into its own column.</span></span> <span data-ttu-id="4157a-134">通过此操作可有效查看和比较不同事件的类似数据。</span><span class="sxs-lookup"><span data-stu-id="4157a-134">This lets you effectively view and compare similar data for different events.</span></span> <span data-ttu-id="4157a-135">有关详细信息，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。</span><span class="sxs-lookup"><span data-stu-id="4157a-135">For more information, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span>

- <span data-ttu-id="4157a-136">**通过Office 365管理活动API访问审核日志**。</span><span class="sxs-lookup"><span data-stu-id="4157a-136">**Access to audit logs via Office 365 Management Activity API**.</span></span> <span data-ttu-id="4157a-137">用于访问和检索审核记录的第三种方法就是使用 Office 365 管理活动 API。</span><span class="sxs-lookup"><span data-stu-id="4157a-137">A third method for accessing and retrieving audit records is to use the Office 365 Management Activity API.</span></span> <span data-ttu-id="4157a-138">这使组织可以审核数据超过默认 90 天的时间，并可以将其审核数据导入 SIEM 解决方案。</span><span class="sxs-lookup"><span data-stu-id="4157a-138">This lets organizations retain auditing data for longer periods than the default 90 days and lets them import their auditing data to a SIEM solution.</span></span> <span data-ttu-id="4157a-139">有关信息，请参阅 [Office 365 管理活动 API 参考](/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="4157a-139">For information, see [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

- <span data-ttu-id="4157a-140">**90 天审核日志保留期**。</span><span class="sxs-lookup"><span data-stu-id="4157a-140">**90-day audit log retention**.</span></span> <span data-ttu-id="4157a-141">当用户或管理员执行审核活动时，将生成审核记录并将其存储在组织的审核日志中。</span><span class="sxs-lookup"><span data-stu-id="4157a-141">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="4157a-142">在基本审核中，记录将保留 90 天，这意味着可以搜索过去三个月内发生的活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-142">In Basic auditing, records are retained for 90 days, which means you can search for activities that occurred within the past three months.</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="4157a-143">高级审核</span><span class="sxs-lookup"><span data-stu-id="4157a-143">Advanced Audit</span></span>

<span data-ttu-id="4157a-144">高级审核基于基本审核的功能，提供审核日志保留策略、审核记录较长的保留时间、高价值关键事件，以及 Office 365 管理活动 API 的更大带宽访问。</span><span class="sxs-lookup"><span data-stu-id="4157a-144">Advanced Audit builds on the capabilities of Basic auditing by providing audit log retention policies, longer retention of audit records, high-value crucial events, and higher bandwidth access to the Office 365 Management Activity API.</span></span>

- <span data-ttu-id="4157a-145">**审核日志保留策略**。</span><span class="sxs-lookup"><span data-stu-id="4157a-145">**Audit log retention policies**.</span></span> <span data-ttu-id="4157a-146">可创建自定义审核日志保留策略，将审核记录保留更长一年（对于需要附加设备许可证的用户，最多保留 10 年）。</span><span class="sxs-lookup"><span data-stu-id="4157a-146">You can create customized audit log retention policies to retain audit records for longer periods of time up to one year (and up to 10 years for users with required add-on license).</span></span> <span data-ttu-id="4157a-147">可创建一个策略，以保留基于被审核活动、经审核的特定活动或执行经审核活动的用户的服务的审核记录。</span><span class="sxs-lookup"><span data-stu-id="4157a-147">You can create a policy to retain audit records based the service where the audited activities occur, specific audited activities, or the user who performs an audited activity.</span></span>

- <span data-ttu-id="4157a-148">**审核记录被延长的保留**。</span><span class="sxs-lookup"><span data-stu-id="4157a-148">**Longer retention of audit records**.</span></span> <span data-ttu-id="4157a-149">默认情况下，Exchange、SharePoint 和 Azure Active Directory 审核记录将保留一年。</span><span class="sxs-lookup"><span data-stu-id="4157a-149">Exchange, SharePoint, and Azure Active Directory audit records are retained for one year by default.</span></span> <span data-ttu-id="4157a-150">默认情况下，所有其他活动的审核记录将保留 90 天，默认情况下，可以使用审核日志保留策略来配置较长的保留期。</span><span class="sxs-lookup"><span data-stu-id="4157a-150">Audit records for all other activities are retained for 90 days by default, by you can use audit log retention policies to configure longer retention periods.</span></span>

- <span data-ttu-id="4157a-151">**具有较高价值、关键事件**。</span><span class="sxs-lookup"><span data-stu-id="4157a-151">**High-value, crucial events**.</span></span> <span data-ttu-id="4157a-152">关键事件的审核记录提供有关事件（例如邮件项目访问时间、邮件项目答复和转发时间，以及用户在 Exchange Online 和 SharePoint Online 中何时和在 SharePoint Online 中搜索内容）的可见性，帮助组织进行邮件和合规性调查。</span><span class="sxs-lookup"><span data-stu-id="4157a-152">Audit records for crucial events can help your organization conduct forensic and compliance investigations by providing visibility to events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="4157a-153">这些关键事件可以帮助你调查可能的违规行为，并确定泄露的范围。</span><span class="sxs-lookup"><span data-stu-id="4157a-153">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>

- <span data-ttu-id="4157a-154">**Office 365管理活动API的更高带宽**。</span><span class="sxs-lookup"><span data-stu-id="4157a-154">**Higher bandwidth to the Office 365 Management Activity API**.</span></span> <span data-ttu-id="4157a-155">高级审核为组织提供了更多的带宽来通过 Office 365 管理活动 API 访问审核日志。</span><span class="sxs-lookup"><span data-stu-id="4157a-155">Advanced Audit provides organizations with more bandwidth to access auditing logs through the Office 365 Management Activity API.</span></span> <span data-ttu-id="4157a-156">虽然所有组织（具有基本审核或高级审核）最初都分配了每分钟 2，000 个请求的基准，但根据组织的席位数及其许可订阅，此限制将动态增加。</span><span class="sxs-lookup"><span data-stu-id="4157a-156">Although all organizations (that have Basic auditing or Advanced Audit) are initially allocated a baseline of 2,000 requests per minute, this limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="4157a-157">其结果为使用高级审核的组织获得与具有基本审核的组织大约两倍的带宽。</span><span class="sxs-lookup"><span data-stu-id="4157a-157">This results in organizations with Advanced Audit getting about twice the bandwidth as organizations with Basic auditing.</span></span>

<span data-ttu-id="4157a-158">有关高级审核功能的更多详细信息，请参阅 [365 高级审核](advanced-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="4157a-158">For more detailed information about Advanced Audit features, see [Advanced Audit in Microsoft 365](advanced-audit.md).</span></span>

## <a name="comparison-of-key-capabilities"></a><span data-ttu-id="4157a-159">比较关键功能</span><span class="sxs-lookup"><span data-stu-id="4157a-159">Comparison of key capabilities</span></span>

<span data-ttu-id="4157a-160">下表比较了基本审核和高级审核中提供的关键功能。</span><span class="sxs-lookup"><span data-stu-id="4157a-160">The following table compares the key capabilities available in Basic auditing and Advanced Audit.</span></span> <span data-ttu-id="4157a-161">高级审核包含所有基本审核功能。</span><span class="sxs-lookup"><span data-stu-id="4157a-161">All Basic auditing functionality is included in Advanced Audit.</span></span>

|<span data-ttu-id="4157a-162">功能</span><span class="sxs-lookup"><span data-stu-id="4157a-162">Capability</span></span>|<span data-ttu-id="4157a-163">基本审核</span><span class="sxs-lookup"><span data-stu-id="4157a-163">Basic auditing</span></span>|<span data-ttu-id="4157a-164">高级审核</span><span class="sxs-lookup"><span data-stu-id="4157a-164">Advanced Audit</span></span>|
|:------|:-------------|:-------------|
|<span data-ttu-id="4157a-165">默认情况下启用</span><span class="sxs-lookup"><span data-stu-id="4157a-165">Enabled by default</span></span>|![支持](../media/check-mark.png)|![支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-168">数千个可搜索的审核事件</span><span class="sxs-lookup"><span data-stu-id="4157a-168">Thousands of searchable audit events</span></span>|![支持](../media/check-mark.png)|![支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-171">Microsoft 365 合规中心中的审核搜索工具</span><span class="sxs-lookup"><span data-stu-id="4157a-171">Audit search tool in the Microsoft 365 compliance center</span></span>|![支持](../media/check-mark.png)|![支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-174">**Search-UnifiedAuditLog** cmdlet</span><span class="sxs-lookup"><span data-stu-id="4157a-174">**Search-UnifiedAuditLog** cmdlet</span></span>|![支持](../media/check-mark.png)|![支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-177">将审核记录导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="4157a-177">Export audit records to CSV file</span></span>|![支持](../media/check-mark.png)|![支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-180">通过Office 365管理活动API访问审核日志<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4157a-180">Access to audit logs via Office 365 Management Activity API <sup>1</sup></span></span>|![受支持](../media/check-mark.png)|<span data-ttu-id="4157a-182">![支持](../media/check-mark.png)</sup></span><span class="sxs-lookup"><span data-stu-id="4157a-182">![Supported](../media/check-mark.png)</sup></span></span>|
|<span data-ttu-id="4157a-183">90 天审核日志保留</span><span class="sxs-lookup"><span data-stu-id="4157a-183">90-day audit log retention</span></span>|![支持](../media/check-mark.png)|![支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-186">1 年审核日志保留期</span><span class="sxs-lookup"><span data-stu-id="4157a-186">1-year audit log retention</span></span>||![受支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-188">10 年审核日志保留期 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4157a-188">10-year audit log retention <sup>2</sup></span></span>||![受支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-190">审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="4157a-190">Audit log retention policies</span></span>||![受支持](../media/check-mark.png)|
|<span data-ttu-id="4157a-192">高价值的、关键事件</span><span class="sxs-lookup"><span data-stu-id="4157a-192">High-value, crucial events</span></span>||![受支持](../media/check-mark.png)|
||||
> [!NOTE]
> <span data-ttu-id="4157a-194"><sup>1</sup> 高级审核包括更高的 Office 365 管理活动 API 访问带宽，可更快地访问审核数据。</span><span class="sxs-lookup"><span data-stu-id="4157a-194"><sup>1</sup> Advanced Audit includes higher bandwidth access to the Office 365 Management Activity API, which provides faster access to audit data.</span></span><br/><span data-ttu-id="4157a-195"><sup>2</sup> 除了高级审核所需的许可（下一节中介绍）外，必须为用户分配 10 年审核日志保留期的许可证，才能保留其审核记录 10 年。</span><span class="sxs-lookup"><span data-stu-id="4157a-195"><sup>2</sup> In addition to the required licensing for Advanced Audit (described in the next section), a user must be assigned a 10-Year Audit Log Retention add on license to retain their audit records for 10 years.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4157a-196">许可要求</span><span class="sxs-lookup"><span data-stu-id="4157a-196">Licensing requirements</span></span>

<span data-ttu-id="4157a-197">以下各节确定基本审核和高级审核的许可要求。</span><span class="sxs-lookup"><span data-stu-id="4157a-197">The following sections identify the licensing requirements for Basic auditing and Advanced Audit.</span></span> <span data-ttu-id="4157a-198">高级审核中包括基本审核功能。</span><span class="sxs-lookup"><span data-stu-id="4157a-198">Basic auditing functionality is included with Advanced Auditing.</span></span>

### <a name="basic-auditing"></a><span data-ttu-id="4157a-199">基本审核</span><span class="sxs-lookup"><span data-stu-id="4157a-199">Basic auditing</span></span>

- <span data-ttu-id="4157a-200">Microsoft 365 企业版 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-200">Microsoft 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="4157a-201">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="4157a-201">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="4157a-202">Microsoft 365 教育版 A3 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-202">Microsoft 365 Education A3 subscription</span></span>
- <span data-ttu-id="4157a-203">Microsoft 365 政府版 G3 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-203">Microsoft 365 Government G3 subscription</span></span>
- <span data-ttu-id="4157a-204">Microsoft 365 政府版 G1 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-204">Microsoft 365 Government G1 subscription</span></span>
- <span data-ttu-id="4157a-205">Office 365 企业版 E3 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-205">Office 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="4157a-206">Office 365 企业版 E1 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-206">Office 365 Enterprise E1 subscription</span></span>
- <span data-ttu-id="4157a-207">Office 365 教育版 A1 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-207">Office 365 Education A1 subscription</span></span>
- <span data-ttu-id="4157a-208">Office 365 教育版 A3 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-208">Office 365 Education A3 subscription</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="4157a-209">高级审核</span><span class="sxs-lookup"><span data-stu-id="4157a-209">Advanced Audit</span></span>

- <span data-ttu-id="4157a-210">Microsoft 365 企业版 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-210">Microsoft 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="4157a-211">Microsoft 365 企业版 E3 订阅 + Microsoft 365 E5 合规性附加内容</span><span class="sxs-lookup"><span data-stu-id="4157a-211">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="4157a-212">Microsoft 365 企业版 E3 订阅 + Microsoft 365 E5 电子数据展示和审核附加项</span><span class="sxs-lookup"><span data-stu-id="4157a-212">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="4157a-213">Microsoft 365 教育版 A5 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-213">Microsoft 365 Education A5 subscription</span></span>
- <span data-ttu-id="4157a-214">Microsoft 365 教育版 A3 订阅 + Microsoft 365 A5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="4157a-214">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="4157a-215">Microsoft 365 教育版 A3 订阅 + Microsoft 365 A5 电子数据展示和审核加载项</span><span class="sxs-lookup"><span data-stu-id="4157a-215">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="4157a-216">Microsoft 365 政府版 G5 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-216">Microsoft 365 Government G5 subscription</span></span>
- <span data-ttu-id="4157a-217">Microsoft 365 政府版 G5 订阅 + Microsoft 365 G5 合规性附加内容</span><span class="sxs-lookup"><span data-stu-id="4157a-217">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="4157a-218">Microsoft 365 政府版 G5 订阅 + Microsoft 365 G5 电子数据展示和审核加载项</span><span class="sxs-lookup"><span data-stu-id="4157a-218">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="4157a-219">Office 365 企业版 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-219">Office 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="4157a-220">Office 365 教育版 A5 订阅</span><span class="sxs-lookup"><span data-stu-id="4157a-220">Office 365 Education A5 subscription</span></span>
- <span data-ttu-id="4157a-221">Office 365 企业版 E3 订阅和 Office 365 高级合规版附加设备（不再适用于新订阅）</span><span class="sxs-lookup"><span data-stu-id="4157a-221">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions)</span></span>

## <a name="set-up-microsoft-365-auditing-solutions"></a><span data-ttu-id="4157a-222">设置 Microsoft 365 审核解决方案</span><span class="sxs-lookup"><span data-stu-id="4157a-222">Set up Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="4157a-223">若要开始在 Microsoft 365 使用审核解决方案，请参阅以下设置指南。</span><span class="sxs-lookup"><span data-stu-id="4157a-223">To get started using the auditing solutions in Microsoft 365, see the following setup guidance.</span></span>

### <a name="set-up-basic-auditing"></a><span data-ttu-id="4157a-224">设置基本审核</span><span class="sxs-lookup"><span data-stu-id="4157a-224">Set up Basic auditing</span></span>

<span data-ttu-id="4157a-225">第一步是设置基本审核，然后开始运行审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4157a-225">The first step is to set up Basic auditing and then start running audit log searches.</span></span>

![用于设置基本审核的工作流](../media/BasicAuditingWorkflow.png)

1. <span data-ttu-id="4157a-227">验证你的组织具有支持基本审核的订阅，以及支持高级审核的订阅（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="4157a-227">Verify that your organization has a subscription that supports Basic auditing and if applicable, a subscription that supports Advanced Audit.</span></span>

2. <span data-ttu-id="4157a-228">在 Exchange Online 中向组织内部人员分配权限，这些人员将使用 Microsoft 365 合规中心或 **Search-UnifiedAuditLog** cmdlet 中的审核日志搜索工具。</span><span class="sxs-lookup"><span data-stu-id="4157a-228">Assign permissions in Exchange Online to people in your organization who will use the audit log search tool in the Microsoft 365 compliance center or the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="4157a-229">具体而言，向用户分配 Exchange Online 中的"仅查看审核日志"或"审核日志"角色。</span><span class="sxs-lookup"><span data-stu-id="4157a-229">Specifically, uses must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online.</span></span>

3. <span data-ttu-id="4157a-230">搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="4157a-230">Search the audit log.</span></span> <span data-ttu-id="4157a-231">完成步骤 1 和步骤 2 后，你组织中的用户可以使用审核日志搜索工具（或相应的 cmdlet）搜索经审核的活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-231">After completing step 1 and step 2, users in your organization can use the audit log search tool (or corresponding cmdlet) to search for audited activities.</span></span>

### <a name="set-up-advanced-audit"></a><span data-ttu-id="4157a-232">设置高级审核</span><span class="sxs-lookup"><span data-stu-id="4157a-232">Set up Advanced Audit</span></span>

<span data-ttu-id="4157a-233">如果你的组织具有支持高级审核的订阅，请执行以下步骤来设置和使用高级审核中的其他功能。</span><span class="sxs-lookup"><span data-stu-id="4157a-233">If your organization has a subscription that supports Advanced Audit, perform the follow steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![设置高级审核的工作流](../media/AdvancedAuditWorkflow.png)

1. <span data-ttu-id="4157a-235">为用户设置高级审核。</span><span class="sxs-lookup"><span data-stu-id="4157a-235">Set up Advanced Audit for users.</span></span> <span data-ttu-id="4157a-236">此步骤包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="4157a-236">This step consists of the following tasks:</span></span>

   - <span data-ttu-id="4157a-237">验证用户分配了用于高级审核的适当许可证或附加设备许可证。</span><span class="sxs-lookup"><span data-stu-id="4157a-237">Verifying that users are assigned the appropriate license or add-on license for Advanced Audit.</span></span>
  
   - <span data-ttu-id="4157a-238">必须为这些用户启用"高级审核应用/服务"计划。</span><span class="sxs-lookup"><span data-stu-id="4157a-238">Turning on the Advanced Audit app/service plan must be for those users.</span></span>
  
   - <span data-ttu-id="4157a-239">对关键事件启用审核，然后为这些用户启用高级审核应用/服务计划。</span><span class="sxs-lookup"><span data-stu-id="4157a-239">Enabling the auditing of crucial events and then turning on the Advanced Auditing app/service plan for those users.</span></span>

2. <span data-ttu-id="4157a-240">启用关键事件，以便用户在 Exchange Online 和 SharePoint Online 中执行搜索时记录。</span><span class="sxs-lookup"><span data-stu-id="4157a-240">Enable crucial events to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span>

3. <span data-ttu-id="4157a-241">设置审核日志保留策略。</span><span class="sxs-lookup"><span data-stu-id="4157a-241">Set up audit log retention policies.</span></span> <span data-ttu-id="4157a-242">除了将 Exchange、SharePoint 和 Azure AD 审核记录保留一年的默认策略外，可以创建其他审核日志保留策略以满足组织安全操作、IT 和合规团队的要求。</span><span class="sxs-lookup"><span data-stu-id="4157a-242">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span>

4. <span data-ttu-id="4157a-243">执行调查时，搜索关键事件和其他活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-243">Search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="4157a-244">完成步骤 1 和步骤 2 后，可在审核日志中搜索关键事件和调查已泄露帐户以及其他类型的安全或合规性调查期间的其他活动。</span><span class="sxs-lookup"><span data-stu-id="4157a-244">After completing step 1 and step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span>

## <a name="training"></a><span data-ttu-id="4157a-245">培训</span><span class="sxs-lookup"><span data-stu-id="4157a-245">Training</span></span>

<span data-ttu-id="4157a-246">在基本审核和高级审核中培训安全运营团队、IT 管理员和合规部团队，可帮助组织更快开始使用审核来帮助完成调查。</span><span class="sxs-lookup"><span data-stu-id="4157a-246">Training your security operations team, IT administrators, and compliance investigators team in Basic auditing and Advanced Audit can help your organization get started more quickly using auditing to help with your investigations.</span></span> <span data-ttu-id="4157a-247">Microsoft 365 提供了以下资源来帮助你组织中这些用户开始进行审核： [描述Microsoft 365中的审核功能](/learn/modules/describe-audit-capabilities-microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="4157a-247">Microsoft 365 provides the following resource to help these users in your organization getting started with auditing: [Describe the audit capabilities in Microsoft 365](/learn/modules/describe-audit-capabilities-microsoft-365).</span></span>
