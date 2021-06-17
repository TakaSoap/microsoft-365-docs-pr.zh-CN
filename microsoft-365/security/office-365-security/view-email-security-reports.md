---
title: 在 Microsoft 365 Defender 门户中查看电子邮件安全报告
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
description: 了解如何查找和使用组织的电子邮件安全报告。 Microsoft 365 Defender 门户中提供了电子邮件安全报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985158"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="8add3-104">在 Microsoft 365 Defender 门户中查看电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="8add3-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8add3-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="8add3-105">**Applies to**</span></span>
- [<span data-ttu-id="8add3-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8add3-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8add3-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="8add3-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8add3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8add3-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8add3-109">Microsoft 365 Defender 门户中提供了各种报告，可帮助你了解 Microsoft 365 中的电子邮件安全功能（如 Microsoft 365 中的反垃圾邮件、反恶意软件和加密功能）如何保护 <https://security.microsoft.com> 你的组织。</span><span class="sxs-lookup"><span data-stu-id="8add3-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="8add3-110">如果你拥有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在 Microsoft 365 Defender 门户中查看这些报告，方式为：查看报告电子邮件&协作 电子邮件& \>  \> **协作报告**。</span><span class="sxs-lookup"><span data-stu-id="8add3-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-111">若要直接转到"电子邮件& **协作报告"** 页，请打开 <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender 门户中的"电子邮件&协作报告"页面](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="8add3-113">"电子邮件和协作报告 **"&一些报告** 需要 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="8add3-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8add3-114">有关这些报告的信息，请参阅在 [Microsoft 365](view-reports-for-mdo.md)Defender 门户中查看适用于 Office 365 的 Defender 报告。</span><span class="sxs-lookup"><span data-stu-id="8add3-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="8add3-115">与邮件流相关的报告现在位于 Exchange 管理中心 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="8add3-116">有关这些报告详细信息，请参阅新 Exchange 管理中心 [中的邮件流报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="8add3-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="8add3-117">遭到入侵的用户报告</span><span class="sxs-lookup"><span data-stu-id="8add3-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="8add3-118">此报告适用于具有 Exchange Online 邮箱的 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="8add3-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="8add3-119">它不适用于独立 Exchange Online Protection (EOP) 组织。</span><span class="sxs-lookup"><span data-stu-id="8add3-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="8add3-120">"**遭到入侵的用户**"报告显示过去 7 天内标记为"可疑"或"受限"的用户帐户数量。</span><span class="sxs-lookup"><span data-stu-id="8add3-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="8add3-121">其中任一状态的帐户存在问题，甚至受到威胁。</span><span class="sxs-lookup"><span data-stu-id="8add3-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="8add3-122">通过频繁使用，可以使用报告来发现可疑或受限帐户的峰值甚至趋势。</span><span class="sxs-lookup"><span data-stu-id="8add3-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="8add3-123">有关遭到入侵的用户详细信息，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

!["电子邮件和协作报告"页上的"遭到入侵&小组件](../../media/compromised-users-report-widget.png)

<span data-ttu-id="8add3-125">聚合视图显示过去 90 天的数据，而详细信息视图显示最近 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="8add3-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="8add3-126">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="8add3-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-127">在 **"遭到入侵的用户"上**，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="8add3-128">若要直接转到报告，请打开 <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="8add3-129">单击"**查看详细信息**"后，可以通过单击"筛选器"，在出现的飞出视图中选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="8add3-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="8add3-130">**DATE (UTC)**： **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="8add3-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="8add3-131">**活动**：</span><span class="sxs-lookup"><span data-stu-id="8add3-131">**Activity**:</span></span>
  - <span data-ttu-id="8add3-132">**可疑**：用户帐户已发送可疑电子邮件，并且存在被限制发送电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="8add3-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="8add3-133">**受限**：由于高度可疑的模式，已限制用户帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="8add3-134">完成筛选后，单击"应用 **"** 或"取消 **"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

!["泄露的用户"报告中的报告视图](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="8add3-136">在图表下面的表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="8add3-137">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="8add3-137">**Creation time**</span></span>
- <span data-ttu-id="8add3-138">**用户 ID**</span><span class="sxs-lookup"><span data-stu-id="8add3-138">**User ID**</span></span>
- <span data-ttu-id="8add3-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="8add3-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="8add3-140">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="8add3-140">Exchange transport rule report</span></span>

<span data-ttu-id="8add3-141">**Exchange 传输规则** 报告显示邮件流规则对组织中 (传输规则) 传入和传出邮件的影响。</span><span class="sxs-lookup"><span data-stu-id="8add3-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="8add3-142">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="8add3-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-143">在 **"Exchange 传输规则"上**，单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="8add3-144">若要直接转到报告，请打开 <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

!["电子邮件和协作报告"页面上的"Exchange 传输&小组件](../../media/transport-rule-report-widget.png)

<span data-ttu-id="8add3-146">单击" **查看详细信息"** 后，以下图表和数据可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="8add3-147">**按 Exchange 传输规则查看数据** \>**按方向划分** 的图表细分：此图显示受邮件流规则影响的入站和出站邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="8add3-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="8add3-148">**按 Exchange 传输规则查看数据** \>**按严重性分类** 的图表：此图表显示高严重性、中等严重性和 **低严重性邮件的数量**。 </span><span class="sxs-lookup"><span data-stu-id="8add3-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="8add3-149">将严重性级别设置为规则中的操作， (严重性级别审核此规则或 _SetAuditSeverity_) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="8add3-150">有关详细信息，请参阅 Mail [flow rule actions in Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="8add3-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="8add3-151">**按 DLP Exchange 传输规则查看数据** \>**按方向划分** 的图表细分：此图显示受DLP和邮件流规则中的数据丢失防护 (入站) 邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="8add3-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="8add3-152">**按 DLP Exchange 传输规则查看数据** \>**按严重性分类** 的图表：此视图显示受 DLP 邮件流规则影响的高严重性、中等严重性和低严重性邮件的数量。 </span><span class="sxs-lookup"><span data-stu-id="8add3-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="8add3-153">对于 **"按 Exchange 传输规则** 查看数据"选项，下图下方的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="8add3-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-154">**Date**</span></span>
- <span data-ttu-id="8add3-155">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="8add3-155">**Transport rule**</span></span>
- <span data-ttu-id="8add3-156">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-156">**Subject**</span></span>
- <span data-ttu-id="8add3-157">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="8add3-157">**Sender address**</span></span>
- <span data-ttu-id="8add3-158">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="8add3-158">**Recipient address**</span></span>
- <span data-ttu-id="8add3-159">**严重性**</span><span class="sxs-lookup"><span data-stu-id="8add3-159">**Severity**</span></span>
- <span data-ttu-id="8add3-160">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-160">**Direction**</span></span>

<span data-ttu-id="8add3-161">对于 **"按 DLP Exchange 传输规则** 查看数据"选项，下图下方的详细信息表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="8add3-162">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-162">**Date**</span></span>
- <span data-ttu-id="8add3-163">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="8add3-163">**DLP policy**</span></span>
- <span data-ttu-id="8add3-164">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="8add3-164">**Transport rule**</span></span>
- <span data-ttu-id="8add3-165">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-165">**Subject**</span></span>
- <span data-ttu-id="8add3-166">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="8add3-166">**Sender address**</span></span>
- <span data-ttu-id="8add3-167">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="8add3-167">**Recipient address**</span></span>
- <span data-ttu-id="8add3-168">**严重性**</span><span class="sxs-lookup"><span data-stu-id="8add3-168">**Severity**</span></span>
- <span data-ttu-id="8add3-169">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-169">**Direction**</span></span>

<span data-ttu-id="8add3-170">通过单击"筛选器"，并选择出现的一个或多个以下值，可以筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="8add3-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="8add3-171">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-172">**方向**： **出站** 和 **入站**</span><span class="sxs-lookup"><span data-stu-id="8add3-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="8add3-173">**严重性：\*\*\*\*高严重性**、**中等严重性** 和 **低严重性**</span><span class="sxs-lookup"><span data-stu-id="8add3-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="8add3-175">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="8add3-175">Mailflow status report</span></span>

<span data-ttu-id="8add3-176">**邮件流状态** 报告是一个智能报告，它显示有关传入和传出电子邮件、垃圾邮件检测、恶意软件、标识为"良好"的电子邮件的信息，以及边缘上允许或阻止的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="8add3-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="8add3-177">这是包含边缘保护信息的唯一报告，它显示了在 Exchange Online Protection (EOP) 允许进入服务之前阻止的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="8add3-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="8add3-178">必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="8add3-179">若要查看 Microsoft 365 Defender 门户中的报告，请转到报告电子邮件 \> **&协作** \> **电子邮件&报告**。</span><span class="sxs-lookup"><span data-stu-id="8add3-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-180">在 **"邮件流状态摘要"上，** 单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="8add3-181">若要直接转到报告，请打开 <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

!["电子邮件和协作报告"页上的"邮件流&摘要"小组件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="8add3-183">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="8add3-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="8add3-184">打开报表时，默认情况下 **会选中** "类型"选项卡。</span><span class="sxs-lookup"><span data-stu-id="8add3-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="8add3-185">默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="8add3-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="8add3-186">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="8add3-187">**邮件方向**：</span><span class="sxs-lookup"><span data-stu-id="8add3-187">**Mail direction**:</span></span>
  - <span data-ttu-id="8add3-188">**入站**</span><span class="sxs-lookup"><span data-stu-id="8add3-188">**Inbound**</span></span>
  - <span data-ttu-id="8add3-189">**出站**</span><span class="sxs-lookup"><span data-stu-id="8add3-189">**Outbound**</span></span>
  - <span data-ttu-id="8add3-190">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="8add3-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="8add3-191">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与 **入站** 和出站邮件 **分开计算)**</span><span class="sxs-lookup"><span data-stu-id="8add3-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="8add3-192">**类型**：</span><span class="sxs-lookup"><span data-stu-id="8add3-192">**Type**:</span></span>
  - <span data-ttu-id="8add3-193">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-193">**Good mail**</span></span>
  - <span data-ttu-id="8add3-194">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-194">**Malware**</span></span>
  - <span data-ttu-id="8add3-195">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-195">**Spam**</span></span>
  - <span data-ttu-id="8add3-196">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="8add3-196">**Edge protection**</span></span>
  - <span data-ttu-id="8add3-197">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-197">**Rule messages**</span></span>
  - <span data-ttu-id="8add3-198">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-198">**Phishing email**</span></span>
- <span data-ttu-id="8add3-199">**域**： **全部**</span><span class="sxs-lookup"><span data-stu-id="8add3-199">**Domain**: **All**</span></span>

<span data-ttu-id="8add3-200">图表按 Type **值组织** 。</span><span class="sxs-lookup"><span data-stu-id="8add3-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="8add3-201">可以通过单击"筛选器 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="8add3-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="8add3-202">该数据表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-202">The data table contains the following information:</span></span>

- <span data-ttu-id="8add3-203">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-203">**Direction**</span></span>
- <span data-ttu-id="8add3-204">**类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-204">**Type**</span></span>
- <span data-ttu-id="8add3-205">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="8add3-205">**24 hours**</span></span>
- <span data-ttu-id="8add3-206">**3 天**</span><span class="sxs-lookup"><span data-stu-id="8add3-206">**3 days**</span></span>
- <span data-ttu-id="8add3-207">**7 天**</span><span class="sxs-lookup"><span data-stu-id="8add3-207">**7 days**</span></span>
- <span data-ttu-id="8add3-208">**15 天**</span><span class="sxs-lookup"><span data-stu-id="8add3-208">**15 days**</span></span>
- <span data-ttu-id="8add3-209">**30 天**</span><span class="sxs-lookup"><span data-stu-id="8add3-209">**30 days**</span></span>

<span data-ttu-id="8add3-210">If you click **Choose a category for more details**， you can select from the following values：</span><span class="sxs-lookup"><span data-stu-id="8add3-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="8add3-211">**网络钓鱼电子邮件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="8add3-212">**电子邮件中的恶意软件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="8add3-213">**垃圾邮件检测**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="8add3-214">**边缘阻止的垃圾邮件**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="8add3-215">从类型视图导出</span><span class="sxs-lookup"><span data-stu-id="8add3-215">Export from Type view</span></span>

<span data-ttu-id="8add3-216">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="8add3-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="8add3-217">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="8add3-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="8add3-218">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="8add3-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8add3-219">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="8add3-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的类型视图](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="8add3-221">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="8add3-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="8add3-222">如果单击" **方向"** 选项卡，则使用"类型"视图中 **的相同** 默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="8add3-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="8add3-223">图表按 Direction **值** 组织。</span><span class="sxs-lookup"><span data-stu-id="8add3-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="8add3-224">可以通过单击"筛选器 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="8add3-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="8add3-225">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="8add3-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="8add3-226">该数据表包含"类型"视图中 **的相同** 信息。</span><span class="sxs-lookup"><span data-stu-id="8add3-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="8add3-227">" **选择类别"了解更多详细信息** 可用的选择和行为与"类型 **"视图相同** 。</span><span class="sxs-lookup"><span data-stu-id="8add3-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="8add3-228">从方向视图导出</span><span class="sxs-lookup"><span data-stu-id="8add3-228">Export from Direction view</span></span>

<span data-ttu-id="8add3-229">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="8add3-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="8add3-230">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="8add3-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="8add3-231">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="8add3-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8add3-232">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="8add3-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的方向视图](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="8add3-234">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="8add3-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="8add3-235">漏 **斗** 视图显示 Microsoft 的电子邮件威胁防护功能如何筛选组织中传入和传出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="8add3-236">它提供有关总电子邮件计数以及配置的威胁防护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）如何影响此计数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8add3-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="8add3-237">如果单击" **漏斗"** 选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="8add3-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="8add3-238">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="8add3-239">**方向**：</span><span class="sxs-lookup"><span data-stu-id="8add3-239">**Direction**:</span></span>

  - <span data-ttu-id="8add3-240">**入站**</span><span class="sxs-lookup"><span data-stu-id="8add3-240">**Inbound**</span></span>
  - <span data-ttu-id="8add3-241">**出站**</span><span class="sxs-lookup"><span data-stu-id="8add3-241">**Outbound**</span></span>
  - <span data-ttu-id="8add3-242">**组织内部**：此计数用于租户内发送的邮件;即，发件人 abc@domain.com 收件人的邮件 xyz@domain.com (入站和出站邮件分开计算) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="8add3-243">聚合视图和数据表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="8add3-244">如果单击 **"筛选器**"，可以同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="8add3-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="8add3-245">此图表显示按以下方式组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="8add3-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="8add3-246">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="8add3-246">**Total email**</span></span>
- <span data-ttu-id="8add3-247">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-247">**Email after edge protection**</span></span>
- <span data-ttu-id="8add3-248">**传输规则之后的电子邮件 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="8add3-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="8add3-249">**反恶意软件后的电子邮件， 文件信誉， 文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="8add3-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="8add3-250">**反网络钓鱼后的电子邮件， URL 信誉， 品牌模拟， 反欺骗**</span><span class="sxs-lookup"><span data-stu-id="8add3-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="8add3-251">**反垃圾邮件、批量邮件筛选后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="8add3-252">**用户和域模拟后的电子邮件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-253">**文件和 URL 触发后的电子邮件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-254">**在传递后保护或 URL 单击时间保护 (检测为安全)**</span><span class="sxs-lookup"><span data-stu-id="8add3-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="8add3-255"><sup>\*</sup>仅 defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8add3-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="8add3-256">若要查看由 EOP 或 Defender 单独筛选的电子邮件Office 365，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="8add3-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="8add3-257">该数据表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="8add3-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="8add3-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-258">**Date**</span></span>
- <span data-ttu-id="8add3-259">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="8add3-259">**Total email**</span></span>
- <span data-ttu-id="8add3-260">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="8add3-260">**Edge protection**</span></span>
- <span data-ttu-id="8add3-261">**反恶意软件， 文件信誉， 文件类型阻止**：</span><span class="sxs-lookup"><span data-stu-id="8add3-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="8add3-262">**文件信誉**：由于其他 Microsoft 客户标识的附加文件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="8add3-263">**文件类型阻止**：由于邮件中标识的恶意文件类型而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="8add3-264">**反网络钓鱼， URL 信誉， 品牌模拟， 反欺骗**：</span><span class="sxs-lookup"><span data-stu-id="8add3-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="8add3-265">**URL 信誉**：由于其他 Microsoft 客户标识的 URL 而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="8add3-266">**品牌模拟**：由于来自已知品牌模拟发件人的邮件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="8add3-267">**反欺骗**：由于邮件试图欺骗收件人所属的域或邮件发件人不属于的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="8add3-268">**反垃圾邮件，批量邮件筛选**：</span><span class="sxs-lookup"><span data-stu-id="8add3-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="8add3-269">**批量邮件筛选**：根据反垃圾邮件策略中的批量投诉级别 (BCL) 筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="8add3-270">**Defender for (的用户和Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="8add3-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="8add3-271">用户模拟：由于尝试模拟用户 (邮件发件人) （在反网络钓鱼策略的模拟保护设置中定义）而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="8add3-272">**域模拟**：由于尝试模拟在反网络钓鱼策略的模拟保护设置中定义的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="8add3-273">**Defender for (的文件和 URL Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="8add3-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="8add3-274">**文件触发**：由附件策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="8add3-275">**URL 触发**：按链接策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="8add3-276">传递后保护和 **ZAP (ATP) 或 ZAP (EOP) ：** 零时差自动清除 (ZAP) 恶意软件、垃圾邮件和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="8add3-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="8add3-277">如果在数据表中选择一行，则电子邮件计数的进一步细分将显示在该飞出区中。</span><span class="sxs-lookup"><span data-stu-id="8add3-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="8add3-278">从漏斗视图导出</span><span class="sxs-lookup"><span data-stu-id="8add3-278">Export from Funnel view</span></span>

<span data-ttu-id="8add3-279">单击"选项 **"** 下的 **"** 导出"后，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8add3-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="8add3-280">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="8add3-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="8add3-281">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="8add3-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="8add3-282">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="8add3-283">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="8add3-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="8add3-284">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="8add3-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8add3-285">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="8add3-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的漏斗视图](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="8add3-287">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="8add3-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="8add3-288">" **技术"** 视图类似于漏 **斗视图** ，提供有关配置的威胁防护功能的更具体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8add3-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="8add3-289">从图中，你可以看到如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="8add3-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="8add3-290">如果单击" **技术视图** "选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="8add3-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="8add3-291">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="8add3-292">**方向**：</span><span class="sxs-lookup"><span data-stu-id="8add3-292">**Direction**:</span></span>

  - <span data-ttu-id="8add3-293">**入站**</span><span class="sxs-lookup"><span data-stu-id="8add3-293">**Inbound**</span></span>
  - <span data-ttu-id="8add3-294">**出站**</span><span class="sxs-lookup"><span data-stu-id="8add3-294">**Outbound**</span></span>
  - <span data-ttu-id="8add3-295">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="8add3-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="8add3-296">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与入站和出站邮件分开计数) </span><span class="sxs-lookup"><span data-stu-id="8add3-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="8add3-297">聚合视图和数据表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="8add3-298">如果单击 **"筛选器**"，可以同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="8add3-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="8add3-299">此图显示按以下类别组织的邮件：</span><span class="sxs-lookup"><span data-stu-id="8add3-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="8add3-300">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="8add3-300">**Total email**</span></span>
- <span data-ttu-id="8add3-301">**边缘允许** 和 **边缘筛选**</span><span class="sxs-lookup"><span data-stu-id="8add3-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="8add3-302">**传输规则允许\*\*\*\*和传输规则筛选 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="8add3-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="8add3-303">**不是恶意软件\*\*\*\*、保险箱附件检测和** <sup>\*</sup> **反恶意软件引擎检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="8add3-304">**非网络钓鱼\*\*\*\*、DMARC 失败**、**模拟检测** <sup>\*</sup> 、**欺骗检测和\*\*\*\*钓鱼检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="8add3-305">**无需检测 URL 触发和** **URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-306">**不是垃圾邮件** 和  **垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="8add3-307">**非恶意电子邮件\*\*\*\*、保险箱链接检测和** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="8add3-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="8add3-308"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8add3-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="8add3-309">将鼠标悬停在图表中的类别上时，可以看到该类别中的消息数。</span><span class="sxs-lookup"><span data-stu-id="8add3-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="8add3-310">该数据表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="8add3-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="8add3-311">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-311">**Date**</span></span>
- <span data-ttu-id="8add3-312">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="8add3-312">**Total email**</span></span>
- <span data-ttu-id="8add3-313">**已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="8add3-313">**Edge filtered**</span></span>
- <span data-ttu-id="8add3-314">**规则邮件**：由于邮件流规则而筛选 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="8add3-315">**反恶意软件引擎** **，保险箱附件** <sup>\*</sup> ：</span><span class="sxs-lookup"><span data-stu-id="8add3-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="8add3-316">**DMARC， 模拟** <sup>\*</sup> ，**欺骗**，**网络钓鱼筛选**：</span><span class="sxs-lookup"><span data-stu-id="8add3-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="8add3-317">**DMARC：** 由于邮件未通过 DMARC 身份验证检查而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="8add3-318">**URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-319">**已筛选反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="8add3-320">**ZAP 已删除**</span><span class="sxs-lookup"><span data-stu-id="8add3-320">**ZAP removed**</span></span>
- <span data-ttu-id="8add3-321">**按链接保险箱检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="8add3-322"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8add3-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="8add3-323">如果在数据表中选择一行，则电子邮件计数的进一步细分将显示在该飞出区中。</span><span class="sxs-lookup"><span data-stu-id="8add3-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="8add3-324">"从技术导出"视图</span><span class="sxs-lookup"><span data-stu-id="8add3-324">Export from Tech view</span></span>

<span data-ttu-id="8add3-325">单击" **导出"，** 在" **选项** "下，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8add3-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="8add3-326">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="8add3-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="8add3-327">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="8add3-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="8add3-328">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="8add3-329">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="8add3-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="8add3-330">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="8add3-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="8add3-331">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="8add3-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的技术视图](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="8add3-333">恶意软件检测报告</span><span class="sxs-lookup"><span data-stu-id="8add3-333">Malware detections report</span></span>

<span data-ttu-id="8add3-334">恶意软件 **检测报告显示** 有关传入和传出电子邮件中的恶意软件检测信息， (EOP Exchange Online Protection检测到的) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="8add3-335">有关 EOP 中的恶意软件保护详细信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="8add3-336">聚合视图筛选器允许 90 天，而详细信息表筛选器仅允许 10 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="8add3-337">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="8add3-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-338">在 **电子邮件中检测到的恶意软件上**，单击 **查看详细信息**。</span><span class="sxs-lookup"><span data-stu-id="8add3-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="8add3-339">若要直接转到报告，请打开 <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![电子邮件小部件中的恶意软件检测（位于"电子邮件&协作报告"页面上）](../../media/malware-detections-widget.png)

<span data-ttu-id="8add3-341">单击" **查看详细信息"** 后，可以通过单击"筛选器"并选择以下选项来筛选图表 **和详细信息表** ：</span><span class="sxs-lookup"><span data-stu-id="8add3-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="8add3-342">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-343">**方向**：**入站\*\*\*\*和出站**</span><span class="sxs-lookup"><span data-stu-id="8add3-343">**Direction**: **Inbound** and **Outbound**</span></span>

![电子邮件报告中的恶意软件检测中的报告视图](../../media/malware-detections-report-view.png)

<span data-ttu-id="8add3-345">在图表下面的详细信息表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="8add3-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-346">**Date**</span></span>
- <span data-ttu-id="8add3-347">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="8add3-347">**Sender address**</span></span>
- <span data-ttu-id="8add3-348">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="8add3-348">**Recipient address**</span></span>
- <span data-ttu-id="8add3-349">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8add3-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="8add3-350">示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="8add3-351">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-351">**Subject**</span></span>
- <span data-ttu-id="8add3-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="8add3-352">**Filename**</span></span>
- <span data-ttu-id="8add3-353">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="8add3-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="8add3-354">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="8add3-354">Mail latency report</span></span>

<span data-ttu-id="8add3-355">Defender **for** Office 365 中的邮件延迟报告包含有关组织中遇到的邮件传递和触发延迟的信息。</span><span class="sxs-lookup"><span data-stu-id="8add3-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="8add3-356">有关详细信息，请参阅邮件 [延迟报告](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="8add3-357">垃圾邮件检测报告</span><span class="sxs-lookup"><span data-stu-id="8add3-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="8add3-358">垃圾邮件 **检测报告将于** 2021 年 6 月 30 日消失。</span><span class="sxs-lookup"><span data-stu-id="8add3-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="8add3-359">威胁防护状态报告中提供了 [相同的信息](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="8add3-360">欺骗检测报告</span><span class="sxs-lookup"><span data-stu-id="8add3-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="8add3-361">本文中所述的改进的欺骗检测报告在预览版中，可能会更改，并且并非在所有组织中都可用。</span><span class="sxs-lookup"><span data-stu-id="8add3-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="8add3-362">较旧版本的报告只显示"**良好邮件"和**"**捕获为垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="8add3-363">欺骗 **检测报告显示** 有关由于欺骗被阻止或允许的邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="8add3-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="8add3-364">有关欺骗功能详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="8add3-365">报告聚合视图允许筛选 45 天，而详细信息视图仅 <sup>\*</sup> 允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="8add3-366"><sup>\*</sup> 最终，你将能够使用最多 90 天的筛选。</span><span class="sxs-lookup"><span data-stu-id="8add3-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="8add3-367">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="8add3-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-368">在 **"欺骗检测"上**，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="8add3-369">若要直接转到报告，请打开 <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

!["电子邮件和协作报告"页面上&欺骗检测小组件](../../media/spoof-detections-widget.png)

<span data-ttu-id="8add3-371">当您将鼠标悬停在 (中) 的数据点时，可以看到检测到的欺骗邮件的个个和原因。</span><span class="sxs-lookup"><span data-stu-id="8add3-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="8add3-372">单击"**查看详细信息**"后，可以通过单击"筛选器"并选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="8add3-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="8add3-373">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-374">**结果**：</span><span class="sxs-lookup"><span data-stu-id="8add3-374">**Result**:</span></span>
  - <span data-ttu-id="8add3-375">**Pass**</span><span class="sxs-lookup"><span data-stu-id="8add3-375">**Pass**</span></span>
  - <span data-ttu-id="8add3-376">**失败**</span><span class="sxs-lookup"><span data-stu-id="8add3-376">**Fail**</span></span>
  - <span data-ttu-id="8add3-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="8add3-377">**SoftPass**</span></span>
  - <span data-ttu-id="8add3-378">**无**</span><span class="sxs-lookup"><span data-stu-id="8add3-378">**None**</span></span>
  - <span data-ttu-id="8add3-379">**其他**</span><span class="sxs-lookup"><span data-stu-id="8add3-379">**Other**</span></span>
- <span data-ttu-id="8add3-380">**欺骗类型**：**内部和外部**</span><span class="sxs-lookup"><span data-stu-id="8add3-380">**Spoof type**: **Internal** and **External**</span></span>

![电子邮件门户中的欺骗邮件Microsoft 365 Defender页面](../../media/spoof-detections-report-page.png)

<span data-ttu-id="8add3-382">在图表下面的表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="8add3-383">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-383">**Date**</span></span>
- <span data-ttu-id="8add3-384">**欺骗用户**</span><span class="sxs-lookup"><span data-stu-id="8add3-384">**Spoofed user**</span></span>
- <span data-ttu-id="8add3-385">**发送基础结构**</span><span class="sxs-lookup"><span data-stu-id="8add3-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="8add3-386">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-386">**Spoof type**</span></span>
- <span data-ttu-id="8add3-387">**结果**</span><span class="sxs-lookup"><span data-stu-id="8add3-387">**Result**</span></span>
- <span data-ttu-id="8add3-388">**结果代码**</span><span class="sxs-lookup"><span data-stu-id="8add3-388">**Result code**</span></span>
- <span data-ttu-id="8add3-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="8add3-389">**SPF**</span></span>
- <span data-ttu-id="8add3-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="8add3-390">**DKIM**</span></span>
- <span data-ttu-id="8add3-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="8add3-391">**DMARC**</span></span>
- <span data-ttu-id="8add3-392">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="8add3-392">**Message count**</span></span>

<span data-ttu-id="8add3-393">有关复合身份验证结果代码详细信息，请参阅邮件中的[反垃圾邮件Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="8add3-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="8add3-394">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="8add3-394">Threat protection status report</span></span>

<span data-ttu-id="8add3-395">威胁 **防护状态报告** 在 EOP 和 Defender for Office 365;但是，报告包含不同的数据。</span><span class="sxs-lookup"><span data-stu-id="8add3-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="8add3-396">例如，EOP 客户可以查看有关电子邮件中检测到的恶意软件的信息，但不能查看有关 SharePoint、OneDrive 和 Microsoft Teams 的 保险箱 附件检测到的恶意[文件的信息](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="8add3-397">该报告提供包含恶意内容的电子邮件（如反恶意软件引擎阻止的文件或网站地址 (URL) 、零时差自动清除[ (ZAP) ](zero-hour-auto-purge.md)和 Defender 等 Office 365 功能（如 保险箱[链接](safe-links.md)[、保险箱](safe-attachments.md)附件和防钓鱼策略中的模拟保护功能）的计数。 [](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="8add3-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="8add3-398">您可以使用此信息来确定趋势或确定组织策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="8add3-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="8add3-399">**注意**：如果邮件发送给五个收件人，则我们将邮件计为五个不同的邮件，而不是一封邮件，了解这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="8add3-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="8add3-400">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="8add3-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-401">在 **"威胁防护状态"上**，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="8add3-402">若要直接转到报告，请打开以下 URL 之一：</span><span class="sxs-lookup"><span data-stu-id="8add3-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="8add3-403">Defender for Office 365：<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="8add3-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="8add3-404">EOP： <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="8add3-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

!["电子邮件和协作报告"页面上的威胁&小组件](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="8add3-406">默认情况下，单击"查看 **详细信息"后**，图表将显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="8add3-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="8add3-407">如果单击 **"筛选**"，可以选择 90 天的日期范围 (试用版订阅可能限制为 30) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="8add3-408">详细信息表允许筛选 30 天。</span><span class="sxs-lookup"><span data-stu-id="8add3-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="8add3-409">以下各节介绍了可用的视图。</span><span class="sxs-lookup"><span data-stu-id="8add3-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="8add3-410">按概述查看数据</span><span class="sxs-lookup"><span data-stu-id="8add3-410">View data by Overview</span></span>

![威胁防护状态报告中的概述视图](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="8add3-412">在 **"按概述查看数据"** 视图中，图表中显示了以下检测信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="8add3-413">**电子邮件恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-413">**Email malware**</span></span>
- <span data-ttu-id="8add3-414">**电子邮件钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-414">**Email phish**</span></span>
- <span data-ttu-id="8add3-415">**内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-415">**Content malware**</span></span>

<span data-ttu-id="8add3-416">图表下方没有详细信息表。</span><span class="sxs-lookup"><span data-stu-id="8add3-416">No details table is available below the chart.</span></span>

<span data-ttu-id="8add3-417">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-418">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-419">**检测**：**电子邮件恶意软件\*\*\*\*、电子邮件钓鱼** 邮件或 **内容恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="8add3-420">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="8add3-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="8add3-421">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="8add3-422">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="8add3-423">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-423">**Direction**</span></span>
- <span data-ttu-id="8add3-424">**域**</span><span class="sxs-lookup"><span data-stu-id="8add3-424">**Domain**</span></span>
- <span data-ttu-id="8add3-425">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-425">**Policy type**</span></span>

<span data-ttu-id="8add3-426">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="8add3-427">通过电子邮件钓鱼查看 \> 数据，按检测技术查看图表细目</span><span class="sxs-lookup"><span data-stu-id="8add3-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![威胁防护状态报告中的网络钓鱼电子邮件的检测技术视图](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="8add3-429">在" **通过电子邮件查看数据" \>** 和"按检测技术查看图表细分 **"** 视图中，图表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="8add3-430">**URL 恶意信誉** <sup>\*</sup> ：来自 Defender 的恶意 URL 信誉Office 365客户的其他Microsoft 365触发。</span><span class="sxs-lookup"><span data-stu-id="8add3-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="8add3-431">**高级筛选器**：基于机器学习的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="8add3-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="8add3-432">**常规筛选器**：基于分析员规则的网络钓鱼信号。</span><span class="sxs-lookup"><span data-stu-id="8add3-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="8add3-433">**欺骗组织内部**：发件人正在尝试欺骗收件人域。</span><span class="sxs-lookup"><span data-stu-id="8add3-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="8add3-434">**欺骗外部域**：发件人正在尝试欺骗某些其他域。</span><span class="sxs-lookup"><span data-stu-id="8add3-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="8add3-435">**欺骗 DMARC：** 邮件上的 DMARC 身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="8add3-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="8add3-436">**模拟品牌**：模拟基于发件人的已知品牌。</span><span class="sxs-lookup"><span data-stu-id="8add3-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="8add3-437">**混合分析检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="8add3-438">**文件信誉**</span><span class="sxs-lookup"><span data-stu-id="8add3-438">**File reputation**</span></span>
- <span data-ttu-id="8add3-439">**指纹匹配**</span><span class="sxs-lookup"><span data-stu-id="8add3-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="8add3-440">**URL 触发信誉**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-441">**URL 触发**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-442">**模拟用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-443">**模拟域** <sup>\*</sup> ：模拟客户拥有或定义的域。</span><span class="sxs-lookup"><span data-stu-id="8add3-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="8add3-444">**邮箱智能模拟** <sup>\*</sup> ：模拟由管理员定义或通过邮箱智能学习的用户。</span><span class="sxs-lookup"><span data-stu-id="8add3-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="8add3-445">**文件触发**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-446">**宣传活动**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="8add3-447">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="8add3-448">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-448">**Date**</span></span>
- <span data-ttu-id="8add3-449">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-449">**Subject**</span></span>
- <span data-ttu-id="8add3-450">**发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-450">**Sender**</span></span>
- <span data-ttu-id="8add3-451">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="8add3-451">**Recipients**</span></span>
- <span data-ttu-id="8add3-452">**检测者**</span><span class="sxs-lookup"><span data-stu-id="8add3-452">**Detected by**</span></span>
- <span data-ttu-id="8add3-453">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="8add3-453">**Delivery Status**</span></span>
- <span data-ttu-id="8add3-454">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="8add3-454">**Source of Compromise**</span></span>
- <span data-ttu-id="8add3-455">**Tags**</span><span class="sxs-lookup"><span data-stu-id="8add3-455">**Tags**</span></span>

<span data-ttu-id="8add3-456">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-457">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-458">**检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-458">**Detection**</span></span>
- <span data-ttu-id="8add3-459">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="8add3-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="8add3-460">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-460">**Direction**</span></span>
- <span data-ttu-id="8add3-461">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="8add3-462">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="8add3-463">**域**</span><span class="sxs-lookup"><span data-stu-id="8add3-463">**Domain**</span></span>
- <span data-ttu-id="8add3-464">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-464">**Policy type**</span></span>
- <span data-ttu-id="8add3-465">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="8add3-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="8add3-466">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-466">**Recipients**</span></span>

<span data-ttu-id="8add3-467">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="8add3-468">按电子邮件恶意软件查看 \> 数据，按检测技术查看图表细目</span><span class="sxs-lookup"><span data-stu-id="8add3-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![威胁防护状态报告中恶意软件的检测技术视图](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="8add3-470">在" **通过电子邮件查看数据 \> "和** "按检测技术查看图表细分 **"** 视图中，图表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="8add3-471">**文件触发** <sup>\*</sup> ：按附件保险箱检测。</span><span class="sxs-lookup"><span data-stu-id="8add3-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="8add3-472">**文件触发信誉** <sup>\*</sup> ：Defender 为安全触发生成的所有恶意Office 365信誉。</span><span class="sxs-lookup"><span data-stu-id="8add3-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="8add3-473">**文件信誉**</span><span class="sxs-lookup"><span data-stu-id="8add3-473">**File reputation**</span></span>
- <span data-ttu-id="8add3-474">**反恶意软件引擎** <sup>\*</sup> ：来自反恶意软件引擎的检测。</span><span class="sxs-lookup"><span data-stu-id="8add3-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="8add3-475">**反恶意软件策略文件类型阻止**：这些是由于邮件中标识的恶意文件类型而筛选掉的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8add3-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="8add3-476">**URL 恶意声誉**</span><span class="sxs-lookup"><span data-stu-id="8add3-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="8add3-477">**URL 设置**</span><span class="sxs-lookup"><span data-stu-id="8add3-477">**URL detonation**</span></span>
- <span data-ttu-id="8add3-478">**URL 组织的信誉**</span><span class="sxs-lookup"><span data-stu-id="8add3-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="8add3-479">**市场活动**</span><span class="sxs-lookup"><span data-stu-id="8add3-479">**Campaign**</span></span>

<span data-ttu-id="8add3-480">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="8add3-481">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-481">**Date**</span></span>
- <span data-ttu-id="8add3-482">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-482">**Subject**</span></span>
- <span data-ttu-id="8add3-483">**发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-483">**Sender**</span></span>
- <span data-ttu-id="8add3-484">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="8add3-484">**Recipients**</span></span>
- <span data-ttu-id="8add3-485">**检测者**</span><span class="sxs-lookup"><span data-stu-id="8add3-485">**Detected by**</span></span>
- <span data-ttu-id="8add3-486">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="8add3-486">**Delivery Status**</span></span>
- <span data-ttu-id="8add3-487">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="8add3-487">**Source of Compromise**</span></span>
- <span data-ttu-id="8add3-488">**Tags**</span><span class="sxs-lookup"><span data-stu-id="8add3-488">**Tags**</span></span>

<span data-ttu-id="8add3-489">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-490">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-491">**检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-491">**Detection**</span></span>
- <span data-ttu-id="8add3-492">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="8add3-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="8add3-493">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-493">**Direction**</span></span>
- <span data-ttu-id="8add3-494">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="8add3-495">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="8add3-496">**域**</span><span class="sxs-lookup"><span data-stu-id="8add3-496">**Domain**</span></span>
- <span data-ttu-id="8add3-497">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-497">**Policy type**</span></span>
- <span data-ttu-id="8add3-498">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="8add3-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="8add3-499">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-499">**Recipients**</span></span>

<span data-ttu-id="8add3-500">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="8add3-501">按策略类型和通过电子邮件查看数据或通过电子邮件恶意软件 \> 查看数据的图表 \> 细分</span><span class="sxs-lookup"><span data-stu-id="8add3-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威胁防护状态报告中网络钓鱼电子邮件或恶意软件电子邮件的策略类型视图](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="8add3-503">在 **"按策略类型划分** 的图表细分"和 **" \>** 通过电子邮件查看数据"或"通过电子邮件查看恶意软件数据"视图中，图表中显示了以下信息： **\>**</span><span class="sxs-lookup"><span data-stu-id="8add3-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="8add3-504">**反恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-504">**Anti-malware**</span></span>
- <span data-ttu-id="8add3-505">**保险箱附件**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8add3-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="8add3-506">**防钓鱼**</span><span class="sxs-lookup"><span data-stu-id="8add3-506">**Anti-phish**</span></span>
- <span data-ttu-id="8add3-507">**反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-507">**Anti-spam**</span></span>
- <span data-ttu-id="8add3-508">**邮件流规则** (也称为传输规则) </span><span class="sxs-lookup"><span data-stu-id="8add3-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="8add3-509">**其他**</span><span class="sxs-lookup"><span data-stu-id="8add3-509">**Others**</span></span>

<span data-ttu-id="8add3-510">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="8add3-511">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-511">**Date**</span></span>
- <span data-ttu-id="8add3-512">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-512">**Subject**</span></span>
- <span data-ttu-id="8add3-513">**发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-513">**Sender**</span></span>
- <span data-ttu-id="8add3-514">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="8add3-514">**Recipients**</span></span>
- <span data-ttu-id="8add3-515">**检测者**</span><span class="sxs-lookup"><span data-stu-id="8add3-515">**Detected by**</span></span>
- <span data-ttu-id="8add3-516">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="8add3-516">**Delivery Status**</span></span>
- <span data-ttu-id="8add3-517">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="8add3-517">**Source of Compromise**</span></span>
- <span data-ttu-id="8add3-518">**Tags**</span><span class="sxs-lookup"><span data-stu-id="8add3-518">**Tags**</span></span>

<span data-ttu-id="8add3-519">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-520">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-521">**检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-521">**Detection**</span></span>
- <span data-ttu-id="8add3-522">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="8add3-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="8add3-523">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-523">**Direction**</span></span>
- <span data-ttu-id="8add3-524">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="8add3-525">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="8add3-526">**域**</span><span class="sxs-lookup"><span data-stu-id="8add3-526">**Domain**</span></span>
- <span data-ttu-id="8add3-527">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-527">**Policy type**</span></span>
- <span data-ttu-id="8add3-528">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="8add3-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="8add3-529">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-529">**Recipients**</span></span>

<span data-ttu-id="8add3-530">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="8add3-531">按传递状态和通过电子邮件查看数据或通过电子邮件恶意软件 \> 查看数据的图表 \> 细分</span><span class="sxs-lookup"><span data-stu-id="8add3-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![威胁防护状态报告中的网络钓鱼电子邮件和恶意软件电子邮件的传递状态视图](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="8add3-533">在 **"按传递状态分类"** 和 **" \>** 通过电子邮件查看数据"或"通过电子邮件查看恶意软件数据"视图中，图表中显示了以下信息： **\>**</span><span class="sxs-lookup"><span data-stu-id="8add3-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="8add3-534">**托管邮箱：收件箱**</span><span class="sxs-lookup"><span data-stu-id="8add3-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="8add3-535">**托管邮箱：垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="8add3-536">**托管邮箱：自定义文件夹**</span><span class="sxs-lookup"><span data-stu-id="8add3-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="8add3-537">**托管邮箱：已删除项目**</span><span class="sxs-lookup"><span data-stu-id="8add3-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="8add3-538">**转发**</span><span class="sxs-lookup"><span data-stu-id="8add3-538">**Forwarded**</span></span>
- <span data-ttu-id="8add3-539">**本地服务器：已传递**</span><span class="sxs-lookup"><span data-stu-id="8add3-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="8add3-540">**隔离**</span><span class="sxs-lookup"><span data-stu-id="8add3-540">**Quarantine**</span></span>
- <span data-ttu-id="8add3-541">**传递失败**</span><span class="sxs-lookup"><span data-stu-id="8add3-541">**Delivery failed**</span></span>
- <span data-ttu-id="8add3-542">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="8add3-542">**Dropped**</span></span>

<span data-ttu-id="8add3-543">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="8add3-544">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-544">**Date**</span></span>
- <span data-ttu-id="8add3-545">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-545">**Subject**</span></span>
- <span data-ttu-id="8add3-546">**发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-546">**Sender**</span></span>
- <span data-ttu-id="8add3-547">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="8add3-547">**Recipients**</span></span>
- <span data-ttu-id="8add3-548">**检测者**</span><span class="sxs-lookup"><span data-stu-id="8add3-548">**Detected by**</span></span>
- <span data-ttu-id="8add3-549">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="8add3-549">**Delivery Status**</span></span>
- <span data-ttu-id="8add3-550">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="8add3-550">**Source of Compromise**</span></span>
- <span data-ttu-id="8add3-551">**Tags**</span><span class="sxs-lookup"><span data-stu-id="8add3-551">**Tags**</span></span>

<span data-ttu-id="8add3-552">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-553">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-554">**检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-554">**Detection**</span></span>
- <span data-ttu-id="8add3-555">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="8add3-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="8add3-556">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-556">**Direction**</span></span>
- <span data-ttu-id="8add3-557">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="8add3-558">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="8add3-559">**域**</span><span class="sxs-lookup"><span data-stu-id="8add3-559">**Domain**</span></span>
- <span data-ttu-id="8add3-560">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-560">**Policy type**</span></span>
- <span data-ttu-id="8add3-561">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="8add3-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="8add3-562">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-562">**Recipients**</span></span>

<span data-ttu-id="8add3-563">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="8add3-564">按内容恶意软件查看 \> 数据</span><span class="sxs-lookup"><span data-stu-id="8add3-564">View data by Content \> Malware</span></span>

![威胁防护状态报告中的内容恶意软件视图](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="8add3-566">在 **"按内容恶意软件查看 \>** 数据"视图中，以下信息显示在 Microsoft Defender for Office 365图表中：</span><span class="sxs-lookup"><span data-stu-id="8add3-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="8add3-567">**反恶意软件引擎**：Sharepoint、OneDrive 和 Microsoft Teams 中内置的病毒检测 [检测到的恶意](virus-detection-in-spo.md)Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8add3-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="8add3-568">**文件触发**：附件检测到的恶意保险箱 [文件SharePoint、OneDrive和Microsoft Teams。](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8add3-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="8add3-569">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="8add3-570">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-571">**位置**</span><span class="sxs-lookup"><span data-stu-id="8add3-571">**Location**</span></span>
- <span data-ttu-id="8add3-572">**检测者**</span><span class="sxs-lookup"><span data-stu-id="8add3-572">**Detected by**</span></span>
- <span data-ttu-id="8add3-573">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="8add3-573">**Malware name**</span></span>

<span data-ttu-id="8add3-574">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-575">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-576">**检测\*\*\*\*：反恶意软件引擎** 或 **文件触发**</span><span class="sxs-lookup"><span data-stu-id="8add3-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="8add3-577">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="8add3-578">按系统覆盖查看数据</span><span class="sxs-lookup"><span data-stu-id="8add3-578">View data by System override</span></span>

![威胁防护状态报告中的邮件替代视图](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="8add3-580">在" **按系统覆盖查看数据"视图中** ，图表中显示了以下替代原因信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="8add3-581">**本地跳过**</span><span class="sxs-lookup"><span data-stu-id="8add3-581">**On-premises skip**</span></span>
- <span data-ttu-id="8add3-582">**IP 允许**</span><span class="sxs-lookup"><span data-stu-id="8add3-582">**IP allow**</span></span>
- <span data-ttu-id="8add3-583">**Exchange邮件传输规则 (** 邮件流规则) </span><span class="sxs-lookup"><span data-stu-id="8add3-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="8add3-584">**组织允许的发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="8add3-585">**组织允许的域**</span><span class="sxs-lookup"><span data-stu-id="8add3-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="8add3-586">**ZAP 未启用**</span><span class="sxs-lookup"><span data-stu-id="8add3-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="8add3-587">**未启用垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="8add3-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="8add3-588">**用户保险箱发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-588">**User Safe Sender**</span></span>
- <span data-ttu-id="8add3-589">**用户保险箱域**</span><span class="sxs-lookup"><span data-stu-id="8add3-589">**User Safe Domain**</span></span>

<span data-ttu-id="8add3-590">在图表下面的详细信息表中，提供了以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="8add3-591">**Date**</span><span class="sxs-lookup"><span data-stu-id="8add3-591">**Date**</span></span>
- <span data-ttu-id="8add3-592">**主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-592">**Subject**</span></span>
- <span data-ttu-id="8add3-593">**发件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-593">**Sender**</span></span>
- <span data-ttu-id="8add3-594">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="8add3-594">**Recipients**</span></span>
- <span data-ttu-id="8add3-595">**检测者**</span><span class="sxs-lookup"><span data-stu-id="8add3-595">**Detected by**</span></span>
- <span data-ttu-id="8add3-596">**传递状态**</span><span class="sxs-lookup"><span data-stu-id="8add3-596">**Delivery Status**</span></span>
- <span data-ttu-id="8add3-597">**泄露来源**</span><span class="sxs-lookup"><span data-stu-id="8add3-597">**Source of Compromise**</span></span>
- <span data-ttu-id="8add3-598">**Tags**</span><span class="sxs-lookup"><span data-stu-id="8add3-598">**Tags**</span></span>

<span data-ttu-id="8add3-599">如果单击 **"筛选器"，** 则以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8add3-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="8add3-600">**Date**： **开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="8add3-601">**检测**</span><span class="sxs-lookup"><span data-stu-id="8add3-601">**Detection**</span></span>
- <span data-ttu-id="8add3-602">**受保护\*\*\*\*：MDO** (Defender for Office 365) **或 EOP**</span><span class="sxs-lookup"><span data-stu-id="8add3-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="8add3-603">**方向**</span><span class="sxs-lookup"><span data-stu-id="8add3-603">**Direction**</span></span>
- <span data-ttu-id="8add3-604">**Tag**：按应用了指定用户标记的用户或组筛选结果 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="8add3-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="8add3-605">有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="8add3-606">**域**</span><span class="sxs-lookup"><span data-stu-id="8add3-606">**Domain**</span></span>
- <span data-ttu-id="8add3-607">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="8add3-607">**Policy type**</span></span>
- <span data-ttu-id="8add3-608">**策略名称** (详细信息表) </span><span class="sxs-lookup"><span data-stu-id="8add3-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="8add3-609">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8add3-609">**Recipients**</span></span>

<span data-ttu-id="8add3-610">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="8add3-611"><sup>\*</sup>仅 defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8add3-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="8add3-612">热门恶意软件报告</span><span class="sxs-lookup"><span data-stu-id="8add3-612">Top malware report</span></span>

<span data-ttu-id="8add3-613">" **热门恶意软件** "报告显示 [EOP](anti-malware-protection.md)中的反恶意软件保护检测到的各种恶意软件。</span><span class="sxs-lookup"><span data-stu-id="8add3-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="8add3-614">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & Email** & collaboration \> **reports**.</span><span class="sxs-lookup"><span data-stu-id="8add3-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="8add3-615">在 **"热门恶意软件"** 上，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="8add3-616">若要直接转到报告，请打开 <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

!["电子邮件和协作报告"页面上&恶意软件小组件](../../media/top-malware-report-widget.png)

<span data-ttu-id="8add3-618">当您将鼠标悬停在饼图中的一个浮点上时，可以看到某种恶意软件的名称，以及检测到具有该恶意软件的邮件数。</span><span class="sxs-lookup"><span data-stu-id="8add3-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="8add3-619">单击" **查看详细信息"** 后，报表页上将显示饼图的较大版本。图表下面的详细信息表显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="8add3-620">**热门恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-620">**Top malware**</span></span>
- <span data-ttu-id="8add3-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="8add3-621">**Count**</span></span>

<span data-ttu-id="8add3-622">If you click **Filter**， you can specify a date range with **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="8add3-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![热门恶意软件报表视图](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="8add3-624">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="8add3-624">URL threat protection report</span></span>

<span data-ttu-id="8add3-625">Microsoft Defender for Office 365 中提供了 **URL** 威胁防护报告。</span><span class="sxs-lookup"><span data-stu-id="8add3-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8add3-626">有关详细信息，请参阅 [URL 威胁防护报告](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="8add3-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="8add3-627">用户报告的邮件报告</span><span class="sxs-lookup"><span data-stu-id="8add3-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8add3-628">为了使用户 **报告的消息** 报告正常工作，必须为用户报告的环境启用Microsoft 365日志记录。</span><span class="sxs-lookup"><span data-stu-id="8add3-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="8add3-629">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="8add3-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="8add3-630">有关详细信息，请参阅打开[Microsoft 365 审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="8add3-631">用户 **报告的邮件** 报告显示有关用户使用报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、网络钓鱼尝试或良好邮件 [的电子邮件的信息](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="8add3-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="8add3-632">To view the report in the Microsoft 365 Defender portal， go to **Reports** \> **Email & collaboration** Email & \> **reports** User \> **reported messages**.</span><span class="sxs-lookup"><span data-stu-id="8add3-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="8add3-633">在 **"用户报告的邮件"上**，单击 **"查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="8add3-634">若要直接转到报告，请打开 <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="8add3-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="8add3-635">若要转到管理 [门户中的管理员Microsoft 365 Defender，请单击](admin-submission.md)**"转到提交"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

!["电子邮件和协作报告"页上&"用户报告的邮件"小组件](../../media/user-reported-messages-widget.png)

<span data-ttu-id="8add3-637">单击"**查看详细信息**"后，可以通过单击"筛选器"，在出现的飞出视图中选择以下一个或多个值来筛选图表和详细信息表：</span><span class="sxs-lookup"><span data-stu-id="8add3-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="8add3-638">**报告的日期\*\*\*\*：开始时间和\*\*\*\*结束时间**</span><span class="sxs-lookup"><span data-stu-id="8add3-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="8add3-639">**报告者**</span><span class="sxs-lookup"><span data-stu-id="8add3-639">**Reported by**</span></span>
- <span data-ttu-id="8add3-640">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-640">**Email subject**</span></span>
- <span data-ttu-id="8add3-641">**邮件报告 ID**</span><span class="sxs-lookup"><span data-stu-id="8add3-641">**Message reported ID**</span></span>
- <span data-ttu-id="8add3-642">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="8add3-642">**Network Message ID**</span></span>
- <span data-ttu-id="8add3-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8add3-643">**Sender**</span></span>
- <span data-ttu-id="8add3-644">**报告的原因**</span><span class="sxs-lookup"><span data-stu-id="8add3-644">**Reported reason**</span></span>
  - <span data-ttu-id="8add3-645">**非垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-645">**Not junk**</span></span>
  - <span data-ttu-id="8add3-646">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="8add3-646">**Phish**</span></span>
  - <span data-ttu-id="8add3-647">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8add3-647">**Spam**</span></span>
- <span data-ttu-id="8add3-648">**网络钓鱼模拟**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="8add3-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="8add3-649">配置完筛选器后，请单击"应用"、"**取消**"或"清除 **筛选器"。**</span><span class="sxs-lookup"><span data-stu-id="8add3-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="8add3-650">若要对条目进行分组，请单击 **"分组** "，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8add3-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="8add3-651">**无**</span><span class="sxs-lookup"><span data-stu-id="8add3-651">**None**</span></span>
- <span data-ttu-id="8add3-652">**原因**</span><span class="sxs-lookup"><span data-stu-id="8add3-652">**Reason**</span></span>
- <span data-ttu-id="8add3-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8add3-653">**Sender**</span></span>
- <span data-ttu-id="8add3-654">**报告者**</span><span class="sxs-lookup"><span data-stu-id="8add3-654">**Reported by**</span></span>
- <span data-ttu-id="8add3-655">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="8add3-655">**Rescan result**</span></span>
- <span data-ttu-id="8add3-656">**网络钓鱼模拟**</span><span class="sxs-lookup"><span data-stu-id="8add3-656">**Phish simulation**</span></span>

![用户报告的邮件报告](../../media/user-reported-messages-report.png)

<span data-ttu-id="8add3-658">在图表下面的表中，可以看到以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8add3-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="8add3-659">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="8add3-659">**Email subject**</span></span>
- <span data-ttu-id="8add3-660">**报告者**</span><span class="sxs-lookup"><span data-stu-id="8add3-660">**Reported by**</span></span>
- <span data-ttu-id="8add3-661">**报告的日期**</span><span class="sxs-lookup"><span data-stu-id="8add3-661">**Date reported**</span></span>
- <span data-ttu-id="8add3-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8add3-662">**Sender**</span></span>
- <span data-ttu-id="8add3-663">**报告的原因**</span><span class="sxs-lookup"><span data-stu-id="8add3-663">**Reported reason**</span></span>
- <span data-ttu-id="8add3-664">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="8add3-664">**Rescan result**</span></span>
- <span data-ttu-id="8add3-665">**Tags**</span><span class="sxs-lookup"><span data-stu-id="8add3-665">**Tags**</span></span>

<span data-ttu-id="8add3-666">若要将邮件提交给 Microsoft 进行分析，请从表中选择邮件条目，单击"提交给 **Microsoft** 进行分析"，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="8add3-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="8add3-667">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="8add3-667">**Report clean**</span></span>
- <span data-ttu-id="8add3-668">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="8add3-668">**Report phishing**</span></span>
- <span data-ttu-id="8add3-669">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="8add3-669">**Report malware**</span></span>
- <span data-ttu-id="8add3-670">**报告垃圾邮件**'</span><span class="sxs-lookup"><span data-stu-id="8add3-670">**Report spam**'</span></span>
- <span data-ttu-id="8add3-671">**触发 Defender** (调查Office 365) </span><span class="sxs-lookup"><span data-stu-id="8add3-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="8add3-672">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="8add3-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="8add3-673">若要查看和使用本文中所述的报告，你需要是本文门户中以下角色组之一Microsoft 365 Defender成员：</span><span class="sxs-lookup"><span data-stu-id="8add3-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="8add3-674">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="8add3-674">**Organization Management**</span></span>
- <span data-ttu-id="8add3-675">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="8add3-675">**Security Administrator**</span></span>
- <span data-ttu-id="8add3-676">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="8add3-676">**Security Reader**</span></span>
- <span data-ttu-id="8add3-677">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="8add3-677">**Global Reader**</span></span>

<span data-ttu-id="8add3-678">有关详细信息，请参阅应用程序[门户中Microsoft 365 Defender权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="8add3-679">**注意**：向 Microsoft 365 管理中心 中的相应 Azure Active Directory 角色添加用户会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 </span><span class="sxs-lookup"><span data-stu-id="8add3-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8add3-680">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="8add3-681">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="8add3-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="8add3-682">如果报告中未显示数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="8add3-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="8add3-683">若要了解更多信息，请参阅 [防范威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="8add3-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8add3-684">相关主题</span><span class="sxs-lookup"><span data-stu-id="8add3-684">Related topics</span></span>

[<span data-ttu-id="8add3-685">EOP 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="8add3-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="8add3-686">智能报表和 Microsoft 365 Defender见解</span><span class="sxs-lookup"><span data-stu-id="8add3-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="8add3-687">在邮件门户中查看Microsoft 365 Defender报告</span><span class="sxs-lookup"><span data-stu-id="8add3-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="8add3-688">查看 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8add3-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
