---
title: 邮件流仪表板中的非接受域报告
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
description: 管理员可以了解如何在安全 & 合规性中心中的邮件流仪表板中使用未接受的域报告来监视来自内部部署组织的邮件，其中发件人的域不是在 Microsoft 365 中配置的。
ms.openlocfilehash: 02692fbded20aa5062ce8add83925fb65c116630
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358574"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="e5331-103">安全 & 合规中心中的非接受域报告</span><span class="sxs-lookup"><span data-stu-id="e5331-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="e5331-104">[Security & 合规性中心](https://protection.office.com)的[邮件流仪表板](mail-flow-insights-v2.md)中的**非接受域**报告显示有关内部部署电子邮件组织中的邮件的信息，其中发件人的域未配置为 Microsoft 365 组织中的接受域。</span><span class="sxs-lookup"><span data-stu-id="e5331-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="e5331-105">如果我们有数据来证明这些邮件的意图是恶意的，Microsoft 365 可能会对这些邮件进行限制。</span><span class="sxs-lookup"><span data-stu-id="e5331-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="e5331-106">因此，重要的是要了解所发生的情况并解决问题。</span><span class="sxs-lookup"><span data-stu-id="e5331-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![安全 & 合规性中心的邮件流仪表板中的 "不接受的域" 小部件](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="e5331-108">不接受的域报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="e5331-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="e5331-109">单击 **不接受的域** 小组件上的图表将转到 **不接受的域** 报告。</span><span class="sxs-lookup"><span data-stu-id="e5331-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="e5331-110">默认情况下，将显示所有受影响的连接器的活动。</span><span class="sxs-lookup"><span data-stu-id="e5331-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="e5331-111">如果单击 " **显示数据**"，则可以从下拉列表中选择特定的连接器。</span><span class="sxs-lookup"><span data-stu-id="e5331-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="e5331-112">如果将鼠标悬停在图表中 (日) 上，您将看到连接器的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="e5331-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![不接受的域报告中的报告视图](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="e5331-114">不接受的域报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="e5331-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="e5331-115">如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="e5331-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e5331-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="e5331-116">**Date**</span></span>
- <span data-ttu-id="e5331-117">**入站连接器名称**</span><span class="sxs-lookup"><span data-stu-id="e5331-117">**Inbound connector name**</span></span>
- <span data-ttu-id="e5331-118">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="e5331-118">**Sender domain**</span></span>
- <span data-ttu-id="e5331-119">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="e5331-119">**Message count**</span></span>
- <span data-ttu-id="e5331-120">**示例邮件**：受影响邮件的示例的邮件 id。</span><span class="sxs-lookup"><span data-stu-id="e5331-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="e5331-121">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="e5331-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e5331-122">若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载**"。</span><span class="sxs-lookup"><span data-stu-id="e5331-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e5331-123">当您在表中选择一行时，将显示一个包含以下信息的浮出控件：</span><span class="sxs-lookup"><span data-stu-id="e5331-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="e5331-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="e5331-124">**Date**</span></span>
- <span data-ttu-id="e5331-125">**入站连接器名称**</span><span class="sxs-lookup"><span data-stu-id="e5331-125">**Inbound connector name**</span></span>
- <span data-ttu-id="e5331-126">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="e5331-126">**Sender domain**</span></span>
- <span data-ttu-id="e5331-127">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="e5331-127">**Message count**</span></span>
- <span data-ttu-id="e5331-128">**示例邮件**：您可以单击 " **查看示例邮件** "，查看有关受影响邮件的示例的 [邮件跟踪](message-trace-scc.md) 结果。</span><span class="sxs-lookup"><span data-stu-id="e5331-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在 "不接受的域" 报表的 "详细信息表" 视图中选择行后的详细信息浮出控件](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="e5331-130">若要返回到 "报告" 视图，请单击 " **查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="e5331-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5331-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5331-131">Related topics</span></span>

<span data-ttu-id="e5331-132">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e5331-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
