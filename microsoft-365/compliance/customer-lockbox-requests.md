---
title: 客户密码箱请求
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解客户密码箱请求，该请求允许你控制 Microsoft 支持工程师在遇到问题时如何访问你的数据。
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922706"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="eba89-103">客户密码箱Office 365</span><span class="sxs-lookup"><span data-stu-id="eba89-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="eba89-104">本文提供客户密码箱的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="eba89-104">This article provides deployment and configuration guidance for Customer Lockbox.</span></span> <span data-ttu-id="eba89-105">客户密码箱支持访问 Exchange Online、SharePoint Online 和 OneDrive for Business 中数据的请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="eba89-106">若要建议支持其他服务，请在[UserVoice Office 365提交请求](https://office365.uservoice.com/)。</span><span class="sxs-lookup"><span data-stu-id="eba89-106">To recommend support for other services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="eba89-107">若要了解从 2020 年 4 月 1 日起允许用户从 Microsoft 365 合规性产品/服务（包括此产品/服务）中获益的选项，请参阅安全与合规的[Microsoft 365 &](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)许可指南。</span><span class="sxs-lookup"><span data-stu-id="eba89-107">To see the options for licensing your users to benefit from Microsoft 365 compliance offerings, including this one, as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="eba89-108">客户密码箱可确保未经您的明确批准，Microsoft 无法访问您的内容以执行服务操作。</span><span class="sxs-lookup"><span data-stu-id="eba89-108">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="eba89-109">客户密码箱将你带入访问内容的请求审批工作流程。</span><span class="sxs-lookup"><span data-stu-id="eba89-109">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="eba89-110">有时，Microsoft 工程师偶尔会帮助排查和解决客户报告的问题。</span><span class="sxs-lookup"><span data-stu-id="eba89-110">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="eba89-111">通常，问题会通过 Microsoft 为其服务准备的大量遥测和调试工具来解决。</span><span class="sxs-lookup"><span data-stu-id="eba89-111">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="eba89-112">但某些情况下需要 Microsoft 的工程师访问客户内容以确定根本原因并修复问题。</span><span class="sxs-lookup"><span data-stu-id="eba89-112">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="eba89-113">客户密码箱要求工程师向客户申请访问，作为审批工作流程的最后一步。</span><span class="sxs-lookup"><span data-stu-id="eba89-113">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="eba89-114">这使组织可以选择批准或拒绝这些请求，并为客户提供直接访问控制。</span><span class="sxs-lookup"><span data-stu-id="eba89-114">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="eba89-115">客户密码箱概述视频</span><span class="sxs-lookup"><span data-stu-id="eba89-115">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="eba89-116">客户密码箱工作流程</span><span class="sxs-lookup"><span data-stu-id="eba89-116">Customer Lockbox workflow</span></span>

<span data-ttu-id="eba89-117">以下步骤概述了 Microsoft 工程师发起客户密码箱请求时的典型工作流程:</span><span class="sxs-lookup"><span data-stu-id="eba89-117">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="eba89-118">组织中的某人在其 Microsoft 365 邮箱中遇到了问题。</span><span class="sxs-lookup"><span data-stu-id="eba89-118">Someone at an organization experiences an issue with their Microsoft 365 mailbox.</span></span>

2. <span data-ttu-id="eba89-119">当用户排除了问题但无法解决后，就会向 Microsoft 支持部门打开支持请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-119">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="eba89-120">Microsoft 支持工程师审查了该服务请求，并确定需要访问组织租户以修复 Exchange Online 中的问题。</span><span class="sxs-lookup"><span data-stu-id="eba89-120">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="eba89-121">Microsoft 支持工程师登录客户密码箱请求工具，提出数据访问请求，其中包括组织的租户名称、服务请求号和工程师需要访问数据的预计时间。</span><span class="sxs-lookup"><span data-stu-id="eba89-121">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="eba89-122">在 Microsoft 支持部门经理批准该请求后，客户密码箱会向组织中指定的批准者发送一封关于 Microsoft 的未决访问请求电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="eba89-122">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![客户密码箱电子邮件通知示例](../media/CustomerLockbox1.png)

   <span data-ttu-id="eba89-124">在管理中心中分配有客户密码箱[访问](/office365/admin/add-users/about-admin-roles)审批者管理员Microsoft 365可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-124">Anyone who is assigned the [Customer Lockbox access approver](/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="eba89-125">审批者登录管理Microsoft 365审批请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-125">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="eba89-126">此步骤会触发创建审核记录，可通过搜索审核日志获得该审核记录。</span><span class="sxs-lookup"><span data-stu-id="eba89-126">This step triggers the creation of an audit record available by searching the audit log.</span></span> <span data-ttu-id="eba89-127">有关详细信息，请参阅审核 [客户密码箱请求](#auditing-customer-lockbox-requests)。</span><span class="sxs-lookup"><span data-stu-id="eba89-127">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="eba89-128">如果客户拒绝请求或者未在 12 小时内批准请求，该请求将过期，并且不会向 Microsoft 工程师授予任何访问权限。</span><span class="sxs-lookup"><span data-stu-id="eba89-128">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="eba89-129">Microsoft 在客户密码箱电子邮件通知中不包含任何需要你登录到密码Office 365。</span><span class="sxs-lookup"><span data-stu-id="eba89-129">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="eba89-130">来自组织的审批者批准该请求后，Microsoft 工程师将收到批准消息、在 Exchange Online 中登录到租户，并修复客户的问题。</span><span class="sxs-lookup"><span data-stu-id="eba89-130">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="eba89-131">Microsoft 工程师对修复这个问题有要求期限，之后访问将自动撤销。</span><span class="sxs-lookup"><span data-stu-id="eba89-131">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="eba89-132">Microsoft 工程师执行的所有操作都会记录在审计日志中。</span><span class="sxs-lookup"><span data-stu-id="eba89-132">All actions performed by a Microsoft engineer are logged in the audit log.</span></span> <span data-ttu-id="eba89-133">你可以搜索和查看这些审核记录。</span><span class="sxs-lookup"><span data-stu-id="eba89-133">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="eba89-134">打开或关闭客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="eba89-134">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="eba89-135">你可以在 Microsoft 365 管理中心中启用客户密码箱控件。</span><span class="sxs-lookup"><span data-stu-id="eba89-135">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="eba89-136">当你打开客户密码箱时，Microsoft 必须在访问你的任何租户内容之前获得组织的批准。</span><span class="sxs-lookup"><span data-stu-id="eba89-136">When you turn on Customer Lockbox, Microsoft must obtain your organization's approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="eba89-137">使用分配了全局管理员或客户密码箱访问审批者角色的工作或学校帐户，转到 [https://admin.microsoft.com](https://admin.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="eba89-137">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="eba89-138">Choose **设置 > Org 设置**.</span><span class="sxs-lookup"><span data-stu-id="eba89-138">Choose **Settings > Org Settings**.</span></span>

3. <span data-ttu-id="eba89-139">选择 **"&** 客户密码箱编辑"，然后将开关移到"开"或"关"以  >    >  打开或关闭功能。  </span><span class="sxs-lookup"><span data-stu-id="eba89-139">Select **Security & Privacy** > **Customer Lockbox** > **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="eba89-141">批准或拒绝客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="eba89-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="eba89-142">使用分配了全局管理员或客户密码箱访问审批者角色的工作或学校帐户，转到 [https://admin.microsoft.com](https://admin.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="eba89-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="eba89-143">Choose **Support > Customer Lockbox Requests**.</span><span class="sxs-lookup"><span data-stu-id="eba89-143">Choose **Support > Customer Lockbox Requests**.</span></span>

    ![单击"支持"，然后单击"客户密码箱请求"](../media/CustomerLockbox5.png)

    <span data-ttu-id="eba89-145">将显示客户密码箱请求列表。</span><span class="sxs-lookup"><span data-stu-id="eba89-145">A list of Customer Lockbox requests displays.</span></span>

    ![客户密码箱请求列表](../media/CustomerLockbox6.png)

3. <span data-ttu-id="eba89-147">选择客户密码箱请求，然后选择 **批准或拒绝。** </span><span class="sxs-lookup"><span data-stu-id="eba89-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny**.</span></span>

    ![批准或拒绝客户密码箱请求](../media/CustomerLockbox7.png)

    <span data-ttu-id="eba89-149">将显示有关客户密码箱请求审批的确认消息。</span><span class="sxs-lookup"><span data-stu-id="eba89-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![批准或拒绝客户密码箱请求](../media/CustomerLockbox8.png)

> [!NOTE]
> <span data-ttu-id="eba89-151">使用 Set-AccessToCustomerDataRequest cmdlet 批准、拒绝或取消 Microsoft 365 客户密码箱请求，以控制 Microsoft 支持工程师对你数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eba89-151">Use the Set-AccessToCustomerDataRequest cmdlet to approve, deny, or cancel Microsoft 365 customer lockbox requests that control access to your data by Microsoft support engineers.</span></span> <span data-ttu-id="eba89-152">有关详细信息，请参阅 [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest)。</span><span class="sxs-lookup"><span data-stu-id="eba89-152">For more information, see [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest).</span></span>


## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="eba89-153">审核客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="eba89-153">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="eba89-154">与客户密码箱请求对应的审核记录将记录在审核日志。</span><span class="sxs-lookup"><span data-stu-id="eba89-154">Audit records that correspond to the Customer Lockbox requests are logged in the audit log.</span></span> <span data-ttu-id="eba89-155">可以使用安全与合规中心审核日志 [搜索工具](search-the-audit-log-in-security-and-compliance.md) 访问&日志。</span><span class="sxs-lookup"><span data-stu-id="eba89-155">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="eba89-156">与接受或拒绝客户密码箱请求相关的操作以及 Microsoft 工程师 (访问请求获得批准时执行的操作) 也会记录在审核日志。</span><span class="sxs-lookup"><span data-stu-id="eba89-156">Actions related to accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the audit log.</span></span> <span data-ttu-id="eba89-157">你可以搜索和查看这些审核记录。</span><span class="sxs-lookup"><span data-stu-id="eba89-157">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="eba89-158">搜索审核日志客户密码箱请求相关的活动</span><span class="sxs-lookup"><span data-stu-id="eba89-158">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="eba89-159">在使用审核日志跟踪客户密码箱请求之前，需要执行一些步骤来设置审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="eba89-159">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to set up audit logging.</span></span> <span data-ttu-id="eba89-160">有关详细信息，请参阅在安全[与审核日志搜索&搜索。](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="eba89-160">For more information, see [Search the audit log in the Security & Compliance Center](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="eba89-161">完成设置后，使用以下步骤创建一个审核日志搜索查询，以返回与客户密码箱相关的审核记录：</span><span class="sxs-lookup"><span data-stu-id="eba89-161">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="eba89-162">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="eba89-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="eba89-163">使用工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="eba89-163">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="eba89-164">在安全与合规中心的&窗格中，选择"搜索&**调查**  >  **审核日志搜索"。**</span><span class="sxs-lookup"><span data-stu-id="eba89-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="eba89-165">将显示 **"审核日志搜索** "页。</span><span class="sxs-lookup"><span data-stu-id="eba89-165">The **Audit log search** page displays.</span></span>

    ![审核日志搜索页](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="eba89-167">配置以下搜索条件：</span><span class="sxs-lookup"><span data-stu-id="eba89-167">Configure the following search criteria:</span></span>

    1. <span data-ttu-id="eba89-168">**Activities** - 将此字段留空，以便搜索返回所有活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="eba89-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="eba89-169">这是返回与客户密码箱请求和 Microsoft 工程师执行的相应活动相关的任何审核记录所必需的。</span><span class="sxs-lookup"><span data-stu-id="eba89-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    1. <span data-ttu-id="eba89-170">**开始日期** 和 **结束日期** - 选择日期和时间范围以显示该时段内发生的事件。</span><span class="sxs-lookup"><span data-stu-id="eba89-170">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    1. <span data-ttu-id="eba89-171">**用户** - 将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="eba89-171">**Users** - Leave this field blank.</span></span>

    1. <span data-ttu-id="eba89-172">**文件、文件夹或网站** - 将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="eba89-172">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="eba89-173">单击“**搜索**”以使用搜索条件运行搜索。</span><span class="sxs-lookup"><span data-stu-id="eba89-173">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="eba89-174">将加载搜索结果，片刻后，它们将显示在"审核日志搜索"页上的"结果 **"** 下。</span><span class="sxs-lookup"><span data-stu-id="eba89-174">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="eba89-175">单击 **搜索结果** 页上的"筛选结果"，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="eba89-175">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="eba89-176">若要显示与组织中审批或拒绝客户密码箱请求的审批者相关的审核记录：在"活动"列下的框中，键入 **Set-AccessToCustomerDataRequest**。</span><span class="sxs-lookup"><span data-stu-id="eba89-176">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="eba89-177">若要显示与 Microsoft 工程师为响应已批准的客户密码箱请求而执行的操作相关的审核记录：在"用户"列下的框中，键入 **"Microsoft 操作员"。**</span><span class="sxs-lookup"><span data-stu-id="eba89-177">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="eba89-178">" **活动** "列显示工程师执行的操作。</span><span class="sxs-lookup"><span data-stu-id="eba89-178">The **Activity** column displays the action performed by the engineer.</span></span>

      ![筛选"Microsoft 操作员"以显示审核记录](../media/CustomerLockbox10.png)

7. <span data-ttu-id="eba89-180">在结果列表中，单击审核记录以显示该记录。</span><span class="sxs-lookup"><span data-stu-id="eba89-180">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="eba89-181">客户密码箱访问请求的审核记录</span><span class="sxs-lookup"><span data-stu-id="eba89-181">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="eba89-182">当组织内部人员批准或拒绝客户密码箱请求时，审核记录将记录在审核日志。</span><span class="sxs-lookup"><span data-stu-id="eba89-182">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the audit log.</span></span> <span data-ttu-id="eba89-183">此记录包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="eba89-183">This record contains the following information.</span></span>

| <span data-ttu-id="eba89-184">审核记录属性</span><span class="sxs-lookup"><span data-stu-id="eba89-184">Audit record property</span></span>| <span data-ttu-id="eba89-185">描述</span><span class="sxs-lookup"><span data-stu-id="eba89-185">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="eba89-186">日期</span><span class="sxs-lookup"><span data-stu-id="eba89-186">Date</span></span>       | <span data-ttu-id="eba89-187">批准或拒绝客户密码箱请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="eba89-187">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="eba89-188">IP 地址</span><span class="sxs-lookup"><span data-stu-id="eba89-188">IP address</span></span> | <span data-ttu-id="eba89-189">审批者用于批准或拒绝请求的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eba89-189">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="eba89-190">用户</span><span class="sxs-lookup"><span data-stu-id="eba89-190">User</span></span>       | <span data-ttu-id="eba89-191">客户帐户BOXServiceAccount@ \[ \] .prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="eba89-191">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="eba89-192">活动</span><span class="sxs-lookup"><span data-stu-id="eba89-192">Activity</span></span>   | <span data-ttu-id="eba89-193">Set-AccessToCustomerDataRequest；这是批准或拒绝客户密码箱请求时记录的审核活动。</span><span class="sxs-lookup"><span data-stu-id="eba89-193">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="eba89-194">项目</span><span class="sxs-lookup"><span data-stu-id="eba89-194">Item</span></span>       | <span data-ttu-id="eba89-195">客户密码箱请求的 Guid</span><span class="sxs-lookup"><span data-stu-id="eba89-195">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="eba89-196">以下屏幕截图显示了与批准的客户密码箱请求审核日志记录的示例。</span><span class="sxs-lookup"><span data-stu-id="eba89-196">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="eba89-197">如果客户密码箱请求被拒绝， **则 ApprovalDecision** 参数的值为 **Deny**。</span><span class="sxs-lookup"><span data-stu-id="eba89-197">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![批准的客户密码箱请求的审核记录](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="eba89-199">若要在审核记录中显示更多详细信息，请单击"**详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="eba89-199">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="eba89-200">Microsoft 工程师执行的操作的审核记录</span><span class="sxs-lookup"><span data-stu-id="eba89-200">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="eba89-201">客户密码箱请求获得批准后 Microsoft 工程师执行的操作（可能导致访问客户内容）将记录在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="eba89-201">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="eba89-202">这些记录包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="eba89-202">These records contain the following information.</span></span>

| <span data-ttu-id="eba89-203">审核记录属性</span><span class="sxs-lookup"><span data-stu-id="eba89-203">Audit record property</span></span>| <span data-ttu-id="eba89-204">描述</span><span class="sxs-lookup"><span data-stu-id="eba89-204">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="eba89-205">日期</span><span class="sxs-lookup"><span data-stu-id="eba89-205">Date</span></span>       | <span data-ttu-id="eba89-206">操作执行的日期时间。</span><span class="sxs-lookup"><span data-stu-id="eba89-206">Date time when the action was performed.</span></span> <span data-ttu-id="eba89-207">请注意，执行此操作的时间将在客户密码箱请求获得批准后的 4 小时内。</span><span class="sxs-lookup"><span data-stu-id="eba89-207">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="eba89-208">IP 地址</span><span class="sxs-lookup"><span data-stu-id="eba89-208">IP address</span></span> | <span data-ttu-id="eba89-209">Microsoft 工程师使用的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eba89-209">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="eba89-210">用户</span><span class="sxs-lookup"><span data-stu-id="eba89-210">User</span></span>       | <span data-ttu-id="eba89-211">Microsoft 操作员；此值表示此记录与客户密码箱请求相关。</span><span class="sxs-lookup"><span data-stu-id="eba89-211">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="eba89-212">活动</span><span class="sxs-lookup"><span data-stu-id="eba89-212">Activity</span></span>   | <span data-ttu-id="eba89-213">Microsoft 工程师执行的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="eba89-213">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="eba89-214">项目</span><span class="sxs-lookup"><span data-stu-id="eba89-214">Item</span></span>       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="eba89-215">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="eba89-215">Frequently asked questions</span></span>

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="eba89-216">客户Microsoft 365密码箱适用于哪些服务？</span><span class="sxs-lookup"><span data-stu-id="eba89-216">Which Microsoft 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="eba89-217">客户密码箱当前在 Exchange Online、SharePoint Online 和 OneDrive for Business 中受支持。</span><span class="sxs-lookup"><span data-stu-id="eba89-217">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-customers"></a><span data-ttu-id="eba89-218">客户密码箱是否可供所有客户使用？</span><span class="sxs-lookup"><span data-stu-id="eba89-218">Is Customer Lockbox available to all customers?</span></span>

<span data-ttu-id="eba89-219">客户密码箱包含在 Microsoft 365 或 Office 365 E5 订阅中，并且可以使用信息保护和合规性订阅或高级合规性附加订阅添加到其他计划中。</span><span class="sxs-lookup"><span data-stu-id="eba89-219">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="eba89-220">有关详细信息 [，请参阅计划和](https://products.office.com/business/office-365-enterprise-e5-business-software) 定价。</span><span class="sxs-lookup"><span data-stu-id="eba89-220">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="eba89-221">什么是客户内容？</span><span class="sxs-lookup"><span data-stu-id="eba89-221">What is customer content?</span></span>

<span data-ttu-id="eba89-222">客户内容是由服务和应用程序Microsoft 365创建的数据。</span><span class="sxs-lookup"><span data-stu-id="eba89-222">Customer content is the data created by users of Microsoft 365 services and applications.</span></span> <span data-ttu-id="eba89-223">客户内容的示例包括：</span><span class="sxs-lookup"><span data-stu-id="eba89-223">Examples of customer content include:</span></span>

- <span data-ttu-id="eba89-224">电子邮件正文或电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="eba89-224">Email body or email attachments</span></span>

- <span data-ttu-id="eba89-225">SharePoint 网站内容</span><span class="sxs-lookup"><span data-stu-id="eba89-225">SharePoint site contents</span></span>

- <span data-ttu-id="eba89-226">SharePoint 文件正文中的信息</span><span class="sxs-lookup"><span data-stu-id="eba89-226">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="eba89-227">Skype for Business演示文稿文件正文</span><span class="sxs-lookup"><span data-stu-id="eba89-227">Skype for Business presentation file body</span></span>

- <span data-ttu-id="eba89-228">即时消息 (IM) 或语音对话</span><span class="sxs-lookup"><span data-stu-id="eba89-228">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="eba89-229">客户生成的 Blob 或结构化存储数据（例如 SQL 容器）</span><span class="sxs-lookup"><span data-stu-id="eba89-229">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="eba89-230">客户拥有的安全信息（例如证书、加密密钥和密码）</span><span class="sxs-lookup"><span data-stu-id="eba89-230">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="eba89-231">如果客户内容保留，则推断以及所有后续推断</span><span class="sxs-lookup"><span data-stu-id="eba89-231">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="eba89-232">有关客户信任中心中的客户Office 365，请参阅Office 365[信任中心。](https://products.office.com/business/office-365-trust-center-privacy/)</span><span class="sxs-lookup"><span data-stu-id="eba89-232">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="eba89-233">Who请求访问我的内容时，是否收到通知？</span><span class="sxs-lookup"><span data-stu-id="eba89-233">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="eba89-234">将通知全局管理员和分配有客户密码箱访问审批者管理员角色的任何人。</span><span class="sxs-lookup"><span data-stu-id="eba89-234">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="eba89-235">这些用户也是可以批准客户密码箱请求的用户。</span><span class="sxs-lookup"><span data-stu-id="eba89-235">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="eba89-236">Who可以批准或拒绝我的组织中这些请求吗？</span><span class="sxs-lookup"><span data-stu-id="eba89-236">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="eba89-237">全局管理员和分配有客户密码箱访问审批者管理员角色的任何人都可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-237">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="eba89-238">客户控制其组织中这些角色分配。</span><span class="sxs-lookup"><span data-stu-id="eba89-238">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="eba89-239">如何选择加入客户密码箱？</span><span class="sxs-lookup"><span data-stu-id="eba89-239">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="eba89-240">全局管理员可以在管理中心或管理中心Microsoft 365 Microsoft 365客户密码箱。</span><span class="sxs-lookup"><span data-stu-id="eba89-240">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="eba89-241">如果我批准客户密码箱请求，工程师可以做什么，如何知道 Microsoft 工程师做什么？</span><span class="sxs-lookup"><span data-stu-id="eba89-241">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="eba89-242">批准客户密码箱请求后，Microsoft 工程师授予了使用预批准的 cmdlet 访问客户内容所需的权限。</span><span class="sxs-lookup"><span data-stu-id="eba89-242">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="eba89-243">Microsoft 工程师为响应客户密码箱请求而采取的操作将记录在安全与合规审核日志中&访问。</span><span class="sxs-lookup"><span data-stu-id="eba89-243">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="eba89-244">我如何知道 Microsoft 遵循审批流程？</span><span class="sxs-lookup"><span data-stu-id="eba89-244">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="eba89-245">可以在管理中心内使用客户密码箱请求历史记录交叉引用发送给组织中管理员和审批者Microsoft 365通知。</span><span class="sxs-lookup"><span data-stu-id="eba89-245">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="eba89-246">客户密码箱包含在最新的 [SOC 1 SSAE 16 审核报告中](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。</span><span class="sxs-lookup"><span data-stu-id="eba89-246">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="eba89-247">有关详细信息，可以在 Microsoft 服务信任门户 [中查找最新报告](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。</span><span class="sxs-lookup"><span data-stu-id="eba89-247">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="eba89-248">Microsoft 能否修改我的租户的审批者列表？</span><span class="sxs-lookup"><span data-stu-id="eba89-248">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="eba89-249">如果不是，如何阻止它？</span><span class="sxs-lookup"><span data-stu-id="eba89-249">If not, how is it prevented?</span></span>

<span data-ttu-id="eba89-250">只有贵组织的全局管理员可以指定谁可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-250">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="eba89-251">这意味着只有全局管理员组的成员Azure Active Directory可以批准请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-251">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="eba89-252">组织中全局管理员组的Azure Active Directory仅由您的组织管理。</span><span class="sxs-lookup"><span data-stu-id="eba89-252">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="eba89-253">如果我需要有关内容访问请求的更多信息来批准它，应该怎么做？</span><span class="sxs-lookup"><span data-stu-id="eba89-253">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="eba89-254">每个客户密码箱请求都包含一Microsoft 365服务请求编号。</span><span class="sxs-lookup"><span data-stu-id="eba89-254">Each Customer Lockbox request contains a Microsoft 365 service request number.</span></span> <span data-ttu-id="eba89-255">可以联系 Microsoft 支持部门并参考此服务号码，获取有关请求详细信息。</span><span class="sxs-lookup"><span data-stu-id="eba89-255">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="eba89-256">当客户密码箱请求得到批准时，权限的有效期是多久？</span><span class="sxs-lookup"><span data-stu-id="eba89-256">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="eba89-257">目前，授予 Microsoft 工程师的访问权限的最长期限为 4 小时。</span><span class="sxs-lookup"><span data-stu-id="eba89-257">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="eba89-258">Microsoft 工程师也可请求较短的期限。</span><span class="sxs-lookup"><span data-stu-id="eba89-258">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="eba89-259">如何获取所有客户密码箱请求的历史记录？</span><span class="sxs-lookup"><span data-stu-id="eba89-259">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="eba89-260">所有客户密码箱请求都通过管理中心Microsoft 365查看。</span><span class="sxs-lookup"><span data-stu-id="eba89-260">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="eba89-261">如何将内容访问请求与相关的审核日志关联？</span><span class="sxs-lookup"><span data-stu-id="eba89-261">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="eba89-262">合规性中心活动源包含客户密码箱的日志活动。</span><span class="sxs-lookup"><span data-stu-id="eba89-262">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="eba89-263">客户可以针对他们收到的电子邮件请求交叉引用活动源中的客户密码箱日志活动。</span><span class="sxs-lookup"><span data-stu-id="eba89-263">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="eba89-264">当客户未响应客户密码箱请求时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="eba89-264">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="eba89-265">客户密码箱请求的默认持续时间为 12 小时。</span><span class="sxs-lookup"><span data-stu-id="eba89-265">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="eba89-266">如果在 12 小时内未响应请求，请求将过期。</span><span class="sxs-lookup"><span data-stu-id="eba89-266">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="eba89-267">当客户拒绝客户密码箱请求时，Microsoft 会做什么？</span><span class="sxs-lookup"><span data-stu-id="eba89-267">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="eba89-268">如果客户拒绝客户密码箱请求，则不访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="eba89-268">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="eba89-269">如果贵组织的用户继续遇到需要 Microsoft 访问客户内容才能解决问题的服务问题，则服务问题可能仍然存在，Microsoft 会通知用户此问题。</span><span class="sxs-lookup"><span data-stu-id="eba89-269">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="eba89-270">客户密码箱是否防止来自执法机构或其他第三方的数据请求？</span><span class="sxs-lookup"><span data-stu-id="eba89-270">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="eba89-271">否。</span><span class="sxs-lookup"><span data-stu-id="eba89-271">No.</span></span> <span data-ttu-id="eba89-272">Microsoft 非常重视客户数据的第三方请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-272">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="eba89-273">作为云服务提供商，Microsoft 始终宣传客户数据的隐私。</span><span class="sxs-lookup"><span data-stu-id="eba89-273">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="eba89-274">如果我们收到一个子请求，Microsoft 将始终尝试将第三方重定向到客户以获取信息。</span><span class="sxs-lookup"><span data-stu-id="eba89-274">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="eba89-275"> (Brad Smith 的博客：保护客户数据免受 [政府](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 窥探) 。</span><span class="sxs-lookup"><span data-stu-id="eba89-275">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="eba89-276">我们定期 [发布有关](https://www.microsoft.com/corporate-responsibility/lerr) Microsoft 收到的执法机构请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eba89-276">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="eba89-277">有关详细信息，[请参阅联机](https://www.microsoft.com/trustcenter/default.aspx)服务条款中有关第三方数据请求的 Microsoft 信任中心和"客户数据泄露"[](https://www.microsoft.com/Licensing/product-licensing/products.aspx)部分。</span><span class="sxs-lookup"><span data-stu-id="eba89-277">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="eba89-278">Microsoft 如何确保其员工没有在应用程序内长期访问客户Office 365？</span><span class="sxs-lookup"><span data-stu-id="eba89-278">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="eba89-279">Microsoft 通过访问控制系统和检测性措施实施广泛的预防措施，以识别和解决试图避开这些访问控制系统的尝试。</span><span class="sxs-lookup"><span data-stu-id="eba89-279">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="eba89-280">Microsoft 365遵循最小特权和实时访问原则。</span><span class="sxs-lookup"><span data-stu-id="eba89-280">Microsoft 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="eba89-281">因此，任何 Microsoft 人员都无权持续访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="eba89-281">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="eba89-282">如果授予权限，则其持续时间有限。</span><span class="sxs-lookup"><span data-stu-id="eba89-282">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="eba89-283">Microsoft 365使用称为 *"密码* 箱"的访问控制系统处理权限请求，这些权限授予在服务内执行操作和管理功能的能力。</span><span class="sxs-lookup"><span data-stu-id="eba89-283">Microsoft 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="eba89-284">操作员必须使用密码箱请求访问客户内容，然后要求第二个人对请求采取操作 (例如，在授予访问权限之前) 批准它。</span><span class="sxs-lookup"><span data-stu-id="eba89-284">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="eba89-285">第二个人不能是请求者，必须被指定为批准访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="eba89-285">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="eba89-286">只有在请求得到批准后，操作员才能临时访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="eba89-286">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="eba89-287">提升期到期后，密码箱将撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="eba89-287">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="eba89-288">有关 Microsoft [一](https://www.microsoft.com/licensing/product-licensing/products) 般安全实践的更多详细信息，请参阅联机服务条款。</span><span class="sxs-lookup"><span data-stu-id="eba89-288">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="eba89-289">在什么情况下，Microsoft 工程师需要访问我的内容？</span><span class="sxs-lookup"><span data-stu-id="eba89-289">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="eba89-290">Microsoft 工程师需要访问客户内容的最常见情形是，客户提出需要访问进行疑难解答的支持请求。</span><span class="sxs-lookup"><span data-stu-id="eba89-290">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="eba89-291">服务的基本Microsoft 365是该服务在 Microsoft 不访问客户内容的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="eba89-291">A foundational principle of Microsoft 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="eba89-292">几乎所有由 Microsoft 执行的服务操作都完全自动化，并且人员参与受到严格控制，并且从客户内容中抽象。</span><span class="sxs-lookup"><span data-stu-id="eba89-292">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="eba89-293">在客户Microsoft 365 Microsoft 访问的特定请求之前，不需要访问支持该服务的客户内容。</span><span class="sxs-lookup"><span data-stu-id="eba89-293">The goal for Microsoft 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="eba89-294">我已经认为我的数据在 Microsoft 云中是安全的，那么为什么我需要客户密码箱？</span><span class="sxs-lookup"><span data-stu-id="eba89-294">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="eba89-295">客户密码箱通过为客户提供为服务操作提供显式访问授权的能力，提供了一层额外的控制。</span><span class="sxs-lookup"><span data-stu-id="eba89-295">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="eba89-296">通过证明针对显式数据访问授权已制定相关过程，客户密码箱还帮助客户履行某些合规性义务，如 HIPAA 和 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="eba89-296">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>