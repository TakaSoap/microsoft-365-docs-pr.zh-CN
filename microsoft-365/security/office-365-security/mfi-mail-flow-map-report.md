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
description: 管理员可以了解如何使用安全 & 合规性中心中邮件流仪表板中的邮件流映射，直观地显示和跟踪邮件在其组织中的流动和发件人，而无需使用连接器。
ms.openlocfilehash: e144d1d42603fbf2a8f031b1cf7584b6e6ed5c7b
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358586"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="31c6a-103">安全 & 合规中心中的邮件流映射</span><span class="sxs-lookup"><span data-stu-id="31c6a-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="31c6a-104">[安全 & 合规性中心](https://protection.office.com)的邮件[流仪表板](mail-flow-insights-v2.md)中的**邮件流映射**可提供邮件在组织中流动的见解。</span><span class="sxs-lookup"><span data-stu-id="31c6a-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="31c6a-105">您可以使用此信息来了解模式、确定异常并在出现问题时解决问题。</span><span class="sxs-lookup"><span data-stu-id="31c6a-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![安全 & 合规性中心的邮件流仪表板中的邮件流映射小部件](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="31c6a-107">默认情况下，该小部件显示来自前一天的邮件流模式（称为 " *Sankey* 图表"）。</span><span class="sxs-lookup"><span data-stu-id="31c6a-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="31c6a-108">您可以使用向左箭头 ![ ](../../media/scc-left-arrow.png) 和向右箭头向 ![ 右箭头 ](../../media/scc-right-arrow.png) 来显示不同天的信息。</span><span class="sxs-lookup"><span data-stu-id="31c6a-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="31c6a-109">每种不同的颜色代表不同入站或出站连接器上的邮件流 (或不使用连接器) 。</span><span class="sxs-lookup"><span data-stu-id="31c6a-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="31c6a-110">如果将鼠标悬停在特定颜色上，则将显示该类型的连接符的邮件数。</span><span class="sxs-lookup"><span data-stu-id="31c6a-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="31c6a-111">邮件流映射的报告视图</span><span class="sxs-lookup"><span data-stu-id="31c6a-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="31c6a-112">单击 " **邮件流地图** " 小部件将转到 **邮件流地图** 报告。</span><span class="sxs-lookup"><span data-stu-id="31c6a-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="31c6a-113">报表视图中提供了以下图表：</span><span class="sxs-lookup"><span data-stu-id="31c6a-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="31c6a-114">**显示数据：概述**：这基本上是小部件的更大视图。</span><span class="sxs-lookup"><span data-stu-id="31c6a-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="31c6a-115">如果将鼠标悬停在特定颜色上，则将显示该类型的连接符的邮件数。</span><span class="sxs-lookup"><span data-stu-id="31c6a-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![邮件流映射报告中的概述视图](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="31c6a-117">**显示以下项的数据：详细**信息：此视图显示有关连接器和目标域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="31c6a-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="31c6a-118">将列出最上面的发件人和收件人域，其余部分将放入 **其他**域中。</span><span class="sxs-lookup"><span data-stu-id="31c6a-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="31c6a-119">如果将鼠标悬停在特定的颜色和节上，则会显示邮件数。</span><span class="sxs-lookup"><span data-stu-id="31c6a-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![邮件流映射报告中的详细信息视图](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="31c6a-121">如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="31c6a-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="31c6a-122">若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载**"。</span><span class="sxs-lookup"><span data-stu-id="31c6a-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="31c6a-123">如果可用，相关的见解将显示在邮件流地图的下面 (例如， [修复可能的邮件循环真知灼见](mfi-mail-loop-insight.md)) 。</span><span class="sxs-lookup"><span data-stu-id="31c6a-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="31c6a-124">邮件流映射的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="31c6a-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="31c6a-125">如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="31c6a-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="31c6a-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="31c6a-126">**Date**</span></span>
- <span data-ttu-id="31c6a-127">**类别**</span><span class="sxs-lookup"><span data-stu-id="31c6a-127">**Category**</span></span>
- <span data-ttu-id="31c6a-128">**连接器/第三方服务提供商**</span><span class="sxs-lookup"><span data-stu-id="31c6a-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="31c6a-129">**发件人/收件人域**</span><span class="sxs-lookup"><span data-stu-id="31c6a-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="31c6a-130">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="31c6a-130">**Message count**</span></span>

<span data-ttu-id="31c6a-131">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="31c6a-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="31c6a-132">如果选择行，则在浮出控件中显示类似的详细信息：</span><span class="sxs-lookup"><span data-stu-id="31c6a-132">If you select a row, similar details are shown in a flyout:</span></span>

![详细信息从邮件流映射的详细信息表中飞出控件](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="31c6a-134">若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载**"。</span><span class="sxs-lookup"><span data-stu-id="31c6a-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="31c6a-135">若要返回到 "报告" 视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="31c6a-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="31c6a-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31c6a-136">See also</span></span>

<span data-ttu-id="31c6a-137">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="31c6a-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
