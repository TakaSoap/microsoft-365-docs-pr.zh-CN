---
title: 邮件流仪表板中的未送达报告
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
description: 管理员可了解如何使用安全 & 合规中心中邮件流仪表板中的"未送达详细信息"报告，来监视组织中发件人的未送达报告 (也称为"NDR"或"退回) 邮件"中的最常见错误代码。
ms.openlocfilehash: bdc2a2a16f76f4e6ada629c82b86423422ab56c9
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826913"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="f77be-103">安全与合规中心中的未&报告</span><span class="sxs-lookup"><span data-stu-id="f77be-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="f77be-104">安全 &**合规中心的**[邮件流仪表板中的](mail-flow-insights-v2.md)未送达报告显示未送达报告 (也称为"NDR"或"退回) 中的组织"</span><span class="sxs-lookup"><span data-stu-id="f77be-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="f77be-105">此报告显示 NDR 的详细信息，以便您可以解决电子邮件传递问题。</span><span class="sxs-lookup"><span data-stu-id="f77be-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![安全与合规中心的邮件流仪表板中的未送达&小部件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="f77be-107">未送达报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="f77be-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="f77be-108">单击未 **送达报告小** 部件会将您转到 **未送达报告**。</span><span class="sxs-lookup"><span data-stu-id="f77be-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="f77be-109">默认情况下，会显示所有错误代码的活动。</span><span class="sxs-lookup"><span data-stu-id="f77be-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="f77be-110">如果单击 **"显示数据"，** 你可以从下拉列表中选择特定的错误代码。</span><span class="sxs-lookup"><span data-stu-id="f77be-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="f77be-111">如果您将鼠标悬停在图表 (一天) 的特定颜色上，您将看到错误的总消息数。</span><span class="sxs-lookup"><span data-stu-id="f77be-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![非接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="f77be-113">未送达报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="f77be-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="f77be-114">如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f77be-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f77be-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="f77be-115">**Date**</span></span>
- <span data-ttu-id="f77be-116">**未送达报告代码**</span><span class="sxs-lookup"><span data-stu-id="f77be-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="f77be-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="f77be-117">**Count**</span></span>
- <span data-ttu-id="f77be-118">**示例消息**：受影响邮件示例的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="f77be-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="f77be-119">如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的\*\*\*\*日期范围**。</span><span class="sxs-lookup"><span data-stu-id="f77be-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f77be-120">若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**</span><span class="sxs-lookup"><span data-stu-id="f77be-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="f77be-121">选择表中行后，将出现一个浮出控件，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f77be-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="f77be-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="f77be-122">**Date**</span></span>
- <span data-ttu-id="f77be-123">**未送达报告代码**： 可以单击链接，以查找有关特定错误代码的原因和解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f77be-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="f77be-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="f77be-124">**Count**</span></span>
- <span data-ttu-id="f77be-125">**示例消息**： 您可以单击 **"查看示例邮件** "来 [查看受](message-trace-scc.md) 影响邮件的示例邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="f77be-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在未送达报告的"详细信息表"视图中选择行后的浮出控件详细信息](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="f77be-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="f77be-127">Related topics</span></span>

<span data-ttu-id="f77be-128">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="f77be-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
