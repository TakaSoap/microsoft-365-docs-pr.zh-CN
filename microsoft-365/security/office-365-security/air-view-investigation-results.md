---
title: 在 Office 365 中查看自动调查的结果
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
description: 在 Office 365 中进行自动调查的过程中和之后，您可以查看结果和主要发现。
ms.openlocfilehash: 104be669dcb6d22cba00974075418e2d14ed629c
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894224"
---
# <a name="details-and-results-of-an-automated-investigation-in-office-365"></a><span data-ttu-id="f45fb-104">Office 365 中的自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="f45fb-104">Details and results of an automated investigation in Office 365</span></span>

<span data-ttu-id="f45fb-105">在[Office 365 高级威胁防护](office-365-atp.md)中进行[自动调查](office-365-air.md)时，有关该调查的详细信息在自动调查过程的过程中和之后都是可用的。</span><span class="sxs-lookup"><span data-stu-id="f45fb-105">When an [automated investigation](office-365-air.md) occurs in [Office 365 Advanced Threat Protection](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="f45fb-106">如果您具有所需的权限，则可以在调查详细信息视图中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-106">If you have the necessary permissions, you can view those details in an investigation details view.</span></span> <span data-ttu-id="f45fb-107">调查详细信息视图为您提供了最新状态，并能够批准任何挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-107">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="f45fb-108">查看调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="f45fb-108">View details of an investigation</span></span>

1. <span data-ttu-id="f45fb-109">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="f45fb-109">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="f45fb-110">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="f45fb-110">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f45fb-111">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f45fb-111">Do one of the following:</span></span>

    - <span data-ttu-id="f45fb-112">转到 "**威胁管理** > **仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="f45fb-112">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="f45fb-113">这将转到[安全仪表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="f45fb-113">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="f45fb-114">您的空中小组件显示在[安全仪表板](security-dashboard.md)的顶部。</span><span class="sxs-lookup"><span data-stu-id="f45fb-114">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="f45fb-115">选择一个小部件，如**调查摘要**。</span><span class="sxs-lookup"><span data-stu-id="f45fb-115">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="f45fb-116">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="f45fb-116">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="f45fb-117">每种方法都将转到调查列表。</span><span class="sxs-lookup"><span data-stu-id="f45fb-117">Either method takes you to a list of investigations.</span></span>

    ![空气的主要调查页面](../../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="f45fb-119">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="f45fb-119">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="f45fb-120">这将打开 "调查详细信息" 页，从视图中的调查图形开始。</span><span class="sxs-lookup"><span data-stu-id="f45fb-120">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![空中调查图形页面](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="f45fb-122">使用各种选项卡了解有关调查的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-122">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="f45fb-123">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="f45fb-123">View details about an alert related to an investigation</span></span>

<span data-ttu-id="f45fb-124">某些类型的警报会触发 Office 365 中的自动调查。</span><span class="sxs-lookup"><span data-stu-id="f45fb-124">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="f45fb-125">若要了解详细信息，请参阅[警报](automated-investigation-response-office.md#alerts)。</span><span class="sxs-lookup"><span data-stu-id="f45fb-125">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="f45fb-126">使用以下过程可查看与自动调查相关联的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-126">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="f45fb-127">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="f45fb-127">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="f45fb-128">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="f45fb-128">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f45fb-129">转到**威胁管理** > **调查**。</span><span class="sxs-lookup"><span data-stu-id="f45fb-129">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="f45fb-130">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="f45fb-130">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="f45fb-131">通过打开调查的详细信息，选择 "**通知**" 选项卡。下面列出了所有触发调查的警报。</span><span class="sxs-lookup"><span data-stu-id="f45fb-131">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="f45fb-132">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="f45fb-132">Select an item in the list.</span></span> <span data-ttu-id="f45fb-133">将打开一个浮出控件，其中包含有关该警报的详细信息以及指向其他信息和操作的链接。</span><span class="sxs-lookup"><span data-stu-id="f45fb-133">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="f45fb-134">查看浮出控件上的信息，根据特定的通知执行操作，如**Resolve**、**隐含**或**通知用户**。</span><span class="sxs-lookup"><span data-stu-id="f45fb-134">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="f45fb-135">**Resolve**等效于关闭通知</span><span class="sxs-lookup"><span data-stu-id="f45fb-135">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="f45fb-136">**禁止**使策略在指定时间段内触发警报</span><span class="sxs-lookup"><span data-stu-id="f45fb-136">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="f45fb-137">**通知用户**启动电子邮件，其中包含已输入的用户电子邮件地址，并允许安全操作团队向这些用户键入邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-137">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="f45fb-138">（这类似于使用[威胁资源管理器](threat-explorer.md)向收件人发送邮件。）</span><span class="sxs-lookup"><span data-stu-id="f45fb-138">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="f45fb-139">如何使用各种选项卡</span><span class="sxs-lookup"><span data-stu-id="f45fb-139">How to use the various tabs</span></span>

<span data-ttu-id="f45fb-140">以下各节将引导您完成 "自动调查" 页面上的各种选项卡，以及如何使用这些信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-140">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="f45fb-141">自动调查页面</span><span class="sxs-lookup"><span data-stu-id="f45fb-141">Automated investigations page</span></span>

<span data-ttu-id="f45fb-142">"自动调查" 页面显示您的组织的调查及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="f45fb-142">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空气的主要调查页面](../../media/air-maininvestigationpage.png) 
  
<span data-ttu-id="f45fb-144">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-144">You can:</span></span>
- <span data-ttu-id="f45fb-145">直接导航到调查（选择**调查 ID**）。</span><span class="sxs-lookup"><span data-stu-id="f45fb-145">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="f45fb-146">应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="f45fb-146">Apply filters.</span></span> <span data-ttu-id="f45fb-147">从**调查类型**、**时间范围**、**状态**或这些情况的组合中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f45fb-147">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="f45fb-148">将数据导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-148">Export the data to a .csv file.</span></span>

<span data-ttu-id="f45fb-149">调查状态指示分析和操作的进度。</span><span class="sxs-lookup"><span data-stu-id="f45fb-149">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="f45fb-150">在调查运行时，状态更改以指示是否发现威胁，以及是否已批准操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-150">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span> 

|<span data-ttu-id="f45fb-151">状态</span><span class="sxs-lookup"><span data-stu-id="f45fb-151">Status</span></span>  |<span data-ttu-id="f45fb-152">含义</span><span class="sxs-lookup"><span data-stu-id="f45fb-152">What it means</span></span>  |
|---------|---------|
|<span data-ttu-id="f45fb-153">即将开始</span><span class="sxs-lookup"><span data-stu-id="f45fb-153">Starting</span></span> | <span data-ttu-id="f45fb-154">调查已排入队列，以便尽快开始</span><span class="sxs-lookup"><span data-stu-id="f45fb-154">The investigation is queued to begin soon</span></span> |
|<span data-ttu-id="f45fb-155">正在运行</span><span class="sxs-lookup"><span data-stu-id="f45fb-155">Running</span></span> | <span data-ttu-id="f45fb-156">调查已开始，正在进行分析</span><span class="sxs-lookup"><span data-stu-id="f45fb-156">The investigation has started and is conducting its analysis</span></span> |
|<span data-ttu-id="f45fb-157">找不到威胁</span><span class="sxs-lookup"><span data-stu-id="f45fb-157">No Threats Found</span></span> | <span data-ttu-id="f45fb-158">调查已完成其分析，未发现任何威胁</span><span class="sxs-lookup"><span data-stu-id="f45fb-158">The investigation has completed its analysis and no threats were found</span></span> |
|<span data-ttu-id="f45fb-159">已由系统终止</span><span class="sxs-lookup"><span data-stu-id="f45fb-159">Terminated By System</span></span> | <span data-ttu-id="f45fb-160">调查未关闭并在7天后过期</span><span class="sxs-lookup"><span data-stu-id="f45fb-160">The investigation was not closed and expired after 7 days</span></span> |
|<span data-ttu-id="f45fb-161">挂起的操作</span><span class="sxs-lookup"><span data-stu-id="f45fb-161">Pending Action</span></span> | <span data-ttu-id="f45fb-162">调查发现了与建议的操作有关的威胁。</span><span class="sxs-lookup"><span data-stu-id="f45fb-162">The investigation found threats with actions recommended.</span></span>  <span data-ttu-id="f45fb-163">调查在发现最初的威胁和推荐的操作后继续运行，因此您应该在批准操作之前检查日志，以查看分析器是否仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="f45fb-163">The investigation continues running after it's found initial threats and recommended actions, so you should check the log before approving actions to see if analyzers are still in-progress.</span></span> |
|<span data-ttu-id="f45fb-164">发现威胁</span><span class="sxs-lookup"><span data-stu-id="f45fb-164">Threats Found</span></span> | <span data-ttu-id="f45fb-165">调查发现威胁，但威胁没有在空中可用的操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-165">The investigation found threats, but the threats do not have actions available within AIR.</span></span>  <span data-ttu-id="f45fb-166">这些是无方向无线操作的用户操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-166">These are user actions where there is no direction AIR action yet.</span></span> |
|<span data-ttu-id="f45fb-167">已修正</span><span class="sxs-lookup"><span data-stu-id="f45fb-167">Remediated</span></span> | <span data-ttu-id="f45fb-168">调查已完成且已完全修正（已批准所有操作）</span><span class="sxs-lookup"><span data-stu-id="f45fb-168">The investigation finished and was fully remediated (all actions were approved)</span></span> |
|<span data-ttu-id="f45fb-169">部分修正</span><span class="sxs-lookup"><span data-stu-id="f45fb-169">Partially Remediated</span></span> | <span data-ttu-id="f45fb-170">调查已完成，某些建议的操作已获得批准</span><span class="sxs-lookup"><span data-stu-id="f45fb-170">The investigation finished and some of the recommended actions were approved</span></span> |
|<span data-ttu-id="f45fb-171">已由用户终止</span><span class="sxs-lookup"><span data-stu-id="f45fb-171">Terminated By User</span></span> | <span data-ttu-id="f45fb-172">管理员终止了调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-172">An admin terminated the investigation</span></span> |
|<span data-ttu-id="f45fb-173">已失败</span><span class="sxs-lookup"><span data-stu-id="f45fb-173">Failed</span></span> | <span data-ttu-id="f45fb-174">调查过程中发生错误，阻止它达到威胁的结论</span><span class="sxs-lookup"><span data-stu-id="f45fb-174">An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span> |
|<span data-ttu-id="f45fb-175">按限制排队</span><span class="sxs-lookup"><span data-stu-id="f45fb-175">Queued By Throttling</span></span> | <span data-ttu-id="f45fb-176">由于系统处理限制，调查正在等待分析（以保护服务性能）</span><span class="sxs-lookup"><span data-stu-id="f45fb-176">The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span> |
|<span data-ttu-id="f45fb-177">已通过限制终止</span><span class="sxs-lookup"><span data-stu-id="f45fb-177">Terminated By Throttling</span></span> | <span data-ttu-id="f45fb-178">由于调查卷和系统处理限制，无法在足够的时间内完成调查。</span><span class="sxs-lookup"><span data-stu-id="f45fb-178">The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="f45fb-179">您可以通过在资源管理器中选择电子邮件并选择调查操作来 retrigger 调查。</span><span class="sxs-lookup"><span data-stu-id="f45fb-179">You can retrigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span> |

### <a name="investigation-graph"></a><span data-ttu-id="f45fb-180">调查图形</span><span class="sxs-lookup"><span data-stu-id="f45fb-180">Investigation graph</span></span>

<span data-ttu-id="f45fb-181">当您打开特定调查时，您将看到 "调查图形" 页。</span><span class="sxs-lookup"><span data-stu-id="f45fb-181">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="f45fb-182">此页面显示所有不同的实体：电子邮件、用户（及其活动）以及自动调查为触发的警报一部分的设备。</span><span class="sxs-lookup"><span data-stu-id="f45fb-182">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空中调查图形页面](../../media/air-investigationgraphpage.png)

<span data-ttu-id="f45fb-184">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-184">You can:</span></span>
- <span data-ttu-id="f45fb-185">获取当前调查的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-185">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="f45fb-186">查看调查持续时间的摘要。</span><span class="sxs-lookup"><span data-stu-id="f45fb-186">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="f45fb-187">在可视化中选择一个节点以查看该节点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-187">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="f45fb-188">在顶部选择一个选项卡以查看该选项卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-188">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="f45fb-189">通知调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-189">Alert investigation</span></span>

<span data-ttu-id="f45fb-190">在调查的 "**通知**" 选项卡上，您可以查看与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="f45fb-190">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="f45fb-191">详细信息包括触发调查的警报以及与调查相关的其他关联警报（如有风险的登录、DLP 策略冲突等）。</span><span class="sxs-lookup"><span data-stu-id="f45fb-191">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, DLP policy violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="f45fb-192">在此页面中，安全分析员还可以查看各个通知的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="f45fb-192">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空气警报页面](../../media/air-investigationalertspage.png)

<span data-ttu-id="f45fb-194">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-194">You can:</span></span>
- <span data-ttu-id="f45fb-195">获取当前触发警报和任何关联警报的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-195">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="f45fb-196">在列表中选择一个警报，打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="f45fb-196">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="f45fb-197">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-197">Email investigation</span></span>

<span data-ttu-id="f45fb-198">在调查的 "**电子邮件**" 选项卡上，您可以查看原始电子邮件和在调查过程中标识的类似电子邮件的群集。</span><span class="sxs-lookup"><span data-stu-id="f45fb-198">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> 

<span data-ttu-id="f45fb-199">由于组织中的用户发送和接收的电子邮件量巨大，以及电子邮件通信和攻击的多用户性质，因此</span><span class="sxs-lookup"><span data-stu-id="f45fb-199">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the process of</span></span> 
- <span data-ttu-id="f45fb-200">根据邮件头、正文、URL 和附件中的类似属性对电子邮件进行群集化;</span><span class="sxs-lookup"><span data-stu-id="f45fb-200">clustering email messages based on similar attributes from a message header, body, URL, and attachments;</span></span> 
- <span data-ttu-id="f45fb-201">将恶意电子邮件与优质电子邮件分开;并</span><span class="sxs-lookup"><span data-stu-id="f45fb-201">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="f45fb-202">对恶意电子邮件采取操作</span><span class="sxs-lookup"><span data-stu-id="f45fb-202">taking action on malicious email messages</span></span> 

<span data-ttu-id="f45fb-203">可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="f45fb-203">can take significant time.</span></span> <span data-ttu-id="f45fb-204">现在，AIR 可以自动执行此过程，从而节省了贵组织的安全团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="f45fb-204">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="f45fb-205">电子邮件分析步骤中可能会标识两种不同类型的电子邮件群集：相似性群集和指示器群集。</span><span class="sxs-lookup"><span data-stu-id="f45fb-205">Two different types of email clusters may be identified during the email analysis step: similarity clusters and indicator clusters.</span></span> 
- <span data-ttu-id="f45fb-206">相似性群集是通过搜寻具有类似发件人和内容属性的电子邮件来标识的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-206">Similarity clusters are email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="f45fb-207">根据原始检测结果评估这些群集中的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="f45fb-207">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="f45fb-208">包含足够恶意电子邮件检测的电子邮件群集被视为恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-208">Email clusters that contain enough malicious email detections are considered malicious.</span></span>
- <span data-ttu-id="f45fb-209">指示器群集是通过搜寻来自原始电子邮件的相同指示器实体（文件哈希或 URL）标识的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-209">Indicator clusters are email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="f45fb-210">将原始文件/URL 实体标识为恶意时，AIR 会将指示器判定为包含该实体的电子邮件的整个群集。</span><span class="sxs-lookup"><span data-stu-id="f45fb-210">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="f45fb-211">被标识为恶意软件的文件意味着包含该文件的电子邮件群集将被视为恶意软件电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-211">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>

<span data-ttu-id="f45fb-212">群集的目标是查找和查找与攻击或市场活动中的同一发件人发送的其他相关电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-212">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="f45fb-213">在某些情况下，合法的电子邮件可能会触发调查（例如，用户报告营销电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="f45fb-213">In some cases, legitimate email may trigger an investigation (e.g. a user reports a marketing email).</span></span>  <span data-ttu-id="f45fb-214">在这些方案中，电子邮件群集应确定电子邮件群集不是恶意的–如果它相应地执行此操作，则不会表示威胁，也**不**会建议删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-214">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat nor will it recommend email removal.</span></span>

<span data-ttu-id="f45fb-215">"**电子邮件**" 选项卡还显示与调查相关的电子邮件项目，例如用户报告的电子邮件详细信息、报告的原始电子邮件、电子邮件 zapped （由于恶意软件/网络钓鱼诈骗等）。</span><span class="sxs-lookup"><span data-stu-id="f45fb-215">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="f45fb-216">"电子邮件" 选项卡上标识的电子邮件计数当前代表 "**电子邮件**" 选项卡上显示的所有电子邮件的总数。由于电子邮件存在于多个群集中，因此标识的电子邮件的实际总数（并受修正操作影响）是所有群集和原始收件人的电子邮件中显示的唯一电子邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="f45fb-216">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="f45fb-217">由于每个收件人的安全 verdicts、操作和传递位置各不相同，因此每个收件人的资源管理器和空中计数电子邮件都会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f45fb-217">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations vary on a per recipient basis.</span></span> <span data-ttu-id="f45fb-218">因此，发送给三个用户的原始电子邮件总共计为三封电子邮件，而不是一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-218">Thus an original email sent to three users count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="f45fb-219">注释可能会出现两次或多次计数电子邮件的情况，因为电子邮件可能会对其进行多个操作，并且在发生所有操作后，可能会有多个电子邮件副本。</span><span class="sxs-lookup"><span data-stu-id="f45fb-219">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="f45fb-220">例如，在传递时检测到的恶意软件电子邮件可能会导致阻止（隔离）的电子邮件和替换的电子邮件（受警告文件替换的威胁文件，然后传递到用户的邮箱）。</span><span class="sxs-lookup"><span data-stu-id="f45fb-220">For example, a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="f45fb-221">由于系统中的电子邮件有两个副本，这两个副本可能会在群集计数中进行计数。</span><span class="sxs-lookup"><span data-stu-id="f45fb-221">Since there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span> 

<span data-ttu-id="f45fb-222">电子邮件计数是在调查时计算的，当您打开调查 flyouts 时（基于基础查询），一些计数也会进行重新计算。</span><span class="sxs-lookup"><span data-stu-id="f45fb-222">Email counts are calculated at the time of the investigation and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="f45fb-223">"电子邮件" 选项卡上显示的电子邮件群集的电子邮件数量和在 "群集" 浮出控件中显示的电子邮件数量值在调查时进行计算且不会发生变化。</span><span class="sxs-lookup"><span data-stu-id="f45fb-223">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation and do not change.</span></span> <span data-ttu-id="f45fb-224">在电子邮件群集浮出控件的 "电子邮件" 选项卡底部显示的电子邮件计数，资源管理器中显示的电子邮件计数反映在调查的初始分析之后收到的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-224">The email count shown at the bottom of the email tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="f45fb-225">因此，显示原始数量10封电子邮件的电子邮件群集将在调查分析阶段和管理员审查调查之间到达5封以上的电子邮件列表中显示全部15封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-225">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span>  <span data-ttu-id="f45fb-226">与资源管理器查询相比，旧调查可能会开始更大的计数，因为在30天后 ATP P2 将到期数据，而付费许可证则为30天。</span><span class="sxs-lookup"><span data-stu-id="f45fb-226">Likewise old investigations may start having bigger counts than Explorer queries show, since ATP P2 expires data after 7 days for trials and 30 days for paid licenses.</span></span>  <span data-ttu-id="f45fb-227">在不同视图中显示计数历史和当前计数已完成，以指示调查时的电子邮件影响和当前影响，直到运行补救时间为止。</span><span class="sxs-lookup"><span data-stu-id="f45fb-227">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="f45fb-228">例如，请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="f45fb-228">As an example, consider the following scenario.</span></span> <span data-ttu-id="f45fb-229">三封电子邮件的第一个群集被认为是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="f45fb-229">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="f45fb-230">找到具有相同 IP 和主题的类似邮件的另一个群集，并被视为恶意邮件，因为在初始检测过程中将其部分标识为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="f45fb-230">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![空中电子邮件调查页面](../../media/air-investigationemailpage.png)

<span data-ttu-id="f45fb-232">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-232">You can:</span></span>
- <span data-ttu-id="f45fb-233">获取当前群集结果和发现的威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-233">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="f45fb-234">单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。</span><span class="sxs-lookup"><span data-stu-id="f45fb-234">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="f45fb-235">单击 "电子邮件群集详细信息" 选项卡顶部的 "在资源管理器中打开" 链接进一步调查电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="f45fb-235">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![使用浮出控件详细信息的航空调查电子邮件](../../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> <span data-ttu-id="f45fb-237">在电子邮件上下文中，您可能会在调查过程中看到一个卷异常威胁曲面。</span><span class="sxs-lookup"><span data-stu-id="f45fb-237">In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="f45fb-238">卷异常表明调查事件时间与之前的时间框架相比，与调查事件的类似电子邮件中的峰值。</span><span class="sxs-lookup"><span data-stu-id="f45fb-238">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="f45fb-239">这种具有类似特征（例如，subject 和发件人域、正文相似性和发件人 IP）的电子邮件通信的峰值是电子邮件宣传活动或攻击的典型启动。</span><span class="sxs-lookup"><span data-stu-id="f45fb-239">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="f45fb-240">但是，批量、垃圾邮件和合法电子邮件活动通常共享这些特征。</span><span class="sxs-lookup"><span data-stu-id="f45fb-240">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="f45fb-241">由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比，大量异常会带来潜在的威胁，因此可能会降低严重程度。</span><span class="sxs-lookup"><span data-stu-id="f45fb-241">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="f45fb-242">用户调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-242">User investigation</span></span>

<span data-ttu-id="f45fb-243">在 "**用户**" 选项卡上，您可以看到标识为调查的一部分的所有用户。</span><span class="sxs-lookup"><span data-stu-id="f45fb-243">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="f45fb-244">当存在事件或指示这些用户帐户可能受到影响或受到威胁时，用户帐户将出现在调查中。</span><span class="sxs-lookup"><span data-stu-id="f45fb-244">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="f45fb-245">例如，在下图中，空气根据创建的新收件箱规则确定了安全指标和异常情况。</span><span class="sxs-lookup"><span data-stu-id="f45fb-245">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="f45fb-246">可通过此选项卡中的详细视图查看调查的其他详细信息（证据）。损坏的迹象和异常也可能包含来自[Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。</span><span class="sxs-lookup"><span data-stu-id="f45fb-246">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空中调查用户页](../../media/air-investigationuserspage.png)

<span data-ttu-id="f45fb-248">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-248">You can:</span></span>
- <span data-ttu-id="f45fb-249">获取已确定的用户结果和发现的风险的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-249">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="f45fb-250">选择用户以打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="f45fb-250">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="f45fb-251">机器调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-251">Machine investigation</span></span>

<span data-ttu-id="f45fb-252">在 "**计算机**" 选项卡上，您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="f45fb-252">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空中调查计算机页面](../../media/air-investigationmachinepage.png)

