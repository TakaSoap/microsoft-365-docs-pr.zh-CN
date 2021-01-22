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
# <a name="advanced-hunting-query-best-practices"></a>高级搜寻查询最佳做法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

应用这些建议，以在运行复杂查询时更快地获取结果并避免超时。 有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。

## <a name="understand-cpu-resource-quotas"></a>了解 CPU 资源配额
根据大小，每个租户都有权访问为运行高级搜寻查询分配的一组 CPU 资源。 有关各种服务限制的详细信息， [请阅读有关高级搜寻配额和使用参数的信息](advanced-hunting-limits.md)。

定期运行多个查询的客户应跟踪使用情况，并应用本文中的优化指南，以最大限度地减少因超出配额或使用参数而导致的中断。

## <a name="general-optimization-tips"></a>常规优化提示

- **调整新查询的大小**— 如果您怀疑查询将返回大型查询结果集，请首先使用 [计数运算符进行评估](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。 使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或它的同义词 `take` 以避免大型结果集。
- **提前应用** 筛选器 - 应用时间筛选器和其他筛选器以减少数据集，尤其是在使用转换和分析函数（如子字符串 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)替换 [ () 、](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)[剪裁 () 、toupper](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction) [ ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json () ）](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)之前。 在下面的示例中，在筛选运算符减少记录数后，使用分析函数[extractjson () 。](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction)

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **具有包含**- 为了避免不必要地搜索单词中的子字符串，请使用 `has` 运算符而不是 `contains` 。 [了解字符串运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **查看特定列**— 查看特定列，而不是在所有列中运行全文搜索。 请勿用于 `*` 检查所有列。
- **速度区分大小写**— 区分大小写的搜索更具体，通常性能更高。 区分大小写的字符串运算符 [的名称](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)，例如 `has_cs` 和 `contains_cs` ，通常以 `_cs` 结尾。 您也可以使用区分大小写的等号运算符 `==` ，而不是 `=~` 。
- **分析，不要提取**- 尽可能使用 [分析](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 运算符或分析函数，如 [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)。 避免 `matches regex` 字符串运算符或 [提取 () 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，两者均使用正则表达式。 保留对更复杂的方案的正则表达式的使用。 [阅读有关分析函数的更多信息](#parse-strings)
- **筛选表而不是表达式**— 如果可以筛选表列，则不要筛选计算列。
- **无三字符术语**- 避免使用包含 3 个字符或更少字符的术语进行比较或筛选。 这些术语未编制索引，匹配它们将需要更多资源。
- **选择性地** 项目 — 通过仅规划所需的列，使结果更易于理解。 在运行联接或类似 [操作之前规划](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 特定列还有助于提高性能。

## <a name="optimize-the-join-operator"></a>优化 `join` 运算符
联接 [运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 通过匹配指定列中的值来合并两个表中的行。 应用这些提示以优化使用此运算符的查询。

- **左侧较小的表**- 运算符将 join 语句左侧的表中的记录与右边的记录 `join` 匹配。 如果左侧有较小的表，则需要匹配的记录就越少，从而加快查询速度。 

    在下表中，我们将左表缩小为仅涵盖三台特定设备，然后再通过帐户 `DeviceLogonEvents` `IdentityLogonEvents` SID 加入它。
 
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

- 使用 **内部联接风格**- 默认联接 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)风格或 [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)重复删除左表中的行，然后按联接键删除左表中的行，然后再将每个匹配项的行返回到右侧表。 如果左表中有多个行的键值相同，则这些行将被重复数据删除，以保留每个唯一值的单个 `join` 随机行。

    此默认行为可能会从左表中排除重要信息，以便提供有用的见解。 例如，下面的查询将只显示一封包含特定附件的电子邮件，即使同一附件是使用多个电子邮件发送的：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    为了应对此限制，我们应用 [了内部](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) 联接风格，具体操作是指定在左侧表中显示所有行，右侧显示匹配 `kind=inner` 值：
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **从时间窗口联接** 记录 — 调查安全事件时，分析员会查找同一时间段内发生的相关事件。 在使用时应用相同方法也会通过减少要检查的记录数 `join` 来提高性能。
    
    下面的查询在接收恶意文件后 30 分钟内检查登录事件：

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
- **对两** 侧应用时间筛选器 - 即使您不调查特定时间窗口，对左侧和右侧表应用时间筛选器也可以减少要检查的记录数并提高性能 `join` 。 下面的查询适用于 `Timestamp > ago(1h)` 这两个表，以便它仅联接过去一小时内的记录：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **使用性能提示**-使用运算符提示，以指示后端在运行资源密集型操作时 `join` 分配负载。 [了解有关加入提示的更多信息](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    例如，使用基数 **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 较高的键（一个具有许多唯一值的键）加入表时，随机提示可帮助提高查询性能，如下面的 `AccountObjectId` 查询：

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    当 **[左表](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 较小时，广播提示 (最多 100，000 条记录) 右表非常大。 例如，下面的查询尝试将具有特定主题的一些电子邮件与表中包含链接的所有邮件 `EmailUrlInfo` 加入：

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>优化 `summarize` 运算符
汇总 [运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 聚合表格的内容。 应用这些提示以优化使用此运算符的查询。

- **查找不同的值**— 通常，用于 `summarize` 查找可能重复不同的值。 不必使用它来聚合没有重复值的列。

    虽然单个电子邮件可以是多个事件的一部分，但下面的示例并非有效使用，因为单个电子邮件的网络邮件 ID 始终带有唯一的 `summarize` 发件人地址。
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    运算符 `summarize` 可以轻松替换为，在消耗更少资源 `project` 时产生可能相同的结果：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    以下示例使用效率更高，因为发件人地址向同一收件人地址发送电子邮件可能有多个 `summarize` 不同实例。 此类组合不同，并且可能具有重复项。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **收缩查询**— 虽然最好在具有重复值的列中使用，但相同的列也可以具有高基数或大量 `summarize` 唯一值。  与运算符一样，还可以应用随机提示来分配处理负载，并有可能在具有高基数的列上 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` 操作时提高性能。

    下面的查询用于统计不同的收件人电子邮件地址，可以在数十万大型组织中 `summarize` 运行。 为了提高性能，它包含了 `hint.shufflekey` ：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>查询方案

### <a name="identify-unique-processes-with-process-ids"></a>使用进程标识唯一进程标识
进程 ID (PID) 在 Windows 中回收，并重新用于新进程。 它们本身不能用作特定进程的唯一标识符。

若要获得特定计算机上进程的唯一标识符，请使用进程 ID 以及进程创建时间。 在进程之间联接或汇总数据时，请加入以下列：计算机标识符（`DeviceId` 或 `DeviceName`）、进程 ID（`ProcessId` 或 `InitiatingProcessId`）以及进程创建时间（`ProcessCreationTime` 或 `InitiatingProcessCreationTime`）

以下示例查询将查找通过端口 445 (SMB) 访问 10 个以上 IP 地址（可能扫描文件共享）的进程。

示例查询：
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

该查询按 `InitiatingProcessId` 和 `InitiatingProcessCreationTime` 进行汇总，以便查看单个进程，而不会混用具有同一进程 ID 的多个进程。

### <a name="query-command-lines"></a>查询命令行
有很多方法可以构造命令行来完成任务。 例如，攻击者可能会引用没有路径、没有文件扩展名、使用环境变量或带引号的图像文件。 攻击者还可以更改参数的顺序或添加多个引号和空格。

若要围绕命令行创建更持久持久查询，请应用以下做法：

- 通过匹配 (字段psexec.exe) ，而不是在命令行本身进行筛选，来标识已知进程，如net.exe或psexec.exe) 。
- 使用 [parse_command_line () 函数分析命令行部分](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- 查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。 而是使用正则表达式或使用多个单独的 Contains 运算符。
- 使用不区分大小写的匹配项。 例如，使用 `=~` `in~` ， ， `contains` 而不是 `==` ， 和 `in` `contains_cs` 。
- 若要缓解命令行模糊处理技术，请考虑删除引号、将逗号替换为空格，以及将多个连续空格替换为单个空格。 有一些更复杂的模糊处理技术需要其他方法，但是这些调整有助于解决常见问题。

以下示例显示构建查询的各种方法，该查询查找net.exe停止防火墙服务"MpsSvc"： 

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

### <a name="ingest-data-from-external-sources"></a>从外部源中输入数据
若要将长列表或大型表合并到查询中，请使用 [externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 运算符从指定的 URI 引入数据。 可以从 TXT、CSV、JSON 或其他格式 [的文件获取数据](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。 下面的示例演示如何利用 MalwareBazaar (abuse.ch) 提供的恶意软件 SHA-256 哈希列表来检查电子邮件中的附件：

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

### <a name="parse-strings"></a>分析字符串
可以使用多种函数来高效地处理需要分析或转换的字符串。 

| String | 函数 | 用法示例 |
|--|--|--|
| 命令行 | [parse_command_line () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | 提取命令和所有参数。 | 
| Paths | [parse_path () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | 提取文件或文件夹路径的各个部分。 |
| 版本号 | [parse_version () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | 解构一个最多包含四个部分且每个节最多八个字符的版本号。 使用分析的数据比较版本使用期。 |
| IPv4 地址 | [parse_ipv4 () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | 将 IPv4 地址转换为长整型。 若要比较 IPv4 地址而不转换它们，请使用 [ipv4_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。 |
| IPv6 地址 | [parse_ipv6 () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | 将 IPv4 或 IPv6 地址转换为规范 IPv6 表示法。 若要比较 IPv6 地址，请使用 [ipv6_compare () ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。 |

若要了解所有受支持的分析函数，请阅读 [Kusto 字符串函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。 

## <a name="related-topics"></a>相关主题
- [Kusto 查询语言文档](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [配额和使用参数](advanced-hunting-limits.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
