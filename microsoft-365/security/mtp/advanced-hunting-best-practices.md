---
title: Microsoft 威胁防护中的高级搜寻查询最佳实践
description: 了解如何使用高级搜寻构建快速、高效和无错误的威胁搜寻查询
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构、kusto、避免超时、命令行、进程 id、优化、最佳实践、分析、联接、汇总
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
ms.openlocfilehash: 3ca475ef6dbdbd66af47216c4130d748788730c2
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419128"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="db6c7-104">高级搜寻查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="db6c7-104">Advanced hunting query best practices</span></span>

<span data-ttu-id="db6c7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db6c7-105">**Applies to:**</span></span>
- <span data-ttu-id="db6c7-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="db6c7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="db6c7-107">应用这些建议以更快地获得结果，并避免在运行复杂查询时超时。</span><span class="sxs-lookup"><span data-stu-id="db6c7-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="db6c7-108">有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="db6c7-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="general-guidance"></a><span data-ttu-id="db6c7-109">一般指导</span><span class="sxs-lookup"><span data-stu-id="db6c7-109">General guidance</span></span>

- <span data-ttu-id="db6c7-110">**调整新查询的大小**—如果您怀疑查询将返回一个大型结果集，请先使用 [count 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)对其进行评估。</span><span class="sxs-lookup"><span data-stu-id="db6c7-110">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="db6c7-111">使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或其同义词 `take` 以避免出现大型结果集。</span><span class="sxs-lookup"><span data-stu-id="db6c7-111">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="db6c7-112">**早期应用筛选器**—应用时间筛选器和其他筛选器以减少数据集，尤其是在使用转换和分析函数（如 [子字符串 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)、将 [ ( # B3 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)、 [trim ( # B5 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)、 [toupper ( # B7 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json ( # B9 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）时。</span><span class="sxs-lookup"><span data-stu-id="db6c7-112">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="db6c7-113">在下面的示例中，分析函数 [extractjson ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) 在筛选运算符减少了记录数量之后使用。</span><span class="sxs-lookup"><span data-stu-id="db6c7-113">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="db6c7-114">**包含节拍**—若要避免在不必要的词中搜索子字符串，请使用 `has` 运算符而不是 `contains` 。</span><span class="sxs-lookup"><span data-stu-id="db6c7-114">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="db6c7-115">了解字符串运算符</span><span class="sxs-lookup"><span data-stu-id="db6c7-115">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="db6c7-116">**查找特定**列—查看特定列，而不是在所有列中运行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="db6c7-116">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="db6c7-117">请勿使用 `*` 检查所有列。</span><span class="sxs-lookup"><span data-stu-id="db6c7-117">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="db6c7-118">**对速度区分大小写**-区分大小写的搜索更具体且性能更高。</span><span class="sxs-lookup"><span data-stu-id="db6c7-118">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="db6c7-119">区分大小写的 [字符串运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)（如 `has_cs` 和）的名称 `contains_cs` 通常以结尾 `_cs` 。</span><span class="sxs-lookup"><span data-stu-id="db6c7-119">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="db6c7-120">您还可以使用区分大小写的 equals 运算符 `==` 而不是 `~=` 。</span><span class="sxs-lookup"><span data-stu-id="db6c7-120">You can also use the case-sensitive equals operator `==` instead of `~=`.</span></span>
- <span data-ttu-id="db6c7-121">**分析、不提取**（如果可能，请使用 [Parse 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 或分析函数，如 [parse_json ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）。</span><span class="sxs-lookup"><span data-stu-id="db6c7-121">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="db6c7-122">避免 `matches regex` 使用字符串运算符或 [提取 ( # A1 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，这两个函数都使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="db6c7-122">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="db6c7-123">为更复杂的方案保留使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="db6c7-123">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="db6c7-124">阅读有关分析函数的详细信息</span><span class="sxs-lookup"><span data-stu-id="db6c7-124">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="db6c7-125">**筛选表不是表达式**—如果可以根据表格列进行筛选，则不能在计算列上进行筛选。</span><span class="sxs-lookup"><span data-stu-id="db6c7-125">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="db6c7-126">**无三字符术语**—避免使用包含三个或更少字符的术语进行比较或筛选。</span><span class="sxs-lookup"><span data-stu-id="db6c7-126">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="db6c7-127">不会对这些术语编制索引，并且匹配这些术语将需要更多资源。</span><span class="sxs-lookup"><span data-stu-id="db6c7-127">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="db6c7-128">**项目**：通过只投影所需的列使您的结果更易于理解。</span><span class="sxs-lookup"><span data-stu-id="db6c7-128">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="db6c7-129">在运行 [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 或类似操作之前投射特定列也有助于提高性能。</span><span class="sxs-lookup"><span data-stu-id="db6c7-129">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="db6c7-130">优化 `join` 运算符</span><span class="sxs-lookup"><span data-stu-id="db6c7-130">Optimize the `join` operator</span></span>
<span data-ttu-id="db6c7-131">[Join 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)通过匹配指定列中的值来合并两个表中的行。</span><span class="sxs-lookup"><span data-stu-id="db6c7-131">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="db6c7-132">应用这些提示以优化使用此运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="db6c7-132">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="db6c7-133">**向左较小的表**- `join` 运算符将联接语句左侧表中的记录与右侧的记录进行匹配。</span><span class="sxs-lookup"><span data-stu-id="db6c7-133">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="db6c7-134">通过在左侧使用较小的表，将需要匹配较少的记录，从而加快查询的运行。</span><span class="sxs-lookup"><span data-stu-id="db6c7-134">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="db6c7-135">在下表中，我们将左表缩小 `DeviceLogonEvents` 为仅包含三个特定设备，然后再 `IdentityLogonEvents` 通过帐户 sid 加入。</span><span class="sxs-lookup"><span data-stu-id="db6c7-135">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="db6c7-136">在将每个匹配项返回到右表中之前，**使用内部联接风格**（默认的[连接风格](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)或[innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates 中的行），然后再将左侧表中的行联接起来。</span><span class="sxs-lookup"><span data-stu-id="db6c7-136">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="db6c7-137">如果左表中有多个行具有相同的键值 `join` ，则这些行将被消除重复，以便为每个唯一值留出单个随机行。</span><span class="sxs-lookup"><span data-stu-id="db6c7-137">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="db6c7-138">此默认行为可能会从左侧表中退出可提供有用见解的重要信息。</span><span class="sxs-lookup"><span data-stu-id="db6c7-138">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="db6c7-139">例如，下面的查询仅显示一个包含特定附件的电子邮件，即使使用多封电子邮件发送相同的附件也是如此：</span><span class="sxs-lookup"><span data-stu-id="db6c7-139">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="db6c7-140">若要解决此限制，请通过[inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)指定 `kind=inner` 将左表中的所有行显示在右侧的匹配值来应用内部联接风格：</span><span class="sxs-lookup"><span data-stu-id="db6c7-140">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="db6c7-141">**从时间窗口加入记录**—在调查安全事件时，分析师将查找在同一时间段内发生的相关事件。</span><span class="sxs-lookup"><span data-stu-id="db6c7-141">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="db6c7-142">在使用时应用相同的方法 `join` 也可减少要检查的记录数，从而提高了优势。</span><span class="sxs-lookup"><span data-stu-id="db6c7-142">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="db6c7-143">下面的查询检查在接收到恶意文件的30分钟内是否发生登录事件：</span><span class="sxs-lookup"><span data-stu-id="db6c7-143">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="db6c7-144">**在两面上应用时间筛选器**—即使您没有调查特定的时间窗口，同时对左侧表和右侧表应用时间筛选器可以减少要检查的记录数并提高 `join` 性能。</span><span class="sxs-lookup"><span data-stu-id="db6c7-144">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="db6c7-145">下面的查询适用于 `Timestamp > ago(1h)` 这两个表，使其仅联接过去一小时内的记录：</span><span class="sxs-lookup"><span data-stu-id="db6c7-145">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="db6c7-146">**使用提示提高性能**-将提示用于 `join` 运算符，以指示后端在运行占用大量资源的操作时分布负载。</span><span class="sxs-lookup"><span data-stu-id="db6c7-146">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="db6c7-147">了解有关联接提示的详细信息</span><span class="sxs-lookup"><span data-stu-id="db6c7-147">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="db6c7-148">例如， **[无序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 可帮助提高查询性能。使用基数较高的键联接表时，具有很多唯一值的键，如 `AccountObjectId` 下面的查询中所示：</span><span class="sxs-lookup"><span data-stu-id="db6c7-148">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="db6c7-149">当左侧表格为最多为100000个记录时， **[广播提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 会有帮助) 而右侧表的大小为极大 (。</span><span class="sxs-lookup"><span data-stu-id="db6c7-149">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="db6c7-150">例如，下面的查询尝试加入几封电子邮件，其中包含包含表中的链接的特定主题的 _所有_ 邮件 `EmailUrlInfo` ：</span><span class="sxs-lookup"><span data-stu-id="db6c7-150">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="db6c7-151">优化 `summarize` 运算符</span><span class="sxs-lookup"><span data-stu-id="db6c7-151">Optimize the `summarize` operator</span></span>
<span data-ttu-id="db6c7-152">[汇总运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator)聚合表的内容。</span><span class="sxs-lookup"><span data-stu-id="db6c7-152">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="db6c7-153">应用这些提示以优化使用此运算符的查询。</span><span class="sxs-lookup"><span data-stu-id="db6c7-153">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="db6c7-154">**查找非重复值**通常，用于 `summarize` 查找可能重复的不同值。</span><span class="sxs-lookup"><span data-stu-id="db6c7-154">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="db6c7-155">将其用于聚合没有重复值的列可能是不必要的。</span><span class="sxs-lookup"><span data-stu-id="db6c7-155">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="db6c7-156">虽然单个电子邮件可以成为多个事件的一部分，但下面的示例并 _不_ 是有效使用， `summarize` 因为单个电子邮件的网络邮件 ID 始终附带唯一的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="db6c7-156">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="db6c7-157">`summarize`操作员可以轻松地替换为 `project` ，在消耗较少资源的情况下可能会产生相同的结果：</span><span class="sxs-lookup"><span data-stu-id="db6c7-157">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="db6c7-158">下面的示例是更有效的使用， `summarize` 因为发件人地址的多个不同实例可以将电子邮件发送到同一收件人地址。</span><span class="sxs-lookup"><span data-stu-id="db6c7-158">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="db6c7-159">此类组合不太明显，并且可能有重复项。</span><span class="sxs-lookup"><span data-stu-id="db6c7-159">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="db6c7-160">**无序查询查询**—虽然 `summarize` 最适用于具有重复值的列，相同的列也可以具有 _较高的基数_ 或大量的唯一值。</span><span class="sxs-lookup"><span data-stu-id="db6c7-160">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="db6c7-161">与 `join` 运算符一样，也可以在对具有高基数的列进行操作时，将 [无序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) 应用于 `summarize` 以分发处理负载，并可能提高性能。</span><span class="sxs-lookup"><span data-stu-id="db6c7-161">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="db6c7-162">下面的查询用于 `summarize` 计算不同的收件人电子邮件地址，该地址可以在大型组织的成百上千个组织中运行。</span><span class="sxs-lookup"><span data-stu-id="db6c7-162">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="db6c7-163">为了提高性能，它采用了 `hint.shufflekey` 以下内容：</span><span class="sxs-lookup"><span data-stu-id="db6c7-163">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="db6c7-164">查询方案</span><span class="sxs-lookup"><span data-stu-id="db6c7-164">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="db6c7-165">确定具有进程 Id 的唯一进程</span><span class="sxs-lookup"><span data-stu-id="db6c7-165">Identify unique processes with process IDs</span></span>
<span data-ttu-id="db6c7-166">进程 ID (PID) 在 Windows 中回收，并重新用于新进程。</span><span class="sxs-lookup"><span data-stu-id="db6c7-166">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="db6c7-167">它们本身不能用作特定进程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="db6c7-167">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="db6c7-168">若要获得特定计算机上进程的唯一标识符，请使用进程 ID 以及进程创建时间。</span><span class="sxs-lookup"><span data-stu-id="db6c7-168">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="db6c7-169">在进程之间联接或汇总数据时，请加入以下列：计算机标识符（`DeviceId` 或 `DeviceName`）、进程 ID（`ProcessId` 或 `InitiatingProcessId`）以及进程创建时间（`ProcessCreationTime` 或 `InitiatingProcessCreationTime`）</span><span class="sxs-lookup"><span data-stu-id="db6c7-169">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="db6c7-170">以下示例查询将查找通过端口 445 (SMB) 访问 10 个以上 IP 地址（可能扫描文件共享）的进程。</span><span class="sxs-lookup"><span data-stu-id="db6c7-170">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="db6c7-171">示例查询：</span><span class="sxs-lookup"><span data-stu-id="db6c7-171">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="db6c7-172">该查询按 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 进行汇总，以便查看单个进程，而不会混用具有同一进程 ID 的多个进程。</span><span class="sxs-lookup"><span data-stu-id="db6c7-172">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="db6c7-173">查询命令行</span><span class="sxs-lookup"><span data-stu-id="db6c7-173">Query command lines</span></span>
<span data-ttu-id="db6c7-174">有很多方法可以构造命令行来完成任务。</span><span class="sxs-lookup"><span data-stu-id="db6c7-174">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="db6c7-175">例如，攻击者可以引用不带路径的图像文件，而无需文件扩展名、使用环境变量或使用引号。</span><span class="sxs-lookup"><span data-stu-id="db6c7-175">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="db6c7-176">攻击者还可以更改参数的顺序或添加多个引号和空格。</span><span class="sxs-lookup"><span data-stu-id="db6c7-176">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="db6c7-177">若要在命令行周围创建更持久的查询，请应用以下做法：</span><span class="sxs-lookup"><span data-stu-id="db6c7-177">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="db6c7-178">通过在 "文件名" 字段上进行匹配（而不是在命令行本身上进行筛选），确定已知的过程 (例如 *net.exe* 或 *psexec.exe*) 。</span><span class="sxs-lookup"><span data-stu-id="db6c7-178">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="db6c7-179">使用[parse_command_line ( # A1 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)分析命令行部分</span><span class="sxs-lookup"><span data-stu-id="db6c7-179">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="db6c7-180">查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。</span><span class="sxs-lookup"><span data-stu-id="db6c7-180">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="db6c7-181">而是使用正则表达式或使用多个单独的 Contains 运算符。</span><span class="sxs-lookup"><span data-stu-id="db6c7-181">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="db6c7-182">使用不区分大小写的匹配项。</span><span class="sxs-lookup"><span data-stu-id="db6c7-182">Use case insensitive matches.</span></span> <span data-ttu-id="db6c7-183">例如，使用 `=~` 、 `in~` 和 `contains` 代替 `==` 、 `in` 和 `contains_cs` 。</span><span class="sxs-lookup"><span data-stu-id="db6c7-183">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="db6c7-184">若要缓解命令行混淆技术，请考虑删除引号、将逗号替换为空格，以及用一个空格替换多个连续空格。</span><span class="sxs-lookup"><span data-stu-id="db6c7-184">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="db6c7-185">有更复杂的模糊处理技术需要其他方法，但这些调整可帮助解决常见的方法。</span><span class="sxs-lookup"><span data-stu-id="db6c7-185">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="db6c7-186">下面的示例展示了用于构造查询的各种方法，该查询将查找用于停止防火墙服务 "MpsSvc" 的文件 *net.exe* ：</span><span class="sxs-lookup"><span data-stu-id="db6c7-186">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="db6c7-187">从外部源中插入数据</span><span class="sxs-lookup"><span data-stu-id="db6c7-187">Ingest data from external sources</span></span>
<span data-ttu-id="db6c7-188">若要将长列表或大型表合并到查询中，请使用 [externaldata 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 从指定的 URI 中插入数据。</span><span class="sxs-lookup"><span data-stu-id="db6c7-188">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="db6c7-189">您可以从文件中获取 TXT、CSV、JSON 或 [其他格式](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)的数据。</span><span class="sxs-lookup"><span data-stu-id="db6c7-189">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="db6c7-190">下面的示例展示了如何利用由 MalwareBazaar (abuse.ch) 提供的恶意软件 SHA-256 哈希列表来检查电子邮件上的附件：</span><span class="sxs-lookup"><span data-stu-id="db6c7-190">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="db6c7-191">分析字符串</span><span class="sxs-lookup"><span data-stu-id="db6c7-191">Parse strings</span></span>
<span data-ttu-id="db6c7-192">您可以使用多种函数来有效处理需要分析或转换的字符串。</span><span class="sxs-lookup"><span data-stu-id="db6c7-192">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="db6c7-193">String</span><span class="sxs-lookup"><span data-stu-id="db6c7-193">String</span></span> | <span data-ttu-id="db6c7-194">函数</span><span class="sxs-lookup"><span data-stu-id="db6c7-194">Function</span></span> | <span data-ttu-id="db6c7-195">用法示例</span><span class="sxs-lookup"><span data-stu-id="db6c7-195">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="db6c7-196">命令行</span><span class="sxs-lookup"><span data-stu-id="db6c7-196">Command-lines</span></span> | [<span data-ttu-id="db6c7-197">parse_command_line ( # B1 </span><span class="sxs-lookup"><span data-stu-id="db6c7-197">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="db6c7-198">提取命令和所有参数。</span><span class="sxs-lookup"><span data-stu-id="db6c7-198">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="db6c7-199">Paths</span><span class="sxs-lookup"><span data-stu-id="db6c7-199">Paths</span></span> | [<span data-ttu-id="db6c7-200">parse_path ( # B1 </span><span class="sxs-lookup"><span data-stu-id="db6c7-200">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="db6c7-201">提取文件或文件夹路径的各个部分。</span><span class="sxs-lookup"><span data-stu-id="db6c7-201">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="db6c7-202">版本号</span><span class="sxs-lookup"><span data-stu-id="db6c7-202">Version numbers</span></span> | [<span data-ttu-id="db6c7-203">parse_version ( # B1 </span><span class="sxs-lookup"><span data-stu-id="db6c7-203">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="db6c7-204">Deconstruct 版本号最多为四个部分，每节最多八个字符。</span><span class="sxs-lookup"><span data-stu-id="db6c7-204">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="db6c7-205">使用已分析的数据比较版本期限。</span><span class="sxs-lookup"><span data-stu-id="db6c7-205">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="db6c7-206">IPv4 地址</span><span class="sxs-lookup"><span data-stu-id="db6c7-206">IPv4 addresses</span></span> | [<span data-ttu-id="db6c7-207">parse_ipv4 ( # B1 </span><span class="sxs-lookup"><span data-stu-id="db6c7-207">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="db6c7-208">将 IPv4 地址转换为长整型。</span><span class="sxs-lookup"><span data-stu-id="db6c7-208">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="db6c7-209">若要比较 IPv4 地址而不进行转换，请使用 [ipv4_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="db6c7-209">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="db6c7-210">IPv6 地址</span><span class="sxs-lookup"><span data-stu-id="db6c7-210">IPv6 addresses</span></span> | [<span data-ttu-id="db6c7-211">parse_ipv6 ( # B1 </span><span class="sxs-lookup"><span data-stu-id="db6c7-211">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="db6c7-212">将 IPv4 或 IPv6 地址转换为规范的 IPv6 表示法。</span><span class="sxs-lookup"><span data-stu-id="db6c7-212">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="db6c7-213">若要比较 IPv6 地址，请使用 [ipv6_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="db6c7-213">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="db6c7-214">若要了解所有受支持的分析函数，请 [阅读有关 Kusto 字符串函数的信息](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。</span><span class="sxs-lookup"><span data-stu-id="db6c7-214">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="db6c7-215">相关主题</span><span class="sxs-lookup"><span data-stu-id="db6c7-215">Related topics</span></span>
- [<span data-ttu-id="db6c7-216">Kusto 查询语言文档</span><span class="sxs-lookup"><span data-stu-id="db6c7-216">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="db6c7-217">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="db6c7-217">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="db6c7-218">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="db6c7-218">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="db6c7-219">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="db6c7-219">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="db6c7-220">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="db6c7-220">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="db6c7-221">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="db6c7-221">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="db6c7-222">了解架构</span><span class="sxs-lookup"><span data-stu-id="db6c7-222">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
