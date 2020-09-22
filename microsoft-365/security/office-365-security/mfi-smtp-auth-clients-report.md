---
title: SMTP 身份验证客户端在邮件流仪表板中了解和报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规性中心中的邮件流仪表板中的 SMTP 身份验证了解和报告来监视组织中的电子邮件发件人，这些发件人使用经过身份验证的 SMTP (SMTP AUTH) 发送电子邮件。
ms.openlocfilehash: 7ca673e5ecc92c28996a976c26a38ae570f16203
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199237"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="9a9d8-103">SMTP 身份验证客户端在安全 & 合规中心中了解和报告</span><span class="sxs-lookup"><span data-stu-id="9a9d8-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9a9d8-104">**Smtp 身份验证客户端**在[邮件流仪表板](mail-flow-insights-v2.md)和关联的[SMTP auth 客户端](#smtp-auth-clients-report)之间的洞察力在[安全 & 合规性中心](https://protection.office.com)中突出显示了组织中的用户或系统帐户对 SMTP 身份验证客户端提交协议的使用。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="9a9d8-105">此旧版协议 (使用终结点 smtp.office365.com) 仅提供基本身份验证，并且容易被受攻击帐户用来发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="9a9d8-106">通过真知灼见和报告，可以检查 SMTP 身份验证电子邮件提交是否有异常活动。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="9a9d8-107">它还显示了使用 SMTP 身份验证的客户端或设备的 TLS 使用数据。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="9a9d8-108">该小部件指示最近7天内已使用 SMTP 身份验证协议的用户或服务帐户的数量。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Security & 合规性中心的邮件流仪表板中的 SMTP 身份验证客户端小部件](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="9a9d8-110">如果单击小组件上的邮件数，则将显示 **SMTP Auth 客户端** 弹出。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="9a9d8-111">浮出控件提供了上一周的 TLS 使用和卷的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![单击邮件流仪表板中的 "SMTP 身份验证客户端" 小部件后的详细信息浮出控件](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="9a9d8-113">您可以单击 " **Smtp auth 客户端报告** " 链接以转到 smtp auth 客户端报告，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="9a9d8-114">SMTP 身份验证客户端报告</span><span class="sxs-lookup"><span data-stu-id="9a9d8-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="9a9d8-115">SMTP Auth 客户端报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="9a9d8-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="9a9d8-116">默认情况下，此报告显示过去7天的数据，但数据可用于过去的90天。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="9a9d8-117">"概述" 部分包含以下图表：</span><span class="sxs-lookup"><span data-stu-id="9a9d8-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="9a9d8-118">**数据查看依据：发送卷**：默认情况下，图表显示从所有域发送的 SMTP 身份验证客户端邮件的数量 (显示其数据：默认情况下， **所有发件人域** 都处于选中状态) 。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="9a9d8-119">您可以通过单击下拉列表中的 " **显示数据** " 并选择 "发件人域"，将结果筛选为特定发件人域。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="9a9d8-120">如果将特定数据点悬停 (天) ，则显示邮件数。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![在 SMTP Auth 客户端的 "安全 & 合规中心" 报告中发送卷视图](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="9a9d8-122">**查看数据的依据： TLS 用法**：图表显示选定时间段内所有 SMTP 身份验证客户端邮件的 TLS 使用百分比。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="9a9d8-123">此图允许你识别仍在使用旧版 TLS 的用户和系统帐户，并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![SMTP Auth 客户端中的 TLS 使用情况视图报告中的安全性 & 合规性中心](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="9a9d8-125">如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9a9d8-126">单击 " **请求报告** " 可在电子邮件中接收更详细的报告版本。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="9a9d8-127">您可以指定日期范围和接收报告的收件人。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="9a9d8-128">SMTP Auth 客户端报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="9a9d8-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="9a9d8-129">如果您单击 " **查看详细信息表**"，则显示的信息将取决于所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="9a9d8-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9a9d8-130">**数据查看方式：发送卷**：表中显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="9a9d8-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="9a9d8-131">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="9a9d8-131">**Sender address**</span></span>
  - <span data-ttu-id="9a9d8-132">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="9a9d8-132">**Message count**</span></span>

  <span data-ttu-id="9a9d8-133">如果选择了行，则会在浮出控件中显示相同的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="9a9d8-134">**数据查看依据： TLS 用法**：表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="9a9d8-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="9a9d8-135">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="9a9d8-135">**Sender address**</span></span>
  - <span data-ttu-id="9a9d8-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9a9d8-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="9a9d8-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9a9d8-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="9a9d8-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9a9d8-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="9a9d8-139">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="9a9d8-139">**Message count**</span></span>

  <span data-ttu-id="9a9d8-140"><sup>\*</sup> 此列显示发件人的邮件的百分比和数量。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="9a9d8-141">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9a9d8-142">如果选择行，则在浮出控件中显示类似的详细信息：</span><span class="sxs-lookup"><span data-stu-id="9a9d8-142">If you select a row, similar details are shown in a flyout:</span></span>

![来自 SMTP Auth 客户端报告中的 TLS 使用状况视图的详细信息表中的详细信息的浮出控件](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="9a9d8-144">单击 " **请求报告** " 可在电子邮件中接收更详细的报告版本。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="9a9d8-145">您可以指定日期范围和接收报告的收件人。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="9a9d8-146">若要返回到 "报告" 视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a9d8-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="9a9d8-147">Related topics</span></span>

<span data-ttu-id="9a9d8-148">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="9a9d8-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
