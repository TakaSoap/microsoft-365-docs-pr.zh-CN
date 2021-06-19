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
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029530"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="4d6ca-103">在 Microsoft 365 Defender 门户中查看电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4d6ca-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-104">**Applies to**</span></span>
- [<span data-ttu-id="4d6ca-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4d6ca-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4d6ca-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4d6ca-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4d6ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d6ca-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4d6ca-108">Microsoft 365 Defender 门户中提供了各种报告，可帮助你了解 Microsoft 365 中的电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护 <https://security.microsoft.com> 你的组织。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="4d6ca-109">如果你拥有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在 Microsoft 365 Defender 门户中查看这些报告，方式为：查看报告电子邮件&协作 电子邮件& \>  \> **协作报告**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-110">若要直接转到"电子邮件& **协作报告"** 页，请打开 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 门户中的"电子邮件&协作报告"页面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="4d6ca-112">"电子邮件和协作报告 **"&一些报告** 需要 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4d6ca-113">有关这些报告的信息，请参阅在 [Microsoft 365](view-reports-for-mdo.md)Defender 门户中查看适用于 Office 365 的 Defender 报告。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="4d6ca-114">与邮件流相关的报告现在位于 Exchange 管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="4d6ca-115">有关这些报告详细信息，请参阅新 Exchange 管理中心 [中的邮件流报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="4d6ca-116">遭到入侵的用户报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="4d6ca-117">此报告适用于具有 Exchange Online 邮箱的 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="4d6ca-118">它不适用于独立 Exchange Online Protection (EOP) 组织。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="4d6ca-119">"**遭到入侵的用户**"报告显示过去 7 天内标记为"可疑"或"受限"的用户帐户数量。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="4d6ca-120">其中任一状态的帐户存在问题，甚至受到威胁。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="4d6ca-121">通过频繁使用，可以使用报告来发现可疑或受限帐户的峰值甚至趋势。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="4d6ca-122">有关遭到入侵的用户详细信息，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["电子邮件和协作报告"页上的"遭到入侵&小组件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="4d6ca-124">聚合视图显示过去 90 天的数据，而详细信息视图显示最近 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="4d6ca-125">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-126">在"**电子邮件&协作报告**"页上，找到 **"遭到** 入侵的用户"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-127">若要直接转到报告，请打开 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="4d6ca-128">在"**遭到入侵** 的用户"页上，可以同时筛选图表和详细信息表，方法是单击"筛选器"，在出现的标注中选择以下一个或多个值：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d6ca-129">**DATE (UTC)**： **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="4d6ca-130">**活动**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-130">**Activity**:</span></span>
  - <span data-ttu-id="4d6ca-131">**可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="4d6ca-132">**受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="4d6ca-133">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

!["泄露的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="4d6ca-135">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d6ca-136">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-136">**Creation time**</span></span>
- <span data-ttu-id="4d6ca-137">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-137">**User ID**</span></span>
- <span data-ttu-id="4d6ca-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="4d6ca-139">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-139">Exchange transport rule report</span></span>

<span data-ttu-id="4d6ca-140">**Exchange 传输规则** 报告显示邮件流规则对组织中 (传输规则) 传入和传出邮件的影响。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="4d6ca-141">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-142">在"**电子邮件&协作报告**"页上，找到 **"Exchange 传输** 规则"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-143">若要直接转到报告，请打开 <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

!["电子邮件和协作报告"页面上的"Exchange 传输&小组件](../../media/transport-rule-report-widget.png)

<span data-ttu-id="4d6ca-145">在 **"Exchange 传输规则报告** "页上，以下各节介绍了可用的图表和数据。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="4d6ca-146">按方向细分图表</span><span class="sxs-lookup"><span data-stu-id="4d6ca-146">Chart breakdown by Direction</span></span>

![Exchange 传输规则报告中 Exchange 传输规则的方向视图](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="4d6ca-148">如果选择" **按方向细分图表"，** 则以下图表可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="4d6ca-149">**按 Exchange 传输规则查看数据**：受邮件流规则影响的入站和出站邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="4d6ca-150">**按 DLP Exchange 传输规则查看数据**：受DLP 和邮件流规则中的数据丢失防护 () 邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="4d6ca-151">下图下的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="4d6ca-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-152">**Date**</span></span>
- <span data-ttu-id="4d6ca-153">**DLP 策略** (**仅通过 DLP Exchange 传输规则** 查看) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="4d6ca-154">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-154">**Transport rule**</span></span>
- <span data-ttu-id="4d6ca-155">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-155">**Subject**</span></span>
- <span data-ttu-id="4d6ca-156">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-156">**Sender address**</span></span>
- <span data-ttu-id="4d6ca-157">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-157">**Recipient address**</span></span>
- <span data-ttu-id="4d6ca-158">**严重性**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-158">**Severity**</span></span>
- <span data-ttu-id="4d6ca-159">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-159">**Direction**</span></span>

<span data-ttu-id="4d6ca-160">通过单击"筛选器"，并选择出现的一个或多个以下值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d6ca-161">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-162">**方向**： **出站** 和 **入站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="4d6ca-163">**严重性：\*\*\*\*高严重性**、**中等严重性** 和 **低严重性**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="4d6ca-164">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="4d6ca-165">按严重性分类的图表</span><span class="sxs-lookup"><span data-stu-id="4d6ca-165">Chart breakdown by Severity</span></span>

![Exchange 传输规则报告中 Exchange 传输规则的严重性视图](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="4d6ca-167">如果选择" **按严重性划分图表细分"，** 则以下图表可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="4d6ca-168">**按 Exchange 传输规则查看数据**：高严重性、中等严重性和 **低严重性邮件的数量**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="4d6ca-169">将严重性级别设置为规则中的操作， (严重性级别审核此规则或 _SetAuditSeverity_) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="4d6ca-170">有关详细信息，请参阅 Mail [flow rule actions in Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="4d6ca-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="4d6ca-171">**按 DLP Exchange 传输规则** 查看数据：受 DLP邮件流规则影响的高严重性、中等严重性和低严重性邮件的数量。 </span><span class="sxs-lookup"><span data-stu-id="4d6ca-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="4d6ca-172">下图下的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="4d6ca-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-173">**Date**</span></span>
- <span data-ttu-id="4d6ca-174">**DLP 策略** (**仅通过 DLP Exchange 传输规则** 查看) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="4d6ca-175">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-175">**Transport rule**</span></span>
- <span data-ttu-id="4d6ca-176">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-176">**Subject**</span></span>
- <span data-ttu-id="4d6ca-177">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-177">**Sender address**</span></span>
- <span data-ttu-id="4d6ca-178">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-178">**Recipient address**</span></span>
- <span data-ttu-id="4d6ca-179">**严重性**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-179">**Severity**</span></span>
- <span data-ttu-id="4d6ca-180">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-180">**Direction**</span></span>

<span data-ttu-id="4d6ca-181">通过单击"筛选器"，并选择出现的一个或多个以下值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d6ca-182">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-183">**方向**： **出站** 和 **入站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="4d6ca-184">**严重性：\*\*\*\*高严重性**、**中等严重性** 和 **低严重性**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="4d6ca-185">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="4d6ca-186">转发报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="4d6ca-187">转发 **报告现已** 在 EAC 中提供。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="4d6ca-188">有关详细信息，请参阅新 [EAC 中的自动转发邮件报告](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="4d6ca-189">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-189">Mailflow status report</span></span>

<span data-ttu-id="4d6ca-190">**邮件流状态** 报告是一个智能报告，它显示有关传入和传出电子邮件、垃圾邮件检测、恶意软件、标识为"良好"的电子邮件的信息，以及边缘上允许或阻止的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="4d6ca-191">这是包含边缘保护信息的唯一报告，它显示了在 Exchange Online Protection (EOP) 允许进入服务之前阻止的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="4d6ca-192">必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="4d6ca-193">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-194">在"**电子邮件&协作报告**"页上，找到 **"邮件流状态摘要**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-195">若要直接转到报告，请打开 <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

!["电子邮件和协作报告"页上的"邮件流&摘要"小组件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d6ca-197">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="4d6ca-197">Type view for the Mailflow status report</span></span>

![邮件流状态报告中的类型视图](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="4d6ca-199">在" **邮件流状态报告** "页上， **默认情况下选择** "类型"选项卡。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="4d6ca-200">默认情况下，此视图包含一个图表和一个使用以下筛选器配置的详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="4d6ca-201">**UTC (日期)** 最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="4d6ca-202">**邮件方向**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-202">**Mail direction**:</span></span>
  - <span data-ttu-id="4d6ca-203">**入站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-203">**Inbound**</span></span>
  - <span data-ttu-id="4d6ca-204">**出站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-204">**Outbound**</span></span>
  - <span data-ttu-id="4d6ca-205">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="4d6ca-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="4d6ca-206">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与 **入站** 和出站邮件 **分开计算)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="4d6ca-207">**类型**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-207">**Type**:</span></span>
  - <span data-ttu-id="4d6ca-208">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-208">**Good mail**</span></span>
  - <span data-ttu-id="4d6ca-209">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-209">**Malware**</span></span>
  - <span data-ttu-id="4d6ca-210">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-210">**Spam**</span></span>
  - <span data-ttu-id="4d6ca-211">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-211">**Edge protection**</span></span>
  - <span data-ttu-id="4d6ca-212">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-212">**Rule messages**</span></span>
  - <span data-ttu-id="4d6ca-213">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-213">**Phishing email**</span></span>
- <span data-ttu-id="4d6ca-214">**域**： **全部**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-214">**Domain**: **All**</span></span>

<span data-ttu-id="4d6ca-215">图表按 Type **值组织** 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="4d6ca-216">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="4d6ca-217">下图下的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="4d6ca-218">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-218">**Direction**</span></span>
- <span data-ttu-id="4d6ca-219">**类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-219">**Type**</span></span>
- <span data-ttu-id="4d6ca-220">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-220">**24 hours**</span></span>
- <span data-ttu-id="4d6ca-221">**3 天**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-221">**3 days**</span></span>
- <span data-ttu-id="4d6ca-222">**7 天**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-222">**7 days**</span></span>
- <span data-ttu-id="4d6ca-223">**15 天**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-223">**15 days**</span></span>
- <span data-ttu-id="4d6ca-224">**30 天**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-224">**30 days**</span></span>

<span data-ttu-id="4d6ca-225">If you click **Choose a category for more details**， you can select from the following values：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="4d6ca-226">**网络钓鱼电子邮件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4d6ca-227">**电子邮件中的恶意软件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4d6ca-228">**垃圾邮件检测**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="4d6ca-229">**边缘阻止的垃圾邮件**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="4d6ca-230">从类型视图导出</span><span class="sxs-lookup"><span data-stu-id="4d6ca-230">Export from Type view</span></span>

<span data-ttu-id="4d6ca-231">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4d6ca-232">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4d6ca-233">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d6ca-234">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d6ca-235">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="4d6ca-235">Direction view for the Mailflow status report</span></span>

![邮件流状态报告中的方向视图](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="4d6ca-237">如果单击" **方向"** 选项卡，则使用"类型"视图中 **的相同** 默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="4d6ca-238">图表按 Direction **值** 组织。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="4d6ca-239">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="4d6ca-240">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="4d6ca-241">详细信息表包含"类型"视图中 **的相同** 信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="4d6ca-242">" **选择类别"了解更多详细信息** 可用的选择和行为与"类型 **"视图相同** 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="4d6ca-243">从方向视图导出</span><span class="sxs-lookup"><span data-stu-id="4d6ca-243">Export from Direction view</span></span>

<span data-ttu-id="4d6ca-244">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4d6ca-245">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4d6ca-246">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d6ca-247">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d6ca-248">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="4d6ca-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="4d6ca-249">漏 **斗** 视图显示 Microsoft 的电子邮件威胁防护功能如何筛选组织中传入和传出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="4d6ca-250">它提供有关总电子邮件计数以及配置的威胁防护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）如何影响此计数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![邮件流状态报告中的漏斗视图](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="4d6ca-252">如果单击" **漏斗"** 选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="4d6ca-253">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="4d6ca-254">**方向**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-254">**Direction**:</span></span>
  - <span data-ttu-id="4d6ca-255">**入站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-255">**Inbound**</span></span>
  - <span data-ttu-id="4d6ca-256">**出站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-256">**Outbound**</span></span>
  - <span data-ttu-id="4d6ca-257">**组织内部**：此计数用于租户内发送的邮件;即，发件人 abc@domain.com 收件人的邮件 xyz@domain.com (入站和出站邮件分开计算) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="4d6ca-258">聚合视图和详细信息表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="4d6ca-259">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="4d6ca-260">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="4d6ca-261">此图表显示按以下方式组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="4d6ca-262">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-262">**Total email**</span></span>
- <span data-ttu-id="4d6ca-263">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-263">**Email after edge protection**</span></span>
- <span data-ttu-id="4d6ca-264">**传输规则之后的电子邮件 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="4d6ca-265">**反恶意软件后的电子邮件， 文件信誉， 文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="4d6ca-266">**反网络钓鱼后的电子邮件， URL 信誉， 品牌模拟， 反欺骗**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="4d6ca-267">**反垃圾邮件、批量邮件筛选后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="4d6ca-268">**用户和域模拟后的电子邮件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-269">**文件和 URL 触发后的电子邮件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-270">**在传递后保护或 URL 单击时间保护 (检测为安全)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="4d6ca-271"><sup>\*</sup>仅 defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d6ca-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="4d6ca-272">若要查看由 EOP 或 Defender 单独筛选的电子邮件Office 365，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="4d6ca-273">详细信息表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="4d6ca-274">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-274">**Date**</span></span>
- <span data-ttu-id="4d6ca-275">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-275">**Total email**</span></span>
- <span data-ttu-id="4d6ca-276">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-276">**Edge protection**</span></span>
- <span data-ttu-id="4d6ca-277">**反恶意软件， 文件信誉， 文件类型阻止**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="4d6ca-278">**文件信誉**：由于其他 Microsoft 客户标识的附加文件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="4d6ca-279">**文件类型阻止**：由于邮件中标识的恶意文件类型而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="4d6ca-280">**反网络钓鱼， URL 信誉， 品牌模拟， 反欺骗**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="4d6ca-281">**URL 信誉**：由于其他 Microsoft 客户标识的 URL 而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="4d6ca-282">**品牌模拟**：由于来自已知品牌模拟发件人的邮件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="4d6ca-283">**反欺骗**：由于邮件试图欺骗收件人所属的域或邮件发件人不属于的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="4d6ca-284">**反垃圾邮件，批量邮件筛选**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="4d6ca-285">**批量邮件筛选**：根据反垃圾邮件策略中的批量投诉级别 (BCL) 筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="4d6ca-286">**Defender for (的用户和Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="4d6ca-287">用户模拟：由于尝试模拟用户 (邮件发件人) （在反网络钓鱼策略的模拟保护设置中定义）而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="4d6ca-288">**域模拟**：由于尝试模拟在反网络钓鱼策略的模拟保护设置中定义的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="4d6ca-289">**Defender for (的文件和 URL Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="4d6ca-290">**文件触发**：由附件策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="4d6ca-291">**URL 触发**：按链接策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="4d6ca-292">传递后保护和 **ZAP (ATP) 或 ZAP (EOP) ：** 零时差自动清除 (ZAP) 恶意软件、垃圾邮件和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="4d6ca-293">如果在详细信息表中选择一行，则电子邮件计数的进一步细分将显示在该飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="4d6ca-294">从漏斗视图导出</span><span class="sxs-lookup"><span data-stu-id="4d6ca-294">Export from Funnel view</span></span>

<span data-ttu-id="4d6ca-295">单击"选项 **"** 下的 **"** 导出"后，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="4d6ca-296">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="4d6ca-297">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="4d6ca-298">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="4d6ca-299">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="4d6ca-300">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d6ca-301">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d6ca-302">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="4d6ca-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="4d6ca-303">" **技术"** 视图类似于漏 **斗视图** ，提供有关配置的威胁防护功能的更具体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="4d6ca-304">从图中，你可以看到如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="4d6ca-305">如果单击" **技术视图** "选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="4d6ca-306">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="4d6ca-307">**方向**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-307">**Direction**:</span></span>
  - <span data-ttu-id="4d6ca-308">**入站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-308">**Inbound**</span></span>
  - <span data-ttu-id="4d6ca-309">**出站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-309">**Outbound**</span></span>
  - <span data-ttu-id="4d6ca-310">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="4d6ca-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="4d6ca-311">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与入站和出站邮件分开计数) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="4d6ca-312">聚合视图和详细信息表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="4d6ca-313">可以通过单击"筛选器"来更改这些 **筛选器**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="4d6ca-314">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="4d6ca-315">此图显示按以下类别组织的邮件：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="4d6ca-316">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-316">**Total email**</span></span>
- <span data-ttu-id="4d6ca-317">**边缘允许** 和 **边缘筛选**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="4d6ca-318">**传输规则允许\*\*\*\*和传输规则筛选 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="4d6ca-319">**不是恶意软件\*\*\*\*、保险箱附件检测和** <sup>\*</sup> **反恶意软件引擎检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="4d6ca-320">**非网络钓鱼\*\*\*\*、DMARC 失败**、**模拟检测** <sup>\*</sup> 、**欺骗检测和\*\*\*\*钓鱼检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="4d6ca-321">**无需检测 URL 触发和** **URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-322">**不是垃圾邮件** 和  **垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="4d6ca-323">**非恶意电子邮件\*\*\*\*、保险箱链接检测和** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="4d6ca-324"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d6ca-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="4d6ca-325">将鼠标悬停在图表中的类别上时，可以看到该类别中的消息数。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="4d6ca-326">详细信息表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="4d6ca-327">**Date (UTC)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-327">**Date (UTC)**</span></span>
- <span data-ttu-id="4d6ca-328">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-328">**Total email**</span></span>
- <span data-ttu-id="4d6ca-329">**已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-329">**Edge filtered**</span></span>
- <span data-ttu-id="4d6ca-330">**规则邮件**：由于邮件流规则而筛选 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="4d6ca-331">**反恶意软件引擎** **，保险箱附件** <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="4d6ca-332">**DMARC， 模拟** <sup>\*</sup> ，**欺骗**，**网络钓鱼筛选**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="4d6ca-333">**DMARC：** 由于邮件未通过 DMARC 身份验证检查而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="4d6ca-334">**URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-335">**已筛选反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="4d6ca-336">**ZAP 已删除**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-336">**ZAP removed**</span></span>
- <span data-ttu-id="4d6ca-337">**按链接保险箱检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="4d6ca-338"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d6ca-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="4d6ca-339">如果在详细信息表中选择一行，则电子邮件计数的进一步细分将显示在该飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="4d6ca-340">"从技术导出"视图</span><span class="sxs-lookup"><span data-stu-id="4d6ca-340">Export from Tech view</span></span>

<span data-ttu-id="4d6ca-341">单击" **导出"，** 在" **选项** "下，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="4d6ca-342">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="4d6ca-343">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="4d6ca-344">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="4d6ca-345">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="4d6ca-346">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d6ca-347">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的技术视图](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="4d6ca-349">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-349">Malware detections report</span></span>

<span data-ttu-id="4d6ca-350">恶意软件 **检测报告显示** 有关传入和传出电子邮件中的恶意软件检测信息， (EOP Exchange Online Protection检测到的) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="4d6ca-351">有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="4d6ca-352">聚合视图筛选器允许 90 天，而详细信息表筛选器仅允许 10 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="4d6ca-353">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-354">在"**电子邮件&协作报告**"页上，找到 **"电子邮件中** 检测到的恶意软件"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-355">若要直接转到报告，请打开 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![电子邮件小部件中的恶意软件检测（位于"电子邮件&协作报告"页面上）](../../media/malware-detections-widget.png)

<span data-ttu-id="4d6ca-357">在"**恶意软件检测报告**"页上，可以通过单击"筛选器"并选择下列值之一来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="4d6ca-358">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-359">**方向**：**入站\*\*\*\*和出站**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-359">**Direction**: **Inbound** and **Outbound**</span></span>

![电子邮件报告中的恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="4d6ca-361">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d6ca-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-362">**Date**</span></span>
- <span data-ttu-id="4d6ca-363">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-363">**Sender address**</span></span>
- <span data-ttu-id="4d6ca-364">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-364">**Recipient address**</span></span>
- <span data-ttu-id="4d6ca-365">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="4d6ca-366">示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="4d6ca-367">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-367">**Subject**</span></span>
- <span data-ttu-id="4d6ca-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-368">**Filename**</span></span>
- <span data-ttu-id="4d6ca-369">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="4d6ca-370">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-370">Mail latency report</span></span>

<span data-ttu-id="4d6ca-371">Defender **for** Office 365 中的邮件延迟报告包含有关组织中遇到的邮件传递和触发延迟的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="4d6ca-372">有关详细信息，请参阅邮件 [延迟报告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="4d6ca-373">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="4d6ca-374">垃圾邮件 **检测报告** 最终将消失。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="4d6ca-375">威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="4d6ca-376">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="4d6ca-377">本文中所述的改进的欺骗检测报告在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="4d6ca-378">较旧版本的报告只显示"**良好邮件"和**"**捕获为垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="4d6ca-379">欺骗 **检测报告显示** 有关由于欺骗被阻止或允许的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="4d6ca-380">有关欺骗功能详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="4d6ca-381">报告聚合视图允许筛选 45 天，而详细信息视图仅 <sup>\*</sup> 允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="4d6ca-382"><sup>\*</sup> 最终，你将能够使用最多 90 天的筛选。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="4d6ca-383">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-384">在"**电子邮件&协作报告**"页上，找到 **"欺骗检测**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-385">若要直接转到报告，请打开 <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

!["电子邮件和协作报告"页面上&欺骗检测小组件](../../media/spoof-detections-widget.png)

<span data-ttu-id="4d6ca-387">该图表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-387">The chart shows the following information:</span></span>

- <span data-ttu-id="4d6ca-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-388">**Pass**</span></span>
- <span data-ttu-id="4d6ca-389">**失败**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-389">**Fail**</span></span>
- <span data-ttu-id="4d6ca-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-390">**SoftPass**</span></span>
- <span data-ttu-id="4d6ca-391">**无**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-391">**None**</span></span>
- <span data-ttu-id="4d6ca-392">**其他**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-392">**Other**</span></span>

<span data-ttu-id="4d6ca-393">当您将鼠标悬停在 (中) 的数据点时，可以看到检测到的欺骗邮件的个个和原因。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="4d6ca-394">在"**欺骗邮件报告**"页上，可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="4d6ca-395">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-396">**结果**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-396">**Result**:</span></span>
  - <span data-ttu-id="4d6ca-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-397">**Pass**</span></span>
  - <span data-ttu-id="4d6ca-398">**失败**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-398">**Fail**</span></span>
  - <span data-ttu-id="4d6ca-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-399">**SoftPass**</span></span>
  - <span data-ttu-id="4d6ca-400">**无**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-400">**None**</span></span>
  - <span data-ttu-id="4d6ca-401">**其他**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-401">**Other**</span></span>
- <span data-ttu-id="4d6ca-402">**欺骗类型**：**内部和外部**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-402">**Spoof type**: **Internal** and **External**</span></span>

![电子邮件门户中的欺骗邮件Microsoft 365 Defender页面](../../media/spoof-detections-report-page.png)

<span data-ttu-id="4d6ca-404">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d6ca-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-405">**Date**</span></span>
- <span data-ttu-id="4d6ca-406">**欺骗用户**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-406">**Spoofed user**</span></span>
- <span data-ttu-id="4d6ca-407">**发送基础结构**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="4d6ca-408">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-408">**Spoof type**</span></span>
- <span data-ttu-id="4d6ca-409">**结果**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-409">**Result**</span></span>
- <span data-ttu-id="4d6ca-410">**结果代码**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-410">**Result code**</span></span>
- <span data-ttu-id="4d6ca-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-411">**SPF**</span></span>
- <span data-ttu-id="4d6ca-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-412">**DKIM**</span></span>
- <span data-ttu-id="4d6ca-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-413">**DMARC**</span></span>
- <span data-ttu-id="4d6ca-414">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-414">**Message count**</span></span>

<span data-ttu-id="4d6ca-415">有关复合身份验证结果代码详细信息，请参阅邮件中的[反垃圾邮件Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ca-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="4d6ca-416">提交报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-416">Submissions report</span></span>

<span data-ttu-id="4d6ca-417">提交 **报告显示** 有关管理员已报告给 Microsoft 进行分析的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="4d6ca-418">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ca-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="4d6ca-419">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-420">在"**电子邮件&协作报告**"页上，找到 **"提交"，** 然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-421">若要直接转到报告，请打开 <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="4d6ca-422">若要转到管理 [门户中的管理员Microsoft 365 Defender，请单击](admin-submission.md)**"转到提交"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

!["电子邮件和协作报告"&"提交"小组件](../../media/submissions-report-widget.png)

<span data-ttu-id="4d6ca-424">该图表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-424">The chart shows the following information:</span></span>

- <span data-ttu-id="4d6ca-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-425">**Pending**</span></span>
- <span data-ttu-id="4d6ca-426">**已完成**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-426">**Completed**</span></span>

<span data-ttu-id="4d6ca-427">在 **"提交"** 页上，可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="4d6ca-428">**报告的日期\*\*\*\*：开始时间和\*\*\*\*结束时间**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="4d6ca-429">**提交类型**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-429">**Submission type**:</span></span>
  - <span data-ttu-id="4d6ca-430">**电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-430">**Email**</span></span>
  - <span data-ttu-id="4d6ca-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-431">**URL**</span></span>
  - <span data-ttu-id="4d6ca-432">**文件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-432">**File**</span></span>
- <span data-ttu-id="4d6ca-433">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-433">**Submission ID**</span></span>
- <span data-ttu-id="4d6ca-434">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-434">**Network Message ID**</span></span>
- <span data-ttu-id="4d6ca-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-435">**Sender**</span></span>
- <span data-ttu-id="4d6ca-436">**名称**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-436">**Name**</span></span>
- <span data-ttu-id="4d6ca-437">**提交者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-437">**Submitted by**</span></span>
- <span data-ttu-id="4d6ca-438">**提交原因**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="4d6ca-439">**非垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-439">**Not junk**</span></span>
  - <span data-ttu-id="4d6ca-440">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-440">**Phish**</span></span>
  - <span data-ttu-id="4d6ca-441">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-441">**Malware**</span></span>
  - <span data-ttu-id="4d6ca-442">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-442">**Spam**</span></span>
- <span data-ttu-id="4d6ca-443">**重新扫描状态**：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-443">**Rescan status**:</span></span>
  - <span data-ttu-id="4d6ca-444">**Pending**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-444">**Pending**</span></span>
  - <span data-ttu-id="4d6ca-445">**已完成**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-445">**Completed**</span></span>

<span data-ttu-id="4d6ca-446">图形下方的详细信息表显示相同的信息，并且具有相同的组或自定义列选项与电子邮件和协作提交中的提交进行分析选项卡& \> **选项**。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="4d6ca-447">有关详细信息，请参阅查看向 [Microsoft 提交的管理员](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Microsoft 365 Defender门户中的提交Microsoft 365 Defender页](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="4d6ca-449">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-449">Threat protection status report</span></span>

<span data-ttu-id="4d6ca-450">威胁 **防护状态报告** 在 EOP 和 Defender for Office 365;但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="4d6ca-451">例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 SharePoint、OneDrive 和 Microsoft Teams 的 保险箱 附件检测到的恶意[文件的信息](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4d6ca-452">该报告提供包含恶意内容的电子邮件（如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和 Defender 等 Office 365 功能（如 保险箱[链接](safe-links.md)[、保险箱](safe-attachments.md)附件和防钓鱼策略中的模拟保护功能）的计数。 [](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="4d6ca-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="4d6ca-453">您可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="4d6ca-454">**注意**：如果邮件发送给五个收件人，则我们将邮件计为五个不同的邮件，而不是一封邮件，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="4d6ca-455">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-456">在"**电子邮件&协作报告**"页上，找到 **"威胁防护状态**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-457">若要直接转到报告，请打开以下 URL 之一：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="4d6ca-458">Defender for Office 365：<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="4d6ca-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="4d6ca-459">EOP： <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="4d6ca-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

!["电子邮件和协作报告"页面上的威胁&小组件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="4d6ca-461">默认情况下，图表显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="4d6ca-462">如果单击"**威胁\*\*\*\*防护状态报告**"页上的"筛选"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="4d6ca-463">详细信息表允许筛选 30 天。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="4d6ca-464">以下各节介绍了可用的视图。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="4d6ca-465">按概述查看数据</span><span class="sxs-lookup"><span data-stu-id="4d6ca-465">View data by Overview</span></span>

![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="4d6ca-467">在 **"按概述查看数据"** 视图中，图表中显示了以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="4d6ca-468">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-468">**Email malware**</span></span>
- <span data-ttu-id="4d6ca-469">**电子邮件钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-469">**Email phish**</span></span>
- <span data-ttu-id="4d6ca-470">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-470">**Content malware**</span></span>

<span data-ttu-id="4d6ca-471">图表下方没有详细信息表。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-471">No details table is available below the chart.</span></span>

<span data-ttu-id="4d6ca-472">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-473">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-474">**检测**：**电子邮件恶意软件\*\*\*\*、电子邮件钓鱼** 邮件或 **内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="4d6ca-475">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d6ca-476">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d6ca-477">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d6ca-478">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-478">**Direction**</span></span>
- <span data-ttu-id="4d6ca-479">**域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-479">**Domain**</span></span>
- <span data-ttu-id="4d6ca-480">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-480">**Policy type**</span></span>

<span data-ttu-id="4d6ca-481">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="4d6ca-482">通过电子邮件钓鱼查看 \> 数据，按检测技术查看图表细目</span><span class="sxs-lookup"><span data-stu-id="4d6ca-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="4d6ca-484">在" **通过电子邮件查看数据" \>** 和"按检测技术查看图表细分 **"** 视图中，图表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="4d6ca-485">**URL 恶意信誉** <sup>\*</sup> ：来自 Defender 的恶意 URL 信誉Office 365客户的其他Microsoft 365触发。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="4d6ca-486">**高级筛选器**：基于机器学习的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="4d6ca-487">**常规筛选器**：基于分析员规则的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="4d6ca-488">**欺骗组织内部**：发件人正在尝试欺骗收件人域。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="4d6ca-489">**欺骗外部域**：发件人正在尝试欺骗某些其他域。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="4d6ca-490">**欺骗 DMARC：** 邮件上的 DMARC 身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="4d6ca-491">**模拟品牌**：模拟基于发件人的已知品牌。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="4d6ca-492">**混合分析检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="4d6ca-493">**文件信誉**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-493">**File reputation**</span></span>
- <span data-ttu-id="4d6ca-494">**指纹匹配**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="4d6ca-495">**URL 触发信誉**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-496">**URL 触发**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-497">**模拟用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-498">**模拟域** <sup>\*</sup> ：模拟客户拥有或定义的域。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="4d6ca-499">**邮箱智能模拟** <sup>\*</sup> ：模拟由管理员定义或通过邮箱智能学习的用户。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="4d6ca-500">**文件触发**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-501">**宣传活动**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="4d6ca-502">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d6ca-503">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-503">**Date**</span></span>
- <span data-ttu-id="4d6ca-504">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-504">**Subject**</span></span>
- <span data-ttu-id="4d6ca-505">**发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-505">**Sender**</span></span>
- <span data-ttu-id="4d6ca-506">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-506">**Recipients**</span></span>
- <span data-ttu-id="4d6ca-507">**检测者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-507">**Detected by**</span></span>
- <span data-ttu-id="4d6ca-508">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-508">**Delivery Status**</span></span>
- <span data-ttu-id="4d6ca-509">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-509">**Source of Compromise**</span></span>
- <span data-ttu-id="4d6ca-510">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-510">**Tags**</span></span>

<span data-ttu-id="4d6ca-511">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-512">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-513">**检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-513">**Detection**</span></span>
- <span data-ttu-id="4d6ca-514">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d6ca-515">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-515">**Direction**</span></span>
- <span data-ttu-id="4d6ca-516">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d6ca-517">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d6ca-518">**域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-518">**Domain**</span></span>
- <span data-ttu-id="4d6ca-519">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-519">**Policy type**</span></span>
- <span data-ttu-id="4d6ca-520">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d6ca-521">**收件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-521">**Recipients**</span></span>

<span data-ttu-id="4d6ca-522">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="4d6ca-523">按电子邮件恶意软件查看 \> 数据，按检测技术查看图表细目</span><span class="sxs-lookup"><span data-stu-id="4d6ca-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="4d6ca-525">在" **通过电子邮件查看数据 \> "和** "按检测技术查看图表细分 **"** 视图中，图表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="4d6ca-526">**文件触发** <sup>\*</sup> ：按附件保险箱检测。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="4d6ca-527">**文件触发信誉** <sup>\*</sup> ：Defender 为安全触发生成的所有恶意Office 365信誉。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="4d6ca-528">**文件信誉**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-528">**File reputation**</span></span>
- <span data-ttu-id="4d6ca-529">**反恶意软件引擎** <sup>\*</sup> ：来自反恶意软件引擎的检测。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="4d6ca-530">**反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="4d6ca-531">**URL 恶意声誉**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="4d6ca-532">**URL 设置**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-532">**URL detonation**</span></span>
- <span data-ttu-id="4d6ca-533">**URL 组织的信誉**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="4d6ca-534">**市场活动**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-534">**Campaign**</span></span>

<span data-ttu-id="4d6ca-535">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d6ca-536">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-536">**Date**</span></span>
- <span data-ttu-id="4d6ca-537">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-537">**Subject**</span></span>
- <span data-ttu-id="4d6ca-538">**发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-538">**Sender**</span></span>
- <span data-ttu-id="4d6ca-539">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-539">**Recipients**</span></span>
- <span data-ttu-id="4d6ca-540">**检测者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-540">**Detected by**</span></span>
- <span data-ttu-id="4d6ca-541">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-541">**Delivery Status**</span></span>
- <span data-ttu-id="4d6ca-542">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-542">**Source of Compromise**</span></span>
- <span data-ttu-id="4d6ca-543">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-543">**Tags**</span></span>

<span data-ttu-id="4d6ca-544">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-545">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-546">**检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-546">**Detection**</span></span>
- <span data-ttu-id="4d6ca-547">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d6ca-548">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-548">**Direction**</span></span>
- <span data-ttu-id="4d6ca-549">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d6ca-550">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d6ca-551">**域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-551">**Domain**</span></span>
- <span data-ttu-id="4d6ca-552">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-552">**Policy type**</span></span>
- <span data-ttu-id="4d6ca-553">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d6ca-554">**收件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-554">**Recipients**</span></span>

<span data-ttu-id="4d6ca-555">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="4d6ca-556">按策略类型和通过电子邮件查看数据或通过电子邮件恶意软件 \> 查看数据的图表 \> 细分</span><span class="sxs-lookup"><span data-stu-id="4d6ca-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威胁防护状态报告中网络钓鱼电子邮件或恶意软件电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="4d6ca-558">在 **"按策略类型划分** 的图表细分"和 **" \>** 通过电子邮件查看数据"或"通过电子邮件查看恶意软件数据"视图中，图表中显示了以下信息： **\>**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="4d6ca-559">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-559">**Anti-malware**</span></span>
- <span data-ttu-id="4d6ca-560">**保险箱附件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d6ca-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="4d6ca-561">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-561">**Anti-phish**</span></span>
- <span data-ttu-id="4d6ca-562">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-562">**Anti-spam**</span></span>
- <span data-ttu-id="4d6ca-563">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="4d6ca-564">**其他**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-564">**Others**</span></span>

<span data-ttu-id="4d6ca-565">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d6ca-566">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-566">**Date**</span></span>
- <span data-ttu-id="4d6ca-567">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-567">**Subject**</span></span>
- <span data-ttu-id="4d6ca-568">**发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-568">**Sender**</span></span>
- <span data-ttu-id="4d6ca-569">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-569">**Recipients**</span></span>
- <span data-ttu-id="4d6ca-570">**检测者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-570">**Detected by**</span></span>
- <span data-ttu-id="4d6ca-571">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-571">**Delivery Status**</span></span>
- <span data-ttu-id="4d6ca-572">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-572">**Source of Compromise**</span></span>
- <span data-ttu-id="4d6ca-573">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-573">**Tags**</span></span>

<span data-ttu-id="4d6ca-574">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-575">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-576">**检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-576">**Detection**</span></span>
- <span data-ttu-id="4d6ca-577">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d6ca-578">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-578">**Direction**</span></span>
- <span data-ttu-id="4d6ca-579">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d6ca-580">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d6ca-581">**域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-581">**Domain**</span></span>
- <span data-ttu-id="4d6ca-582">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-582">**Policy type**</span></span>
- <span data-ttu-id="4d6ca-583">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d6ca-584">**收件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-584">**Recipients**</span></span>

<span data-ttu-id="4d6ca-585">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="4d6ca-586">按传递状态和通过电子邮件查看数据或通过电子邮件恶意软件 \> 查看数据的图表 \> 细分</span><span class="sxs-lookup"><span data-stu-id="4d6ca-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威胁防护状态报告中的网络钓鱼电子邮件和恶意软件电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="4d6ca-588">在 **"按传递状态分类"** 和 **" \>** 通过电子邮件查看数据"或"通过电子邮件查看恶意软件数据"视图中，图表中显示了以下信息： **\>**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="4d6ca-589">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="4d6ca-590">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="4d6ca-591">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="4d6ca-592">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="4d6ca-593">**转发**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-593">**Forwarded**</span></span>
- <span data-ttu-id="4d6ca-594">**本地服务器：已传递**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="4d6ca-595">**隔离**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-595">**Quarantine**</span></span>
- <span data-ttu-id="4d6ca-596">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-596">**Delivery failed**</span></span>
- <span data-ttu-id="4d6ca-597">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-597">**Dropped**</span></span>

<span data-ttu-id="4d6ca-598">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d6ca-599">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-599">**Date**</span></span>
- <span data-ttu-id="4d6ca-600">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-600">**Subject**</span></span>
- <span data-ttu-id="4d6ca-601">**发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-601">**Sender**</span></span>
- <span data-ttu-id="4d6ca-602">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-602">**Recipients**</span></span>
- <span data-ttu-id="4d6ca-603">**检测者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-603">**Detected by**</span></span>
- <span data-ttu-id="4d6ca-604">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-604">**Delivery Status**</span></span>
- <span data-ttu-id="4d6ca-605">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-605">**Source of Compromise**</span></span>
- <span data-ttu-id="4d6ca-606">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-606">**Tags**</span></span>

<span data-ttu-id="4d6ca-607">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-608">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-609">**检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-609">**Detection**</span></span>
- <span data-ttu-id="4d6ca-610">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d6ca-611">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-611">**Direction**</span></span>
- <span data-ttu-id="4d6ca-612">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d6ca-613">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d6ca-614">**域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-614">**Domain**</span></span>
- <span data-ttu-id="4d6ca-615">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-615">**Policy type**</span></span>
- <span data-ttu-id="4d6ca-616">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d6ca-617">**收件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-617">**Recipients**</span></span>

<span data-ttu-id="4d6ca-618">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="4d6ca-619">按内容恶意软件查看 \> 数据</span><span class="sxs-lookup"><span data-stu-id="4d6ca-619">View data by Content \> Malware</span></span>

![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="4d6ca-621">在 **"按内容恶意软件查看 \>** 数据"视图中，以下信息显示在 Microsoft Defender for Office 365图表中：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="4d6ca-622">**反恶意软件引擎**：Sharepoint、OneDrive 和 Microsoft Teams 中内置的病毒检测 [检测到的恶意](virus-detection-in-spo.md)Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="4d6ca-623">**文件触发**：附件检测到的恶意保险箱 [文件SharePoint、OneDrive和Microsoft Teams。](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ca-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4d6ca-624">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d6ca-625">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-626">**位置**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-626">**Location**</span></span>
- <span data-ttu-id="4d6ca-627">**检测者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-627">**Detected by**</span></span>
- <span data-ttu-id="4d6ca-628">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-628">**Malware name**</span></span>

<span data-ttu-id="4d6ca-629">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-630">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-631">**检测\*\*\*\*：反恶意软件引擎** 或 **文件触发**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="4d6ca-632">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="4d6ca-633">按系统覆盖查看数据</span><span class="sxs-lookup"><span data-stu-id="4d6ca-633">View data by System override</span></span>

![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="4d6ca-635">在" **按系统覆盖查看数据"视图中** ，图表中显示了以下替代原因信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="4d6ca-636">**本地跳过**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-636">**On-premises skip**</span></span>
- <span data-ttu-id="4d6ca-637">**IP 允许**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-637">**IP allow**</span></span>
- <span data-ttu-id="4d6ca-638">**Exchange邮件传输规则 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="4d6ca-639">**组织允许的发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="4d6ca-640">**组织允许的域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="4d6ca-641">**ZAP 未启用**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="4d6ca-642">**未启用垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="4d6ca-643">**用户保险箱发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-643">**User Safe Sender**</span></span>
- <span data-ttu-id="4d6ca-644">**用户保险箱域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-644">**User Safe Domain**</span></span>

<span data-ttu-id="4d6ca-645">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d6ca-646">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-646">**Date**</span></span>
- <span data-ttu-id="4d6ca-647">**主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-647">**Subject**</span></span>
- <span data-ttu-id="4d6ca-648">**发件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-648">**Sender**</span></span>
- <span data-ttu-id="4d6ca-649">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-649">**Recipients**</span></span>
- <span data-ttu-id="4d6ca-650">**检测者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-650">**Detected by**</span></span>
- <span data-ttu-id="4d6ca-651">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-651">**Delivery Status**</span></span>
- <span data-ttu-id="4d6ca-652">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-652">**Source of Compromise**</span></span>
- <span data-ttu-id="4d6ca-653">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-653">**Tags**</span></span>

<span data-ttu-id="4d6ca-654">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d6ca-655">**UTC (UTC)\*\*\*\*开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="4d6ca-656">**检测**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-656">**Detection**</span></span>
- <span data-ttu-id="4d6ca-657">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d6ca-658">**方向**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-658">**Direction**</span></span>
- <span data-ttu-id="4d6ca-659">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d6ca-660">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d6ca-661">**域**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-661">**Domain**</span></span>
- <span data-ttu-id="4d6ca-662">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-662">**Policy type**</span></span>
- <span data-ttu-id="4d6ca-663">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d6ca-664">**收件人**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-664">**Recipients**</span></span>

<span data-ttu-id="4d6ca-665">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="4d6ca-666"><sup>\*</sup>仅 defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d6ca-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="4d6ca-667">热门恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-667">Top malware report</span></span>

<span data-ttu-id="4d6ca-668">" **热门恶意软件** "报告显示 [EOP](anti-malware-protection.md)中的反恶意软件保护检测到的各种恶意软件。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="4d6ca-669">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-670">在"**电子邮件&协作报告**"页上，找到 **"热门恶意软件**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-671">若要直接转到报告，请打开 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

!["电子邮件和协作报告"页面上&恶意软件小组件](../../media/top-malware-report-widget.png)

<span data-ttu-id="4d6ca-673">当您将鼠标悬停在饼图中的一个浮点上时，可以看到某种恶意软件的名称，以及检测到具有该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="4d6ca-674">在" **热门恶意软件报告** "页上，报表页上将显示饼图的较大版本。图表下面的详细信息表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="4d6ca-675">**热门恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-675">**Top malware**</span></span>
- <span data-ttu-id="4d6ca-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-676">**Count**</span></span>

<span data-ttu-id="4d6ca-677">If you click **Filter**， you can specify a date range with **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="4d6ca-679">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-679">URL threat protection report</span></span>

<span data-ttu-id="4d6ca-680">URL **威胁防护报告** 仅适用于 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4d6ca-681">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="4d6ca-682">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d6ca-683">为了使用户 **报告的消息** 报告正常工作，必须为用户报告的环境启用Microsoft 365日志记录。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="4d6ca-684">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="4d6ca-685">有关详细信息，请参阅打开[Microsoft 365 审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="4d6ca-686">用户 **报告的邮件** 报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ca-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="4d6ca-687">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="4d6ca-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d6ca-688">在"**电子邮件&协作报告**"页上，找到 **"用户报告的邮件**"，然后单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="4d6ca-689">若要直接转到报告，请打开 <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="4d6ca-690">若要转到管理 [门户中的管理员Microsoft 365 Defender，请单击](admin-submission.md)**"转到提交"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

!["电子邮件和协作报告"页上&"用户报告的邮件"小组件](../../media/user-reported-messages-widget.png)

<span data-ttu-id="4d6ca-692">在"**用户报告的消息**"页上，可以通过单击"筛选器"，在出现的飞出中选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d6ca-693">**报告的日期\*\*\*\*：开始时间和\*\*\*\*结束时间**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="4d6ca-694">**报告者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-694">**Reported by**</span></span>
- <span data-ttu-id="4d6ca-695">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-695">**Email subject**</span></span>
- <span data-ttu-id="4d6ca-696">**邮件报告 ID**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-696">**Message reported ID**</span></span>
- <span data-ttu-id="4d6ca-697">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-697">**Network Message ID**</span></span>
- <span data-ttu-id="4d6ca-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-698">**Sender**</span></span>
- <span data-ttu-id="4d6ca-699">**报告的原因**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-699">**Reported reason**</span></span>
  - <span data-ttu-id="4d6ca-700">**非垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-700">**Not junk**</span></span>
  - <span data-ttu-id="4d6ca-701">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-701">**Phish**</span></span>
  - <span data-ttu-id="4d6ca-702">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-702">**Spam**</span></span>
- <span data-ttu-id="4d6ca-703">**网络钓鱼模拟**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="4d6ca-704">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="4d6ca-705">若要对条目进行分组，请单击 **"分组** "，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="4d6ca-706">**无**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-706">**None**</span></span>
- <span data-ttu-id="4d6ca-707">**原因**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-707">**Reason**</span></span>
- <span data-ttu-id="4d6ca-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-708">**Sender**</span></span>
- <span data-ttu-id="4d6ca-709">**报告者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-709">**Reported by**</span></span>
- <span data-ttu-id="4d6ca-710">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-710">**Rescan result**</span></span>
- <span data-ttu-id="4d6ca-711">**网络钓鱼模拟**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-711">**Phish simulation**</span></span>

![用户报告的邮件报告](../../media/user-reported-messages-report.png)

<span data-ttu-id="4d6ca-713">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d6ca-714">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-714">**Email subject**</span></span>
- <span data-ttu-id="4d6ca-715">**报告者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-715">**Reported by**</span></span>
- <span data-ttu-id="4d6ca-716">**报告的日期**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-716">**Date reported**</span></span>
- <span data-ttu-id="4d6ca-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-717">**Sender**</span></span>
- <span data-ttu-id="4d6ca-718">**报告的原因**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-718">**Reported reason**</span></span>
- <span data-ttu-id="4d6ca-719">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-719">**Rescan result**</span></span>
- <span data-ttu-id="4d6ca-720">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-720">**Tags**</span></span>

<span data-ttu-id="4d6ca-721">若要将邮件提交给 Microsoft 进行分析，请从表中选择邮件条目，单击"提交给 **Microsoft** 进行分析"，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="4d6ca-722">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-722">**Report clean**</span></span>
- <span data-ttu-id="4d6ca-723">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-723">**Report phishing**</span></span>
- <span data-ttu-id="4d6ca-724">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-724">**Report malware**</span></span>
- <span data-ttu-id="4d6ca-725">**报告垃圾邮件**'</span><span class="sxs-lookup"><span data-stu-id="4d6ca-725">**Report spam**'</span></span>
- <span data-ttu-id="4d6ca-726">**触发 Defender** (调查Office 365) </span><span class="sxs-lookup"><span data-stu-id="4d6ca-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="4d6ca-727">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="4d6ca-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="4d6ca-728">若要查看和使用本文中所述的报告，你需要是本文门户中以下角色组之一Microsoft 365 Defender成员：</span><span class="sxs-lookup"><span data-stu-id="4d6ca-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="4d6ca-729">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-729">**Organization Management**</span></span>
- <span data-ttu-id="4d6ca-730">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-730">**Security Administrator**</span></span>
- <span data-ttu-id="4d6ca-731">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-731">**Security Reader**</span></span>
- <span data-ttu-id="4d6ca-732">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="4d6ca-732">**Global Reader**</span></span>

<span data-ttu-id="4d6ca-733">有关详细信息，请参阅应用程序[门户中Microsoft 365 Defender权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="4d6ca-734">**注意**：向 Microsoft 365 管理中心 中的相应 Azure Active Directory 角色添加用户会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 </span><span class="sxs-lookup"><span data-stu-id="4d6ca-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4d6ca-735">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4d6ca-736">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="4d6ca-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4d6ca-737">如果报告中未显示数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4d6ca-738">若要了解更多信息，请参阅 [防范威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6ca-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d6ca-739">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d6ca-739">Related topics</span></span>

[<span data-ttu-id="4d6ca-740">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="4d6ca-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="4d6ca-741">智能报表和 Microsoft 365 Defender见解</span><span class="sxs-lookup"><span data-stu-id="4d6ca-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="4d6ca-742">在邮件门户中查看Microsoft 365 Defender报告</span><span class="sxs-lookup"><span data-stu-id="4d6ca-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="4d6ca-743">查看 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d6ca-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