<span data-ttu-id="f45fb-254">作为一些行动手册的一部分，空中将电子邮件威胁与设备（例如 Zapped 恶意软件）相关联。</span><span class="sxs-lookup"><span data-stu-id="f45fb-254">As part of some playbooks, AIR correlates email threats to devices (e.g. Zapped malware).</span></span> <span data-ttu-id="f45fb-255">例如，调查会将恶意文件哈希传递到[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)以进行调查。</span><span class="sxs-lookup"><span data-stu-id="f45fb-255">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="f45fb-256">这样，就可以为您的用户自动调查相关的计算机，以帮助确保在云中和终结点上解决威胁。</span><span class="sxs-lookup"><span data-stu-id="f45fb-256">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="f45fb-257">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-257">You can:</span></span>
- <span data-ttu-id="f45fb-258">获取发现的当前计算机和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-258">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="f45fb-259">选择一台计算机以打开在 Microsoft Defender 安全中心的相关[Microsoft DEFENDER ATP 调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)中的视图。</span><span class="sxs-lookup"><span data-stu-id="f45fb-259">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="f45fb-260">实体调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-260">Entity investigation</span></span>

<span data-ttu-id="f45fb-261">在 "**实体**" 选项卡上，您可以看到在调查过程中标识和分析的实体。</span><span class="sxs-lookup"><span data-stu-id="f45fb-261">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span> 

