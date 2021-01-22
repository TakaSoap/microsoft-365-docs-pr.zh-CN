---
title: Microsoft 365 Defender 中的高级搜寻查询最佳实践
description: 了解如何使用高级搜寻构造快速、高效且无错误的威胁搜寻查询
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构， kusto， 避免超时， 命令行， 进程 ID， 优化， 最佳做法， 分析， 加入， 总结
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928470"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="35c6a-104">高级搜寻查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="35c6a-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="35c6a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="35c6a-105">**Applies to:**</span></span>
- <span data-ttu-id="35c6a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35c6a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="35c6a-107">应用这些建议，以在运行复杂查询时更快地获取结果并避免超时。</span><span class="sxs-lookup"><span data-stu-id="35c6a-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="35c6a-108">有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="35c6a-109">了解 CPU 资源配额</span><span class="sxs-lookup"><span data-stu-id="35c6a-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="35c6a-110">根据大小，每个租户都有权访问为运行高级搜寻查询分配的一组 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="35c6a-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="35c6a-111">有关各种服务限制的详细信息， [请阅读有关高级搜寻配额和使用参数的信息](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="35c6a-112">定期运行多个查询的客户应跟踪使用情况，并应用本文中的优化指南，以最大限度地减少因超出配额或使用参数而导致的中断。</span><span class="sxs-lookup"><span data-stu-id="35c6a-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="35c6a-113">常规优化提示</span><span class="sxs-lookup"><span data-stu-id="35c6a-113">General optimization tips</span></span>

- <span data-ttu-id="35c6a-114">**调整新查询的大小**— 如果您怀疑查询将返回大型查询结果集，请首先使用 [计数运算符进行评估](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="35c6a-115">使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或它的同义词 `take` 以避免大型结果集。</span><span class="sxs-lookup"><span data-stu-id="35c6a-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="35c6a-116">**提前应用** 筛选器 - 应用时间筛选器和其他筛选器以减少数据集，尤其是在使用转换和分析函数（如子字符串 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)替换 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)[剪裁 () 、toupper](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction) [ ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json () ）](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)之前。</span><span class="sxs-lookup"><span data-stu-id="35c6a-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="35c6a-117">在下面的示例中，在筛选运算符减少记录数后，使用分析函数[extractjson () 。](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction)</span><span class="sxs-lookup"><span data-stu-id="35c6a-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="35c6a-118">**具有包含**- 为了避免不必要地搜索单词中的子字符串，请使用 `has` 运算符而不是 `contains` 。</span><span class="sxs-lookup"><span data-stu-id="35c6a-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="35c6a-119">了解字符串运算符</span><span class="sxs-lookup"><span data-stu-id="35c6a-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="35c6a-120">**查看特定列**— 查看特定列，而不是在所有列中运行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="35c6a-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="35c6a-121">请勿用于 `*` 检查所有列。</span><span class="sxs-lookup"><span data-stu-id="35c6a-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="35c6a-122">**速度区分大小写**— 区分大小写的搜索更具体，通常性能更高。</span><span class="sxs-lookup"><span data-stu-id="35c6a-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="35c6a-123">区分大小写的字符串运算符 [的名称](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)，例如 `has_cs` 和 `contains_cs` ，通常以 `_cs` 结尾。</span><span class="sxs-lookup"><span data-stu-id="35c6a-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="35c6a-124">您也可以使用区分大小写的等号运算符 `==` ，而不是 `=~` 。</span><span class="sxs-lookup"><span data-stu-id="35c6a-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="35c6a-125">**分析，不要提取**- 尽可能使用 [分析](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 运算符或分析函数，如 [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="35c6a-126">避免 `matches regex` 字符串运算符或 [提取 () 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，两者均使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="35c6a-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="35c6a-127">保留对更复杂的方案的正则表达式的使用。</span><span class="sxs-lookup"><span data-stu-id="35c6a-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="35c6a-128">阅读有关分析函数的更多信息</span><span class="sxs-lookup"><span data-stu-id="35c6a-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="35c6a-129">**筛选表而不是表达式**— 如果可以筛选表列，则不要筛选计算列。</span><span class="sxs-lookup"><span data-stu-id="35c6a-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="35c6a-130">**无三字符术语**- 避免使用包含 3 个字符或更少字符的术语进行比较或筛选。</span><span class="sxs-lookup"><span data-stu-id="35c6a-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="35c6a-131">这些术语未编制索引，匹配它们将需要更多资源。</span><span class="sxs-lookup"><span data-stu-id="35c6a-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="35c6a-132">**选择性地** 项目 — 通过仅规划所需的列，使结果更易于理解。</span><span class="sxs-lookup"><span data-stu-id="35c6a-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="35c6a-133">在运行联接或类似 [操作之前规划](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 特定列还有助于提高性能。</span><span class="sxs-lookup"><span data-stu-id="35c6a-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="35c6a-134">优化 `join` 运算符</span><span class="sxs-lookup"><span data-stu-id="35c6a-134">Optimize the `join` operator</span></span>
<span data-ttu-id="35c6a-135">联接 [运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 通过匹配指定列中的值来合并两个表中的行。</span><span class="sxs-lookup"><span data-stu-id="35c6a-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="35c6a-136">应用这些提示以优化使用此运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="35c6a-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="35c6a-137">**左侧较小的表**- 运算符将 join 语句左侧的表中的记录与右边的记录 `join` 匹配。</span><span class="sxs-lookup"><span data-stu-id="35c6a-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="35c6a-138">如果左侧有较小的表，则需要匹配的记录就越少，从而加快查询速度。</span><span class="sxs-lookup"><span data-stu-id="35c6a-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="35c6a-139">在下表中，我们将左表缩小为仅涵盖三台特定设备，然后再通过帐户 `DeviceLogonEvents` `IdentityLogonEvents` SID 加入它。</span><span class="sxs-lookup"><span data-stu-id="35c6a-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="35c6a-140">使用 **内部联接风格**- 默认联接 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)风格或 [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)重复删除左表中的行，然后按联接键删除左表中的行，然后再将每个匹配项的行返回到右侧表。</span><span class="sxs-lookup"><span data-stu-id="35c6a-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="35c6a-141">如果左表中有多个行的键值相同，则这些行将被重复数据删除，以保留每个唯一值的单个 `join` 随机行。</span><span class="sxs-lookup"><span data-stu-id="35c6a-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="35c6a-142">此默认行为可能会从左表中排除重要信息，以便提供有用的见解。</span><span class="sxs-lookup"><span data-stu-id="35c6a-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="35c6a-143">例如，下面的查询将只显示一封包含特定附件的电子邮件，即使同一附件是使用多个电子邮件发送的：</span><span class="sxs-lookup"><span data-stu-id="35c6a-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="35c6a-144">为了应对此限制，我们应用 [了内部](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 联接风格，具体操作是指定在左侧表中显示所有行，右侧显示匹配 `kind=inner` 值：</span><span class="sxs-lookup"><span data-stu-id="35c6a-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="35c6a-145">**从时间窗口联接** 记录 — 调查安全事件时，分析员会查找同一时间段内发生的相关事件。</span><span class="sxs-lookup"><span data-stu-id="35c6a-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="35c6a-146">在使用时应用相同方法也会通过减少要检查的记录数 `join` 来提高性能。</span><span class="sxs-lookup"><span data-stu-id="35c6a-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="35c6a-147">下面的查询在接收恶意文件后 30 分钟内检查登录事件：</span><span class="sxs-lookup"><span data-stu-id="35c6a-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="35c6a-148">**对两** 侧应用时间筛选器 - 即使您不调查特定时间窗口，对左侧和右侧表应用时间筛选器也可以减少要检查的记录数并提高性能 `join` 。</span><span class="sxs-lookup"><span data-stu-id="35c6a-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="35c6a-149">下面的查询适用于 `Timestamp > ago(1h)` 这两个表，以便它仅联接过去一小时内的记录：</span><span class="sxs-lookup"><span data-stu-id="35c6a-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="35c6a-150">**使用性能提示**-使用运算符提示，以指示后端在运行资源密集型操作时 `join` 分配负载。</span><span class="sxs-lookup"><span data-stu-id="35c6a-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="35c6a-151">了解有关加入提示的更多信息</span><span class="sxs-lookup"><span data-stu-id="35c6a-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="35c6a-152">例如，使用基数 **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 较高的键（一个具有许多唯一值的键）加入表时，随机提示可帮助提高查询性能，如下面的 `AccountObjectId` 查询：</span><span class="sxs-lookup"><span data-stu-id="35c6a-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="35c6a-153">当 **[左表](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 较小时，广播提示 (最多 100，000 条记录) 右表非常大。</span><span class="sxs-lookup"><span data-stu-id="35c6a-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="35c6a-154">例如，下面的查询尝试将具有特定主题的一些电子邮件与表中包含链接的所有邮件 `EmailUrlInfo` 加入：</span><span class="sxs-lookup"><span data-stu-id="35c6a-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="35c6a-155">优化 `summarize` 运算符</span><span class="sxs-lookup"><span data-stu-id="35c6a-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="35c6a-156">汇总 [运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 聚合表格的内容。</span><span class="sxs-lookup"><span data-stu-id="35c6a-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="35c6a-157">应用这些提示以优化使用此运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="35c6a-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="35c6a-158">**查找不同的值**— 通常，用于 `summarize` 查找可能重复不同的值。</span><span class="sxs-lookup"><span data-stu-id="35c6a-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="35c6a-159">不必使用它来聚合没有重复值的列。</span><span class="sxs-lookup"><span data-stu-id="35c6a-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="35c6a-160">虽然单个电子邮件可以是多个事件的一部分，但下面的示例并非有效使用，因为单个电子邮件的网络邮件 ID 始终带有唯一的 `summarize` 发件人地址。</span><span class="sxs-lookup"><span data-stu-id="35c6a-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="35c6a-161">运算符 `summarize` 可以轻松替换为，在消耗更少资源 `project` 时产生可能相同的结果：</span><span class="sxs-lookup"><span data-stu-id="35c6a-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="35c6a-162">以下示例使用效率更高，因为发件人地址向同一收件人地址发送电子邮件可能有多个 `summarize` 不同实例。</span><span class="sxs-lookup"><span data-stu-id="35c6a-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="35c6a-163">此类组合不同，并且可能具有重复项。</span><span class="sxs-lookup"><span data-stu-id="35c6a-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="35c6a-164">**收缩查询**— 虽然最好在具有重复值的列中使用，但相同的列也可以具有高基数或大量 `summarize` 唯一值。 </span><span class="sxs-lookup"><span data-stu-id="35c6a-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="35c6a-165">与运算符一样，还可以应用随机提示来分配处理负载，并有可能在具有高基数的列上 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` 操作时提高性能。</span><span class="sxs-lookup"><span data-stu-id="35c6a-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="35c6a-166">下面的查询用于统计不同的收件人电子邮件地址，可以在数十万大型组织中 `summarize` 运行。</span><span class="sxs-lookup"><span data-stu-id="35c6a-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="35c6a-167">为了提高性能，它包含了 `hint.shufflekey` ：</span><span class="sxs-lookup"><span data-stu-id="35c6a-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="35c6a-168">查询方案</span><span class="sxs-lookup"><span data-stu-id="35c6a-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="35c6a-169">使用进程标识唯一进程标识</span><span class="sxs-lookup"><span data-stu-id="35c6a-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="35c6a-170">进程 ID (PID) 在 Windows 中回收，并重新用于新进程。</span><span class="sxs-lookup"><span data-stu-id="35c6a-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="35c6a-171">它们本身不能用作特定进程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="35c6a-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="35c6a-172">若要获得特定计算机上进程的唯一标识符，请使用进程 ID 以及进程创建时间。</span><span class="sxs-lookup"><span data-stu-id="35c6a-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="35c6a-173">在进程之间联接或汇总数据时，请加入以下列：计算机标识符（`DeviceId` 或 `DeviceName`）、进程 ID（`ProcessId` 或 `InitiatingProcessId`）以及进程创建时间（`ProcessCreationTime` 或 `InitiatingProcessCreationTime`）</span><span class="sxs-lookup"><span data-stu-id="35c6a-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="35c6a-174">以下示例查询将查找通过端口 445 (SMB) 访问 10 个以上 IP 地址（可能扫描文件共享）的进程。</span><span class="sxs-lookup"><span data-stu-id="35c6a-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="35c6a-175">示例查询：</span><span class="sxs-lookup"><span data-stu-id="35c6a-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="35c6a-176">该查询按 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 进行汇总，以便查看单个进程，而不会混用具有同一进程 ID 的多个进程。</span><span class="sxs-lookup"><span data-stu-id="35c6a-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="35c6a-177">查询命令行</span><span class="sxs-lookup"><span data-stu-id="35c6a-177">Query command lines</span></span>
<span data-ttu-id="35c6a-178">有很多方法可以构造命令行来完成任务。</span><span class="sxs-lookup"><span data-stu-id="35c6a-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="35c6a-179">例如，攻击者可能会引用没有路径、没有文件扩展名、使用环境变量或带引号的图像文件。</span><span class="sxs-lookup"><span data-stu-id="35c6a-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="35c6a-180">攻击者还可以更改参数的顺序或添加多个引号和空格。</span><span class="sxs-lookup"><span data-stu-id="35c6a-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="35c6a-181">若要围绕命令行创建更持久持久查询，请应用以下做法：</span><span class="sxs-lookup"><span data-stu-id="35c6a-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="35c6a-182">通过匹配 (字段psexec.exe) ，而不是在命令行本身进行筛选，来标识已知进程，如net.exe或psexec.exe) 。</span><span class="sxs-lookup"><span data-stu-id="35c6a-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="35c6a-183">使用 [parse_command_line () 函数分析命令行部分](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="35c6a-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="35c6a-184">查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。</span><span class="sxs-lookup"><span data-stu-id="35c6a-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="35c6a-185">而是使用正则表达式或使用多个单独的 Contains 运算符。</span><span class="sxs-lookup"><span data-stu-id="35c6a-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="35c6a-186">使用不区分大小写的匹配项。</span><span class="sxs-lookup"><span data-stu-id="35c6a-186">Use case insensitive matches.</span></span> <span data-ttu-id="35c6a-187">例如，使用 `=~` `in~` ， ， `contains` 而不是 `==` ， 和 `in` `contains_cs` 。</span><span class="sxs-lookup"><span data-stu-id="35c6a-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="35c6a-188">若要缓解命令行模糊处理技术，请考虑删除引号、将逗号替换为空格，以及将多个连续空格替换为单个空格。</span><span class="sxs-lookup"><span data-stu-id="35c6a-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="35c6a-189">有一些更复杂的模糊处理技术需要其他方法，但是这些调整有助于解决常见问题。</span><span class="sxs-lookup"><span data-stu-id="35c6a-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="35c6a-190">以下示例显示构建查询的各种方法，该查询查找net.exe停止防火墙服务"MpsSvc"： </span><span class="sxs-lookup"><span data-stu-id="35c6a-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="35c6a-191">从外部源中输入数据</span><span class="sxs-lookup"><span data-stu-id="35c6a-191">Ingest data from external sources</span></span>
<span data-ttu-id="35c6a-192">若要将长列表或大型表合并到查询中，请使用 [externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 运算符从指定的 URI 引入数据。</span><span class="sxs-lookup"><span data-stu-id="35c6a-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="35c6a-193">可以从 TXT、CSV、JSON 或其他格式 [的文件获取数据](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="35c6a-194">下面的示例演示如何利用 MalwareBazaar (abuse.ch) 提供的恶意软件 SHA-256 哈希列表来检查电子邮件中的附件：</span><span class="sxs-lookup"><span data-stu-id="35c6a-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a><span data-ttu-id="35c6a-195">分析字符串</span><span class="sxs-lookup"><span data-stu-id="35c6a-195">Parse strings</span></span>
<span data-ttu-id="35c6a-196">可以使用多种函数来高效地处理需要分析或转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="35c6a-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="35c6a-197">String</span><span class="sxs-lookup"><span data-stu-id="35c6a-197">String</span></span> | <span data-ttu-id="35c6a-198">函数</span><span class="sxs-lookup"><span data-stu-id="35c6a-198">Function</span></span> | <span data-ttu-id="35c6a-199">用法示例</span><span class="sxs-lookup"><span data-stu-id="35c6a-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="35c6a-200">命令行</span><span class="sxs-lookup"><span data-stu-id="35c6a-200">Command-lines</span></span> | [<span data-ttu-id="35c6a-201">parse_command_line () </span><span class="sxs-lookup"><span data-stu-id="35c6a-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="35c6a-202">提取命令和所有参数。</span><span class="sxs-lookup"><span data-stu-id="35c6a-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="35c6a-203">Paths</span><span class="sxs-lookup"><span data-stu-id="35c6a-203">Paths</span></span> | [<span data-ttu-id="35c6a-204">parse_path () </span><span class="sxs-lookup"><span data-stu-id="35c6a-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="35c6a-205">提取文件或文件夹路径的各个部分。</span><span class="sxs-lookup"><span data-stu-id="35c6a-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="35c6a-206">版本号</span><span class="sxs-lookup"><span data-stu-id="35c6a-206">Version numbers</span></span> | [<span data-ttu-id="35c6a-207">parse_version () </span><span class="sxs-lookup"><span data-stu-id="35c6a-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="35c6a-208">解构一个最多包含四个部分且每个节最多八个字符的版本号。</span><span class="sxs-lookup"><span data-stu-id="35c6a-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="35c6a-209">使用分析的数据比较版本使用期。</span><span class="sxs-lookup"><span data-stu-id="35c6a-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="35c6a-210">IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="35c6a-210">IPv4 addresses</span></span> | [<span data-ttu-id="35c6a-211">parse_ipv4 () </span><span class="sxs-lookup"><span data-stu-id="35c6a-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="35c6a-212">将 IPv4 地址转换为长整型。</span><span class="sxs-lookup"><span data-stu-id="35c6a-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="35c6a-213">若要比较 IPv4 地址而不转换它们，请使用 [ipv4_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="35c6a-214">IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="35c6a-214">IPv6 addresses</span></span> | [<span data-ttu-id="35c6a-215">parse_ipv6 () </span><span class="sxs-lookup"><span data-stu-id="35c6a-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="35c6a-216">将 IPv4 或 IPv6 地址转换为规范 IPv6 表示法。</span><span class="sxs-lookup"><span data-stu-id="35c6a-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="35c6a-217">若要比较 IPv6 地址，请使用 [ipv6_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="35c6a-218">若要了解所有受支持的分析函数，请阅读 [Kusto 字符串函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。</span><span class="sxs-lookup"><span data-stu-id="35c6a-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="35c6a-219">相关主题</span><span class="sxs-lookup"><span data-stu-id="35c6a-219">Related topics</span></span>
- [<span data-ttu-id="35c6a-220">Kusto 查询语言文档</span><span class="sxs-lookup"><span data-stu-id="35c6a-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="35c6a-221">配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="35c6a-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="35c6a-222">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="35c6a-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="35c6a-223">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="35c6a-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="35c6a-224">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="35c6a-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
