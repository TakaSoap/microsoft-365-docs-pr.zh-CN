---
title: 了解 Microsoft 威胁防护中的高级搜寻查询语言
description: 创建你的第一个威胁搜寻查询，并了解高级搜寻查询语言的常见运算符和其他方面
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、语言、学习、第一个查询、遥测、事件、遥测、自定义检测、架构、kusto、运算符、数据类型、powershell下载，查询示例
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
ms.openlocfilehash: 5715baaccd95d975f7d15196906a6326177bbc2e
ms.sourcegitcommit: 242f051c4cf3683f8c1a5da20ceca81bde212cfc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982002"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="93732-104">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="93732-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="93732-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="93732-105">**Applies to:**</span></span>
- <span data-ttu-id="93732-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="93732-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="93732-107">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="93732-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="93732-108">你可以使用 Kusto 语法和运算符来构建查询，该查询可以在专为高级搜寻构造的[架构](advanced-hunting-schema-tables.md)中查找信息。</span><span class="sxs-lookup"><span data-stu-id="93732-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="93732-109">若要更好地了解这些概念，请运行你的第一个查询。</span><span class="sxs-lookup"><span data-stu-id="93732-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="93732-110">尝试你的第一个查询</span><span class="sxs-lookup"><span data-stu-id="93732-110">Try your first query</span></span>

<span data-ttu-id="93732-111">在 Microsoft 365 安全中心中，转到 "**搜寻**" 以运行第一个查询。</span><span class="sxs-lookup"><span data-stu-id="93732-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="93732-112">使用以下示例：</span><span class="sxs-lookup"><span data-stu-id="93732-112">Use the following example:</span></span>

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

