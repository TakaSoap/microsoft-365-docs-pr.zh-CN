---
title: Office 365 客户密码箱请求
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
description: 了解客户密码箱请求，使您可以控制 Microsoft 支持工程师在遇到问题时如何访问数据。
ms.openlocfilehash: 8906fde608e6e6c26604450eed063915e4617d29
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076808"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="97e8e-103">Office 365 中的客户密码箱</span><span class="sxs-lookup"><span data-stu-id="97e8e-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="97e8e-104">本文提供了当前仅适用于具有 Microsoft 365 E5、Office 365 E5、信息保护和合规性或高级合规性附加订阅的组织的功能的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="97e8e-104">This article provides deployment and configuration guidance for a feature that is currently available only for organizations that have a Microsoft 365 E5, Office 365 E5, Information Protection and Compliance, or Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="97e8e-105">客户密码箱支持访问 Exchange Online、SharePoint Online 和 OneDrive for Business 中的数据的请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="97e8e-106">若要建议支持其他 Office 365 服务，请提交[Office 365 UserVoice](https://office365.uservoice.com/)的请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-106">To recommend support for other Office 365 services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="97e8e-107">客户密码箱可确保 Microsoft 无法访问你的内容以执行服务操作，而无需你的明确批准。</span><span class="sxs-lookup"><span data-stu-id="97e8e-107">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="97e8e-108">客户密码箱将你带到审批工作流，以获取访问内容的请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-108">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="97e8e-109">有时，Microsoft 工程师可帮助解决和修复支持流程中的客户报告的问题。</span><span class="sxs-lookup"><span data-stu-id="97e8e-109">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="97e8e-110">通常情况下，通过 Microsoft 已对其服务实施的大量遥测和调试工具来修复问题。</span><span class="sxs-lookup"><span data-stu-id="97e8e-110">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="97e8e-111">但是，某些情况下，需要 Microsoft 工程师才能访问客户内容，以确定根本原因并解决问题。</span><span class="sxs-lookup"><span data-stu-id="97e8e-111">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="97e8e-112">客户密码箱要求工程师在审批工作流的最后步骤中请求从客户进行访问。</span><span class="sxs-lookup"><span data-stu-id="97e8e-112">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="97e8e-113">这将为组织提供批准或拒绝这些请求的选项，并向客户提供直接访问控制。</span><span class="sxs-lookup"><span data-stu-id="97e8e-113">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="97e8e-114">客户密码箱概述视频</span><span class="sxs-lookup"><span data-stu-id="97e8e-114">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="97e8e-115">客户密码箱工作流</span><span class="sxs-lookup"><span data-stu-id="97e8e-115">Customer Lockbox workflow</span></span>

<span data-ttu-id="97e8e-116">Microsoft 工程师启动客户密码箱请求时，以下步骤概述了典型的工作流：</span><span class="sxs-lookup"><span data-stu-id="97e8e-116">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="97e8e-117">组织中的某个人遇到 Office 365 邮箱的问题。</span><span class="sxs-lookup"><span data-stu-id="97e8e-117">Someone at an organization experiences an issue with their Office 365 mailbox.</span></span>

2. <span data-ttu-id="97e8e-118">在用户对问题进行故障排除但不能修复时，他们将使用 Microsoft 支持打开支持请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-118">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="97e8e-119">Microsoft 支持工程师会检查服务请求，并确定访问组织的租户以修复 Exchange Online 中的问题的需求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-119">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="97e8e-120">Microsoft 支持工程师登录到客户密码箱请求工具，并发出数据访问请求，其中包括组织的租户名称、服务请求编号以及工程师需要对数据进行访问的预计时间。</span><span class="sxs-lookup"><span data-stu-id="97e8e-120">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="97e8e-121">Microsoft 支持经理批准请求后，客户密码箱将向组织发送指定的审批者，发送来自 Microsoft 的挂起的访问请求的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="97e8e-121">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![客户密码箱电子邮件通知示例](../media/CustomerLockbox1.png)

   <span data-ttu-id="97e8e-123">在 Microsoft 365 管理中心中分配了 "[客户密码箱访问审批者](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)" 管理员角色的任何人都可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-123">Anyone who is assigned the [Customer Lockbox access approver](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="97e8e-124">审批者登录到 Microsoft 365 管理中心并批准该请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-124">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="97e8e-125">此步骤将通过搜索 Office 365 审核日志，触发创建可供使用的审核记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-125">This step triggers the creation of an audit record available by searching the Office 365 audit log.</span></span> <span data-ttu-id="97e8e-126">有关详细信息，请参阅[审核客户密码箱请求](#auditing-customer-lockbox-requests)。</span><span class="sxs-lookup"><span data-stu-id="97e8e-126">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="97e8e-127">如果客户拒绝请求或不在12小时内批准请求，则请求将过期，并且不向 Microsoft 工程师授予任何访问权限。</span><span class="sxs-lookup"><span data-stu-id="97e8e-127">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="97e8e-128">Microsoft 不包含客户密码箱中的任何链接需要登录 Office 365 的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="97e8e-128">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="97e8e-129">组织中的审批者批准请求后，Microsoft 工程师将收到审批邮件，登录到 Exchange Online 中的租户，并解决客户的问题。</span><span class="sxs-lookup"><span data-stu-id="97e8e-129">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="97e8e-130">Microsoft 工程师将请求的持续时间解决问题，在此之后，将自动吊销访问权限。</span><span class="sxs-lookup"><span data-stu-id="97e8e-130">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="97e8e-131">Microsoft 工程师执行的所有操作都记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="97e8e-131">All actions performed by a Microsoft engineer are logged in the Office 365 audit log.</span></span> <span data-ttu-id="97e8e-132">您可以搜索并查看这些审核记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-132">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="97e8e-133">打开或关闭客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="97e8e-133">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="97e8e-134">您可以在 Microsoft 365 管理中心中打开客户密码箱控件。</span><span class="sxs-lookup"><span data-stu-id="97e8e-134">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="97e8e-135">当你启用客户密码箱时，Microsoft 必须先获取你的组织的审批，然后才能访问你的租户的任何内容。</span><span class="sxs-lookup"><span data-stu-id="97e8e-135">When you turn on Customer Lockbox, Microsoft must obtain your organization’s approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="97e8e-136">使用已分配全局管理员或**客户密码箱访问审批者**角色的工作或学校帐户，转到[https://admin.microsoft.com](https://admin.microsoft.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-136">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="97e8e-137">选择 "**设置" > 安全性 & 隐私**"。</span><span class="sxs-lookup"><span data-stu-id="97e8e-137">Choose **Settings > Security & privacy**.</span></span>

    ![编辑管理中心中的客户密码箱设置](../media/CustomerLockbox2.png)

3. <span data-ttu-id="97e8e-139">在 "**客户密码箱**" 磁贴上，选择 "**编辑**"，然后将开关移动到 "打开" 或 **"** **关闭**" 以打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="97e8e-139">On the **Customer Lockbox** tile, choose **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="97e8e-141">批准或拒绝客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="97e8e-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="97e8e-142">使用已分配全局管理员或**客户密码箱访问审批者**角色的工作或学校帐户，转到[https://admin.microsoft.com](https://admin.microsoft.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="97e8e-143">选择 "**支持 > 客户密码箱请求**"。</span><span class="sxs-lookup"><span data-stu-id="97e8e-143">Choose **Support > Customer Lockbox Requests**.</span></span>

    ![单击 "支持"，然后单击 "客户密码箱请求"](../media/CustomerLockbox5.png)

    <span data-ttu-id="97e8e-145">将显示客户密码箱请求的列表。</span><span class="sxs-lookup"><span data-stu-id="97e8e-145">A list of Customer Lockbox requests displays.</span></span>

    ![客户密码箱请求列表](../media/CustomerLockbox6.png)

3. <span data-ttu-id="97e8e-147">选择 "客户密码箱请求"，然后选择 "**批准**" 或 "**拒绝**"。</span><span class="sxs-lookup"><span data-stu-id="97e8e-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny**.</span></span>

    ![批准或拒绝客户密码箱请求](../media/CustomerLockbox7.png)

    <span data-ttu-id="97e8e-149">将显示有关客户密码箱请求的审批的确认消息。</span><span class="sxs-lookup"><span data-stu-id="97e8e-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![批准或拒绝客户密码箱请求](../media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="97e8e-151">审核客户密码箱请求</span><span class="sxs-lookup"><span data-stu-id="97e8e-151">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="97e8e-152">与客户密码箱请求对应的审核记录将记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="97e8e-152">Audit records that correspond to the Customer Lockbox requests are logged in the Office 365 audit log.</span></span> <span data-ttu-id="97e8e-153">您可以使用 "Office 365 安全 & 合规中心" 中的 "[审核日志搜索" 工具](search-the-audit-log-in-security-and-compliance.md)访问这些日志。</span><span class="sxs-lookup"><span data-stu-id="97e8e-153">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="97e8e-154">与接受或拒绝客户密码箱请求以及 Microsoft 工程师执行的操作相关的操作（当访问请求获得批准时）也会记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="97e8e-154">Actions related to a accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the Office 365 audit log.</span></span> <span data-ttu-id="97e8e-155">您可以搜索并查看这些审核记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-155">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="97e8e-156">在审核日志中搜索与客户密码箱请求相关的活动</span><span class="sxs-lookup"><span data-stu-id="97e8e-156">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="97e8e-157">在可以使用审核日志跟踪客户密码箱的请求之前，需要执行一些步骤来设置审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-157">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to to set up audit logging.</span></span> <span data-ttu-id="97e8e-158">有关详细信息，请参阅[在 Office 365 安全与合规中心内搜索审核日志](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)。</span><span class="sxs-lookup"><span data-stu-id="97e8e-158">For more information, see [Search the audit log in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="97e8e-159">完成安装后，请按照以下步骤创建审核日志搜索查询，以返回与客户密码箱相关的审核记录：</span><span class="sxs-lookup"><span data-stu-id="97e8e-159">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="97e8e-160">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="97e8e-160">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="97e8e-161">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="97e8e-161">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="97e8e-162">在安全性 & 合规性中心的左侧窗格中，选择 "**搜索 & 调查** > **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="97e8e-162">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="97e8e-163">将显示 "**审核日志搜索**" 页。</span><span class="sxs-lookup"><span data-stu-id="97e8e-163">The **Audit log search** page displays.</span></span>

    ![审核日志搜索页](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="97e8e-165">配置以下搜索条件：</span><span class="sxs-lookup"><span data-stu-id="97e8e-165">Configure the following search criteria:</span></span>

    <span data-ttu-id="97e8e-166">a.</span><span class="sxs-lookup"><span data-stu-id="97e8e-166">a.</span></span> <span data-ttu-id="97e8e-167">**活动**-将此字段保留为空，以便搜索将返回所有活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-167">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="97e8e-168">若要返回与客户密码箱请求和 Microsoft 工程师所执行的相应活动相关的任何审核记录，这是必需的。</span><span class="sxs-lookup"><span data-stu-id="97e8e-168">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    <span data-ttu-id="97e8e-169">b.</span><span class="sxs-lookup"><span data-stu-id="97e8e-169">b.</span></span> <span data-ttu-id="97e8e-170">"**开始日期**" 和 "**结束日期**"-选择要显示在该时间段内发生的事件的日期和时间范围。</span><span class="sxs-lookup"><span data-stu-id="97e8e-170">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    <span data-ttu-id="97e8e-171">c.</span><span class="sxs-lookup"><span data-stu-id="97e8e-171">c.</span></span> <span data-ttu-id="97e8e-172">**用户**-将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="97e8e-172">**Users** - Leave this field blank.</span></span>

    <span data-ttu-id="97e8e-173">d.</span><span class="sxs-lookup"><span data-stu-id="97e8e-173">d.</span></span> <span data-ttu-id="97e8e-174">**文件、文件夹或网站**-将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="97e8e-174">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="97e8e-175">单击“**搜索**”以使用搜索条件运行搜索。</span><span class="sxs-lookup"><span data-stu-id="97e8e-175">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="97e8e-176">搜索结果已加载，并在几分钟后显示在 "**审核日志搜索**" 页上的 "**结果**" 下。</span><span class="sxs-lookup"><span data-stu-id="97e8e-176">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="97e8e-177">单击 "搜索结果" 页上的 "**筛选结果**"，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="97e8e-177">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="97e8e-178">若要显示与组织中的审批者批准或拒绝客户密码箱请求的审核记录，请执行以下操作：在 "**活动**" 列下的框中，键入**AccessToCustomerDataRequest**。</span><span class="sxs-lookup"><span data-stu-id="97e8e-178">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="97e8e-179">显示与 Microsoft 工程师相关的审核记录，以响应批准的客户密码箱请求：在 "**用户**" 列下的框中，键入 " **Microsoft 接线员**"。</span><span class="sxs-lookup"><span data-stu-id="97e8e-179">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="97e8e-180">"**活动**" 列将显示工程师执行的操作。</span><span class="sxs-lookup"><span data-stu-id="97e8e-180">The **Activity** column displays the action performed by the engineer.</span></span>

      ![在 "Microsoft 接线员" 上筛选以显示审核记录](../media/CustomerLockbox10.png)

7. <span data-ttu-id="97e8e-182">在结果列表中，单击要显示的审核记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-182">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="97e8e-183">客户密码箱访问请求的审核记录</span><span class="sxs-lookup"><span data-stu-id="97e8e-183">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="97e8e-184">当您的组织中的某个人批准或拒绝客户密码箱请求时，将在 Office 365 审核日志中记录审核记录。</span><span class="sxs-lookup"><span data-stu-id="97e8e-184">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the Office 365 audit log.</span></span> <span data-ttu-id="97e8e-185">此记录包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="97e8e-185">This record contains the following information.</span></span>

| <span data-ttu-id="97e8e-186">审核记录属性</span><span class="sxs-lookup"><span data-stu-id="97e8e-186">Audit record property</span></span>| <span data-ttu-id="97e8e-187">描述</span><span class="sxs-lookup"><span data-stu-id="97e8e-187">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="97e8e-188">日期</span><span class="sxs-lookup"><span data-stu-id="97e8e-188">Date</span></span>       | <span data-ttu-id="97e8e-189">批准或拒绝客户密码箱请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="97e8e-189">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="97e8e-190">IP 地址</span><span class="sxs-lookup"><span data-stu-id="97e8e-190">IP address</span></span> | <span data-ttu-id="97e8e-191">审批者用于批准或拒绝请求的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="97e8e-191">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="97e8e-192">用户</span><span class="sxs-lookup"><span data-stu-id="97e8e-192">User</span></span>       | <span data-ttu-id="97e8e-193">服务帐户 BOXServiceAccount@\[customerforest\]。 prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="97e8e-193">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="97e8e-194">活动</span><span class="sxs-lookup"><span data-stu-id="97e8e-194">Activity</span></span>   | <span data-ttu-id="97e8e-195">AccessToCustomerDataRequest;这是您批准或拒绝客户密码箱请求时记录的审核活动。</span><span class="sxs-lookup"><span data-stu-id="97e8e-195">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="97e8e-196">项目</span><span class="sxs-lookup"><span data-stu-id="97e8e-196">Item</span></span>       | <span data-ttu-id="97e8e-197">客户密码箱请求的 Guid</span><span class="sxs-lookup"><span data-stu-id="97e8e-197">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="97e8e-198">下面的屏幕截图显示了与批准的客户密码箱请求对应的审核日志记录的示例。</span><span class="sxs-lookup"><span data-stu-id="97e8e-198">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="97e8e-199">如果客户密码箱请求被拒绝，则**ApprovalDecision**参数的值将为**Deny**。</span><span class="sxs-lookup"><span data-stu-id="97e8e-199">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![批准的客户密码箱请求的审核记录](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="97e8e-201">若要在审核记录中显示更详细的信息，请单击 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="97e8e-201">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="97e8e-202">由 Microsoft 工程师执行的操作的审核记录</span><span class="sxs-lookup"><span data-stu-id="97e8e-202">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="97e8e-203">在客户密码箱请求获得批准（并可能导致访问客户内容）后，由 Microsoft 工程师执行的操作将记录在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="97e8e-203">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="97e8e-204">这些记录包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="97e8e-204">These records contain the following information.</span></span>

| <span data-ttu-id="97e8e-205">审核记录属性</span><span class="sxs-lookup"><span data-stu-id="97e8e-205">Audit record property</span></span>| <span data-ttu-id="97e8e-206">描述</span><span class="sxs-lookup"><span data-stu-id="97e8e-206">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="97e8e-207">日期</span><span class="sxs-lookup"><span data-stu-id="97e8e-207">Date</span></span>       | <span data-ttu-id="97e8e-208">执行操作的日期时间。</span><span class="sxs-lookup"><span data-stu-id="97e8e-208">Date time when the action was performed.</span></span> <span data-ttu-id="97e8e-209">请注意，执行此操作的时间将不超过客户密码箱请求批准的4个小时。</span><span class="sxs-lookup"><span data-stu-id="97e8e-209">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="97e8e-210">IP 地址</span><span class="sxs-lookup"><span data-stu-id="97e8e-210">IP address</span></span> | <span data-ttu-id="97e8e-211">Microsoft 工程师使用的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="97e8e-211">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="97e8e-212">用户</span><span class="sxs-lookup"><span data-stu-id="97e8e-212">User</span></span>       | <span data-ttu-id="97e8e-213">Microsoft 运算符;此值指示此记录与客户密码箱请求相关。</span><span class="sxs-lookup"><span data-stu-id="97e8e-213">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="97e8e-214">活动</span><span class="sxs-lookup"><span data-stu-id="97e8e-214">Activity</span></span>   | <span data-ttu-id="97e8e-215">Microsoft 工程师执行的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="97e8e-215">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="97e8e-216">项目</span><span class="sxs-lookup"><span data-stu-id="97e8e-216">Item</span></span>       | <span data-ttu-id="97e8e-217">\<empty\></span><span class="sxs-lookup"><span data-stu-id="97e8e-217">\<empty\></span></span>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="97e8e-218">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="97e8e-218">Frequently asked questions</span></span>

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="97e8e-219">客户密码箱适用的 Office 365 服务是什么？</span><span class="sxs-lookup"><span data-stu-id="97e8e-219">Which Office 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="97e8e-220">客户密码箱目前在 Exchange Online、SharePoint Online 和 OneDrive for Business 中受支持。</span><span class="sxs-lookup"><span data-stu-id="97e8e-220">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a><span data-ttu-id="97e8e-221">客户密码箱是否适用于所有 Office 365 客户？</span><span class="sxs-lookup"><span data-stu-id="97e8e-221">Is Customer Lockbox available to all Office 365 customers?</span></span>

<span data-ttu-id="97e8e-222">客户密码箱包含在 Microsoft 365 或 Office 365 E5 订阅中，并且可以添加到具有信息保护和合规性或高级合规性附加订阅的其他计划中。</span><span class="sxs-lookup"><span data-stu-id="97e8e-222">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="97e8e-223">有关详细信息，请参阅 [计划和定价](https://products.office.com/business/office-365-enterprise-e5-business-software) 。</span><span class="sxs-lookup"><span data-stu-id="97e8e-223">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="97e8e-224">什么是客户内容？</span><span class="sxs-lookup"><span data-stu-id="97e8e-224">What is customer content?</span></span>

<span data-ttu-id="97e8e-225">客户内容是由 Office 365 服务和应用程序的用户创建的数据。</span><span class="sxs-lookup"><span data-stu-id="97e8e-225">Customer content is the data created by users of Office 365 services and applications.</span></span> <span data-ttu-id="97e8e-226">客户内容的示例包括：</span><span class="sxs-lookup"><span data-stu-id="97e8e-226">Examples of customer content include:</span></span>

- <span data-ttu-id="97e8e-227">电子邮件正文或电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="97e8e-227">Email body or email attachments</span></span>

- <span data-ttu-id="97e8e-228">SharePoint 网站内容</span><span class="sxs-lookup"><span data-stu-id="97e8e-228">SharePoint site contents</span></span>

- <span data-ttu-id="97e8e-229">SharePoint 文件正文中的信息</span><span class="sxs-lookup"><span data-stu-id="97e8e-229">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="97e8e-230">Skype for Business 演示文稿文件正文</span><span class="sxs-lookup"><span data-stu-id="97e8e-230">Skype for Business presentation file body</span></span>

- <span data-ttu-id="97e8e-231">即时消息（IM）或语音对话</span><span class="sxs-lookup"><span data-stu-id="97e8e-231">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="97e8e-232">客户生成的 blob 或结构化存储数据（例如，SQL 容器）</span><span class="sxs-lookup"><span data-stu-id="97e8e-232">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="97e8e-233">由客户拥有的安全信息（例如，证书、加密密钥和密码）</span><span class="sxs-lookup"><span data-stu-id="97e8e-233">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="97e8e-234">如果客户内容仍然存在，则推断和所有后续推断</span><span class="sxs-lookup"><span data-stu-id="97e8e-234">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="97e8e-235">有关 Office 365 中的客户内容的其他信息，请参阅[office 365 信任中心](https://products.office.com/business/office-365-trust-center-privacy/)。</span><span class="sxs-lookup"><span data-stu-id="97e8e-235">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="97e8e-236">当有访问我的内容的请求时，会向谁发出通知？</span><span class="sxs-lookup"><span data-stu-id="97e8e-236">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="97e8e-237">系统会通知全局管理员和分配了客户密码箱访问审批者管理员角色的任何人。</span><span class="sxs-lookup"><span data-stu-id="97e8e-237">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="97e8e-238">这些用户也是可以批准客户密码箱请求的相同用户。</span><span class="sxs-lookup"><span data-stu-id="97e8e-238">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="97e8e-239">谁可以在组织中批准或拒绝这些请求？</span><span class="sxs-lookup"><span data-stu-id="97e8e-239">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="97e8e-240">全局管理员和分配了客户密码箱访问审批者管理员角色的任何人都可以批准客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-240">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="97e8e-241">客户在其组织中控制这些角色分配。</span><span class="sxs-lookup"><span data-stu-id="97e8e-241">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="97e8e-242">如何选择客户密码箱？</span><span class="sxs-lookup"><span data-stu-id="97e8e-242">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="97e8e-243">全局管理员可以在 Microsoft 365 或 Microsoft 365 管理中心中启用和配置客户密码箱。</span><span class="sxs-lookup"><span data-stu-id="97e8e-243">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="97e8e-244">如果我批准客户密码箱请求，工程师可以执行哪些操作，以及我如何知道 Microsoft 工程师所做的工作？</span><span class="sxs-lookup"><span data-stu-id="97e8e-244">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="97e8e-245">批准客户密码箱请求后，Microsoft 工程师授予这些必需的权限，以使用预先批准的 cmdlet 访问客户内容。</span><span class="sxs-lookup"><span data-stu-id="97e8e-245">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="97e8e-246">Microsoft 工程师在响应客户密码箱请求时所执行的操作将记录下来并可在 Office 365 安全 & 合规性中心的审核日志中访问。</span><span class="sxs-lookup"><span data-stu-id="97e8e-246">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Office 365 Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="97e8e-247">我如何知道 Microsoft 遵循审批过程？</span><span class="sxs-lookup"><span data-stu-id="97e8e-247">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="97e8e-248">您可以通过 Microsoft 365 管理中心中的客户密码箱请求历史记录，交叉引用发送给组织中的管理员和审批者的电子邮件审批通知。</span><span class="sxs-lookup"><span data-stu-id="97e8e-248">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="97e8e-249">最新[SOC 1 SSAE 16 审核报告](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)中包含客户密码箱。</span><span class="sxs-lookup"><span data-stu-id="97e8e-249">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="97e8e-250">有关更多详细信息，可以在[Microsoft 服务信任门户](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)中找到最新报告。</span><span class="sxs-lookup"><span data-stu-id="97e8e-250">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="97e8e-251">Microsoft 是否可以修改我的租户的审批者列表？</span><span class="sxs-lookup"><span data-stu-id="97e8e-251">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="97e8e-252">如果不是，如何避免？</span><span class="sxs-lookup"><span data-stu-id="97e8e-252">If not, how is it prevented?</span></span>

<span data-ttu-id="97e8e-253">只有组织中的全局管理员才能指定可以批准客户密码箱请求的用户。</span><span class="sxs-lookup"><span data-stu-id="97e8e-253">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="97e8e-254">这意味着，只有 Azure Active Directory 中全局管理员组的成员才能指定可以批准请求的人员。</span><span class="sxs-lookup"><span data-stu-id="97e8e-254">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="97e8e-255">Azure Active Directory 中全局管理员组的成员身份仅由您的组织管理。</span><span class="sxs-lookup"><span data-stu-id="97e8e-255">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="97e8e-256">如果我需要有关内容访问请求的详细信息来批准它，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="97e8e-256">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="97e8e-257">每个客户密码箱请求都包含一个 Office 365 服务请求号码。</span><span class="sxs-lookup"><span data-stu-id="97e8e-257">Each Customer Lockbox request contains an Office 365 service request number.</span></span> <span data-ttu-id="97e8e-258">您可以联系 Microsoft 支持部门并参考此服务号码，以获取有关请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="97e8e-258">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="97e8e-259">在批准客户密码箱请求时，权限的有效期是多长时间？</span><span class="sxs-lookup"><span data-stu-id="97e8e-259">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="97e8e-260">目前，授予 Microsoft 工程师访问权限的最长期限为4小时。</span><span class="sxs-lookup"><span data-stu-id="97e8e-260">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="97e8e-261">Microsoft 工程师还可以请求较短的时间段。</span><span class="sxs-lookup"><span data-stu-id="97e8e-261">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="97e8e-262">如何获取所有客户密码箱请求的历史记录？</span><span class="sxs-lookup"><span data-stu-id="97e8e-262">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="97e8e-263">在 Microsoft 365 管理中心中查看所有客户密码箱请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-263">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="97e8e-264">如何将内容访问请求与相关审核日志关联？</span><span class="sxs-lookup"><span data-stu-id="97e8e-264">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="97e8e-265">合规中心活动源包含客户密码箱的日志活动。</span><span class="sxs-lookup"><span data-stu-id="97e8e-265">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="97e8e-266">客户可以根据其收到的电子邮件请求，从活动源中交叉引用客户密码箱日志活动。</span><span class="sxs-lookup"><span data-stu-id="97e8e-266">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="97e8e-267">当客户没有响应客户密码箱请求时，会发生什么？</span><span class="sxs-lookup"><span data-stu-id="97e8e-267">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="97e8e-268">客户密码箱请求的默认持续时间为12小时。</span><span class="sxs-lookup"><span data-stu-id="97e8e-268">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="97e8e-269">如果在12小时内不响应请求，则请求将过期。</span><span class="sxs-lookup"><span data-stu-id="97e8e-269">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="97e8e-270">当客户拒绝客户密码箱请求时，Microsoft 会做什么？</span><span class="sxs-lookup"><span data-stu-id="97e8e-270">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="97e8e-271">如果客户拒绝客户密码箱请求，则不会发生对客户内容的访问。</span><span class="sxs-lookup"><span data-stu-id="97e8e-271">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="97e8e-272">如果组织中的用户继续遇到要求 Microsoft 访问客户内容以解决问题的服务问题，则服务问题可能会持续存在，Microsoft 将向用户通知此问题。</span><span class="sxs-lookup"><span data-stu-id="97e8e-272">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="97e8e-273">客户密码箱是否防止来自法律强制机构或其他第三方的数据请求？</span><span class="sxs-lookup"><span data-stu-id="97e8e-273">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="97e8e-274">否。</span><span class="sxs-lookup"><span data-stu-id="97e8e-274">No.</span></span> <span data-ttu-id="97e8e-275">Microsoft 会认真为客户数据提供第三方请求。</span><span class="sxs-lookup"><span data-stu-id="97e8e-275">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="97e8e-276">作为云服务提供商，Microsoft 始终支持客户数据的隐私。</span><span class="sxs-lookup"><span data-stu-id="97e8e-276">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="97e8e-277">在我们收到传唤的情况下，Microsoft 将始终尝试将第三方重定向到客户以获取信息。</span><span class="sxs-lookup"><span data-stu-id="97e8e-277">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="97e8e-278">（阅读 Brad Smith 的博客：[保护客户数据免受政府窥探](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)）。</span><span class="sxs-lookup"><span data-stu-id="97e8e-278">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="97e8e-279">我们将定期发布有关 Microsoft 收到的法律强制请求的[详细信息](https://www.microsoft.com/corporate-responsibility/lerr)。</span><span class="sxs-lookup"><span data-stu-id="97e8e-279">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="97e8e-280">有关详细信息，请参阅有关第三方数据请求的[Microsoft 信任中心](https://www.microsoft.com/trustcenter/default.aspx)和[在线服务条款](https://www.microsoft.com/Licensing/product-licensing/products.aspx)中的 "客户数据泄露" 部分。</span><span class="sxs-lookup"><span data-stu-id="97e8e-280">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="97e8e-281">Microsoft 如何确保其员工的成员在 Office 365 应用程序中不具有对客户内容的访问权限？</span><span class="sxs-lookup"><span data-stu-id="97e8e-281">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="97e8e-282">Microsoft 通过访问控制系统实施广泛的防护措施，使用侦探措施来识别和解决绕过这些访问控制系统的尝试。</span><span class="sxs-lookup"><span data-stu-id="97e8e-282">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="97e8e-283">Office 365 以最小特权和实时访问原则运行。</span><span class="sxs-lookup"><span data-stu-id="97e8e-283">Office 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="97e8e-284">因此，任何 Microsoft 人员都不具有定期访问客户内容的权限。</span><span class="sxs-lookup"><span data-stu-id="97e8e-284">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="97e8e-285">如果授予了权限，将在有限的持续时间内进行。</span><span class="sxs-lookup"><span data-stu-id="97e8e-285">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="97e8e-286">Office 365 使用称为 "*密码箱*" 的访问控制系统处理权限的请求，该权限允许在服务中执行操作和管理功能。</span><span class="sxs-lookup"><span data-stu-id="97e8e-286">Office 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="97e8e-287">操作员必须使用密码箱请求对客户内容的访问权限，这样，在授予访问权限之前，需要第二个人对请求执行操作（例如，审批它）。</span><span class="sxs-lookup"><span data-stu-id="97e8e-287">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="97e8e-288">第二个人不能是请求者，必须指定它以批准对客户内容的访问。</span><span class="sxs-lookup"><span data-stu-id="97e8e-288">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="97e8e-289">仅当请求得到批准时，操作员才能获取对客户内容的临时访问权限。</span><span class="sxs-lookup"><span data-stu-id="97e8e-289">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="97e8e-290">提升期过期后，密码箱将撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="97e8e-290">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="97e8e-291">有关 Microsoft 常规安全实践的更多详细信息，请参阅[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。</span><span class="sxs-lookup"><span data-stu-id="97e8e-291">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="97e8e-292">在什么情况下，Microsoft 工程师需要访问我的内容？</span><span class="sxs-lookup"><span data-stu-id="97e8e-292">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="97e8e-293">最常见的情况是，Microsoft 工程师需要访问客户内容的情况是，客户提出支持访问请求以进行故障排除的情况。</span><span class="sxs-lookup"><span data-stu-id="97e8e-293">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="97e8e-294">Office 365 的基础原则是，该服务在没有 Microsoft 访问客户内容的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="97e8e-294">A foundational principle of Office 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="97e8e-295">Microsoft 执行的几乎所有服务操作都是完全自动化的，人工干预是高度控制的，并从客户内容中提取出来。</span><span class="sxs-lookup"><span data-stu-id="97e8e-295">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="97e8e-296">Office 365 的目标是，在客户批准对 Microsoft access 的特定请求之前，不需要访问客户内容以支持服务。</span><span class="sxs-lookup"><span data-stu-id="97e8e-296">The goal for Office 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="97e8e-297">我已经认为我的数据是 Microsoft 云的安全性，所以我为什么需要客户密码箱？</span><span class="sxs-lookup"><span data-stu-id="97e8e-297">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="97e8e-298">客户密码箱通过让客户能够为服务操作提供显式访问授权，从而提供了额外的控制层。</span><span class="sxs-lookup"><span data-stu-id="97e8e-298">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="97e8e-299">通过演示如何将过程用于显式数据访问授权，客户密码箱还可帮助客户满足某些合规性义务，如 HIPAA 和 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="97e8e-299">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>
