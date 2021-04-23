---
title: 在 Microsoft 365 Defender 中处理高级搜寻查询结果
description: 在 Microsoft 365 Defender 中充分利用高级搜寻返回的查询结果
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， 可视化， 图表， 筛选器， 深化
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952592"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="a991b-104">使用高级搜寻查询结果</span><span class="sxs-lookup"><span data-stu-id="a991b-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a991b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a991b-105">**Applies to:**</span></span>
- <span data-ttu-id="a991b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a991b-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="a991b-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a991b-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a991b-108">虽然你可以构造 [高级](advanced-hunting-overview.md) 搜寻查询以返回非常精确的信息，但您也可以使用查询结果来进一步获得见解并调查特定活动和指示器。</span><span class="sxs-lookup"><span data-stu-id="a991b-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="a991b-109">您可以对查询结果执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a991b-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="a991b-110">以表格或图表查看结果</span><span class="sxs-lookup"><span data-stu-id="a991b-110">View results as a table or chart</span></span>
- <span data-ttu-id="a991b-111">导出表格和图表</span><span class="sxs-lookup"><span data-stu-id="a991b-111">Export tables and charts</span></span>
- <span data-ttu-id="a991b-112">向下钻取到详细的实体信息</span><span class="sxs-lookup"><span data-stu-id="a991b-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="a991b-113">直接从结果调整查询或应用筛选器</span><span class="sxs-lookup"><span data-stu-id="a991b-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="a991b-114">以表或图表查看查询结果</span><span class="sxs-lookup"><span data-stu-id="a991b-114">View query results as a table or chart</span></span>
<span data-ttu-id="a991b-115">默认情况下，高级搜寻将查询结果显示为表格数据。</span><span class="sxs-lookup"><span data-stu-id="a991b-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="a991b-116">还可以显示与图表相同的数据。</span><span class="sxs-lookup"><span data-stu-id="a991b-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="a991b-117">高级搜寻支持以下视图：</span><span class="sxs-lookup"><span data-stu-id="a991b-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="a991b-118">视图类型</span><span class="sxs-lookup"><span data-stu-id="a991b-118">View type</span></span> | <span data-ttu-id="a991b-119">说明</span><span class="sxs-lookup"><span data-stu-id="a991b-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="a991b-120">**Table**</span><span class="sxs-lookup"><span data-stu-id="a991b-120">**Table**</span></span> | <span data-ttu-id="a991b-121">以表格格式显示查询结果</span><span class="sxs-lookup"><span data-stu-id="a991b-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="a991b-122">**柱形图**</span><span class="sxs-lookup"><span data-stu-id="a991b-122">**Column chart**</span></span> | <span data-ttu-id="a991b-123">将 x 轴上的一系列唯一项呈现为垂直条，其高度代表另一个字段的数值</span><span class="sxs-lookup"><span data-stu-id="a991b-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="a991b-124">**堆积柱形图**</span><span class="sxs-lookup"><span data-stu-id="a991b-124">**Stacked column chart**</span></span> | <span data-ttu-id="a991b-125">将 x 轴上的一系列唯一项呈现为堆积竖线，其高度代表来自一个或多个其他字段的数字值</span><span class="sxs-lookup"><span data-stu-id="a991b-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="a991b-126">**饼图**</span><span class="sxs-lookup"><span data-stu-id="a991b-126">**Pie chart**</span></span> | <span data-ttu-id="a991b-127">呈现表示唯一项的节饼图。</span><span class="sxs-lookup"><span data-stu-id="a991b-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="a991b-128">每个饼图的大小表示来自另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="a991b-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="a991b-129">**Donut 图表**</span><span class="sxs-lookup"><span data-stu-id="a991b-129">**Donut chart**</span></span> | <span data-ttu-id="a991b-130">呈现表示唯一项的圆弧。</span><span class="sxs-lookup"><span data-stu-id="a991b-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="a991b-131">每个弧的长度表示来自另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="a991b-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="a991b-132">**折线图**</span><span class="sxs-lookup"><span data-stu-id="a991b-132">**Line chart**</span></span> | <span data-ttu-id="a991b-133">绘制一系列唯一项的数值并连接绘制的值</span><span class="sxs-lookup"><span data-stu-id="a991b-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="a991b-134">**散点图**</span><span class="sxs-lookup"><span data-stu-id="a991b-134">**Scatter chart**</span></span> | <span data-ttu-id="a991b-135">绘制一系列唯一项的数值</span><span class="sxs-lookup"><span data-stu-id="a991b-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="a991b-136">**面积图**</span><span class="sxs-lookup"><span data-stu-id="a991b-136">**Area chart**</span></span> | <span data-ttu-id="a991b-137">绘制一系列唯一项的数值并填充绘制值下方的各部分</span><span class="sxs-lookup"><span data-stu-id="a991b-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="a991b-138">构造有效图表的查询</span><span class="sxs-lookup"><span data-stu-id="a991b-138">Construct queries for effective charts</span></span>
<span data-ttu-id="a991b-139">呈现图表时，高级搜寻会自动标识感兴趣的列和要聚合的数字值。</span><span class="sxs-lookup"><span data-stu-id="a991b-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="a991b-140">若要获取有意义的图表，请构造查询以返回您希望可视化的特定值。</span><span class="sxs-lookup"><span data-stu-id="a991b-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="a991b-141">下面是一些示例查询和生成的图表。</span><span class="sxs-lookup"><span data-stu-id="a991b-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="a991b-142">按严重性表示的警报</span><span class="sxs-lookup"><span data-stu-id="a991b-142">Alerts by severity</span></span>
<span data-ttu-id="a991b-143">使用 `summarize` 运算符可获取要绘制图表的值的数值计数。</span><span class="sxs-lookup"><span data-stu-id="a991b-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="a991b-144">下面的查询使用 `summarize` 运算符按严重性获取警报数。</span><span class="sxs-lookup"><span data-stu-id="a991b-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="a991b-145">呈现结果时，柱形图将每个严重性值显示为单独的列：</span><span class="sxs-lookup"><span data-stu-id="a991b-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="a991b-146">![以柱形图显示的高级搜寻查询结果的图像 按严重性显示 ](../../media/advanced-hunting-column-chart.jpg)
 *为柱形图的警报查询结果*</span><span class="sxs-lookup"><span data-stu-id="a991b-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="a991b-147">按操作系统警报严重性</span><span class="sxs-lookup"><span data-stu-id="a991b-147">Alert severity by operating system</span></span>