<span data-ttu-id="93732-113">这是它在高级搜寻中的显示效果。</span><span class="sxs-lookup"><span data-stu-id="93732-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft 威胁防护高级搜寻查询的图像](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="93732-115">描述查询并指定要搜索的表</span><span class="sxs-lookup"><span data-stu-id="93732-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="93732-116">已将简短注释添加到查询的开头，以描述它的用途。</span><span class="sxs-lookup"><span data-stu-id="93732-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="93732-117">如果你后来决定保存查询并与组织中的其他人共享它，这将会帮助。</span><span class="sxs-lookup"><span data-stu-id="93732-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="93732-118">查询本身通常以表名称开头，后跟一系列由管道 (`|`) 开头的元素。</span><span class="sxs-lookup"><span data-stu-id="93732-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="93732-119">在此示例中，我们首先创建两个表的联合， `DeviceProcessEvents`并`DeviceNetworkEvents`根据需要添加管道元素。</span><span class="sxs-lookup"><span data-stu-id="93732-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="93732-120">设置时间范围</span><span class="sxs-lookup"><span data-stu-id="93732-120">Set the time range</span></span>
<span data-ttu-id="93732-121">第一个管道元素是范围为前七天的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="93732-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="93732-122">尽可能缩小时间范围可以确保查询运行良好、返回易于管理的结果并且不会超时。</span><span class="sxs-lookup"><span data-stu-id="93732-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="93732-123">检查特定进程</span><span class="sxs-lookup"><span data-stu-id="93732-123">Check specific processes</span></span>
<span data-ttu-id="93732-124">时间范围紧跟在搜索代表 PowerShell 应用程序的进程文件名称后。</span><span class="sxs-lookup"><span data-stu-id="93732-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="93732-125">搜索特定的命令字符串</span><span class="sxs-lookup"><span data-stu-id="93732-125">Search for specific command strings</span></span>
<span data-ttu-id="93732-126">随后，查询将在命令行中查找通常用于使用 PowerShell 下载文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="93732-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="93732-127">自定义结果列和长度</span><span class="sxs-lookup"><span data-stu-id="93732-127">Customize result columns and length</span></span> 
<span data-ttu-id="93732-128">现在，你的查询清楚地标识了要查找的数据，你可以添加定义结果外观的元素。</span><span class="sxs-lookup"><span data-stu-id="93732-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="93732-129">`project`返回特定的列， `top`并限制结果数。</span><span class="sxs-lookup"><span data-stu-id="93732-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="93732-130">这些运算符有助于确保结果格式良好且相当大且易于处理。</span><span class="sxs-lookup"><span data-stu-id="93732-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="93732-131">单击“**运行查询**”以查看结果。</span><span class="sxs-lookup"><span data-stu-id="93732-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="93732-132">选择查询编辑器右上角的展开图标以重点关注您的搜索查询和结果。</span><span class="sxs-lookup"><span data-stu-id="93732-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高级搜寻查询编辑器中的展开控件的图像](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="93732-134">您可以查看图表中的查询结果，并快速调整筛选器。</span><span class="sxs-lookup"><span data-stu-id="93732-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="93732-135">有关指南，请[阅读使用查询结果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="93732-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="93732-136">了解高级搜寻的常见查询运算符</span><span class="sxs-lookup"><span data-stu-id="93732-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="93732-137">你已运行第一个查询并对其组成部分有了大致了解，现在是时候回顾并学习一些基础知识了。</span><span class="sxs-lookup"><span data-stu-id="93732-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="93732-138">高级搜寻使用的 Kusto 查询语言支持多种运算符，包括以下常见的运算符。</span><span class="sxs-lookup"><span data-stu-id="93732-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="93732-139">运算符</span><span class="sxs-lookup"><span data-stu-id="93732-139">Operator</span></span> | <span data-ttu-id="93732-140">说明和用法</span><span class="sxs-lookup"><span data-stu-id="93732-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="93732-141">从表中筛选出满足谓词的行的子集。</span><span class="sxs-lookup"><span data-stu-id="93732-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="93732-142">生成聚合输入表内容的表。</span><span class="sxs-lookup"><span data-stu-id="93732-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="93732-143">通过匹配每个表中指定列的值，合并两个表的行以形成新表。</span><span class="sxs-lookup"><span data-stu-id="93732-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="93732-144">返回输入记录集中的记录数。</span><span class="sxs-lookup"><span data-stu-id="93732-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="93732-145">返回按指定列排序的前 N 条记录。</span><span class="sxs-lookup"><span data-stu-id="93732-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="93732-146">最多返回指定的行数。</span><span class="sxs-lookup"><span data-stu-id="93732-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="93732-147">选择要包含、重命名或删除的列，然后插入新的计算列。</span><span class="sxs-lookup"><span data-stu-id="93732-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="93732-148">创建计算列并将其附加到结果集。</span><span class="sxs-lookup"><span data-stu-id="93732-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="93732-149">返回 Expr 在组中采用的一组不同值的动态 (JSON) 数组。</span><span class="sxs-lookup"><span data-stu-id="93732-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="93732-150">查找与一组表中的谓词匹配的行。</span><span class="sxs-lookup"><span data-stu-id="93732-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="93732-151">若要查看这些操作符的实时示例，请在高级搜寻的**入门**部分中运行它们。</span><span class="sxs-lookup"><span data-stu-id="93732-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="93732-152">了解数据类型及其查询语法含义</span><span class="sxs-lookup"><span data-stu-id="93732-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="93732-153">高级搜寻表中的数据通常分为以下数据类型。</span><span class="sxs-lookup"><span data-stu-id="93732-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="93732-154">数据类型</span><span class="sxs-lookup"><span data-stu-id="93732-154">Data type</span></span> | <span data-ttu-id="93732-155">说明和查询含义</span><span class="sxs-lookup"><span data-stu-id="93732-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="93732-156">通常表示事件时间戳的数据和时间信息</span><span class="sxs-lookup"><span data-stu-id="93732-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="93732-157">字符串</span><span class="sxs-lookup"><span data-stu-id="93732-157">Character string</span></span> |
| `bool` | <span data-ttu-id="93732-158">True 或 False</span><span class="sxs-lookup"><span data-stu-id="93732-158">True or false</span></span> |
| `int` | <span data-ttu-id="93732-159">32 位数值</span><span class="sxs-lookup"><span data-stu-id="93732-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="93732-160">64 位数值</span><span class="sxs-lookup"><span data-stu-id="93732-160">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="93732-161">使用示例查询</span><span class="sxs-lookup"><span data-stu-id="93732-161">Use sample queries</span></span>

<span data-ttu-id="93732-162">**入门**部分提供了使用常用运算符的几个简单查询。</span><span class="sxs-lookup"><span data-stu-id="93732-162">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="93732-163">请尝试运行这些查询，并对其进行细微修改。</span><span class="sxs-lookup"><span data-stu-id="93732-163">Try running these queries and making small modifications to them.</span></span>

![高级搜寻窗口的图像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="93732-165">除了基本查询示例之外，你还可以访问特定威胁搜寻方案的[共享查询](advanced-hunting-shared-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="93732-165">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="93732-166">浏览页面左侧或 GitHub 查询存储库中的共享查询。</span><span class="sxs-lookup"><span data-stu-id="93732-166">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="93732-167">访问查询语言文档</span><span class="sxs-lookup"><span data-stu-id="93732-167">Access query language documentation</span></span>

<span data-ttu-id="93732-168">有关 Kusto 查询语言和受支持运算符的详细信息，请参阅 [Kusto 查询语言文档](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="93732-168">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="93732-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="93732-169">Related topics</span></span>
- [<span data-ttu-id="93732-170">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="93732-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="93732-171">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="93732-171">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="93732-172">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="93732-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="93732-173">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="93732-173">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="93732-174">了解架构</span><span class="sxs-lookup"><span data-stu-id="93732-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="93732-175">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="93732-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
