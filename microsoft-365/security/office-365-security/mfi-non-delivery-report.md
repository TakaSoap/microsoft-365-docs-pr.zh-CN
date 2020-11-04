---
title: 邮件流仪表板中的未送达报告
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在安全 & 合规性中心中使用邮件流仪表板中的 "未送达详细信息" 报告来监视未送达报告中最常遇到的错误代码 (也称为 "Ndr" 或 "退回邮件") 来自组织中的发件人的邮件。
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877677"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="97640-103">安全 & 合规中心中的未送达报告</span><span class="sxs-lookup"><span data-stu-id="97640-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="97640-104">[Security & 合规性中心](https://protection.office.com)的 [邮件流仪表板](mail-flow-insights-v2.md)中的 **未送达报告** 显示在未送达报告中遇到的最大错误代码 (也称为 "ndr" 或 "退回邮件") 组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="97640-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="97640-105">此报告显示 Ndr 的详细信息，以便您可以解决电子邮件传递问题。</span><span class="sxs-lookup"><span data-stu-id="97640-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Security & 合规性中心的邮件流仪表板中的未送达报告小部件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="97640-107">未送达报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="97640-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="97640-108">单击 **未送达报告** 小部件将转到 **未送达报告** 。</span><span class="sxs-lookup"><span data-stu-id="97640-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="97640-109">默认情况下，显示所有错误代码的活动。</span><span class="sxs-lookup"><span data-stu-id="97640-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="97640-110">如果单击 " **显示数据** "，则可以从下拉列表中选择特定的错误代码。</span><span class="sxs-lookup"><span data-stu-id="97640-110">If you click **Show data for** , you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="97640-111">如果将鼠标悬停在特定颜色 (在图表中特定日期) 的错误代码，您将看到错误的邮件总数。</span><span class="sxs-lookup"><span data-stu-id="97640-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![不接受的域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="97640-113">未送达报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="97640-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="97640-114">如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="97640-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="97640-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="97640-115">**Date**</span></span>
- <span data-ttu-id="97640-116">**未送达报告代码**</span><span class="sxs-lookup"><span data-stu-id="97640-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="97640-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="97640-117">**Count**</span></span>
- <span data-ttu-id="97640-118">**示例邮件** ：受影响邮件的示例的邮件 id。</span><span class="sxs-lookup"><span data-stu-id="97640-118">**Sample messages** : The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="97640-119">如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期** " 的日期范围。</span><span class="sxs-lookup"><span data-stu-id="97640-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="97640-120">若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载** "。</span><span class="sxs-lookup"><span data-stu-id="97640-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="97640-121">当您在表中选择一行时，将显示一个包含以下信息的浮出控件：</span><span class="sxs-lookup"><span data-stu-id="97640-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="97640-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="97640-122">**Date**</span></span>
- <span data-ttu-id="97640-123">**未送达报告代码** ：您可以单击链接以查找有关特定错误代码的原因和解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="97640-123">**Non-delivery report code** : You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="97640-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="97640-124">**Count**</span></span>
- <span data-ttu-id="97640-125">**示例邮件** ：您可以单击 " **查看示例邮件** "，查看有关受影响邮件的示例的 [邮件跟踪](message-trace-scc.md) 结果。</span><span class="sxs-lookup"><span data-stu-id="97640-125">**Sample messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在未送达报告的 "详细信息表" 视图中选择行后的详细信息浮出控件](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="97640-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="97640-127">Related topics</span></span>

<span data-ttu-id="97640-128">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="97640-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
