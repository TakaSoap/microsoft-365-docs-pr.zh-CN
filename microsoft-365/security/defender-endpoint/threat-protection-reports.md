---
title: Microsoft Defender for Endpoint 中的威胁防护报告
description: 使用威胁防护报告跟踪警报检测、类别和严重性
keywords: 警报检测， 来源， 警报按类别， 警报严重性， 警报分类， 确定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688977"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="16b12-104">Microsoft Defender for Endpoint 中的威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="16b12-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="16b12-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="16b12-105">**Applies to:**</span></span>
- [<span data-ttu-id="16b12-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="16b12-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16b12-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b12-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="16b12-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="16b12-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16b12-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="16b12-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="16b12-110">威胁防护报告提供有关在组织中生成的警报的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="16b12-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="16b12-111">该报告包括趋势信息，显示检测源、类别、严重性、状态、分类以及警报的确定。</span><span class="sxs-lookup"><span data-stu-id="16b12-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="16b12-112">仪表板分为两个部分：</span><span class="sxs-lookup"><span data-stu-id="16b12-112">The dashboard is structured into two sections:</span></span>

![威胁防护报告的图像](images/threat-protection-reports.png)

<span data-ttu-id="16b12-114">节</span><span class="sxs-lookup"><span data-stu-id="16b12-114">Section</span></span> | <span data-ttu-id="16b12-115">说明</span><span class="sxs-lookup"><span data-stu-id="16b12-115">Description</span></span> 
:---|:---
<span data-ttu-id="16b12-116">1</span><span class="sxs-lookup"><span data-stu-id="16b12-116">1</span></span> | <span data-ttu-id="16b12-117">警报趋势</span><span class="sxs-lookup"><span data-stu-id="16b12-117">Alerts trends</span></span>
<span data-ttu-id="16b12-118">2</span><span class="sxs-lookup"><span data-stu-id="16b12-118">2</span></span> | <span data-ttu-id="16b12-119">警报摘要</span><span class="sxs-lookup"><span data-stu-id="16b12-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="16b12-120">警报趋势</span><span class="sxs-lookup"><span data-stu-id="16b12-120">Alert trends</span></span>
<span data-ttu-id="16b12-121">默认情况下，警报趋势显示以最后一整天结尾的 30 天时段的警报信息。</span><span class="sxs-lookup"><span data-stu-id="16b12-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="16b12-122">为了更好地了解组织中发生的趋势，您可以通过调整所显示的时间段来微调报告期间。</span><span class="sxs-lookup"><span data-stu-id="16b12-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="16b12-123">若要调整时间段，请从下拉列表选项中选择一个时间范围：</span><span class="sxs-lookup"><span data-stu-id="16b12-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="16b12-124">30 天</span><span class="sxs-lookup"><span data-stu-id="16b12-124">30 days</span></span>
- <span data-ttu-id="16b12-125">3 个月</span><span class="sxs-lookup"><span data-stu-id="16b12-125">3 months</span></span>
- <span data-ttu-id="16b12-126">6 个月</span><span class="sxs-lookup"><span data-stu-id="16b12-126">6 months</span></span>
- <span data-ttu-id="16b12-127">自定义警报</span><span class="sxs-lookup"><span data-stu-id="16b12-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="16b12-128">这些筛选器仅适用于警报趋势部分。</span><span class="sxs-lookup"><span data-stu-id="16b12-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="16b12-129">它不会影响警报摘要部分。</span><span class="sxs-lookup"><span data-stu-id="16b12-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="16b12-130">警报摘要</span><span class="sxs-lookup"><span data-stu-id="16b12-130">Alert summary</span></span>
<span data-ttu-id="16b12-131">虽然警报趋势显示趋势警报信息，但警报摘要显示范围为当天的警报信息。</span><span class="sxs-lookup"><span data-stu-id="16b12-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="16b12-132">警报摘要允许您向下钻取到应用了相应筛选器的特定警报队列。</span><span class="sxs-lookup"><span data-stu-id="16b12-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="16b12-133">例如，单击"检测EDR"卡片中的"警报"栏，将进入警报队列，其中仅显示从检测结果EDR警报。</span><span class="sxs-lookup"><span data-stu-id="16b12-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="16b12-134">摘要部分反映的数据的范围为当前日期之前的 180 天。</span><span class="sxs-lookup"><span data-stu-id="16b12-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="16b12-135">例如，如果今天的日期为 2019 年 11 月 5 日，则摘要部分的数据将反映从 2019 年 5 月 5 日到 2019 年 11 月 5 日的数字。</span><span class="sxs-lookup"><span data-stu-id="16b12-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="16b12-136">对"趋势"部分应用的筛选器不会应用于摘要节。</span><span class="sxs-lookup"><span data-stu-id="16b12-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="16b12-137">警报属性</span><span class="sxs-lookup"><span data-stu-id="16b12-137">Alert attributes</span></span>
<span data-ttu-id="16b12-138">报告由显示以下警报属性的卡片决定：</span><span class="sxs-lookup"><span data-stu-id="16b12-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="16b12-139">**检测源**：显示有关传感器和检测技术的信息，这些传感器和检测技术提供 Microsoft Defender for Endpoint 用于触发警报的数据。</span><span class="sxs-lookup"><span data-stu-id="16b12-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="16b12-140">**威胁类别**：显示触发警报的威胁或攻击活动类型，指示安全操作可能重点关注的区域。</span><span class="sxs-lookup"><span data-stu-id="16b12-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="16b12-141">**严重性**：显示警报的严重性级别，指示威胁对组织的潜在共同影响以及解决这些威胁所需的响应级别。</span><span class="sxs-lookup"><span data-stu-id="16b12-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="16b12-142">**状态**：显示警报的解析状态，指示手动警报响应的效率以及自动修正 (（如果启用) ）。</span><span class="sxs-lookup"><span data-stu-id="16b12-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="16b12-143">分类 **&** 确定：显示如何在解决时对警报进行分类，是将它们分类为实际威胁 (真正的警报) 还是错误检测 (错误警报) 。</span><span class="sxs-lookup"><span data-stu-id="16b12-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="16b12-144">这些卡片还显示已解决警报的确定，提供其他见解，如找到的实际威胁类型或错误检测到的合法活动。</span><span class="sxs-lookup"><span data-stu-id="16b12-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="16b12-145">筛选数据</span><span class="sxs-lookup"><span data-stu-id="16b12-145">Filter data</span></span>

<span data-ttu-id="16b12-146">使用提供的筛选器包含或排除具有特定属性的警报。</span><span class="sxs-lookup"><span data-stu-id="16b12-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="16b12-147">这些筛选器适用于 **报告中** 的所有卡片。</span><span class="sxs-lookup"><span data-stu-id="16b12-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="16b12-148">例如，若要显示有关高严重性警报的数据，请仅：</span><span class="sxs-lookup"><span data-stu-id="16b12-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="16b12-149">在 **"筛选器>严重性"下，选择**" **高"**</span><span class="sxs-lookup"><span data-stu-id="16b12-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="16b12-150">确保已取消选择"严重性 **"下的** 所有其他选项。</span><span class="sxs-lookup"><span data-stu-id="16b12-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="16b12-151">选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="16b12-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="16b12-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="16b12-152">Related topic</span></span>
- [<span data-ttu-id="16b12-153">设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="16b12-153">Device health and compliance report</span></span>](machine-reports.md)