<span data-ttu-id="f45fb-262">在这里，您可以查看调查的实体和实体类型的详细信息，例如电子邮件、群集、IP 地址、用户等。</span><span class="sxs-lookup"><span data-stu-id="f45fb-262">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="f45fb-263">您还可以查看已分析的实体数以及与每个实体相关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="f45fb-263">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

!["航空调查实体" 页](../../media/air-investigationentitiespage.png)

<span data-ttu-id="f45fb-265">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-265">You can:</span></span>
- <span data-ttu-id="f45fb-266">获取发现的调查实体和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-266">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="f45fb-267">选择一个实体以打开显示相关实体详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="f45fb-267">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中调查实体详细信息](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="f45fb-269">行动手册日志</span><span class="sxs-lookup"><span data-stu-id="f45fb-269">Playbook log</span></span>

<span data-ttu-id="f45fb-270">在 "**日志**" 选项卡上，您可以查看调查过程中的所有操作手册步骤。</span><span class="sxs-lookup"><span data-stu-id="f45fb-270">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="f45fb-271">该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有分析器和操作的完整清单。</span><span class="sxs-lookup"><span data-stu-id="f45fb-271">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="f45fb-272">它提供了所执行的所有步骤的清晰视图，包括操作本身、说明以及实际 "开始到完成" 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f45fb-272">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![航空调查日志页](../../media/air-investigationlogpage.png)