<span data-ttu-id="a991b-148">您还可以使用 运算符 `summarize` 为来自多个字段的图表值准备结果。</span><span class="sxs-lookup"><span data-stu-id="a991b-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="a991b-149">例如，你可能想要了解警报严重性如何在操作系统和操作系统之间 (分布) 。</span><span class="sxs-lookup"><span data-stu-id="a991b-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="a991b-150">下面的查询使用运算符从表中拉取操作系统信息，然后使用 计算 `join` `DeviceInfo` 和 `summarize` 列中 `OSPlatform` `Severity` 的值：</span><span class="sxs-lookup"><span data-stu-id="a991b-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="a991b-151">使用堆积柱形图可以最好地可视化这些结果：</span><span class="sxs-lookup"><span data-stu-id="a991b-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="a991b-152">![以堆叠图表显示的高级搜寻查询结果的图像 按操作系统和严重性显示的警报查询结果显示为 ](../../media/advanced-hunting-stacked-chart.jpg)
 *堆积图表*</span><span class="sxs-lookup"><span data-stu-id="a991b-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="a991b-153">十大发件人域中的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="a991b-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="a991b-154">如果处理的值列表并不有限，可以使用 运算符仅绘制具有最多实例 `Top` 的值的图表。</span><span class="sxs-lookup"><span data-stu-id="a991b-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="a991b-155">例如，若要获取钓鱼电子邮件最多的前十个发件人域，请使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="a991b-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="a991b-156">使用饼图视图可有效地显示顶部域的分布：</span><span class="sxs-lookup"><span data-stu-id="a991b-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="a991b-157">![以饼图饼图显示的高级搜寻查询结果的图像，显示钓鱼电子邮件在顶部 ](../../media/advanced-hunting-pie-chart.jpg)
 *发件人域的分布*</span><span class="sxs-lookup"><span data-stu-id="a991b-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="a991b-158">一段时间的文件活动</span><span class="sxs-lookup"><span data-stu-id="a991b-158">File activities over time</span></span>
<span data-ttu-id="a991b-159">将 `summarize` 运算符与 `bin()` 函数一同使用，可以检查一段时间内是否涉及特定指示器的事件。</span><span class="sxs-lookup"><span data-stu-id="a991b-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="a991b-160">下面的查询以 30 分钟的间隔对涉及文件的事件进行计数，以显示与该文件 `invoice.doc` 相关的活动峰值：</span><span class="sxs-lookup"><span data-stu-id="a991b-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="a991b-161">下面的图表清楚地突出显示了具有更多活动涉及的时间段 `invoice.doc` ：</span><span class="sxs-lookup"><span data-stu-id="a991b-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="a991b-162">![高级搜寻查询结果的图像，显示为显示一段时间涉及文件的事件数的线形图 ](../../media/advanced-hunting-line-chart.jpg)
 *的线形图*</span><span class="sxs-lookup"><span data-stu-id="a991b-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="a991b-163">导出表格和图表</span><span class="sxs-lookup"><span data-stu-id="a991b-163">Export tables and charts</span></span>
