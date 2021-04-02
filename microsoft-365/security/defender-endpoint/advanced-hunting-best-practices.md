---
title: 高级搜寻的查询最佳做法
description: 了解如何在使用高级搜寻时构建快速、高效且无错误的威胁搜寻查询
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 自定义检测， 架构， kusto， 避免超时， 命令行， 进程 ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499258"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="edeae-104">高级搜寻查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="edeae-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="edeae-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="edeae-105">**Applies to:**</span></span>
- [<span data-ttu-id="edeae-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edeae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="edeae-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="edeae-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="edeae-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="edeae-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="edeae-109">优化查询性能</span><span class="sxs-lookup"><span data-stu-id="edeae-109">Optimize query performance</span></span>

<span data-ttu-id="edeae-110">应用这些建议可更快地获取结果，并避免在运行复杂查询时出现超时。</span><span class="sxs-lookup"><span data-stu-id="edeae-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="edeae-111">尝试新查询时，请始终使用 `limit` 来避免出现过大的结果集。</span><span class="sxs-lookup"><span data-stu-id="edeae-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="edeae-112">还可以使用 `count` 初步评估结果集的大小。</span><span class="sxs-lookup"><span data-stu-id="edeae-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="edeae-113">首先使用时间筛选器。</span><span class="sxs-lookup"><span data-stu-id="edeae-113">Use time filters first.</span></span> <span data-ttu-id="edeae-114">理想情况下，将查询限制为七天。</span><span class="sxs-lookup"><span data-stu-id="edeae-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="edeae-115">将预期会删除大多数数据的筛选器放在查询的开头，紧跟在时间筛选器后面。</span><span class="sxs-lookup"><span data-stu-id="edeae-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="edeae-116">查找完整标记时，请使用 `has` 运算符覆盖 `contains`。</span><span class="sxs-lookup"><span data-stu-id="edeae-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="edeae-117">查找特定的列，而不是在所有列上运行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="edeae-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="edeae-118">联接表时，先指定行数较少的表。</span><span class="sxs-lookup"><span data-stu-id="edeae-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="edeae-119">仅 `project` 已联接表的所需列。</span><span class="sxs-lookup"><span data-stu-id="edeae-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="edeae-120">有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="edeae-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="edeae-121">查询提示和易犯错误</span><span class="sxs-lookup"><span data-stu-id="edeae-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="edeae-122">通过进程 ID 查询</span><span class="sxs-lookup"><span data-stu-id="edeae-122">Queries with process IDs</span></span>

<span data-ttu-id="edeae-123">进程 ID (PID) 在 Windows 中回收，并重新用于新进程。</span><span class="sxs-lookup"><span data-stu-id="edeae-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="edeae-124">它们本身不能用作特定进程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="edeae-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="edeae-125">若要获取特定设备上进程的唯一标识符，请使用进程 ID 和进程创建时间。</span><span class="sxs-lookup"><span data-stu-id="edeae-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="edeae-126">当围绕进程加入或汇总数据时，请包含设备标识符 (或) 、进程 ID (或) 以及进程创建时间 (或 `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime`) 。</span><span class="sxs-lookup"><span data-stu-id="edeae-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="edeae-127">以下示例查询将查找通过端口 445 (SMB) 访问 10 个以上 IP 地址（可能扫描文件共享）的进程。</span><span class="sxs-lookup"><span data-stu-id="edeae-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="edeae-128">该查询按 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 进行汇总，以便查看单个进程，而不会混用具有同一进程 ID 的多个进程。</span><span class="sxs-lookup"><span data-stu-id="edeae-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="edeae-129">通过命令行查询</span><span class="sxs-lookup"><span data-stu-id="edeae-129">Queries with command lines</span></span>

<span data-ttu-id="edeae-130">命令行可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="edeae-130">Command lines can vary.</span></span> <span data-ttu-id="edeae-131">在适用的情况下，筛选文件名称，并执行模糊匹配。</span><span class="sxs-lookup"><span data-stu-id="edeae-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="edeae-132">有很多方法可以构造命令行来完成任务。</span><span class="sxs-lookup"><span data-stu-id="edeae-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="edeae-133">例如，攻击者可以使用环境变量或引号引用带/不带路径、不带文件扩展名的映像文件。</span><span class="sxs-lookup"><span data-stu-id="edeae-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="edeae-134">此外，攻击者还可以更改参数的顺序或添加多个引号和空格。</span><span class="sxs-lookup"><span data-stu-id="edeae-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="edeae-135">若要使用命令行创建更持久的查询，请采用以下做法：</span><span class="sxs-lookup"><span data-stu-id="edeae-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="edeae-136">通过匹配文件名字段来识别已知进程（例如 *net.exe* 或 *psexec.exe*），而不是在命令行字段上进行筛选。</span><span class="sxs-lookup"><span data-stu-id="edeae-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="edeae-137">查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。</span><span class="sxs-lookup"><span data-stu-id="edeae-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="edeae-138">而是使用正则表达式或使用多个单独的 Contains 运算符。</span><span class="sxs-lookup"><span data-stu-id="edeae-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="edeae-139">使用不区分大小写的匹配项。</span><span class="sxs-lookup"><span data-stu-id="edeae-139">Use case insensitive matches.</span></span> <span data-ttu-id="edeae-140">例如，使用 `=~` 、 `in~` 和 `contains` ，而不是 、 `==` `in` 和 `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="edeae-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="edeae-141">为了减轻 DOS 命令行混淆技术的影响，请考虑删除引号，将逗号替换为空格，并用单个空格替换多个连续的空格。</span><span class="sxs-lookup"><span data-stu-id="edeae-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="edeae-142">请注意，还有一些更复杂的 DOS 混淆技术需要适用其他方法，但这些方法可以帮助解决最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="edeae-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="edeae-143">下面的示例演示了构造查询的各种方式，该查询将查找 *net.exe* 文件以停止 Windows Defender 防火墙服务：</span><span class="sxs-lookup"><span data-stu-id="edeae-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

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

> <span data-ttu-id="edeae-144">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="edeae-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="edeae-145">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="edeae-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="edeae-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="edeae-146">Related topics</span></span>

- [<span data-ttu-id="edeae-147">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="edeae-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="edeae-148">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="edeae-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="edeae-149">了解架构</span><span class="sxs-lookup"><span data-stu-id="edeae-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="edeae-150">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="edeae-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="edeae-151">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="edeae-151">Custom detections overview</span></span>](overview-custom-detections.md)
