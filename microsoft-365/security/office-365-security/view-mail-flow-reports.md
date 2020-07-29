---
title: 查看安全与合规中心中的邮件流报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解如何查找和使用组织的邮件流安全报告。 "安全性 & 合规性中心中提供了邮件流报告。
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434175"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="eb082-104">查看安全与合规中心中的邮件流报告</span><span class="sxs-lookup"><span data-stu-id="eb082-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="eb082-105">除了安全性 & 合规性中心中提供的[邮件流见解](mail-flow-insights-v2.md)之外，还可以使用多种邮件流报告来帮助您监视 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="eb082-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="eb082-106">如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以 <https://office.protection.com> 通过转到 "**报告**" \> **仪表板**，在安全 & 合规性中心中查看这些报告。</span><span class="sxs-lookup"><span data-stu-id="eb082-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="eb082-107">若要直接转到 "报表" 仪表板，请打开 <https://office.protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="eb082-109">连接器报告</span><span class="sxs-lookup"><span data-stu-id="eb082-109">Connector report</span></span>

<span data-ttu-id="eb082-110">**连接器报告**显示为您的组织配置的[入站和出站连接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的 "邮件流" 活动。</span><span class="sxs-lookup"><span data-stu-id="eb082-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="eb082-111">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**连接器报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="eb082-112">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

!["报告" 仪表板中的连接器报告小部件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="eb082-114">连接器报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="eb082-114">Report view for the Connector report</span></span>

<span data-ttu-id="eb082-115">以下图表在报表视图中可用：</span><span class="sxs-lookup"><span data-stu-id="eb082-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="eb082-116">**数据查看依据：邮件流**：此图显示按以下方式组织的入站和出站邮件的数量：</span><span class="sxs-lookup"><span data-stu-id="eb082-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="eb082-117">**Total**</span><span class="sxs-lookup"><span data-stu-id="eb082-117">**Total**</span></span>
  - <span data-ttu-id="eb082-118">**从不带连接器的 internet**</span><span class="sxs-lookup"><span data-stu-id="eb082-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="eb082-119">**不带连接器的 internet 连接**</span><span class="sxs-lookup"><span data-stu-id="eb082-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="eb082-120">您已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="eb082-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="eb082-121">若要隔离图表中的数据，请使用 "**显示数据以供**控制" 选择其中一个选项或**所有邮件流**。</span><span class="sxs-lookup"><span data-stu-id="eb082-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![通过邮件流查看连接器报告中的数据](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="eb082-123">**数据查看依据： TLS 用法**：此图显示邮件流的传输层安全性（TLS）版本使用百分比。</span><span class="sxs-lookup"><span data-stu-id="eb082-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="eb082-124">若要隔离图表中的数据，请使用 "**显示数据以供**控制" 选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="eb082-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="eb082-125">**所有邮件流**</span><span class="sxs-lookup"><span data-stu-id="eb082-125">**All mail flow**</span></span>
  - <span data-ttu-id="eb082-126">**从不带连接器的 internet**</span><span class="sxs-lookup"><span data-stu-id="eb082-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="eb082-127">**不带连接器的 internet 连接**</span><span class="sxs-lookup"><span data-stu-id="eb082-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="eb082-128">您已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="eb082-128">A specific connector that you've configured.</span></span>

  ![通过 TLS 使用在连接器报告中查看数据](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="eb082-130">如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="eb082-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="eb082-131">连接器报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="eb082-131">Details table view for the Connector report</span></span>

<span data-ttu-id="eb082-132">如果您在报告视图中单击 "**查看详细信息表**"，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="eb082-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="eb082-133">**Date**</span><span class="sxs-lookup"><span data-stu-id="eb082-133">**Date**</span></span>
- <span data-ttu-id="eb082-134">**连接器方向和名称**</span><span class="sxs-lookup"><span data-stu-id="eb082-134">**Connector direction and name**</span></span>
- <span data-ttu-id="eb082-135">**连接器类型**</span><span class="sxs-lookup"><span data-stu-id="eb082-135">**Connector type**</span></span>
- <span data-ttu-id="eb082-136">**强制 TLS？**：值**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="eb082-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="eb082-137">**无 TLS** （百分比）</span><span class="sxs-lookup"><span data-stu-id="eb082-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="eb082-138">**TLS 1.0** （百分比）</span><span class="sxs-lookup"><span data-stu-id="eb082-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="eb082-139">**TLS 1.1** （百分比）</span><span class="sxs-lookup"><span data-stu-id="eb082-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="eb082-140">**TLS 1.2** （百分比）</span><span class="sxs-lookup"><span data-stu-id="eb082-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="eb082-141">**Volume**：邮件数。</span><span class="sxs-lookup"><span data-stu-id="eb082-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="eb082-142">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="eb082-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="eb082-143">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="eb082-144">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="eb082-144">Exchange transport rule report</span></span>

<span data-ttu-id="eb082-145">**Exchange 传输规则报告**显示了邮件流规则（也称为传输规则）对组织中的传入和传出邮件的影响。</span><span class="sxs-lookup"><span data-stu-id="eb082-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="eb082-146">若要查看报告，请打开[安全 & 合规中心](https://protection.office.com)，转到 "**报告** \> **仪表板**"，然后选择 " **Exchange 传输规则**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="eb082-147">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

!["报告" 仪表板中的 Exchange 传输规则小部件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="eb082-149">Exchange 传输规则报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="eb082-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="eb082-150">以下图表在报表视图中可用：</span><span class="sxs-lookup"><span data-stu-id="eb082-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="eb082-151">**数据查看依据： Exchange 传输规则** \>**分解方式：方向**：此图显示受传输规则影响的**入站**和**出站**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="eb082-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="eb082-152">**数据查看依据： Exchange 传输规则** \>**分解方式：严重性**：此图显示**高严重性**和**中低严重性**以及**低严重性**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="eb082-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="eb082-153">将严重性级别设置为规则中的操作（**使用严重性级别或 SetAuditSeverity 审核此规则**） _SetAuditSeverity_。</span><span class="sxs-lookup"><span data-stu-id="eb082-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="eb082-154">有关详细信息，请参阅[Exchange Online 中的邮件流规则操作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="eb082-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="eb082-155">**数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此图显示受数据丢失防护（DLP）传输规则影响的**入站**和**出站**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="eb082-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="eb082-156">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="eb082-157">**显示以下项的数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="eb082-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="eb082-158">**显示以下项的数据：已损坏的用户**</span><span class="sxs-lookup"><span data-stu-id="eb082-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="eb082-159">**显示以下项的数据：检测到的内容量过低美国爱国法案**</span><span class="sxs-lookup"><span data-stu-id="eb082-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="eb082-160">**数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此视图显示**高严重性**和**中严重性**的数目以及受 DLP 传输规则影响的**低严重性**邮件。</span><span class="sxs-lookup"><span data-stu-id="eb082-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="eb082-161">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="eb082-162">**显示以下项的数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="eb082-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="eb082-163">**显示以下项的数据：已损坏的用户**</span><span class="sxs-lookup"><span data-stu-id="eb082-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="eb082-164">**显示以下项的数据：检测到的内容量过低美国爱国法案**</span><span class="sxs-lookup"><span data-stu-id="eb082-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="eb082-165">如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：：</span><span class="sxs-lookup"><span data-stu-id="eb082-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="eb082-166">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="eb082-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb082-167">方向值</span><span class="sxs-lookup"><span data-stu-id="eb082-167">Direction values</span></span>
- <span data-ttu-id="eb082-168">严重度值</span><span class="sxs-lookup"><span data-stu-id="eb082-168">Severity values</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="eb082-170">Exchange 传输规则报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="eb082-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="eb082-171">如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="eb082-172">**数据查看依据： Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="eb082-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="eb082-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="eb082-173">**Date**</span></span>
  - <span data-ttu-id="eb082-174">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="eb082-174">**Transport rule**</span></span>
  - <span data-ttu-id="eb082-175">**主题**</span><span class="sxs-lookup"><span data-stu-id="eb082-175">**Subject**</span></span>
  - <span data-ttu-id="eb082-176">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="eb082-176">**Sender address**</span></span>
  - <span data-ttu-id="eb082-177">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="eb082-177">**Recipient address**</span></span>
  - <span data-ttu-id="eb082-178">**严重性**</span><span class="sxs-lookup"><span data-stu-id="eb082-178">**Severity**</span></span>
  - <span data-ttu-id="eb082-179">**方向**</span><span class="sxs-lookup"><span data-stu-id="eb082-179">**Direction**</span></span>

- <span data-ttu-id="eb082-180">**数据查看依据： DLP Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="eb082-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="eb082-181">**Date**</span><span class="sxs-lookup"><span data-stu-id="eb082-181">**Date**</span></span>
  - <span data-ttu-id="eb082-182">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="eb082-182">**DLP policy**</span></span>
  - <span data-ttu-id="eb082-183">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="eb082-183">**Transport rule**</span></span>
  - <span data-ttu-id="eb082-184">**主题**</span><span class="sxs-lookup"><span data-stu-id="eb082-184">**Subject**</span></span>
  - <span data-ttu-id="eb082-185">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="eb082-185">**Sender address**</span></span>
  - <span data-ttu-id="eb082-186">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="eb082-186">**Recipient address**</span></span>
  - <span data-ttu-id="eb082-187">**严重性**</span><span class="sxs-lookup"><span data-stu-id="eb082-187">**Severity**</span></span>
  - <span data-ttu-id="eb082-188">**方向**</span><span class="sxs-lookup"><span data-stu-id="eb082-188">**Direction**</span></span>

<span data-ttu-id="eb082-189">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="eb082-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="eb082-190">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="eb082-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb082-191">方向值</span><span class="sxs-lookup"><span data-stu-id="eb082-191">Direction values</span></span>
- <span data-ttu-id="eb082-192">严重度值</span><span class="sxs-lookup"><span data-stu-id="eb082-192">Severity values</span></span>

<span data-ttu-id="eb082-193">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="eb082-194">转发报告</span><span class="sxs-lookup"><span data-stu-id="eb082-194">Forwarding report</span></span>

<span data-ttu-id="eb082-195">**转发报告**将组织的自动转发的邮件显示为 Exchange Online 邮箱中的外部域。</span><span class="sxs-lookup"><span data-stu-id="eb082-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="eb082-196">转发的邮件可能会带来安全或合规性风险，并可能指示已损坏的帐户。</span><span class="sxs-lookup"><span data-stu-id="eb082-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="eb082-197">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**转发报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="eb082-198">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

!["报告" 仪表板中的转发报告构件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="eb082-200">转发报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="eb082-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="eb082-201">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="eb082-202">显示以下各项**的数据：转发方法**：显示以下方法：</span><span class="sxs-lookup"><span data-stu-id="eb082-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="eb082-203">**传输规则**：也称为[邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="eb082-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="eb082-204">**邮箱规则**：也称为[收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="eb082-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="eb082-206">**显示数据：转发域**：此视图显示作为转发目标的收件人域。</span><span class="sxs-lookup"><span data-stu-id="eb082-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="eb082-208">**显示以下项的数据：转发器**：显示以下转发器：</span><span class="sxs-lookup"><span data-stu-id="eb082-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="eb082-209">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="eb082-209">**Transport rule**</span></span>
  - <span data-ttu-id="eb082-210">包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="eb082-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![转发报告中的转发器视图](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="eb082-212">如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="eb082-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="eb082-213">转发报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="eb082-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="eb082-214">如果您在报告视图中单击 "**查看详细信息表**"，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="eb082-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="eb082-215">**转发器**：值**传输规则**或包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="eb082-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="eb082-216">**转发类型**：值**邮箱规则**或**传输规则**。</span><span class="sxs-lookup"><span data-stu-id="eb082-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="eb082-217">**收件人名称**</span><span class="sxs-lookup"><span data-stu-id="eb082-217">**Recipient name**</span></span>
- <span data-ttu-id="eb082-218">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="eb082-218">**Recipient domain**</span></span>
- <span data-ttu-id="eb082-219">**详细信息**：这是邮件流规则的 GUID 值，或收件箱规则的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="eb082-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="eb082-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="eb082-220">**Count**</span></span>
- <span data-ttu-id="eb082-221">**第一次转发日期**</span><span class="sxs-lookup"><span data-stu-id="eb082-221">**First forward date**</span></span>

<span data-ttu-id="eb082-222">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="eb082-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="eb082-223">若要返回到 "报告" 视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="eb082-224">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="eb082-224">Mailflow status report</span></span>

<span data-ttu-id="eb082-225">**邮件流状态报告**类似于[发送和接收的电子邮件报告](#sent-and-received-email-report)，其中包含有关在边缘上允许或阻止的电子邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="eb082-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="eb082-226">这是唯一包含 edge 保护信息的报告，仅显示 Exchange Online Protection （EOP）在评估服务中被允许的电子邮件数量。</span><span class="sxs-lookup"><span data-stu-id="eb082-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="eb082-227">若要查看报表，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**邮件流状态报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="eb082-228">若要直接转到 "**邮件流状态" 报告**，请打开 <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

!["报告" 仪表板中的邮件流状态报告小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="eb082-230">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="eb082-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="eb082-231">打开报表时，"**类型**" 选项卡在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="eb082-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="eb082-232">默认情况下，此视图包含一个使用以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="eb082-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="eb082-233">**日期**：最近7天。</span><span class="sxs-lookup"><span data-stu-id="eb082-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="eb082-234">**方向**：</span><span class="sxs-lookup"><span data-stu-id="eb082-234">**Direction**:</span></span>

  - <span data-ttu-id="eb082-235">**进货**</span><span class="sxs-lookup"><span data-stu-id="eb082-235">**Inbound**</span></span>
  - <span data-ttu-id="eb082-236">**出站**</span><span class="sxs-lookup"><span data-stu-id="eb082-236">**Outbound**</span></span>
  - <span data-ttu-id="eb082-237">**组织内**（独立于**入站**和**出站**计数）</span><span class="sxs-lookup"><span data-stu-id="eb082-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="eb082-238">**类型**：</span><span class="sxs-lookup"><span data-stu-id="eb082-238">**Type**:</span></span>

  - <span data-ttu-id="eb082-239">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="eb082-239">**Good mail**</span></span>
  - <span data-ttu-id="eb082-240">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="eb082-240">**Malware**</span></span>
  - <span data-ttu-id="eb082-241">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="eb082-241">**Spam**</span></span>
  - <span data-ttu-id="eb082-242">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="eb082-242">**Edge protection**</span></span>
  - <span data-ttu-id="eb082-243">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="eb082-243">**Rule messages**</span></span>
  - <span data-ttu-id="eb082-244">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="eb082-244">**Phishing email**</span></span>

<span data-ttu-id="eb082-245">图表按**类型**值进行组织。</span><span class="sxs-lookup"><span data-stu-id="eb082-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="eb082-246">您可以通过单击 "**筛选器**" 或单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="eb082-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="eb082-247">数据表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="eb082-247">The data table contains the following information:</span></span>

- <span data-ttu-id="eb082-248">**方向**</span><span class="sxs-lookup"><span data-stu-id="eb082-248">**Direction**</span></span>
- <span data-ttu-id="eb082-249">**类型**</span><span class="sxs-lookup"><span data-stu-id="eb082-249">**Type**</span></span>
- <span data-ttu-id="eb082-250">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="eb082-250">**24 hours**</span></span>
- <span data-ttu-id="eb082-251">**3 天**</span><span class="sxs-lookup"><span data-stu-id="eb082-251">**3 days**</span></span>
- <span data-ttu-id="eb082-252">**7 天**</span><span class="sxs-lookup"><span data-stu-id="eb082-252">**7 days**</span></span>
- <span data-ttu-id="eb082-253">**15 天**</span><span class="sxs-lookup"><span data-stu-id="eb082-253">**15 days**</span></span>
- <span data-ttu-id="eb082-254">**30 天**</span><span class="sxs-lookup"><span data-stu-id="eb082-254">**30 days**</span></span>

<span data-ttu-id="eb082-255">如果单击 "**选择类别" 以了解更多详细信息**，则可以从以下值中进行选择：</span><span class="sxs-lookup"><span data-stu-id="eb082-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="eb082-256">**网络钓鱼电子邮件**：此选择会将您带到[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="eb082-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="eb082-257">**电子邮件中的恶意软件**：此选择会将您带到[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="eb082-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="eb082-258">**垃圾邮件检测**：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="eb082-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="eb082-259">**边缘阻止的垃圾邮件**：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="eb082-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="eb082-260">**导出**：</span><span class="sxs-lookup"><span data-stu-id="eb082-260">**Export**:</span></span>

<span data-ttu-id="eb082-261">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="eb082-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="eb082-262">因此，如果要将数据导出7天，则需要执行7个不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="eb082-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="eb082-263">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="eb082-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="eb082-264">如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="eb082-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="eb082-265">邮件流状态报告中的类型视图</span><span class="sxs-lookup"><span data-stu-id="eb082-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="eb082-266">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="eb082-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="eb082-267">如果单击 "**方向**" 选项卡，则将使用 "**类型**" 视图中的相同默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="eb082-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="eb082-268">图表按**方向**值组织。</span><span class="sxs-lookup"><span data-stu-id="eb082-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="eb082-269">您可以通过单击 "**筛选器**" 或通过单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="eb082-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="eb082-270">将使用 "**类型**" 视图中的相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="eb082-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="eb082-271">数据表包含**类型**视图中的相同信息。</span><span class="sxs-lookup"><span data-stu-id="eb082-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="eb082-272">**选择类别以获取更多详细信息**可用的选择和行为与 "**类型**" 视图相同。</span><span class="sxs-lookup"><span data-stu-id="eb082-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="eb082-273">**导出**：</span><span class="sxs-lookup"><span data-stu-id="eb082-273">**Export**:</span></span>

<span data-ttu-id="eb082-274">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="eb082-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="eb082-275">因此，如果要将数据导出7天，则需要执行7个不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="eb082-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="eb082-276">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="eb082-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="eb082-277">如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="eb082-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="eb082-278">邮件流状态报告中的 "方向" 视图</span><span class="sxs-lookup"><span data-stu-id="eb082-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="eb082-279">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="eb082-279">Sent and received email report</span></span>

<span data-ttu-id="eb082-280">**已发送和已接收的电子邮件**报告是一个智能报告，显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为 "正常" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb082-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="eb082-281">此报告和[邮件流状态报告](#mailflow-status-report)的区别在于：此报告不包含有关边缘保护阻止的邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="eb082-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="eb082-282">报告的聚合视图和详细信息视图允许90天的筛选。</span><span class="sxs-lookup"><span data-stu-id="eb082-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="eb082-283">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**已发送和已接收电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="eb082-284">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

!["报告" 仪表板中的发送和接收电子邮件小部件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="eb082-286">已发送和已接收电子邮件报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="eb082-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="eb082-287">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="eb082-288">**分解方式：类型**：图表显示所有可用类别：</span><span class="sxs-lookup"><span data-stu-id="eb082-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="eb082-289">**Total**</span><span class="sxs-lookup"><span data-stu-id="eb082-289">**Total**</span></span>
  - <span data-ttu-id="eb082-290">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="eb082-290">**Good mail**</span></span>
  - <span data-ttu-id="eb082-291">**恶意软件（反恶意软件）** （EOP）</span><span class="sxs-lookup"><span data-stu-id="eb082-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="eb082-292">**垃圾邮件检测**</span><span class="sxs-lookup"><span data-stu-id="eb082-292">**Spam detections**</span></span>
  - <span data-ttu-id="eb082-293">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="eb082-293">**Rule messages**</span></span>
  - <span data-ttu-id="eb082-294">**高级恶意软件**（OFFICE 365 ATP）</span><span class="sxs-lookup"><span data-stu-id="eb082-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="eb082-295">当您将鼠标指针悬停在图表中的某一天（数据点）上时，您可以查看那天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb082-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![发送和接收的电子邮件报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="eb082-297">**分解方式：方向**：图表显示**总计**、**入站**和**出站**数据。</span><span class="sxs-lookup"><span data-stu-id="eb082-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="eb082-298">当您将鼠标指针悬停在图表中的某一天（数据点）上时，您可以查看那天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb082-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![已发送和已接收电子邮件报告中的方向视图](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="eb082-300">**向下** \> 钻取**恶意软件（反恶意软件）**：此选择会将您带到[电子邮件报告中的恶意软件检测](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="eb082-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="eb082-301">**向下** \> 钻取**垃圾邮件检测）**：此选择会将您带到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="eb082-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="eb082-302">如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="eb082-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="eb082-303">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="eb082-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb082-304">方向值</span><span class="sxs-lookup"><span data-stu-id="eb082-304">Direction values</span></span>
- <span data-ttu-id="eb082-305">类型值</span><span class="sxs-lookup"><span data-stu-id="eb082-305">Type values</span></span>

<span data-ttu-id="eb082-306">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="eb082-307">已发送和已接收电子邮件报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="eb082-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="eb082-308">如果在 "分解方式" 中单击 "**查看详细信息表** **：方向**" 或 "**分解方式"： "方向**" 视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="eb082-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="eb082-309">**Date （UTC）**</span><span class="sxs-lookup"><span data-stu-id="eb082-309">**Date (UTC)**</span></span>
- <span data-ttu-id="eb082-310">**类型**</span><span class="sxs-lookup"><span data-stu-id="eb082-310">**Type**</span></span>
- <span data-ttu-id="eb082-311">**方向**</span><span class="sxs-lookup"><span data-stu-id="eb082-311">**Direction**</span></span>
- <span data-ttu-id="eb082-312">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="eb082-312">**Message count**</span></span>

<span data-ttu-id="eb082-313">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="eb082-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="eb082-314">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="eb082-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb082-315">方向值</span><span class="sxs-lookup"><span data-stu-id="eb082-315">Direction values</span></span>
- <span data-ttu-id="eb082-316">类型值</span><span class="sxs-lookup"><span data-stu-id="eb082-316">Type values</span></span>

<span data-ttu-id="eb082-317">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="eb082-318">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="eb082-318">Top senders and recipients report</span></span>

<span data-ttu-id="eb082-319">**最上面的发件人和收件人**报告是显示主要电子邮件发件人和收件人的饼形图。</span><span class="sxs-lookup"><span data-stu-id="eb082-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="eb082-320">若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**主要发件人和收件人**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="eb082-321">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="eb082-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

!["报告" 仪表板中的 "主要发件人和收件人" 小部件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="eb082-323">主要发件人和收件人报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="eb082-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="eb082-324">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="eb082-325">**显示 \> 主要邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="eb082-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="eb082-326">**显示 \> 主要邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="eb082-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="eb082-327">**显示 \> 排名靠前的垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="eb082-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="eb082-328">**显示数据 \>主要恶意软件收件人**（EOP）</span><span class="sxs-lookup"><span data-stu-id="eb082-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="eb082-329">**显示数据 \>主要恶意软件收件人（ATP）** （Office 365 ATP）</span><span class="sxs-lookup"><span data-stu-id="eb082-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="eb082-330">饼图的复合根据这些选择的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="eb082-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="eb082-331">当您将鼠标指针悬停在饼图中时，您可以看到发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="eb082-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="eb082-332">如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="eb082-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

!["热门发件人和收件人" 报告中报告视图中的饼形图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="eb082-334">主要发件人和收件人报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="eb082-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="eb082-335">如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="eb082-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="eb082-336">**显示 \> 主要邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="eb082-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="eb082-337">**主要邮件发件人**</span><span class="sxs-lookup"><span data-stu-id="eb082-337">**Top mail senders**</span></span>
  - <span data-ttu-id="eb082-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="eb082-338">**Count**</span></span>

- <span data-ttu-id="eb082-339">**显示 \> 主要邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="eb082-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="eb082-340">**主要邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="eb082-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="eb082-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="eb082-341">**Count**</span></span>

- <span data-ttu-id="eb082-342">**显示 \> 排名靠前的垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="eb082-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="eb082-343">**主要垃圾邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="eb082-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="eb082-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="eb082-344">**Count**</span></span>

- <span data-ttu-id="eb082-345">**显示数据 \>主要恶意软件收件人**（EOP）</span><span class="sxs-lookup"><span data-stu-id="eb082-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="eb082-346">**主要恶意软件收件人**</span><span class="sxs-lookup"><span data-stu-id="eb082-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="eb082-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="eb082-347">**Count**</span></span>

- <span data-ttu-id="eb082-348">**显示数据 \>主要恶意软件收件人（ATP）** （Office 365 ATP）</span><span class="sxs-lookup"><span data-stu-id="eb082-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="eb082-349">**主要恶意软件收件人（ATP）**</span><span class="sxs-lookup"><span data-stu-id="eb082-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="eb082-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="eb082-350">**Count**</span></span>

<span data-ttu-id="eb082-351">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="eb082-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="eb082-352">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="eb082-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="eb082-353">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="eb082-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="eb082-354">若要查看和使用报告，您必须是安全 & 合规性中心**和**Exchange Online 中指定角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="eb082-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="eb082-355">在安全 & 合规性中心中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="eb082-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="eb082-356">-组织管理</span><span class="sxs-lookup"><span data-stu-id="eb082-356">-Organization Management</span></span>

  <span data-ttu-id="eb082-357">-安全管理员（也可以在[Azure Active Directory 管理中心](https://aad.portal.azure.com)中执行此操作-安全读取器</span><span class="sxs-lookup"><span data-stu-id="eb082-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="eb082-358">有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="eb082-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="eb082-359">在 Exchange Online 中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="eb082-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="eb082-360">-组织管理</span><span class="sxs-lookup"><span data-stu-id="eb082-360">-Organization Management</span></span>

  <span data-ttu-id="eb082-361">-仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="eb082-361">-View-only Organization Management</span></span>

  <span data-ttu-id="eb082-362">-仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="eb082-362">-View-Only Recipients</span></span>

  <span data-ttu-id="eb082-363">合规性管理</span><span class="sxs-lookup"><span data-stu-id="eb082-363">-Compliance Management</span></span>

<span data-ttu-id="eb082-364">有关详细信息，请参阅[Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)中的权限和[管理 exchange online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="eb082-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb082-365">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb082-365">Related topics</span></span>

[<span data-ttu-id="eb082-366">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="eb082-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="eb082-367">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="eb082-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
