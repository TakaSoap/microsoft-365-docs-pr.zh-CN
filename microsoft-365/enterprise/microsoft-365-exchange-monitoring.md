---
title: 用于 Microsoft 365 的 Exchange Online 监视
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 使用 Exchange Online 监视获取有关 Microsoft 365 中电子邮件事件或通报信息。
ms.openlocfilehash: 53dc7f990f57fd8d4da68bd424947676cbf0e85d
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572851"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="2bd3c-103">用于 Microsoft 365 的 Exchange Online 监视</span><span class="sxs-lookup"><span data-stu-id="2bd3c-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="2bd3c-104">可使用 Microsoft 365 管理中心中的 Exchange Online 监视来监视组织的 Microsoft 365 订阅的 Exchange 服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="2bd3c-105">Exchange Online 监视提供了有关在以下类别中收集的事件和通报的信息：</span><span class="sxs-lookup"><span data-stu-id="2bd3c-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="2bd3c-106">**基础结构**：在 Microsoft 所拥有的用于提供定期更新和解决问题的 Microsoft 365 基础结构中检测到了问题。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="2bd3c-107">例如，由于 Exchange 或其他 Microsoft 365 云基础结构的问题，用户无法访问 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="2bd3c-108">**第三方基础结构**：在组织已取得相关性的第三方基础结构中检测到问题，并需要组织提供的措施来解决问题。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="2bd3c-109">例如，用户身份验证事务受到阻止用户连接到 Exchange Online 的第三方安全令牌服务 (STS) 提供程序的限制。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="2bd3c-110">**客户基础结构**：在组织基础结构中检测到问题，并要求组织执行操作以解决问题。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="2bd3c-111">例如，用户无法访问 Exchange Online，因为证书已过期，他们无法获取由组织托管的 STS 提供商提供的身份验证令牌。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="2bd3c-112">以下为 Microsoft 365 管理中心中的 **服务运行状况** 页面的示例， 可通过 **“运行状况” > “服务运行状况”** 查看。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Microsoft 365 管理中心中的“服务运行状况”页面](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="2bd3c-114">**状态** 列的值表示服务状态是否正常，或基于 Microsoft 维护的云服务是否存在建议或事件。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="2bd3c-115">**你的组织和第三方问题** 的值表示你的组织基础结构或第三方软件通过 Exchange Online 对用户的服务运行状况体验的影响。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="2bd3c-116">建议或事件需要 *你的* 操作才能解决。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="2bd3c-117">下面是 Microsoft 365 管理中心中的 **Exchange Online** 监视页面的示例， 可通过 **“运行状况” > “服务运行状况” > “Exchange Online”** 查看。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Microsoft 365 管理中心中的 Exchange Online 监视页面](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="2bd3c-119">使用 **Exchange Online** 监视页面，可查看 Exchange Online 服务是否运行正常，以及是否存在任何关联的事件或通报。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="2bd3c-120">借助 Exchange Online 监视，可查看特定电子邮件方案的服务运行状况，查看准实时信号，确定方案产生的影响。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="2bd3c-121">要求</span><span class="sxs-lookup"><span data-stu-id="2bd3c-121">Requirements</span></span>

<span data-ttu-id="2bd3c-122">对于满足这些要求的客户，将启用此预览版：</span><span class="sxs-lookup"><span data-stu-id="2bd3c-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="2bd3c-123">你的组织必须从以下产品之一或其组合中获取至少 10,000 的许可证计数：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-123">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="2bd3c-124">例如，你的组织可以拥有 3,000 个 Office 365 E3 许可证，8,500 个 Microsoft 365 E5，即总计拥有 11,500 个合格产品许可证。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-124">For example, your organization can have 3,000 Office 365 E3 licenses and 8,500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="2bd3c-125">你的组织需要拥有至少50 个 Exchange Online 月活跃用户。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="2bd3c-126">借助 Exchange 监视，可基于电子邮件阅读活动查看以下电子邮件客户端的运行状况：</span><span class="sxs-lookup"><span data-stu-id="2bd3c-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="2bd3c-127">Outlook 桌面版</span><span class="sxs-lookup"><span data-stu-id="2bd3c-127">Outlook Desktop</span></span>
- <span data-ttu-id="2bd3c-128">Web 上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="2bd3c-128">Outlook on the Web</span></span>
- <span data-ttu-id="2bd3c-129">iOS 版和 Android 版的本机邮件客户端</span><span class="sxs-lookup"><span data-stu-id="2bd3c-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="2bd3c-130">用于 iOS 和 Android 的 Outlook 移动应用</span><span class="sxs-lookup"><span data-stu-id="2bd3c-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="2bd3c-131">Outlook Mac 客户端</span><span class="sxs-lookup"><span data-stu-id="2bd3c-131">Outlook Mac client</span></span>

