---
title: 查看 "报告" 仪表板中的邮件流报告
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
description: 管理员可以了解安全 & 合规性中心的 "报告" 仪表板中提供的邮件流报告。
ms.custom: ''
ms.openlocfilehash: 801463877db2e022ab84c3187367587c61f71090
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600577"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="ed1fd-103">在安全 & 合规中心中查看 "报告" 仪表板中的邮件流报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ed1fd-104">除了安全性 & 合规性中心中的 [邮件流仪表板](mail-flow-insights-v2.md) 中提供的邮件流报告之外，"报告" 仪表板中还提供了多种其他邮件流报告，可帮助您监视 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="ed1fd-105">如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，则可以转到 "**报告**" 仪表板，在[安全 & 合规中心](https://office.protection.com)中查看这些报告 \> **Dashboard**。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="ed1fd-106">若要直接转到 "报表" 仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Security & 合规中心中的报告仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="ed1fd-108">连接器报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-108">Connector report</span></span>

<span data-ttu-id="ed1fd-109">**连接器报告**显示为您的组织配置的[入站和出站连接器](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)上的 "邮件流" 活动。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="ed1fd-110">若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **连接器报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="ed1fd-111">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

!["报告" 仪表板中的连接器报告小部件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="ed1fd-113">连接器报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-113">Report view for the Connector report</span></span>

<span data-ttu-id="ed1fd-114">以下图表在报表视图中可用：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="ed1fd-115">**数据查看依据：邮件流**：此图显示按以下方式组织的入站和出站邮件的数量：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="ed1fd-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-116">**Total**</span></span>
  - <span data-ttu-id="ed1fd-117">**从不带连接器的 internet**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="ed1fd-118">**不带连接器的 internet 连接**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="ed1fd-119">您已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="ed1fd-120">若要隔离图表中的数据，请使用 " **显示数据以供** 控制" 选择其中一个选项或 **所有邮件流**。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![通过邮件流查看连接器报告中的数据](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="ed1fd-122">**查看数据的依据： TLS 用法**：此图显示了邮件流的传输层安全性 (TLS) 版本使用情况的百分比。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="ed1fd-123">若要隔离图表中的数据，请使用 " **显示数据以供** 控制" 选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="ed1fd-124">**所有邮件流**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-124">**All mail flow**</span></span>
  - <span data-ttu-id="ed1fd-125">**从不带连接器的 internet**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="ed1fd-126">**不带连接器的 internet 连接**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="ed1fd-127">您已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-127">A specific connector that you've configured.</span></span>

  ![通过 TLS 使用在连接器报告中查看数据](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="ed1fd-129">如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="ed1fd-130">连接器报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-130">Details table view for the Connector report</span></span>

<span data-ttu-id="ed1fd-131">如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ed1fd-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-132">**Date**</span></span>
- <span data-ttu-id="ed1fd-133">**连接器方向和名称**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-133">**Connector direction and name**</span></span>
- <span data-ttu-id="ed1fd-134">**连接器类型**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-134">**Connector type**</span></span>
- <span data-ttu-id="ed1fd-135">**强制 TLS？**：值 **True** 或 **False**。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="ed1fd-136">**没有 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="ed1fd-137">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="ed1fd-138">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="ed1fd-139">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="ed1fd-140">**Volume**：邮件数。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="ed1fd-141">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ed1fd-142">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="ed1fd-143">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-143">Exchange transport rule report</span></span>

<span data-ttu-id="ed1fd-144">**Exchange 传输规则报告**显示邮件流规则的效果 (也称为传输规则) 组织中的传入和传出邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="ed1fd-145">若要查看报告，请打开 [安全 & 合规中心](https://protection.office.com)，转到 " **报告** \> **仪表板** "，然后选择 " **Exchange 传输规则**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="ed1fd-146">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

!["报告" 仪表板中的 Exchange 传输规则小部件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="ed1fd-148">Exchange 传输规则报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="ed1fd-149">以下图表在报表视图中可用：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="ed1fd-150">**数据查看依据： Exchange 传输规则** \>**分解方式：方向**：此图显示受传输规则影响的**入站**和**出站**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="ed1fd-151">**数据查看依据： Exchange 传输规则** \>**分解方式：严重性**：此图显示**高严重性**和**中低严重性**以及**低严重性**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="ed1fd-152">将严重性级别设置为规则中的操作 (使用严重级别或_SetAuditSeverity_) **审核此规则**。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="ed1fd-153">有关详细信息，请参阅 [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="ed1fd-154">**数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此图显示受数据丢失防护 (DLP) 传输规则影响的**入站**和**出站**邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="ed1fd-155">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="ed1fd-156">**显示以下项的数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="ed1fd-157">**显示以下项的数据：已损坏的用户**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="ed1fd-158">**显示以下项的数据：检测到的内容量过低美国爱国法案**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="ed1fd-159">**数据查看依据： DLP Exchange 传输规则** \>**分解方式：方向**：此视图显示**高严重性**和**中严重性**的数目以及受 DLP 传输规则影响的**低严重性**邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="ed1fd-160">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="ed1fd-161">**显示以下项的数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="ed1fd-162">**显示以下项的数据：已损坏的用户**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="ed1fd-163">**显示以下项的数据：检测到的内容量过低美国爱国法案**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="ed1fd-164">如果您在报告视图中单击 " **筛选器** "，则可以使用以下筛选器修改结果：：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="ed1fd-165">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="ed1fd-166">方向值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-166">Direction values</span></span>
- <span data-ttu-id="ed1fd-167">严重度值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-167">Severity values</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="ed1fd-169">Exchange 传输规则报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="ed1fd-170">如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ed1fd-171">**数据查看依据： Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="ed1fd-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-172">**Date**</span></span>
  - <span data-ttu-id="ed1fd-173">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-173">**Transport rule**</span></span>
  - <span data-ttu-id="ed1fd-174">**Subject**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-174">**Subject**</span></span>
  - <span data-ttu-id="ed1fd-175">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-175">**Sender address**</span></span>
  - <span data-ttu-id="ed1fd-176">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-176">**Recipient address**</span></span>
  - <span data-ttu-id="ed1fd-177">**严重性**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-177">**Severity**</span></span>
  - <span data-ttu-id="ed1fd-178">**Direction**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-178">**Direction**</span></span>

- <span data-ttu-id="ed1fd-179">**数据查看依据： DLP Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="ed1fd-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-180">**Date**</span></span>
  - <span data-ttu-id="ed1fd-181">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-181">**DLP policy**</span></span>
  - <span data-ttu-id="ed1fd-182">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-182">**Transport rule**</span></span>
  - <span data-ttu-id="ed1fd-183">**Subject**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-183">**Subject**</span></span>
  - <span data-ttu-id="ed1fd-184">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-184">**Sender address**</span></span>
  - <span data-ttu-id="ed1fd-185">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-185">**Recipient address**</span></span>
  - <span data-ttu-id="ed1fd-186">**严重性**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-186">**Severity**</span></span>
  - <span data-ttu-id="ed1fd-187">**Direction**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-187">**Direction**</span></span>

<span data-ttu-id="ed1fd-188">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ed1fd-189">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="ed1fd-190">方向值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-190">Direction values</span></span>
- <span data-ttu-id="ed1fd-191">严重度值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-191">Severity values</span></span>

<span data-ttu-id="ed1fd-192">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="ed1fd-193">转发报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-193">Forwarding report</span></span>

<span data-ttu-id="ed1fd-194">**转发报告**将组织的自动转发的邮件显示为 Exchange Online 邮箱中的外部域。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="ed1fd-195">转发的邮件可能会带来安全或合规性风险，并可能指示已损坏的帐户。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="ed1fd-196">若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **转发报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="ed1fd-197">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

!["报告" 仪表板中的转发报告构件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="ed1fd-199">转发报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="ed1fd-200">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ed1fd-201">显示以下各项**的数据：转发方法**：显示以下方法：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="ed1fd-202">**传输规则**：也称为 [邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="ed1fd-203">**邮箱规则**：也称为 [收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="ed1fd-205">**显示数据：转发域**：此视图显示作为转发目标的收件人域。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="ed1fd-207">**显示以下项的数据：转发器**：显示以下转发器：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="ed1fd-208">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-208">**Transport rule**</span></span>
  - <span data-ttu-id="ed1fd-209">包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![转发报告中的转发器视图](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="ed1fd-211">如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="ed1fd-212">转发报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="ed1fd-213">如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ed1fd-214">**转发器**：值 **传输规则** 或包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="ed1fd-215">**转发类型**：值 **邮箱规则** 或 **传输规则**。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="ed1fd-216">**收件人名称**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-216">**Recipient name**</span></span>
- <span data-ttu-id="ed1fd-217">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-217">**Recipient domain**</span></span>
- <span data-ttu-id="ed1fd-218">**详细信息**：这是邮件流规则的 GUID 值，或收件箱规则的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="ed1fd-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-219">**Count**</span></span>
- <span data-ttu-id="ed1fd-220">**第一次转发日期**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-220">**First forward date**</span></span>

<span data-ttu-id="ed1fd-221">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ed1fd-222">若要返回到 "报告" 视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="ed1fd-223">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-223">Mailflow status report</span></span>

<span data-ttu-id="ed1fd-224">**邮件流状态报告**类似于[发送和接收的电子邮件报告](#sent-and-received-email-report)，其中包含有关在边缘上允许或阻止的电子邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="ed1fd-225">这是唯一包含 edge 保护信息的报告，仅显示在允许 Exchange Online Protection (EOP) 进行评估之前阻止的电子邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="ed1fd-226">请务必注意，如果将邮件发送给5个收件人，我们会将其计数为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="ed1fd-227">若要查看报表，请打开 " [安全 & 合规中心](https://protection.office.com)"，转到 " **报告**" \> **仪表板** ，然后选择 " **邮件流状态报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="ed1fd-228">若要直接转到 " **邮件流状态" 报告**，请打开 <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

!["报告" 仪表板中的邮件流状态报告小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="ed1fd-230">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="ed1fd-231">打开报表时，" **类型** " 选项卡在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="ed1fd-232">默认情况下，此视图包含一个使用以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="ed1fd-233">**日期**：最近7天。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="ed1fd-234">**方向**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-234">**Direction**:</span></span>

  - <span data-ttu-id="ed1fd-235">**进货**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-235">**Inbound**</span></span>
  - <span data-ttu-id="ed1fd-236">**出站**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-236">**Outbound**</span></span>
  - <span data-ttu-id="ed1fd-237">**组织内**：此计数用于租户中的邮件，即</span><span class="sxs-lookup"><span data-stu-id="ed1fd-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="ed1fd-238">发件人 abc@domain.com 从 **入站** 和 **出站**) 分别发送给收件人 xyz@domain.com (计数</span><span class="sxs-lookup"><span data-stu-id="ed1fd-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="ed1fd-239">**类型**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-239">**Type**:</span></span>

  - <span data-ttu-id="ed1fd-240">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-240">**Good mail**</span></span>
  - <span data-ttu-id="ed1fd-241">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-241">**Malware**</span></span>
  - <span data-ttu-id="ed1fd-242">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-242">**Spam**</span></span>
  - <span data-ttu-id="ed1fd-243">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-243">**Edge protection**</span></span>
  - <span data-ttu-id="ed1fd-244">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-244">**Rule messages**</span></span>
  - <span data-ttu-id="ed1fd-245">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-245">**Phishing email**</span></span>

<span data-ttu-id="ed1fd-246">图表按 **类型** 值进行组织。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="ed1fd-247">您可以通过单击 " **筛选器** " 或通过单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="ed1fd-248">数据表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-248">The data table contains the following information:</span></span>

- <span data-ttu-id="ed1fd-249">**Direction**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-249">**Direction**</span></span>
- <span data-ttu-id="ed1fd-250">**类型**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-250">**Type**</span></span>
- <span data-ttu-id="ed1fd-251">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-251">**24 hours**</span></span>
- <span data-ttu-id="ed1fd-252">**3 天**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-252">**3 days**</span></span>
- <span data-ttu-id="ed1fd-253">**7 天**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-253">**7 days**</span></span>
- <span data-ttu-id="ed1fd-254">**15 天**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-254">**15 days**</span></span>
- <span data-ttu-id="ed1fd-255">**30 天**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-255">**30 days**</span></span>

<span data-ttu-id="ed1fd-256">如果单击 " **选择类别" 以了解更多详细信息**，则可以从以下值中进行选择：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="ed1fd-257">**网络钓鱼电子邮件**：此选择会将您带到 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="ed1fd-258">**电子邮件中的恶意软件**：此选择会将您带到 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="ed1fd-259">**垃圾邮件检测**：选择此选项将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="ed1fd-260">**边缘阻止的垃圾邮件**：选择此选项将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="ed1fd-261">**导出**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-261">**Export**:</span></span>

<span data-ttu-id="ed1fd-262">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="ed1fd-263">因此，如果要将数据导出7天，则需要执行7个不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="ed1fd-264">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ed1fd-265">如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="ed1fd-266">邮件流状态报告中的类型视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="ed1fd-267">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="ed1fd-268">如果单击 " **方向** " 选项卡，则将使用 " **类型** " 视图中的相同默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="ed1fd-269">图表按 **方向** 值组织。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="ed1fd-270">您可以通过单击 " **筛选器** " 或通过单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="ed1fd-271">将使用 " **类型** " 视图中的相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="ed1fd-272">数据表包含 **类型** 视图中的相同信息。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="ed1fd-273">**选择类别以获取更多详细信息**可用的选择和行为与 "**类型**" 视图相同。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="ed1fd-274">**导出**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-274">**Export**:</span></span>

<span data-ttu-id="ed1fd-275">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="ed1fd-276">因此，如果要将数据导出7天，则需要执行7个不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="ed1fd-277">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ed1fd-278">如果该天的数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="ed1fd-279">邮件流状态报告中的 "方向" 视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="ed1fd-280">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="ed1fd-281">**漏斗**视图显示了 Microsoft 的电子邮件威胁防护功能如何筛选组织中的传入和传出电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="ed1fd-282">它提供有关总电子邮件计数的详细信息，以及配置的威胁防护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）对此计数的影响。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="ed1fd-283">如果单击 " **漏斗** " 选项卡，则默认情况下，此视图包含一个使用以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="ed1fd-284">**日期**：最近7天。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="ed1fd-285">**方向**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-285">**Direction**:</span></span>

  - <span data-ttu-id="ed1fd-286">**进货**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-286">**Inbound**</span></span>
  - <span data-ttu-id="ed1fd-287">**出站**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-287">**Outbound**</span></span>
  - <span data-ttu-id="ed1fd-288">**组织内**：此计数适用于在租户内发送的邮件;即，发件人 abc@domain.com 发送到收件人 xyz@domain.com (与入站和出站) 分开计数。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="ed1fd-289">"聚合视图" 和 "数据表" 视图允许在筛选时90天。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="ed1fd-290">如果单击 " **筛选**"，则可以筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="ed1fd-291">此图显示了按以下方式组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="ed1fd-292">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-292">**Total email**</span></span>
- <span data-ttu-id="ed1fd-293">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-293">**Email after edge protection**</span></span>
- <span data-ttu-id="ed1fd-294">**反恶意软件、文件信誉、文件类型阻止之后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="ed1fd-295">**反网络钓鱼、URL 信誉、品牌模拟、反欺骗之后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="ed1fd-296">**反垃圾邮件后的电子邮件，批量邮件筛选**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="ed1fd-297">**用户和域模拟1之后的电子邮件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ed1fd-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="ed1fd-298">**File AND URL 沙箱1之后的电子邮件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ed1fd-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="ed1fd-299">\*\*在送达后保护 (URL 后，电子邮件被检测为良性。单击 "时间保护") \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="ed1fd-300">仅<sup>1</sup>个 OFFICE 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ed1fd-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="ed1fd-301">若要查看由 EOP 或 ATP 单独筛选的电子邮件，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="ed1fd-302">数据表包含以下信息，以降序显示日期顺序：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="ed1fd-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-303">**Date**</span></span>
- <span data-ttu-id="ed1fd-304">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-304">**Total email**</span></span>
- <span data-ttu-id="ed1fd-305">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-305">**Edge protection**</span></span> 
- <span data-ttu-id="ed1fd-306">**反恶意软件、文件信誉、文件类型阻止**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="ed1fd-307">**文件信誉**：由于其他 Microsoft 客户附加文件的标识而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="ed1fd-308">**文件类型阻止**：由于邮件中标识的恶意文件的类型而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>      
- <span data-ttu-id="ed1fd-309">**反钓鱼诈骗、URL 信誉、品牌模拟、反欺骗**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="ed1fd-310">**URL 信誉**：由于其他 Microsoft 客户的 URL 标识而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="ed1fd-311">**品牌模拟**：由于从知名品牌模拟发件人收到的邮件而被筛选出的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="ed1fd-312">**反欺骗**：由于试图欺骗收件人所属域的邮件或邮件发件人不拥有的域而被筛选出的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>  
- <span data-ttu-id="ed1fd-313">**反垃圾邮件、批量邮件筛选**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="ed1fd-314">**批量邮件筛选**：由于尝试将批量邮件传递给收件人而筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span> 
- <span data-ttu-id="ed1fd-315">\*\* (ATP) 的用户和域模拟 \*\*：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-315">**User and domain impersonation (ATP)**:</span></span>
  - <span data-ttu-id="ed1fd-316">**用户模拟**：由于试图模拟用户 (邮件发件人) （在反网络钓鱼策略的模拟保护设置中定义），筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="ed1fd-317">**域模拟**：由于试图模拟在反网络钓鱼策略的模拟保护设置中定义的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span> 
- <span data-ttu-id="ed1fd-318">\*\*文件和 URL 沙箱 (ATP) \*\*：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-318">**File and URL detonation (ATP)**:</span></span>
  - <span data-ttu-id="ed1fd-319">**文件沙箱**：通过安全附件策略筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="ed1fd-320">**URL 沙箱**：由安全链接策略筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>  
- <span data-ttu-id="ed1fd-321">\*\*传递后保护和 zap (ATP) 或 zap (EOP) \*\*： zap 指示自动清除零小时。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="ed1fd-322">如果选择数据表中的行，则会在浮出控件中显示电子邮件计数的进一步细分。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="ed1fd-323">**导出**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-323">**Export**:</span></span>

<span data-ttu-id="ed1fd-324">单击 "**选项**" 下的 "**导出**" 后，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="ed1fd-325">\*\*汇总 (最近90天内的数据) \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="ed1fd-326">\*\*详细信息 (最近30天内的数据) \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="ed1fd-327">在 " **日期**" 下，选择一个区域，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="ed1fd-328">将当前筛选器的数据导出到 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="ed1fd-329">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ed1fd-330">如果数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="ed1fd-331">邮件流状态报告中的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="ed1fd-332">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="ed1fd-333">**技术视图**类似于**漏斗**视图，提供了已配置的威胁防护功能的更精细详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="ed1fd-334">在图表中，您可以查看如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="ed1fd-335">如果单击 " **技术视图** " 选项卡，默认情况下，此视图包含一个使用以下筛选器配置的图表和数据表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="ed1fd-336">**日期**：最近7天。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="ed1fd-337">**方向**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-337">**Direction**:</span></span>

  - <span data-ttu-id="ed1fd-338">**进货**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-338">**Inbound**</span></span>
  - <span data-ttu-id="ed1fd-339">**出站**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-339">**Outbound**</span></span>
  - <span data-ttu-id="ed1fd-340">**组织内**：此计数用于租户中的邮件，即</span><span class="sxs-lookup"><span data-stu-id="ed1fd-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="ed1fd-341">发件人 abc@domain.com 从入站和出站) 分别发送给收件人 xyz@domain.com (计数</span><span class="sxs-lookup"><span data-stu-id="ed1fd-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="ed1fd-342">"聚合视图" 和 "数据表" 视图允许在筛选时90天。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="ed1fd-343">如果单击 " **筛选**"，则可以筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="ed1fd-344">此图显示了按以下类别组织的邮件：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="ed1fd-345">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-345">**Total email**</span></span>
- <span data-ttu-id="ed1fd-346">**边缘允许，已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-346">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="ed1fd-347">**非恶意软件、安全附件检测 (ATP) 、反恶意软件引擎检测、规则块**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-347">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="ed1fd-348">**不是网络钓鱼诈骗、DMARC 故障、模拟检测、欺骗检测、网络钓鱼检测**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-348">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="ed1fd-349">\*\*未检测到 URL 沙箱、URL 沙箱检测 (ATP) \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-349">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="ed1fd-350">**非垃圾邮件、垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-350">**Not spam, spam**</span></span>
- <span data-ttu-id="ed1fd-351">**非恶意电子邮件、安全链接检测 (ATP) 、ZAP**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-351">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="ed1fd-352">当您将鼠标悬停在图表中的某个类别上时，您可以看到该类别中的邮件数。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-352">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="ed1fd-353">数据表包含以下信息，以降序显示日期顺序：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-353">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="ed1fd-354">**Date**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-354">**Date**</span></span>
- <span data-ttu-id="ed1fd-355">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-355">**Total email**</span></span>
- <span data-ttu-id="ed1fd-356">**已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-356">**Edge filtered**</span></span>
- <span data-ttu-id="ed1fd-357">**反恶意软件引擎、安全附件、已筛选的规则**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-357">**Anti-malware engine, safe attachments, rule filtered**:</span></span>
  - <span data-ttu-id="ed1fd-358">已**筛选的规则**：由于邮件流规则而筛选出的邮件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-358">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="ed1fd-359">**DMARC、模拟、欺骗、网络钓鱼筛选**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-359">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="ed1fd-360">**DMARC**：由于邮件失败而导致的 DMARC 身份验证检查而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-360">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span> 
- <span data-ttu-id="ed1fd-361">**URL 沙箱检测**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-361">**URL detonation detection**</span></span>
- <span data-ttu-id="ed1fd-362">**已筛选的反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-362">**Anti-spam filtered**</span></span>
- <span data-ttu-id="ed1fd-363">**删除的 ZAP**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-363">**ZAP removed**</span></span>
- <span data-ttu-id="ed1fd-364">**通过安全链接进行检测**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-364">**Detection by safe links**</span></span>

<span data-ttu-id="ed1fd-365">如果选择数据表中的行，则会在浮出控件中显示电子邮件计数的进一步细分。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-365">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="ed1fd-366">**导出**：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-366">**Export**:</span></span>

<span data-ttu-id="ed1fd-367">单击 " **导出**"，在 " **选项** " 下，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-367">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="ed1fd-368">\*\*汇总 (最近90天内的数据) \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-368">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="ed1fd-369">\*\*详细信息 (最近30天内的数据) \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-369">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="ed1fd-370">在 " **日期**" 下，选择一个区域，然后单击 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-370">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="ed1fd-371">将当前筛选器的数据导出到 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-371">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="ed1fd-372">每个导出的 .csv 文件限制为150000行。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-372">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ed1fd-373">如果数据包含的行数超过150000，则会创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-373">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="ed1fd-374">邮件流状态报告中的技术视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-374">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="ed1fd-375">发送和接收的电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-375">Sent and received email report</span></span>

<span data-ttu-id="ed1fd-376">**已发送和已接收的电子邮件**报告是一个智能报告，显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为 "正常" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-376">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="ed1fd-377">此报告和 [邮件流状态报告](#mailflow-status-report) 的区别在于：此报告不包含有关边缘保护阻止的邮件的数据。请务必了解，如果将邮件发送给五个收件人，我们会将其作为一封邮件进行计数。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-377">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="ed1fd-378">报告的聚合视图和详细信息视图允许90天的筛选。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-378">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="ed1fd-379">若要查看报告，请打开 [安全性 & 合规性中心](https://protection.office.com)，转到 " **报告**" \> **仪表板** ，然后选择 " **已发送和已接收电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-379">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="ed1fd-380">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-380">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

!["报告" 仪表板中的发送和接收电子邮件小部件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="ed1fd-382">已发送和已接收电子邮件报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-382">Report view for the Sent and received email report</span></span>

<span data-ttu-id="ed1fd-383">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-383">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ed1fd-384">**分解方式：类型**：图表显示所有可用类别：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-384">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="ed1fd-385">**Total**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-385">**Total**</span></span>
  - <span data-ttu-id="ed1fd-386">**正常邮件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-386">**Good mail**</span></span>
  - <span data-ttu-id="ed1fd-387">\*\*恶意软件 (反恶意软件) \*\* (EOP) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-387">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="ed1fd-388">**垃圾邮件检测**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-388">**Spam detections**</span></span>
  - <span data-ttu-id="ed1fd-389">**规则消息**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-389">**Rule messages**</span></span>
  - <span data-ttu-id="ed1fd-390"> (Office 365 ATP) 的**高级恶意软件**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-390">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="ed1fd-391">当鼠标悬停在图表中某天 (数据点) 时，可以查看那天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-391">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![发送和接收的电子邮件报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="ed1fd-393">**分解方式：方向**：图表显示 **总计**、 **入站**和 **出站** 数据。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-393">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="ed1fd-394">当鼠标悬停在图表中某天 (数据点) 时，可以查看那天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-394">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![已发送和已接收电子邮件报告中的方向视图](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="ed1fd-396">**向下** \> 钻取 \*\*恶意软件 (反恶意软件) \*\*：此选择会将您带到 [电子邮件报告中的恶意软件检测](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-396">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="ed1fd-397">**向下** \> 钻取 \*\*垃圾邮件检测) \*\*：选择此选项将转到 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-397">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="ed1fd-398">如果您在报告视图中单击 " **筛选器** "，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-398">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ed1fd-399">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-399">**Start date** and **End date**</span></span>
- <span data-ttu-id="ed1fd-400">方向值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-400">Direction values</span></span>
- <span data-ttu-id="ed1fd-401">类型值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-401">Type values</span></span>

<span data-ttu-id="ed1fd-402">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-402">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="ed1fd-403">已发送和已接收电子邮件报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-403">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="ed1fd-404">如果在 "分解方式" 中单击 " **查看详细信息表** **：方向** " 或 " **分解方式"： "方向** " 视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-404">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="ed1fd-405">\*\*日期 (UTC) \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-405">**Date (UTC)**</span></span>
- <span data-ttu-id="ed1fd-406">**类型**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-406">**Type**</span></span>
- <span data-ttu-id="ed1fd-407">**Direction**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-407">**Direction**</span></span>
- <span data-ttu-id="ed1fd-408">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-408">**Message count**</span></span>

<span data-ttu-id="ed1fd-409">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-409">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ed1fd-410">**开始日期** 和 **结束日期**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-410">**Start date** and **End date**</span></span>
- <span data-ttu-id="ed1fd-411">方向值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-411">Direction values</span></span>
- <span data-ttu-id="ed1fd-412">类型值</span><span class="sxs-lookup"><span data-stu-id="ed1fd-412">Type values</span></span>

<span data-ttu-id="ed1fd-413">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-413">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="ed1fd-414">主要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-414">Top senders and recipients report</span></span>

<span data-ttu-id="ed1fd-415">**最上面的发件人和收件人**报告是显示主要电子邮件发件人和收件人的饼形图。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-415">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="ed1fd-416">若要查看报告，请打开 " [安全 & 合规中心](https://protection.office.com)"，转到 " **报告**" \> **仪表板** ，然后选择 " **主要发件人和收件人**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-416">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="ed1fd-417">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-417">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

!["报告" 仪表板中的 "主要发件人和收件人" 小部件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="ed1fd-419">主要发件人和收件人报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-419">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="ed1fd-420">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-420">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ed1fd-421">**显示 \> 主要邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-421">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="ed1fd-422">**显示 \> 主要邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-422">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="ed1fd-423">**显示 \> 排名靠前的垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-423">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="ed1fd-424">**显示数据 \> 主要的恶意软件收件人** (EOP) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-424">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="ed1fd-425">\*\*显示数据 \> 主要的恶意软件收件人 (ATP) \*\* (Office 365 ATP) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-425">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="ed1fd-426">饼图的复合根据这些选择的变化而变化。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-426">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="ed1fd-427">当您将鼠标指针悬停在饼图中时，您可以看到发送或接收的邮件数。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-427">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="ed1fd-428">如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-428">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

!["热门发件人和收件人" 报告中报告视图中的饼形图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="ed1fd-430">主要发件人和收件人报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="ed1fd-430">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="ed1fd-431">如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-431">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ed1fd-432">**显示 \> 主要邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-432">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="ed1fd-433">**主要邮件发件人**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-433">**Top mail senders**</span></span>
  - <span data-ttu-id="ed1fd-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-434">**Count**</span></span>

- <span data-ttu-id="ed1fd-435">**显示 \> 主要邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-435">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="ed1fd-436">**主要邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-436">**Top mail recipients**</span></span>
  - <span data-ttu-id="ed1fd-437">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-437">**Count**</span></span>

- <span data-ttu-id="ed1fd-438">**显示 \> 排名靠前的垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-438">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="ed1fd-439">**主要垃圾邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-439">**Top spam recipients**</span></span>
  - <span data-ttu-id="ed1fd-440">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-440">**Count**</span></span>

- <span data-ttu-id="ed1fd-441">**显示数据 \> 主要的恶意软件收件人** (EOP) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-441">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="ed1fd-442">**主要恶意软件收件人**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-442">**Top malware recipients**</span></span>
  - <span data-ttu-id="ed1fd-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-443">**Count**</span></span>

- <span data-ttu-id="ed1fd-444">\*\*显示数据 \> 主要的恶意软件收件人 (ATP) \*\* (Office 365 ATP) </span><span class="sxs-lookup"><span data-stu-id="ed1fd-444">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="ed1fd-445">\*\* (ATP) 的主要恶意软件收件人 \*\*</span><span class="sxs-lookup"><span data-stu-id="ed1fd-445">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="ed1fd-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="ed1fd-446">**Count**</span></span>

<span data-ttu-id="ed1fd-447">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-447">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ed1fd-448">若要返回到报告视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-448">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="ed1fd-449">查看这些报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="ed1fd-449">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="ed1fd-450">若要查看和使用报告，您必须是安全 & 合规性中心 **和** Exchange Online 中指定角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-450">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="ed1fd-451">在安全 & 合规性中心中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-451">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="ed1fd-452">-组织管理-安全管理员 (你也可以在 [Azure Active Directory 管理中心](https://aad.portal.azure.com) 中执行此操作-安全读者</span><span class="sxs-lookup"><span data-stu-id="ed1fd-452">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="ed1fd-453">有关详细信息，请参阅[安全与合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-453">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="ed1fd-454">在 Exchange Online 中，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="ed1fd-454">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="ed1fd-455">-组织管理-仅查看组织管理-仅查看收件人-合规性管理</span><span class="sxs-lookup"><span data-stu-id="ed1fd-455">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="ed1fd-456">有关详细信息，请参阅 [Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 中的权限和 [管理 exchange online 中的角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="ed1fd-456">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed1fd-457">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed1fd-457">Related topics</span></span>

[<span data-ttu-id="ed1fd-458">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="ed1fd-458">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ed1fd-459">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="ed1fd-459">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="ed1fd-460">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-460">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="ed1fd-461">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="ed1fd-461">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
