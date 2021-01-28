---
title: 邮件流仪表板中的未送达报告
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
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"未送达详细信息"报告来监视未送达报告中最常遇到的错误代码 (也称为来自组织中发件人的NDDR或退回邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029830"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="183be-103">安全与合规中心中的&报告</span><span class="sxs-lookup"><span data-stu-id="183be-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="183be-104">安全与合规中心的邮件流仪表板[](mail-flow-insights-v2.md)中的"未送达报告"显示未送达报告（也称为" (或退回邮件) 报告）中遇到次数最多的错误代码。 [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="183be-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="183be-105">此报告显示了 NDR 的详细信息，因此您可以解决电子邮件传递问题。</span><span class="sxs-lookup"><span data-stu-id="183be-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![安全与合规中心的邮件流仪表板中的"未送达&小组件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="183be-107">未送达报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="183be-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="183be-108">单击" **未送达报告"** 小部件将进入 **未送达报告**。</span><span class="sxs-lookup"><span data-stu-id="183be-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="183be-109">默认情况下，将显示所有错误代码的活动。</span><span class="sxs-lookup"><span data-stu-id="183be-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="183be-110">如果单击 **"显示数据"，** 可以从下拉列表中选择特定的错误代码。</span><span class="sxs-lookup"><span data-stu-id="183be-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="183be-111">如果将鼠标悬停在图表中 (特定) 指定天的错误代码上，你将看到该错误的消息总数。</span><span class="sxs-lookup"><span data-stu-id="183be-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![非接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="183be-113">未送达报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="183be-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="183be-114">如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="183be-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="183be-115">"日期"</span><span class="sxs-lookup"><span data-stu-id="183be-115">**Date**</span></span>
- <span data-ttu-id="183be-116">**未送达报告代码**</span><span class="sxs-lookup"><span data-stu-id="183be-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="183be-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="183be-117">**Count**</span></span>
- <span data-ttu-id="183be-118">**示例邮件**：受影响邮件示例的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="183be-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="183be-119">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="183be-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="183be-120">若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**</span><span class="sxs-lookup"><span data-stu-id="183be-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="183be-121">当您在表中选择一行时，将显示一个包含以下信息的飞出图：</span><span class="sxs-lookup"><span data-stu-id="183be-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="183be-122">"日期"</span><span class="sxs-lookup"><span data-stu-id="183be-122">**Date**</span></span>
- <span data-ttu-id="183be-123">**未送达报告代码**：可以单击链接来查找有关特定错误代码的原因和解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="183be-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="183be-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="183be-124">**Count**</span></span>
- <span data-ttu-id="183be-125">**示例邮件**：可以单击 **"查看示例邮件**"以查看受影响 [](message-trace-scc.md)邮件示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="183be-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在未送达报告中的"详细信息"表视图中选择行后的详细信息飞出](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="183be-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="183be-127">Related topics</span></span>

<span data-ttu-id="183be-128">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="183be-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
