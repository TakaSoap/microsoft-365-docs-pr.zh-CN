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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f18a98b19b6a1920d1e4d2094ba0bab74f10035e
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430135"
---
# <a name="advanced-hunting-query-best-practices"></a>高级搜寻查询最佳做法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

应用这些建议以更快地获得结果，并避免在运行复杂查询时超时。 有关提高查询性能的更多指导，请参阅 [Kusto 查询最佳做法](https://docs.microsoft.com/azure/kusto/query/best-practices)。

## <a name="understand-cpu-resource-limits"></a>了解 CPU 资源限制
根据其大小，每个租户都有权访问为运行高级搜寻查询而分配的一组 CPU 资源。 有关各种服务限制的详细信息，请 [阅读有关高级搜寻限制](advanced-hunting-limits.md)的信息。

定期运行多个查询的客户应跟踪消耗量并在本文中应用优化指南，以最大限度地减少因超出限制而导致的中断。

## <a name="general-optimization-tips"></a>常规优化提示

- **调整新查询的大小**—如果您怀疑查询将返回一个大型结果集，请先使用 [count 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)对其进行评估。 使用 [限制](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) 或其同义词 `take` 以避免出现大型结果集。
- **早期应用筛选器**—应用时间筛选器和其他筛选器以减少数据集，尤其是在使用转换和分析函数（如 [子字符串 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)、将 [ ( # B3 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)、 [trim ( # B5 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)、 [toupper ( # B7 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)或 [parse_json ( # B9 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）时。 在下面的示例中，分析函数 [extractjson ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) 在筛选运算符减少了记录数量之后使用。

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **包含节拍**—若要避免在不必要的词中搜索子字符串，请使用 `has` 运算符而不是 `contains` 。 [了解字符串运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **查找特定**列—查看特定列，而不是在所有列中运行全文搜索。 请勿使用 `*` 检查所有列。
- **对速度区分大小写**-区分大小写的搜索更具体且性能更高。 区分大小写的 [字符串运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)（如 `has_cs` 和）的名称 `contains_cs` 通常以结尾 `_cs` 。 您还可以使用区分大小写的 equals 运算符 `==` 而不是 `~=` 。
- **分析、不提取**（如果可能，请使用 [Parse 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) 或分析函数，如 [parse_json ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)）。 避免 `matches regex` 使用字符串运算符或 [提取 ( # A1 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)，这两个函数都使用正则表达式。 为更复杂的方案保留使用正则表达式。 [阅读有关分析函数的详细信息](#parse-strings)
- **筛选表不是表达式**—如果可以根据表格列进行筛选，则不能在计算列上进行筛选。
- **无三字符术语**—避免使用包含三个或更少字符的术语进行比较或筛选。 不会对这些术语编制索引，并且匹配这些术语将需要更多资源。
- **项目**：通过只投影所需的列使您的结果更易于理解。 在运行 [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) 或类似操作之前投射特定列也有助于提高性能。

## <a name="optimize-the-join-operator"></a>优化 `join` 运算符
[Join 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)通过匹配指定列中的值来合并两个表中的行。 应用这些提示以优化使用此运算符的查询。

- **向左较小的表**- `join` 运算符将联接语句左侧表中的记录与右侧的记录进行匹配。 通过在左侧使用较小的表，将需要匹配较少的记录，从而加快查询的运行。 

    在下表中，我们将左表缩小 `DeviceLogonEvents` 为仅包含三个特定设备，然后再 `IdentityLogonEvents` 通过帐户 sid 加入。
 
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

- 在将每个匹配项返回到右表中之前，**使用内部联接风格**（默认的[连接风格](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)或[innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates 中的行），然后再将左侧表中的行联接起来。 如果左表中有多个行具有相同的键值 `join` ，则这些行将被消除重复，以便为每个唯一值留出单个随机行。

    此默认行为可能会从左侧表中退出可提供有用见解的重要信息。 例如，下面的查询仅显示一个包含特定附件的电子邮件，即使使用多封电子邮件发送相同的附件也是如此：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    若要解决此限制，请通过[inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)指定 `kind=inner` 将左表中的所有行显示在右侧的匹配值来应用内部联接风格：
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **从时间窗口加入记录**—在调查安全事件时，分析师将查找在同一时间段内发生的相关事件。 在使用时应用相同的方法 `join` 也可减少要检查的记录数，从而提高了优势。
    
    下面的查询检查在接收到恶意文件的30分钟内是否发生登录事件：

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
- **在两面上应用时间筛选器**—即使您没有调查特定的时间窗口，同时对左侧表和右侧表应用时间筛选器可以减少要检查的记录数并提高 `join` 性能。 下面的查询适用于 `Timestamp > ago(1h)` 这两个表，使其仅联接过去一小时内的记录：

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **使用提示提高性能**-将提示用于 `join` 运算符，以指示后端在运行占用大量资源的操作时分布负载。 [了解有关联接提示的详细信息](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    例如， **[无序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** 可帮助提高查询性能。使用基数较高的键联接表时，具有很多唯一值的键，如 `AccountObjectId` 下面的查询中所示：

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    当左侧表格为最多为100000个记录时， **[广播提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 会有帮助) 而右侧表的大小为极大 (。 例如，下面的查询尝试加入几封电子邮件，其中包含包含表中的链接的特定主题的 _所有_ 邮件 `EmailUrlInfo` ：

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>优化 `summarize` 运算符
[汇总运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator)聚合表的内容。 应用这些提示以优化使用此运算符的查询。

- **查找非重复值**通常，用于 `summarize` 查找可能重复的不同值。 将其用于聚合没有重复值的列可能是不必要的。

    虽然单个电子邮件可以成为多个事件的一部分，但下面的示例并 _不_ 是有效使用， `summarize` 因为单个电子邮件的网络邮件 ID 始终附带唯一的发件人地址。
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    `summarize`操作员可以轻松地替换为 `project` ，在消耗较少资源的情况下可能会产生相同的结果：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    下面的示例是更有效的使用， `summarize` 因为发件人地址的多个不同实例可以将电子邮件发送到同一收件人地址。 此类组合不太明显，并且可能有重复项。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **无序查询查询**—虽然 `summarize` 最适用于具有重复值的列，相同的列也可以具有 _较高的基数_ 或大量的唯一值。 与 `join` 运算符一样，也可以在对具有高基数的列进行操作时，将 [无序提示](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) 应用于 `summarize` 以分发处理负载，并可能提高性能。

    下面的查询用于 `summarize` 计算不同的收件人电子邮件地址，该地址可以在大型组织的成百上千个组织中运行。 为了提高性能，它采用了 `hint.shufflekey` 以下内容：

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>查询方案

### <a name="identify-unique-processes-with-process-ids"></a>确定具有进程 Id 的唯一进程
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
有很多方法可以构造命令行来完成任务。 例如，攻击者可以引用不带路径的图像文件，而无需文件扩展名、使用环境变量或使用引号。 攻击者还可以更改参数的顺序或添加多个引号和空格。

若要在命令行周围创建更持久的查询，请应用以下做法：

- 通过在 "文件名" 字段上进行匹配（而不是在命令行本身上进行筛选），确定已知的过程 (例如 *net.exe* 或 *psexec.exe*) 。
- 使用[parse_command_line ( # A1 函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)分析命令行部分 
- 查询命令行参数时，请勿按特定顺序查找多个不相关参数的完全匹配。 而是使用正则表达式或使用多个单独的 Contains 运算符。
- 使用不区分大小写的匹配项。 例如，使用 `=~` 、 `in~` 和 `contains` 代替 `==` 、 `in` 和 `contains_cs` 。
- 若要缓解命令行混淆技术，请考虑删除引号、将逗号替换为空格，以及用一个空格替换多个连续空格。 有更复杂的模糊处理技术需要其他方法，但这些调整可帮助解决常见的方法。

下面的示例展示了用于构造查询的各种方法，该查询将查找用于停止防火墙服务 "MpsSvc" 的文件 *net.exe* ：

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

### <a name="ingest-data-from-external-sources"></a>从外部源中插入数据
若要将长列表或大型表合并到查询中，请使用 [externaldata 运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 从指定的 URI 中插入数据。 您可以从文件中获取 TXT、CSV、JSON 或 [其他格式](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)的数据。 下面的示例展示了如何利用由 MalwareBazaar (abuse.ch) 提供的恶意软件 SHA-256 哈希列表来检查电子邮件上的附件：

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
您可以使用多种函数来有效处理需要分析或转换的字符串。 

| String | 函数 | 用法示例 |
|--|--|--|
| 命令行 | [parse_command_line ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | 提取命令和所有参数。 | 
| Paths | [parse_path ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | 提取文件或文件夹路径的各个部分。 |
| 版本号 | [parse_version ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct 版本号最多为四个部分，每节最多八个字符。 使用已分析的数据比较版本期限。 |
| IPv4 地址 | [parse_ipv4 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | 将 IPv4 地址转换为长整型。 若要比较 IPv4 地址而不进行转换，请使用 [ipv4_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。 |
| IPv6 地址 | [parse_ipv6 ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | 将 IPv4 或 IPv6 地址转换为规范的 IPv6 表示法。 若要比较 IPv6 地址，请使用 [ipv6_compare ( # B1 ](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。 |

若要了解所有受支持的分析函数，请 [阅读有关 Kusto 字符串函数的信息](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。 

## <a name="related-topics"></a>相关主题
- [Kusto 查询语言文档](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [服务限制](advanced-hunting-limits.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
