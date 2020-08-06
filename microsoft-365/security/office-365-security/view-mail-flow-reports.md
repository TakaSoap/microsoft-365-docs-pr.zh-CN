---
title: 查看 "报告" 仪表板中的邮件流报告
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
description: 管理员可以了解安全 & 合规性中心的 "报告" 仪表板中提供的邮件流报告。
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578014"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="fcaf8-103">在安全 & 合规中心中查看 "报告" 仪表板中的邮件流报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="fcaf8-104">除了安全性 & 合规性中心中的[邮件流仪表板](mail-flow-insights-v2.md)中提供的邮件流报告之外，"报告" 仪表板中还提供了多种其他邮件流报告，可帮助您监视 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="fcaf8-105">如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 "**报告**" 仪表板，在[安全 & 合规中心](https://office.protection.com)中查看这些报告 \> **Dashboard**。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="fcaf8-106">若要直接转到 "报表" 仪表板，请打开 <https://office.protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="fcaf8-108">连接器报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-108">Connector report</span></span>

<span data-ttu-id="fcaf8-109">**连接器报告**显示为您的组织配置的[入站和出站连接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的 "邮件流" 活动。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="fcaf8-110">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**连接器报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="fcaf8-111">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

!["报告" 仪表板中的连接器报告小部件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="fcaf8-113">连接器报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-113">Report view for the Connector report</span></span>

<span data-ttu-id="fcaf8-114">以下图表在报表视图中可用：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="fcaf8-115">**数据查看依据：邮件流**：此图显示按以下方式组织的入站和出站邮件的数量：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="fcaf8-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-116">**Total**</span></span>
  - <span data-ttu-id="fcaf8-117">**从不带连接器的 internet**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="fcaf8-118">**不带连接器的 internet 连接**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="fcaf8-119">您已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="fcaf8-120">若要隔离图表中的数据，请使用 "**显示数据以供**控制" 选择其中一个选项或**所有邮件流**。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![通过邮件流查看连接器报告中的数据](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="fcaf8-122">**查看数据的依据： TLS 用法**：此图显示了邮件流的传输层安全性 (TLS) 版本使用情况的百分比。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="fcaf8-123">若要隔离图表中的数据，请使用 "**显示数据以供**控制" 选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="fcaf8-124">**所有邮件流**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-124">**All mail flow**</span></span>
  - <span data-ttu-id="fcaf8-125">**从不带连接器的 internet**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="fcaf8-126">**不带连接器的 internet 连接**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="fcaf8-127">您已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-127">A specific connector that you've configured.</span></span>

  ![通过 TLS 使用在连接器报告中查看数据](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="fcaf8-129">如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="fcaf8-130">连接器报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-130">Details table view for the Connector report</span></span>

<span data-ttu-id="fcaf8-131">如果您在报告视图中单击 "**查看详细信息表**"，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fcaf8-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-132">**Date**</span></span>
- <span data-ttu-id="fcaf8-133">**连接器方向和名称**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-133">**Connector direction and name**</span></span>
- <span data-ttu-id="fcaf8-134">**连接器类型**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-134">**Connector type**</span></span>
- <span data-ttu-id="fcaf8-135">**强制 TLS？**：值**True**或**False**。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="fcaf8-136">**没有 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="fcaf8-137">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="fcaf8-138">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="fcaf8-139">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="fcaf8-140">**Volume**：邮件数。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="fcaf8-141">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fcaf8-142">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="fcaf8-143">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-143">Exchange transport rule report</span></span>

<span data-ttu-id="fcaf8-144">**Exchange 传输规则报告**显示邮件流规则的效果 (也称为传输规则) 组织中的传入和传出邮件。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="fcaf8-145">若要查看报告，请打开[安全 & 合规中心](https://protection.office.com)，转到 "**报告** \> **仪表板**"，然后选择 " **Exchange 传输规则**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="fcaf8-146">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

!["报告" 仪表板中的 Exchange 传输规则小部件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="fcaf8-148">Exchange 传输规则报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="fcaf8-149">以下图表在报表视图中可用：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="fcaf8-150">**数据查看依据： Exchange 传输规则** \>**分解方式：方向**：此图显示受传输规则影响的**入站**和**出站**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="fcaf8-151">**数据查看依据： Exchange 传输规则** \>**分解方式：严重性**：此图显示**高严重性**和**中低严重性**以及**低严重性**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="fcaf8-152">将严重性级别设置为规则中的操作 (使用严重级别或_SetAuditSeverity_) **审核此规则**。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="fcaf8-153">有关详细信息，请参阅[Exchange Online 中的邮件流规则操作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="fcaf8-154">**数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此图显示受数据丢失防护 (DLP) 传输规则影响的**入站**和**出站**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="fcaf8-155">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="fcaf8-156">**显示以下项的数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="fcaf8-157">**显示以下项的数据：已损坏的用户**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="fcaf8-158">**显示以下项的数据：检测到的内容量过低美国爱国法案**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="fcaf8-159">**数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此视图显示**高严重性**和**中严重性**的数目以及受 DLP 传输规则影响的**低严重性**邮件。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="fcaf8-160">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="fcaf8-161">**显示以下项的数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="fcaf8-162">**显示以下项的数据：已损坏的用户**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="fcaf8-163">**显示以下项的数据：检测到的内容量过低美国爱国法案**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="fcaf8-164">如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="fcaf8-165">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="fcaf8-166">方向值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-166">Direction values</span></span>
- <span data-ttu-id="fcaf8-167">严重度值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-167">Severity values</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="fcaf8-169">Exchange 传输规则报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="fcaf8-170">如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fcaf8-171">**数据查看依据： Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="fcaf8-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-172">**Date**</span></span>
  - <span data-ttu-id="fcaf8-173">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-173">**Transport rule**</span></span>
  - <span data-ttu-id="fcaf8-174">**主题**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-174">**Subject**</span></span>
  - <span data-ttu-id="fcaf8-175">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-175">**Sender address**</span></span>
  - <span data-ttu-id="fcaf8-176">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-176">**Recipient address**</span></span>
  - <span data-ttu-id="fcaf8-177">**严重性**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-177">**Severity**</span></span>
  - <span data-ttu-id="fcaf8-178">**方向**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-178">**Direction**</span></span>

- <span data-ttu-id="fcaf8-179">**数据查看依据： DLP Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="fcaf8-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-180">**Date**</span></span>
  - <span data-ttu-id="fcaf8-181">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-181">**DLP policy**</span></span>
  - <span data-ttu-id="fcaf8-182">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-182">**Transport rule**</span></span>
  - <span data-ttu-id="fcaf8-183">**主题**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-183">**Subject**</span></span>
  - <span data-ttu-id="fcaf8-184">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-184">**Sender address**</span></span>
  - <span data-ttu-id="fcaf8-185">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-185">**Recipient address**</span></span>
  - <span data-ttu-id="fcaf8-186">**严重性**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-186">**Severity**</span></span>
  - <span data-ttu-id="fcaf8-187">**方向**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-187">**Direction**</span></span>

<span data-ttu-id="fcaf8-188">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fcaf8-189">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="fcaf8-190">方向值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-190">Direction values</span></span>
- <span data-ttu-id="fcaf8-191">严重度值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-191">Severity values</span></span>

<span data-ttu-id="fcaf8-192">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="fcaf8-193">转发报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-193">Forwarding report</span></span>

<span data-ttu-id="fcaf8-194">**转发报告**将组织的自动转发的邮件显示为 Exchange Online 邮箱中的外部域。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="fcaf8-195">转发的邮件可能会带来安全或合规性风险，并可能指示已损坏的帐户。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="fcaf8-196">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**转发报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="fcaf8-197">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

!["报告" 仪表板中的转发报告构件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="fcaf8-199">转发报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="fcaf8-200">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fcaf8-201">显示以下各项**的数据：转发方法**：显示以下方法：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="fcaf8-202">**传输规则**：也称为[邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="fcaf8-203">**邮箱规则**：也称为[收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="fcaf8-205">**显示数据：转发域**：此视图显示作为转发目标的收件人域。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="fcaf8-207">**显示以下项的数据：转发器**：显示以下转发器：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="fcaf8-208">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-208">**Transport rule**</span></span>
  - <span data-ttu-id="fcaf8-209">包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![转发报告中的转发器视图](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="fcaf8-211">如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="fcaf8-212">转发报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="fcaf8-213">如果您在报告视图中单击 "**查看详细信息表**"，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fcaf8-214">**转发器**：值**传输规则**或包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="fcaf8-215">**转发类型**：值**邮箱规则**或**传输规则**。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="fcaf8-216">**收件人名称**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-216">**Recipient name**</span></span>
- <span data-ttu-id="fcaf8-217">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-217">**Recipient domain**</span></span>
- <span data-ttu-id="fcaf8-218">**详细信息**：这是邮件流规则的 GUID 值，或收件箱规则的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="fcaf8-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-219">**Count**</span></span>
- <span data-ttu-id="fcaf8-220">**第一次转发日期**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-220">**First forward date**</span></span>

<span data-ttu-id="fcaf8-221">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fcaf8-222">若要返回到 "报告" 视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="fcaf8-223">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-223">Mailflow status report</span></span>

<span data-ttu-id="fcaf8-224">**邮件流状态报告**类似于[发送和接收的电子邮件报告](#sent-and-received-email-report)，其中包含有关在边缘上允许或阻止的电子邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="fcaf8-225">这是唯一包含 edge 保护信息的报告，仅显示在允许 Exchange Online Protection (EOP) 进行评估之前阻止的电子邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="fcaf8-226">若要查看报表，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**邮件流状态报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="fcaf8-227">若要直接转到 "**邮件流状态" 报告**，请打开 <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

!["报告" 仪表板中的邮件流状态报告小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="fcaf8-229">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="fcaf8-230">打开报表时，"**类型**" 选项卡在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="fcaf8-231">默认情况下，此视图包含一个使用以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="fcaf8-232">**日期**：最近7天。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="fcaf8-233">**方向**：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-233">**Direction**:</span></span>

  - <span data-ttu-id="fcaf8-234">**进货**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-234">**Inbound**</span></span>
  - <span data-ttu-id="fcaf8-235">**出站**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-235">**Outbound**</span></span>
  - <span data-ttu-id="fcaf8-236">**组织内** (独立于**入站**和**出站**) 计数</span><span class="sxs-lookup"><span data-stu-id="fcaf8-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="fcaf8-237">**类型**：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-237">**Type**:</span></span>

  - <span data-ttu-id="fcaf8-238">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-238">**Good mail**</span></span>
  - <span data-ttu-id="fcaf8-239">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-239">**Malware**</span></span>
  - <span data-ttu-id="fcaf8-240">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-240">**Spam**</span></span>
  - <span data-ttu-id="fcaf8-241">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-241">**Edge protection**</span></span>
  - <span data-ttu-id="fcaf8-242">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-242">**Rule messages**</span></span>
  - <span data-ttu-id="fcaf8-243">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-243">**Phishing email**</span></span>

<span data-ttu-id="fcaf8-244">图表按**类型**值进行组织。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="fcaf8-245">您可以通过单击 "**筛选器**" 或单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="fcaf8-246">数据表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-246">The data table contains the following information:</span></span>

- <span data-ttu-id="fcaf8-247">**方向**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-247">**Direction**</span></span>
- <span data-ttu-id="fcaf8-248">**类型**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-248">**Type**</span></span>
- <span data-ttu-id="fcaf8-249">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-249">**24 hours**</span></span>
- <span data-ttu-id="fcaf8-250">**3 天**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-250">**3 days**</span></span>
- <span data-ttu-id="fcaf8-251">**7 天**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-251">**7 days**</span></span>
- <span data-ttu-id="fcaf8-252">**15 天**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-252">**15 days**</span></span>
- <span data-ttu-id="fcaf8-253">**30 天**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-253">**30 days**</span></span>

<span data-ttu-id="fcaf8-254">如果单击 "**选择类别" 以了解更多详细信息**，则可以从以下值中进行选择：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="fcaf8-255">**网络钓鱼电子邮件**：此选择会将您带到[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="fcaf8-256">**电子邮件中的恶意软件**：此选择会将您带到[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="fcaf8-257">**垃圾邮件检测**：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="fcaf8-258">**边缘阻止的垃圾邮件**：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="fcaf8-259">**导出**：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-259">**Export**:</span></span>

<span data-ttu-id="fcaf8-260">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="fcaf8-261">因此，如果要将数据导出7天，则需要执行7个不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="fcaf8-262">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fcaf8-263">如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="fcaf8-264">邮件流状态报告中的类型视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="fcaf8-265">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="fcaf8-266">如果单击 "**方向**" 选项卡，则将使用 "**类型**" 视图中的相同默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="fcaf8-267">图表按**方向**值组织。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="fcaf8-268">您可以通过单击 "**筛选器**" 或通过单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="fcaf8-269">将使用 "**类型**" 视图中的相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="fcaf8-270">数据表包含**类型**视图中的相同信息。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="fcaf8-271">**选择类别以获取更多详细信息**可用的选择和行为与 "**类型**" 视图相同。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="fcaf8-272">**导出**：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-272">**Export**:</span></span>

<span data-ttu-id="fcaf8-273">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="fcaf8-274">因此，如果要将数据导出7天，则需要执行7个不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="fcaf8-275">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fcaf8-276">如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="fcaf8-277">邮件流状态报告中的 "方向" 视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="fcaf8-278">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-278">Sent and received email report</span></span>

<span data-ttu-id="fcaf8-279">**已发送和已接收的电子邮件**报告是一个智能报告，显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为 "正常" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="fcaf8-280">此报告和[邮件流状态报告](#mailflow-status-report)的区别在于：此报告不包含有关边缘保护阻止的邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="fcaf8-281">报告的聚合视图和详细信息视图允许90天的筛选。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="fcaf8-282">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 "**已发送和已接收电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="fcaf8-283">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

!["报告" 仪表板中的发送和接收电子邮件小部件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="fcaf8-285">已发送和已接收电子邮件报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="fcaf8-286">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fcaf8-287">**分解方式：类型**：图表显示所有可用类别：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="fcaf8-288">**Total**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-288">**Total**</span></span>
  - <span data-ttu-id="fcaf8-289">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-289">**Good mail**</span></span>
  - <span data-ttu-id="fcaf8-290">\*\*恶意软件 (反恶意软件) \*\* (EOP) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="fcaf8-291">**垃圾邮件检测**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-291">**Spam detections**</span></span>
  - <span data-ttu-id="fcaf8-292">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-292">**Rule messages**</span></span>
  - <span data-ttu-id="fcaf8-293"> (Office 365 ATP) 的**高级恶意软件**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="fcaf8-294">当鼠标悬停在图表中某天 (数据点) 时，可以查看那天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![发送和接收的电子邮件报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="fcaf8-296">**分解方式：方向**：图表显示**总计**、**入站**和**出站**数据。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="fcaf8-297">当鼠标悬停在图表中某天 (数据点) 时，可以查看那天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![已发送和已接收电子邮件报告中的方向视图](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="fcaf8-299">**向下** \> 钻取\*\*恶意软件 (反恶意软件) \*\*：此选择会将您带到[电子邮件报告中的恶意软件检测](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="fcaf8-300">**向下** \> 钻取\*\*垃圾邮件检测) \*\*：选择此选项将转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="fcaf8-301">如果您在报告视图中单击 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fcaf8-302">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="fcaf8-303">方向值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-303">Direction values</span></span>
- <span data-ttu-id="fcaf8-304">类型值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-304">Type values</span></span>

<span data-ttu-id="fcaf8-305">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="fcaf8-306">已发送和已接收电子邮件报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="fcaf8-307">如果在 "分解方式" 中单击 "**查看详细信息表** **：方向**" 或 "**分解方式"： "方向**" 视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="fcaf8-308">\*\*日期 (UTC) \*\*</span><span class="sxs-lookup"><span data-stu-id="fcaf8-308">**Date (UTC)**</span></span>
- <span data-ttu-id="fcaf8-309">**类型**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-309">**Type**</span></span>
- <span data-ttu-id="fcaf8-310">**方向**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-310">**Direction**</span></span>
- <span data-ttu-id="fcaf8-311">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-311">**Message count**</span></span>

<span data-ttu-id="fcaf8-312">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fcaf8-313">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="fcaf8-314">方向值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-314">Direction values</span></span>
- <span data-ttu-id="fcaf8-315">类型值</span><span class="sxs-lookup"><span data-stu-id="fcaf8-315">Type values</span></span>

<span data-ttu-id="fcaf8-316">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="fcaf8-317">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-317">Top senders and recipients report</span></span>

<span data-ttu-id="fcaf8-318">**最上面的发件人和收件人**报告是显示主要电子邮件发件人和收件人的饼形图。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="fcaf8-319">若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 "**主要发件人和收件人**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="fcaf8-320">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

!["报告" 仪表板中的 "主要发件人和收件人" 小部件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="fcaf8-322">主要发件人和收件人报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="fcaf8-323">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fcaf8-324">**显示 \> 主要邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="fcaf8-325">**显示 \> 主要邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="fcaf8-326">**显示 \> 排名靠前的垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="fcaf8-327">**显示数据 \>主要的恶意软件收件人** (EOP) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="fcaf8-328">\*\*显示数据 \>主要的恶意软件收件人 (ATP) \*\* (Office 365 ATP) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="fcaf8-329">饼图的复合根据这些选择的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="fcaf8-330">当您将鼠标指针悬停在饼图中时，您可以看到发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="fcaf8-331">如果您在报告视图中单击 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

!["热门发件人和收件人" 报告中报告视图中的饼形图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="fcaf8-333">主要发件人和收件人报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="fcaf8-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="fcaf8-334">如果您单击 "**查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fcaf8-335">**显示 \> 主要邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="fcaf8-336">**主要邮件发件人**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-336">**Top mail senders**</span></span>
  - <span data-ttu-id="fcaf8-337">**Count**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-337">**Count**</span></span>

- <span data-ttu-id="fcaf8-338">**显示 \> 主要邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="fcaf8-339">**主要邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="fcaf8-340">**Count**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-340">**Count**</span></span>

- <span data-ttu-id="fcaf8-341">**显示 \> 排名靠前的垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="fcaf8-342">**主要垃圾邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="fcaf8-343">**Count**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-343">**Count**</span></span>

- <span data-ttu-id="fcaf8-344">**显示数据 \>主要的恶意软件收件人** (EOP) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="fcaf8-345">**主要恶意软件收件人**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="fcaf8-346">**Count**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-346">**Count**</span></span>

- <span data-ttu-id="fcaf8-347">\*\*显示数据 \>主要的恶意软件收件人 (ATP) \*\* (Office 365 ATP) </span><span class="sxs-lookup"><span data-stu-id="fcaf8-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="fcaf8-348">\*\* (ATP) 的主要恶意软件收件人\*\*</span><span class="sxs-lookup"><span data-stu-id="fcaf8-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="fcaf8-349">**Count**</span><span class="sxs-lookup"><span data-stu-id="fcaf8-349">**Count**</span></span>

<span data-ttu-id="fcaf8-350">如果单击 "详细信息" 表视图中的 "**筛选器**"，则可以指定具有 "**开始日期**" 和 "**结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fcaf8-351">若要返回到报告视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="fcaf8-352">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="fcaf8-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="fcaf8-353">若要查看和使用报告，您必须是安全 & 合规性中心**和**Exchange Online 中指定角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="fcaf8-354">在安全 & 合规性中心中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="fcaf8-355">-组织管理-安全管理员 (你也可以在[Azure Active Directory 管理中心](https://aad.portal.azure.com)中执行此操作-安全读者</span><span class="sxs-lookup"><span data-stu-id="fcaf8-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="fcaf8-356">有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="fcaf8-357">在 Exchange Online 中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="fcaf8-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="fcaf8-358">-组织管理-仅查看组织管理-仅查看收件人-合规性管理</span><span class="sxs-lookup"><span data-stu-id="fcaf8-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="fcaf8-359">有关详细信息，请参阅[Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)中的权限和[管理 exchange online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="fcaf8-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fcaf8-360">相关主题</span><span class="sxs-lookup"><span data-stu-id="fcaf8-360">Related topics</span></span>

[<span data-ttu-id="fcaf8-361">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="fcaf8-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="fcaf8-362">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="fcaf8-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="fcaf8-363">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="fcaf8-364">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="fcaf8-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
