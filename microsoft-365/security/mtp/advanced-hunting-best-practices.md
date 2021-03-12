---
title: Microsoft 365 Defender 中的高级搜寻查询最佳做法
description: 了解如何使用高级搜寻构建快速、高效且无错误的威胁搜寻查询
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
ms.openlocfilehash: e838ce873a1c3ecc0f437f96e75cc2a40d3af79d
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727267"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="74a8f-104">高级搜寻查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="74a8f-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="74a8f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74a8f-105">**Applies to:**</span></span>
- <span data-ttu-id="74a8f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74a8f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="74a8f-107">应用这些建议可更快地获取结果，并避免在运行复杂查询时出现超时。</span><span class="sxs-lookup"><span data-stu-id="74a8f-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="74a8f-108">有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="74a8f-109">了解 CPU 资源配额</span><span class="sxs-lookup"><span data-stu-id="74a8f-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="74a8f-110">根据大小，每个租户都有权访问分配给运行高级搜寻查询的一组 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="74a8f-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="74a8f-111">有关各种服务限制的详细信息， [请阅读有关高级搜寻配额和使用参数的信息](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="74a8f-112">定期运行多个查询的客户应跟踪使用情况，并应用本文中的优化指南，以最大限度地减少因超出配额或使用参数而导致的中断。</span><span class="sxs-lookup"><span data-stu-id="74a8f-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="74a8f-113">常规优化提示</span><span class="sxs-lookup"><span data-stu-id="74a8f-113">General optimization tips</span></span>

- <span data-ttu-id="74a8f-114">**调整新查询的大小**— 如果您怀疑查询将返回大型查询结果集，请首先使用 count 运算符 [来评估它](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="74a8f-115">使用 [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或它的同义词 `take` 以避免大型结果集。</span><span class="sxs-lookup"><span data-stu-id="74a8f-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="74a8f-116">**提前** 应用筛选器 — 应用时间筛选器和其他筛选器以减少数据集，尤其是在使用转换和分析函数（如子字符串 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)替换 [ () 、trim](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction) () 、toupper [ ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)[](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)或 [parse_json () ）之前](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="74a8f-117">在下面的示例中，在筛选运算符减少记录数 () 使用分析函数 [extractjson ](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) 方法。</span><span class="sxs-lookup"><span data-stu-id="74a8f-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="74a8f-118">**Has beats contains**-To avoid searching substrings within words unnecessarily， use the `has` operator instead of `contains` .</span><span class="sxs-lookup"><span data-stu-id="74a8f-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="74a8f-119">了解字符串运算符</span><span class="sxs-lookup"><span data-stu-id="74a8f-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="74a8f-120">**查看特定列**— 查看特定列，而不是在所有列中运行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="74a8f-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="74a8f-121">请勿使用 `*` 检查所有列。</span><span class="sxs-lookup"><span data-stu-id="74a8f-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="74a8f-122">**对于速度，区分** 大小写 — 区分大小写的搜索更为具体，通常性能也更高。</span><span class="sxs-lookup"><span data-stu-id="74a8f-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="74a8f-123">区分大小写的字符串 [运算符的名称，](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)例如 和 `has_cs` `contains_cs` ，通常以 结尾 `_cs` 。</span><span class="sxs-lookup"><span data-stu-id="74a8f-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="74a8f-124">您还可以使用区分大小写的等于运算符 `==` ，而不是 `=~` 。</span><span class="sxs-lookup"><span data-stu-id="74a8f-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="74a8f-125">**分析，不要提取**— 尽可能使用 [分析](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 运算符或分析函数（ [如 parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）。</span><span class="sxs-lookup"><span data-stu-id="74a8f-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="74a8f-126">避免 `matches regex` 使用字符串运算符或 [extract () 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，两者均使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="74a8f-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="74a8f-127">保留对更复杂的方案的正则表达式的使用。</span><span class="sxs-lookup"><span data-stu-id="74a8f-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="74a8f-128">阅读有关分析函数的更多信息</span><span class="sxs-lookup"><span data-stu-id="74a8f-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="74a8f-129">**筛选表不是表达式**-如果可以筛选表列，则不要筛选计算列。</span><span class="sxs-lookup"><span data-stu-id="74a8f-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="74a8f-130">**无三字符术语**- 避免使用带三个字符或更少字符的术语进行比较或筛选。</span><span class="sxs-lookup"><span data-stu-id="74a8f-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="74a8f-131">这些术语未编制索引，匹配它们将需要更多资源。</span><span class="sxs-lookup"><span data-stu-id="74a8f-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="74a8f-132">**选择性地** 项目 — 仅预测所需的列，使结果更易于理解。</span><span class="sxs-lookup"><span data-stu-id="74a8f-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="74a8f-133">在运行联接或类似 [操作之前规划](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 特定列还有助于提高性能。</span><span class="sxs-lookup"><span data-stu-id="74a8f-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="74a8f-134">优化 `join` 运算符</span><span class="sxs-lookup"><span data-stu-id="74a8f-134">Optimize the `join` operator</span></span>
<span data-ttu-id="74a8f-135">联接 [运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 通过匹配指定列中的值来合并两个表中的行。</span><span class="sxs-lookup"><span data-stu-id="74a8f-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="74a8f-136">应用这些提示以优化使用此运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="74a8f-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="74a8f-137">**左侧较小的表**- 运算符将联接语句左侧的表中的记录与右侧 `join` 记录相匹配。</span><span class="sxs-lookup"><span data-stu-id="74a8f-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="74a8f-138">通过使较小的表位于左侧，需要匹配的记录就更少，从而加快了查询速度。</span><span class="sxs-lookup"><span data-stu-id="74a8f-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="74a8f-139">在下表中，在通过帐户 SID 加入之前，我们将左表缩小为仅覆盖三台特定 `DeviceLogonEvents` `IdentityLogonEvents` 设备。</span><span class="sxs-lookup"><span data-stu-id="74a8f-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="74a8f-140">使用 **inner-join 风格**-[](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)默认联接风格或 [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)删除左表中的行，然后通过联接键将每一个匹配项的行返回到右表。</span><span class="sxs-lookup"><span data-stu-id="74a8f-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="74a8f-141">如果左表有多个行，这些行的键值相同，则这些行将进行重复数据删除，以保留每个唯一值的一 `join` 个随机行。</span><span class="sxs-lookup"><span data-stu-id="74a8f-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="74a8f-142">此默认行为可能会从左侧表中排除可提供有用见解的重要信息。</span><span class="sxs-lookup"><span data-stu-id="74a8f-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="74a8f-143">例如，下面的查询将只显示一封包含特定附件的电子邮件，即使该同一附件是使用多个电子邮件发送的：</span><span class="sxs-lookup"><span data-stu-id="74a8f-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="74a8f-144">为了应对此限制，我们应用 [了内部](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 联接风格，具体操作是指定在左侧表中显示所有行，其右侧具有 `kind=inner` 匹配值：</span><span class="sxs-lookup"><span data-stu-id="74a8f-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="74a8f-145">**从时间窗口** 加入记录 — 调查安全事件时，分析员会查找大约在同一时间段发生的相关事件。</span><span class="sxs-lookup"><span data-stu-id="74a8f-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="74a8f-146">在使用时应用相同方法还通过减少要检查的记录数 `join` 来提高性能。</span><span class="sxs-lookup"><span data-stu-id="74a8f-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="74a8f-147">下面的查询在接收恶意文件后 30 分钟内检查登录事件：</span><span class="sxs-lookup"><span data-stu-id="74a8f-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="74a8f-148">**对双方应用** 时间筛选器 - 即使您未调查特定时间窗口，对左侧和右侧表应用时间筛选器可以减少要检查的记录数并 `join` 提高性能。</span><span class="sxs-lookup"><span data-stu-id="74a8f-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="74a8f-149">下面的查询适用于 `Timestamp > ago(1h)` 这两个表，以便它仅联接过去一小时内的记录：</span><span class="sxs-lookup"><span data-stu-id="74a8f-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="74a8f-150">**使用性能提示**— 将提示与 运算符一同使用，以指示后端在运行资源 `join` 密集型操作时分配负载。</span><span class="sxs-lookup"><span data-stu-id="74a8f-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="74a8f-151">详细了解加入提示</span><span class="sxs-lookup"><span data-stu-id="74a8f-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="74a8f-152">例如，收缩提示 **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 有助于在使用基数较高的键（具有许多唯一值的键）加入表时提高查询性能，如下面的 `AccountObjectId` 查询：</span><span class="sxs-lookup"><span data-stu-id="74a8f-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="74a8f-153">当 **[左表](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 较小且最多包含 100，000 (且右表非常大时，广播) 会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="74a8f-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="74a8f-154">例如，下面的查询尝试将具有特定主题的一些电子邮件与表中包含链接的所有邮件 `EmailUrlInfo` 加入：</span><span class="sxs-lookup"><span data-stu-id="74a8f-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="74a8f-155">优化 `summarize` 运算符</span><span class="sxs-lookup"><span data-stu-id="74a8f-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="74a8f-156">summarize [运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 聚合表的内容。</span><span class="sxs-lookup"><span data-stu-id="74a8f-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="74a8f-157">应用这些提示以优化使用此运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="74a8f-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="74a8f-158">**查找不同的** 值 - 通常，使用 `summarize` 查找可能重复的不同的值。</span><span class="sxs-lookup"><span data-stu-id="74a8f-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="74a8f-159">使用它来聚合没有重复值的列是不必要的。</span><span class="sxs-lookup"><span data-stu-id="74a8f-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="74a8f-160">虽然单个电子邮件可以是多个事件的一部分，但以下示例并非有效使用，因为单个电子邮件的网络邮件 `summarize` ID 始终带有唯一的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="74a8f-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="74a8f-161">运算符可以轻松替换为 ，从而在消耗更少 `summarize` `project` 资源时产生可能相同的结果：</span><span class="sxs-lookup"><span data-stu-id="74a8f-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="74a8f-162">以下示例使用效率更高，因为发件人地址向同一收件人地址发送电子邮件可能有多个 `summarize` 不同实例。</span><span class="sxs-lookup"><span data-stu-id="74a8f-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="74a8f-163">此类组合不同，并且可能具有重复项。</span><span class="sxs-lookup"><span data-stu-id="74a8f-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="74a8f-164">**收缩查询**— 虽然最好在具有重复值的列中使用，但相同的列也可以具有高基数或大量 `summarize` 唯一值。 </span><span class="sxs-lookup"><span data-stu-id="74a8f-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="74a8f-165">与 运算符一样，还可以将收缩提示与 一起应用，以分配处理负载，并可能改进在高基数列 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` 上操作时的性能。</span><span class="sxs-lookup"><span data-stu-id="74a8f-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="74a8f-166">下面的查询用于计算不同的收件人电子邮件地址，这些地址可以在数十万大型 `summarize` 组织中运行。</span><span class="sxs-lookup"><span data-stu-id="74a8f-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="74a8f-167">为了提高性能，它包含了 `hint.shufflekey` ：</span><span class="sxs-lookup"><span data-stu-id="74a8f-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="74a8f-168">查询方案</span><span class="sxs-lookup"><span data-stu-id="74a8f-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="74a8f-169">使用进程标识唯一进程标识</span><span class="sxs-lookup"><span data-stu-id="74a8f-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="74a8f-170">进程 ID (PID) 在 Windows 中回收，并重新用于新进程。</span><span class="sxs-lookup"><span data-stu-id="74a8f-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="74a8f-171">它们本身不能用作特定进程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="74a8f-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="74a8f-172">若要获得特定计算机上进程的唯一标识符，请使用进程 ID 以及进程创建时间。</span><span class="sxs-lookup"><span data-stu-id="74a8f-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="74a8f-173">在进程之间联接或汇总数据时，请加入以下列：计算机标识符（`DeviceId` 或 `DeviceName`）、进程 ID（`ProcessId` 或 `InitiatingProcessId`）以及进程创建时间（`ProcessCreationTime` 或 `InitiatingProcessCreationTime`）</span><span class="sxs-lookup"><span data-stu-id="74a8f-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="74a8f-174">以下示例查询将查找通过端口 445 (SMB) 访问 10 个以上 IP 地址（可能扫描文件共享）的进程。</span><span class="sxs-lookup"><span data-stu-id="74a8f-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="74a8f-175">示例查询：</span><span class="sxs-lookup"><span data-stu-id="74a8f-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="74a8f-176">该查询按 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 进行汇总，以便查看单个进程，而不会混用具有同一进程 ID 的多个进程。</span><span class="sxs-lookup"><span data-stu-id="74a8f-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="74a8f-177">查询命令行</span><span class="sxs-lookup"><span data-stu-id="74a8f-177">Query command lines</span></span>
<span data-ttu-id="74a8f-178">有很多方法可以构造命令行来完成任务。</span><span class="sxs-lookup"><span data-stu-id="74a8f-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="74a8f-179">例如，攻击者可能会引用没有路径、没有文件扩展名、使用环境变量或带引号的图像文件。</span><span class="sxs-lookup"><span data-stu-id="74a8f-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="74a8f-180">攻击者还可以更改参数的顺序或添加多个引号和空格。</span><span class="sxs-lookup"><span data-stu-id="74a8f-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="74a8f-181">若要围绕命令行创建更持久的查询，请应用以下做法：</span><span class="sxs-lookup"><span data-stu-id="74a8f-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="74a8f-182">通过匹配 (字段（而不是筛选命令行本身）psexec.exe) 标识已知进程，例如net.exe或) 。 </span><span class="sxs-lookup"><span data-stu-id="74a8f-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="74a8f-183">使用 parse_command_line () [函数分析命令行部分](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="74a8f-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="74a8f-184">查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。</span><span class="sxs-lookup"><span data-stu-id="74a8f-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="74a8f-185">而是使用正则表达式或使用多个单独的 Contains 运算符。</span><span class="sxs-lookup"><span data-stu-id="74a8f-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="74a8f-186">使用不区分大小写的匹配项。</span><span class="sxs-lookup"><span data-stu-id="74a8f-186">Use case insensitive matches.</span></span> <span data-ttu-id="74a8f-187">例如，使用 `=~` 、 `in~` 和 `contains` ，而不是 、 和 `==` `in` `contains_cs` 。</span><span class="sxs-lookup"><span data-stu-id="74a8f-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="74a8f-188">若要缓解命令行混淆技术，请考虑删除引号、将逗号替换为空格，以及将多个连续空格替换为单个空格。</span><span class="sxs-lookup"><span data-stu-id="74a8f-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="74a8f-189">有一些更复杂的模糊处理技术需要其他方法，但这些调整可帮助解决常见问题。</span><span class="sxs-lookup"><span data-stu-id="74a8f-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="74a8f-190">以下示例显示了构建查询的各种方法，该查询查找用于停止net.exe"MpsSvc"的文件： </span><span class="sxs-lookup"><span data-stu-id="74a8f-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="74a8f-191">从外部源中输入数据</span><span class="sxs-lookup"><span data-stu-id="74a8f-191">Ingest data from external sources</span></span>
<span data-ttu-id="74a8f-192">若要将长列表或大型表合并到查询中，请使用 [externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 运算符从指定的 URI 引入数据。</span><span class="sxs-lookup"><span data-stu-id="74a8f-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="74a8f-193">可以从 TXT、CSV、JSON 或其他格式 [的文件获取数据](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="74a8f-194">以下示例演示如何利用 MalwareBazaar 文件提供的恶意软件 SHA-256 哈希的广泛列表 (abuse.ch) 检查电子邮件上的附件：</span><span class="sxs-lookup"><span data-stu-id="74a8f-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a><span data-ttu-id="74a8f-195">分析字符串</span><span class="sxs-lookup"><span data-stu-id="74a8f-195">Parse strings</span></span>
<span data-ttu-id="74a8f-196">可以使用多种函数高效处理需要分析或转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="74a8f-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="74a8f-197">字符串</span><span class="sxs-lookup"><span data-stu-id="74a8f-197">String</span></span> | <span data-ttu-id="74a8f-198">函数</span><span class="sxs-lookup"><span data-stu-id="74a8f-198">Function</span></span> | <span data-ttu-id="74a8f-199">用法示例</span><span class="sxs-lookup"><span data-stu-id="74a8f-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="74a8f-200">命令行</span><span class="sxs-lookup"><span data-stu-id="74a8f-200">Command-lines</span></span> | [<span data-ttu-id="74a8f-201">parse_command_line () </span><span class="sxs-lookup"><span data-stu-id="74a8f-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="74a8f-202">提取命令和所有参数。</span><span class="sxs-lookup"><span data-stu-id="74a8f-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="74a8f-203">Paths</span><span class="sxs-lookup"><span data-stu-id="74a8f-203">Paths</span></span> | [<span data-ttu-id="74a8f-204">parse_path () </span><span class="sxs-lookup"><span data-stu-id="74a8f-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="74a8f-205">提取文件或文件夹路径的各个部分。</span><span class="sxs-lookup"><span data-stu-id="74a8f-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="74a8f-206">版本号</span><span class="sxs-lookup"><span data-stu-id="74a8f-206">Version numbers</span></span> | [<span data-ttu-id="74a8f-207">parse_version () </span><span class="sxs-lookup"><span data-stu-id="74a8f-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="74a8f-208">解构一个版本号，每个节最多包含四个部分，最多八个字符。</span><span class="sxs-lookup"><span data-stu-id="74a8f-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="74a8f-209">使用分析的数据比较版本使用期。</span><span class="sxs-lookup"><span data-stu-id="74a8f-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="74a8f-210">IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="74a8f-210">IPv4 addresses</span></span> | [<span data-ttu-id="74a8f-211">parse_ipv4 () </span><span class="sxs-lookup"><span data-stu-id="74a8f-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="74a8f-212">将 IPv4 地址转换为长整型。</span><span class="sxs-lookup"><span data-stu-id="74a8f-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="74a8f-213">若要比较 IPv4 地址而不转换它们，请使用 [ipv4_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="74a8f-214">IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="74a8f-214">IPv6 addresses</span></span> | [<span data-ttu-id="74a8f-215">parse_ipv6 () </span><span class="sxs-lookup"><span data-stu-id="74a8f-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="74a8f-216">将 IPv4 或 IPv6 地址转换为规范 IPv6 表示法。</span><span class="sxs-lookup"><span data-stu-id="74a8f-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="74a8f-217">若要比较 IPv6 地址，请使用 [ipv6_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="74a8f-218">若要了解所有受支持的分析函数，请阅读 [Kusto 字符串函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。</span><span class="sxs-lookup"><span data-stu-id="74a8f-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="74a8f-219">相关主题</span><span class="sxs-lookup"><span data-stu-id="74a8f-219">Related topics</span></span>
- [<span data-ttu-id="74a8f-220">Kusto 查询语言文档</span><span class="sxs-lookup"><span data-stu-id="74a8f-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="74a8f-221">配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="74a8f-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="74a8f-222">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="74a8f-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="74a8f-223">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="74a8f-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="74a8f-224">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="74a8f-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
