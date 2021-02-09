---
title: 邮件流地图
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
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的邮件流映射来可视化和跟踪邮件流如何通过连接器和不使用连接器从组织流动。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87a5780bd2485ba6ad3b295c09a30a4d7fc34277
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150556"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="b4793-103">安全与合规中心内&映射</span><span class="sxs-lookup"><span data-stu-id="b4793-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b4793-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="b4793-104">**Applies to**</span></span>
- [<span data-ttu-id="b4793-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b4793-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="b4793-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b4793-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b4793-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4793-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b4793-108">安全 **与合规中心** 的邮件流 [](mail-flow-insights-v2.md)仪表板中的邮件 [流](https://protection.office.com)&提供了邮件在组织中流动的见解。</span><span class="sxs-lookup"><span data-stu-id="b4793-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="b4793-109">您可以使用此信息了解模式、识别异常，并解决出现的问题。</span><span class="sxs-lookup"><span data-stu-id="b4793-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![安全与合规中心的邮件流仪表板中的"邮件流&小组件](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="b4793-111">默认情况下，小部件在称为 *Sankey* 图表的图表中显示前一天的邮件流模式。</span><span class="sxs-lookup"><span data-stu-id="b4793-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="b4793-112">可以使用向左箭头和向右箭头显示不同 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 日期的信息。</span><span class="sxs-lookup"><span data-stu-id="b4793-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="b4793-113">每种不同的颜色表示通过不同入站或出站连接器的邮件流 (或不使用连接器) 。</span><span class="sxs-lookup"><span data-stu-id="b4793-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="b4793-114">如果将鼠标悬停在特定颜色上，将显示该类型的连接器的消息数。</span><span class="sxs-lookup"><span data-stu-id="b4793-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="b4793-115">邮件流映射的报告视图</span><span class="sxs-lookup"><span data-stu-id="b4793-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="b4793-116">单击" **邮件流映射"** 小部件将进入 **邮件流映射** 报告。</span><span class="sxs-lookup"><span data-stu-id="b4793-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="b4793-117">下表中提供了以下报表视图：</span><span class="sxs-lookup"><span data-stu-id="b4793-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b4793-118">**显示数据：概述**：这基本上是小部件的较大视图。</span><span class="sxs-lookup"><span data-stu-id="b4793-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="b4793-119">如果将鼠标悬停在特定颜色上，将显示该类型的连接器的消息数。</span><span class="sxs-lookup"><span data-stu-id="b4793-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![邮件流映射报告中的概述视图](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="b4793-121">**显示其数据：详细信息**：此视图显示有关连接器和目标域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b4793-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="b4793-122">列出顶级发件人和收件人域，其余域放在"其他 **"中**。</span><span class="sxs-lookup"><span data-stu-id="b4793-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="b4793-123">如果将鼠标悬停在特定颜色和节上，将显示消息数。</span><span class="sxs-lookup"><span data-stu-id="b4793-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![邮件流映射报告中的详细信息视图](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="b4793-125">如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="b4793-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b4793-126">若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**</span><span class="sxs-lookup"><span data-stu-id="b4793-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="b4793-127">相关见解显示在邮件流映射下方（如果它们可用 (例如， [修复](mfi-mail-loop-insight.md) 可能的邮件循环见解) 。</span><span class="sxs-lookup"><span data-stu-id="b4793-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="b4793-128">邮件流映射的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="b4793-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="b4793-129">如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="b4793-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b4793-130">"日期"</span><span class="sxs-lookup"><span data-stu-id="b4793-130">**Date**</span></span>
- <span data-ttu-id="b4793-131">**类别**</span><span class="sxs-lookup"><span data-stu-id="b4793-131">**Category**</span></span>
- <span data-ttu-id="b4793-132">**连接器/第三方服务提供商**</span><span class="sxs-lookup"><span data-stu-id="b4793-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="b4793-133">**发件人/收件人域**</span><span class="sxs-lookup"><span data-stu-id="b4793-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="b4793-134">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="b4793-134">**Message count**</span></span>

<span data-ttu-id="b4793-135">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="b4793-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b4793-136">如果您选择一行，则类似的详细信息将显示在一个标注中：</span><span class="sxs-lookup"><span data-stu-id="b4793-136">If you select a row, similar details are shown in a flyout:</span></span>

![邮件流映射中详细信息表中的详细信息飞出](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="b4793-138">若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**</span><span class="sxs-lookup"><span data-stu-id="b4793-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="b4793-139">若要返回到报告视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="b4793-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4793-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4793-140">See also</span></span>

<span data-ttu-id="b4793-141">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="b4793-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
