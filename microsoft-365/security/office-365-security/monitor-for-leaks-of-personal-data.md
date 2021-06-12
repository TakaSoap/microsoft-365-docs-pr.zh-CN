---
title: 监视个人数据泄露
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
description: 了解可用于监视个人数据泄露的三种工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05d31ac36fbdc687c60ec3c03efac9be43da9c39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878480"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="82e49-103">监视个人数据泄露</span><span class="sxs-lookup"><span data-stu-id="82e49-103">Monitor for leaks of personal data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="82e49-p101">有许多工具可用于监视个人数据的使用和传输。本主题介绍了三种十分有用的工具。</span><span class="sxs-lookup"><span data-stu-id="82e49-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![用于监视个人数据的使用和传输的工具](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="82e49-107">在此图中：</span><span class="sxs-lookup"><span data-stu-id="82e49-107">In the illustration:</span></span>

- <span data-ttu-id="82e49-p102">从 Microsoft 365 数据丢失防护报告入手，它们用于监视 SharePoint Online、OneDrive for Business 和传输中的电子邮件内的个人数据。这些报告为监控个人数据提供了最详细的信息。然而，这些报告并未囊括 Office 365 中的所有服务。</span><span class="sxs-lookup"><span data-stu-id="82e49-p102">Start with Microsoft 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These reports provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="82e49-p103">接下来，使用警报策略和审核日志监视服务中的活动。设置持续监视或搜索审核日志以调查事件。审核日志适用于以下服务：Sway、Power BI、电子数据展示、Dynamics 365、Microsoft Flow、Microsoft Teams、管理员活动、OneDrive for Business、SharePoint Online、传输中的邮件和静态邮箱。Skype 对话属于静态邮箱服务。</span><span class="sxs-lookup"><span data-stu-id="82e49-p103">Next, use alert policies and the audit log to monitor activity across services. Set up ongoing monitoring or search the audit log to investigate an incident. The audit log works across services—Sway, Power BI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="82e49-p104">最后，使用 Microsoft Cloud App Security 监视其他 SaaS 提供程序中包含敏感数据的文件。即将推出的功能为，通过 Cloud App Security 跨 Azure 信息保护和 Office 使用敏感信息类型和统一标签。可以设置适用于所有 SaaS 应用或特定应用（如 Box）的策略。Cloud App Security 不会发现 Exchange Online 中的文件（包括附加到电子邮件的文件）。</span><span class="sxs-lookup"><span data-stu-id="82e49-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can set up policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="data-loss-prevention-reports"></a><span data-ttu-id="82e49-119">数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="82e49-119">Data loss prevention reports</span></span>

<span data-ttu-id="82e49-p105">创建数据丢失防护 (DLP) 策略后，你需要验证这些策略是否按预期运行，以及是否有助于你保持合规性。借助 Office 365 中的 DLP 报告，可以快速查看 DLP 策略匹配数、替代数或误报数；观察它们随时间推移是呈上升趋势还是下降趋势；以不同的方式筛选报告；以及通过选择图中直线上的点来查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="82e49-p105">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view more details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="82e49-122">可以使用 DLP 报告实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="82e49-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="82e49-123">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="82e49-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
- <span data-ttu-id="82e49-124">发现违反组织的 DLP 策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="82e49-124">Discover business processes that violate your organization's DLP policies.</span></span>
- <span data-ttu-id="82e49-125">了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="82e49-125">Understand any business impact of the DLP policies.</span></span>
- <span data-ttu-id="82e49-126">查看用户在通过重写策略或报告误报解析策略提示时提交的理由。</span><span class="sxs-lookup"><span data-stu-id="82e49-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>
- <span data-ttu-id="82e49-127">通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="82e49-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
- <span data-ttu-id="82e49-128">在详细信息窗格中查看与您的 DLP 策略相匹配的含敏感数据的文件列表。</span><span class="sxs-lookup"><span data-stu-id="82e49-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="82e49-129">此外，当你在测试模式下运行 DLP 策略时，可以使用 DLP 报告对其进行微调。</span><span class="sxs-lookup"><span data-stu-id="82e49-129">In addition, you can use the DLP reports to fine-tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="82e49-130">DLP 报告在 Microsoft 365 合规中心内。</span><span class="sxs-lookup"><span data-stu-id="82e49-130">DLP reports are in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="82e49-131">转到“**报告**”\>“**组织数据**”部分来查找“**DLP 策略匹配**”、“**DLP 事件**”、“**DLP 误报和重写**”报告。</span><span class="sxs-lookup"><span data-stu-id="82e49-131">Go to **Reports** \> **Organizational data** section to find the **DLP policy matches**, **DLP incidents**, and **DLP false positives and overrides** reports.</span></span>

<span data-ttu-id="82e49-132">有关详细信息，请参阅[查看数据丢失防护报告](../../compliance/view-the-dlp-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="82e49-132">For more information, see [View the reports for data loss prevention](../../compliance/view-the-dlp-reports.md).</span></span>

![显示 DLP 策略匹配项的报告](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a><span data-ttu-id="82e49-134">审核日志和警报策略</span><span class="sxs-lookup"><span data-stu-id="82e49-134">Audit log and alert policies</span></span>

<span data-ttu-id="82e49-135">审核日志包含来自 Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft Teams、Power BI、Sway 和其他服务的事件。</span><span class="sxs-lookup"><span data-stu-id="82e49-135">The audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other services.</span></span>

<span data-ttu-id="82e49-136">Microsoft 365 Defender 门户和 Microsoft 365 合规中心提供两种对审核日志的监视和报告:</span><span class="sxs-lookup"><span data-stu-id="82e49-136">The Microsoft 365 Defender portal and the Microsoft 365 compliance center provide two ways to monitor and report against the audit log:</span></span>

- <span data-ttu-id="82e49-137">设置警报策略、查看警报和监视趋势 — 使用 Microsoft 365 Defender 门户和 Microsoft 365 合规中心中的警报策略和警报仪表板工具。</span><span class="sxs-lookup"><span data-stu-id="82e49-137">Set up alert policies, view alerts, and monitor trends—Use the alert policy and alert dashboard tools in either the Microsoft 365 Defender portal or the Microsoft 365 compliance center.</span></span>
- <span data-ttu-id="82e49-p107">直接搜索审核日志：搜索指定日期范围内的所有事件。也可以根据特定条件（如执行操作的用户、操作或目标对象）筛选结果。</span><span class="sxs-lookup"><span data-stu-id="82e49-p107">Search the audit log directly: Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="82e49-p108">信息安全和合规性团队可以使用这些工具主动审核由最终用户和管理员在服务中执行的活动。可以配置自动警报，以在特定网站集上发生某些活动时（例如从已知包含 GDPR 相关信息的网站共享内容时）发送电子邮件通知。通过此操作，这些团队可以跟进用户，以确保遵守企业安全策略或提供其他培训。</span><span class="sxs-lookup"><span data-stu-id="82e49-p108">Information compliance and security teams can use these tools to proactively review activities performed by both end users and administrators across services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR-related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="82e49-p109">信息安全团队还可以搜索审核日志来调查可疑的数据泄露并确定泄露的根本原因和程度。此内置功能有助于遵守 GDPR 条款 33 和 34 的规定，其中要求在特定时间段内向 GDPR 监管机构和数据泄露的数据主体自身提供通知。通常的建议是，仅将审核日志条目在服务内保留 90 天，但许多组织都要求将这些日志保留更长的时间。</span><span class="sxs-lookup"><span data-stu-id="82e49-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built-in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="82e49-p110">有些解决方案可以通过 Microsoft 管理活动 API 来订阅统一审核日志，而且可以按需存储日志条目并提供高级仪表板和警报。例如：[Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365)。</span><span class="sxs-lookup"><span data-stu-id="82e49-p110">Solutions are available that subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="82e49-148">有关警报策略和搜索审核日志的更多信息：</span><span class="sxs-lookup"><span data-stu-id="82e49-148">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="82e49-149">Microsoft 365 中的警报策略</span><span class="sxs-lookup"><span data-stu-id="82e49-149">Alert policies in Microsoft 365</span></span>](../../compliance/alert-policies.md)
- <span data-ttu-id="82e49-150">[在 Office 365 中搜索用户和管理员活动的审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)（介绍）</span><span class="sxs-lookup"><span data-stu-id="82e49-150">[Search the audit log for user and admin activity in Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md) (introduction)</span></span>
- [<span data-ttu-id="82e49-151">启用或禁用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="82e49-151">Turn audit log search on or off</span></span>](../../compliance/turn-audit-log-search-on-or-off.md)
- [<span data-ttu-id="82e49-152">搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="82e49-152">Search the audit log</span></span>](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- <span data-ttu-id="82e49-153">[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span><span class="sxs-lookup"><span data-stu-id="82e49-153">[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span></span>
- [<span data-ttu-id="82e49-154">审核日志中的详细属性</span><span class="sxs-lookup"><span data-stu-id="82e49-154">Detailed properties in the audit log</span></span>](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="82e49-155">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="82e49-155">Microsoft Cloud App Security</span></span>

<span data-ttu-id="82e49-156">Microsoft Cloud App Security 可帮助你跨网络发现使用中的其他 SaaS 应用、发送到这些应用的敏感数据以及从这些应用发送的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="82e49-156">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data sent to and from these apps.</span></span>

<span data-ttu-id="82e49-p111">Microsoft Cloud App Security 是一项可为云应用提供深层可见性、细化控制和增强型威胁防护的综合服务。它可以在你的网络中（从所有设备）识别出超过 15,000 个云应用程序，并提供风险评分以及持续的风险评估和分析。无需代理：从你的防火墙和代理收集信息，从而为你提供有关云使用情况和影子 IT 的完整可见性和上下文。</span><span class="sxs-lookup"><span data-stu-id="82e49-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls, and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="82e49-p112">为了更好地了解云环境，Cloud App Security 调查功能可让你深入了解批准的应用和托管的应用的所有活动、文件和帐户。你可以获得文件级别的详细信息，并发现数据在云应用中的传输位置。</span><span class="sxs-lookup"><span data-stu-id="82e49-p112">To better understand your cloud environment, the Cloud App Security investigate feature provides deep visibility into all activities, files, and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="82e49-162">例如，下图说明了有助于符合 GDPR 的两个 Cloud App Security 策略。</span><span class="sxs-lookup"><span data-stu-id="82e49-162">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![示例 Cloud App Security 策略](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="82e49-164">如果选择的文件包含预定义的 PII 属性或自定义表达式，并且从选择的 SaaS 应用组织外部共享，那么第一个策略发出警报。</span><span class="sxs-lookup"><span data-stu-id="82e49-164">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="82e49-p113">第二个策略会阻止将文件下载到任何非托管设备。选择要查找的文件内的属性以及需要对其应用策略的 SaaS 应用。</span><span class="sxs-lookup"><span data-stu-id="82e49-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="82e49-167">即将向 Cloud App Security 提供以下属性类型：</span><span class="sxs-lookup"><span data-stu-id="82e49-167">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="82e49-168">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="82e49-168">Sensitive information types</span></span>
- <span data-ttu-id="82e49-169">Microsoft 365 和 Azure 信息保护中的统一标签</span><span class="sxs-lookup"><span data-stu-id="82e49-169">Unified labels across Microsoft 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="82e49-170">Cloud App Security 仪表板</span><span class="sxs-lookup"><span data-stu-id="82e49-170">Cloud App Security dashboard</span></span>

<span data-ttu-id="82e49-p114">如果尚未开始使用 Cloud App Security，那就开始吧。Cloud App Security 的访问网址为 <https://portal.cloudappsecurity.com>。</span><span class="sxs-lookup"><span data-stu-id="82e49-p114">If you haven't yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

> [!NOTE]
> <span data-ttu-id="82e49-p115">开始使用 Cloud App Security 时或在分配标签前，请务必启用“自动扫描文件中是否有 Azure 信息保护分类标签”（位于“常规”设置中）。设置后，Cloud App Security 不会再次扫描现有文件，除非它们遭到修改。</span><span class="sxs-lookup"><span data-stu-id="82e49-p115">Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![显示有关警报信息的仪表板](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="82e49-176">详细信息：</span><span class="sxs-lookup"><span data-stu-id="82e49-176">More information:</span></span>

- [<span data-ttu-id="82e49-177">部署 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="82e49-177">Deploy Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security)
- [<span data-ttu-id="82e49-178">有关 Microsoft Cloud App Security 的更多信息</span><span class="sxs-lookup"><span data-stu-id="82e49-178">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [<span data-ttu-id="82e49-179">使用 Microsoft Cloud App Security 代理阻止下载敏感信息</span><span class="sxs-lookup"><span data-stu-id="82e49-179">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="82e49-180">用于检测个人数据共享的示例文件和活动策略</span><span class="sxs-lookup"><span data-stu-id="82e49-180">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="82e49-181">检测包含 PII 的文件共享 — 信用卡卡号</span><span class="sxs-lookup"><span data-stu-id="82e49-181">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="82e49-182">从批准的云应用共享包含信用卡卡号的文件时发出警报。</span><span class="sxs-lookup"><span data-stu-id="82e49-182">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<br>

****

|<span data-ttu-id="82e49-183">控件</span><span class="sxs-lookup"><span data-stu-id="82e49-183">Control</span></span>|<span data-ttu-id="82e49-184">设置</span><span class="sxs-lookup"><span data-stu-id="82e49-184">Settings</span></span>|
|---|---|
|<span data-ttu-id="82e49-185">策略类型</span><span class="sxs-lookup"><span data-stu-id="82e49-185">Policy type</span></span>|<span data-ttu-id="82e49-186">文件策略</span><span class="sxs-lookup"><span data-stu-id="82e49-186">File policy</span></span>|
|<span data-ttu-id="82e49-187">策略模板</span><span class="sxs-lookup"><span data-stu-id="82e49-187">Policy template</span></span>|<span data-ttu-id="82e49-188">无模板</span><span class="sxs-lookup"><span data-stu-id="82e49-188">No template</span></span>|
|<span data-ttu-id="82e49-189">策略严重性</span><span class="sxs-lookup"><span data-stu-id="82e49-189">Policy severity</span></span>|<span data-ttu-id="82e49-190">高</span><span class="sxs-lookup"><span data-stu-id="82e49-190">High</span></span>|
|<span data-ttu-id="82e49-191">类别</span><span class="sxs-lookup"><span data-stu-id="82e49-191">Category</span></span>|<span data-ttu-id="82e49-192">DLP</span><span class="sxs-lookup"><span data-stu-id="82e49-192">DLP</span></span>|
|<span data-ttu-id="82e49-193">筛选设置</span><span class="sxs-lookup"><span data-stu-id="82e49-193">Filter settings</span></span>|<span data-ttu-id="82e49-194">访问级别 = 公共 (Internet)，公共，外部</span><span class="sxs-lookup"><span data-stu-id="82e49-194">Access level = Public (Internet), Public, External</span></span> <p> <span data-ttu-id="82e49-195">应用 = \<select apps\>（如果想要将监视限制为特定 SaaS 应用，请使用此设置）</span><span class="sxs-lookup"><span data-stu-id="82e49-195">App = \<select apps\> (use this setting if you want to limit monitoring to specific SaaS apps)</span></span>|
|<span data-ttu-id="82e49-196">应用对象</span><span class="sxs-lookup"><span data-stu-id="82e49-196">Apply to</span></span>|<span data-ttu-id="82e49-197">所有文件、所有的所有者</span><span class="sxs-lookup"><span data-stu-id="82e49-197">All files, all owners</span></span>|
|<span data-ttu-id="82e49-198">内容检查</span><span class="sxs-lookup"><span data-stu-id="82e49-198">Content inspection</span></span>|<span data-ttu-id="82e49-199">包括匹配当前表达式的文件：所有国家/地区：法国：信用卡卡号</span><span class="sxs-lookup"><span data-stu-id="82e49-199">Includes files that match a present expression: All countries: Finance: Credit card number</span></span> <p> <span data-ttu-id="82e49-200">无需相关上下文：未选中（此设置将匹配关键字和正则表达式）</span><span class="sxs-lookup"><span data-stu-id="82e49-200">Don't require relevant context: unchecked (this setting will match keywords as well as regex)</span></span> <p> <span data-ttu-id="82e49-201">包括具有至少 1 个匹配项的文件</span><span class="sxs-lookup"><span data-stu-id="82e49-201">Includes files with at least 1 match</span></span> <p> <span data-ttu-id="82e49-202">取消屏蔽冲突的最后 4 个字符：已选中</span><span class="sxs-lookup"><span data-stu-id="82e49-202">Unmask the last 4 characters of the violation: checked</span></span>|
|<span data-ttu-id="82e49-203">警报</span><span class="sxs-lookup"><span data-stu-id="82e49-203">Alerts</span></span>|<span data-ttu-id="82e49-204">为每个匹配文件创建警报：已选中</span><span class="sxs-lookup"><span data-stu-id="82e49-204">Create an alert for each matching file: checked</span></span> <p> <span data-ttu-id="82e49-205">每日警报限制：1000</span><span class="sxs-lookup"><span data-stu-id="82e49-205">Daily alert limit: 1000</span></span> <p> <span data-ttu-id="82e49-206">选择一个警报作为电子邮件：已选中</span><span class="sxs-lookup"><span data-stu-id="82e49-206">Select an alert as email: checked</span></span> <p> <span data-ttu-id="82e49-207">收件人：infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82e49-207">To: infosec@contoso.com</span></span>|
|<span data-ttu-id="82e49-208">治理</span><span class="sxs-lookup"><span data-stu-id="82e49-208">Governance</span></span>|<span data-ttu-id="82e49-209">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="82e49-209">Microsoft OneDrive for Business</span></span> <p> <span data-ttu-id="82e49-210">设为专用：选中“删除外部用户”</span><span class="sxs-lookup"><span data-stu-id="82e49-210">Make private: check Remove External Users</span></span> <p> <span data-ttu-id="82e49-211">所有其他设置：未选中</span><span class="sxs-lookup"><span data-stu-id="82e49-211">All other settings: unchecked</span></span> <p> <span data-ttu-id="82e49-212">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="82e49-212">Microsoft SharePoint Online</span></span> <p> <span data-ttu-id="82e49-213">设为专用：选中“删除外部用户”</span><span class="sxs-lookup"><span data-stu-id="82e49-213">Make private: check Remove External Users</span></span> <p> <span data-ttu-id="82e49-214">所有其他设置：未选中</span><span class="sxs-lookup"><span data-stu-id="82e49-214">All other settings: unchecked</span></span>|
|

<span data-ttu-id="82e49-215">类似策略：</span><span class="sxs-lookup"><span data-stu-id="82e49-215">Similar policies:</span></span>

- <span data-ttu-id="82e49-216">检测包含 PII 的文件共享 — 电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="82e49-216">Detect sharing of Files containing PII - Email Address</span></span>
- <span data-ttu-id="82e49-217">检测包含 PII 的文件共享 — 护照编号</span><span class="sxs-lookup"><span data-stu-id="82e49-217">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="82e49-218">检测 Box 或 OneDrive for Business 中的客户或 HR 数据</span><span class="sxs-lookup"><span data-stu-id="82e49-218">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="82e49-219">当标记为“客户数据”或“HR 数据”的文件上传至 OneDrive for Business 或 Box 时发出警报。</span><span class="sxs-lookup"><span data-stu-id="82e49-219">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="82e49-220">注意：</span><span class="sxs-lookup"><span data-stu-id="82e49-220">Notes:</span></span>

- <span data-ttu-id="82e49-221">Box 监视要求使用 API 连接器 SDK 配置连接器。</span><span class="sxs-lookup"><span data-stu-id="82e49-221">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>
- <span data-ttu-id="82e49-222">此策略需要当前为个人预览版的功能。</span><span class="sxs-lookup"><span data-stu-id="82e49-222">This policy requires capabilities that are currently in private preview.</span></span>

<br>

****

|<span data-ttu-id="82e49-223">控件</span><span class="sxs-lookup"><span data-stu-id="82e49-223">Control</span></span>|<span data-ttu-id="82e49-224">设置</span><span class="sxs-lookup"><span data-stu-id="82e49-224">Settings</span></span>|
|---|---|
|<span data-ttu-id="82e49-225">策略类型</span><span class="sxs-lookup"><span data-stu-id="82e49-225">Policy type</span></span>|<span data-ttu-id="82e49-226">活动策略</span><span class="sxs-lookup"><span data-stu-id="82e49-226">Activity policy</span></span>|
|<span data-ttu-id="82e49-227">策略模板</span><span class="sxs-lookup"><span data-stu-id="82e49-227">Policy template</span></span>|<span data-ttu-id="82e49-228">无模板</span><span class="sxs-lookup"><span data-stu-id="82e49-228">No template</span></span>|
|<span data-ttu-id="82e49-229">策略严重性</span><span class="sxs-lookup"><span data-stu-id="82e49-229">Policy severity</span></span>|<span data-ttu-id="82e49-230">高</span><span class="sxs-lookup"><span data-stu-id="82e49-230">High</span></span>|
|<span data-ttu-id="82e49-231">类别</span><span class="sxs-lookup"><span data-stu-id="82e49-231">Category</span></span>|<span data-ttu-id="82e49-232">共享控制</span><span class="sxs-lookup"><span data-stu-id="82e49-232">Sharing Control</span></span>|
|<span data-ttu-id="82e49-233">作用对象</span><span class="sxs-lookup"><span data-stu-id="82e49-233">Act on</span></span>|<span data-ttu-id="82e49-234">单个活动</span><span class="sxs-lookup"><span data-stu-id="82e49-234">Single activity</span></span>|
|<span data-ttu-id="82e49-235">筛选设置</span><span class="sxs-lookup"><span data-stu-id="82e49-235">Filter settings</span></span>|<span data-ttu-id="82e49-236">活动类型 = 上传文件</span><span class="sxs-lookup"><span data-stu-id="82e49-236">Activity type = Upload File</span></span> <p> <span data-ttu-id="82e49-237">应用 = Microsoft OneDrive for Business 和 Box</span><span class="sxs-lookup"><span data-stu-id="82e49-237">App = Microsoft OneDrive for Business and Box</span></span> <p> <span data-ttu-id="82e49-238">分类标签（目前为个人预览版）：Azure 信息保护 = 客户数据、人力资源—薪资数据、人力资源—员工数据</span><span class="sxs-lookup"><span data-stu-id="82e49-238">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span>|
|<span data-ttu-id="82e49-239">警报</span><span class="sxs-lookup"><span data-stu-id="82e49-239">Alerts</span></span>|<span data-ttu-id="82e49-240">创建警报：已选中</span><span class="sxs-lookup"><span data-stu-id="82e49-240">Create an alert: checked</span></span> <p> <span data-ttu-id="82e49-241">每日警报限制：1000</span><span class="sxs-lookup"><span data-stu-id="82e49-241">Daily alert limit: 1000</span></span> <p> <span data-ttu-id="82e49-242">选择一个警报作为电子邮件：已选中</span><span class="sxs-lookup"><span data-stu-id="82e49-242">Select an alert as email: checked</span></span> <p> <span data-ttu-id="82e49-243">收件人：infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82e49-243">To: infosec@contoso.com</span></span>|
|<span data-ttu-id="82e49-244">治理</span><span class="sxs-lookup"><span data-stu-id="82e49-244">Governance</span></span>|<span data-ttu-id="82e49-245">所有应用</span><span class="sxs-lookup"><span data-stu-id="82e49-245">All apps</span></span> <p> <span data-ttu-id="82e49-246">隔离用户：选中</span><span class="sxs-lookup"><span data-stu-id="82e49-246">Put user in quarantine: check</span></span> <p> <span data-ttu-id="82e49-247">所有其他设置：未选中</span><span class="sxs-lookup"><span data-stu-id="82e49-247">All other settings: unchecked</span></span> <p> <span data-ttu-id="82e49-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="82e49-248">Office 365</span></span> <p> <span data-ttu-id="82e49-249">隔离用户：选中</span><span class="sxs-lookup"><span data-stu-id="82e49-249">Put user in quarantine: check</span></span> <p> <span data-ttu-id="82e49-250">所有其他设置：未选中</span><span class="sxs-lookup"><span data-stu-id="82e49-250">All other settings: unchecked</span></span>|
|

<span data-ttu-id="82e49-251">类似策略：</span><span class="sxs-lookup"><span data-stu-id="82e49-251">Similar policies:</span></span>

- <span data-ttu-id="82e49-252">检测大量下载客户数据或 HR 数据的情况 — 如果检测到单个用户在较短的一段时间内下载了大量包含客户数据或 HR 数据的文件，则发出警报。</span><span class="sxs-lookup"><span data-stu-id="82e49-252">Detect large downloads of Customer data or HR Data—Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>
- <span data-ttu-id="82e49-253">检测共享客户和 HR 数据的情况 — 共享包含客户或 HR 数据的文件时发出警报。</span><span class="sxs-lookup"><span data-stu-id="82e49-253">Detect Sharing of Customer and HR Data—Alert when files containing Customer or HR Data are shared.</span></span>
