---
title: 了解高级搜寻查询语言Microsoft 365 Defender
description: 创建你的第一个威胁搜寻查询，并了解高级搜寻查询语言的常见运算符和其他方面
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 语言， 学习， 第一个查询， 遥测， 事件， 遥测， 自定义检测， 架构， kusto， 运算符， 数据类型， powershell 下载， 查询示例
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7092b4ed30400fb559751d4d939801c1982407f8
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241971"
---
# <a name="learn-the-advanced-hunting-query-language"></a>了解高级搜寻查询语言

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

高级搜寻基于 [Kusto 查询语言](/azure/kusto/query/)。 您可以使用 Kusto 运算符和语句构造在专用架构 中查找信息的 [查询](advanced-hunting-schema-tables.md)。 

观看此简短视频，了解一些方便易用的 Kusto 查询语言基础知识。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRwfJ]
 
若要更好地了解这些概念，请运行你的第一个查询。

## <a name="try-your-first-query"></a>尝试你的第一个查询

在Microsoft 365 Defender门户中，转到 **"搜寻**"以运行你的第一个查询。 使用以下示例： 

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

**[在高级搜寻中运行此查询](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>描述查询并指定要搜索的表
在查询的开头添加了一个简短注释，用于描述查询内容。 如果你以后决定要保存查询并与组织中的其他人共享，这将很有用。 

```kusto
// Finds PowerShell execution events that could involve a download
```

查询本身通常以表名称开始，后跟几个以管道连接 `|` () 。 此示例首先创建两个表和 的联合，  `DeviceProcessEvents` `DeviceNetworkEvents` 并根据需要添加管道元素。

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>设置时间范围
第一个通过管道的元素是一个范围为前七天的时间筛选器。 限制时间范围有助于确保查询运行良好、返回可管理的结果，并且不会超时。

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>检查特定进程
该时间范围后紧跟着搜索代表 PowerShell 应用程序的进程文件名。

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>搜索特定命令字符串
之后，查询在命令行中查找通常用于使用 PowerShell 下载文件的字符串。

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

### <a name="customize-result-columns-and-length"></a>自定义结果列和长度 
现在，你的查询清楚地标识了要查找的数据，你可以定义结果外观。 `project` 返回特定列 `top` ，并限制结果数。 这些运算符有助于确保结果的格式正确，并且相当大且易于处理。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

选择 **"运行查询** "以查看结果。

>[!TIP]
>您可以将查询结果作为图表进行查看并快速调整筛选器。 有关指导 [，请阅读关于使用查询结果](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>了解常见查询运算符

您刚刚运行了第一个查询，并且对它的组件有一个一般性了解。 现在应该稍微后退一下，了解一些基础知识。 高级搜寻使用的 Kusto 查询语言支持多种运算符，包括以下常见的运算符。

| 运算符 | 说明和用法 |
|--|--|
| `where` | 从表中筛选出满足谓词的行的子集。 |
| `summarize` | 生成聚合输入表内容的表。 |
| `join` | 通过匹配每个表中指定列的值，合并两个表的行以形成新表。 |
| `count` | 返回输入记录集中的记录数。 |
| `top` | 返回按指定列排序的前 N 条记录。 |
| `limit` | 最多返回指定的行数。 |
| `project` | 选择要包含、重命名或删除的列，然后插入新的计算列。 |
| `extend` | 创建计算列并将其附加到结果集。 |
| `makeset` |  返回 Expr 在组中采用的一组不同值的动态 (JSON) 数组。 |
| `find` | 查找与一组表中的谓词匹配的行。 |

若要查看这些操作符的实时示例，请在高级搜寻的 **入门** 部分中运行它们。

## <a name="understand-data-types"></a>了解数据类型

高级搜寻支持 Kusto 数据类型，包括以下常见类型：

| 数据类型 | 说明和查询含义 |
|--|--|
| `datetime` | 通常表示事件时间戳的数据和时间信息。 [查看受支持的日期时间格式](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | UTF-8 中的字符串用单引号 (`'`) 或双引号 (`"`) 括起来。 [阅读有关字符串的更多信息](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | 此数据类型支持 `true` 或 `false` 状态。 [查看受支持的文字和运算符](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32 位整数  |
| `long` | 64 位整数 |

若要详细了解这些数据类型， [请阅读 Kusto 标量数据类型](/azure/data-explorer/kusto/query/scalar-data-types/)。

## <a name="get-help-as-you-write-queries"></a>编写查询时获取帮助
利用以下功能更快地编写查询：
- **自动建议**- 当你编写查询时，高级搜寻会提供来自IntelliSense。 
- **架构** 树 — 包含表及其列列表的架构表示形式在工作区旁边提供。 有关详细信息，请将鼠标悬停在某个项上。 双击某个项，将其插入到查询编辑器中。
- **[架构参考](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**- 包含表和列说明的门户内参考，以及支持的事件 (`ActionType` 值) 查询

## <a name="work-with-multiple-queries-in-the-editor"></a>在编辑器中处理多个查询
您可以使用查询编辑器试验多个查询。 若要使用多个查询：

- 使用空行分隔每个查询。
- 将光标放在查询的任何部分，以在运行该查询之前选择该查询。 这将仅运行选定的查询。 若要运行另一个查询，请相应地移动游标并选择"**运行查询"。**

:::image type="content" source="../../media/learn-work-with-multiple.png" alt-text="示例：在应用程序门户的 **New query** 页中执行Microsoft 365 Defender查询" lightbox="../../media/learn-work-with-multiple.png":::

## <a name="use-sample-queries"></a>使用示例查询

**入门** 部分提供了使用常用运算符的几个简单查询。 请尝试运行这些查询，并对其进行细微修改。

:::image type="content" source="../../media/get-started-section.png" alt-text="应用门户中 **高级搜寻** 页面中的**入门**Microsoft 365 Defender部分" lightbox="../../media/get-started-section.png":::

>[!NOTE]
>除了基本查询示例之外，你还可以访问特定威胁搜寻方案的[共享查询](advanced-hunting-shared-queries.md)。 浏览页面左侧或页面查询库的GitHub[查询](https://aka.ms/hunting-queries)。

## <a name="access-query-language-documentation"></a>访问查询语言文档

有关 Kusto 查询语言和受支持运算符的详细信息，请参阅 [Kusto 查询语言文档](/azure/kusto/query/)。

>[!NOTE]
>本文中的某些表在 Microsoft Defender for Endpoint 中可能不可用。 [打开"Microsoft 365 Defender，](m365d-enable.md)以使用更多数据源搜寻威胁。 你可以按照从 Microsoft Defender for Endpoint 迁移高级搜寻查询中的步骤将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到[Microsoft 365 Defender。](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)