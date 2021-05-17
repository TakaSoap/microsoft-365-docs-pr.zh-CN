---
title: 攻击模拟培训部署注意事项和常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解有关部署注意事项和有关攻击模拟和 Microsoft Defender for Microsoft 365 E5 For Office 365 Plan 2 组织中培训的常见问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203214"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a><span data-ttu-id="7434a-103">攻击模拟培训部署注意事项和常见问题解答</span><span class="sxs-lookup"><span data-stu-id="7434a-103">Attack simulation training deployment considerations and FAQ</span></span>

<span data-ttu-id="7434a-104">攻击模拟培训现已 [普遍可用](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)。</span><span class="sxs-lookup"><span data-stu-id="7434a-104">Attack simulation training is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291).</span></span> <span data-ttu-id="7434a-105">攻击模拟培训使 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织能够度量和管理社交工程风险，通过允许创建和管理由实际、已取消武器化网络钓鱼有效负载的网络钓鱼模拟。</span><span class="sxs-lookup"><span data-stu-id="7434a-105">Attack simulation training enables Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 organizations to measure and manage social engineering risk by allowing the creation and management of phishing simulations that are powered by real-world, de-weaponized phishing payloads.</span></span> <span data-ttu-id="7434a-106">与 Terranova 安全性合作提供的超目标培训可帮助提高知识并改变员工行为。</span><span class="sxs-lookup"><span data-stu-id="7434a-106">Hyper-targeted training, delivered in partnership with Terranova security, helps improve knowledge and change employee behavior.</span></span>

