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
description: 管理员可以了解如何使用安全 & 合规中心内的邮件流仪表板中的"未送达详细信息"报告来监视未送达报告中最常遇到的错误代码 (也称为"未送达报告"或退回来自组织中发件人的邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055192"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="61313-103">安全与合规中心&未送达报告</span><span class="sxs-lookup"><span data-stu-id="61313-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61313-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="61313-104">**Applies to**</span></span>
- [<span data-ttu-id="61313-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="61313-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="61313-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="61313-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="61313-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61313-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="61313-108">安全与合规中心内"邮件[](mail-flow-insights-v2.md)流"仪表板中的"未送达报告"显示未送达报告中遇到的错误代码 (也称为"未送达报告"或针对组织中用户的退回邮件) 。 [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="61313-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="61313-109">此报告显示了 NDR 的详细信息，因此您可以解决电子邮件传递问题。</span><span class="sxs-lookup"><span data-stu-id="61313-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![安全与合规中心的"邮件流"仪表板中的"未送达&小组件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="61313-111">未送达报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="61313-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="61313-112">单击" **未送达报告"** 小部件将进入 **未送达报告**。</span><span class="sxs-lookup"><span data-stu-id="61313-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="61313-113">默认情况下，将显示所有错误代码的活动。</span><span class="sxs-lookup"><span data-stu-id="61313-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="61313-114">If you click **Show data for**， you can select a specific error code from the dropdown.</span><span class="sxs-lookup"><span data-stu-id="61313-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="61313-115">如果将鼠标悬停在图表中 (特定) 显示的错误代码上，你将看到该错误的消息总数。</span><span class="sxs-lookup"><span data-stu-id="61313-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![未接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="61313-117">未送达报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="61313-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="61313-118">如果单击 **视图中的"** 查看详细信息"报表视图，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="61313-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="61313-119">"日期"</span><span class="sxs-lookup"><span data-stu-id="61313-119">**Date**</span></span>
- <span data-ttu-id="61313-120">**未送达报告代码**</span><span class="sxs-lookup"><span data-stu-id="61313-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="61313-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="61313-121">**Count**</span></span>
- <span data-ttu-id="61313-122">**示例邮件**：受影响邮件示例的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="61313-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="61313-123">如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 </span><span class="sxs-lookup"><span data-stu-id="61313-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="61313-124">若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**</span><span class="sxs-lookup"><span data-stu-id="61313-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="61313-125">选择表格中的行时，将显示一个包含以下信息的飞出图：</span><span class="sxs-lookup"><span data-stu-id="61313-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="61313-126">"日期"</span><span class="sxs-lookup"><span data-stu-id="61313-126">**Date**</span></span>
- <span data-ttu-id="61313-127">**未送达报告代码**：可以单击链接来查找有关特定错误代码的原因和解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="61313-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="61313-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="61313-128">**Count**</span></span>
- <span data-ttu-id="61313-129">**示例邮件**：可以单击 **"查看示例** 邮件"以查看 [受影响邮件](message-trace-scc.md) 示例的邮件跟踪结果。</span><span class="sxs-lookup"><span data-stu-id="61313-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在未送达报告中的"详细信息"表视图中选择一行后的详细信息飞出](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="61313-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="61313-131">Related topics</span></span>

<span data-ttu-id="61313-132">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="61313-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
