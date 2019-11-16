---
title: 在 Office 365 中自动调查和响应威胁
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 开始使用 Office 365 中的自动事件响应功能高级威胁防护计划2。
ms.openlocfilehash: 13f7e95829b8cf3adf17a40cf7b02c5322b15ea7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673418"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="dbc48-104">在 Office 365 中自动调查和响应威胁</span><span class="sxs-lookup"><span data-stu-id="dbc48-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="dbc48-105">概述</span><span class="sxs-lookup"><span data-stu-id="dbc48-105">Overview</span></span>

<span data-ttu-id="dbc48-106">根据你的订阅， [Office 365 高级威胁防护](office-365-atp.md)可以包括自动事件响应（空气）功能，可节省安全操作团队时间和处理警报和威胁的工作。</span><span class="sxs-lookup"><span data-stu-id="dbc48-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="dbc48-107">若要开始使用 Office 365 中的 AIR 功能，请使用本文。</span><span class="sxs-lookup"><span data-stu-id="dbc48-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="dbc48-108">若要了解无线的工作原理，请参阅[Office 365 中的自动化事件响应（空中）](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="dbc48-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="dbc48-109">使用 AIR 时，在触发特定警报时，一个或多个安全行动手册启动，并且自动调查开始。</span><span class="sxs-lookup"><span data-stu-id="dbc48-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="dbc48-110">在自动调查过程期间和之后，管理员和安全操作团队可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dbc48-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="dbc48-111">查看调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="dbc48-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="dbc48-112">查看和批准作为调查结果的操作</span><span class="sxs-lookup"><span data-stu-id="dbc48-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="dbc48-113">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="dbc48-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="dbc48-114">您必须具有适当的权限才能执行本文中所述的任务。</span><span class="sxs-lookup"><span data-stu-id="dbc48-114">You must have appropriate permissions to perform the tasks described in this article.</span></span> <span data-ttu-id="dbc48-115">例如，您 myst 是全局管理员、安全管理员、安全操作员或安全读者。</span><span class="sxs-lookup"><span data-stu-id="dbc48-115">For example, you myst be a global administrator, security administrator, security operator, or security reader.</span></span> <span data-ttu-id="dbc48-116">[了解有关 Microsoft 365 安全中心角色和权限的详细信息](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。</span><span class="sxs-lookup"><span data-stu-id="dbc48-116">[Learn more about Microsoft 365 security center roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="dbc48-117">以下订阅中包含空中：</span><span class="sxs-lookup"><span data-stu-id="dbc48-117">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="dbc48-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dbc48-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="dbc48-119">Microsoft 365 E5 安全版</span><span class="sxs-lookup"><span data-stu-id="dbc48-119">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="dbc48-120">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="dbc48-120">Office 365 E5</span></span>
- <span data-ttu-id="dbc48-121">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="dbc48-121">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="dbc48-122">如果你没有这些订阅之一，请[启动免费试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="dbc48-122">If you don't have one of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="dbc48-123">查看调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="dbc48-123">View details of an investigation</span></span>

1. <span data-ttu-id="dbc48-124">作为 Office 365 全局管理员、安全管理员或安全阅读者，请转到[https://protection.office.com](https://protection.office.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="dbc48-124">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="dbc48-125">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="dbc48-125">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="dbc48-126">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="dbc48-126">Do one of the following:</span></span>

    - <span data-ttu-id="dbc48-127">转到 "**威胁管理** > **仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="dbc48-127">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="dbc48-128">这将转到[安全仪表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="dbc48-128">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="dbc48-129">您的空中小组件显示在[安全仪表板](security-dashboard.md)的顶部。</span><span class="sxs-lookup"><span data-stu-id="dbc48-129">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="dbc48-130">选择一个小部件，如**调查摘要**。</span><span class="sxs-lookup"><span data-stu-id="dbc48-130">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="dbc48-131">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="dbc48-131">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="dbc48-132">每种方法都将转到调查列表。</span><span class="sxs-lookup"><span data-stu-id="dbc48-132">Either method takes you to a list of investigations.</span></span>

    ![空气的主要调查页面](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="dbc48-134">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="dbc48-134">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="dbc48-135">这将打开 "调查详细信息" 页，从视图中的调查图形开始。</span><span class="sxs-lookup"><span data-stu-id="dbc48-135">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![空中调查图形页面](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="dbc48-137">使用各种选项卡了解有关调查的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dbc48-137">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="dbc48-138">审阅和批准操作</span><span class="sxs-lookup"><span data-stu-id="dbc48-138">Review and approve actions</span></span>

<span data-ttu-id="dbc48-139">在 Office 365 中，自动调查通常会生成一个或多个建议的操作。</span><span class="sxs-lookup"><span data-stu-id="dbc48-139">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="dbc48-140">但是，在安全操作团队批准之前，不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="dbc48-140">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="dbc48-141">使用以下过程可查看和审批操作。</span><span class="sxs-lookup"><span data-stu-id="dbc48-141">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="dbc48-142">作为 Office 365 全局管理员、安全管理员或安全阅读者，请转到[https://protection.office.com](https://protection.office.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="dbc48-142">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="dbc48-143">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="dbc48-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="dbc48-144">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="dbc48-144">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="dbc48-145">在调查详细信息视图中，选择 "**操作**" 选项卡。此处列出了待审批的任何操作。</span><span class="sxs-lookup"><span data-stu-id="dbc48-145">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="dbc48-146">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="dbc48-146">Select an item in the list.</span></span>

5. <span data-ttu-id="dbc48-147">选择 "**批准**" 以执行建议的操作（或 "**拒绝**" 以在不采取措施的情况下关闭调查）。</span><span class="sxs-lookup"><span data-stu-id="dbc48-147">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="dbc48-148">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="dbc48-148">View details about an alert related to an investigation</span></span>

<span data-ttu-id="dbc48-149">某些类型的警报会触发 Office 365 中的自动调查。</span><span class="sxs-lookup"><span data-stu-id="dbc48-149">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="dbc48-150">若要了解详细信息，请参阅[警报](automated-investigation-response-office.md#alerts)。</span><span class="sxs-lookup"><span data-stu-id="dbc48-150">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="dbc48-151">使用以下过程可查看与自动调查相关联的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dbc48-151">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="dbc48-152">作为 Office 365 全局管理员、安全管理员或安全阅读者，请转到[https://protection.office.com](https://protection.office.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="dbc48-152">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="dbc48-153">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="dbc48-153">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="dbc48-154">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="dbc48-154">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="dbc48-155">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="dbc48-155">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="dbc48-156">通过打开调查的详细信息，选择 "**通知**" 选项卡。下面列出了所有触发调查的警报。</span><span class="sxs-lookup"><span data-stu-id="dbc48-156">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="dbc48-157">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="dbc48-157">Select an item in the list.</span></span> <span data-ttu-id="dbc48-158">将打开一个浮出控件，其中包含有关该警报的详细信息以及指向其他信息和操作的链接。</span><span class="sxs-lookup"><span data-stu-id="dbc48-158">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="dbc48-159">查看浮出控件上的信息，根据特定的通知执行操作，如**Resolve**、**隐含**或**通知用户**。</span><span class="sxs-lookup"><span data-stu-id="dbc48-159">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="dbc48-160">**Resolve**等效于关闭通知</span><span class="sxs-lookup"><span data-stu-id="dbc48-160">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="dbc48-161">**禁止**使策略在指定时间段内触发警报</span><span class="sxs-lookup"><span data-stu-id="dbc48-161">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="dbc48-162">**通知用户**启动电子邮件，其中包含已输入的用户电子邮件地址，并允许安全操作团队向这些用户键入邮件。</span><span class="sxs-lookup"><span data-stu-id="dbc48-162">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="dbc48-163">（这类似于使用[威胁资源管理器](threat-explorer.md)向收件人发送邮件。）</span><span class="sxs-lookup"><span data-stu-id="dbc48-163">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="dbc48-164">将 Office 365 管理活动 API 用于自定义或第三方报告解决方案</span><span class="sxs-lookup"><span data-stu-id="dbc48-164">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="dbc48-165">如果您的组织使用自定义或第三方报告解决方案，则可以使用 Office 365 管理活动 API 查看该解决方案中有关自动调查的信息。</span><span class="sxs-lookup"><span data-stu-id="dbc48-165">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="dbc48-166">使用以下资源对此进行设置：</span><span class="sxs-lookup"><span data-stu-id="dbc48-166">Use the following resources to set this up:</span></span>

|<span data-ttu-id="dbc48-167">资源</span><span class="sxs-lookup"><span data-stu-id="dbc48-167">Resource</span></span>  |<span data-ttu-id="dbc48-168">说明</span><span class="sxs-lookup"><span data-stu-id="dbc48-168">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="dbc48-169">Office 365 管理 API 概述</span><span class="sxs-lookup"><span data-stu-id="dbc48-169">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="dbc48-170">使用 Office 365 管理活动 API，可从 Office 365 和 Azure Active Directory 活动日志中获取各个用户、管理员、系统以及策略操作和事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="dbc48-170">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="dbc48-171">Office 365 管理 API 入门</span><span class="sxs-lookup"><span data-stu-id="dbc48-171">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="dbc48-172">Office 365 管理 API 使用 Azure AD 为应用程序提供用于访问 Office 365 数据的身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="dbc48-172">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="dbc48-173">请按照本文中的步骤进行设置。</span><span class="sxs-lookup"><span data-stu-id="dbc48-173">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="dbc48-174">Office 365 管理活动 API 参考</span><span class="sxs-lookup"><span data-stu-id="dbc48-174">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="dbc48-175">您可以使用 Office 365 管理活动 API，从 Office 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作以及事件的信息。</span><span class="sxs-lookup"><span data-stu-id="dbc48-175">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="dbc48-176">阅读本文以了解有关如何工作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dbc48-176">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="dbc48-177">Office 365 管理活动 API 架构</span><span class="sxs-lookup"><span data-stu-id="dbc48-177">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="dbc48-178">获取[常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)和[office 365 ATP 以及威胁调查和响应架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)的概述，以了解通过 OFFICE 365 管理活动 API 提供的特定类型的数据。</span><span class="sxs-lookup"><span data-stu-id="dbc48-178">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="dbc48-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dbc48-179">Next steps</span></span>

[<span data-ttu-id="dbc48-180">了解有关通知的详细信息</span><span class="sxs-lookup"><span data-stu-id="dbc48-180">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="dbc48-181">手动查找和调查 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="dbc48-181">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="dbc48-182">了解 Microsoft Defender ATP 中的空气</span><span class="sxs-lookup"><span data-stu-id="dbc48-182">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="dbc48-183">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="dbc48-183">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)