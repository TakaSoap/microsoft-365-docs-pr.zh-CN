---
title: 安全仪表板概述
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用新的安全仪表板查看 Office 365 的威胁防护状态，查看安全警报并对其采取操作。
ms.openlocfilehash: 1bef6d0496c39d5157bbc40893d2710e89d1c734
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200069"
---
# <a name="security-dashboard"></a><span data-ttu-id="10335-103">安全仪表板</span><span class="sxs-lookup"><span data-stu-id="10335-103">Security Dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a><span data-ttu-id="10335-104">基本功能以及如何打开安全仪表板</span><span class="sxs-lookup"><span data-stu-id="10335-104">Basic functions and how to open Security Dashboard</span></span>

<span data-ttu-id="10335-105">[安全 & 合规中心](../../compliance/go-to-the-securitycompliance-center.md)使组织能够管理数据保护和合规性。</span><span class="sxs-lookup"><span data-stu-id="10335-105">The [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) enables your organization to manage data protection and compliance.</span></span> <span data-ttu-id="10335-106">如果您具有必要的权限，安全仪表板将使您能够查看威胁保护状态，并查看安全警报并对其采取措施。</span><span class="sxs-lookup"><span data-stu-id="10335-106">Assuming you have the necessary permissions, the Security Dashboard enables you to review your Threat Protection Status, as well as view and act on security alerts.</span></span>

<span data-ttu-id="10335-107">观看视频以获取概述，然后阅读本文以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="10335-107">Watch the video to get an overview, and then read this article to learn more.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

<span data-ttu-id="10335-108">根据您组织的订阅包括的内容，安全仪表板包含多个小部件，如威胁管理摘要、威胁保护状态、全球每周威胁检测、恶意软件等，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="10335-108">Depending on what your organization's subscription includes, the Security Dashboard includes several widgets, such as Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware, and more, as described in the following sections.</span></span>

<span data-ttu-id="10335-109">若要查看安全仪表板，请在 [安全性 & 合规性中心](../../compliance/go-to-the-securitycompliance-center.md)中，转到 " **威胁管理**" \> **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="10335-109">To view the Security Dashboard, in the [Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md), go to **Threat management** \> **Dashboard**.</span></span>

