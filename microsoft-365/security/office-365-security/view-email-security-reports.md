---
title: 查看电子邮件安全报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何查找和使用 Microsoft 365 Defender 门户中提供的电子邮件安全报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022896"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="b2b10-103">在 Microsoft 365 Defender 门户中查看电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b2b10-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b2b10-104">**Applies to**</span></span>
- [<span data-ttu-id="b2b10-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b2b10-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b2b10-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b2b10-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b2b10-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2b10-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b2b10-108">Microsoft 365 Defender 门户中提供了各种报告，可帮助你了解 Microsoft 365 中的电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护 <https://security.microsoft.com> 你的组织。</span><span class="sxs-lookup"><span data-stu-id="b2b10-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="b2b10-109">如果你拥有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在 Microsoft 365 Defender 门户中查看这些报告，方式为：查看报告电子邮件&协作 电子邮件& \>  \> **协作报告**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-110">若要直接转到"电子邮件& **协作报告"** 页，请打开 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 门户中的"电子邮件&协作报告"页面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="b2b10-112">"电子邮件和协作报告 **"&一些报告** 需要 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="b2b10-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b2b10-113">有关这些报告的信息，请参阅在 [Microsoft 365](view-reports-for-mdo.md)Defender 门户中查看适用于 Office 365 的 Defender 报告。</span><span class="sxs-lookup"><span data-stu-id="b2b10-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="b2b10-114">与邮件流相关的报告现在位于 Exchange 管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="b2b10-115">有关这些报告详细信息，请参阅新 Exchange 管理中心 [中的邮件流报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="b2b10-116">遭到入侵的用户报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="b2b10-117">此报告适用于具有 Exchange Online 邮箱的 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="b2b10-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="b2b10-118">它不适用于独立 Exchange Online Protection (EOP) 组织。</span><span class="sxs-lookup"><span data-stu-id="b2b10-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="b2b10-119">"**遭到入侵的用户**"报告显示过去 7 天内标记为"可疑"或"受限"的用户帐户数量。</span><span class="sxs-lookup"><span data-stu-id="b2b10-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="b2b10-120">其中任一状态的帐户存在问题，甚至受到威胁。</span><span class="sxs-lookup"><span data-stu-id="b2b10-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="b2b10-121">通过频繁使用，可以使用报告来发现可疑或受限帐户的峰值甚至趋势。</span><span class="sxs-lookup"><span data-stu-id="b2b10-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="b2b10-122">有关遭到入侵的用户详细信息，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["电子邮件和协作报告"页上的"遭到入侵&小组件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="b2b10-124">聚合视图显示过去 90 天的数据，而详细信息视图显示最近 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b10-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="b2b10-125">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-126">在"**电子邮件&协作报告**"页上，找到 **"遭到** 入侵的用户"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="b2b10-127">若要直接转到报告，请打开 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="b2b10-128">在"**遭到入侵** 的用户"页上，可以同时筛选图表和详细信息表，方法是单击"筛选器"，在出现的标注中选择以下一个或多个值：</span><span class="sxs-lookup"><span data-stu-id="b2b10-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b2b10-129">**DATE (UTC)**： **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="b2b10-130">**活动**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-130">**Activity**:</span></span>
  - <span data-ttu-id="b2b10-131">**可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="b2b10-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="b2b10-132">**受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="b2b10-133">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

!["泄露的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="b2b10-135">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b2b10-136">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="b2b10-136">**Creation time**</span></span>
- <span data-ttu-id="b2b10-137">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="b2b10-137">**User ID**</span></span>
- <span data-ttu-id="b2b10-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="b2b10-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="b2b10-139">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-139">Exchange transport rule report</span></span>

<span data-ttu-id="b2b10-140">**Exchange 传输规则** 报告显示邮件流规则对组织中 (传输规则) 传入和传出邮件的影响。</span><span class="sxs-lookup"><span data-stu-id="b2b10-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="b2b10-141">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-142">在"**电子邮件&协作报告**"页上，找到 **"Exchange 传输** 规则"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="b2b10-143">若要直接转到报告，请打开 <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

!["电子邮件和协作报告"页面上的"Exchange 传输&小组件](../../media/transport-rule-report-widget.png)

<span data-ttu-id="b2b10-145">在 **"Exchange 传输规则报告** "页上，以下各节介绍了可用的图表和数据。</span><span class="sxs-lookup"><span data-stu-id="b2b10-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="b2b10-146">按方向细分图表</span><span class="sxs-lookup"><span data-stu-id="b2b10-146">Chart breakdown by Direction</span></span>

![Exchange 传输规则报告中 Exchange 传输规则的方向视图](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="b2b10-148">如果选择" **按方向细分图表"，** 则以下图表可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="b2b10-149">**按 Exchange 传输规则查看数据**：受邮件流规则影响的入站和出站邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="b2b10-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="b2b10-150">**按 DLP Exchange 传输规则查看数据**：受DLP 和邮件流规则中的数据丢失防护 () 邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="b2b10-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="b2b10-151">下图下的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="b2b10-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-152">**Date**</span></span>
- <span data-ttu-id="b2b10-153">**DLP 策略** (**仅通过 DLP Exchange 传输规则** 查看) </span><span class="sxs-lookup"><span data-stu-id="b2b10-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="b2b10-154">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="b2b10-154">**Transport rule**</span></span>
- <span data-ttu-id="b2b10-155">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-155">**Subject**</span></span>
- <span data-ttu-id="b2b10-156">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="b2b10-156">**Sender address**</span></span>
- <span data-ttu-id="b2b10-157">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="b2b10-157">**Recipient address**</span></span>
- <span data-ttu-id="b2b10-158">**严重性**</span><span class="sxs-lookup"><span data-stu-id="b2b10-158">**Severity**</span></span>
- <span data-ttu-id="b2b10-159">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-159">**Direction**</span></span>

<span data-ttu-id="b2b10-160">通过单击"筛选器"，并选择出现的一个或多个以下值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b2b10-161">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-162">**方向**： **出站** 和 **入站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="b2b10-163">**严重性：\*\*\*\*高严重性**、**中等严重性** 和 **低严重性**</span><span class="sxs-lookup"><span data-stu-id="b2b10-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="b2b10-164">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="b2b10-165">按严重性分类的图表</span><span class="sxs-lookup"><span data-stu-id="b2b10-165">Chart breakdown by Severity</span></span>

![Exchange 传输规则报告中 Exchange 传输规则的严重性视图](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="b2b10-167">如果选择" **按严重性划分图表细分"，** 则以下图表可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="b2b10-168">**按 Exchange 传输规则查看数据**：高严重性、中等严重性和 **低严重性邮件的数量**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="b2b10-169">将严重性级别设置为规则中的操作， (严重性级别审核此规则或 _SetAuditSeverity_) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="b2b10-170">有关详细信息，请参阅 Mail [flow rule actions in Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="b2b10-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="b2b10-171">**按 DLP Exchange 传输规则** 查看数据：受 DLP邮件流规则影响的高严重性、中等严重性和低严重性邮件的数量。 </span><span class="sxs-lookup"><span data-stu-id="b2b10-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="b2b10-172">下图下的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="b2b10-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-173">**Date**</span></span>
- <span data-ttu-id="b2b10-174">**DLP 策略** (**仅通过 DLP Exchange 传输规则** 查看) </span><span class="sxs-lookup"><span data-stu-id="b2b10-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="b2b10-175">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="b2b10-175">**Transport rule**</span></span>
- <span data-ttu-id="b2b10-176">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-176">**Subject**</span></span>
- <span data-ttu-id="b2b10-177">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="b2b10-177">**Sender address**</span></span>
- <span data-ttu-id="b2b10-178">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="b2b10-178">**Recipient address**</span></span>
- <span data-ttu-id="b2b10-179">**严重性**</span><span class="sxs-lookup"><span data-stu-id="b2b10-179">**Severity**</span></span>
- <span data-ttu-id="b2b10-180">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-180">**Direction**</span></span>

<span data-ttu-id="b2b10-181">通过单击"筛选器"，并选择出现的一个或多个以下值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b2b10-182">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-183">**方向**： **出站** 和 **入站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="b2b10-184">**严重性：\*\*\*\*高严重性**、**中等严重性** 和 **低严重性**</span><span class="sxs-lookup"><span data-stu-id="b2b10-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="b2b10-185">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="b2b10-186">转发报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="b2b10-187">转发 **报告现已** 在 EAC 中提供。</span><span class="sxs-lookup"><span data-stu-id="b2b10-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="b2b10-188">有关详细信息，请参阅新 [EAC 中的自动转发邮件报告](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b2b10-189">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-189">Mailflow status report</span></span>

<span data-ttu-id="b2b10-190">**邮件流状态** 报告是一个智能报告，它显示有关传入和传出电子邮件、垃圾邮件检测、恶意软件、标识为"良好"的电子邮件的信息，以及边缘上允许或阻止的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="b2b10-191">这是包含边缘保护信息的唯一报告，它显示了在 Exchange Online Protection (EOP) 允许进入服务之前阻止的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="b2b10-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b2b10-192">必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="b2b10-193">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-194">在"**电子邮件&协作报告**"页上，找到 **"邮件流状态摘要**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="b2b10-195">若要直接转到报告，请打开 <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

!["电子邮件和协作报告"页上的"邮件流&摘要"小组件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2b10-197">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="b2b10-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="b2b10-198">打开报表时，默认情况下 **会选中** "类型"选项卡。</span><span class="sxs-lookup"><span data-stu-id="b2b10-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="b2b10-199">默认情况下，此视图包含一个图表和一个使用以下筛选器配置的详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="b2b10-200">**UTC (日期)** 最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="b2b10-201">**邮件方向**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-201">**Mail direction**:</span></span>
  - <span data-ttu-id="b2b10-202">**入站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-202">**Inbound**</span></span>
  - <span data-ttu-id="b2b10-203">**出站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-203">**Outbound**</span></span>
  - <span data-ttu-id="b2b10-204">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="b2b10-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b2b10-205">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与 **入站** 和出站邮件 **分开计算)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="b2b10-206">**类型**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-206">**Type**:</span></span>
  - <span data-ttu-id="b2b10-207">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-207">**Good mail**</span></span>
  - <span data-ttu-id="b2b10-208">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-208">**Malware**</span></span>
  - <span data-ttu-id="b2b10-209">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-209">**Spam**</span></span>
  - <span data-ttu-id="b2b10-210">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="b2b10-210">**Edge protection**</span></span>
  - <span data-ttu-id="b2b10-211">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-211">**Rule messages**</span></span>
  - <span data-ttu-id="b2b10-212">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-212">**Phishing email**</span></span>
- <span data-ttu-id="b2b10-213">**域**： **全部**</span><span class="sxs-lookup"><span data-stu-id="b2b10-213">**Domain**: **All**</span></span>

<span data-ttu-id="b2b10-214">图表按 Type **值组织** 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="b2b10-215">可以通过单击"筛选器 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b10-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="b2b10-216">下图下的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="b2b10-217">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-217">**Direction**</span></span>
- <span data-ttu-id="b2b10-218">**类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-218">**Type**</span></span>
- <span data-ttu-id="b2b10-219">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="b2b10-219">**24 hours**</span></span>
- <span data-ttu-id="b2b10-220">**3 天**</span><span class="sxs-lookup"><span data-stu-id="b2b10-220">**3 days**</span></span>
- <span data-ttu-id="b2b10-221">**7 天**</span><span class="sxs-lookup"><span data-stu-id="b2b10-221">**7 days**</span></span>
- <span data-ttu-id="b2b10-222">**15 天**</span><span class="sxs-lookup"><span data-stu-id="b2b10-222">**15 days**</span></span>
- <span data-ttu-id="b2b10-223">**30 天**</span><span class="sxs-lookup"><span data-stu-id="b2b10-223">**30 days**</span></span>

<span data-ttu-id="b2b10-224">If you click **Choose a category for more details**， you can select from the following values：</span><span class="sxs-lookup"><span data-stu-id="b2b10-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="b2b10-225">**网络钓鱼电子邮件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b2b10-226">**电子邮件中的恶意软件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b2b10-227">**垃圾邮件检测**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="b2b10-228">**边缘阻止的垃圾邮件**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="b2b10-229">从类型视图导出</span><span class="sxs-lookup"><span data-stu-id="b2b10-229">Export from Type view</span></span>

<span data-ttu-id="b2b10-230">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b10-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b2b10-231">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="b2b10-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b2b10-232">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="b2b10-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2b10-233">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的类型视图](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2b10-235">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="b2b10-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="b2b10-236">如果单击" **方向"** 选项卡，则使用"类型"视图中 **的相同** 默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b10-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="b2b10-237">图表按 Direction **值** 组织。</span><span class="sxs-lookup"><span data-stu-id="b2b10-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="b2b10-238">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="b2b10-239">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b10-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b2b10-240">详细信息表包含"类型"视图中 **的相同** 信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="b2b10-241">" **选择类别"了解更多详细信息** 可用的选择和行为与"类型 **"视图相同** 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="b2b10-242">从方向视图导出</span><span class="sxs-lookup"><span data-stu-id="b2b10-242">Export from Direction view</span></span>

<span data-ttu-id="b2b10-243">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b10-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b2b10-244">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="b2b10-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b2b10-245">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="b2b10-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2b10-246">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的方向视图](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2b10-248">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="b2b10-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="b2b10-249">漏 **斗** 视图显示 Microsoft 的电子邮件威胁防护功能如何筛选组织中传入和传出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="b2b10-250">它提供有关总电子邮件计数以及配置的威胁防护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）如何影响此计数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="b2b10-251">如果单击" **漏斗"** 选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="b2b10-252">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b2b10-253">**方向**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-253">**Direction**:</span></span>
  - <span data-ttu-id="b2b10-254">**入站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-254">**Inbound**</span></span>
  - <span data-ttu-id="b2b10-255">**出站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-255">**Outbound**</span></span>
  - <span data-ttu-id="b2b10-256">**组织内部**：此计数用于租户内发送的邮件;即，发件人 abc@domain.com 收件人的邮件 xyz@domain.com (入站和出站邮件分开计算) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="b2b10-257">聚合视图和详细信息表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b2b10-258">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="b2b10-259">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b10-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b2b10-260">此图表显示按以下方式组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="b2b10-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="b2b10-261">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="b2b10-261">**Total email**</span></span>
- <span data-ttu-id="b2b10-262">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-262">**Email after edge protection**</span></span>
- <span data-ttu-id="b2b10-263">**传输规则之后的电子邮件 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="b2b10-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="b2b10-264">**反恶意软件后的电子邮件， 文件信誉， 文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="b2b10-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="b2b10-265">**反网络钓鱼后的电子邮件， URL 信誉， 品牌模拟， 反欺骗**</span><span class="sxs-lookup"><span data-stu-id="b2b10-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="b2b10-266">**反垃圾邮件、批量邮件筛选后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="b2b10-267">**用户和域模拟后的电子邮件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-268">**文件和 URL 触发后的电子邮件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-269">**在传递后保护或 URL 单击时间保护 (检测为安全)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="b2b10-270"><sup>\*</sup>仅 defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b2b10-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b2b10-271">若要查看由 EOP 或 Defender 单独筛选的电子邮件Office 365，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="b2b10-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="b2b10-272">详细信息表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="b2b10-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b2b10-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-273">**Date**</span></span>
- <span data-ttu-id="b2b10-274">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="b2b10-274">**Total email**</span></span>
- <span data-ttu-id="b2b10-275">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="b2b10-275">**Edge protection**</span></span>
- <span data-ttu-id="b2b10-276">**反恶意软件， 文件信誉， 文件类型阻止**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="b2b10-277">**文件信誉**：由于其他 Microsoft 客户标识的附加文件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="b2b10-278">**文件类型阻止**：由于邮件中标识的恶意文件类型而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b2b10-279">**反网络钓鱼， URL 信誉， 品牌模拟， 反欺骗**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="b2b10-280">**URL 信誉**：由于其他 Microsoft 客户标识的 URL 而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="b2b10-281">**品牌模拟**：由于来自已知品牌模拟发件人的邮件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="b2b10-282">**反欺骗**：由于邮件试图欺骗收件人所属的域或邮件发件人不属于的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="b2b10-283">**反垃圾邮件，批量邮件筛选**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="b2b10-284">**批量邮件筛选**：根据反垃圾邮件策略中的批量投诉级别 (BCL) 筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="b2b10-285">**Defender for (的用户和Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="b2b10-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b2b10-286">用户模拟：由于尝试模拟用户 (邮件发件人) （在反网络钓鱼策略的模拟保护设置中定义）而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="b2b10-287">**域模拟**：由于尝试模拟在反网络钓鱼策略的模拟保护设置中定义的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="b2b10-288">**Defender for (的文件和 URL Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="b2b10-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b2b10-289">**文件触发**：由附件策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="b2b10-290">**URL 触发**：按链接策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="b2b10-291">传递后保护和 **ZAP (ATP) 或 ZAP (EOP) ：** 零时差自动清除 (ZAP) 恶意软件、垃圾邮件和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="b2b10-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="b2b10-292">如果在详细信息表中选择一行，则电子邮件计数的进一步细分将显示在该飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="b2b10-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="b2b10-293">从漏斗视图导出</span><span class="sxs-lookup"><span data-stu-id="b2b10-293">Export from Funnel view</span></span>

<span data-ttu-id="b2b10-294">单击"选项 **"** 下的 **"** 导出"后，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b2b10-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="b2b10-295">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b2b10-296">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b2b10-297">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b2b10-298">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="b2b10-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b2b10-299">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="b2b10-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2b10-300">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的漏斗视图](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="b2b10-302">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="b2b10-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="b2b10-303">" **技术"** 视图类似于漏 **斗视图** ，提供有关配置的威胁防护功能的更具体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="b2b10-304">从图中，你可以看到如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="b2b10-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="b2b10-305">如果单击" **技术视图** "选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="b2b10-306">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b2b10-307">**方向**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-307">**Direction**:</span></span>
  - <span data-ttu-id="b2b10-308">**入站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-308">**Inbound**</span></span>
  - <span data-ttu-id="b2b10-309">**出站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-309">**Outbound**</span></span>
  - <span data-ttu-id="b2b10-310">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="b2b10-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b2b10-311">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与入站和出站邮件分开计数) </span><span class="sxs-lookup"><span data-stu-id="b2b10-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="b2b10-312">聚合视图和详细信息表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b2b10-313">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="b2b10-314">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b10-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b2b10-315">此图显示按以下类别组织的邮件：</span><span class="sxs-lookup"><span data-stu-id="b2b10-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b2b10-316">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="b2b10-316">**Total email**</span></span>
- <span data-ttu-id="b2b10-317">**边缘允许** 和 **边缘筛选**</span><span class="sxs-lookup"><span data-stu-id="b2b10-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="b2b10-318">**传输规则允许\*\*\*\*和传输规则筛选 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="b2b10-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="b2b10-319">**不是恶意软件\*\*\*\*、保险箱附件检测和** <sup>\*</sup> **反恶意软件引擎检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="b2b10-320">**非网络钓鱼\*\*\*\*、DMARC 失败**、**模拟检测** <sup>\*</sup> 、**欺骗检测和\*\*\*\*钓鱼检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="b2b10-321">**无需检测 URL 触发和** **URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-322">**不是垃圾邮件** 和  **垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="b2b10-323">**非恶意电子邮件\*\*\*\*、保险箱链接检测和** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="b2b10-324"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b2b10-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b2b10-325">将鼠标悬停在图表中的类别上时，可以看到该类别中的消息数。</span><span class="sxs-lookup"><span data-stu-id="b2b10-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="b2b10-326">详细信息表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="b2b10-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b2b10-327">**Date (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-327">**Date (UTC)**</span></span>
- <span data-ttu-id="b2b10-328">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="b2b10-328">**Total email**</span></span>
- <span data-ttu-id="b2b10-329">**已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="b2b10-329">**Edge filtered**</span></span>
- <span data-ttu-id="b2b10-330">**规则邮件**：由于邮件流规则而筛选 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="b2b10-331">**反恶意软件引擎** **，保险箱附件** <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="b2b10-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="b2b10-332">**DMARC， 模拟** <sup>\*</sup> ，**欺骗**，**网络钓鱼筛选**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="b2b10-333">**DMARC：** 由于邮件未通过 DMARC 身份验证检查而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="b2b10-334">**URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-335">**已筛选反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="b2b10-336">**ZAP 已删除**</span><span class="sxs-lookup"><span data-stu-id="b2b10-336">**ZAP removed**</span></span>
- <span data-ttu-id="b2b10-337">**按链接保险箱检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="b2b10-338"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b2b10-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b2b10-339">如果在详细信息表中选择一行，则电子邮件计数的进一步细分将显示在该飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="b2b10-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="b2b10-340">"从技术导出"视图</span><span class="sxs-lookup"><span data-stu-id="b2b10-340">Export from Tech view</span></span>

<span data-ttu-id="b2b10-341">单击" **导出"，** 在" **选项** "下，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b2b10-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="b2b10-342">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b2b10-343">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="b2b10-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b2b10-344">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b2b10-345">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="b2b10-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b2b10-346">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="b2b10-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b2b10-347">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的技术视图](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="b2b10-349">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-349">Malware detections report</span></span>

<span data-ttu-id="b2b10-350">恶意软件 **检测报告显示** 有关传入和传出电子邮件中的恶意软件检测信息， (EOP Exchange Online Protection检测到的) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="b2b10-351">有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="b2b10-352">聚合视图筛选器允许 90 天，而详细信息表筛选器仅允许 10 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="b2b10-353">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-354">在"**电子邮件&协作报告**"页上，找到 **"电子邮件中** 检测到的恶意软件"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="b2b10-355">若要直接转到报告，请打开 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![电子邮件小部件中的恶意软件检测（位于"电子邮件&协作报告"页面上）](../../media/malware-detections-widget.png)

<span data-ttu-id="b2b10-357">在"**恶意软件检测报告**"页上，可以通过单击"筛选器"并选择下列值之一来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="b2b10-358">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-359">**方向**：**入站\*\*\*\*和出站**</span><span class="sxs-lookup"><span data-stu-id="b2b10-359">**Direction**: **Inbound** and **Outbound**</span></span>

![电子邮件报告中的恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="b2b10-361">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b2b10-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-362">**Date**</span></span>
- <span data-ttu-id="b2b10-363">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="b2b10-363">**Sender address**</span></span>
- <span data-ttu-id="b2b10-364">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="b2b10-364">**Recipient address**</span></span>
- <span data-ttu-id="b2b10-365">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b2b10-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="b2b10-366">示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="b2b10-367">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-367">**Subject**</span></span>
- <span data-ttu-id="b2b10-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="b2b10-368">**Filename**</span></span>
- <span data-ttu-id="b2b10-369">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="b2b10-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="b2b10-370">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-370">Mail latency report</span></span>

<span data-ttu-id="b2b10-371">Defender **for** Office 365 中的邮件延迟报告包含有关组织中遇到的邮件传递和触发延迟的信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="b2b10-372">有关详细信息，请参阅邮件 [延迟报告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="b2b10-373">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="b2b10-374">垃圾邮件 **检测报告** 最终将消失。</span><span class="sxs-lookup"><span data-stu-id="b2b10-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="b2b10-375">威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="b2b10-376">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="b2b10-377">本文中所述的改进的欺骗检测报告在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="b2b10-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="b2b10-378">较旧版本的报告只显示"**良好邮件"和**"**捕获为垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="b2b10-379">欺骗 **检测报告显示** 有关由于欺骗被阻止或允许的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="b2b10-380">有关欺骗功能详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b2b10-381">报告聚合视图允许筛选 45 天，而详细信息视图仅 <sup>\*</sup> 允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="b2b10-382"><sup>\*</sup> 最终，你将能够使用最多 90 天的筛选。</span><span class="sxs-lookup"><span data-stu-id="b2b10-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="b2b10-383">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-384">在"**电子邮件&协作报告**"页上，找到 **"欺骗检测**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="b2b10-385">若要直接转到报告，请打开 <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

!["电子邮件和协作报告"页面上&欺骗检测小组件](../../media/spoof-detections-widget.png)

<span data-ttu-id="b2b10-387">该图表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-387">The chart shows the following information:</span></span>

- <span data-ttu-id="b2b10-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="b2b10-388">**Pass**</span></span>
- <span data-ttu-id="b2b10-389">**失败**</span><span class="sxs-lookup"><span data-stu-id="b2b10-389">**Fail**</span></span>
- <span data-ttu-id="b2b10-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="b2b10-390">**SoftPass**</span></span>
- <span data-ttu-id="b2b10-391">**无**</span><span class="sxs-lookup"><span data-stu-id="b2b10-391">**None**</span></span>
- <span data-ttu-id="b2b10-392">**其他**</span><span class="sxs-lookup"><span data-stu-id="b2b10-392">**Other**</span></span>

<span data-ttu-id="b2b10-393">当您将鼠标悬停在 (中) 的数据点时，可以看到检测到的欺骗邮件的个个和原因。</span><span class="sxs-lookup"><span data-stu-id="b2b10-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="b2b10-394">在"**欺骗邮件报告**"页上，可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b2b10-395">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-396">**结果**：</span><span class="sxs-lookup"><span data-stu-id="b2b10-396">**Result**:</span></span>
  - <span data-ttu-id="b2b10-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="b2b10-397">**Pass**</span></span>
  - <span data-ttu-id="b2b10-398">**失败**</span><span class="sxs-lookup"><span data-stu-id="b2b10-398">**Fail**</span></span>
  - <span data-ttu-id="b2b10-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="b2b10-399">**SoftPass**</span></span>
  - <span data-ttu-id="b2b10-400">**无**</span><span class="sxs-lookup"><span data-stu-id="b2b10-400">**None**</span></span>
  - <span data-ttu-id="b2b10-401">**其他**</span><span class="sxs-lookup"><span data-stu-id="b2b10-401">**Other**</span></span>
- <span data-ttu-id="b2b10-402">**欺骗类型**：**内部和外部**</span><span class="sxs-lookup"><span data-stu-id="b2b10-402">**Spoof type**: **Internal** and **External**</span></span>

![电子邮件门户中的欺骗邮件Microsoft 365 Defender页面](../../media/spoof-detections-report-page.png)

<span data-ttu-id="b2b10-404">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b2b10-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-405">**Date**</span></span>
- <span data-ttu-id="b2b10-406">**欺骗用户**</span><span class="sxs-lookup"><span data-stu-id="b2b10-406">**Spoofed user**</span></span>
- <span data-ttu-id="b2b10-407">**发送基础结构**</span><span class="sxs-lookup"><span data-stu-id="b2b10-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="b2b10-408">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-408">**Spoof type**</span></span>
- <span data-ttu-id="b2b10-409">**结果**</span><span class="sxs-lookup"><span data-stu-id="b2b10-409">**Result**</span></span>
- <span data-ttu-id="b2b10-410">**结果代码**</span><span class="sxs-lookup"><span data-stu-id="b2b10-410">**Result code**</span></span>
- <span data-ttu-id="b2b10-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="b2b10-411">**SPF**</span></span>
- <span data-ttu-id="b2b10-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="b2b10-412">**DKIM**</span></span>
- <span data-ttu-id="b2b10-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="b2b10-413">**DMARC**</span></span>
- <span data-ttu-id="b2b10-414">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="b2b10-414">**Message count**</span></span>

<span data-ttu-id="b2b10-415">有关复合身份验证结果代码详细信息，请参阅邮件中的[反垃圾邮件Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="b2b10-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="b2b10-416">提交报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-416">Submissions report</span></span>

<span data-ttu-id="b2b10-417">提交 **报告显示** 有关管理员已报告给 Microsoft 进行分析的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="b2b10-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="b2b10-418">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="b2b10-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="b2b10-419">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-420">在"**电子邮件&协作报告**"页上，找到 **"提交"，** 然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="b2b10-421">若要直接转到报告，请打开 <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="b2b10-422">若要转到管理 [门户中的管理员Microsoft 365 Defender，请单击](admin-submission.md)**"转到提交"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

!["电子邮件和协作报告"&"提交"小组件](../../media/submissions-report-widget.png)

<span data-ttu-id="b2b10-424">该图表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-424">The chart shows the following information:</span></span>

- <span data-ttu-id="b2b10-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="b2b10-425">**Pending**</span></span>
- <span data-ttu-id="b2b10-426">**已完成**</span><span class="sxs-lookup"><span data-stu-id="b2b10-426">**Completed**</span></span>

<span data-ttu-id="b2b10-427">在 **"提交"** 页上，可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b2b10-428">**报告的日期\*\*\*\*：开始时间和\*\*\*\*结束时间**</span><span class="sxs-lookup"><span data-stu-id="b2b10-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="b2b10-429">**提交类型**：**电子邮件\*\*\*\*、URL** 或 **文件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="b2b10-430">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="b2b10-430">**Submission ID**</span></span>
- <span data-ttu-id="b2b10-431">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="b2b10-431">**Network Message ID**</span></span>
- <span data-ttu-id="b2b10-432">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b2b10-432">**Sender**</span></span>
- <span data-ttu-id="b2b10-433">**名称**</span><span class="sxs-lookup"><span data-stu-id="b2b10-433">**Name**</span></span>
- <span data-ttu-id="b2b10-434">**提交者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-434">**Submitted by**</span></span>
- <span data-ttu-id="b2b10-435">**提交原因**：**非垃圾邮件**、**网络钓鱼\*\*\*\*、** 恶意软件或 **垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="b2b10-436">**重新扫描状态**： **挂起** 或 **已完成**</span><span class="sxs-lookup"><span data-stu-id="b2b10-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="b2b10-437">图形下方的详细信息表显示相同的信息，并且具有相同的组或自定义列选项与电子邮件和协作提交中的提交进行分析选项卡& \> **选项**。</span><span class="sxs-lookup"><span data-stu-id="b2b10-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="b2b10-438">有关详细信息，请参阅查看向 [Microsoft 提交的管理员](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Microsoft 365 Defender门户中的提交Microsoft 365 Defender页](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="b2b10-440">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-440">Threat protection status report</span></span>

<span data-ttu-id="b2b10-441">威胁 **防护状态报告** 在 EOP 和 Defender for Office 365;但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b10-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="b2b10-442">例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 SharePoint、OneDrive 和 Microsoft Teams 的 保险箱 附件检测到的恶意[文件的信息](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b2b10-443">该报告提供包含恶意内容的电子邮件（如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和 Defender 等 Office 365 功能（如 保险箱[链接](safe-links.md)[、保险箱](safe-attachments.md)附件和防钓鱼策略中的模拟保护功能）的计数。 [](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b2b10-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b2b10-444">您可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="b2b10-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="b2b10-445">**注意**：如果邮件发送给五个收件人，则我们将邮件计为五个不同的邮件，而不是一封邮件，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="b2b10-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="b2b10-446">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-447">在"**电子邮件&协作报告**"页上，找到 **"威胁防护状态**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="b2b10-448">若要直接转到报告，请打开以下 URL 之一：</span><span class="sxs-lookup"><span data-stu-id="b2b10-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="b2b10-449">Defender for Office 365：<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="b2b10-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="b2b10-450">EOP： <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="b2b10-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

!["电子邮件和协作报告"页面上的威胁&小组件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="b2b10-452">默认情况下，图表显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b10-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="b2b10-453">如果单击"**威胁\*\*\*\*防护状态报告**"页上的"筛选"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="b2b10-454">详细信息表允许筛选 30 天。</span><span class="sxs-lookup"><span data-stu-id="b2b10-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="b2b10-455">以下各节介绍了可用的视图。</span><span class="sxs-lookup"><span data-stu-id="b2b10-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="b2b10-456">按概述查看数据</span><span class="sxs-lookup"><span data-stu-id="b2b10-456">View data by Overview</span></span>

![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="b2b10-458">在 **"按概述查看数据"** 视图中，图表中显示了以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="b2b10-459">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-459">**Email malware**</span></span>
- <span data-ttu-id="b2b10-460">**电子邮件钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-460">**Email phish**</span></span>
- <span data-ttu-id="b2b10-461">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-461">**Content malware**</span></span>

<span data-ttu-id="b2b10-462">图表下方没有详细信息表。</span><span class="sxs-lookup"><span data-stu-id="b2b10-462">No details table is available below the chart.</span></span>

<span data-ttu-id="b2b10-463">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-464">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-465">**检测**：**电子邮件恶意软件\*\*\*\*、电子邮件钓鱼** 邮件或 **内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="b2b10-466">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b2b10-467">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b2b10-468">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b2b10-469">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-469">**Direction**</span></span>
- <span data-ttu-id="b2b10-470">**域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-470">**Domain**</span></span>
- <span data-ttu-id="b2b10-471">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-471">**Policy type**</span></span>

<span data-ttu-id="b2b10-472">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="b2b10-473">通过电子邮件钓鱼查看 \> 数据，按检测技术查看图表细目</span><span class="sxs-lookup"><span data-stu-id="b2b10-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="b2b10-475">在" **通过电子邮件查看数据" \>** 和"按检测技术查看图表细分 **"** 视图中，图表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="b2b10-476">**URL 恶意信誉** <sup>\*</sup> ：来自 Defender 的恶意 URL 信誉Office 365客户的其他Microsoft 365触发。</span><span class="sxs-lookup"><span data-stu-id="b2b10-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="b2b10-477">**高级筛选器**：基于机器学习的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="b2b10-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="b2b10-478">**常规筛选器**：基于分析员规则的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="b2b10-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="b2b10-479">**欺骗组织内部**：发件人正在尝试欺骗收件人域。</span><span class="sxs-lookup"><span data-stu-id="b2b10-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="b2b10-480">**欺骗外部域**：发件人正在尝试欺骗某些其他域。</span><span class="sxs-lookup"><span data-stu-id="b2b10-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="b2b10-481">**欺骗 DMARC：** 邮件上的 DMARC 身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="b2b10-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="b2b10-482">**模拟品牌**：模拟基于发件人的已知品牌。</span><span class="sxs-lookup"><span data-stu-id="b2b10-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="b2b10-483">**混合分析检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="b2b10-484">**文件信誉**</span><span class="sxs-lookup"><span data-stu-id="b2b10-484">**File reputation**</span></span>
- <span data-ttu-id="b2b10-485">**指纹匹配**</span><span class="sxs-lookup"><span data-stu-id="b2b10-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="b2b10-486">**URL 触发信誉**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-487">**URL 触发**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-488">**模拟用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-489">**模拟域** <sup>\*</sup> ：模拟客户拥有或定义的域。</span><span class="sxs-lookup"><span data-stu-id="b2b10-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="b2b10-490">**邮箱智能模拟** <sup>\*</sup> ：模拟由管理员定义或通过邮箱智能学习的用户。</span><span class="sxs-lookup"><span data-stu-id="b2b10-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="b2b10-491">**文件触发**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-492">**宣传活动**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="b2b10-493">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b2b10-494">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-494">**Date**</span></span>
- <span data-ttu-id="b2b10-495">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-495">**Subject**</span></span>
- <span data-ttu-id="b2b10-496">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-496">**Sender**</span></span>
- <span data-ttu-id="b2b10-497">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="b2b10-497">**Recipients**</span></span>
- <span data-ttu-id="b2b10-498">**检测者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-498">**Detected by**</span></span>
- <span data-ttu-id="b2b10-499">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="b2b10-499">**Delivery Status**</span></span>
- <span data-ttu-id="b2b10-500">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="b2b10-500">**Source of Compromise**</span></span>
- <span data-ttu-id="b2b10-501">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b2b10-501">**Tags**</span></span>

<span data-ttu-id="b2b10-502">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-503">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-504">**检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-504">**Detection**</span></span>
- <span data-ttu-id="b2b10-505">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b2b10-506">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-506">**Direction**</span></span>
- <span data-ttu-id="b2b10-507">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b2b10-508">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b2b10-509">**域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-509">**Domain**</span></span>
- <span data-ttu-id="b2b10-510">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-510">**Policy type**</span></span>
- <span data-ttu-id="b2b10-511">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="b2b10-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b2b10-512">**收件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-512">**Recipients**</span></span>

<span data-ttu-id="b2b10-513">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="b2b10-514">按电子邮件恶意软件查看 \> 数据，按检测技术查看图表细目</span><span class="sxs-lookup"><span data-stu-id="b2b10-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="b2b10-516">在" **通过电子邮件查看数据 \> "和** "按检测技术查看图表细分 **"** 视图中，图表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="b2b10-517">**文件触发** <sup>\*</sup> ：按附件保险箱检测。</span><span class="sxs-lookup"><span data-stu-id="b2b10-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="b2b10-518">**文件触发信誉** <sup>\*</sup> ：Defender 为安全触发生成的所有恶意Office 365信誉。</span><span class="sxs-lookup"><span data-stu-id="b2b10-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="b2b10-519">**文件信誉**</span><span class="sxs-lookup"><span data-stu-id="b2b10-519">**File reputation**</span></span>
- <span data-ttu-id="b2b10-520">**反恶意软件引擎** <sup>\*</sup> ：来自反恶意软件引擎的检测。</span><span class="sxs-lookup"><span data-stu-id="b2b10-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="b2b10-521">**反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b2b10-522">**URL 恶意声誉**</span><span class="sxs-lookup"><span data-stu-id="b2b10-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="b2b10-523">**URL 设置**</span><span class="sxs-lookup"><span data-stu-id="b2b10-523">**URL detonation**</span></span>
- <span data-ttu-id="b2b10-524">**URL 组织的信誉**</span><span class="sxs-lookup"><span data-stu-id="b2b10-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="b2b10-525">**市场活动**</span><span class="sxs-lookup"><span data-stu-id="b2b10-525">**Campaign**</span></span>

<span data-ttu-id="b2b10-526">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b2b10-527">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-527">**Date**</span></span>
- <span data-ttu-id="b2b10-528">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-528">**Subject**</span></span>
- <span data-ttu-id="b2b10-529">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-529">**Sender**</span></span>
- <span data-ttu-id="b2b10-530">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="b2b10-530">**Recipients**</span></span>
- <span data-ttu-id="b2b10-531">**检测者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-531">**Detected by**</span></span>
- <span data-ttu-id="b2b10-532">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="b2b10-532">**Delivery Status**</span></span>
- <span data-ttu-id="b2b10-533">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="b2b10-533">**Source of Compromise**</span></span>
- <span data-ttu-id="b2b10-534">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b2b10-534">**Tags**</span></span>

<span data-ttu-id="b2b10-535">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-536">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-537">**检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-537">**Detection**</span></span>
- <span data-ttu-id="b2b10-538">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b2b10-539">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-539">**Direction**</span></span>
- <span data-ttu-id="b2b10-540">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b2b10-541">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b2b10-542">**域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-542">**Domain**</span></span>
- <span data-ttu-id="b2b10-543">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-543">**Policy type**</span></span>
- <span data-ttu-id="b2b10-544">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="b2b10-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b2b10-545">**收件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-545">**Recipients**</span></span>

<span data-ttu-id="b2b10-546">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="b2b10-547">按策略类型和通过电子邮件查看数据或通过电子邮件恶意软件 \> 查看数据的图表 \> 细分</span><span class="sxs-lookup"><span data-stu-id="b2b10-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威胁防护状态报告中网络钓鱼电子邮件或恶意软件电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="b2b10-549">在 **"按策略类型划分** 的图表细分"和 **" \>** 通过电子邮件查看数据"或"通过电子邮件查看恶意软件数据"视图中，图表中显示了以下信息： **\>**</span><span class="sxs-lookup"><span data-stu-id="b2b10-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="b2b10-550">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-550">**Anti-malware**</span></span>
- <span data-ttu-id="b2b10-551">**保险箱附件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b2b10-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="b2b10-552">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="b2b10-552">**Anti-phish**</span></span>
- <span data-ttu-id="b2b10-553">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-553">**Anti-spam**</span></span>
- <span data-ttu-id="b2b10-554">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="b2b10-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="b2b10-555">**其他**</span><span class="sxs-lookup"><span data-stu-id="b2b10-555">**Others**</span></span>

<span data-ttu-id="b2b10-556">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b2b10-557">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-557">**Date**</span></span>
- <span data-ttu-id="b2b10-558">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-558">**Subject**</span></span>
- <span data-ttu-id="b2b10-559">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-559">**Sender**</span></span>
- <span data-ttu-id="b2b10-560">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="b2b10-560">**Recipients**</span></span>
- <span data-ttu-id="b2b10-561">**检测者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-561">**Detected by**</span></span>
- <span data-ttu-id="b2b10-562">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="b2b10-562">**Delivery Status**</span></span>
- <span data-ttu-id="b2b10-563">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="b2b10-563">**Source of Compromise**</span></span>
- <span data-ttu-id="b2b10-564">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b2b10-564">**Tags**</span></span>

<span data-ttu-id="b2b10-565">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-566">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-567">**检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-567">**Detection**</span></span>
- <span data-ttu-id="b2b10-568">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b2b10-569">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-569">**Direction**</span></span>
- <span data-ttu-id="b2b10-570">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b2b10-571">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b2b10-572">**域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-572">**Domain**</span></span>
- <span data-ttu-id="b2b10-573">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-573">**Policy type**</span></span>
- <span data-ttu-id="b2b10-574">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="b2b10-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b2b10-575">**收件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-575">**Recipients**</span></span>

<span data-ttu-id="b2b10-576">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="b2b10-577">按传递状态和通过电子邮件查看数据或通过电子邮件恶意软件 \> 查看数据的图表 \> 细分</span><span class="sxs-lookup"><span data-stu-id="b2b10-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威胁防护状态报告中的网络钓鱼电子邮件和恶意软件电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="b2b10-579">在 **"按传递状态分类"** 和 **" \>** 通过电子邮件查看数据"或"通过电子邮件查看恶意软件数据"视图中，图表中显示了以下信息： **\>**</span><span class="sxs-lookup"><span data-stu-id="b2b10-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="b2b10-580">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="b2b10-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="b2b10-581">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="b2b10-582">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="b2b10-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="b2b10-583">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="b2b10-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="b2b10-584">**转发**</span><span class="sxs-lookup"><span data-stu-id="b2b10-584">**Forwarded**</span></span>
- <span data-ttu-id="b2b10-585">**本地服务器：已传递**</span><span class="sxs-lookup"><span data-stu-id="b2b10-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="b2b10-586">**隔离**</span><span class="sxs-lookup"><span data-stu-id="b2b10-586">**Quarantine**</span></span>
- <span data-ttu-id="b2b10-587">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="b2b10-587">**Delivery failed**</span></span>
- <span data-ttu-id="b2b10-588">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="b2b10-588">**Dropped**</span></span>

<span data-ttu-id="b2b10-589">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b2b10-590">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-590">**Date**</span></span>
- <span data-ttu-id="b2b10-591">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-591">**Subject**</span></span>
- <span data-ttu-id="b2b10-592">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-592">**Sender**</span></span>
- <span data-ttu-id="b2b10-593">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="b2b10-593">**Recipients**</span></span>
- <span data-ttu-id="b2b10-594">**检测者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-594">**Detected by**</span></span>
- <span data-ttu-id="b2b10-595">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="b2b10-595">**Delivery Status**</span></span>
- <span data-ttu-id="b2b10-596">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="b2b10-596">**Source of Compromise**</span></span>
- <span data-ttu-id="b2b10-597">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b2b10-597">**Tags**</span></span>

<span data-ttu-id="b2b10-598">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-599">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-600">**检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-600">**Detection**</span></span>
- <span data-ttu-id="b2b10-601">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b2b10-602">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-602">**Direction**</span></span>
- <span data-ttu-id="b2b10-603">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b2b10-604">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b2b10-605">**域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-605">**Domain**</span></span>
- <span data-ttu-id="b2b10-606">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-606">**Policy type**</span></span>
- <span data-ttu-id="b2b10-607">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="b2b10-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b2b10-608">**收件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-608">**Recipients**</span></span>

<span data-ttu-id="b2b10-609">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="b2b10-610">按内容恶意软件查看 \> 数据</span><span class="sxs-lookup"><span data-stu-id="b2b10-610">View data by Content \> Malware</span></span>

![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="b2b10-612">在 **"按内容恶意软件查看 \>** 数据"视图中，以下信息显示在 Microsoft Defender for Office 365图表中：</span><span class="sxs-lookup"><span data-stu-id="b2b10-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="b2b10-613">**反恶意软件引擎**：Sharepoint、OneDrive 和 Microsoft Teams 中内置的病毒检测 [检测到的恶意](virus-detection-in-spo.md)Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b2b10-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="b2b10-614">**文件触发**：附件检测到的恶意保险箱 [文件SharePoint、OneDrive和Microsoft Teams。](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b2b10-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b2b10-615">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b2b10-616">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-617">**位置**</span><span class="sxs-lookup"><span data-stu-id="b2b10-617">**Location**</span></span>
- <span data-ttu-id="b2b10-618">**检测者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-618">**Detected by**</span></span>
- <span data-ttu-id="b2b10-619">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="b2b10-619">**Malware name**</span></span>

<span data-ttu-id="b2b10-620">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-621">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-622">**检测\*\*\*\*：反恶意软件引擎** 或 **文件触发**</span><span class="sxs-lookup"><span data-stu-id="b2b10-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="b2b10-623">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="b2b10-624">按系统覆盖查看数据</span><span class="sxs-lookup"><span data-stu-id="b2b10-624">View data by System override</span></span>

![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="b2b10-626">在" **按系统覆盖查看数据"视图中** ，图表中显示了以下替代原因信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="b2b10-627">**本地跳过**</span><span class="sxs-lookup"><span data-stu-id="b2b10-627">**On-premises skip**</span></span>
- <span data-ttu-id="b2b10-628">**IP 允许**</span><span class="sxs-lookup"><span data-stu-id="b2b10-628">**IP allow**</span></span>
- <span data-ttu-id="b2b10-629">**Exchange邮件传输规则 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="b2b10-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="b2b10-630">**组织允许的发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="b2b10-631">**组织允许的域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="b2b10-632">**ZAP 未启用**</span><span class="sxs-lookup"><span data-stu-id="b2b10-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="b2b10-633">**未启用垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="b2b10-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="b2b10-634">**用户保险箱发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-634">**User Safe Sender**</span></span>
- <span data-ttu-id="b2b10-635">**用户保险箱域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-635">**User Safe Domain**</span></span>

<span data-ttu-id="b2b10-636">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b2b10-637">**Date**</span><span class="sxs-lookup"><span data-stu-id="b2b10-637">**Date**</span></span>
- <span data-ttu-id="b2b10-638">**主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-638">**Subject**</span></span>
- <span data-ttu-id="b2b10-639">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-639">**Sender**</span></span>
- <span data-ttu-id="b2b10-640">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="b2b10-640">**Recipients**</span></span>
- <span data-ttu-id="b2b10-641">**检测者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-641">**Detected by**</span></span>
- <span data-ttu-id="b2b10-642">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="b2b10-642">**Delivery Status**</span></span>
- <span data-ttu-id="b2b10-643">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="b2b10-643">**Source of Compromise**</span></span>
- <span data-ttu-id="b2b10-644">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b2b10-644">**Tags**</span></span>

<span data-ttu-id="b2b10-645">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b2b10-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b2b10-646">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b2b10-647">**检测**</span><span class="sxs-lookup"><span data-stu-id="b2b10-647">**Detection**</span></span>
- <span data-ttu-id="b2b10-648">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="b2b10-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b2b10-649">**方向**</span><span class="sxs-lookup"><span data-stu-id="b2b10-649">**Direction**</span></span>
- <span data-ttu-id="b2b10-650">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b2b10-651">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b2b10-652">**域**</span><span class="sxs-lookup"><span data-stu-id="b2b10-652">**Domain**</span></span>
- <span data-ttu-id="b2b10-653">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="b2b10-653">**Policy type**</span></span>
- <span data-ttu-id="b2b10-654">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="b2b10-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b2b10-655">**收件人**</span><span class="sxs-lookup"><span data-stu-id="b2b10-655">**Recipients**</span></span>

<span data-ttu-id="b2b10-656">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b2b10-657"><sup>\*</sup>仅 defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b2b10-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="b2b10-658">热门恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-658">Top malware report</span></span>

<span data-ttu-id="b2b10-659">" **热门恶意软件** "报告显示 [EOP](anti-malware-protection.md)中的反恶意软件保护检测到的各种恶意软件。</span><span class="sxs-lookup"><span data-stu-id="b2b10-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="b2b10-660">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-661">在"**电子邮件&协作报告**"页上，找到 **"热门恶意软件**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="b2b10-662">若要直接转到报告，请打开 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

!["电子邮件和协作报告"页面上&恶意软件小组件](../../media/top-malware-report-widget.png)

<span data-ttu-id="b2b10-664">当您将鼠标悬停在饼图中的一个浮点上时，可以看到某种恶意软件的名称，以及检测到具有该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="b2b10-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="b2b10-665">在" **热门恶意软件报告** "页上，报表页上将显示饼图的较大版本。图表下面的详细信息表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="b2b10-666">**热门恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-666">**Top malware**</span></span>
- <span data-ttu-id="b2b10-667">**Count**</span><span class="sxs-lookup"><span data-stu-id="b2b10-667">**Count**</span></span>

<span data-ttu-id="b2b10-668">If you click **Filter**， you can specify a date range with **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="b2b10-670">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-670">URL threat protection report</span></span>

<span data-ttu-id="b2b10-671">Microsoft Defender for Office 365 中提供了 **URL** 威胁防护报告。</span><span class="sxs-lookup"><span data-stu-id="b2b10-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b2b10-672">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="b2b10-673">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2b10-674">为了使用户 **报告的消息** 报告正常工作，必须为用户报告的环境启用Microsoft 365日志记录。</span><span class="sxs-lookup"><span data-stu-id="b2b10-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="b2b10-675">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="b2b10-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="b2b10-676">有关详细信息，请参阅打开[Microsoft 365 审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="b2b10-677">用户 **报告的邮件** 报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="b2b10-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="b2b10-678">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="b2b10-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b2b10-679">在"**电子邮件&协作报告**"页上，找到 **"用户报告的邮件**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="b2b10-680">若要直接转到报告，请打开 <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="b2b10-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="b2b10-681">若要转到管理 [门户中的管理员Microsoft 365 Defender，请单击](admin-submission.md)**"转到提交"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

!["电子邮件和协作报告"页上&"用户报告的邮件"小组件](../../media/user-reported-messages-widget.png)

<span data-ttu-id="b2b10-683">在"**用户报告的消息**"页上，可以通过单击"筛选器"，在出现的飞出中选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="b2b10-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b2b10-684">**报告的日期\*\*\*\*：开始时间和\*\*\*\*结束时间**</span><span class="sxs-lookup"><span data-stu-id="b2b10-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="b2b10-685">**报告者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-685">**Reported by**</span></span>
- <span data-ttu-id="b2b10-686">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-686">**Email subject**</span></span>
- <span data-ttu-id="b2b10-687">**邮件报告 ID**</span><span class="sxs-lookup"><span data-stu-id="b2b10-687">**Message reported ID**</span></span>
- <span data-ttu-id="b2b10-688">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="b2b10-688">**Network Message ID**</span></span>
- <span data-ttu-id="b2b10-689">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b2b10-689">**Sender**</span></span>
- <span data-ttu-id="b2b10-690">**报告的原因**</span><span class="sxs-lookup"><span data-stu-id="b2b10-690">**Reported reason**</span></span>
  - <span data-ttu-id="b2b10-691">**非垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-691">**Not junk**</span></span>
  - <span data-ttu-id="b2b10-692">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="b2b10-692">**Phish**</span></span>
  - <span data-ttu-id="b2b10-693">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-693">**Spam**</span></span>
- <span data-ttu-id="b2b10-694">**网络钓鱼模拟**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="b2b10-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="b2b10-695">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="b2b10-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b2b10-696">若要对条目进行分组，请单击 **"分组** "，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b2b10-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="b2b10-697">**无**</span><span class="sxs-lookup"><span data-stu-id="b2b10-697">**None**</span></span>
- <span data-ttu-id="b2b10-698">**原因**</span><span class="sxs-lookup"><span data-stu-id="b2b10-698">**Reason**</span></span>
- <span data-ttu-id="b2b10-699">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b2b10-699">**Sender**</span></span>
- <span data-ttu-id="b2b10-700">**报告者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-700">**Reported by**</span></span>
- <span data-ttu-id="b2b10-701">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="b2b10-701">**Rescan result**</span></span>
- <span data-ttu-id="b2b10-702">**网络钓鱼模拟**</span><span class="sxs-lookup"><span data-stu-id="b2b10-702">**Phish simulation**</span></span>

![用户报告的邮件报告](../../media/user-reported-messages-report.png)

<span data-ttu-id="b2b10-704">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="b2b10-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b2b10-705">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="b2b10-705">**Email subject**</span></span>
- <span data-ttu-id="b2b10-706">**报告者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-706">**Reported by**</span></span>
- <span data-ttu-id="b2b10-707">**报告的日期**</span><span class="sxs-lookup"><span data-stu-id="b2b10-707">**Date reported**</span></span>
- <span data-ttu-id="b2b10-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b2b10-708">**Sender**</span></span>
- <span data-ttu-id="b2b10-709">**报告的原因**</span><span class="sxs-lookup"><span data-stu-id="b2b10-709">**Reported reason**</span></span>
- <span data-ttu-id="b2b10-710">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="b2b10-710">**Rescan result**</span></span>
- <span data-ttu-id="b2b10-711">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b2b10-711">**Tags**</span></span>

<span data-ttu-id="b2b10-712">若要将邮件提交给 Microsoft 进行分析，请从表中选择邮件条目，单击"提交给 **Microsoft** 进行分析"，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b2b10-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="b2b10-713">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="b2b10-713">**Report clean**</span></span>
- <span data-ttu-id="b2b10-714">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="b2b10-714">**Report phishing**</span></span>
- <span data-ttu-id="b2b10-715">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b2b10-715">**Report malware**</span></span>
- <span data-ttu-id="b2b10-716">**报告垃圾邮件**'</span><span class="sxs-lookup"><span data-stu-id="b2b10-716">**Report spam**'</span></span>
- <span data-ttu-id="b2b10-717">**触发 Defender** (调查Office 365) </span><span class="sxs-lookup"><span data-stu-id="b2b10-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b2b10-718">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="b2b10-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b2b10-719">若要查看和使用本文中所述的报告，你需要是本文门户中以下角色组之一Microsoft 365 Defender成员：</span><span class="sxs-lookup"><span data-stu-id="b2b10-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="b2b10-720">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="b2b10-720">**Organization Management**</span></span>
- <span data-ttu-id="b2b10-721">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="b2b10-721">**Security Administrator**</span></span>
- <span data-ttu-id="b2b10-722">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-722">**Security Reader**</span></span>
- <span data-ttu-id="b2b10-723">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="b2b10-723">**Global Reader**</span></span>

<span data-ttu-id="b2b10-724">有关详细信息，请参阅应用程序[门户中Microsoft 365 Defender权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b2b10-725">**注意**：向 Microsoft 365 管理中心 中的相应 Azure Active Directory 角色添加用户会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 </span><span class="sxs-lookup"><span data-stu-id="b2b10-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b2b10-726">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="b2b10-727">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="b2b10-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="b2b10-728">如果报告中未显示数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="b2b10-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="b2b10-729">若要了解更多信息，请参阅 [防范威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="b2b10-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2b10-730">相关主题</span><span class="sxs-lookup"><span data-stu-id="b2b10-730">Related topics</span></span>

[<span data-ttu-id="b2b10-731">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="b2b10-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="b2b10-732">智能报表和 Microsoft 365 Defender见解</span><span class="sxs-lookup"><span data-stu-id="b2b10-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b2b10-733">在邮件门户中查看Microsoft 365 Defender报告</span><span class="sxs-lookup"><span data-stu-id="b2b10-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="b2b10-734">查看 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b2b10-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
