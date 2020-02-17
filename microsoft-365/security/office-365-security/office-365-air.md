---
title: 在 Office 365 中自动调查和响应威胁
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 开始使用 Office 365 中的自动调查和响应功能高级威胁防护计划2。
ms.openlocfilehash: d45141ce671a4615cb4fd550e36bc7215cd38d51
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088311"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="571ac-104">在 Office 365 中自动调查和响应威胁</span><span class="sxs-lookup"><span data-stu-id="571ac-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="571ac-105">概述</span><span class="sxs-lookup"><span data-stu-id="571ac-105">Overview</span></span>

<span data-ttu-id="571ac-106">根据你的订阅， [Office 365 高级威胁防护](office-365-atp.md)可以包括自动调查和响应（空气）功能，可以在处理警报和威胁时节省安全运营团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="571ac-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="571ac-107">若要开始使用 Office 365 中的自动调查和响应功能，请使用本文。</span><span class="sxs-lookup"><span data-stu-id="571ac-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="571ac-108">若要获取其工作原理的概述，请参阅[Office 365 中的自动调查和响应](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="571ac-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="571ac-109">你的 Microsoft 365 E5 或 Microsoft 365 E3 是否具有身份和威胁防护？</span><span class="sxs-lookup"><span data-stu-id="571ac-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="571ac-110">考虑尝试[在 Microsoft 威胁防护中进行自动调查和响应（空中）](../mtp/mtp-autoir.md)。</span><span class="sxs-lookup"><span data-stu-id="571ac-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="571ac-111">使用自动调查和响应功能，在触发特定警报时，一个或多个安全行动手册启动，并且自动调查过程开始。</span><span class="sxs-lookup"><span data-stu-id="571ac-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="571ac-112">在自动调查过程期间和之后，安全团队可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="571ac-112">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="571ac-113">查看调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="571ac-113">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="571ac-114">查看和批准作为调查结果的操作</span><span class="sxs-lookup"><span data-stu-id="571ac-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="571ac-115">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="571ac-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="571ac-116">若要执行本文中所述的任务，您必须分配有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="571ac-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="571ac-117">查看[使用空中功能所需的权限](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="571ac-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="571ac-118">查看调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="571ac-118">View details of an investigation</span></span>

1. <span data-ttu-id="571ac-119">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="571ac-119">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="571ac-120">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="571ac-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="571ac-121">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="571ac-121">Do one of the following:</span></span>

    - <span data-ttu-id="571ac-122">转到 "**威胁管理** > **仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="571ac-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="571ac-123">这将转到[安全仪表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="571ac-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="571ac-124">您的空中小组件显示在[安全仪表板](security-dashboard.md)的顶部。</span><span class="sxs-lookup"><span data-stu-id="571ac-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="571ac-125">选择一个小部件，如**调查摘要**。</span><span class="sxs-lookup"><span data-stu-id="571ac-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="571ac-126">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="571ac-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="571ac-127">每种方法都将转到调查列表。</span><span class="sxs-lookup"><span data-stu-id="571ac-127">Either method takes you to a list of investigations.</span></span>

    ![空气的主要调查页面](../../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="571ac-129">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="571ac-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="571ac-130">这将打开 "调查详细信息" 页，从视图中的调查图形开始。</span><span class="sxs-lookup"><span data-stu-id="571ac-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![空中调查图形页面](../../media/air-investigationgraphpage.png)

4. <span data-ttu-id="571ac-132">使用各种选项卡了解有关调查的详细信息。</span><span class="sxs-lookup"><span data-stu-id="571ac-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="571ac-133">审阅和批准操作</span><span class="sxs-lookup"><span data-stu-id="571ac-133">Review and approve actions</span></span>

<span data-ttu-id="571ac-134">在 Office 365 中，自动调查通常会生成一个或多个建议的操作。</span><span class="sxs-lookup"><span data-stu-id="571ac-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="571ac-135">但是，在安全操作团队批准之前，不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="571ac-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="571ac-136">使用以下过程可查看和审批操作。</span><span class="sxs-lookup"><span data-stu-id="571ac-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="571ac-137">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="571ac-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="571ac-138">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="571ac-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="571ac-139">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="571ac-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="571ac-140">在调查详细信息视图中，选择 "**操作**" 选项卡。此处列出了待审批的任何操作。</span><span class="sxs-lookup"><span data-stu-id="571ac-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="571ac-141">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="571ac-141">Select an item in the list.</span></span>

5. <span data-ttu-id="571ac-142">选择 "**批准**" 以执行建议的操作（或 "**拒绝**" 以在不采取措施的情况下关闭调查）。</span><span class="sxs-lookup"><span data-stu-id="571ac-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="571ac-143">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="571ac-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="571ac-144">某些类型的警报会触发 Office 365 中的自动调查。</span><span class="sxs-lookup"><span data-stu-id="571ac-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="571ac-145">若要了解详细信息，请参阅[警报](automated-investigation-response-office.md#alerts)。</span><span class="sxs-lookup"><span data-stu-id="571ac-145">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="571ac-146">使用以下过程可查看与自动调查相关联的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="571ac-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="571ac-147">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="571ac-147">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="571ac-148">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="571ac-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="571ac-149">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="571ac-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="571ac-150">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="571ac-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="571ac-151">通过打开调查的详细信息，选择 "**通知**" 选项卡。下面列出了所有触发调查的警报。</span><span class="sxs-lookup"><span data-stu-id="571ac-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="571ac-152">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="571ac-152">Select an item in the list.</span></span> <span data-ttu-id="571ac-153">将打开一个浮出控件，其中包含有关该警报的详细信息以及指向其他信息和操作的链接。</span><span class="sxs-lookup"><span data-stu-id="571ac-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="571ac-154">查看浮出控件上的信息，根据特定的通知执行操作，如**Resolve**、**隐含**或**通知用户**。</span><span class="sxs-lookup"><span data-stu-id="571ac-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="571ac-155">**Resolve**等效于关闭通知</span><span class="sxs-lookup"><span data-stu-id="571ac-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="571ac-156">**禁止**使策略在指定时间段内触发警报</span><span class="sxs-lookup"><span data-stu-id="571ac-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="571ac-157">**通知用户**启动电子邮件，其中包含已输入的用户电子邮件地址，并允许安全操作团队向这些用户键入邮件。</span><span class="sxs-lookup"><span data-stu-id="571ac-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="571ac-158">（这类似于使用[威胁资源管理器](threat-explorer.md)向收件人发送邮件。）</span><span class="sxs-lookup"><span data-stu-id="571ac-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="571ac-159">将 Office 365 管理活动 API 用于自定义或第三方报告解决方案</span><span class="sxs-lookup"><span data-stu-id="571ac-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="571ac-160">如果您的组织使用自定义或第三方报告解决方案，则可以使用 Office 365 管理活动 API 查看该解决方案中有关自动调查的信息。</span><span class="sxs-lookup"><span data-stu-id="571ac-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="571ac-161">使用以下资源对此进行设置：</span><span class="sxs-lookup"><span data-stu-id="571ac-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="571ac-162">Resource</span><span class="sxs-lookup"><span data-stu-id="571ac-162">Resource</span></span>  |<span data-ttu-id="571ac-163">描述</span><span class="sxs-lookup"><span data-stu-id="571ac-163">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="571ac-164">Office 365 管理 API 概述</span><span class="sxs-lookup"><span data-stu-id="571ac-164">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="571ac-165">使用 Office 365 管理活动 API，可从 Office 365 和 Azure Active Directory 活动日志中获取各个用户、管理员、系统以及策略操作和事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="571ac-165">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="571ac-166">Office 365 管理 API 入门</span><span class="sxs-lookup"><span data-stu-id="571ac-166">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="571ac-167">Office 365 管理 API 使用 Azure AD 为应用程序提供用于访问 Office 365 数据的身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="571ac-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="571ac-168">请按照本文中的步骤进行设置。</span><span class="sxs-lookup"><span data-stu-id="571ac-168">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="571ac-169">Office 365 管理活动 API 参考</span><span class="sxs-lookup"><span data-stu-id="571ac-169">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="571ac-170">您可以使用 Office 365 管理活动 API，从 Office 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作以及事件的信息。</span><span class="sxs-lookup"><span data-stu-id="571ac-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="571ac-171">阅读本文以了解有关如何工作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="571ac-171">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="571ac-172">Office 365 管理活动 API 架构</span><span class="sxs-lookup"><span data-stu-id="571ac-172">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="571ac-173">获取[常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)和[office 365 ATP 以及威胁调查和响应架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)的概述，以了解通过 OFFICE 365 管理活动 API 提供的特定类型的数据。</span><span class="sxs-lookup"><span data-stu-id="571ac-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="571ac-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="571ac-174">Next steps</span></span>

- [<span data-ttu-id="571ac-175">了解如何获取空中和查看所需的权限</span><span class="sxs-lookup"><span data-stu-id="571ac-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="571ac-176">了解有关通知的详细信息</span><span class="sxs-lookup"><span data-stu-id="571ac-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="571ac-177">手动查找和调查 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="571ac-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="571ac-178">了解 Microsoft Defender ATP 中的空气</span><span class="sxs-lookup"><span data-stu-id="571ac-178">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="571ac-179">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="571ac-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
