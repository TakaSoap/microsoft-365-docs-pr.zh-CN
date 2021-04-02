---
title: 了解高级搜寻查询语言
description: 创建你的第一个威胁搜寻查询，并了解高级搜寻查询语言的常见运算符和其他方面
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 语言， 学习， 第一个查询， 遥测， 事件， 遥测， 自定义检测， 架构， kusto， 运算符， 数据类型
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: af612a051f133e4846e04033ab35ea39769d0193
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499541"
---
# <a name="learn-the-advanced-hunting-query-language"></a>了解高级搜寻查询语言

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)。 您可以使用 Kusto 运算符和语句来构造在专用架构 中查找信息的 [查询](advanced-hunting-schema-reference.md)。 若要更好地了解这些概念，请运行你的第一个查询。

## <a name="try-your-first-query"></a>尝试你的第一个查询

在 Microsoft Defender 安全中心，转到 **高级搜寻以** 运行你的第一个查询。 使用以下示例：

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
**[在高级搜寻中运行此查询](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>描述查询并指定要搜索的表
在查询的开头添加了一个简短注释，用于描述查询内容。 如果您稍后决定保存查询并将其与组织其他人共享，此注释将有所帮助。

```kusto
// Finds PowerShell execution events that could involve a download
```
查询本身通常以表名称开始，后跟几个以管道连接 `|` () 。 此示例首先创建由 和 两个表组成并根据需要  `DeviceProcessEvents` `DeviceNetworkEvents` 添加管道元素。

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>设置时间范围
第一个管道元素是一个范围为前七天的时间筛选器。 限制时间范围有助于确保查询运行良好、返回可管理的结果，并且不会因此而省时。

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
现在，您的查询清楚地标识了要查找的数据，您可以定义结果的外观。 `project` 返回特定列 `top` ，并限制结果数。 这些运算符有助于确保结果的格式正确，并且相当大且易于处理。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

选择 **"运行查询** "以查看结果。 使用查询编辑器右上角的展开图标专注于搜寻查询和结果。 

![高级搜寻查询编辑器中的"展开"控件的图像](images/advanced-hunting-expand.png)

>[!TIP]
>您可以将查询结果作为图表进行查看并快速调整筛选器。 有关指导 [，请阅读关于使用查询结果](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>了解高级搜寻的常见查询运算符

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

To see a live example of these operators， run them from the **Get started** section of the advanced hunting page.

## <a name="understand-data-types"></a>了解数据类型

高级搜寻支持 Kusto 数据类型，包括以下常见类型：

| 数据类型 | 说明和查询含义 |
|--|--|
| `datetime` | 通常表示事件时间戳的数据和时间信息。 [查看受支持的日期时间格式](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | UTF-8 中的字符串，括在单引号 () `'` 或双引号 `"` () 。 [阅读有关字符串的更多信息](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | 此选项数据类型 `true` 或 `false` 状态。 [查看受支持的文字和运算符](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32 位整数  |
| `long` | 64 位整数 |

若要详细了解这些数据类型， [请阅读 Kusto 标量数据类型](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)。

## <a name="get-help-as-you-write-queries"></a>编写查询时获取帮助
利用以下功能更快地编写查询：

- **自动建议**- 当你编写查询时，高级搜寻会提供来自IntelliSense。
- **架构** 树 — 包含表及其列列表的架构表示形式在工作区旁边提供。 有关详细信息，请将鼠标悬停在某个项上。 双击某个项，将其插入到查询编辑器中。
- **[架构参考](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**- 包含表和列说明的门户内参考，以及支持的事件 (`ActionType` 值) 查询

## <a name="work-with-multiple-queries-in-the-editor"></a>在编辑器中处理多个查询
您可以使用查询编辑器试验多个查询。 若要使用多个查询：

- 使用空行分隔每个查询。
- 将光标放在查询的任何部分，以在运行该查询之前选择该查询。 这将仅运行选定的查询。 若要运行另一个查询，请相应地移动游标并选择"**运行查询"。**

![包含多个查询的高级搜寻查询编辑器的图像 具有 ](images/ah-multi-query.png)
 _多个查询的查询编辑器_

## <a name="use-sample-queries"></a>使用示例查询

**入门** 部分提供了使用常用运算符的几个简单查询。 请尝试运行这些查询，并对其进行细微修改。

![高级搜寻"开始"选项卡的图像](images/atp-advanced-hunting.png)

> [!NOTE]
> 除了基本查询示例之外，你还可以访问特定威胁搜寻方案的[共享查询](advanced-hunting-shared-queries.md)。 浏览页面左侧或 GitHub 查询存储库 [上的共享查询](https://aka.ms/hunting-queries)。

## <a name="access-comprehensive-query-language-reference"></a>Access 综合查询语言参考

有关查询语言的详细信息，请参阅 [Kusto 查询语言文档](https://docs.microsoft.com/azure/kusto/query/)。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
