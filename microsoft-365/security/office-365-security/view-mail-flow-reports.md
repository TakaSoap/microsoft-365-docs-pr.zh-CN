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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解安全与合规中心的"报告"仪表板中&报告。
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029434"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="4b364-103">在安全与合规中心的"报告"仪表板中&邮件流报告</span><span class="sxs-lookup"><span data-stu-id="4b364-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4b364-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4b364-104">**Applies to**</span></span>
- [<span data-ttu-id="4b364-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4b364-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4b364-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4b364-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4b364-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b364-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="4b364-108">本主题中介绍的大多数报告都位于 Exchange 管理中心或 EAC () 。</span><span class="sxs-lookup"><span data-stu-id="4b364-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="4b364-109">有关详细信息，请参阅新 [Exchange 管理中心中的邮件流报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="4b364-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="4b364-110">[Exchange 传输规则报告](view-email-security-reports.md#exchange-transport-rule-report)在 Microsoft 365 Defender 门户中提供。</span><span class="sxs-lookup"><span data-stu-id="4b364-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="4b364-111">除了安全 & 合规中心的邮件流仪表板中提供[](mail-flow-insights-v2.md)的邮件流报告之外，报告仪表板中还提供了各种其他邮件流报告，以帮助您监视 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="4b364-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="4b364-112">如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在安全与合规中心内查看这些报告 [&"报告仪表板](https://protection.office.com) \> **"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="4b364-113">若要直接转到"报表"仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全与合规中心&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="4b364-115">连接器报告</span><span class="sxs-lookup"><span data-stu-id="4b364-115">Connector report</span></span>

<span data-ttu-id="4b364-116">连接器 **报告显示** 为组织配置的 [入站](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 和出站连接器上的邮件流活动。</span><span class="sxs-lookup"><span data-stu-id="4b364-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="4b364-117">若要查看报告，请打开安全与合规 [&，转到](https://protection.office.com)**报告仪表板** \> ，然后选择连接器 **报告**。</span><span class="sxs-lookup"><span data-stu-id="4b364-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="4b364-118">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

!["报告"仪表板中的"连接器报告"小组件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="4b364-120">连接器报表的报表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-120">Report view for the Connector report</span></span>

<span data-ttu-id="4b364-121">以下图表可用于报表视图：</span><span class="sxs-lookup"><span data-stu-id="4b364-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="4b364-122">**查看数据者：邮件流**：此图表显示组织方式的入站和出站邮件数：</span><span class="sxs-lookup"><span data-stu-id="4b364-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="4b364-123">**Total**</span><span class="sxs-lookup"><span data-stu-id="4b364-123">**Total**</span></span>
  - <span data-ttu-id="4b364-124">**从 Internet（不含连接器）**</span><span class="sxs-lookup"><span data-stu-id="4b364-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="4b364-125">**在没有连接器的情况下连接到 Internet**</span><span class="sxs-lookup"><span data-stu-id="4b364-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="4b364-126">已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="4b364-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="4b364-127">若要隔离图表中的数据，请使用"显示数据 **以** 控制"选择这些选项之一或"**所有邮件流"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在连接器报告中按邮件流查看数据](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="4b364-129">**查看数据者：TLS 使用情况**：此图显示传输层安全性 (TLS) 邮件流版本使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="4b364-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="4b364-130">若要隔离图表中的数据，请使用"显示 **控件的数据** "选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="4b364-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="4b364-131">**所有邮件流**</span><span class="sxs-lookup"><span data-stu-id="4b364-131">**All mail flow**</span></span>
  - <span data-ttu-id="4b364-132">**从 Internet（不含连接器）**</span><span class="sxs-lookup"><span data-stu-id="4b364-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="4b364-133">**在没有连接器的情况下连接到 Internet**</span><span class="sxs-lookup"><span data-stu-id="4b364-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="4b364-134">已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="4b364-134">A specific connector that you've configured.</span></span>

  ![在连接器报告中按 TLS 使用情况查看数据](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="4b364-136">如果 **单击筛选器中的** 报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="4b364-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="4b364-137">连接器报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-137">Details table view for the Connector report</span></span>

<span data-ttu-id="4b364-138">如果单击 **视图中的"** 查看详细信息"报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="4b364-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4b364-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b364-139">**Date**</span></span>
- <span data-ttu-id="4b364-140">**连接器方向和名称**</span><span class="sxs-lookup"><span data-stu-id="4b364-140">**Connector direction and name**</span></span>
- <span data-ttu-id="4b364-141">**连接器类型**</span><span class="sxs-lookup"><span data-stu-id="4b364-141">**Connector type**</span></span>
- <span data-ttu-id="4b364-142">**强制 TLS？：** 值 **True** 或 **False**。</span><span class="sxs-lookup"><span data-stu-id="4b364-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="4b364-143">**无 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="4b364-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="4b364-144">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="4b364-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="4b364-145">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="4b364-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="4b364-146">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="4b364-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="4b364-147">**Volume：** 消息数。</span><span class="sxs-lookup"><span data-stu-id="4b364-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="4b364-148">如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="4b364-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4b364-149">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="4b364-150">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="4b364-150">Exchange transport rule report</span></span>

<span data-ttu-id="4b364-151">**Exchange 传输规则报告显示** 邮件流规则对组织中 (传输规则) 传入和传出邮件的影响。</span><span class="sxs-lookup"><span data-stu-id="4b364-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="4b364-152">若要查看报告，请打开安全与合规 [&，转到](https://protection.office.com)**报告仪表板** \> ，然后选择 **Exchange 传输规则**。</span><span class="sxs-lookup"><span data-stu-id="4b364-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="4b364-153">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![报告仪表板中的 Exchange 传输规则小组件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="4b364-155">Exchange 传输规则报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="4b364-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="4b364-156">以下图表可用于报表视图：</span><span class="sxs-lookup"><span data-stu-id="4b364-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="4b364-157">**查看数据者：Exchange 传输规则** \>**Break down by： Direction**： This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="4b364-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="4b364-158">**查看数据者：Exchange 传输规则** \>**按以下值进行** 分解：严重性：此图表显示高严重性和中等严重性和 **低严重性邮件的数量**。</span><span class="sxs-lookup"><span data-stu-id="4b364-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="4b364-159">将严重性级别设置为规则中的操作， (严重性级别审核此规则或 _SetAuditSeverity_) 。</span><span class="sxs-lookup"><span data-stu-id="4b364-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="4b364-160">有关详细信息，请参阅 Mail [flow rule actions in Exchange Online。](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="4b364-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="4b364-161">**查看数据者：DLP Exchange 传输规则** \>**Break down by： Direction**： This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) rules.</span><span class="sxs-lookup"><span data-stu-id="4b364-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="4b364-162">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="4b364-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="4b364-163">**显示数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="4b364-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="4b364-164">**显示针对：遭到入侵的用户的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="4b364-165">**显示数据：检测到美国爱国者法案的内容量较低**</span><span class="sxs-lookup"><span data-stu-id="4b364-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="4b364-166">**查看数据者：DLP Exchange 传输规则** \>**Break down by： Direction**： This view shows the number of **High severity** and **Medium severity**， and Low **severity messages** that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="4b364-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="4b364-167">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="4b364-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="4b364-168">**显示数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="4b364-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="4b364-169">**显示针对：遭到入侵的用户的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="4b364-170">**显示数据：检测到美国爱国者法案的内容量较低**</span><span class="sxs-lookup"><span data-stu-id="4b364-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="4b364-171">如果 **单击筛选器中的** 报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="4b364-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="4b364-172">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4b364-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b364-173">方向值</span><span class="sxs-lookup"><span data-stu-id="4b364-173">Direction values</span></span>
- <span data-ttu-id="4b364-174">严重性值</span><span class="sxs-lookup"><span data-stu-id="4b364-174">Severity values</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="4b364-176">Exchange 传输规则报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="4b364-177">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="4b364-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4b364-178">**查看数据者：Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="4b364-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="4b364-179">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b364-179">**Date**</span></span>
  - <span data-ttu-id="4b364-180">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="4b364-180">**Transport rule**</span></span>
  - <span data-ttu-id="4b364-181">**主题**</span><span class="sxs-lookup"><span data-stu-id="4b364-181">**Subject**</span></span>
  - <span data-ttu-id="4b364-182">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="4b364-182">**Sender address**</span></span>
  - <span data-ttu-id="4b364-183">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="4b364-183">**Recipient address**</span></span>
  - <span data-ttu-id="4b364-184">**严重性**</span><span class="sxs-lookup"><span data-stu-id="4b364-184">**Severity**</span></span>
  - <span data-ttu-id="4b364-185">**方向**</span><span class="sxs-lookup"><span data-stu-id="4b364-185">**Direction**</span></span>

- <span data-ttu-id="4b364-186">**查看数据者：DLP Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="4b364-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="4b364-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b364-187">**Date**</span></span>
  - <span data-ttu-id="4b364-188">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="4b364-188">**DLP policy**</span></span>
  - <span data-ttu-id="4b364-189">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="4b364-189">**Transport rule**</span></span>
  - <span data-ttu-id="4b364-190">**主题**</span><span class="sxs-lookup"><span data-stu-id="4b364-190">**Subject**</span></span>
  - <span data-ttu-id="4b364-191">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="4b364-191">**Sender address**</span></span>
  - <span data-ttu-id="4b364-192">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="4b364-192">**Recipient address**</span></span>
  - <span data-ttu-id="4b364-193">**严重性**</span><span class="sxs-lookup"><span data-stu-id="4b364-193">**Severity**</span></span>
  - <span data-ttu-id="4b364-194">**方向**</span><span class="sxs-lookup"><span data-stu-id="4b364-194">**Direction**</span></span>

<span data-ttu-id="4b364-195">如果在详细信息 **表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="4b364-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4b364-196">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4b364-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b364-197">方向值</span><span class="sxs-lookup"><span data-stu-id="4b364-197">Direction values</span></span>
- <span data-ttu-id="4b364-198">严重性值</span><span class="sxs-lookup"><span data-stu-id="4b364-198">Severity values</span></span>

<span data-ttu-id="4b364-199">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="4b364-200">转发报告</span><span class="sxs-lookup"><span data-stu-id="4b364-200">Forwarding report</span></span>

<span data-ttu-id="4b364-201">转发 **报告显示** 组织自动将邮件从邮箱转发到Exchange Online域。</span><span class="sxs-lookup"><span data-stu-id="4b364-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="4b364-202">转发的邮件可能会带来安全或合规性风险，并可能指示帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="4b364-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="4b364-203">若要查看报告，请打开安全与&中心，**转到报告**[仪表板](https://protection.office.com) \> ，然后选择 **转发报告**。</span><span class="sxs-lookup"><span data-stu-id="4b364-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="4b364-204">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

!["报告"仪表板中的"转发报告"小组件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="4b364-206">转发报告的报表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="4b364-207">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="4b364-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4b364-208">**显示以下方法的数据：转发方法**：显示以下方法：</span><span class="sxs-lookup"><span data-stu-id="4b364-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="4b364-209">**传输规则**：也称为邮件 [流规则](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="4b364-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="4b364-210">**邮箱规则**：也称为收件箱 [规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="4b364-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="4b364-212">**显示数据：转发域**：此视图显示作为转发目标收件人域。</span><span class="sxs-lookup"><span data-stu-id="4b364-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="4b364-214">**显示以下转发器** 的数据：转发器如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b364-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="4b364-215">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="4b364-215">**Transport rule**</span></span>
  - <span data-ttu-id="4b364-216">包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4b364-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![转发报告中的转发器视图](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="4b364-218">如果 **单击筛选器中的** 报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="4b364-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="4b364-219">转发报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="4b364-220">如果单击 **视图中的"** 查看详细信息"报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="4b364-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="4b364-221">**转发器**：值 **传输规则** 或包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4b364-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="4b364-222">**转发类型**：值 **Mailbox rule** 或 **Transport rule**。</span><span class="sxs-lookup"><span data-stu-id="4b364-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="4b364-223">**收件人名称**</span><span class="sxs-lookup"><span data-stu-id="4b364-223">**Recipient name**</span></span>
- <span data-ttu-id="4b364-224">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="4b364-224">**Recipient domain**</span></span>
- <span data-ttu-id="4b364-225">**详细信息**：这是邮件流规则的 GUID 值或收件箱规则的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="4b364-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="4b364-226">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b364-226">**Count**</span></span>
- <span data-ttu-id="4b364-227">**第一个转发日期**</span><span class="sxs-lookup"><span data-stu-id="4b364-227">**First forward date**</span></span>

<span data-ttu-id="4b364-228">如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="4b364-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4b364-229">若要返回到报告视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="4b364-230">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="4b364-230">Mailflow status report</span></span>

<span data-ttu-id="4b364-231">邮件 **流状态报告** 类似于"已发送和已接收 [电子邮件](#sent-and-received-email-report)"报告，包含有关边缘上允许或阻止的电子邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="4b364-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="4b364-232">这是包含边缘保护信息的唯一报告，它只显示 EOP Exchange Online Protection (允许进入服务进行评估之前阻止的电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="4b364-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="4b364-233">必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="4b364-234">若要查看报告，请打开安全与合规 [&，转到](https://protection.office.com)**报告仪表板** \> ，然后选择 **邮件流状态报告**。</span><span class="sxs-lookup"><span data-stu-id="4b364-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="4b364-235">若要直接转到邮件 **流状态报告，** 请打开 <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

!["报告"仪表板中的"邮件流状态报告"小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="4b364-237">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="4b364-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="4b364-238">打开报表时，默认情况下 **会选中** "类型"选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b364-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="4b364-239">默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="4b364-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4b364-240">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="4b364-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="4b364-241">**方向**：</span><span class="sxs-lookup"><span data-stu-id="4b364-241">**Direction**:</span></span>

  - <span data-ttu-id="4b364-242">**入站**</span><span class="sxs-lookup"><span data-stu-id="4b364-242">**Inbound**</span></span>
  - <span data-ttu-id="4b364-243">**出站**</span><span class="sxs-lookup"><span data-stu-id="4b364-243">**Outbound**</span></span>
  - <span data-ttu-id="4b364-244">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="4b364-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="4b364-245">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与 **入站** 和出站邮件 **分开计算)**</span><span class="sxs-lookup"><span data-stu-id="4b364-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="4b364-246">**类型**：</span><span class="sxs-lookup"><span data-stu-id="4b364-246">**Type**:</span></span>

  - <span data-ttu-id="4b364-247">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-247">**Good mail**</span></span>
  - <span data-ttu-id="4b364-248">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="4b364-248">**Malware**</span></span>
  - <span data-ttu-id="4b364-249">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-249">**Spam**</span></span>
  - <span data-ttu-id="4b364-250">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="4b364-250">**Edge protection**</span></span>
  - <span data-ttu-id="4b364-251">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-251">**Rule messages**</span></span>
  - <span data-ttu-id="4b364-252">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-252">**Phishing email**</span></span>

<span data-ttu-id="4b364-253">图表按 Type **值组织** 。</span><span class="sxs-lookup"><span data-stu-id="4b364-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="4b364-254">可以通过单击"筛选器 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="4b364-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="4b364-255">该数据表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="4b364-255">The data table contains the following information:</span></span>

- <span data-ttu-id="4b364-256">**方向**</span><span class="sxs-lookup"><span data-stu-id="4b364-256">**Direction**</span></span>
- <span data-ttu-id="4b364-257">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b364-257">**Type**</span></span>
- <span data-ttu-id="4b364-258">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="4b364-258">**24 hours**</span></span>
- <span data-ttu-id="4b364-259">**3 天**</span><span class="sxs-lookup"><span data-stu-id="4b364-259">**3 days**</span></span>
- <span data-ttu-id="4b364-260">**7 天**</span><span class="sxs-lookup"><span data-stu-id="4b364-260">**7 days**</span></span>
- <span data-ttu-id="4b364-261">**15 天**</span><span class="sxs-lookup"><span data-stu-id="4b364-261">**15 days**</span></span>
- <span data-ttu-id="4b364-262">**30 天**</span><span class="sxs-lookup"><span data-stu-id="4b364-262">**30 days**</span></span>

<span data-ttu-id="4b364-263">If you click **Choose a category for more details**， you can select from the following values：</span><span class="sxs-lookup"><span data-stu-id="4b364-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="4b364-264">**网络钓鱼电子邮件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4b364-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4b364-265">**电子邮件中的恶意软件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4b364-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4b364-266">**垃圾邮件检测**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4b364-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="4b364-267">**边缘阻止的垃圾邮件**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4b364-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="4b364-268">**导出**：</span><span class="sxs-lookup"><span data-stu-id="4b364-268">**Export**:</span></span>

<span data-ttu-id="4b364-269">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="4b364-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4b364-270">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="4b364-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4b364-271">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4b364-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4b364-272">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4b364-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的类型视图](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="4b364-274">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="4b364-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="4b364-275">如果单击" **方向"** 选项卡，则使用"类型"视图中 **的相同** 默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="4b364-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="4b364-276">图表按 Direction **值** 组织。</span><span class="sxs-lookup"><span data-stu-id="4b364-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="4b364-277">可以通过单击"筛选器 **"或单击** 图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="4b364-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="4b364-278">使用"类型" **视图中的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="4b364-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="4b364-279">该数据表包含"类型"视图中 **的相同** 信息。</span><span class="sxs-lookup"><span data-stu-id="4b364-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="4b364-280">" **选择类别"了解更多详细信息** 可用的选择和行为与"类型 **"视图相同** 。</span><span class="sxs-lookup"><span data-stu-id="4b364-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="4b364-281">**导出**：</span><span class="sxs-lookup"><span data-stu-id="4b364-281">**Export**:</span></span>

<span data-ttu-id="4b364-282">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="4b364-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4b364-283">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="4b364-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4b364-284">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4b364-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4b364-285">如果当天的数据包含超过 150，000 行，则创建多个.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4b364-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![邮件流状态报告中的方向视图](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="4b364-287">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="4b364-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="4b364-288">漏 **斗** 视图显示 Microsoft 的电子邮件威胁防护功能如何筛选组织中传入和传出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="4b364-289">它提供有关总电子邮件计数以及配置的威胁防护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）如何影响此计数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b364-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="4b364-290">如果单击" **漏斗"** 选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="4b364-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4b364-291">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="4b364-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="4b364-292">**方向**：</span><span class="sxs-lookup"><span data-stu-id="4b364-292">**Direction**:</span></span>

  - <span data-ttu-id="4b364-293">**入站**</span><span class="sxs-lookup"><span data-stu-id="4b364-293">**Inbound**</span></span>
  - <span data-ttu-id="4b364-294">**出站**</span><span class="sxs-lookup"><span data-stu-id="4b364-294">**Outbound**</span></span>
  - <span data-ttu-id="4b364-295">**组织内部**：此计数用于租户内发送的邮件;即，发件人 abc@domain.com 收件人的邮件 xyz@domain.com (入站和出站邮件分开计算) 。</span><span class="sxs-lookup"><span data-stu-id="4b364-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="4b364-296">聚合视图和数据表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="4b364-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="4b364-297">如果单击 **"筛选器**"，可以同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="4b364-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="4b364-298">此图表显示按以下方式组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="4b364-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="4b364-299">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4b364-299">**Total email**</span></span>
- <span data-ttu-id="4b364-300">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-300">**Email after edge protection**</span></span>
- <span data-ttu-id="4b364-301">**反恶意软件后的电子邮件， 文件信誉， 文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="4b364-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="4b364-302">**反网络钓鱼后的电子邮件， URL 信誉， 品牌模拟， 反欺骗**</span><span class="sxs-lookup"><span data-stu-id="4b364-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="4b364-303">**反垃圾邮件、批量邮件筛选后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="4b364-304">**用户和域模拟之后的电子邮件**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b364-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="4b364-305">**文件和 URL 触发**<sup>1</sup>之后的电子邮件</span><span class="sxs-lookup"><span data-stu-id="4b364-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="4b364-306">**在传递后保护或 URL 单击时间保护 (检测为安全)**</span><span class="sxs-lookup"><span data-stu-id="4b364-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="4b364-307"><sup>1</sup> Defender for Office 365 仅</span><span class="sxs-lookup"><span data-stu-id="4b364-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="4b364-308">若要查看由 EOP 或 Defender 单独筛选的电子邮件Office 365，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="4b364-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="4b364-309">该数据表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="4b364-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="4b364-310">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b364-310">**Date**</span></span>
- <span data-ttu-id="4b364-311">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4b364-311">**Total email**</span></span>
- <span data-ttu-id="4b364-312">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="4b364-312">**Edge protection**</span></span>
- <span data-ttu-id="4b364-313">**反恶意软件， 文件信誉， 文件类型阻止**：</span><span class="sxs-lookup"><span data-stu-id="4b364-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="4b364-314">**文件信誉**：由于其他 Microsoft 客户标识的附加文件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="4b364-315">**文件类型阻止**：由于邮件中标识的恶意文件类型而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="4b364-316">**反网络钓鱼， URL 信誉， 品牌模拟， 反欺骗**：</span><span class="sxs-lookup"><span data-stu-id="4b364-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="4b364-317">**URL 信誉**：由于其他 Microsoft 客户标识的 URL 而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="4b364-318">**品牌模拟**：由于来自已知品牌模拟发件人的邮件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="4b364-319">**反欺骗**：由于邮件试图欺骗收件人所属的域或邮件发件人不属于的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="4b364-320">**反垃圾邮件，批量邮件筛选**：</span><span class="sxs-lookup"><span data-stu-id="4b364-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="4b364-321">**批量邮件筛选**：由于尝试将批量邮件传递至收件人而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="4b364-322">**Defender for (的用户和Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="4b364-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="4b364-323">用户模拟：由于尝试模拟用户 (邮件发件人) （在反网络钓鱼策略的模拟保护设置中定义）而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="4b364-324">**域模拟**：由于尝试模拟在反网络钓鱼策略的模拟保护设置中定义的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="4b364-325">**Defender for (的文件和 URL Office 365) ：**</span><span class="sxs-lookup"><span data-stu-id="4b364-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="4b364-326">**文件触发**：由附件策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="4b364-327">**URL 触发**：按链接策略保险箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="4b364-328">**传递后保护和 ZAP (ATP) 或 ZAP (EOP)**：ZAP 表示零时差自动清除。</span><span class="sxs-lookup"><span data-stu-id="4b364-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="4b364-329">如果在数据表中选择一行，则电子邮件计数的进一步细分将显示在该飞出区中。</span><span class="sxs-lookup"><span data-stu-id="4b364-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="4b364-330">**导出**：</span><span class="sxs-lookup"><span data-stu-id="4b364-330">**Export**:</span></span>

<span data-ttu-id="4b364-331">单击"选项 **"** 下的 **"** 导出"后，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4b364-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="4b364-332">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="4b364-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="4b364-333">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="4b364-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="4b364-334">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="4b364-335">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="4b364-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="4b364-336">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4b364-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4b364-337">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4b364-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![邮件流状态报告中的漏斗视图](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="4b364-339">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="4b364-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="4b364-340">" **技术"** 视图类似于漏 **斗视图** ，提供有关配置的威胁防护功能的更具体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b364-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="4b364-341">从图中，你可以看到如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="4b364-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="4b364-342">如果单击" **技术视图** "选项卡，默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="4b364-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4b364-343">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="4b364-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="4b364-344">**方向**：</span><span class="sxs-lookup"><span data-stu-id="4b364-344">**Direction**:</span></span>

  - <span data-ttu-id="4b364-345">**入站**</span><span class="sxs-lookup"><span data-stu-id="4b364-345">**Inbound**</span></span>
  - <span data-ttu-id="4b364-346">**出站**</span><span class="sxs-lookup"><span data-stu-id="4b364-346">**Outbound**</span></span>
  - <span data-ttu-id="4b364-347">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="4b364-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="4b364-348">发件人 abc@domain.com 发送到收件人的邮件 xyz@domain.com (与入站和出站邮件分开计数) </span><span class="sxs-lookup"><span data-stu-id="4b364-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="4b364-349">聚合视图和数据表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="4b364-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="4b364-350">如果单击 **"筛选器**"，可以同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="4b364-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="4b364-351">此图显示按以下类别组织的邮件：</span><span class="sxs-lookup"><span data-stu-id="4b364-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="4b364-352">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4b364-352">**Total email**</span></span>
- <span data-ttu-id="4b364-353">**边缘允许** 和 **边缘筛选**</span><span class="sxs-lookup"><span data-stu-id="4b364-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="4b364-354">**不是恶意软件\*\*\*\*、保险箱附件检测** <sup>\*</sup> **、反恶意软件引擎检测和\*\*\*\*规则邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="4b364-355">**非网络钓鱼\*\*\*\*、DMARC 失败**、**模拟检测**、**欺骗检测和\*\*\*\*钓鱼检测**</span><span class="sxs-lookup"><span data-stu-id="4b364-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="4b364-356">**无需检测 URL 触发和** **URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b364-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="4b364-357">**不是垃圾邮件** 和  **垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="4b364-358">**非恶意电子邮件\*\*\*\*、保险箱链接检测和** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="4b364-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="4b364-359"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4b364-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="4b364-360">将鼠标悬停在图表中的类别上时，可以看到该类别中的消息数。</span><span class="sxs-lookup"><span data-stu-id="4b364-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="4b364-361">该数据表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="4b364-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="4b364-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b364-362">**Date**</span></span>
- <span data-ttu-id="4b364-363">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="4b364-363">**Total email**</span></span>
- <span data-ttu-id="4b364-364">**已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="4b364-364">**Edge filtered**</span></span>
- <span data-ttu-id="4b364-365">**反恶意软件引擎，保险箱附件，已筛选规则**：</span><span class="sxs-lookup"><span data-stu-id="4b364-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="4b364-366">**已筛选规则**：由于邮件流规则而筛选 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="4b364-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="4b364-367">**DMARC， 模拟， 欺骗， 网络钓鱼筛选：**</span><span class="sxs-lookup"><span data-stu-id="4b364-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="4b364-368">**DMARC：** 由于邮件未通过 DMARC 身份验证检查而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="4b364-369">**URL 触发检测**</span><span class="sxs-lookup"><span data-stu-id="4b364-369">**URL detonation detection**</span></span>
- <span data-ttu-id="4b364-370">**已筛选反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="4b364-371">**ZAP 已删除**</span><span class="sxs-lookup"><span data-stu-id="4b364-371">**ZAP removed**</span></span>
- <span data-ttu-id="4b364-372">**按链接保险箱检测**</span><span class="sxs-lookup"><span data-stu-id="4b364-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="4b364-373">如果在数据表中选择一行，则电子邮件计数的进一步细分将显示在该飞出区中。</span><span class="sxs-lookup"><span data-stu-id="4b364-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="4b364-374">**导出**：</span><span class="sxs-lookup"><span data-stu-id="4b364-374">**Export**:</span></span>

<span data-ttu-id="4b364-375">单击" **导出"，** 在" **选项** "下，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4b364-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="4b364-376">**摘要 (最近 90 天的数据汇总)**</span><span class="sxs-lookup"><span data-stu-id="4b364-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="4b364-377">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="4b364-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="4b364-378">在 **"日期**"下，选择一个范围，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="4b364-379">当前筛选器的数据将导出到.csv文件中。</span><span class="sxs-lookup"><span data-stu-id="4b364-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="4b364-380">每个导出.csv文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="4b364-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4b364-381">如果数据包含的行数超过 150，000，.csv文件。</span><span class="sxs-lookup"><span data-stu-id="4b364-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![邮件流状态报告中的技术视图](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="4b364-383">已发送和已接收电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="4b364-383">Sent and received email report</span></span>

<span data-ttu-id="4b364-384">" **已发送和** 已接收电子邮件"报告是一个智能报告，它显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为"良好"的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="4b364-385">此报告与邮件流状态报告[](#mailflow-status-report)之间的区别在于：此报告不包含有关被边缘保护阻止的邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="4b364-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="4b364-386">**注意**：必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为一封邮件。</span><span class="sxs-lookup"><span data-stu-id="4b364-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="4b364-387">聚合视图和报告的详细视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="4b364-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="4b364-388">若要查看报告，请打开安全与&中心，转到报告 [仪表板](https://protection.office.com) \> ，然后选择 **已发送和已接收的电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="4b364-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="4b364-389">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

!["报告"仪表板中的"已发送和已接收电子邮件"小组件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="4b364-391">已发送和已接收电子邮件报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="4b364-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="4b364-392">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="4b364-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4b364-393">**分类：类型**：图表显示所有可用类别：</span><span class="sxs-lookup"><span data-stu-id="4b364-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="4b364-394">**Total**</span><span class="sxs-lookup"><span data-stu-id="4b364-394">**Total**</span></span>
  - <span data-ttu-id="4b364-395">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-395">**Good mail**</span></span>
  - <span data-ttu-id="4b364-396">**EOP (反恶意软件)  (** 恶意软件) </span><span class="sxs-lookup"><span data-stu-id="4b364-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="4b364-397">**垃圾邮件检测**</span><span class="sxs-lookup"><span data-stu-id="4b364-397">**Spam detections**</span></span>
  - <span data-ttu-id="4b364-398">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="4b364-398">**Rule messages**</span></span>
  - <span data-ttu-id="4b364-399">**Microsoft Defender (** 高级恶意软件Office 365) </span><span class="sxs-lookup"><span data-stu-id="4b364-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="4b364-400">当您将鼠标悬停在图表中 (一) ，可以看到当天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b364-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  !["已发送和已接收电子邮件"报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="4b364-402">**按：方向：** 图表显示 **总计**、 **入站** 和 **出站** 数据。</span><span class="sxs-lookup"><span data-stu-id="4b364-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="4b364-403">当您将鼠标悬停在图表中 (一) ，可以看到当天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b364-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![已发送和已接收电子邮件报告中的方向视图](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="4b364-405">**向下钻取** \>**恶意软件 (反恶意软件) ：** 此选择将你带至 [恶意软件检测报告](view-email-security-reports.md#malware-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4b364-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="4b364-406">**向下钻取** \>**垃圾邮件检测) ：** 此选择将您带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4b364-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="4b364-407">如果 **单击筛选器** 中的报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="4b364-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4b364-408">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4b364-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b364-409">方向值</span><span class="sxs-lookup"><span data-stu-id="4b364-409">Direction values</span></span>
- <span data-ttu-id="4b364-410">类型值</span><span class="sxs-lookup"><span data-stu-id="4b364-410">Type values</span></span>

<span data-ttu-id="4b364-411">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="4b364-412">已发送和已接收电子邮件报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="4b364-413">如果在"**中断者：** 方向"或"中断者：方向"视图中单击"查看详细信息"表，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="4b364-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="4b364-414">**Date (UTC)**</span><span class="sxs-lookup"><span data-stu-id="4b364-414">**Date (UTC)**</span></span>
- <span data-ttu-id="4b364-415">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b364-415">**Type**</span></span>
- <span data-ttu-id="4b364-416">**方向**</span><span class="sxs-lookup"><span data-stu-id="4b364-416">**Direction**</span></span>
- <span data-ttu-id="4b364-417">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="4b364-417">**Message count**</span></span>

<span data-ttu-id="4b364-418">如果在详细信息 **表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="4b364-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4b364-419">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="4b364-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b364-420">方向值</span><span class="sxs-lookup"><span data-stu-id="4b364-420">Direction values</span></span>
- <span data-ttu-id="4b364-421">类型值</span><span class="sxs-lookup"><span data-stu-id="4b364-421">Type values</span></span>

<span data-ttu-id="4b364-422">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="4b364-423">首要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="4b364-423">Top senders and recipients report</span></span>

<span data-ttu-id="4b364-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span><span class="sxs-lookup"><span data-stu-id="4b364-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="4b364-425">若要查看报告，请打开安全与合规&，**转到"** 报告 [仪表板](https://protection.office.com)"，然后选择" \> **顶级发件人和收件人"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="4b364-426">若要直接转到报告，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="4b364-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

!["报告"仪表板中的"热门发件人和收件人"小组件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="4b364-428">顶级发件人和收件人报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="4b364-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="4b364-429">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="4b364-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4b364-430">**显示热门 \> 邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="4b364-431">**显示热门 \> 邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="4b364-432">**显示热门 \> 垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="4b364-433">**显示数据 \>** EOP 邮件 (恶意软件) </span><span class="sxs-lookup"><span data-stu-id="4b364-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="4b364-434">**在 Defender for \> Office 365) 中显示 (恶意软件收件人Office 365)**</span><span class="sxs-lookup"><span data-stu-id="4b364-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="4b364-435">饼图的组成将基于这些选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="4b364-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="4b364-436">将鼠标悬停在饼图中的一个浮点上时，可以看到已发送或已接收邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="4b364-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="4b364-437">如果 **单击筛选器中的** 报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="4b364-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

!["热门发件人和收件人"报告中的"报告"视图中的饼图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="4b364-439">"热门发件人和收件人"报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="4b364-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="4b364-440">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="4b364-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4b364-441">**显示热门 \> 邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="4b364-442">**热门邮件发件人**</span><span class="sxs-lookup"><span data-stu-id="4b364-442">**Top mail senders**</span></span>
  - <span data-ttu-id="4b364-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b364-443">**Count**</span></span>

- <span data-ttu-id="4b364-444">**显示热门 \> 邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="4b364-445">**热门邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="4b364-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="4b364-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b364-446">**Count**</span></span>

- <span data-ttu-id="4b364-447">**显示热门 \> 垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="4b364-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="4b364-448">**热门垃圾邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="4b364-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="4b364-449">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b364-449">**Count**</span></span>

- <span data-ttu-id="4b364-450">**显示数据 \>** EOP 邮件 (恶意软件) </span><span class="sxs-lookup"><span data-stu-id="4b364-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="4b364-451">**热门恶意软件收件人**</span><span class="sxs-lookup"><span data-stu-id="4b364-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="4b364-452">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b364-452">**Count**</span></span>

- <span data-ttu-id="4b364-453">**在 Defender for \> Office 365) 中显示 (恶意软件收件人Office 365)**</span><span class="sxs-lookup"><span data-stu-id="4b364-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="4b364-454">**Defender for (的热门恶意软件Office 365)**</span><span class="sxs-lookup"><span data-stu-id="4b364-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="4b364-455">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b364-455">**Count**</span></span>

<span data-ttu-id="4b364-456">如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="4b364-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="4b364-457">若要返回到报告报表视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="4b364-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="4b364-458">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="4b364-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="4b364-459">若要查看和使用本文中所述的报告，你需要是安全与合规中心内以下角色&之一：</span><span class="sxs-lookup"><span data-stu-id="4b364-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="4b364-460">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="4b364-460">**Organization Management**</span></span>
- <span data-ttu-id="4b364-461">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="4b364-461">**Security Administrator**</span></span>
- <span data-ttu-id="4b364-462">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="4b364-462">**Security Reader**</span></span>
- <span data-ttu-id="4b364-463">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="4b364-463">**Global Reader**</span></span>

<span data-ttu-id="4b364-464">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4b364-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4b364-465">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="4b364-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4b364-466">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4b364-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b364-467">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b364-467">Related topics</span></span>

[<span data-ttu-id="4b364-468">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="4b364-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="4b364-469">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="4b364-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="4b364-470">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="4b364-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="4b364-471">查看 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4b364-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