<span data-ttu-id="f45fb-274">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-274">You can:</span></span>
- <span data-ttu-id="f45fb-275">获取有关执行操作手册步骤的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-275">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="f45fb-276">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-276">Export the results to a CSV file.</span></span>
- <span data-ttu-id="f45fb-277">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="f45fb-277">Filter the view.</span></span>

|<span data-ttu-id="f45fb-278">工具</span><span class="sxs-lookup"><span data-stu-id="f45fb-278">Analyzer</span></span> | <span data-ttu-id="f45fb-279">说明</span><span class="sxs-lookup"><span data-stu-id="f45fb-279">Description</span></span> |
|-----|-----|
|<span data-ttu-id="f45fb-280">DLP 违规调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-280">DLP violations investigation</span></span> |<span data-ttu-id="f45fb-281">调查[Office 365 数据丢失防护](../../compliance/data-loss-prevention-policies.md)（DLP）检测到的任何冲突</span><span class="sxs-lookup"><span data-stu-id="f45fb-281">Investigate any violations detected by [Office 365 Data Loss Prevention](../../compliance/data-loss-prevention-policies.md) (DLP)</span></span> |
|<span data-ttu-id="f45fb-282">电子邮件指示器提取</span><span class="sxs-lookup"><span data-stu-id="f45fb-282">Email indicators extraction</span></span> |<span data-ttu-id="f45fb-283">从要调查的电子邮件的标题、正文和内容中提取指示器</span><span class="sxs-lookup"><span data-stu-id="f45fb-283">Extract indicators from the header, body, and content of an email message for investigation</span></span> |
|<span data-ttu-id="f45fb-284">文件哈希信誉</span><span class="sxs-lookup"><span data-stu-id="f45fb-284">File Hash Reputation</span></span> |<span data-ttu-id="f45fb-285">根据组织中的用户和计算机的文件哈希值检测异常</span><span class="sxs-lookup"><span data-stu-id="f45fb-285">Detect anomalies based on file hashes for users and machines in your organization</span></span> |
|<span data-ttu-id="f45fb-286">邮件群集标识</span><span class="sxs-lookup"><span data-stu-id="f45fb-286">Mail cluster identification</span></span> |<span data-ttu-id="f45fb-287">基于标头、正文、内容和 Url 的电子邮件群集分析</span><span class="sxs-lookup"><span data-stu-id="f45fb-287">Email cluster analysis based on header, body, content, and URLs</span></span> |
|<span data-ttu-id="f45fb-288">邮件群集卷分析</span><span class="sxs-lookup"><span data-stu-id="f45fb-288">Mail cluster volume analysis</span></span> |<span data-ttu-id="f45fb-289">基于出站邮件流卷模式的电子邮件群集分析</span><span class="sxs-lookup"><span data-stu-id="f45fb-289">Email cluster analysis based on outbound mail flow volume patterns</span></span> |
|<span data-ttu-id="f45fb-290">邮件委派调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-290">Mail delegation investigation</span></span> |<span data-ttu-id="f45fb-291">调查与此调查相关的用户邮箱的邮件委派访问权限</span><span class="sxs-lookup"><span data-stu-id="f45fb-291">Investigate mail delegation access for user mailboxes related to this investigation</span></span> |
|<span data-ttu-id="f45fb-292">邮件转发规则调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-292">Mail forwarding rules investigation</span></span> |<span data-ttu-id="f45fb-293">调查与此调查相关的用户邮箱的任何邮件转发规则</span><span class="sxs-lookup"><span data-stu-id="f45fb-293">Investigate any mail forwarding rules for user mailboxes related to this investigation</span></span> |
|<span data-ttu-id="f45fb-294">检测到未命中的恶意软件</span><span class="sxs-lookup"><span data-stu-id="f45fb-294">Missed malware detected</span></span> |<span data-ttu-id="f45fb-295">检测在组织中向用户邮箱发送的未命中的恶意软件</span><span class="sxs-lookup"><span data-stu-id="f45fb-295">Detect missed malware delivered to user's mailbox in your organization</span></span> |
|<span data-ttu-id="f45fb-296">按需沙箱</span><span class="sxs-lookup"><span data-stu-id="f45fb-296">On-demand detonation</span></span> |<span data-ttu-id="f45fb-297">对电子邮件、附件和 Url 触发按需沙箱</span><span class="sxs-lookup"><span data-stu-id="f45fb-297">On-demand detonation triggered for email messages, attachments, and URLs</span></span> |
|<span data-ttu-id="f45fb-298">出站邮件异常情况调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-298">Outbound mail anomaly investigation</span></span> |<span data-ttu-id="f45fb-299">根据历史邮件流为组织中的用户发送模式来检测异常情况</span><span class="sxs-lookup"><span data-stu-id="f45fb-299">Detect anomalies based on historical mail flow sending patterns for users in your organization</span></span> |
|<span data-ttu-id="f45fb-300">出站恶意软件和垃圾邮件异常调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-300">Outbound malware and spam anomaly investigation</span></span> |<span data-ttu-id="f45fb-301">检测来自组织中用户的组织内部和出站恶意软件、网络钓鱼诈骗或垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="f45fb-301">Detect intra-org and outbound malware, phish, or spam originating from users in your organization</span></span> |
|<span data-ttu-id="f45fb-302">发件人域调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-302">Sender domain investigation</span></span> |<span data-ttu-id="f45fb-303">根据需要检查[Microsoft 智能安全图形](https://www.microsoft.com/security/operations/intelligence)和外部威胁智能源中的域信誉</span><span class="sxs-lookup"><span data-stu-id="f45fb-303">On-demand check of domain reputation from the [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) and external threat intelligence sources</span></span> |
|<span data-ttu-id="f45fb-304">发件人 IP 调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-304">Sender IP investigation</span></span> | <span data-ttu-id="f45fb-305">根据需要检查[Microsoft 智能安全图](https://www.microsoft.com/security/operations/intelligence)和外部威胁智能源的 IP 信誉</span><span class="sxs-lookup"><span data-stu-id="f45fb-305">On-demand check of IP reputation from the [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) and external threat intelligence sources</span></span> |
|<span data-ttu-id="f45fb-306">URL 单击调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-306">URL clicks investigation</span></span> | <span data-ttu-id="f45fb-307">调查受[Office 365 ATP 安全链接](atp-safe-links.md)保护的用户对组织的点击率</span><span class="sxs-lookup"><span data-stu-id="f45fb-307">Investigate clicks  from users protected by [Office 365 ATP Safe Links](atp-safe-links.md) in your organization</span></span> |
|<span data-ttu-id="f45fb-308">URL 信誉调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-308">URL reputation investigation</span></span> |<span data-ttu-id="f45fb-309">对来自[Microsoft 智能安全图形](https://www.microsoft.com/security/operations/intelligence)和外部威胁智能源的 URL 信誉的按需检查</span><span class="sxs-lookup"><span data-stu-id="f45fb-309">On-demand check on URL reputation from the [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) and external threat intelligence sources</span></span> |
|<span data-ttu-id="f45fb-310">用户活动调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-310">User activity investigation</span></span> |<span data-ttu-id="f45fb-311">分析[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)中的用户活动异常</span><span class="sxs-lookup"><span data-stu-id="f45fb-311">Analyze user activity anomalies in [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</span></span> |
|<span data-ttu-id="f45fb-312">用户报告的电子邮件指示器提取</span><span class="sxs-lookup"><span data-stu-id="f45fb-312">User-reported emails indicators extraction</span></span> |<span data-ttu-id="f45fb-313">从标头、正文和[用户报告的电子邮件](enable-the-report-message-add-in.md)的内容中提取指示器以供调查</span><span class="sxs-lookup"><span data-stu-id="f45fb-313">Extract indicators from the header, body, and content of [user-reported email](enable-the-report-message-add-in.md) for investigation</span></span> |