<span data-ttu-id="a991b-164">运行查询后，选择 **"导出** "将结果保存到本地文件。</span><span class="sxs-lookup"><span data-stu-id="a991b-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="a991b-165">所选视图确定结果的导出方式：</span><span class="sxs-lookup"><span data-stu-id="a991b-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="a991b-166">**表视图** — 查询结果以表格形式导出为 Microsoft Excel 工作簿</span><span class="sxs-lookup"><span data-stu-id="a991b-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="a991b-167">**任何图表** — 查询结果导出为已呈现图表的 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="a991b-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="a991b-168">从查询结果向下钻取</span><span class="sxs-lookup"><span data-stu-id="a991b-168">Drill down from query results</span></span>
<span data-ttu-id="a991b-169">若要快速检查查询结果中的记录，请选择相应的行以打开" **检查记录"** 面板。</span><span class="sxs-lookup"><span data-stu-id="a991b-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="a991b-170">面板根据所选记录提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="a991b-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="a991b-171">**资产** — 记录中发现 (、设备和用户的主要资产汇总) 丰富的可用信息，如风险和曝光级别</span><span class="sxs-lookup"><span data-stu-id="a991b-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="a991b-172">**进程树** - 为包含进程信息的记录生成，并且使用可用的上下文信息进行扩充;通常，返回更多列的查询可产生更丰富的进程树。</span><span class="sxs-lookup"><span data-stu-id="a991b-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="a991b-173">**所有详细信息** - 记录中列的所有值</span><span class="sxs-lookup"><span data-stu-id="a991b-173">**All details** — all the values from the columns in the record</span></span>  

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="a991b-175">若要查看有关查询结果中的特定实体（如计算机、文件、用户、IP 地址或 URL）的详细信息，请选择实体标识符以打开该实体的详细配置文件页。</span><span class="sxs-lookup"><span data-stu-id="a991b-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="a991b-176">调整结果中的查询</span><span class="sxs-lookup"><span data-stu-id="a991b-176">Tweak your queries from the results</span></span>
<span data-ttu-id="a991b-177">右键单击结果集中的值以快速增强查询。</span><span class="sxs-lookup"><span data-stu-id="a991b-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="a991b-178">可以使用这些选项执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a991b-178">You can use the options to:</span></span>

- <span data-ttu-id="a991b-179">显式查找选定值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="a991b-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="a991b-180">从查询中排除选定值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="a991b-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="a991b-181">获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="a991b-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高级搜寻设备结果集](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="a991b-183">筛选查询结果</span><span class="sxs-lookup"><span data-stu-id="a991b-183">Filter the query results</span></span>
<span data-ttu-id="a991b-184">右侧显示的筛选器提供结果集的摘要。</span><span class="sxs-lookup"><span data-stu-id="a991b-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="a991b-185">每列都有其自己的部分，其中列出了该列找到的非重复值和实例数。</span><span class="sxs-lookup"><span data-stu-id="a991b-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="a991b-186">优化查询，在要包含或排除的值上选择 或 按钮，然后选择 `+` `-` "运行 **查询"。**</span><span class="sxs-lookup"><span data-stu-id="a991b-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高级搜寻筛选器的图像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="a991b-188">应用筛选器以修改查询并运行查询后，将相应更新结果。</span><span class="sxs-lookup"><span data-stu-id="a991b-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="a991b-189">本文中的某些表在 Microsoft Defender for Endpoint 中可能不可用。</span><span class="sxs-lookup"><span data-stu-id="a991b-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a991b-190">[打开 Microsoft 365 Defender](m365d-enable.md) 以使用更多数据源搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="a991b-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="a991b-191">你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤将高级搜寻工作流从 [Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)移动到 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="a991b-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a991b-192">相关主题</span><span class="sxs-lookup"><span data-stu-id="a991b-192">Related topics</span></span>
- [<span data-ttu-id="a991b-193">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="a991b-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a991b-194">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="a991b-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a991b-195">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="a991b-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a991b-196">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="a991b-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a991b-197">了解架构</span><span class="sxs-lookup"><span data-stu-id="a991b-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a991b-198">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="a991b-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a991b-199">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="a991b-199">Custom detections overview</span></span>](custom-detections-overview.md)
