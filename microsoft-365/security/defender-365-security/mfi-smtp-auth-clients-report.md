---
title: 邮件流仪表板中的 SMTP 身份验证客户端见解和报表
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的 SMTP 身份验证见解和报表来监视组织中使用已验证的 SMTP (SMTP AUTH) 发送电子邮件的电子邮件发件人。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054887"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="94064-103">安全与合规中心中的 SMTP 身份验证客户端见解&报告</span><span class="sxs-lookup"><span data-stu-id="94064-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94064-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="94064-104">**Applies to**</span></span>
- [<span data-ttu-id="94064-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="94064-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94064-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="94064-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94064-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94064-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="94064-108">安全 & 合规中心中的"[](mail-flow-insights-v2.md)邮件流"仪表板中的 **SMTP** 身份验证客户端见解和关联的 [SMTP](#smtp-auth-clients-report) [身份验证](https://protection.office.com)客户端报告突出显示了组织中用户或系统帐户对 SMTP AUTH 客户端提交协议的使用。</span><span class="sxs-lookup"><span data-stu-id="94064-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="94064-109">此旧协议 (终结点 smtp.office365.com) 仅提供基本身份验证，并且易于被破坏的帐户用来发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="94064-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="94064-110">通过见解和报表，可以检查 SMTP AUTH 电子邮件提交的异常活动。</span><span class="sxs-lookup"><span data-stu-id="94064-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="94064-111">它还显示使用 SMTP AUTH 的客户端或设备的 TLS 使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="94064-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="94064-112">小部件指示过去 7 天内使用 SMTP 身份验证协议的用户和服务帐户的数量。</span><span class="sxs-lookup"><span data-stu-id="94064-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![安全与合规中心的"邮件流"仪表板中的"SMTP &小组件"](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="94064-114">如果单击小部件上的消息数，则会出现 SMTP **身份验证客户端** 飞出控件。</span><span class="sxs-lookup"><span data-stu-id="94064-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="94064-115">该飞出站提供上一周 TLS 使用情况和卷的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="94064-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![单击"邮件流"仪表板中的"SMTP 身份验证客户端"小组件后的详细信息 flyout](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="94064-117">您可以单击 **"SMTP 身份验证客户端报告** "链接以转到 SMTP 身份验证客户端报告，如下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="94064-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="94064-118">SMTP 身份验证客户端报告</span><span class="sxs-lookup"><span data-stu-id="94064-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="94064-119">SMTP 身份验证客户端报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="94064-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="94064-120">默认情况下，报告显示过去 7 天的数据，但最近 90 天的数据可用。</span><span class="sxs-lookup"><span data-stu-id="94064-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="94064-121">概述部分包含以下图表：</span><span class="sxs-lookup"><span data-stu-id="94064-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="94064-122">查看数据 **者：** 发送卷：默认情况下，图表显示从所有域发送的 SMTP 身份验证客户端邮件数 (显示其数据 **：** 默认情况下，所有发件人域都) 。</span><span class="sxs-lookup"><span data-stu-id="94064-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="94064-123">可以通过单击"显示其数据"，然后从下拉列表中选择发件人域，将结果筛选到特定发件人域。</span><span class="sxs-lookup"><span data-stu-id="94064-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="94064-124">如果您将特定的数据点悬停在 (天) ，将显示消息数。</span><span class="sxs-lookup"><span data-stu-id="94064-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![安全与合规中心内 SMTP 身份验证客户端报告中&卷视图](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="94064-126">**查看数据者：TLS 使用情况**：图表显示选定时段内所有 SMTP 身份验证客户端邮件的 TLS 使用率百分比。</span><span class="sxs-lookup"><span data-stu-id="94064-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="94064-127">此图允许你识别仍在使用较早版本的 TLS 的用户和系统帐户并采取措施。</span><span class="sxs-lookup"><span data-stu-id="94064-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![安全与合规中心内 SMTP 身份验证客户端报告中的 TLS &视图](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="94064-129">如果 **单击筛选器中的** 报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="94064-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="94064-130">单击 **"请求** 报告"以在电子邮件中接收报告的详细版本。</span><span class="sxs-lookup"><span data-stu-id="94064-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="94064-131">可以指定接收报告的日期范围和收件人。</span><span class="sxs-lookup"><span data-stu-id="94064-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="94064-132">SMTP 身份验证客户端报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="94064-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="94064-133">如果单击 **"查看详细信息表**"，显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="94064-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="94064-134">**查看数据者：发送卷**：下表显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="94064-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="94064-135">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="94064-135">**Sender address**</span></span>
  - <span data-ttu-id="94064-136">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="94064-136">**Message count**</span></span>

  <span data-ttu-id="94064-137">如果您选择一行，则相同的详细信息将显示在一个飞出区中。</span><span class="sxs-lookup"><span data-stu-id="94064-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="94064-138">**查看数据者：TLS 使用情况**：下表显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="94064-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="94064-139">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="94064-139">**Sender address**</span></span>
  - <span data-ttu-id="94064-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94064-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="94064-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94064-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="94064-142">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="94064-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="94064-143">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="94064-143">**Message count**</span></span>

  <span data-ttu-id="94064-144"><sup>\*</sup> 此列显示发件人发送的邮件的百分比和数量。</span><span class="sxs-lookup"><span data-stu-id="94064-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="94064-145">如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="94064-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="94064-146">如果您选择一行，则类似的详细信息将显示在一个飞出内容中：</span><span class="sxs-lookup"><span data-stu-id="94064-146">If you select a row, similar details are shown in a flyout:</span></span>

![SMTP 身份验证客户端报告中 TLS 使用情况视图的详细信息表的"详细信息"飞出](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="94064-148">单击 **"请求** 报告"以在电子邮件中接收报告的详细版本。</span><span class="sxs-lookup"><span data-stu-id="94064-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="94064-149">可以指定接收报告的日期范围和收件人。</span><span class="sxs-lookup"><span data-stu-id="94064-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="94064-150">若要返回到报告视图，请单击"查看 **报告"。**</span><span class="sxs-lookup"><span data-stu-id="94064-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94064-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="94064-151">Related topics</span></span>

<span data-ttu-id="94064-152">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="94064-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