### <a name="recommended-actions"></a><span data-ttu-id="f45fb-314">建议的操作</span><span class="sxs-lookup"><span data-stu-id="f45fb-314">Recommended actions</span></span>

<span data-ttu-id="f45fb-315">在 "**操作**" 选项卡上，您可以查看在调查完成后建议用于修正的所有操作手册操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-315">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="f45fb-316">操作会捕获 Microsoft 建议在调查结束时执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="f45fb-316">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="f45fb-317">您可以通过选择一个或多个操作来采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="f45fb-317">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="f45fb-318">单击 "**批准**" 可开始进行修正。</span><span class="sxs-lookup"><span data-stu-id="f45fb-318">Clicking **Approve** allows remediation to begin.</span></span> <span data-ttu-id="f45fb-319">（需要适当的权限-需要 "搜索和清除" 角色才能从资源管理器和 AIR 运行操作）。</span><span class="sxs-lookup"><span data-stu-id="f45fb-319">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="f45fb-320">例如，安全读者可以查看操作但不能批准。</span><span class="sxs-lookup"><span data-stu-id="f45fb-320">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="f45fb-321">注意：无需批准每个操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-321">Note: You do not have to approve every action.</span></span> <span data-ttu-id="f45fb-322">如果您不同意建议的操作，或者您的组织未选择特定类型的操作，则可以选择**拒绝**这些操作，也可以仅忽略它们，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-322">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="f45fb-323">通过审核和/或拒绝所有操作，可以完全关闭调查（状态变为已修正），同时保留某些操作不完整将导致调查状态更改为 "部分修正" 状态。</span><span class="sxs-lookup"><span data-stu-id="f45fb-323">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![航空调查操作页](../../media/air-investigationactionspage.png)

<span data-ttu-id="f45fb-325">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f45fb-325">You can:</span></span>
- <span data-ttu-id="f45fb-326">获取对操作手册建议的操作的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f45fb-326">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="f45fb-327">选择一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-327">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="f45fb-328">使用注释批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="f45fb-328">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="f45fb-329">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f45fb-329">Export the results to a CSV file.</span></span>
- <span data-ttu-id="f45fb-330">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="f45fb-330">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f45fb-331">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f45fb-331">Next steps</span></span>

- [<span data-ttu-id="f45fb-332">查看和批准挂起的操作</span><span class="sxs-lookup"><span data-stu-id="f45fb-332">Review and approve pending actions</span></span>](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions)

- [<span data-ttu-id="f45fb-333">了解 Microsoft 威胁防护中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="f45fb-333">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
