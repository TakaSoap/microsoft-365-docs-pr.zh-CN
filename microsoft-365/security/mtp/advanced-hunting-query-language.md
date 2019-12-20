---
title: 了解 Microsoft 威胁防护中的高级搜寻查询语言
description: 创建你的第一个威胁搜寻查询，并了解高级搜寻查询语言的常见运算符和其他方面
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 语言, 学习, 第一个查询, 遥测, 事件, 自定义检测, 架构, kusto, 运算符, 数据类型
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 7c6c92aeec6c1644472103a1aaf175eb813d5758
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808677"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="8a5b1-104">了解高级搜寻查询语言</span><span class="sxs-lookup"><span data-stu-id="8a5b1-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="8a5b1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8a5b1-105">**Applies to:**</span></span>
- <span data-ttu-id="8a5b1-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8a5b1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8a5b1-107">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="8a5b1-108">你可以使用 Kusto 语法和运算符来构建查询，该查询可以在专为高级搜寻构造的[架构](advanced-hunting-schema-tables.md)中查找信息。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="8a5b1-109">若要更好地了解这些概念，请运行你的第一个查询。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="8a5b1-110">尝试你的第一个查询</span><span class="sxs-lookup"><span data-stu-id="8a5b1-110">Try your first query</span></span>

<span data-ttu-id="8a5b1-111">在 Microsoft 365 安全中心，转到“**搜寻**”以运行你的第一个查询。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="8a5b1-112">使用以下示例：</span><span class="sxs-lookup"><span data-stu-id="8a5b1-112">Use the following example:</span></span>

```
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

<span data-ttu-id="8a5b1-113">这是它在高级搜寻中的显示效果。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Defender ATP 高级搜寻查询的图像](../images/advanced-hunting-query-example.png)

<span data-ttu-id="8a5b1-115">查询将从描述其用途的简短批注开始。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="8a5b1-116">如果你以后决定保存查询并与组织中的其他人共享，这将很有用。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

<span data-ttu-id="8a5b1-117">查询本身通常以表名称开头，后跟一系列由管道 (`|`) 开头的元素。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="8a5b1-118">在此示例中，我们首先添加表名称 `DeviceProcessEvents`，然后根据需要添加管道元素。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-118">In this example, we start by adding  with the table name `DeviceProcessEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="8a5b1-119">第一个管道元素是范围为前 7 天的时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="8a5b1-120">尽可能缩小时间范围可以确保查询运行良好、返回易于管理的结果并且不会超时。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```
| where Timestamp > ago(7d)
```

<span data-ttu-id="8a5b1-121">时间范围后紧跟表示 PowerShell 应用程序的文件搜索。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="8a5b1-122">之后，查询将查找通常与 PowerShell 一起使用以下载文件的命令行。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="8a5b1-123">现在，你的查询清楚地标识了要查找的数据，你可以添加定义结果外观的元素。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="8a5b1-124">`project` 将返回特定列，并且 `top` 将限制结果数量，以使结果格式良好、大小合理且易于处理。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp'
```

<span data-ttu-id="8a5b1-125">单击“**运行查询**”以查看结果。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="8a5b1-126">你可以展开屏幕视图，以便专注于你的搜寻查询和结果。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="8a5b1-127">了解高级搜寻的常见查询运算符</span><span class="sxs-lookup"><span data-stu-id="8a5b1-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="8a5b1-128">你已运行第一个查询并对其组成部分有了大致了解，现在是时候回顾并学习一些基础知识了。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="8a5b1-129">高级搜寻使用的 Kusto 查询语言支持多种运算符，包括以下常见的运算符。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="8a5b1-130">运算符</span><span class="sxs-lookup"><span data-stu-id="8a5b1-130">Operator</span></span> | <span data-ttu-id="8a5b1-131">说明和用法</span><span class="sxs-lookup"><span data-stu-id="8a5b1-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="8a5b1-132">从表中筛选出满足谓词的行的子集。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="8a5b1-133">生成聚合输入表内容的表。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="8a5b1-134">通过匹配每个表中指定列的值，合并两个表的行以形成新表。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="8a5b1-135">返回输入记录集中的记录数。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="8a5b1-136">返回按指定列排序的前 N 条记录。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="8a5b1-137">最多返回指定的行数。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="8a5b1-138">选择要包含、重命名或删除的列，然后插入新的计算列。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="8a5b1-139">创建计算列并将其附加到结果集。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="8a5b1-140">返回 Expr 在组中采用的一组不同值的动态 (JSON) 数组。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="8a5b1-141">查找与一组表中的谓词匹配的行。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="8a5b1-142">若要查看这些操作符的实时示例，请在高级搜寻的**入门**部分中运行它们。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="8a5b1-143">了解数据类型及其查询语法含义</span><span class="sxs-lookup"><span data-stu-id="8a5b1-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="8a5b1-144">高级搜寻表中的数据通常分为以下数据类型。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="8a5b1-145">数据类型</span><span class="sxs-lookup"><span data-stu-id="8a5b1-145">Data type</span></span> | <span data-ttu-id="8a5b1-146">说明和查询含义</span><span class="sxs-lookup"><span data-stu-id="8a5b1-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="8a5b1-147">通常表示事件时间戳的数据和时间信息</span><span class="sxs-lookup"><span data-stu-id="8a5b1-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="8a5b1-148">字符串</span><span class="sxs-lookup"><span data-stu-id="8a5b1-148">Character string</span></span> |
| `bool` | <span data-ttu-id="8a5b1-149">True 或 False</span><span class="sxs-lookup"><span data-stu-id="8a5b1-149">True or false</span></span> |
| `int` | <span data-ttu-id="8a5b1-150">32 位数值</span><span class="sxs-lookup"><span data-stu-id="8a5b1-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="8a5b1-151">64 位数值</span><span class="sxs-lookup"><span data-stu-id="8a5b1-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="8a5b1-152">使用示例查询</span><span class="sxs-lookup"><span data-stu-id="8a5b1-152">Use sample queries</span></span>

<span data-ttu-id="8a5b1-153">**入门**部分提供了使用常用运算符的几个简单查询。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="8a5b1-154">请尝试运行这些查询，并对其进行细微修改。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-154">Try running these queries and making small modifications to them.</span></span>

![高级搜寻窗口的图像](../images/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="8a5b1-156">除了基本查询示例之外，你还可以访问特定威胁搜寻方案的[共享查询](advanced-hunting-shared-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="8a5b1-157">浏览页面左侧或 GitHub 查询存储库中的共享查询。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="8a5b1-158">访问查询语言文档</span><span class="sxs-lookup"><span data-stu-id="8a5b1-158">Access query language documentation</span></span>

<span data-ttu-id="8a5b1-159">有关 Kusto 查询语言和受支持运算符的详细信息，请参阅 [Kusto 查询语言文档](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="8a5b1-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8a5b1-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="8a5b1-160">Related topics</span></span>
- [<span data-ttu-id="8a5b1-161">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="8a5b1-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a5b1-162">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="8a5b1-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a5b1-163">在设备和电子邮件中搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="8a5b1-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a5b1-164">了解架构</span><span class="sxs-lookup"><span data-stu-id="8a5b1-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a5b1-165">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="8a5b1-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)