<span data-ttu-id="2bd3c-132">通过这些客户端，你可以根据阅读电子邮件的用户以及仪表板中的事件数和建议，查看最近 30 分钟内的活动用户数。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="2bd3c-133">此数据将与前一周的相同间隔进行比较，以查看是否存在问题。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="2bd3c-134">活跃用户计数由单个活动测量，例如，用户阅读电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="2bd3c-135">该帐户仅适用于最近 30 分钟的活动。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="2bd3c-136">你也可以在以下情况下监视 Exchange 运行状况：</span><span class="sxs-lookup"><span data-stu-id="2bd3c-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="2bd3c-137">**邮件流**：邮件连接到 Microsoft 365 网络后，在不延迟的情况下成功传送到邮箱的邮件数。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="2bd3c-138">**基本身份验证和新式验证**：Exchange Online 服务中成功验证的用户数。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![用于在邮件传递中监视 Exchange 运行状况的示例](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="2bd3c-140">在所有这些情况下，获得的是主仪表板中的最后 30 分钟的关键数量。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="2bd3c-141">上述每种情况的详细视图将显示与前一周相比，在 30 分钟聚合的情况下，七天内的准实时趋势。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="2bd3c-142">向我们发送反馈</span><span class="sxs-lookup"><span data-stu-id="2bd3c-142">Send us feedback</span></span>

<span data-ttu-id="2bd3c-143">可以通过下列两种方式提供反馈：</span><span class="sxs-lookup"><span data-stu-id="2bd3c-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="2bd3c-144">使用 **“提供反馈”** 选项，可在 Microsoft 365 管理中心的每个页面上提供反馈。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="2bd3c-145">使用 **这篇文章是否有用？** 链接提交特定事件或通报的反馈。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![这篇文章是否有用？](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="2bd3c-148">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="2bd3c-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2bd3c-149">1. 为什么在 Microsoft 365 管理中心中的“运行状况”下看不到“Exchange Online 监视”？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="2bd3c-150">首先，请确保已在 Microsoft 365 管理中心 **主页** 页面上启用了新管理中心。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="2bd3c-151">然后，请确保满足以下两项要求：</span><span class="sxs-lookup"><span data-stu-id="2bd3c-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="2bd3c-152">你的组织必须从以下产品之一或其组合中获取至少 10,000 的许可证计数：Office 365 E3、Microsoft 365 E3、Office 365 E5、Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-152">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="2bd3c-153">你的组织需要拥有至少50 个 Exchange Online 月活跃用户。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="2bd3c-154">如果你的组织的许可证计数低于 10,000 个用户，且月活跃用户低于 50 个，则在满足这些要求之前，不会启用 Exchange Online 监视。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-154">If the license count for your organization goes below 10,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="2bd3c-155">2. 仪表板中每个客户端的活动用户账户计数似乎很低。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="2bd3c-156">向用户分配了大量活动的许可证。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="2bd3c-157">这意味着什么？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-157">What does this mean?</span></span> 

<span data-ttu-id="2bd3c-158">监视中显示的活跃用户计数是基于 30 分钟的窗口，其中用户执行了功能中调用的活动。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="2bd3c-159">这不应该与使用数字相混淆。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="2bd3c-160">若要查看使用数字，请使用 Microsoft 365 管理中心中的活动报告（**“报告” > “使用情况”**）。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="2bd3c-161">3. 其他服务（如 Teams 和 SharePoint）是否有其他监视方案？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="2bd3c-162">Microsoft 在 Microsoft 365 管理中心中的服务运行状况仪表板内直接集成了这种体验。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2bd3c-163">这将使 Microsoft 有机会扩展其他服务的监视方案，在有新闻可供共享时，将通知这些情况。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="2bd3c-164">4. 此体验的总体可用性计划是什么？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="2bd3c-165">Microsoft 已直接在 Microsoft 365 管理中心中的 **服务运行状况** 仪表板上集成了 Exchange Online 监视。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="2bd3c-166">通过这项全新的集成体验，Microsoft 计划收集你的反馈，然后定义我们的总体可用性计划。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="2bd3c-167">5. 这是免费的（含）还是付费的（额外）功能？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="2bd3c-168">此功能适用于公共预览版，并且仅适用于满足问题 1 的要求的客户。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="2bd3c-169">6. 如何提供反馈？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="2bd3c-170">有关一般反馈，请使用 **Exchange Online** 监视页右下角的 **提供反馈** 图标。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="2bd3c-171">有关事件或通报的反馈，请使用 **这篇文章是否有用？** 链接。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="2bd3c-172">7. 在哪里处理这些用于显示活动趋势的方案的数据？</span><span class="sxs-lookup"><span data-stu-id="2bd3c-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="2bd3c-173">在 Exchange Online 服务中处理这些数据。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-173">The data is instrumented in the Exchange Online service.</span></span> <span data-ttu-id="2bd3c-174">如果在请求到达 Exchange Online 之前出现错误，或 Exchange Online 出现错误，将会看到活动信号下降。</span><span class="sxs-lookup"><span data-stu-id="2bd3c-174">If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

