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
description: 管理员可以了解安全与合规中心的"报告"仪表板中&报告。
ms.custom: ''
ms.openlocfilehash: 1ededf2d0d693c537c159c52d00deb03f278b4b2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659461"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="f3a24-103">在安全与合规中心的"报告"仪表板中查看&报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f3a24-104">除了安全与合规中心的邮件流仪表板中提供的邮件流[](mail-flow-insights-v2.md)报告外，报告仪表板中还提供了各种额外的邮件流报告，以帮助您监视 Microsoft 365 组织。 &</span><span class="sxs-lookup"><span data-stu-id="f3a24-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="f3a24-105">如果您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在安全与合规中心内查看这些报告&报告[](https://office.protection.com)仪表板 \> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="f3a24-106">若要直接转到报表仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全与合规中心&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="f3a24-108">连接器报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-108">Connector report</span></span>

<span data-ttu-id="f3a24-109">连接器 **报告显示** 为组织配置的 [入站](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 和出站连接器上的邮件流活动。</span><span class="sxs-lookup"><span data-stu-id="f3a24-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="f3a24-110">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，**转到"** 报告仪表板 \> "，然后选择 **"连接器报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="f3a24-111">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ConnectorReport> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

!["报表"仪表板中的"连接器报告"小部件](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="f3a24-113">连接器报表的报表视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-113">Report view for the Connector report</span></span>

<span data-ttu-id="f3a24-114">以下图表可用于报表视图：</span><span class="sxs-lookup"><span data-stu-id="f3a24-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="f3a24-115">**查看数据者：邮件流**：此图显示按以下方式组织的入站和出站邮件数：</span><span class="sxs-lookup"><span data-stu-id="f3a24-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="f3a24-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="f3a24-116">**Total**</span></span>
  - <span data-ttu-id="f3a24-117">**从 Internet（不含连接器）**</span><span class="sxs-lookup"><span data-stu-id="f3a24-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f3a24-118">**在没有连接器的情况下连接到 Internet**</span><span class="sxs-lookup"><span data-stu-id="f3a24-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f3a24-119">已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="f3a24-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="f3a24-120">若要隔离图表中的数据，请使用"显示数据 **"** 控件选择这些选项或"所有邮件 **流"之一**。</span><span class="sxs-lookup"><span data-stu-id="f3a24-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![在连接器报告中按邮件流查看数据](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="f3a24-122">**查看数据者：TLS 使用情况**：此图显示传输层安全性 (TLS) 邮件流版本使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="f3a24-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="f3a24-123">若要隔离图表中的数据，请使用"显示控件数据"选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="f3a24-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="f3a24-124">**所有邮件流**</span><span class="sxs-lookup"><span data-stu-id="f3a24-124">**All mail flow**</span></span>
  - <span data-ttu-id="f3a24-125">**从 Internet（不含连接器）**</span><span class="sxs-lookup"><span data-stu-id="f3a24-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f3a24-126">**在没有连接器的情况下连接到 Internet**</span><span class="sxs-lookup"><span data-stu-id="f3a24-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f3a24-127">已配置的特定连接器。</span><span class="sxs-lookup"><span data-stu-id="f3a24-127">A specific connector that you've configured.</span></span>

  ![在连接器报告中按 TLS 使用情况查看数据](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="f3a24-129">如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="f3a24-130">连接器报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-130">Details table view for the Connector report</span></span>

<span data-ttu-id="f3a24-131">如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f3a24-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f3a24-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3a24-132">**Date**</span></span>
- <span data-ttu-id="f3a24-133">**连接器方向和名称**</span><span class="sxs-lookup"><span data-stu-id="f3a24-133">**Connector direction and name**</span></span>
- <span data-ttu-id="f3a24-134">**连接器类型**</span><span class="sxs-lookup"><span data-stu-id="f3a24-134">**Connector type**</span></span>
- <span data-ttu-id="f3a24-135">**强制 TLS？：** 值 **True** 或 **False**。</span><span class="sxs-lookup"><span data-stu-id="f3a24-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="f3a24-136">**无 TLS** (百分比) </span><span class="sxs-lookup"><span data-stu-id="f3a24-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="f3a24-137">**TLS 1.0** (百分比) </span><span class="sxs-lookup"><span data-stu-id="f3a24-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="f3a24-138">**TLS 1.1** (百分比) </span><span class="sxs-lookup"><span data-stu-id="f3a24-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="f3a24-139">**TLS 1.2** (百分比) </span><span class="sxs-lookup"><span data-stu-id="f3a24-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="f3a24-140">**卷**：邮件数。</span><span class="sxs-lookup"><span data-stu-id="f3a24-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="f3a24-141">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f3a24-142">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f3a24-143">Exchange 传输规则报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-143">Exchange transport rule report</span></span>

<span data-ttu-id="f3a24-144">**Exchange 传输规则报告显示** 邮件流规则对 (传输规则) 传入和传出邮件的影响。</span><span class="sxs-lookup"><span data-stu-id="f3a24-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f3a24-145">若要查看报告，请打开安全与 [合规](https://protection.office.com)&，**转到"** 报告仪表板 \> "，然后选择 **"Exchange 传输规则"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="f3a24-146">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![报告仪表板中的 Exchange 传输规则小组件](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f3a24-148">Exchange 传输规则报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="f3a24-149">以下图表可用于报表视图：</span><span class="sxs-lookup"><span data-stu-id="f3a24-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="f3a24-150">**查看数据者：Exchange 传输规则** \>**按：方向：** 此图显示受传输规则影响的入站和出 **站** 邮件数。</span><span class="sxs-lookup"><span data-stu-id="f3a24-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="f3a24-151">**查看数据者：Exchange 传输规则** \>**按以下值进行分解：严重性**：此图表显示高 **严重性** 和中等严重性以及 **低严重性消息的数量**。</span><span class="sxs-lookup"><span data-stu-id="f3a24-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f3a24-152">将严重性级别设置为规则中的操作， (严重性级别或 _SetAuditSeverity_ 审核此) 。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f3a24-153">有关详细信息，请参阅 [Exchange Online 中的邮件流规则操作](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f3a24-154">**按：DLP Exchange 传输规则查看数据** \>**按：方向：** 此图显示受 DLP 传输规则中的数据丢失防护影响的入站和出站 () 数量。</span><span class="sxs-lookup"><span data-stu-id="f3a24-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="f3a24-155">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f3a24-156">**显示数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="f3a24-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f3a24-157">**显示其数据：遭到入侵的用户**</span><span class="sxs-lookup"><span data-stu-id="f3a24-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f3a24-158">**显示其数据：检测到的低量内容美国爱国者法案**</span><span class="sxs-lookup"><span data-stu-id="f3a24-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="f3a24-159">**按：DLP Exchange 传输规则查看数据** \>**按：方向**：此视图显示受 DLP 传输规则影响的高严重性和中等严重性和低严重性邮件的数量。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="f3a24-160">您可以通过选择以下选项来进一步优化图表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f3a24-161">**显示数据：所有 DLP 传输规则**</span><span class="sxs-lookup"><span data-stu-id="f3a24-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f3a24-162">**显示其数据：遭到入侵的用户**</span><span class="sxs-lookup"><span data-stu-id="f3a24-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f3a24-163">**显示其数据：检测到的低量内容美国爱国者法案**</span><span class="sxs-lookup"><span data-stu-id="f3a24-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="f3a24-164">如果 **单击筛选器** 报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="f3a24-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="f3a24-165">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="f3a24-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3a24-166">方向值</span><span class="sxs-lookup"><span data-stu-id="f3a24-166">Direction values</span></span>
- <span data-ttu-id="f3a24-167">严重性值</span><span class="sxs-lookup"><span data-stu-id="f3a24-167">Severity values</span></span>

![Exchange 传输规则报告中的报告视图](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f3a24-169">Exchange 传输规则报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="f3a24-170">如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f3a24-171">**查看数据方式：Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="f3a24-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3a24-172">**Date**</span></span>
  - <span data-ttu-id="f3a24-173">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="f3a24-173">**Transport rule**</span></span>
  - <span data-ttu-id="f3a24-174">**主题**</span><span class="sxs-lookup"><span data-stu-id="f3a24-174">**Subject**</span></span>
  - <span data-ttu-id="f3a24-175">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="f3a24-175">**Sender address**</span></span>
  - <span data-ttu-id="f3a24-176">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="f3a24-176">**Recipient address**</span></span>
  - <span data-ttu-id="f3a24-177">**严重性**</span><span class="sxs-lookup"><span data-stu-id="f3a24-177">**Severity**</span></span>
  - <span data-ttu-id="f3a24-178">**方向**</span><span class="sxs-lookup"><span data-stu-id="f3a24-178">**Direction**</span></span>

- <span data-ttu-id="f3a24-179">**查看数据方式：DLP Exchange 传输规则**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="f3a24-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3a24-180">**Date**</span></span>
  - <span data-ttu-id="f3a24-181">**DLP 策略**</span><span class="sxs-lookup"><span data-stu-id="f3a24-181">**DLP policy**</span></span>
  - <span data-ttu-id="f3a24-182">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="f3a24-182">**Transport rule**</span></span>
  - <span data-ttu-id="f3a24-183">**主题**</span><span class="sxs-lookup"><span data-stu-id="f3a24-183">**Subject**</span></span>
  - <span data-ttu-id="f3a24-184">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="f3a24-184">**Sender address**</span></span>
  - <span data-ttu-id="f3a24-185">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="f3a24-185">**Recipient address**</span></span>
  - <span data-ttu-id="f3a24-186">**严重性**</span><span class="sxs-lookup"><span data-stu-id="f3a24-186">**Severity**</span></span>
  - <span data-ttu-id="f3a24-187">**方向**</span><span class="sxs-lookup"><span data-stu-id="f3a24-187">**Direction**</span></span>

<span data-ttu-id="f3a24-188">如果在 **详细信息表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="f3a24-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f3a24-189">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="f3a24-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3a24-190">方向值</span><span class="sxs-lookup"><span data-stu-id="f3a24-190">Direction values</span></span>
- <span data-ttu-id="f3a24-191">严重性值</span><span class="sxs-lookup"><span data-stu-id="f3a24-191">Severity values</span></span>

<span data-ttu-id="f3a24-192">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f3a24-193">转发报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-193">Forwarding report</span></span>

<span data-ttu-id="f3a24-194">转发 **报告显示** 组织从 Exchange Online 邮箱自动转发到外部域的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="f3a24-195">转发的邮件可能会带来安全或合规性风险，并可能指示帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="f3a24-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="f3a24-196">若要查看报告，请打开安全&[合规](https://protection.office.com)中心 **，转到"** 报告仪表板"， \> **然后选择"转发报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="f3a24-197">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=MailFlowForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

!["报告"仪表板中的"转发报告"小部件](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="f3a24-199">转发报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="f3a24-200">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="f3a24-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f3a24-201">**显示以下方法的数据：转发** 方法：显示以下方法：</span><span class="sxs-lookup"><span data-stu-id="f3a24-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="f3a24-202">**传输规则**：也称为 [邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="f3a24-203">**邮箱规则**：也称为 [收件箱规则](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![转发报告中的转发方法视图](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="f3a24-205">**显示其数据：转发域**：此视图显示作为转发目标收件人域。</span><span class="sxs-lookup"><span data-stu-id="f3a24-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![转发报告中的转发域视图](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="f3a24-207">**显示其数据：转发器**：显示以下转发器：</span><span class="sxs-lookup"><span data-stu-id="f3a24-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="f3a24-208">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="f3a24-208">**Transport rule**</span></span>
  - <span data-ttu-id="f3a24-209">包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f3a24-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![转发报告中的转发器视图](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="f3a24-211">如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="f3a24-212">转发报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="f3a24-213">如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f3a24-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f3a24-214">**转发器**：值 **传输规则** 或包含转发收件箱规则的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f3a24-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="f3a24-215">**转发类型**：值 **邮箱规则** 或 **传输规则**。</span><span class="sxs-lookup"><span data-stu-id="f3a24-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="f3a24-216">**收件人名称**</span><span class="sxs-lookup"><span data-stu-id="f3a24-216">**Recipient name**</span></span>
- <span data-ttu-id="f3a24-217">**收件人域**</span><span class="sxs-lookup"><span data-stu-id="f3a24-217">**Recipient domain**</span></span>
- <span data-ttu-id="f3a24-218">**详细信息**：这是邮件流规则的 GUID 值，或收件箱规则的 RuleIdentity 值。</span><span class="sxs-lookup"><span data-stu-id="f3a24-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="f3a24-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3a24-219">**Count**</span></span>
- <span data-ttu-id="f3a24-220">**第一个转发日期**</span><span class="sxs-lookup"><span data-stu-id="f3a24-220">**First forward date**</span></span>

<span data-ttu-id="f3a24-221">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f3a24-222">若要返回到报告视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f3a24-223">邮件流状态报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-223">Mailflow status report</span></span>

<span data-ttu-id="f3a24-224">邮件 **流状态报告** 类似于"已发送和 [](#sent-and-received-email-report)已接收电子邮件"报告，包含有关边缘上允许或阻止的电子邮件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f3a24-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f3a24-225">这是包含边缘保护信息的唯一报告，其中只显示 Exchange Online Protection (EOP) 允许进入服务之前阻止的电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f3a24-226">必须了解，如果邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="f3a24-227">若要查看报告，请打开安全&合规中心 **，转到"** 报告 [仪表板](https://protection.office.com) \> "，然后选择 **"邮件流状态报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="f3a24-228">若要直接转到邮件 **流状态报告，** 请打开 <https://protection.office.com/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

!["报告"仪表板中的"邮件流状态报告"小部件](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3a24-230">邮件流状态报告的类型视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="f3a24-231">打开报表时，默认情况下会选中"类型"选项卡。</span><span class="sxs-lookup"><span data-stu-id="f3a24-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f3a24-232">默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f3a24-233">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="f3a24-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="f3a24-234">**方向**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-234">**Direction**:</span></span>

  - <span data-ttu-id="f3a24-235">**入站**</span><span class="sxs-lookup"><span data-stu-id="f3a24-235">**Inbound**</span></span>
  - <span data-ttu-id="f3a24-236">**出站**</span><span class="sxs-lookup"><span data-stu-id="f3a24-236">**Outbound**</span></span>
  - <span data-ttu-id="f3a24-237">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="f3a24-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f3a24-238">发件人abc@domain.com收件人的邮件xyz@domain.com (与入站和出站邮件分开 **计数)** </span><span class="sxs-lookup"><span data-stu-id="f3a24-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="f3a24-239">**类型**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-239">**Type**:</span></span>

  - <span data-ttu-id="f3a24-240">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-240">**Good mail**</span></span>
  - <span data-ttu-id="f3a24-241">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-241">**Malware**</span></span>
  - <span data-ttu-id="f3a24-242">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-242">**Spam**</span></span>
  - <span data-ttu-id="f3a24-243">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="f3a24-243">**Edge protection**</span></span>
  - <span data-ttu-id="f3a24-244">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-244">**Rule messages**</span></span>
  - <span data-ttu-id="f3a24-245">**钓鱼电子邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-245">**Phishing email**</span></span>

<span data-ttu-id="f3a24-246">图表按 **类型值组织** 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f3a24-247">可以通过单击" **筛选器"或** 单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="f3a24-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="f3a24-248">该数据表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="f3a24-248">The data table contains the following information:</span></span>

- <span data-ttu-id="f3a24-249">**方向**</span><span class="sxs-lookup"><span data-stu-id="f3a24-249">**Direction**</span></span>
- <span data-ttu-id="f3a24-250">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3a24-250">**Type**</span></span>
- <span data-ttu-id="f3a24-251">**24 小时**</span><span class="sxs-lookup"><span data-stu-id="f3a24-251">**24 hours**</span></span>
- <span data-ttu-id="f3a24-252">**3 天**</span><span class="sxs-lookup"><span data-stu-id="f3a24-252">**3 days**</span></span>
- <span data-ttu-id="f3a24-253">**7 天**</span><span class="sxs-lookup"><span data-stu-id="f3a24-253">**7 days**</span></span>
- <span data-ttu-id="f3a24-254">**15 天**</span><span class="sxs-lookup"><span data-stu-id="f3a24-254">**15 days**</span></span>
- <span data-ttu-id="f3a24-255">**30 天**</span><span class="sxs-lookup"><span data-stu-id="f3a24-255">**30 days**</span></span>

<span data-ttu-id="f3a24-256">If you click **Choose a category for more details，** you can select from the following values：</span><span class="sxs-lookup"><span data-stu-id="f3a24-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f3a24-257">**网络钓鱼电子邮件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f3a24-258">**电子邮件中的恶意软件**：此选择将你带至 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f3a24-259">**垃圾邮件检测**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f3a24-260">**边缘阻止的垃圾邮件**：此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f3a24-261">**导出**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-261">**Export**:</span></span>

<span data-ttu-id="f3a24-262">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="f3a24-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f3a24-263">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="f3a24-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f3a24-264">每个导出的 .csv 文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="f3a24-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3a24-265">如果当天的数据包含超过 150，000 行，将创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f3a24-266">邮件流状态报告中的类型视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3a24-267">邮件流状态报告的方向视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="f3a24-268">如果单击" **方向"** 选项卡，则使用"类型"视图中 **的相同** 默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="f3a24-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f3a24-269">图表按方向 **值** 组织。</span><span class="sxs-lookup"><span data-stu-id="f3a24-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f3a24-270">可以通过单击" **筛选器"或** 单击图表图例中的值来更改这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="f3a24-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="f3a24-271">使用"类型"视图中 **的** 相同筛选器。</span><span class="sxs-lookup"><span data-stu-id="f3a24-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f3a24-272">该数据表包含来自"类型"视图 **的相同** 信息。</span><span class="sxs-lookup"><span data-stu-id="f3a24-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f3a24-273">" **选择一个类别"，** 了解更多详细信息可用的选择和行为与"类型" **视图** 相同。</span><span class="sxs-lookup"><span data-stu-id="f3a24-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="f3a24-274">**导出**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-274">**Export**:</span></span>

<span data-ttu-id="f3a24-275">对于详细信息视图，只能导出一天的数据。</span><span class="sxs-lookup"><span data-stu-id="f3a24-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f3a24-276">因此，如果要导出 7 天的数据，需要执行 7 种不同的导出操作。</span><span class="sxs-lookup"><span data-stu-id="f3a24-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f3a24-277">每个导出的 .csv 文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="f3a24-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3a24-278">如果当天的数据包含超过 150，000 行，将创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="f3a24-279">邮件流状态报告中的方向视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3a24-280">邮件流状态报告的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="f3a24-281">漏 **斗** 视图显示 Microsoft 的电子邮件威胁防护功能如何筛选组织中传入和传出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="f3a24-282">它提供有关电子邮件总数以及配置的威胁防护功能（包括边缘保护、反恶意软件、反网络钓鱼、反垃圾邮件和反欺骗）如何影响此计数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3a24-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="f3a24-283">默认情况下，如果单击 **"漏斗** "选项卡，则此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f3a24-284">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="f3a24-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f3a24-285">**方向**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-285">**Direction**:</span></span>

  - <span data-ttu-id="f3a24-286">**入站**</span><span class="sxs-lookup"><span data-stu-id="f3a24-286">**Inbound**</span></span>
  - <span data-ttu-id="f3a24-287">**出站**</span><span class="sxs-lookup"><span data-stu-id="f3a24-287">**Outbound**</span></span>
  - <span data-ttu-id="f3a24-288">**组织内部**：此计数用于租户内发送的邮件;即，发件人abc@domain.com收件人的邮件xyz@domain.com (与入站和出站邮件分开) 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="f3a24-289">聚合视图和数据表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="f3a24-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f3a24-290">如果单击 **"筛选**"，可以同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="f3a24-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f3a24-291">此图表显示按以下方式组织的电子邮件计数：</span><span class="sxs-lookup"><span data-stu-id="f3a24-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="f3a24-292">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="f3a24-292">**Total email**</span></span>
- <span data-ttu-id="f3a24-293">**边缘保护后的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-293">**Email after edge protection**</span></span>
- <span data-ttu-id="f3a24-294">**反恶意软件后的电子邮件， 文件信誉， 文件类型阻止**</span><span class="sxs-lookup"><span data-stu-id="f3a24-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f3a24-295">**反网络钓鱼后的电子邮件， URL 信誉， 品牌模拟， 反欺骗**</span><span class="sxs-lookup"><span data-stu-id="f3a24-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f3a24-296">**反垃圾邮件后的电子邮件，批量邮件筛选**</span><span class="sxs-lookup"><span data-stu-id="f3a24-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f3a24-297">**用户和域模拟**<sup>1</sup>之后的电子邮件</span><span class="sxs-lookup"><span data-stu-id="f3a24-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="f3a24-298">**文件和 URL 触发**<sup>后的电子邮件 1</sup></span><span class="sxs-lookup"><span data-stu-id="f3a24-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="f3a24-299">**在传递后保护或 URL 单击时间保护 (电子邮件被检测为)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="f3a24-300"><sup>仅 1</sup> 个 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f3a24-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="f3a24-301">若要查看由 EOP 或 Defender for Office 365 单独筛选的电子邮件，请单击图表图例中的值。</span><span class="sxs-lookup"><span data-stu-id="f3a24-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="f3a24-302">该数据表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="f3a24-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f3a24-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3a24-303">**Date**</span></span>
- <span data-ttu-id="f3a24-304">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="f3a24-304">**Total email**</span></span>
- <span data-ttu-id="f3a24-305">**边缘保护**</span><span class="sxs-lookup"><span data-stu-id="f3a24-305">**Edge protection**</span></span>
- <span data-ttu-id="f3a24-306">**反恶意软件， 文件信誉， 文件类型阻止**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="f3a24-307">**文件信誉**：由于其他 Microsoft 客户标识附加文件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="f3a24-308">**文件类型阻止**：由于邮件中标识的恶意文件类型而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f3a24-309">**反网络钓鱼， URL 信誉， 品牌模拟， 反欺骗**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="f3a24-310">**URL 信誉**：由于其他 Microsoft 客户标识的 URL 而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="f3a24-311">**品牌模拟**：由于邮件来自已知品牌模拟发件人而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="f3a24-312">**反欺骗**：由于邮件试图欺骗收件人所属的域或邮件发件人没有的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="f3a24-313">**反垃圾邮件，批量邮件筛选**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="f3a24-314">**批量邮件筛选**：由于尝试向收件人传递批量邮件而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="f3a24-315">**适用于 Office 365 (Defender 的用户和) ：**</span><span class="sxs-lookup"><span data-stu-id="f3a24-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f3a24-316">用户模拟：由于尝试模拟用户 (邮件发件人) 在防钓鱼策略的模拟保护设置中定义的邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="f3a24-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="f3a24-317">**域模拟**：由于尝试模拟在防钓鱼策略的模拟保护设置中定义的域而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="f3a24-318">**Office 365 (Defender 的文件和 URL) ：**</span><span class="sxs-lookup"><span data-stu-id="f3a24-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f3a24-319">**文件触发**：由安全附件策略筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="f3a24-320">**URL 触发**：按安全链接策略筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="f3a24-321">**传递后保护和 ZAP (ATP) 或 ZAP (EOP)**：ZAP 指示零时差自动清除。</span><span class="sxs-lookup"><span data-stu-id="f3a24-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="f3a24-322">如果在数据表中选择一行，则电子邮件计数的进一步细分将显示在该飞出中。</span><span class="sxs-lookup"><span data-stu-id="f3a24-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f3a24-323">**导出**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-323">**Export**:</span></span>

<span data-ttu-id="f3a24-324">单击"选项 **"** 下的 **"** 导出"后，可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="f3a24-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="f3a24-325">**最多 (最近 90 天的数据摘要)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f3a24-326">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f3a24-327">在 **"日期**"下，选择一个范围，然后单击"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f3a24-328">当前筛选器的数据将导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f3a24-329">每个导出的 .csv 文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="f3a24-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3a24-330">如果数据包含超过 150，000 行，将创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="f3a24-331">邮件流状态报告中的漏斗视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="f3a24-332">邮件流状态报告的技术视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="f3a24-333">" **技术"** 视图类似于漏 **斗视图** ，为配置的威胁防护功能提供更精细的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3a24-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="f3a24-334">从图中，你可以看到如何在威胁防护的不同阶段对邮件进行分类。</span><span class="sxs-lookup"><span data-stu-id="f3a24-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="f3a24-335">如果单击 **"技术视图** "选项卡，则默认情况下，此视图包含一个图表和一个使用以下筛选器配置的数据表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f3a24-336">**日期**：最近 7 天。</span><span class="sxs-lookup"><span data-stu-id="f3a24-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f3a24-337">**方向**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-337">**Direction**:</span></span>

  - <span data-ttu-id="f3a24-338">**入站**</span><span class="sxs-lookup"><span data-stu-id="f3a24-338">**Inbound**</span></span>
  - <span data-ttu-id="f3a24-339">**出站**</span><span class="sxs-lookup"><span data-stu-id="f3a24-339">**Outbound**</span></span>
  - <span data-ttu-id="f3a24-340">**组织内部**：此计数用于租户内的邮件，即</span><span class="sxs-lookup"><span data-stu-id="f3a24-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f3a24-341">发件人abc@domain.com收件人的邮件xyz@domain.com (与入站和出站邮件分开计数) </span><span class="sxs-lookup"><span data-stu-id="f3a24-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="f3a24-342">聚合视图和数据表视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="f3a24-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f3a24-343">如果单击 **"筛选**"，可以同时筛选图表和数据表。</span><span class="sxs-lookup"><span data-stu-id="f3a24-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f3a24-344">此图表显示按以下类别组织的消息：</span><span class="sxs-lookup"><span data-stu-id="f3a24-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f3a24-345">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="f3a24-345">**Total email**</span></span>
- <span data-ttu-id="f3a24-346">**边缘允许** 和 **边缘筛选**</span><span class="sxs-lookup"><span data-stu-id="f3a24-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="f3a24-347">**非恶意软件**、**安全附件检测** <sup>\*</sup> 、**反恶意软件引擎检测和\*\*\*\*规则邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="f3a24-348">**非网络钓鱼\*\*\*\*、DMARC** 故障 **、模拟检测\*\*\*\*、欺骗检测和\*\*\*\*网络钓鱼检测**</span><span class="sxs-lookup"><span data-stu-id="f3a24-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="f3a24-349">**未检测 URL 触发和** **URL 触发检测**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f3a24-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f3a24-350">**不是垃圾邮件** 和  **垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="f3a24-351">**非恶意电子邮件**、**安全链接检测和** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="f3a24-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="f3a24-352"><sup>\*</sup> Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f3a24-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f3a24-353">将鼠标悬停在图表中的类别上时，可以看到该类别中的消息数。</span><span class="sxs-lookup"><span data-stu-id="f3a24-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="f3a24-354">该数据表包含以下信息，按降序日期顺序显示：</span><span class="sxs-lookup"><span data-stu-id="f3a24-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f3a24-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="f3a24-355">**Date**</span></span>
- <span data-ttu-id="f3a24-356">**电子邮件总数**</span><span class="sxs-lookup"><span data-stu-id="f3a24-356">**Total email**</span></span>
- <span data-ttu-id="f3a24-357">**已筛选边缘**</span><span class="sxs-lookup"><span data-stu-id="f3a24-357">**Edge filtered**</span></span>
- <span data-ttu-id="f3a24-358">**反恶意软件引擎，安全附件，已筛选规则**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="f3a24-359">**已筛选规则**：由于邮件流规则而筛选 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="f3a24-360">**DMARC， 模拟， 欺骗， 网络钓鱼筛选**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="f3a24-361">**DMARC：** 由于邮件未通过 DMARC 身份验证检查而筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="f3a24-362">**URL 触发检测**</span><span class="sxs-lookup"><span data-stu-id="f3a24-362">**URL detonation detection**</span></span>
- <span data-ttu-id="f3a24-363">**经过筛选的反垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="f3a24-364">**ZAP 已删除**</span><span class="sxs-lookup"><span data-stu-id="f3a24-364">**ZAP removed**</span></span>
- <span data-ttu-id="f3a24-365">**通过安全链接检测**</span><span class="sxs-lookup"><span data-stu-id="f3a24-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="f3a24-366">如果在数据表中选择一行，则电子邮件计数的进一步细分将显示在该飞出中。</span><span class="sxs-lookup"><span data-stu-id="f3a24-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f3a24-367">**导出**：</span><span class="sxs-lookup"><span data-stu-id="f3a24-367">**Export**:</span></span>

<span data-ttu-id="f3a24-368">单击"**导出"，\*\*\*\*在"** 选项"下可以选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="f3a24-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="f3a24-369">**最多 (最近 90 天的数据摘要)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f3a24-370">**有关 (最近 30 天的数据的详细信息)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f3a24-371">在 **"日期**"下，选择一个范围，然后单击"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f3a24-372">当前筛选器的数据将导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f3a24-373">每个导出的 .csv 文件限制为 150，000 行。</span><span class="sxs-lookup"><span data-stu-id="f3a24-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f3a24-374">如果数据包含超过 150，000 行，将创建多个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="f3a24-375">邮件流状态报告中的技术视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="f3a24-376">已发送和已接收电子邮件报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-376">Sent and received email report</span></span>

<span data-ttu-id="f3a24-377">" **已发送和已** 接收电子邮件"报告是一个智能报告，可显示有关传入和传出电子邮件的信息，包括垃圾邮件检测、恶意软件和标识为"良好"的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="f3a24-378">此报告与邮件流状态报告[](#mailflow-status-report)之间的区别在于：此报告不包含有关受边缘保护阻止的邮件的数据。必须了解，如果邮件发送给五个收件人，我们会将邮件计为一封邮件。</span><span class="sxs-lookup"><span data-stu-id="f3a24-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="f3a24-379">聚合视图和报表的详细信息视图允许筛选 90 天。</span><span class="sxs-lookup"><span data-stu-id="f3a24-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="f3a24-380">若要查看报告，请打开安全&合规中心，转到"报告 [仪表板](https://protection.office.com) \> "，然后选择"已发送 **和已接收电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="f3a24-381">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

!["报告"仪表板中的"已发送和已接收电子邮件"小部件](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f3a24-383">已发送和已接收电子邮件报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="f3a24-384">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="f3a24-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f3a24-385">**分类：类型**：图表显示所有可用类别：</span><span class="sxs-lookup"><span data-stu-id="f3a24-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="f3a24-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="f3a24-386">**Total**</span></span>
  - <span data-ttu-id="f3a24-387">**良好的邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-387">**Good mail**</span></span>
  - <span data-ttu-id="f3a24-388">**EOP (恶意软件)  (** 恶意软件) </span><span class="sxs-lookup"><span data-stu-id="f3a24-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="f3a24-389">**垃圾邮件检测**</span><span class="sxs-lookup"><span data-stu-id="f3a24-389">**Spam detections**</span></span>
  - <span data-ttu-id="f3a24-390">**规则邮件**</span><span class="sxs-lookup"><span data-stu-id="f3a24-390">**Rule messages**</span></span>
  - <span data-ttu-id="f3a24-391">**Microsoft Defender** (Office 365 高级恶意软件) </span><span class="sxs-lookup"><span data-stu-id="f3a24-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="f3a24-392">当您将鼠标悬停在 (的数据) 上时，可以看到当天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3a24-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  !["已发送和已接收电子邮件"报告中的类型视图](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="f3a24-394">**按：方向：** 图表显示 **总计\*\*\*\*、入站** 和 **出站** 数据。</span><span class="sxs-lookup"><span data-stu-id="f3a24-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="f3a24-395">当您将鼠标悬停在 (的数据) 上时，可以看到当天的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f3a24-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![已发送和已接收电子邮件报告中的方向视图](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="f3a24-397">**向下钻取** \>**恶意软件 (反恶意软件) ：** 此选择将你带至电子邮件 [报告中的恶意软件检测](view-email-security-reports.md#malware-detections-in-email-report)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="f3a24-398">**向下钻取** \>**垃圾邮件检测) ：** 此选择将你带至 [垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f3a24-399">如果 **单击筛选器** 报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="f3a24-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f3a24-400">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="f3a24-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3a24-401">方向值</span><span class="sxs-lookup"><span data-stu-id="f3a24-401">Direction values</span></span>
- <span data-ttu-id="f3a24-402">类型值</span><span class="sxs-lookup"><span data-stu-id="f3a24-402">Type values</span></span>

<span data-ttu-id="f3a24-403">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f3a24-404">"已发送和已接收电子邮件"报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="f3a24-405">如果在"中断者：方向或分解 **者：** 方向"视图中单击"查看详细信息"表，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f3a24-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="f3a24-406">**UTC (日期)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-406">**Date (UTC)**</span></span>
- <span data-ttu-id="f3a24-407">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3a24-407">**Type**</span></span>
- <span data-ttu-id="f3a24-408">**方向**</span><span class="sxs-lookup"><span data-stu-id="f3a24-408">**Direction**</span></span>
- <span data-ttu-id="f3a24-409">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="f3a24-409">**Message count**</span></span>

<span data-ttu-id="f3a24-410">如果在 **详细信息表** 视图中单击"筛选器"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="f3a24-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f3a24-411">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="f3a24-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="f3a24-412">方向值</span><span class="sxs-lookup"><span data-stu-id="f3a24-412">Direction values</span></span>
- <span data-ttu-id="f3a24-413">类型值</span><span class="sxs-lookup"><span data-stu-id="f3a24-413">Type values</span></span>

<span data-ttu-id="f3a24-414">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="f3a24-415">首要发件人和收件人报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-415">Top senders and recipients report</span></span>

<span data-ttu-id="f3a24-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span><span class="sxs-lookup"><span data-stu-id="f3a24-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="f3a24-417">若要查看报告，请打开安全&合规中心，转到"报告 [仪表板](https://protection.office.com)"，然后选择"顶级 \> **发件人和收件人"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="f3a24-418">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> 。</span><span class="sxs-lookup"><span data-stu-id="f3a24-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

!["报告"仪表板中的"首要发件人和收件人"小组件](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f3a24-420">顶级发件人和收件人报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="f3a24-421">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="f3a24-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f3a24-422">**显示热门 \> 邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="f3a24-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="f3a24-423">**显示热门 \> 邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="f3a24-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="f3a24-424">**显示热门 \> 垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="f3a24-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="f3a24-425">**显示其数据 \> EOP 邮件** (恶意软件) </span><span class="sxs-lookup"><span data-stu-id="f3a24-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="f3a24-426">**显示适用于 \> Office 365 (Defender 的顶级恶意软件)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="f3a24-427">复合饼图将基于这些选择进行更改。</span><span class="sxs-lookup"><span data-stu-id="f3a24-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="f3a24-428">当您将鼠标悬停在饼图中的一个上方时，可以看到已发送或已接收邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="f3a24-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="f3a24-429">如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![顶部发件人和收件人报告中报告视图中的饼图](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f3a24-431">顶级发件人和收件人报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="f3a24-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="f3a24-432">如果单击 **"查看详细信息"表**，则显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="f3a24-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f3a24-433">**显示热门 \> 邮件发件人的数据**</span><span class="sxs-lookup"><span data-stu-id="f3a24-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="f3a24-434">**热门邮件发件人**</span><span class="sxs-lookup"><span data-stu-id="f3a24-434">**Top mail senders**</span></span>
  - <span data-ttu-id="f3a24-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3a24-435">**Count**</span></span>

- <span data-ttu-id="f3a24-436">**显示热门 \> 邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="f3a24-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="f3a24-437">**热门邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="f3a24-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="f3a24-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3a24-438">**Count**</span></span>

- <span data-ttu-id="f3a24-439">**显示热门 \> 垃圾邮件收件人的数据**</span><span class="sxs-lookup"><span data-stu-id="f3a24-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="f3a24-440">**热门垃圾邮件收件人**</span><span class="sxs-lookup"><span data-stu-id="f3a24-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="f3a24-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3a24-441">**Count**</span></span>

- <span data-ttu-id="f3a24-442">**显示其数据 \> EOP 邮件** (恶意软件) </span><span class="sxs-lookup"><span data-stu-id="f3a24-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="f3a24-443">**首要恶意软件收件人**</span><span class="sxs-lookup"><span data-stu-id="f3a24-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="f3a24-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3a24-444">**Count**</span></span>

- <span data-ttu-id="f3a24-445">**显示适用于 \> Office 365 (Defender 的顶级恶意软件)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="f3a24-446">**Office 365 (Defender 中恶意软件)**</span><span class="sxs-lookup"><span data-stu-id="f3a24-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="f3a24-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="f3a24-447">**Count**</span></span>

<span data-ttu-id="f3a24-448">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="f3a24-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f3a24-449">若要返回到该报表视图，请单击 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="f3a24-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f3a24-450">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="f3a24-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f3a24-451">若要查看和使用本文中所述的报告，您需要是安全与合规中心内以下角色组之&的成员：</span><span class="sxs-lookup"><span data-stu-id="f3a24-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f3a24-452">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="f3a24-452">**Organization Management**</span></span>
- <span data-ttu-id="f3a24-453">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="f3a24-453">**Security Administrator**</span></span>
- <span data-ttu-id="f3a24-454">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="f3a24-454">**Security Reader**</span></span>
- <span data-ttu-id="f3a24-455">**全局阅读器**</span><span class="sxs-lookup"><span data-stu-id="f3a24-455">**Global Reader**</span></span>

<span data-ttu-id="f3a24-456">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f3a24-457">注意：将用户添加到 Microsoft 36 & 5 管理中心的相应 Azure Active Directory 角色会为用户提供安全与合规中心所需的权限和 Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="f3a24-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f3a24-458">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="f3a24-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3a24-459">相关主题</span><span class="sxs-lookup"><span data-stu-id="f3a24-459">Related topics</span></span>

[<span data-ttu-id="f3a24-460">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="f3a24-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f3a24-461">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="f3a24-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="f3a24-462">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f3a24-463">查看 Microsoft Defender for Office 365 报告</span><span class="sxs-lookup"><span data-stu-id="f3a24-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
