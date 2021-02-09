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
ms.openlocfilehash: af4beefb8ba15fd7d98b11ec2571eee65a99e4e3
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150155"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="5448d-103">安全与合规中心中的&报告</span><span class="sxs-lookup"><span data-stu-id="5448d-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5448d-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="5448d-104">**Applies to**</span></span>
- [<span data-ttu-id="5448d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5448d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="5448d-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="5448d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="5448d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5448d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5448d-108">安全与合规中心的邮件流仪表板[](mail-flow-insights-v2.md)中的未送达报告显示未送达报告（也称为 (报告或退回邮件) 组织中用户遇到次数最多的错误代码。 [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="5448d-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="5448d-109">此报告显示了 NDR 的详细信息，因此您可以解决电子邮件传递问题。</span><span class="sxs-lookup"><span data-stu-id="5448d-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![安全与合规中心的邮件流仪表板中的"未送达&小组件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="5448d-111">未送达报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="5448d-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="5448d-112">单击" **未送达报告"** 小部件将进入 **未送达报告**。</span><span class="sxs-lookup"><span data-stu-id="5448d-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="5448d-113">默认情况下，将显示所有错误代码的活动。</span><span class="sxs-lookup"><span data-stu-id="5448d-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="5448d-114">如果单击 **"显示数据"，** 可以从下拉列表中选择特定的错误代码。</span><span class="sxs-lookup"><span data-stu-id="5448d-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="5448d-115">如果将鼠标悬停在 (特定) 特定天的错误代码上，则会看到该错误的消息总数。</span><span class="sxs-lookup"><span data-stu-id="5448d-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![非接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="5448d-117">未送达报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="5448d-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="5448d-118">如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="5448d-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5448d-119">"日期"</span><span class="sxs-lookup"><span data-stu-id="5448d-119">**Date**</span></span>
- <span data-ttu-id="5448d-120">**未送达报告代码**</span><span class="sxs-lookup"><span data-stu-id="5448d-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="5448d-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="5448d-121">**Count**</span></span>
- <span data-ttu-id="5448d-122">**示例邮件**：受影响邮件示例的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="5448d-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="5448d-123">如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="5448d-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5448d-124">若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**</span><span class="sxs-lookup"><span data-stu-id="5448d-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="5448d-125">当您在表中选择一行时，将显示一个包含以下信息的飞出图：</span><span class="sxs-lookup"><span data-stu-id="5448d-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="5448d-126">"日期"</span><span class="sxs-lookup"><span data-stu-id="5448d-126">**Date**</span></span>
- <span data-ttu-id="5448d-127">**未送达报告代码**：可以单击链接来查找有关特定错误代码的原因和解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5448d-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="5448d-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="5448d-128">**Count**</span></span>
- <span data-ttu-id="5448d-129">**示例邮件**：可以单击 **"查看示例邮件** " [以查看受影响邮件](message-trace-scc.md) 示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="5448d-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在未送达报告中的"详细信息"表视图中选择行后的详细信息飞出](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="5448d-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="5448d-131">Related topics</span></span>

<span data-ttu-id="5448d-132">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="5448d-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
