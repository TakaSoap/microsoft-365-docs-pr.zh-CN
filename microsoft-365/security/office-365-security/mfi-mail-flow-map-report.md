---
title: 邮件流地图
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
description: 管理员可了解如何使用安全 & 合规中心的邮件流仪表板中的邮件流地图，直观显示和跟踪通过连接器和不使用连接器如何流出其组织的邮件流。
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826997"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="8989b-103">安全与合规中心&邮件流图</span><span class="sxs-lookup"><span data-stu-id="8989b-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="8989b-104">安全 &**合**[规中心的邮件流](mail-flow-insights-v2.md)仪表板中的邮件流图可以了解邮件流如何通过组织。</span><span class="sxs-lookup"><span data-stu-id="8989b-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="8989b-105">你可以使用此信息了解模式、识别异常并修复发生的问题。</span><span class="sxs-lookup"><span data-stu-id="8989b-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![安全电子邮件合规性中心内邮件流仪表板中的邮件流&小部件](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="8989b-107">默认情况下，小部件显示图表（称为 *Sankey* 图表）中上一天的邮件流模式。</span><span class="sxs-lookup"><span data-stu-id="8989b-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="8989b-108">您可以使用向左箭头 ![ 和向右 ](../../media/scc-left-arrow.png) 键显示 ![ ](../../media/scc-right-arrow.png) 不同天的信息。</span><span class="sxs-lookup"><span data-stu-id="8989b-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="8989b-109">每种不同的颜色代表不同的入站或出站连接器的邮件流 (不使用连接器) 。</span><span class="sxs-lookup"><span data-stu-id="8989b-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="8989b-110">如果将鼠标悬停在特定颜色上，则将为该类型的连接线显示邮件数。</span><span class="sxs-lookup"><span data-stu-id="8989b-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="8989b-111">邮件流地图的报表视图</span><span class="sxs-lookup"><span data-stu-id="8989b-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="8989b-112">单击邮件流 **地图小部件** 可转到邮件流 **地图** 报告。</span><span class="sxs-lookup"><span data-stu-id="8989b-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="8989b-113">下面的图表提供了报表视图：</span><span class="sxs-lookup"><span data-stu-id="8989b-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8989b-114">**显示数据：概述**：此基本上是小部件的更大视图。</span><span class="sxs-lookup"><span data-stu-id="8989b-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="8989b-115">如果将鼠标悬停在特定颜色上，则会为该类型的连接线显示邮件数。</span><span class="sxs-lookup"><span data-stu-id="8989b-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![邮件流地图报告中的概述视图](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="8989b-117">**显示数据：详细信息**：此视图显示有关连接器和目标域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8989b-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="8989b-118">会列出顶部发件人和收件人域，其他域将放入其他 **域**。</span><span class="sxs-lookup"><span data-stu-id="8989b-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="8989b-119">如果您将鼠标悬停在特定颜色和节的上，将显示消息数。</span><span class="sxs-lookup"><span data-stu-id="8989b-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![邮件流地图报告中的详细信息视图](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="8989b-121">如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="8989b-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8989b-122">若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**</span><span class="sxs-lookup"><span data-stu-id="8989b-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="8989b-123">相关见解（如果存在）到 (例如 [，Fix 可能的邮件循环见](mfi-mail-loop-insight.md) 解和时间见) 。</span><span class="sxs-lookup"><span data-stu-id="8989b-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="8989b-124">邮件流地图的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="8989b-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="8989b-125">如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="8989b-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="8989b-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="8989b-126">**Date**</span></span>
- <span data-ttu-id="8989b-127">**类别**</span><span class="sxs-lookup"><span data-stu-id="8989b-127">**Category**</span></span>
- <span data-ttu-id="8989b-128">**连接器/第三方服务提供商**</span><span class="sxs-lookup"><span data-stu-id="8989b-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="8989b-129">**发件人/收件人域**</span><span class="sxs-lookup"><span data-stu-id="8989b-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="8989b-130">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="8989b-130">**Message count**</span></span>

<span data-ttu-id="8989b-131">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="8989b-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8989b-132">如果选择行，类似于的详细信息会显示在浮出控件中：</span><span class="sxs-lookup"><span data-stu-id="8989b-132">If you select a row, similar details are shown in a flyout:</span></span>

![来自邮件流地图中详细信息表格的详细信息浮出控件](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="8989b-134">若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**</span><span class="sxs-lookup"><span data-stu-id="8989b-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="8989b-135">若要返回报告视图，请单击"查看**报告"。**</span><span class="sxs-lookup"><span data-stu-id="8989b-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8989b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8989b-136">See also</span></span>

<span data-ttu-id="8989b-137">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="8989b-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