<span data-ttu-id="7434a-107">有关攻击模拟培训入门的信息，请参阅使用 [攻击模拟培训入门](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="7434a-107">For more information about getting started with Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="7434a-108">尽管整个模拟创建和计划体验设计为可自由流动且流畅，但企业规模运行的模拟通常需要规划。</span><span class="sxs-lookup"><span data-stu-id="7434a-108">While the whole simulation creation and scheduling experience has been designed to be free-flowing and frictionless, running simulations at an enterprise scale often requires planning.</span></span> <span data-ttu-id="7434a-109">本文有助于解决客户在其自己的环境中运行模拟时所看到的特定挑战。</span><span class="sxs-lookup"><span data-stu-id="7434a-109">This article helps address specific challenges that we see as our customers run simulations in their own environments.</span></span>

## <a name="issues-with-end-user-experiences"></a><span data-ttu-id="7434a-110">最终用户体验问题</span><span class="sxs-lookup"><span data-stu-id="7434a-110">Issues with end user experiences</span></span>

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a><span data-ttu-id="7434a-111">Google 网页浏览阻止的网络钓鱼保险箱 URL</span><span class="sxs-lookup"><span data-stu-id="7434a-111">Phishing simulation URLs blocked by Google Safe Browsing</span></span>

<span data-ttu-id="7434a-112">URL 信誉服务可能会将攻击模拟培训使用的一个或多个 URL 标识为不安全。</span><span class="sxs-lookup"><span data-stu-id="7434a-112">A URL reputation service might identify one or more of the URLs that are used by Attack simulation training as unsafe.</span></span> <span data-ttu-id="7434a-113">Google 保险箱 Chrome 中的浏览功能会阻止一些带有欺骗性网站提前消息的模拟网络钓鱼 **URL。**</span><span class="sxs-lookup"><span data-stu-id="7434a-113">Google Safe Browsing in Google Chrome blocks some of the simulated phishing URLs with a **Deceptive site ahead** message.</span></span> <span data-ttu-id="7434a-114">虽然我们与许多 URL 信誉供应商合作，始终允许我们的模拟 URL，但并不总是具有完全覆盖。</span><span class="sxs-lookup"><span data-stu-id="7434a-114">While we work with many URL reputation vendors to always allow our simulation URLs, we don't always have full coverage.</span></span>

![Google Chrome 中的欺骗性网站提前警告](../../media/attack-sim-chrome-deceptive-site-message.png)

<span data-ttu-id="7434a-116">请注意，此问题不会影响Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="7434a-116">Note that this issue does not affect Microsoft Edge.</span></span>

<span data-ttu-id="7434a-117">作为规划阶段的一部分，请务必先检查 URL 在支持的 Web 浏览器中的可用性，然后再在网络钓鱼活动中使用该 URL。</span><span class="sxs-lookup"><span data-stu-id="7434a-117">As part of the planning phase, be sure to check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="7434a-118">如果 Google 保险箱阻止 URL，请按照 Google 的本指南[](https://support.google.com/chrome/a/answer/7532419)允许访问 URL。</span><span class="sxs-lookup"><span data-stu-id="7434a-118">If the URLs are blocked by Google Safe Browsing, [follow this guidance](https://support.google.com/chrome/a/answer/7532419) from Google to allow access to the URLs.</span></span>

<span data-ttu-id="7434a-119">有关 [攻击模拟培训当前](attack-simulation-training-get-started.md) 使用的 URL 列表，请参阅使用攻击模拟培训入门。</span><span class="sxs-lookup"><span data-stu-id="7434a-119">Refer to [Get started using Attack simulation training](attack-simulation-training-get-started.md) for the list of URLs that are currently used by Attack simulation training.</span></span>

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a><span data-ttu-id="7434a-120">网络代理解决方案和筛选器驱动程序阻止的网络钓鱼模拟和管理 URL</span><span class="sxs-lookup"><span data-stu-id="7434a-120">Phishing simulation and admin URLs blocked by network proxy solutions and filter drivers</span></span>

<span data-ttu-id="7434a-121">您的中间安全设备或筛选器可能会阻止或删除网络钓鱼模拟 URL 和管理 URL。</span><span class="sxs-lookup"><span data-stu-id="7434a-121">Both phishing simulation URLs and admin URLs might be blocked or dropped by your intermediate security devices or filters.</span></span> <span data-ttu-id="7434a-122">例如：</span><span class="sxs-lookup"><span data-stu-id="7434a-122">For example:</span></span>

- <span data-ttu-id="7434a-123">防火墙</span><span class="sxs-lookup"><span data-stu-id="7434a-123">Firewalls</span></span>
- <span data-ttu-id="7434a-124">WAF 解决方案 (Web) 防火墙</span><span class="sxs-lookup"><span data-stu-id="7434a-124">Web Application Firewall (WAF) solutions</span></span>
- <span data-ttu-id="7434a-125">例如，第三方筛选器 (，例如内核模式) </span><span class="sxs-lookup"><span data-stu-id="7434a-125">Third-party filter drivers (for example, kernel mode filters)</span></span>

<span data-ttu-id="7434a-126">尽管我们看到此层中很少客户被阻止，但确实如此。</span><span class="sxs-lookup"><span data-stu-id="7434a-126">While we have seen few customers being blocked at this layer, it does happen.</span></span> <span data-ttu-id="7434a-127">如果遇到问题，请考虑将以下 URL 配置为绕过安全设备或筛选器所需的扫描：</span><span class="sxs-lookup"><span data-stu-id="7434a-127">If you encounter problems, consider configuring the following URLs to bypass scanning by your security devices or filters as required:</span></span>

- <span data-ttu-id="7434a-128">如使用攻击模拟培训入门中所述的模拟[网络钓鱼 URL。](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="7434a-128">The simulated phishing URLs as described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a><span data-ttu-id="7434a-129">未向所有目标用户传递模拟消息</span><span class="sxs-lookup"><span data-stu-id="7434a-129">Simulation messages not delivered to all targeted users</span></span>

<span data-ttu-id="7434a-130">实际接收模拟电子邮件的用户数可能小于模拟的目标用户数。</span><span class="sxs-lookup"><span data-stu-id="7434a-130">It's possible that the number of users who actually receive the simulation email messages is less than the number of users who were targeted by the simulation.</span></span> <span data-ttu-id="7434a-131">作为目标验证的一部分，将排除以下类型的用户：</span><span class="sxs-lookup"><span data-stu-id="7434a-131">The following types of users will be excluded as part of target validation:</span></span>

- <span data-ttu-id="7434a-132">收件人电子邮件地址无效。</span><span class="sxs-lookup"><span data-stu-id="7434a-132">Invalid recipient email addresses.</span></span>
- <span data-ttu-id="7434a-133">来宾用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-133">Guest users.</span></span>
- <span data-ttu-id="7434a-134">在 Azure AD Azure Active Directory (中不再) 。</span><span class="sxs-lookup"><span data-stu-id="7434a-134">Users that are no longer active in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="7434a-135">只有具有有效邮箱的有效非来宾用户才包括在模拟中。</span><span class="sxs-lookup"><span data-stu-id="7434a-135">Only valid, non-guest users with a valid mailbox will be included in simulations.</span></span> <span data-ttu-id="7434a-136">如果使用通讯组或启用邮件的安全组作为目标用户，可以使用[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的[Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet 查看和验证通讯组成员。</span><span class="sxs-lookup"><span data-stu-id="7434a-136">If you use distribution groups or mail-enabled security groups to target users, you can use the [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to view and validate distribution group members.</span></span>

## <a name="issues-with-attack-simulation-training-reporting"></a><span data-ttu-id="7434a-137">攻击模拟培训报告问题</span><span class="sxs-lookup"><span data-stu-id="7434a-137">Issues with Attack simulation training reporting</span></span>

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a><span data-ttu-id="7434a-138">攻击模拟培训报告不包含任何活动详细信息</span><span class="sxs-lookup"><span data-stu-id="7434a-138">Attack simulation training reports do not contain any activity details</span></span>

<span data-ttu-id="7434a-139">攻击模拟培训附带丰富、可操作见解，可让你了解员工的威胁就绪进度。</span><span class="sxs-lookup"><span data-stu-id="7434a-139">Attack simulation training comes with rich, actionable insights that keep you informed of the threat readiness progress of your employees.</span></span> <span data-ttu-id="7434a-140">如果攻击模拟培训报告未填充数据，请验证 审核日志搜索是否在你的组织中打开 (是否默认启用) 。</span><span class="sxs-lookup"><span data-stu-id="7434a-140">If Attack simulation training reports are not populated with data, verify that audit log search is turned on in your organization (it's on by default).</span></span>

<span data-ttu-id="7434a-141">攻击模拟培训需要审核日志搜索，以便可以捕获、记录和重新读取事件。</span><span class="sxs-lookup"><span data-stu-id="7434a-141">Audit log search is required by Attack simulation training so events can be captured, recorded, and read back.</span></span> <span data-ttu-id="7434a-142">关闭审核日志搜索对攻击模拟培训有以下后果：</span><span class="sxs-lookup"><span data-stu-id="7434a-142">Turning off audit log search has the following consequences for Attack simulation training:</span></span>

- <span data-ttu-id="7434a-143">报告数据并非在所有报告中都可用。</span><span class="sxs-lookup"><span data-stu-id="7434a-143">Reporting data is not available across all reports.</span></span> <span data-ttu-id="7434a-144">报告将显示为空。</span><span class="sxs-lookup"><span data-stu-id="7434a-144">The reports will appear empty.</span></span>
- <span data-ttu-id="7434a-145">由于数据不可用，因此将阻止培训作业。</span><span class="sxs-lookup"><span data-stu-id="7434a-145">Training assignments are blocked, because data is not available.</span></span>

<span data-ttu-id="7434a-146">若要打开搜索审核日志，请参阅打开 [审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7434a-146">To turn on audit log search, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7434a-147">未向用户分配 E5 许可证也导致了空活动详细信息。</span><span class="sxs-lookup"><span data-stu-id="7434a-147">Empty activity details can also be caused by no E5 licenses being assigned to users.</span></span> <span data-ttu-id="7434a-148">确认至少向活动用户分配了一个 E5 许可证，以确保捕获并记录报告事件。</span><span class="sxs-lookup"><span data-stu-id="7434a-148">Verify at least one E5 license is assigned to an active user to ensure that reporting events are captured and recorded.</span></span>

### <a name="simulation-reports-are-not-updated-immediately"></a><span data-ttu-id="7434a-149">模拟报告不会立即更新</span><span class="sxs-lookup"><span data-stu-id="7434a-149">Simulation reports are not updated immediately</span></span>

<span data-ttu-id="7434a-150">详细的模拟报告不会在启动市场活动后立即更新。</span><span class="sxs-lookup"><span data-stu-id="7434a-150">Detailed simulation reports are not updated immediately after you launch a campaign.</span></span> <span data-ttu-id="7434a-151">不要担心;此行为是预期行为。</span><span class="sxs-lookup"><span data-stu-id="7434a-151">Don't worry; this behavior is expected.</span></span>

<span data-ttu-id="7434a-152">每个模拟活动都有一个生命周期。</span><span class="sxs-lookup"><span data-stu-id="7434a-152">Every simulation campaign has a lifecycle.</span></span> <span data-ttu-id="7434a-153">首次创建时，模拟将位于 **计划** 状态。</span><span class="sxs-lookup"><span data-stu-id="7434a-153">When first created, the simulation is in the **Scheduled** state.</span></span> <span data-ttu-id="7434a-154">模拟开始时，它将转换为 **正在进行状态。**</span><span class="sxs-lookup"><span data-stu-id="7434a-154">When the simulation starts, it transitions to the **In progress** state.</span></span> <span data-ttu-id="7434a-155">完成后，模拟将转换为 **"已完成"** 状态。</span><span class="sxs-lookup"><span data-stu-id="7434a-155">When completed, the simulation transitions to the **Completed** state.</span></span>

<span data-ttu-id="7434a-156">当模拟状态为 **计划** 时，模拟报告将大部分为空。</span><span class="sxs-lookup"><span data-stu-id="7434a-156">While a simulation is in the **Scheduled** state, the simulation reports will be mostly empty.</span></span> <span data-ttu-id="7434a-157">在此阶段，模拟引擎将解析目标用户电子邮件地址、展开通讯组、从列表中删除来宾用户等：</span><span class="sxs-lookup"><span data-stu-id="7434a-157">During this stage, the simulation engine is resolving the target user email addresses, expanding distribution groups, removing guest users from the list, etc.:</span></span>

![计划状态中的报告](../../media/attack-sim-empty-reporting.png)

<span data-ttu-id="7434a-159">模拟进入正在进行阶段 **后** ，你将注意到信息开始欺骗报告：</span><span class="sxs-lookup"><span data-stu-id="7434a-159">Once the simulation enters the **In progress** stage, you will notice information starting to trickle into the reporting:</span></span>

![报告为正在进行状态](../../media/attack-sim-in-progress.png)

<span data-ttu-id="7434a-161">转换到正在进行状态后，可能需要 30 分钟才能更新单个 **模拟** 报告。</span><span class="sxs-lookup"><span data-stu-id="7434a-161">It can take up to 30 minutes for the individual simulation reports to update after the transition to the **In progress** state.</span></span> <span data-ttu-id="7434a-162">报告数据将继续生成，直到模拟达到 **"已完成"** 状态。</span><span class="sxs-lookup"><span data-stu-id="7434a-162">The report data continues to build until the simulation reaches the **Completed** state.</span></span> <span data-ttu-id="7434a-163">报告更新将按照以下间隔发生：</span><span class="sxs-lookup"><span data-stu-id="7434a-163">Reporting updates occur at the following intervals:</span></span>

- <span data-ttu-id="7434a-164">前 60 分钟每 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="7434a-164">Every 10 minutes for the first 60 minutes.</span></span>
- <span data-ttu-id="7434a-165">每隔 15 分钟，60 分钟到 2 天。</span><span class="sxs-lookup"><span data-stu-id="7434a-165">Every 15 minutes after 60 minutes until 2 days.</span></span>
- <span data-ttu-id="7434a-166">每隔 2 天到 7 天每 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="7434a-166">Every 30 minutes after 2 days until 7 days.</span></span>
- <span data-ttu-id="7434a-167">每 7 天 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="7434a-167">Every 60 minutes after 7 days.</span></span>

<span data-ttu-id="7434a-168">"概述 **"页上** 的小部件提供组织基于模拟的安全状态在一段时间的快速快照。</span><span class="sxs-lookup"><span data-stu-id="7434a-168">Widgets on the **Overview** page provide a quick snapshot of your organization's simulation-based security posture over time.</span></span> <span data-ttu-id="7434a-169">由于这些小组件反映了整体安全状况和一段时间的旅程，因此在每个模拟市场活动完成后会更新它们。</span><span class="sxs-lookup"><span data-stu-id="7434a-169">Because these widgets reflect your overall security posture and journey over time, they're updated after each simulation campaign is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="7434a-170">可以使用各种报告 **页面上** 的"导出"选项提取数据。</span><span class="sxs-lookup"><span data-stu-id="7434a-170">You can use the **Export** option on the various reporting pages to extract data.</span></span>

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a><span data-ttu-id="7434a-171">用户报告为网络钓鱼的邮件不会显示在模拟报告中</span><span class="sxs-lookup"><span data-stu-id="7434a-171">Messages reported as phishing by users aren't appearing in simulation reports</span></span>

<span data-ttu-id="7434a-172">攻击模拟器培训中的模拟报告提供有关用户活动的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7434a-172">Simulation reports in Attack simulator training provide details on user activity.</span></span> <span data-ttu-id="7434a-173">例如：</span><span class="sxs-lookup"><span data-stu-id="7434a-173">For example:</span></span>

- <span data-ttu-id="7434a-174">单击邮件中链接的用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-174">Users who clicked on the link in the message.</span></span>
- <span data-ttu-id="7434a-175">放弃其凭据的用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-175">Users who gave up their credentials.</span></span>
- <span data-ttu-id="7434a-176">将邮件报告为网络钓鱼的用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-176">Users who reported the message as phishing.</span></span>

<span data-ttu-id="7434a-177">如果用户报告为网络钓鱼的邮件未在攻击模拟培训模拟报告中捕获，则可能有 Exchange 邮件流规则 (也称为传输规则) 该规则阻止将报告的邮件送达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7434a-177">If messages that users reported as phishing aren't captured in Attack simulation training simulation reports, there might be an Exchange mail flow rule (also known as a transport rule) that's blocking the delivery of the reported messages to Microsoft.</span></span> <span data-ttu-id="7434a-178">验证任何邮件流规则是否未阻止到以下电子邮件地址的传递：</span><span class="sxs-lookup"><span data-stu-id="7434a-178">Verify that any mail flow rules aren't blocking delivery to the following email addresses:</span></span>

- <span data-ttu-id="7434a-179">junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7434a-179">junk@office365.microsoft.com</span></span>
- <span data-ttu-id="7434a-180">abuse@messaging.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7434a-180">abuse@messaging.microsoft.com</span></span>
- <span data-ttu-id="7434a-181">phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7434a-181">phish@office365.microsoft.com</span></span>
- <span data-ttu-id="7434a-182">不 \_ junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7434a-182">not\_junk@office365.microsoft.com</span></span>

## <a name="other-frequently-asked-questions"></a><span data-ttu-id="7434a-183">其他常见问题</span><span class="sxs-lookup"><span data-stu-id="7434a-183">Other frequently asked questions</span></span>

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a><span data-ttu-id="7434a-184">问：对于模拟市场活动，建议采用什么方法面向用户？</span><span class="sxs-lookup"><span data-stu-id="7434a-184">Q: What is the recommended method to target users for simulation campaigns?</span></span>

<span data-ttu-id="7434a-185">答：目标用户可以使用以下几种选项：</span><span class="sxs-lookup"><span data-stu-id="7434a-185">A: Several options are available to target users:</span></span>

- <span data-ttu-id="7434a-186">包括当前 (用户数少于 40，000 的组织可用的) 。</span><span class="sxs-lookup"><span data-stu-id="7434a-186">Include all users (currently available to organizations with less than 40,000 users).</span></span>
- <span data-ttu-id="7434a-187">选择特定用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-187">Choose specific users.</span></span>
- <span data-ttu-id="7434a-188">从 CSV 文件选择用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-188">Select users from a CSV file.</span></span>
- <span data-ttu-id="7434a-189">基于 Azure AD 组的定位。</span><span class="sxs-lookup"><span data-stu-id="7434a-189">Azure AD group-based targeting.</span></span>

<span data-ttu-id="7434a-190">我们发现通过 Azure AD 组标识目标用户的市场活动通常更易于管理。</span><span class="sxs-lookup"><span data-stu-id="7434a-190">We've found that campaigns where the targeted users are identified by Azure AD groups are generally easier to manage.</span></span>

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a><span data-ttu-id="7434a-191">问：从 CSV 导入或添加用户时，目标用户是否有限制？</span><span class="sxs-lookup"><span data-stu-id="7434a-191">Q: Are there any limits in targeting users while importing from a CSV or adding users?</span></span>

<span data-ttu-id="7434a-192">答：从 CSV 文件导入收件人或将单个收件人添加到模拟中的限制为 40，000。</span><span class="sxs-lookup"><span data-stu-id="7434a-192">A: The limit for importing recipients from a CSV file or adding individual recipients to a simulation is 40,000.</span></span>

<span data-ttu-id="7434a-193">收件人可以是单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="7434a-193">A recipient can be an individual user or a group.</span></span> <span data-ttu-id="7434a-194">一个组可能包含数百个或数千个收件人，因此不会对单个用户的数量设置实际限制。</span><span class="sxs-lookup"><span data-stu-id="7434a-194">A group might contain hundreds or thousands of recipients, so an actual limit isn't placed on the number of individual users.</span></span>

<span data-ttu-id="7434a-195">管理大型 CSV 文件或添加多个单个收件人可能很麻烦。</span><span class="sxs-lookup"><span data-stu-id="7434a-195">Managing a large CSV file or adding many individual recipients can be cumbersome.</span></span> <span data-ttu-id="7434a-196">使用 Azure AD 组将简化模拟的总体管理。</span><span class="sxs-lookup"><span data-stu-id="7434a-196">Using Azure AD groups will simplify the overall management of the simulation.</span></span>

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a><span data-ttu-id="7434a-197">问：Microsoft 是否提供其他语言的负载？</span><span class="sxs-lookup"><span data-stu-id="7434a-197">Q: Does Microsoft provide payloads in other languages?</span></span>

<span data-ttu-id="7434a-198">答：目前，有 5 个本地化有效负载可用。</span><span class="sxs-lookup"><span data-stu-id="7434a-198">A: Currently, there are 5 localized payloads available.</span></span> <span data-ttu-id="7434a-199">我们已注意到，现有有效负载到其他语言的任何直接或机器翻译都会导致不准确和相关性降低。</span><span class="sxs-lookup"><span data-stu-id="7434a-199">We've noticed than any direct or machine translations of existing payloads to other languages will lead to inaccuracies and decreased relevance.</span></span>

<span data-ttu-id="7434a-200">也就是说，可以使用自定义有效负载创作体验，以你选择的语言创建自己的有效负载。</span><span class="sxs-lookup"><span data-stu-id="7434a-200">That being said, you can create your own payload in the language of your choice using the custom payload authoring experience.</span></span> <span data-ttu-id="7434a-201">我们还强烈建议你获取用于面向特定地理位置的用户的现有有效负载。</span><span class="sxs-lookup"><span data-stu-id="7434a-201">We also strongly recommend that you harvest existing payloads that were used to target users in a specific geography.</span></span> <span data-ttu-id="7434a-202">换句话说，让攻击者本地化内容。</span><span class="sxs-lookup"><span data-stu-id="7434a-202">In other words, let the attackers localize the content for you.</span></span>

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a><span data-ttu-id="7434a-203">问：如何切换到其他语言以用于我的管理门户和培训体验？</span><span class="sxs-lookup"><span data-stu-id="7434a-203">Q: How can I switch to other languages for my admin portal and training experience?</span></span>

<span data-ttu-id="7434a-204">答：在Microsoft 365或Office 365中，语言配置是特定于每个用户帐户的集中式配置。</span><span class="sxs-lookup"><span data-stu-id="7434a-204">A: In Microsoft 365 or Office 365, language configuration is specific and centralized for each user account.</span></span> <span data-ttu-id="7434a-205">有关如何更改语言设置的说明，请参阅更改 Microsoft 365 for Business 中的显示语言[和时区](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)。</span><span class="sxs-lookup"><span data-stu-id="7434a-205">For instructions on how to change your language setting, see [Change your display language and time zone in Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).</span></span>

<span data-ttu-id="7434a-206">请注意，配置更改可能需要 30 分钟才能在所有服务之间同步。</span><span class="sxs-lookup"><span data-stu-id="7434a-206">Note that the configuration change might take up to 30 minutes to synchronize across all services.</span></span>

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a><span data-ttu-id="7434a-207">问：能否触发测试模拟，了解在启动功能齐全的市场活动之前它的外观？</span><span class="sxs-lookup"><span data-stu-id="7434a-207">Q: Can I trigger a test simulation to understand what it looks like prior to launching a full-fledged campaign?</span></span>

<span data-ttu-id="7434a-208">答：可以！</span><span class="sxs-lookup"><span data-stu-id="7434a-208">A: Yes you can!</span></span> <span data-ttu-id="7434a-209">在 **向导中用于** 创建新模拟的最后一个"审阅模拟"页上，有一个 **"发送测试"选项**。</span><span class="sxs-lookup"><span data-stu-id="7434a-209">On the very last **Review Simulation** page in the wizard to create a new simulation, there's an option to **Send a test**.</span></span> <span data-ttu-id="7434a-210">此选项将向当前登录的用户发送示例网络钓鱼模拟消息。</span><span class="sxs-lookup"><span data-stu-id="7434a-210">This option will send a sample phishing simulation message to the currently logged in user.</span></span> <span data-ttu-id="7434a-211">验证收件箱中的网络钓鱼邮件后，可以提交模拟。</span><span class="sxs-lookup"><span data-stu-id="7434a-211">After you validate the phishing message in your Inbox, you can submit the simulation.</span></span>

![在"审阅模拟"页上发送测试按钮](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a><span data-ttu-id="7434a-213">问：我能否将属于不同租户的用户作为同一模拟市场活动的一部分？</span><span class="sxs-lookup"><span data-stu-id="7434a-213">Q: Can I target users that belong to a different tenant as part of the same simulation campaign?</span></span>

<span data-ttu-id="7434a-214">答：不可以。</span><span class="sxs-lookup"><span data-stu-id="7434a-214">A: No.</span></span> <span data-ttu-id="7434a-215">目前不支持跨租户模拟。</span><span class="sxs-lookup"><span data-stu-id="7434a-215">Currently, cross-tenant simulations are not supported.</span></span> <span data-ttu-id="7434a-216">验证所有目标用户是否位于同一租户中。</span><span class="sxs-lookup"><span data-stu-id="7434a-216">Verify that all of your targeted users are in the same tenant.</span></span> <span data-ttu-id="7434a-217">任何跨租户用户或来宾用户都将从模拟市场活动中排除。</span><span class="sxs-lookup"><span data-stu-id="7434a-217">Any cross-tenant users or guest users will be excluded from the simulation campaign.</span></span>

### <a name="q-how-does-region-aware-delivery-work"></a><span data-ttu-id="7434a-218">问：区域感知传递如何工作？</span><span class="sxs-lookup"><span data-stu-id="7434a-218">Q: How does region aware delivery work?</span></span>

<span data-ttu-id="7434a-219">答：区域感知传递使用目标用户邮箱的 TimeZone 属性和"not before"逻辑来确定何时传递邮件。</span><span class="sxs-lookup"><span data-stu-id="7434a-219">A: Region aware delivery uses the TimeZone attribute of the targeted user's mailbox and 'not before' logic to determine when to deliver the message.</span></span> <span data-ttu-id="7434a-220">例如，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="7434a-220">For example, consider the following scenario:</span></span>

- <span data-ttu-id="7434a-221">在太平洋时区 (UTC-8) 的上午 7：00，管理员创建并计划一个活动，以在当天上午 9：00 开始。</span><span class="sxs-lookup"><span data-stu-id="7434a-221">At 7:00 AM in the Pacific time zone (UTC-8), an admin creates and schedules a campaign to start at 9:00 AM on the same day.</span></span>
- <span data-ttu-id="7434a-222">UserA 位于 UTC-5 (东部时区) 。</span><span class="sxs-lookup"><span data-stu-id="7434a-222">UserA is in the Eastern time zone (UTC-5).</span></span>
- <span data-ttu-id="7434a-223">UserB 也位于太平洋时区。</span><span class="sxs-lookup"><span data-stu-id="7434a-223">UserB is also in the Pacific time zone.</span></span>

<span data-ttu-id="7434a-224">同一天上午 9：00，模拟消息将发送到 UserB。</span><span class="sxs-lookup"><span data-stu-id="7434a-224">At 9:00 AM on the same day, the simulation message is sent to UserB.</span></span> <span data-ttu-id="7434a-225">使用区域感知传递，邮件不会在同一天发送给 UserA，因为太平洋时间上午 9：00 是东部时间晚上 12：00。</span><span class="sxs-lookup"><span data-stu-id="7434a-225">With region-aware delivery, the message is not sent to UserA on the same day, because 9:00 AM Pacific time is 12:00 PM Eastern time.</span></span> <span data-ttu-id="7434a-226">相反，邮件会于第二天东部时间上午 9：00 发送到 UserA。</span><span class="sxs-lookup"><span data-stu-id="7434a-226">Instead, the message is sent to UserA at 9:00 AM Eastern time on the following day.</span></span>

<span data-ttu-id="7434a-227">因此，在启用了区域感知传递的市场活动的初始运行中，模拟消息可能只发送给特定时区的用户。</span><span class="sxs-lookup"><span data-stu-id="7434a-227">So, on the initial run of a campaign with region aware delivery enabled, it might appear that the simulation message was sent only to users in a specific time zone.</span></span> <span data-ttu-id="7434a-228">但是，随着时间的推移，越来越多的用户进入作用域，目标用户将会增加。</span><span class="sxs-lookup"><span data-stu-id="7434a-228">But, as time passes and more users come into scope, the targeted users will increase.</span></span>