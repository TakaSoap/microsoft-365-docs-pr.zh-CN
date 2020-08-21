---
title: 在"报告"仪表板中查看邮件流报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解安全与合规中心的"报告"仪表板中的&报告。
ms.custom: ''
ms.openlocfilehash: 9e9249eab5d3519dac0e33acf40d600d471b7cb2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826453"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="521d5-103">在安全与合规中心的"报告"仪表板中 &查看邮件流报告</span><span class="sxs-lookup"><span data-stu-id="521d5-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="521d5-104">除了安全&合规中心的 [邮件流仪表板中可用的](mail-flow-insights-v2.md) 邮件流报告，"报告"仪表板中还提供了各种其他邮件流报告，可以帮助监视 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="521d5-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="521d5-105">如果你具有必要[的权限，](#what-permissions-are-needed-to-view-these-reports)可通过转到"报表仪表板["在安全&合规性](https://office.protection.com)中心查看**Reports** \> **这些报告**。</span><span class="sxs-lookup"><span data-stu-id="521d5-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="521d5-106">若要直接转到"报表"仪表板，请打开 <https://office.protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![安全与合规中心中的&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="521d5-108">连接器报告</span><span class="sxs-lookup"><span data-stu-id="521d5-108">Connector report</span></span>

<span data-ttu-id="521d5-109">连接器 **报告** 显示在为组织配置的 [入站和出站](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 连接器上的邮件流活动。</span><span class="sxs-lookup"><span data-stu-id="521d5-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="521d5-110">若要查看报告，请打开安全 [&合规中心，](https://protection.office.com)转到" **报告** \> **仪表板"，** 然后选择" **连接器"报告**。</span><span class="sxs-lookup"><span data-stu-id="521d5-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="521d5-111">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![报表仪表板中的连接器报告小部件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="521d5-113">连接器报告的报表视图</span><span class="sxs-lookup"><span data-stu-id="521d5-113">Report view for the Connector report</span></span>

<span data-ttu-id="521d5-114">下面的图表分为报表视图：</span><span class="sxs-lookup"><span data-stu-id="521d5-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="521d5-115">**查看数据：邮件流：** 此图显示按以下条件组织的入站和出站邮件的数量：</span><span class="sxs-lookup"><span data-stu-id="521d5-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="521d5-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="521d5-116">**Total**</span></span>
  - <span data-ttu-id="521d5-117">**在不带连接器的情况下通过 Internet**</span><span class="sxs-lookup"><span data-stu-id="521d5-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="521d5-118">**在没有连接器的情况下连接到 Internet**</span><span class="sxs-lookup"><span data-stu-id="521d5-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="521d5-119">你配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="521d5-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="521d5-120">若要隔离图表中的数据，请使用"显示控制**数据**"选择这些选项之一或"全部**邮件流"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在连接器报告中按邮件流查看数据](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="521d5-122">**查看数据：TLS 使用**情况：此图显示邮件流的传输层安全性 (TLS) 的百分比。</span><span class="sxs-lookup"><span data-stu-id="521d5-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="521d5-123">若要隔离图表中的数据，请使用控件的"显示 **数据"** 以选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="521d5-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="521d5-124">**所有邮件流**</span><span class="sxs-lookup"><span data-stu-id="521d5-124">**All mail flow**</span></span>
  - <span data-ttu-id="521d5-125">**在不带连接器的情况下通过 Internet**</span><span class="sxs-lookup"><span data-stu-id="521d5-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="521d5-126">**在没有连接器的情况下连接到 Internet**</span><span class="sxs-lookup"><span data-stu-id="521d5-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="521d5-127">你配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="521d5-127">A specific connector that you've configured.</span></span>

  ![在连接器报告中按 TLS 使用情况查看数据](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="521d5-129">如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="521d5-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="521d5-130">连接器报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="521d5-130">Details table view for the Connector report</span></span>

<span data-ttu-id="521d5-131">如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="521d5-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="521d5-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="521d5-132">**Date**</span></span>
- <span data-ttu-id="521d5-133">**连接器方向和名称**</span><span class="sxs-lookup"><span data-stu-id="521d5-133">**Connector direction and name**</span></span>
- <span data-ttu-id="521d5-134">**连接器类型**</span><span class="sxs-lookup"><span data-stu-id="521d5-134">**Connector type**</span></span>
- <span data-ttu-id="521d5-135">**是否被启用 TLS？：** 值 **True** 或 **False**。</span><span class="sxs-lookup"><span data-stu-id="521d5-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="521d5-136">**无 TLS** 百 (百) </span><span class="sxs-lookup"><span data-stu-id="521d5-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="521d5-137">**TLS 1.0 百** (百) </span><span class="sxs-lookup"><span data-stu-id="521d5-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="521d5-138">**TLS 1.1 百** () </span><span class="sxs-lookup"><span data-stu-id="521d5-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="521d5-139">**TLS 1.2** (百) </span><span class="sxs-lookup"><span data-stu-id="521d5-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="521d5-140">**Volume：** 邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="521d5-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="521d5-141">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="521d5-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="521d5-142">要返回到下一报表视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="521d5-143">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="521d5-143">Exchange transport rule report</span></span>

<span data-ttu-id="521d5-144">**Exchange 传输规则报告显示**邮件流规则类型 (也称为组织中接收和传) 出邮件的传输规则的影响。</span><span class="sxs-lookup"><span data-stu-id="521d5-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="521d5-145">若要查看报告，请打开[安全&合规中心](https://protection.office.com)，转到 **"报告** \> **仪表板"，** 然后选择 **"Exchange 传输规则"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="521d5-146">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![报告仪表板中的 Exchange 传输规则小部件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="521d5-148">Exchange 传输规则报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="521d5-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="521d5-149">下面的图表分为报表视图：</span><span class="sxs-lookup"><span data-stu-id="521d5-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="521d5-150">**查看数据：Exchange 传输规则** \>**按方向分解**：方向：此图显示**受传输规则**影响的**入站**和出站邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="521d5-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="521d5-151">**查看数据：Exchange 传输规则** \>**细节信息：严重性**：此图显示**高严重性**和**中等严重性**、低**严重性邮件的**数量。</span><span class="sxs-lookup"><span data-stu-id="521d5-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="521d5-152">在规则中将严重级别设置为操作， (**使用以下严重性级别或** _SetAuditSeverity_) 。</span><span class="sxs-lookup"><span data-stu-id="521d5-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="521d5-153">有关详细信息，请参阅 [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="521d5-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="521d5-154">**查看数据：DLP Exchange 传输规则** \>**按方向分解：方向**：该图显示了**受数据**丢失防护**Outbound**或 DLP 保护策略影响的入) 站和出站邮件 (数量。</span><span class="sxs-lookup"><span data-stu-id="521d5-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="521d5-155">通过选择以下选项，可以进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="521d5-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="521d5-156">**显示数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="521d5-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="521d5-157">**显示数据：被已被阻止的用户**</span><span class="sxs-lookup"><span data-stu-id="521d5-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="521d5-158">**显示数据：检测到美国纹理法的低内容量**</span><span class="sxs-lookup"><span data-stu-id="521d5-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="521d5-159">**查看数据：DLP Exchange 传输规则** \>**"按方向：方向**：方向：此视图显示受 DLP**传输规则**影响的高严重性和**Low severity**中等严重性邮件数"和"低严重性"邮件数。 **Medium severity**</span><span class="sxs-lookup"><span data-stu-id="521d5-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="521d5-160">通过选择以下选项，可以进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="521d5-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="521d5-161">**显示数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="521d5-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="521d5-162">**显示数据：被已被阻止的用户**</span><span class="sxs-lookup"><span data-stu-id="521d5-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="521d5-163">**显示数据：检测到美国纹理法的低内容量**</span><span class="sxs-lookup"><span data-stu-id="521d5-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="521d5-164">如果单击 **筛选器** 报表视图，则可以通过以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="521d5-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="521d5-165">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="521d5-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="521d5-166">方向值</span><span class="sxs-lookup"><span data-stu-id="521d5-166">Direction values</span></span>
- <span data-ttu-id="521d5-167">严重性值</span><span class="sxs-lookup"><span data-stu-id="521d5-167">Severity values</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="521d5-169">Exchange 传输规则报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="521d5-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="521d5-170">如果您单击 **"查看详细信息**表"，显示的信息取决于正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="521d5-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="521d5-171">**查看数据：Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="521d5-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="521d5-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="521d5-172">**Date**</span></span>
  - <span data-ttu-id="521d5-173">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="521d5-173">**Transport rule**</span></span>
  - <span data-ttu-id="521d5-174">**主题**</span><span class="sxs-lookup"><span data-stu-id="521d5-174">**Subject**</span></span>
  - <span data-ttu-id="521d5-175">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="521d5-175">**Sender address**</span></span>
  - <span data-ttu-id="521d5-176">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="521d5-176">**Recipient address**</span></span>
  - <span data-ttu-id="521d5-177">**严重性**</span><span class="sxs-lookup"><span data-stu-id="521d5-177">**Severity**</span></span>
  - <span data-ttu-id="521d5-178">**方向**</span><span class="sxs-lookup"><span data-stu-id="521d5-178">**Direction**</span></span>

- <span data-ttu-id="521d5-179">**查看数据：DLP Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="521d5-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="521d5-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="521d5-180">**Date**</span></span>
  - <span data-ttu-id="521d5-181">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="521d5-181">**DLP policy**</span></span>
  - <span data-ttu-id="521d5-182">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="521d5-182">**Transport rule**</span></span>
  - <span data-ttu-id="521d5-183">**主题**</span><span class="sxs-lookup"><span data-stu-id="521d5-183">**Subject**</span></span>
  - <span data-ttu-id="521d5-184">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="521d5-184">**Sender address**</span></span>
  - <span data-ttu-id="521d5-185">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="521d5-185">**Recipient address**</span></span>
  - <span data-ttu-id="521d5-186">**严重性**</span><span class="sxs-lookup"><span data-stu-id="521d5-186">**Severity**</span></span>
  - <span data-ttu-id="521d5-187">**方向**</span><span class="sxs-lookup"><span data-stu-id="521d5-187">**Direction**</span></span>

<span data-ttu-id="521d5-188">如果单击 **详细信息表** 视图中的"筛选器"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="521d5-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="521d5-189">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="521d5-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="521d5-190">方向值</span><span class="sxs-lookup"><span data-stu-id="521d5-190">Direction values</span></span>
- <span data-ttu-id="521d5-191">严重性值</span><span class="sxs-lookup"><span data-stu-id="521d5-191">Severity values</span></span>

<span data-ttu-id="521d5-192">要返回到下一报表视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="521d5-193">转发报告</span><span class="sxs-lookup"><span data-stu-id="521d5-193">Forwarding report</span></span>

<span data-ttu-id="521d5-194">转 **发报告** 显示您的组织从 Exchange Online 邮箱自动将邮件转发到外部域。</span><span class="sxs-lookup"><span data-stu-id="521d5-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="521d5-195">转发的邮件可能带来安全或合规性风险，并且可能指示帐户被已被了威胁。</span><span class="sxs-lookup"><span data-stu-id="521d5-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="521d5-196">若要查看报告，请打开安全[&合规中心](https://protection.office.com)，转到"**报告** \> **仪表板"，** 然后选择"**转发报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="521d5-197">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![报表仪表板中的转发报表小部件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="521d5-199">转发报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="521d5-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="521d5-200">下面的图表提供了报表视图：</span><span class="sxs-lookup"><span data-stu-id="521d5-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="521d5-201">**显示数据：转发方法**：以下方法分为如下：</span><span class="sxs-lookup"><span data-stu-id="521d5-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="521d5-202">**传输规则：** 也称为 [邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="521d5-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="521d5-203">**邮箱规则**：也称为收 [件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="521d5-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="521d5-205">**显示数据：转发域**：此视图显示作为转发目标的收件人域。</span><span class="sxs-lookup"><span data-stu-id="521d5-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="521d5-207">**显示数据：转发器**：以下转发器显示：</span><span class="sxs-lookup"><span data-stu-id="521d5-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="521d5-208">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="521d5-208">**Transport rule**</span></span>
  - <span data-ttu-id="521d5-209">包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="521d5-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![转发报告中的转发者视图](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="521d5-211">如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="521d5-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="521d5-212">转发报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="521d5-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="521d5-213">如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="521d5-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="521d5-214">**转发器**：值 **传输规则** 或包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="521d5-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="521d5-215">**转发类型**：邮箱 **规则** 或 **传输规则的值**。</span><span class="sxs-lookup"><span data-stu-id="521d5-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="521d5-216">**收件人名称**</span><span class="sxs-lookup"><span data-stu-id="521d5-216">**Recipient name**</span></span>
- <span data-ttu-id="521d5-217">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="521d5-217">**Recipient domain**</span></span>
- <span data-ttu-id="521d5-218">**详细信息**：这是邮件流规则的 GUID 值，或收件箱规则的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="521d5-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="521d5-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="521d5-219">**Count**</span></span>
- <span data-ttu-id="521d5-220">**第一个前进日期**</span><span class="sxs-lookup"><span data-stu-id="521d5-220">**First forward date**</span></span>

<span data-ttu-id="521d5-221">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="521d5-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="521d5-222">若要返回报告视图，请单击"查看**报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="521d5-223">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="521d5-223">Mailflow status report</span></span>

<span data-ttu-id="521d5-224">邮件流 **状态报告类似于** "已发送 [和已接收的电子邮件"报告，包含](#sent-and-received-email-report)边缘上允许或阻止的电子邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="521d5-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="521d5-225">这是唯一包含边缘保护信息的报告，其中仅显示 Exchange Online Protection (EOP 邮件允许用于评估的服务中的 (数量) 。</span><span class="sxs-lookup"><span data-stu-id="521d5-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="521d5-226">务必了解，如果将邮件发送给五个收件人，则将其计为五封不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="521d5-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="521d5-227">要查看报告，请打开[安全&合规中心](https://protection.office.com)，转到报告**Reports** \> **仪表板，** 然后选择 **"邮件流状态报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="521d5-228">若要直接转到邮件流 **状态报告，请**打开 <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

!["报告"仪表板中的邮件流状态报告小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="521d5-230">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="521d5-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="521d5-231">打开报表时，" **类型"选项卡** 在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="521d5-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="521d5-232">默认情况下，此视图包含一个使用以下筛选器配置的图表和一个数据表：</span><span class="sxs-lookup"><span data-stu-id="521d5-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="521d5-233">**日期**：过去 7 天。</span><span class="sxs-lookup"><span data-stu-id="521d5-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="521d5-234">**方向**：</span><span class="sxs-lookup"><span data-stu-id="521d5-234">**Direction**:</span></span>

  - <span data-ttu-id="521d5-235">**入站**</span><span class="sxs-lookup"><span data-stu-id="521d5-235">**Inbound**</span></span>
  - <span data-ttu-id="521d5-236">**出站**</span><span class="sxs-lookup"><span data-stu-id="521d5-236">**Outbound**</span></span>
  - <span data-ttu-id="521d5-237">**组织内： 此**计数针对租户中的邮件，即</span><span class="sxs-lookup"><span data-stu-id="521d5-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="521d5-238">发件人abc@domain.com邮件发送到由入站xyz@domain.com (站邮件**和出站邮件\*\*\*\*单独计数的**) </span><span class="sxs-lookup"><span data-stu-id="521d5-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="521d5-239">**类型**：</span><span class="sxs-lookup"><span data-stu-id="521d5-239">**Type**:</span></span>

  - <span data-ttu-id="521d5-240">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-240">**Good mail**</span></span>
  - <span data-ttu-id="521d5-241">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="521d5-241">**Malware**</span></span>
  - <span data-ttu-id="521d5-242">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-242">**Spam**</span></span>
  - <span data-ttu-id="521d5-243">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="521d5-243">**Edge protection**</span></span>
  - <span data-ttu-id="521d5-244">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="521d5-244">**Rule messages**</span></span>
  - <span data-ttu-id="521d5-245">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-245">**Phishing email**</span></span>

<span data-ttu-id="521d5-246">图表按 Type 值 **组织** 。</span><span class="sxs-lookup"><span data-stu-id="521d5-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="521d5-247">你可以通过单击"筛选 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="521d5-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="521d5-248">该表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="521d5-248">The data table contains the following information:</span></span>

- <span data-ttu-id="521d5-249">**方向**</span><span class="sxs-lookup"><span data-stu-id="521d5-249">**Direction**</span></span>
- <span data-ttu-id="521d5-250">**类型**</span><span class="sxs-lookup"><span data-stu-id="521d5-250">**Type**</span></span>
- <span data-ttu-id="521d5-251">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="521d5-251">**24 hours**</span></span>
- <span data-ttu-id="521d5-252">**3 天**</span><span class="sxs-lookup"><span data-stu-id="521d5-252">**3 days**</span></span>
- <span data-ttu-id="521d5-253">**7 天**</span><span class="sxs-lookup"><span data-stu-id="521d5-253">**7 days**</span></span>
- <span data-ttu-id="521d5-254">**15 天**</span><span class="sxs-lookup"><span data-stu-id="521d5-254">**15 days**</span></span>
- <span data-ttu-id="521d5-255">**30 天**</span><span class="sxs-lookup"><span data-stu-id="521d5-255">**30 days**</span></span>

<span data-ttu-id="521d5-256">如果您单击 **"选择类别"可获取更多**详细信息，可以从下列值中进行选择：</span><span class="sxs-lookup"><span data-stu-id="521d5-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="521d5-257">**网络钓鱼电子邮件：** 选择此选项后，将你转到威 [胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="521d5-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="521d5-258">**电子邮件中的恶意软件**：选择此选项可转到威胁 [防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="521d5-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="521d5-259">**垃圾邮件检测：** 选择此选项后，您可以 [进出垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="521d5-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="521d5-260">**边缘阻止垃圾邮件**：选择此选项后，您将 [进出垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="521d5-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="521d5-261">**导出**：</span><span class="sxs-lookup"><span data-stu-id="521d5-261">**Export**:</span></span>

<span data-ttu-id="521d5-262">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="521d5-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="521d5-263">因此，如果要将数据导出 7 天，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="521d5-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="521d5-264">每个导出的 .csv 文件只能包含 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="521d5-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="521d5-265">如果当天数据包含 150，000 个行以上，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="521d5-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="521d5-266">邮件流状态报告中的类型视图</span><span class="sxs-lookup"><span data-stu-id="521d5-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="521d5-267">邮件流状态报告的路线视图</span><span class="sxs-lookup"><span data-stu-id="521d5-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="521d5-268">如果单击方向 **选项卡** ，将使用来自类型视图中 **相同的** 默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="521d5-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="521d5-269">图表按方向值 **组织** 。</span><span class="sxs-lookup"><span data-stu-id="521d5-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="521d5-270">你可以通过单击"筛选 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="521d5-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="521d5-271">使用"类型"视图中 **的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="521d5-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="521d5-272">该数据表包含来自类型视图的 **相同** 信息。</span><span class="sxs-lookup"><span data-stu-id="521d5-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="521d5-273">" **为更多详细信息提供的内容和** 行为选择类别"与"类型" **视图** 相同。</span><span class="sxs-lookup"><span data-stu-id="521d5-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="521d5-274">**导出**：</span><span class="sxs-lookup"><span data-stu-id="521d5-274">**Export**:</span></span>

<span data-ttu-id="521d5-275">对于详细信息视图，您只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="521d5-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="521d5-276">因此，如果要将数据导出 7 天，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="521d5-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="521d5-277">每个导出的 .csv 文件只能包含 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="521d5-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="521d5-278">如果当天数据包含 150，000 个行以上，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="521d5-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="521d5-279">邮件流状态报告中的方向视图</span><span class="sxs-lookup"><span data-stu-id="521d5-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="521d5-280">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="521d5-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="521d5-281">漏 **斗视图向** 你显示 Microsoft 电子邮件威胁防护功能如何在组织中筛选传入和传出电子邮件。</span><span class="sxs-lookup"><span data-stu-id="521d5-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="521d5-282">它提供了有关总电子邮件计数的详细信息，以及配置的威胁保护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）对此计数的影响的详细信息。</span><span class="sxs-lookup"><span data-stu-id="521d5-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="521d5-283">如果单击 **"漏斗"** 选项卡，此视图默认包含一个使用以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="521d5-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="521d5-284">**日期**：过去 7 天。</span><span class="sxs-lookup"><span data-stu-id="521d5-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="521d5-285">**方向**：</span><span class="sxs-lookup"><span data-stu-id="521d5-285">**Direction**:</span></span>

  - <span data-ttu-id="521d5-286">**入站**</span><span class="sxs-lookup"><span data-stu-id="521d5-286">**Inbound**</span></span>
  - <span data-ttu-id="521d5-287">**出站**</span><span class="sxs-lookup"><span data-stu-id="521d5-287">**Outbound**</span></span>
  - <span data-ttu-id="521d5-288">**组织内：此**计数适用于在租户内发送的邮件;例如，发件人abc@domain.com发送至收件人，xyz@domain.com (入站和出站邮件计数器) 。</span><span class="sxs-lookup"><span data-stu-id="521d5-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="521d5-289">聚合视图和数据表视图允许 90 天过时筛选。</span><span class="sxs-lookup"><span data-stu-id="521d5-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="521d5-290">如果单击 **"筛选器**"，可同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="521d5-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="521d5-291">此图显示按以下条件组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="521d5-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="521d5-292">**总电子邮件数**</span><span class="sxs-lookup"><span data-stu-id="521d5-292">**Total email**</span></span>
- <span data-ttu-id="521d5-293">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-293">**Email after edge protection**</span></span>
- <span data-ttu-id="521d5-294">**反恶意软件、文件信誉后的电子邮件、文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="521d5-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="521d5-295">**反网络钓鱼、URL 信誉、品牌模拟、反欺骗邮件的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="521d5-296">**反垃圾邮件、批量邮件筛选之后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="521d5-297">**用户和域模拟 1 后的电子邮件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="521d5-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="521d5-298">**文件后的电子邮件和 URL 销销**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="521d5-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="521d5-299">\*\*传递后保护后被检测为)  (性的电子邮件) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="521d5-300"><sup>仅</sup> 限 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="521d5-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="521d5-301">若要单独查看 EOP 或 ATP 筛选的电子邮件，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="521d5-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="521d5-302">Data 表包含以下信息，按日期顺序降序显示：</span><span class="sxs-lookup"><span data-stu-id="521d5-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="521d5-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="521d5-303">**Date**</span></span>
- <span data-ttu-id="521d5-304">**总电子邮件数**</span><span class="sxs-lookup"><span data-stu-id="521d5-304">**Total email**</span></span>
- <span data-ttu-id="521d5-305">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="521d5-305">**Edge protection**</span></span>
- <span data-ttu-id="521d5-306">**反恶意软件， 文件信誉， 文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="521d5-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="521d5-307">**Anti-phish， URL reputation， Brand impersonation， anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="521d5-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="521d5-308">**反垃圾邮件、批量邮件筛选**</span><span class="sxs-lookup"><span data-stu-id="521d5-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="521d5-309">\*\*用户和域模拟 (ATP) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="521d5-310">\*\*文件和 URL 指定 (ATP) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="521d5-311">\*\*传递后保护和 ZAP 防 (ATP) 或 ZAP (EOP) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="521d5-312">如果你选择数据表中的行，电子邮件计数的进一步细分会显示在浮出控件中。</span><span class="sxs-lookup"><span data-stu-id="521d5-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="521d5-313">**导出**：</span><span class="sxs-lookup"><span data-stu-id="521d5-313">**Export**:</span></span>

<span data-ttu-id="521d5-314">单击" **选项"** 下 **的"** 导出"后，可以选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="521d5-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="521d5-315">\*\*摘要 (，最多 90 天的数据) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="521d5-316">\*\*详细信息 (，最多使用过去 30) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="521d5-317">在 **"日期**"下，选择一个范围，然后单击"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="521d5-318">当前筛选器的数据将导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="521d5-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="521d5-319">每个导出的 .csv 文件只能包含 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="521d5-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="521d5-320">如果数据包含的行超过 150，000 个，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="521d5-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="521d5-321">邮件流状态报告中的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="521d5-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="521d5-322">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="521d5-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="521d5-323">" **技术"** 视图类似于 **漏斗视图** ，为配置的威胁防护功能提供更精细的详细信息。</span><span class="sxs-lookup"><span data-stu-id="521d5-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="521d5-324">你可以从该图表查看如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="521d5-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="521d5-325">如果单击" **技术"** 视图选项卡，默认情况下，此视图将包含一个具有以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="521d5-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="521d5-326">**日期**：过去 7 天。</span><span class="sxs-lookup"><span data-stu-id="521d5-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="521d5-327">**方向**：</span><span class="sxs-lookup"><span data-stu-id="521d5-327">**Direction**:</span></span>

  - <span data-ttu-id="521d5-328">**入站**</span><span class="sxs-lookup"><span data-stu-id="521d5-328">**Inbound**</span></span>
  - <span data-ttu-id="521d5-329">**出站**</span><span class="sxs-lookup"><span data-stu-id="521d5-329">**Outbound**</span></span>
  - <span data-ttu-id="521d5-330">**组织内： 此**计数针对租户中的邮件，即</span><span class="sxs-lookup"><span data-stu-id="521d5-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="521d5-331">发件人abc@domain.com邮件发送到收件人，xyz@domain.com (来自入站和出站邮件邮件) </span><span class="sxs-lookup"><span data-stu-id="521d5-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="521d5-332">聚合视图和数据表视图允许 90 天过时筛选。</span><span class="sxs-lookup"><span data-stu-id="521d5-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="521d5-333">如果单击 **"筛选器**"，可同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="521d5-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="521d5-334">此图显示分为以下类别的邮件：</span><span class="sxs-lookup"><span data-stu-id="521d5-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="521d5-335">**总电子邮件数**</span><span class="sxs-lookup"><span data-stu-id="521d5-335">**Total email**</span></span>
- <span data-ttu-id="521d5-336">**边缘允许，边缘筛选出**</span><span class="sxs-lookup"><span data-stu-id="521d5-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="521d5-337">**非恶意软件，安全附件检测 (ATP) 、反恶意软件引擎检测、规则阻止**</span><span class="sxs-lookup"><span data-stu-id="521d5-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="521d5-338">**非网络钓鱼、DMARC 失败、模拟检测、欺骗检测、钓鱼邮件检测**</span><span class="sxs-lookup"><span data-stu-id="521d5-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="521d5-339">\*\*无具有 URL 通知的检测、URL 反向检测 (ATP) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="521d5-340">**非垃圾邮件、垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-340">**Not spam, spam**</span></span>
- <span data-ttu-id="521d5-341">**非恶意电子邮件、安全链接检测和 (ATP) ZAP**</span><span class="sxs-lookup"><span data-stu-id="521d5-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="521d5-342">将鼠标悬停在图表的某个类别上时，可以看到该类别中的邮件数。</span><span class="sxs-lookup"><span data-stu-id="521d5-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="521d5-343">Data 表包含以下信息，按日期顺序降序显示：</span><span class="sxs-lookup"><span data-stu-id="521d5-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="521d5-344">**Date**</span><span class="sxs-lookup"><span data-stu-id="521d5-344">**Date**</span></span>
- <span data-ttu-id="521d5-345">**总电子邮件数**</span><span class="sxs-lookup"><span data-stu-id="521d5-345">**Total email**</span></span>
- <span data-ttu-id="521d5-346">**筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="521d5-346">**Edge filtered**</span></span>
- <span data-ttu-id="521d5-347">**反恶意软件引擎、安全附件、已筛选规则**</span><span class="sxs-lookup"><span data-stu-id="521d5-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="521d5-348">**DMARC， 模拟， 欺骗， 已筛选钓鱼**</span><span class="sxs-lookup"><span data-stu-id="521d5-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="521d5-349">**URL 描述检测**</span><span class="sxs-lookup"><span data-stu-id="521d5-349">**URL detonation detection**</span></span>
- <span data-ttu-id="521d5-350">**已筛选反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="521d5-351">**删除 ZAP**</span><span class="sxs-lookup"><span data-stu-id="521d5-351">**ZAP removed**</span></span>
- <span data-ttu-id="521d5-352">**通过安全链接进行检测**</span><span class="sxs-lookup"><span data-stu-id="521d5-352">**Detection by safe links**</span></span>

<span data-ttu-id="521d5-353">如果你选择数据表中的行，电子邮件计数的进一步细分会显示在浮出控件中。</span><span class="sxs-lookup"><span data-stu-id="521d5-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="521d5-354">**导出**：</span><span class="sxs-lookup"><span data-stu-id="521d5-354">**Export**:</span></span>

<span data-ttu-id="521d5-355">单击"导出 **"，** 可以在" **选项** "下选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="521d5-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="521d5-356">\*\*摘要 (，最多 90 天的数据) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="521d5-357">\*\*详细信息 (，最多使用过去 30) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="521d5-358">在 **"日期**"下，选择一个范围，然后单击"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="521d5-359">当前筛选器的数据将导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="521d5-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="521d5-360">每个导出的 .csv 文件只能包含 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="521d5-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="521d5-361">如果数据包含的行超过 150，000 个，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="521d5-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="521d5-362">邮件流状态报告中的技术视图</span><span class="sxs-lookup"><span data-stu-id="521d5-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="521d5-363">已发送和已接收电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="521d5-363">Sent and received email report</span></span>

<span data-ttu-id="521d5-364">已 **发送和已接收电子邮件** 报告是一种智能报告，其中显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件以及标识为"良好"的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="521d5-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="521d5-365">此报告和邮件流状态报告 [之间的差异在](#mailflow-status-report) 于：此报告不包括有关受边缘保护阻止的邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="521d5-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="521d5-366">报告的聚合视图和详细信息视图允许 90 天过时筛选。</span><span class="sxs-lookup"><span data-stu-id="521d5-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="521d5-367">若要查看报告，请打开安全 [与&合规中心，](https://protection.office.com)转到"报表 **仪表板** \> **"，选择** "已发送 **和已接收"电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="521d5-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="521d5-368">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

!["报表"仪表板中已发送和已接收的电子邮件小部件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="521d5-370">"已发送和已接收的电子邮件"报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="521d5-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="521d5-371">下面的图表提供了报表视图：</span><span class="sxs-lookup"><span data-stu-id="521d5-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="521d5-372">**按类型分解：** 类型：此图显示所有可用类别：</span><span class="sxs-lookup"><span data-stu-id="521d5-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="521d5-373">**Total**</span><span class="sxs-lookup"><span data-stu-id="521d5-373">**Total**</span></span>
  - <span data-ttu-id="521d5-374">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="521d5-374">**Good mail**</span></span>
  - <span data-ttu-id="521d5-375">**EOP (恶意软件策略)  (** 恶意软件) </span><span class="sxs-lookup"><span data-stu-id="521d5-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="521d5-376">**垃圾邮件检测**</span><span class="sxs-lookup"><span data-stu-id="521d5-376">**Spam detections**</span></span>
  - <span data-ttu-id="521d5-377">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="521d5-377">**Rule messages**</span></span>
  - <span data-ttu-id="521d5-378">Office 365 ATP \*\* (高级\*\*) </span><span class="sxs-lookup"><span data-stu-id="521d5-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="521d5-379">当您将鼠标悬停在图表 (的数据) 时，可以看到该天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="521d5-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![已发送和已接收电子邮件报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="521d5-381">**分解器：方向**：图表显示**总数据**、**入站\*\*\*\*和出站**数据。</span><span class="sxs-lookup"><span data-stu-id="521d5-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="521d5-382">当您将鼠标悬停在图表 (的数据) 时，可以看到该天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="521d5-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  !["已发送和接收的电子邮件"报告中的"路线"视图](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="521d5-384">**深化信息** \>**恶意软件 (恶意软件) ：** 该选择将会使您[进入电子邮件报告中的恶意软件检测](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="521d5-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="521d5-385">**深化信息** \>\*\*垃圾邮件检测) \*\*：此选项将会转到[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="521d5-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="521d5-386">如果单击 **文件** 中的报表视图筛选器，可以用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="521d5-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="521d5-387">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="521d5-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="521d5-388">方向值</span><span class="sxs-lookup"><span data-stu-id="521d5-388">Direction values</span></span>
- <span data-ttu-id="521d5-389">类型值</span><span class="sxs-lookup"><span data-stu-id="521d5-389">Type values</span></span>

<span data-ttu-id="521d5-390">要返回到下一报表视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="521d5-391">"已发送"和"已接收邮件"报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="521d5-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="521d5-392">如果您单击"**分解依次**显示：**方向或细分：方向\*\*\*\*视图"或"方向"视图中**的"查看详细信息表"，会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="521d5-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="521d5-393">\*\*UTC (日期) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-393">**Date (UTC)**</span></span>
- <span data-ttu-id="521d5-394">**类型**</span><span class="sxs-lookup"><span data-stu-id="521d5-394">**Type**</span></span>
- <span data-ttu-id="521d5-395">**方向**</span><span class="sxs-lookup"><span data-stu-id="521d5-395">**Direction**</span></span>
- <span data-ttu-id="521d5-396">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="521d5-396">**Message count**</span></span>

<span data-ttu-id="521d5-397">如果单击 **详细信息表** 视图中的"筛选器"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="521d5-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="521d5-398">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="521d5-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="521d5-399">方向值</span><span class="sxs-lookup"><span data-stu-id="521d5-399">Direction values</span></span>
- <span data-ttu-id="521d5-400">类型值</span><span class="sxs-lookup"><span data-stu-id="521d5-400">Type values</span></span>

<span data-ttu-id="521d5-401">要返回到下一报表视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="521d5-402">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="521d5-402">Top senders and recipients report</span></span>

<span data-ttu-id="521d5-403">主要 **发件人数和收件人** 报告是一个饼图，显示主要的电子邮件发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="521d5-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="521d5-404">若要查看报告，请打开安全[&合规中心，](https://protection.office.com)转到"**报告仪表板** \> **"，然后选择**"首**要发件人和收件人"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="521d5-405">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="521d5-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

!["报表"仪表板中的"主要发件人和收件人"小部件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="521d5-407">主要发件人和收件人报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="521d5-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="521d5-408">下面的图表提供了报表视图：</span><span class="sxs-lookup"><span data-stu-id="521d5-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="521d5-409">**显示主要 \> 邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="521d5-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="521d5-410">**显示主要邮件 \> 收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="521d5-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="521d5-411">**显示主要垃圾邮件 \> 收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="521d5-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="521d5-412">**显示数据 \> EOP 网站集的 (** 收件人) </span><span class="sxs-lookup"><span data-stu-id="521d5-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="521d5-413">\*\*显示数据 \> Office \*\* 365 ATP ()  (主要的恶意软件) </span><span class="sxs-lookup"><span data-stu-id="521d5-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="521d5-414">复合饼图的大小根据这些选择发生变化。</span><span class="sxs-lookup"><span data-stu-id="521d5-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="521d5-415">将鼠标悬停在饼图中的 wedge 上时，可以看到发送或接收的邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="521d5-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="521d5-416">如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="521d5-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![用户和收件人报告中"报告"视图中的饼图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="521d5-418">主要发件人和收件人报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="521d5-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="521d5-419">如果您单击 **"查看详细信息**表"，显示的信息取决于正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="521d5-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="521d5-420">**显示主要 \> 邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="521d5-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="521d5-421">**主要邮件发件人**</span><span class="sxs-lookup"><span data-stu-id="521d5-421">**Top mail senders**</span></span>
  - <span data-ttu-id="521d5-422">**Count**</span><span class="sxs-lookup"><span data-stu-id="521d5-422">**Count**</span></span>

- <span data-ttu-id="521d5-423">**显示主要邮件 \> 收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="521d5-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="521d5-424">**主要邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="521d5-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="521d5-425">**Count**</span><span class="sxs-lookup"><span data-stu-id="521d5-425">**Count**</span></span>

- <span data-ttu-id="521d5-426">**显示主要垃圾邮件 \> 收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="521d5-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="521d5-427">**主要垃圾邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="521d5-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="521d5-428">**Count**</span><span class="sxs-lookup"><span data-stu-id="521d5-428">**Count**</span></span>

- <span data-ttu-id="521d5-429">**显示数据 \> EOP 网站集的 (** 收件人) </span><span class="sxs-lookup"><span data-stu-id="521d5-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="521d5-430">**主要的恶意软件收件人**</span><span class="sxs-lookup"><span data-stu-id="521d5-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="521d5-431">**Count**</span><span class="sxs-lookup"><span data-stu-id="521d5-431">**Count**</span></span>

- <span data-ttu-id="521d5-432">\*\*显示数据 \> Office \*\* 365 ATP ()  (主要的恶意软件) </span><span class="sxs-lookup"><span data-stu-id="521d5-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="521d5-433">\*\*ATP 对象 (的主要) \*\*</span><span class="sxs-lookup"><span data-stu-id="521d5-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="521d5-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="521d5-434">**Count**</span></span>

<span data-ttu-id="521d5-435">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="521d5-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="521d5-436">要返回到下一报表视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="521d5-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="521d5-437">查看这些报表需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="521d5-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="521d5-438">若要查看和使用这些报告，你必须是安全 & 合规中心和 Exchange Online **中指定角色** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="521d5-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="521d5-439">在安全&合规中心内，你必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="521d5-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="521d5-440">-组织管理 -安全 (也可以在 Azure Active Directory 管理中心 [-Security](https://aad.portal.azure.com) Reader 中执行此操作</span><span class="sxs-lookup"><span data-stu-id="521d5-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="521d5-441">有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="521d5-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="521d5-442">在 Exchange Online 中，你必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="521d5-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="521d5-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span><span class="sxs-lookup"><span data-stu-id="521d5-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="521d5-444">有关详细信息，请参阅 Exchange [Online 中的权限和](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)[管理 Exchange Online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="521d5-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="521d5-445">相关主题</span><span class="sxs-lookup"><span data-stu-id="521d5-445">Related topics</span></span>

[<span data-ttu-id="521d5-446">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="521d5-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="521d5-447">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="521d5-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="521d5-448">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="521d5-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="521d5-449">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="521d5-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
