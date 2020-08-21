---
title: 邮件流仪表板中的"非接受域"报告
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
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"不接受域"报告来监视来自本地组织的邮件，其中发件人域未在 Microsoft 365 中配置。
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826937"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="cea2b-103">安全电子邮件合规中心中的"非&域"报告</span><span class="sxs-lookup"><span data-stu-id="cea2b-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="cea2b-104">安全 & **合规** 中心的 [邮件流仪表板中的"](mail-flow-insights-v2.md) 未接受域"报告显示内部部署电子邮件组织中邮件的相关信息，其中发件人域未在 Microsoft 365 组织中配置为接受域。</span><span class="sxs-lookup"><span data-stu-id="cea2b-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="cea2b-105">如果我们有数据来证明这些邮件的意图是恶意邮件，Microsoft 365 可能会限制这些邮件。</span><span class="sxs-lookup"><span data-stu-id="cea2b-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="cea2b-106">因此，请务必了解发生的情况以及解决问题。</span><span class="sxs-lookup"><span data-stu-id="cea2b-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

!["安全 &合规中心"""邮件流"仪表板中的"不接受&小部件](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="cea2b-108">非接受域报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="cea2b-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="cea2b-109">在"不接受域 **"小部件中单击** 此图表会将您转到 **"不接受域"** 报告。</span><span class="sxs-lookup"><span data-stu-id="cea2b-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="cea2b-110">默认情况下，会显示所有受影响连接器的活动。</span><span class="sxs-lookup"><span data-stu-id="cea2b-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="cea2b-111">如果您单击 **"显示数据"，** 可以在下拉列表中选择特定连接器。</span><span class="sxs-lookup"><span data-stu-id="cea2b-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="cea2b-112">如果您将鼠标悬停在图表 (的数据) 点，您将看到连接器的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="cea2b-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![非接受域报告中的报告视图](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="cea2b-114">非接受域报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="cea2b-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="cea2b-115">如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="cea2b-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="cea2b-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="cea2b-116">**Date**</span></span>
- <span data-ttu-id="cea2b-117">**入站连接器名称**</span><span class="sxs-lookup"><span data-stu-id="cea2b-117">**Inbound connector name**</span></span>
- <span data-ttu-id="cea2b-118">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="cea2b-118">**Sender domain**</span></span>
- <span data-ttu-id="cea2b-119">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="cea2b-119">**Message count**</span></span>
- <span data-ttu-id="cea2b-120">**示例消息**：受影响邮件示例的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="cea2b-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="cea2b-121">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="cea2b-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="cea2b-122">若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**</span><span class="sxs-lookup"><span data-stu-id="cea2b-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="cea2b-123">选择表中行后，将出现一个浮出控件，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="cea2b-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="cea2b-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="cea2b-124">**Date**</span></span>
- <span data-ttu-id="cea2b-125">**入站连接器名称**</span><span class="sxs-lookup"><span data-stu-id="cea2b-125">**Inbound connector name**</span></span>
- <span data-ttu-id="cea2b-126">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="cea2b-126">**Sender domain**</span></span>
- <span data-ttu-id="cea2b-127">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="cea2b-127">**Message count**</span></span>
- <span data-ttu-id="cea2b-128">**示例消息**： 您可以单击 **"查看示例** 邮件"来 [查看受](message-trace-scc.md) 影响邮件的示例邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="cea2b-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在非接受域报告的"详细信息表"视图中选择行后的详细信息浮出控件](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="cea2b-130">若要返回报告视图，请单击"查看**报告"。**</span><span class="sxs-lookup"><span data-stu-id="cea2b-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cea2b-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="cea2b-131">Related topics</span></span>

<span data-ttu-id="cea2b-132">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="cea2b-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
