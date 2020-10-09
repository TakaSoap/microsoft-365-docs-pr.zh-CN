---
title: 了解 Microsoft 威胁防护中的高级搜寻查询语言
description: 创建你的第一个威胁搜寻查询，并了解高级搜寻查询语言的常见运算符和其他方面
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、语言、学习、第一个查询、遥测、事件、遥测、自定义检测、架构、kusto、运算符、数据类型、powershell 下载、查询示例
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: de8a2c3d55d887a28500bb82a97e4453861aef46
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399213"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="1b380-104">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="1b380-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b380-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1b380-105">**Applies to:**</span></span>
- <span data-ttu-id="1b380-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="1b380-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="1b380-107">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="1b380-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="1b380-108">您可以使用 Kusto 语法和运算符构造在专用 [架构](advanced-hunting-schema-tables.md)中查找信息的查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-108">You can use Kusto syntax and operators to construct queries that locate information in specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="1b380-109">若要更好地了解这些概念，请运行你的第一个查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="1b380-110">尝试你的第一个查询</span><span class="sxs-lookup"><span data-stu-id="1b380-110">Try your first query</span></span>

<span data-ttu-id="1b380-111">在 Microsoft 365 安全中心中，转到 " **搜寻** " 以运行第一个查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="1b380-112">使用以下示例：</span><span class="sxs-lookup"><span data-stu-id="1b380-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="1b380-113">**[在高级搜寻中运行此查询](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="1b380-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="1b380-114">描述查询并指定要搜索的表</span><span class="sxs-lookup"><span data-stu-id="1b380-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="1b380-115">已将简短注释添加到查询的开头，以描述它的用途。</span><span class="sxs-lookup"><span data-stu-id="1b380-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="1b380-116">如果你后来决定保存查询并将其与组织中的其他人共享，则此注释会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="1b380-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="1b380-117">查询本身通常以表名称开头，后跟多个以管道 () 开头的元素 `|` 。</span><span class="sxs-lookup"><span data-stu-id="1b380-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="1b380-118">在此示例中，我们首先创建两个表的联合，  `DeviceProcessEvents` 并 `DeviceNetworkEvents` 根据需要添加管道元素。</span><span class="sxs-lookup"><span data-stu-id="1b380-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="1b380-119">设置时间范围</span><span class="sxs-lookup"><span data-stu-id="1b380-119">Set the time range</span></span>
<span data-ttu-id="1b380-120">第一个管道元素是范围为前七天的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="1b380-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="1b380-121">限制时间范围有助于确保查询运行良好，返回可管理的结果并不超时。</span><span class="sxs-lookup"><span data-stu-id="1b380-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="1b380-122">检查特定进程</span><span class="sxs-lookup"><span data-stu-id="1b380-122">Check specific processes</span></span>
<span data-ttu-id="1b380-123">时间范围紧跟在搜索代表 PowerShell 应用程序的进程文件名称后。</span><span class="sxs-lookup"><span data-stu-id="1b380-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="1b380-124">搜索特定的命令字符串</span><span class="sxs-lookup"><span data-stu-id="1b380-124">Search for specific command strings</span></span>
<span data-ttu-id="1b380-125">随后，查询将在命令行中查找通常用于使用 PowerShell 下载文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="1b380-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="1b380-126">自定义结果列和长度</span><span class="sxs-lookup"><span data-stu-id="1b380-126">Customize result columns and length</span></span> 
<span data-ttu-id="1b380-127">现在，您的查询清楚地标识了要查找的数据，您可以定义结果的外观。</span><span class="sxs-lookup"><span data-stu-id="1b380-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="1b380-128">`project` 返回特定的列，并 `top` 限制结果数。</span><span class="sxs-lookup"><span data-stu-id="1b380-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="1b380-129">这些运算符有助于确保结果格式良好且相当大且易于处理。</span><span class="sxs-lookup"><span data-stu-id="1b380-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="1b380-130">选择 " **运行查询** " 以查看结果。</span><span class="sxs-lookup"><span data-stu-id="1b380-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="1b380-131">使用查询编辑器右上角的展开图标将重点放在您的搜索查询和结果上。</span><span class="sxs-lookup"><span data-stu-id="1b380-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高级搜寻查询编辑器中的展开控件的图像](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="1b380-133">您可以查看图表中的查询结果，并快速调整筛选器。</span><span class="sxs-lookup"><span data-stu-id="1b380-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="1b380-134">有关指南，请 [阅读使用查询结果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="1b380-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="1b380-135">了解通用查询运算符</span><span class="sxs-lookup"><span data-stu-id="1b380-135">Learn common query operators</span></span>

<span data-ttu-id="1b380-136">你刚刚运行了第一个查询，并大致了解其组件。</span><span class="sxs-lookup"><span data-stu-id="1b380-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="1b380-137">需要略微进行回溯并了解一些基础知识。</span><span class="sxs-lookup"><span data-stu-id="1b380-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="1b380-138">高级搜寻使用的 Kusto 查询语言支持多种运算符，包括以下常见的运算符。</span><span class="sxs-lookup"><span data-stu-id="1b380-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="1b380-139">运算符</span><span class="sxs-lookup"><span data-stu-id="1b380-139">Operator</span></span> | <span data-ttu-id="1b380-140">说明和用法</span><span class="sxs-lookup"><span data-stu-id="1b380-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="1b380-141">从表中筛选出满足谓词的行的子集。</span><span class="sxs-lookup"><span data-stu-id="1b380-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="1b380-142">生成聚合输入表内容的表。</span><span class="sxs-lookup"><span data-stu-id="1b380-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="1b380-143">通过匹配每个表中指定列的值，合并两个表的行以形成新表。</span><span class="sxs-lookup"><span data-stu-id="1b380-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="1b380-144">返回输入记录集中的记录数。</span><span class="sxs-lookup"><span data-stu-id="1b380-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="1b380-145">返回按指定列排序的前 N 条记录。</span><span class="sxs-lookup"><span data-stu-id="1b380-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="1b380-146">最多返回指定的行数。</span><span class="sxs-lookup"><span data-stu-id="1b380-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="1b380-147">选择要包含、重命名或删除的列，然后插入新的计算列。</span><span class="sxs-lookup"><span data-stu-id="1b380-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="1b380-148">创建计算列并将其附加到结果集。</span><span class="sxs-lookup"><span data-stu-id="1b380-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="1b380-149">返回 Expr 在组中采用的一组不同值的动态 (JSON) 数组。</span><span class="sxs-lookup"><span data-stu-id="1b380-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="1b380-150">查找与一组表中的谓词匹配的行。</span><span class="sxs-lookup"><span data-stu-id="1b380-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="1b380-151">若要查看这些操作符的实时示例，请在高级搜寻的**入门**部分中运行它们。</span><span class="sxs-lookup"><span data-stu-id="1b380-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="1b380-152">了解数据类型</span><span class="sxs-lookup"><span data-stu-id="1b380-152">Understand data types</span></span>

<span data-ttu-id="1b380-153">高级搜寻支持 Kusto 数据类型，包括以下通用类型：</span><span class="sxs-lookup"><span data-stu-id="1b380-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="1b380-154">数据类型</span><span class="sxs-lookup"><span data-stu-id="1b380-154">Data type</span></span> | <span data-ttu-id="1b380-155">说明和查询含义</span><span class="sxs-lookup"><span data-stu-id="1b380-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="1b380-156">通常表示事件时间戳的数据和时间信息。</span><span class="sxs-lookup"><span data-stu-id="1b380-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="1b380-157">查看支持的日期时间格式</span><span class="sxs-lookup"><span data-stu-id="1b380-157">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="1b380-158">UTF-8 中括在单引号中的字符字符串 (`'`) 或双引号 (`"`) 。</span><span class="sxs-lookup"><span data-stu-id="1b380-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="1b380-159">阅读有关字符串的详细信息</span><span class="sxs-lookup"><span data-stu-id="1b380-159">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="1b380-160">此数据类型支持 `true` 或 `false` 状态。</span><span class="sxs-lookup"><span data-stu-id="1b380-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="1b380-161">请参阅支持的文字和运算符</span><span class="sxs-lookup"><span data-stu-id="1b380-161">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="1b380-162">32位整数</span><span class="sxs-lookup"><span data-stu-id="1b380-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="1b380-163">64位整数</span><span class="sxs-lookup"><span data-stu-id="1b380-163">64-bit integer</span></span> |

<span data-ttu-id="1b380-164">若要了解有关这些数据类型的详细信息，请 [阅读有关 Kusto 标量数据类型的信息](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)。</span><span class="sxs-lookup"><span data-stu-id="1b380-164">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="1b380-165">编写查询时获取帮助</span><span class="sxs-lookup"><span data-stu-id="1b380-165">Get help as you write queries</span></span>
<span data-ttu-id="1b380-166">利用以下功能更快地编写查询：</span><span class="sxs-lookup"><span data-stu-id="1b380-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="1b380-167">**Autosuggest**—在编写查询时，高级搜寻将提供 IntelliSense 的建议。</span><span class="sxs-lookup"><span data-stu-id="1b380-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="1b380-168">**架构树**—在工作区旁边提供一个架构表示形式，其中包含表及其列的列表。</span><span class="sxs-lookup"><span data-stu-id="1b380-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="1b380-169">有关详细信息，请将鼠标悬停在某个项上。</span><span class="sxs-lookup"><span data-stu-id="1b380-169">For more information, hover over an item.</span></span> <span data-ttu-id="1b380-170">双击某个项，将其插入到查询编辑器中。</span><span class="sxs-lookup"><span data-stu-id="1b380-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="1b380-171">**[架构参考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—门户中的包含表和列说明的引用，以及支持的事件类型 (`ActionType` 值) 和示例查询</span><span class="sxs-lookup"><span data-stu-id="1b380-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="1b380-172">在编辑器中使用多个查询</span><span class="sxs-lookup"><span data-stu-id="1b380-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="1b380-173">您可以使用查询编辑器试用多个查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="1b380-174">若要使用多个查询：</span><span class="sxs-lookup"><span data-stu-id="1b380-174">To use multiple queries:</span></span>

- <span data-ttu-id="1b380-175">使用空行分隔每个查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="1b380-176">将光标放在查询的任何部分，以在运行查询之前选择该查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="1b380-177">这将只运行选定的查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-177">This will run only the selected query.</span></span> <span data-ttu-id="1b380-178">若要运行其他查询，请相应地移动游标，然后选择 " **运行查询**"。</span><span class="sxs-lookup"><span data-stu-id="1b380-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![包含多个查询的查询编辑器的图像](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="1b380-180">使用示例查询</span><span class="sxs-lookup"><span data-stu-id="1b380-180">Use sample queries</span></span>

<span data-ttu-id="1b380-181">**入门**部分提供了使用常用运算符的几个简单查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="1b380-182">请尝试运行这些查询，并对其进行细微修改。</span><span class="sxs-lookup"><span data-stu-id="1b380-182">Try running these queries and making small modifications to them.</span></span>

![高级搜寻窗口的图像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="1b380-184">除了基本查询示例之外，你还可以访问特定威胁搜寻方案的[共享查询](advanced-hunting-shared-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="1b380-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="1b380-185">浏览页面左侧或 [GitHub 查询存储库](https://aka.ms/hunting-queries)的共享查询。</span><span class="sxs-lookup"><span data-stu-id="1b380-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="1b380-186">访问查询语言文档</span><span class="sxs-lookup"><span data-stu-id="1b380-186">Access query language documentation</span></span>

<span data-ttu-id="1b380-187">有关 Kusto 查询语言和受支持运算符的详细信息，请参阅 [Kusto 查询语言文档](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="1b380-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b380-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b380-188">Related topics</span></span>
- [<span data-ttu-id="1b380-189">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="1b380-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1b380-190">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="1b380-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="1b380-191">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="1b380-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1b380-192">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="1b380-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1b380-193">了解架构</span><span class="sxs-lookup"><span data-stu-id="1b380-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1b380-194">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="1b380-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
