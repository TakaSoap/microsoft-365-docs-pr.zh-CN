---
title: Microsoft 威胁防护中的高级搜寻最佳做法
description: 了解如何在使用高级搜寻时构建快速、高效且无错误的威胁搜寻查询
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、避免超时、命令行、进程 id
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
ms.openlocfilehash: b5cd421770469e674e66045ac341d12a2808da09
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602837"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="d87d8-104">高级搜寻查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d87d8-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="d87d8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d87d8-105">**Applies to:**</span></span>
- <span data-ttu-id="d87d8-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="d87d8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a><span data-ttu-id="d87d8-107">优化查询性能</span><span class="sxs-lookup"><span data-stu-id="d87d8-107">Optimize query performance</span></span>
<span data-ttu-id="d87d8-108">应用这些建议可以更快地获得结果，并在运行复杂查询时避免超时：</span><span class="sxs-lookup"><span data-stu-id="d87d8-108">Apply these recommendations to get results faster and avoid timeouts while running complex queries:</span></span>
- <span data-ttu-id="d87d8-109">尝试新查询时，请始终使用 `limit` 来避免出现过大的结果集。</span><span class="sxs-lookup"><span data-stu-id="d87d8-109">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="d87d8-110">还可以使用 `count` 初步评估结果集的大小。</span><span class="sxs-lookup"><span data-stu-id="d87d8-110">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="d87d8-111">首先使用时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="d87d8-111">Use time filters first.</span></span> <span data-ttu-id="d87d8-112">理想情况下，将查询限制为偶数天。</span><span class="sxs-lookup"><span data-stu-id="d87d8-112">Ideally, limit your queries to even days.</span></span>
- <span data-ttu-id="d87d8-113">将预期会删除大多数数据的筛选器放在查询的开头，紧跟在时间筛选器后面。</span><span class="sxs-lookup"><span data-stu-id="d87d8-113">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="d87d8-114">查找完整标记时，请使用 `has` 运算符覆盖 `contains`。</span><span class="sxs-lookup"><span data-stu-id="d87d8-114">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="d87d8-115">查找特定的列，而不是在所有列上运行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="d87d8-115">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="d87d8-116">联接表时，先指定行数较少的表。</span><span class="sxs-lookup"><span data-stu-id="d87d8-116">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="d87d8-117">仅 `project` 已联接表的所需列。</span><span class="sxs-lookup"><span data-stu-id="d87d8-117">`project` only the necessary columns from tables you've joined.</span></span>

>[!Tip]
><span data-ttu-id="d87d8-118">有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="d87d8-118">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="d87d8-119">查询提示和易犯错误</span><span class="sxs-lookup"><span data-stu-id="d87d8-119">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="d87d8-120">通过进程 ID 查询</span><span class="sxs-lookup"><span data-stu-id="d87d8-120">Queries with process IDs</span></span>
<span data-ttu-id="d87d8-121">进程 ID (PID) 在 Windows 中回收，并重新用于新进程。</span><span class="sxs-lookup"><span data-stu-id="d87d8-121">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="d87d8-122">它们本身不能用作特定进程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d87d8-122">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="d87d8-123">若要获得特定计算机上进程的唯一标识符，请使用进程 ID 以及进程创建时间。</span><span class="sxs-lookup"><span data-stu-id="d87d8-123">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="d87d8-124">在进程之间联接或汇总数据时，请加入以下列：计算机标识符（`DeviceId` 或 `DeviceName`）、进程 ID（`ProcessId` 或 `InitiatingProcessId`）以及进程创建时间（`ProcessCreationTime` 或 `InitiatingProcessCreationTime`）</span><span class="sxs-lookup"><span data-stu-id="d87d8-124">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="d87d8-125">以下示例查询将查找通过端口 445 (SMB) 访问 10 个以上 IP 地址（可能扫描文件共享）的进程。</span><span class="sxs-lookup"><span data-stu-id="d87d8-125">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="d87d8-126">示例查询：</span><span class="sxs-lookup"><span data-stu-id="d87d8-126">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="d87d8-127">该查询按 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 进行汇总，以便查看单个进程，而不会混用具有同一进程 ID 的多个进程。</span><span class="sxs-lookup"><span data-stu-id="d87d8-127">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="d87d8-128">通过命令行查询</span><span class="sxs-lookup"><span data-stu-id="d87d8-128">Queries with command lines</span></span>

<span data-ttu-id="d87d8-129">命令行可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="d87d8-129">Command lines can vary.</span></span> <span data-ttu-id="d87d8-130">在适用的情况下，筛选文件名称，并执行模糊匹配。</span><span class="sxs-lookup"><span data-stu-id="d87d8-130">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="d87d8-131">有很多方法可以构造命令行来完成任务。</span><span class="sxs-lookup"><span data-stu-id="d87d8-131">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="d87d8-132">例如，攻击者可以使用环境变量或引号引用带/不带路径、不带文件扩展名的映像文件。</span><span class="sxs-lookup"><span data-stu-id="d87d8-132">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="d87d8-133">此外，攻击者还可以更改参数的顺序或添加多个引号和空格。</span><span class="sxs-lookup"><span data-stu-id="d87d8-133">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="d87d8-134">若要使用命令行创建更持久的查询，请采用以下做法：</span><span class="sxs-lookup"><span data-stu-id="d87d8-134">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="d87d8-135">通过匹配文件名字段来识别已知进程（例如 *net.exe* 或 *psexec.exe*），而不是在命令行字段上进行筛选。</span><span class="sxs-lookup"><span data-stu-id="d87d8-135">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="d87d8-136">查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。</span><span class="sxs-lookup"><span data-stu-id="d87d8-136">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="d87d8-137">而是使用正则表达式或使用多个单独的 Contains 运算符。</span><span class="sxs-lookup"><span data-stu-id="d87d8-137">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="d87d8-138">使用不区分大小写的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d87d8-138">Use case insensitive matches.</span></span> <span data-ttu-id="d87d8-139">例如，使用 `=~``in~` 和 `contains` 代替 `==`、`in` 和 `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="d87d8-139">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`</span></span>
- <span data-ttu-id="d87d8-140">为了减轻 DOS 命令行混淆技术的影响，请考虑删除引号，将逗号替换为空格，并用单个空格替换多个连续的空格。</span><span class="sxs-lookup"><span data-stu-id="d87d8-140">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="d87d8-141">请注意，还有一些更复杂的 DOS 混淆技术需要适用其他方法，但这些方法可以帮助解决最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="d87d8-141">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="d87d8-142">下面的示例演示了构造查询的各种方式，该查询将查找 *net.exe* 文件以停止 Windows Defender 防火墙服务：</span><span class="sxs-lookup"><span data-stu-id="d87d8-142">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```
## <a name="related-topics"></a><span data-ttu-id="d87d8-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="d87d8-143">Related topics</span></span>
- [<span data-ttu-id="d87d8-144">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="d87d8-144">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d87d8-145">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d87d8-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d87d8-146">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d87d8-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d87d8-147">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="d87d8-147">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d87d8-148">了解架构</span><span class="sxs-lookup"><span data-stu-id="d87d8-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
