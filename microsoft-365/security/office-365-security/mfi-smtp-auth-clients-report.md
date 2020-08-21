---
title: 邮件流仪表板中的 SMTP 身份验证客户端见解和报告
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
description: 管理员可了解如何使用安全 & 合规中心的邮件流仪表板中的 SMTP 身份验证见解和报告，以监视组织中使用经身份验证的 SMTP (SMTP AUTH) 发送电子邮件的电子邮件发件人。
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826865"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="79bbb-103">安全与合规中心内的 SMTP 身份验证&见解和报告</span><span class="sxs-lookup"><span data-stu-id="79bbb-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="79bbb-104">"**邮件流"仪表板和**关联的[SMTP](#smtp-auth-clients-report) [身份验证](mail-flow-insights-v2.md)客户端报告重点说明了组织中用户或系统帐户使用 SMTP AUTH 客户端提交协议。</span><span class="sxs-lookup"><span data-stu-id="79bbb-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="79bbb-105">此传 (它仅使用端点smtp.office365.com) 仅提供基本身份验证，并容被入入入被入入以供入入用来发送电子邮件的协议。</span><span class="sxs-lookup"><span data-stu-id="79bbb-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="79bbb-106">通过见解和报告，可以检查 SMTP AUTH 电子邮件提交是否有异常活动。</span><span class="sxs-lookup"><span data-stu-id="79bbb-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="79bbb-107">该示例还显示使用 SMTP AUTH 的客户端或设备的 TLS 使用率数据。</span><span class="sxs-lookup"><span data-stu-id="79bbb-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="79bbb-108">小部件指示过去 7 天内使用 SMTP 身份验证协议的用户或服务帐户的数量。</span><span class="sxs-lookup"><span data-stu-id="79bbb-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

!["安全组合规中心"的"邮件流"仪表板中的"SMTP &小部件"](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="79bbb-110">如果您单击小部件上的邮件数量，则会 **出现一个 SMTP 身份验证客户端** 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="79bbb-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="79bbb-111">浮出控件提供上周 TLS 用法和卷的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="79bbb-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![在"邮件流"仪表板中单击"SMTP 身份验证客户端"小部件后的详细信息浮出控件](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="79bbb-113">可以单击 **SMTP 身份验证客户端报告** 链接转到 SMTP 身份验证客户端报告，如下一节所述。</span><span class="sxs-lookup"><span data-stu-id="79bbb-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="79bbb-114">SMTP 身份验证客户端报告</span><span class="sxs-lookup"><span data-stu-id="79bbb-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="79bbb-115">SMTP 身份验证客户端报表的报告视图</span><span class="sxs-lookup"><span data-stu-id="79bbb-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="79bbb-116">默认情况下，报告显示最近 7 天的数据，但数据在最近 90 天内可用。</span><span class="sxs-lookup"><span data-stu-id="79bbb-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="79bbb-117">"概述"部分包含以下图表：</span><span class="sxs-lookup"><span data-stu-id="79bbb-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="79bbb-118">**查看数据：发送方**：默认情况下，图表显示从所有域发送的 SMTP 身份验证客户端消息 (**显示所有发件人域** 的 SMTP 身份验证客户端消息 (显示所有发件人域在默认情况下) 。</span><span class="sxs-lookup"><span data-stu-id="79bbb-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="79bbb-119">可通过单击"从下拉列表中显示发件人 **域"** 并从下拉列表中选择发件人域，将结果筛选为特定发件人域。</span><span class="sxs-lookup"><span data-stu-id="79bbb-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="79bbb-120">如果您将特定数据点分段并 (数据) ，会显示消息数。</span><span class="sxs-lookup"><span data-stu-id="79bbb-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![安全与合规中心内"安全"报告中的"SMTP 验证&视图](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="79bbb-122">**查看数据：TLS 用法**：图表显示所选时间段内所有 SMTP 身份验证客户端消息的 TLS 使用情况百分比。</span><span class="sxs-lookup"><span data-stu-id="79bbb-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="79bbb-123">此图允许你识别仍在使用较旧版本的 TLS 的用户和系统帐户并对它们采取操作。</span><span class="sxs-lookup"><span data-stu-id="79bbb-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![安全 & 合规中心内 SMTP 身份验证客户端报告中的 TLS 使用情况视图](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="79bbb-125">如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="79bbb-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="79bbb-126">单击 **"请求** "报告可在电子邮件中收到报告的更详细版本。</span><span class="sxs-lookup"><span data-stu-id="79bbb-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="79bbb-127">您可以指定日期范围和收件人来接收报告。</span><span class="sxs-lookup"><span data-stu-id="79bbb-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="79bbb-128">SMTP 身份验证客户端报表的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="79bbb-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="79bbb-129">如果您单击 **"查看详细信息**表"，显示的信息取决于正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="79bbb-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="79bbb-130">**通过以下方式查看数据**：发送卷：下表中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="79bbb-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="79bbb-131">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="79bbb-131">**Sender address**</span></span>
  - <span data-ttu-id="79bbb-132">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="79bbb-132">**Message count**</span></span>

  <span data-ttu-id="79bbb-133">如果选择一行，则在浮出控件中显示相同详细信息。</span><span class="sxs-lookup"><span data-stu-id="79bbb-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="79bbb-134">**通过以下方式查看数据**：TLS 用法：以下信息显示在表中：</span><span class="sxs-lookup"><span data-stu-id="79bbb-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="79bbb-135">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="79bbb-135">**Sender address**</span></span>
  - <span data-ttu-id="79bbb-136">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="79bbb-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="79bbb-137">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="79bbb-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="79bbb-138">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="79bbb-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="79bbb-139">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="79bbb-139">**Message count**</span></span>

  <span data-ttu-id="79bbb-140"><sup>\*</sup> 此列显示来自发件人的邮件的百分比和数量。</span><span class="sxs-lookup"><span data-stu-id="79bbb-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="79bbb-141">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="79bbb-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="79bbb-142">如果选择行，类似的详细信息会显示在浮出控件中：</span><span class="sxs-lookup"><span data-stu-id="79bbb-142">If you select a row, similar details are shown in a flyout:</span></span>

![从 SMTP 身份验证客户端报告中 TLS 使用状况视图的详细信息表明天](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="79bbb-144">单击 **"请求** "报告可在电子邮件中收到报告的更详细版本。</span><span class="sxs-lookup"><span data-stu-id="79bbb-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="79bbb-145">您可以指定日期范围和收件人来接收报告。</span><span class="sxs-lookup"><span data-stu-id="79bbb-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="79bbb-146">若要返回报告视图，请单击"查看**报告"。**</span><span class="sxs-lookup"><span data-stu-id="79bbb-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="79bbb-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="79bbb-147">Related topics</span></span>

<span data-ttu-id="79bbb-148">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="79bbb-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