> [!NOTE]
> <span data-ttu-id="10335-110">您必须是全局管理员、安全管理员或安全读者才能查看安全仪表板。</span><span class="sxs-lookup"><span data-stu-id="10335-110">You must be a global administrator, a security administrator, or a security reader to view the Security Dashboard.</span></span> <span data-ttu-id="10335-111">某些小部件需要其他权限才能查看。</span><span class="sxs-lookup"><span data-stu-id="10335-111">Some widgets require additional permissions to view.</span></span> <span data-ttu-id="10335-112">若要了解详细信息，请参阅 [安全性 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="10335-112">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="threat-management-summary"></a><span data-ttu-id="10335-113">威胁管理摘要</span><span class="sxs-lookup"><span data-stu-id="10335-113">Threat Management Summary</span></span>

<span data-ttu-id="10335-114">威胁管理摘要小部件告诉你组织在过去七 (7) 天内抵御威胁的方式。</span><span class="sxs-lookup"><span data-stu-id="10335-114">The Threat Management Summary widget tells you at a glance how your organization was protected from threats over the past seven (7) days.</span></span>

![安全仪表板-威胁管理摘要小部件](../../media/SecDash-ThreatMgmtSummary.png)

<span data-ttu-id="10335-116">您在威胁管理摘要中看到的信息取决于订阅所包含的内容。</span><span class="sxs-lookup"><span data-stu-id="10335-116">The information you'll see in the Threat Management Summary depends on what you subscription includes.</span></span> <span data-ttu-id="10335-117">下表介绍了 Office 365 E3 和 Office 365 E5 包含的信息。</span><span class="sxs-lookup"><span data-stu-id="10335-117">The following table describes what information is included for Office 365 E3 and Office 365 E5.</span></span>

|<span data-ttu-id="10335-118">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="10335-118">Office 365 E3</span></span>|<span data-ttu-id="10335-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="10335-119">Office 365 E5</span></span>|
|---|---|
|<span data-ttu-id="10335-120">阻止的恶意软件邮件</span><span class="sxs-lookup"><span data-stu-id="10335-120">Malware messages blocked</span></span><br/><span data-ttu-id="10335-121">阻止的仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="10335-121">Phishing messages blocked</span></span><br><span data-ttu-id="10335-122">用户报告的邮件</span><span class="sxs-lookup"><span data-stu-id="10335-122">Messages reported by users</span></span><br><br><br><br>|<span data-ttu-id="10335-123">阻止的恶意软件邮件</span><span class="sxs-lookup"><span data-stu-id="10335-123">Malware messages blocked</span></span><br><span data-ttu-id="10335-124">阻止的仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="10335-124">Phishing messages blocked</span></span><br><span data-ttu-id="10335-125">用户报告的邮件</span><span class="sxs-lookup"><span data-stu-id="10335-125">Messages reported by users</span></span><br><span data-ttu-id="10335-126">已阻止零天恶意软件</span><span class="sxs-lookup"><span data-stu-id="10335-126">Zero-day malware blocked</span></span><br><span data-ttu-id="10335-127">检测到高级网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="10335-127">Advanced phishing messages detected</span></span><br><span data-ttu-id="10335-128">阻止的恶意 Url</span><span class="sxs-lookup"><span data-stu-id="10335-128">Malicious URLs blocked</span></span>|

<span data-ttu-id="10335-129">若要查看或访问 "威胁管理摘要" 小部件，您必须具有查看高级威胁防护报告的权限。</span><span class="sxs-lookup"><span data-stu-id="10335-129">To view or access the Threat Management Summary widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="10335-130">若要了解详细信息，请参阅 [查看 ATP 报告所需的权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。</span><span class="sxs-lookup"><span data-stu-id="10335-130">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span></span>

## <a name="threat-protection-status"></a><span data-ttu-id="10335-131">威胁保护状态</span><span class="sxs-lookup"><span data-stu-id="10335-131">Threat Protection Status</span></span>

<span data-ttu-id="10335-132">威胁防护状态构件显示了威胁防护的有效性，并提供了有关网络钓鱼和恶意软件的趋势分析和详细视图。</span><span class="sxs-lookup"><span data-stu-id="10335-132">The Threat Protection Status widget shows threat protection effectiveness with a trending and detailed view of phish and malware.</span></span>

![威胁防护状态小部件](../../media/tpswidget.png)

<span data-ttu-id="10335-134">详细信息取决于您的 Microsoft 365 订阅是否包括 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 带有或不包含 [Office 365 高级威胁防护](office-365-atp.md) (ATP) 。</span><span class="sxs-lookup"><span data-stu-id="10335-134">The details depend on whether your Microsoft 365 subscription includes [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) with or without [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).</span></span>

|<span data-ttu-id="10335-135">如果你的订阅包括 .。。</span><span class="sxs-lookup"><span data-stu-id="10335-135">If your subscription includes...</span></span>|<span data-ttu-id="10335-136">你将看到这些详细信息</span><span class="sxs-lookup"><span data-stu-id="10335-136">You'll see these details</span></span>|
|---|---|
|<span data-ttu-id="10335-137">EOP，而不是 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="10335-137">EOP but not Office 365 ATP</span></span>|<span data-ttu-id="10335-138">由 EOP 检测并阻止的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="10335-138">Malicious email that was detected and blocked by EOP.</span></span><br><br> <span data-ttu-id="10335-139">请参阅 [威胁防护状态报告 (EOP) ](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="10335-139">See [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="10335-140">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="10335-140">Office 365 ATP</span></span>|<span data-ttu-id="10335-141">EOP 和 Office 365 ATP 检测到并阻止了恶意内容和恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="10335-141">Malicious content and malicious email detected and blocked by EOP and Office 365 ATP</span></span><br><br><span data-ttu-id="10335-142">由反恶意软件引擎阻止的包含恶意内容的独特电子邮件的聚合计数、 [零小时自动清除](zero-hour-auto-purge.md)和 atp 功能 (包括 [安全链接](atp-safe-links.md)、 [安全附件](atp-safe-attachments.md)和 [atp 反网络钓鱼](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)) 。</span><span class="sxs-lookup"><span data-stu-id="10335-142">Aggregated count of unique email messages with malicious content blocked by the anti-malware engine, [zero-hour auto purge](zero-hour-auto-purge.md), and ATP features (including [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)).</span></span><br><br><span data-ttu-id="10335-143">请参阅 [威胁防护状态报告 (ATP) ](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="10335-143">See [Threat protection status report (ATP)](view-reports-for-atp.md#threat-protection-status-report).</span></span>|

<span data-ttu-id="10335-144">若要查看或访问威胁防护状态小部件，您必须具有查看高级威胁防护报告的权限。</span><span class="sxs-lookup"><span data-stu-id="10335-144">To view or access the Threat Protection Status widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="10335-145">若要了解详细信息，请参阅 [查看 ATP 报告所需的权限。](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)</span><span class="sxs-lookup"><span data-stu-id="10335-145">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)</span></span>

## <a name="global-weekly-threat-detections"></a><span data-ttu-id="10335-146">全球每周威胁检测</span><span class="sxs-lookup"><span data-stu-id="10335-146">Global Weekly Threat Detections</span></span>

<span data-ttu-id="10335-147">"全球每周威胁检测" 小部件显示在过去七 (7) 天内的电子邮件中检测到的威胁数。</span><span class="sxs-lookup"><span data-stu-id="10335-147">The Global Weekly Threat Detections widget shows how many threats were detected in email messages over the past seven (7) days.</span></span>

![全球每周威胁检测小组件](../../media/globalweeklythreatdetections.png)

<span data-ttu-id="10335-149">指标的计算如下表所述：</span><span class="sxs-lookup"><span data-stu-id="10335-149">The metrics are calculated as described in the following table:</span></span>

|<span data-ttu-id="10335-150">跃点数</span><span class="sxs-lookup"><span data-stu-id="10335-150">Metric</span></span>|<span data-ttu-id="10335-151">如何计算</span><span class="sxs-lookup"><span data-stu-id="10335-151">How it's calculated</span></span>|
|---|---|
|<span data-ttu-id="10335-152">扫描的邮件</span><span class="sxs-lookup"><span data-stu-id="10335-152">Messages scanned</span></span>|<span data-ttu-id="10335-153">扫描的电子邮件数乘以收件人数</span><span class="sxs-lookup"><span data-stu-id="10335-153">Number of email messages scanned multiplied by the number of recipients</span></span>|
|<span data-ttu-id="10335-154">威胁已停止</span><span class="sxs-lookup"><span data-stu-id="10335-154">Threats stopped</span></span>|<span data-ttu-id="10335-155">被标识为包含恶意软件的电子邮件数乘以收件人数</span><span class="sxs-lookup"><span data-stu-id="10335-155">Number of email messages identified as containing malware multiplied by the number of recipients</span></span>|
|<span data-ttu-id="10335-156">由[ATP](office-365-atp.md)阻止</span><span class="sxs-lookup"><span data-stu-id="10335-156">Blocked by [ATP](office-365-atp.md)</span></span>|<span data-ttu-id="10335-157">由 ATP 阻止的电子邮件数乘以收件人数</span><span class="sxs-lookup"><span data-stu-id="10335-157">Number of email messages blocked by ATP multiplied by the number of recipients</span></span>|
|<span data-ttu-id="10335-158">传递后删除</span><span class="sxs-lookup"><span data-stu-id="10335-158">Removed after delivery</span></span>|<span data-ttu-id="10335-159">由 [零小时自动清除](zero-hour-auto-purge.md) 删除的邮件数乘以收件人数</span><span class="sxs-lookup"><span data-stu-id="10335-159">Number of messages removed by [zero-hour auto purge](zero-hour-auto-purge.md) multiplied by the number of recipients</span></span>|

## <a name="malware"></a><span data-ttu-id="10335-160">恶意软件</span><span class="sxs-lookup"><span data-stu-id="10335-160">Malware</span></span>

<span data-ttu-id="10335-161">恶意软件小组件显示过去七个 (7) 天内的恶意软件趋势和恶意软件系列类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="10335-161">Malware widgets show details about malware trends and malware family types over the past seven (7) days.</span></span>

![恶意软件趋势和系列类型](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a><span data-ttu-id="10335-163">见解</span><span class="sxs-lookup"><span data-stu-id="10335-163">Insights</span></span>

<span data-ttu-id="10335-164">不只是 Insights 应查看的表面密钥问题，它们还包括建议和要考虑的操作。</span><span class="sxs-lookup"><span data-stu-id="10335-164">Insights not only surface key issues you should review, they also include recommendations and actions to consider.</span></span>

![智能见解](../../media/smartinsights.png)

<span data-ttu-id="10335-166">例如，您可能会看到网络钓鱼电子邮件被传递，因为某些用户禁用了其 "垃圾邮件" 选项。</span><span class="sxs-lookup"><span data-stu-id="10335-166">For example, you might see that phishing email messages are being delivered because some users have disabled their junk mail options.</span></span> <span data-ttu-id="10335-167">若要了解有关 insights 工作方式的详细信息，请参阅 [Security & 合规性中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="10335-167">To learn more about how insights work, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

## <a name="threat-investigation-and-response"></a><span data-ttu-id="10335-168">威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="10335-168">Threat investigation and response</span></span>

<span data-ttu-id="10335-169">如果贵组织的订阅包括  [Office 365 高级威胁防护计划 2](office-365-ti.md)，则安全仪表板包含一个包含高级威胁调查和响应工具的部分。</span><span class="sxs-lookup"><span data-stu-id="10335-169">If your organization's subscription includes  [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), your Security Dashboard has a section that includes advanced threat investigation and response tools.</span></span> <span data-ttu-id="10335-170">这些工具包括 [自动调查和响应功能](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="10335-170">These tools include [automated investigation and response capabilities](automated-investigation-response-office.md).</span></span> <span data-ttu-id="10335-171">自动调查和响应在诸如 [快速解决已泄露用户帐户](address-compromised-users-quickly.md)的方案中非常有用。</span><span class="sxs-lookup"><span data-stu-id="10335-171">Automated investigation and response can be helpful in scenarios such as [addressing compromised user accounts quickly](address-compromised-users-quickly.md).</span></span>

<span data-ttu-id="10335-172">若要了解详细信息，请参阅 [Office 365 中的开始使用自动调查和响应 (AIR) ](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="10335-172">To learn more, see [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).</span></span>

## <a name="trends"></a><span data-ttu-id="10335-173">趋势</span><span class="sxs-lookup"><span data-stu-id="10335-173">Trends</span></span>

<span data-ttu-id="10335-174">靠近安全仪表板底部的是 " **趋势** " 部分，它汇总了贵组织的电子邮件流趋势。</span><span class="sxs-lookup"><span data-stu-id="10335-174">Near the bottom of the Security Dashboard is a **Trends** section, which summarizes email flow trends for your organization.</span></span> <span data-ttu-id="10335-175">报告提供有关分类为垃圾邮件、恶意软件、网络钓鱼尝试和优质电子邮件的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="10335-175">Reports provide information about email categorized as spam, malware, phishing attempts, and good email.</span></span> <span data-ttu-id="10335-176">单击平铺可在报告中查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="10335-176">Click a tile to view more detailed information in the report.</span></span>

![趋势部分汇总了组织的电子邮件流趋势](../../media/trends.png)

<span data-ttu-id="10335-178">此外，如果您的组织的订阅包括 [Office 365 高级威胁防护计划 2](office-365-ti.md)，您还将在此部分中添加一个 **最近的威胁管理警报** 报告，使安全团队能够查看高优先级安全警报并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="10335-178">And, if your organization's subscription includes [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), you will also have a **Recent threat management alerts** report in this section that enables your security team to view and take action on high-priority security alerts.</span></span>

<span data-ttu-id="10335-179">若要查看或访问已发送和已接收的电子邮件小组件，您必须具有查看高级威胁防护报告的权限。</span><span class="sxs-lookup"><span data-stu-id="10335-179">To view or access the Sent and Received Email widget, you must have permissions to view Advanced Threat Protection reports.</span></span> <span data-ttu-id="10335-180">若要了解详细信息，请参阅 [查看 ATP 报告所需的权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。</span><span class="sxs-lookup"><span data-stu-id="10335-180">To learn more, see [What permissions are needed to view the ATP reports?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports).</span></span>

<span data-ttu-id="10335-181">若要查看或访问最新的威胁管理警报小部件，您必须具有查看警报的权限。</span><span class="sxs-lookup"><span data-stu-id="10335-181">To view or access the Recent Threat Management Alerts widget, you must have permissions to view alerts.</span></span> <span data-ttu-id="10335-182">若要了解详细信息，请参阅 [查看警报所需的 RBAC 权限](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。</span><span class="sxs-lookup"><span data-stu-id="10335-182">To learn more, see [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span></span>

## <a name="related-topics"></a><span data-ttu-id="10335-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="10335-183">Related topics</span></span>

[<span data-ttu-id="10335-184">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="10335-184">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="10335-185">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="10335-185">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="10335-186">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="10335-186">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="10335-187">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="10335-187">Office 365 Threat investigation and response</span></span>](office-365-ti.md)
