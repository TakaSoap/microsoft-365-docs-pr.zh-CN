---
title: 高级电子数据展示限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解Microsoft 365中Advanced eDiscovery解决方案的大小写限制、索引限制和搜索限制。
ms.openlocfilehash: 0f21a78a90eee6069618e2ab35bb011aa870b62c
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758560"
---
# <a name="limits-in-advanced-ediscovery"></a>高级电子数据展示中的限制

本文介绍Microsoft 365中Advanced eDiscovery解决方案中的限制。

## <a name="case-and-review-set-limits"></a>案例和审阅集限制

下表列出了Advanced eDiscovery中案例和审阅集的限制。

|限制说明|限制|
|---|---|
|在案例) 中，可添加到案例 (的所有审阅集的文档总数。|3 百万|
|每个负载集的总文件大小。 这包括将非Office 365加载到审阅集中。|300 GB|
|每天加载到组织中所有审阅集的数据总量。<br/>|2 TB|
|每个事例的最大负载集数。|200|
|每个案例的最大审阅集数。|20|
|每个事例的最大标记组数。|1,000|
|每个事例的最大唯一标记数。|1，<sup>0001</sup>|
|组织中向审阅集添加内容的最大并发作业数。 这些作业名为 **“将数据添加到审阅集** ”，在某个情况下显示在 **“作业** ”选项卡上。|<sup>102</sup>|
|向每个用户的审阅集添加内容的最大并发作业数。 这些作业名为 **“将数据添加到审阅集** ”，在某个情况下显示在 **“作业** ”选项卡上。|3|

## <a name="hold-limits"></a>保留限制

下表列出了与Advanced eDiscovery案例关联的保留的限制。

|限制说明|限制|
|---|---|
|组织的最大保留策略数。 此限制包括核心电子数据展示和Advanced eDiscovery个案例中保存策略的总和。|10，<sup>0003</sup>|
|单个事例保留中的最大邮箱数。 此限制包括用户邮箱总数，以及与Microsoft 365 组、Microsoft Teams和Yammer组关联的邮箱。|1,000|
|单个事例保留中的最大站点数。 此限制包括OneDrive for Business网站、SharePoint站点以及与Microsoft 365 组、Microsoft Teams 和Yammer组关联的站点总数。|100|

## <a name="indexing-limits"></a>索引限制

下表列出了Advanced eDiscovery中的索引限制。

|限制说明|限制|
|---|---|
|从单个文件中提取的最大字符数。|1000万<sup>4</sup>|
|单个文件的最大大小。|150 <sup>MB4</sup>|
|文档中嵌入项的最大深度。|<sup>254</sup>|
|光学字符识别 (OCR) 处理的文件的最大大小。|24 <sup>MB4</sup> <br/>  

## <a name="search-limits"></a>搜索限制

本部分中所述的限制与使用“ **搜索** ”选项卡上的搜索工具收集案例的数据有关。 有关详细信息，请参阅[Advanced eDiscovery中收集案例的数据](collecting-data-for-ediscovery.md)。

|限制说明|限制|
|---|---|
|可在单个搜索中搜索的最大邮箱或网站数。|无限制|
|可以同时运行的最大搜索数。|无限制|
|单个用户可以同时启动的最大搜索次数。|10 |
|搜索查询的最大字符数 (包括运算符和条件) 。|10，<sup>0005</sup>|
|搜索查询SharePoint和OneDrive for Business网站的最大字符数 (包括运算符和条件) 。|10,000<br>4，000 与通配符 <sup>5</sup>|
|前缀通配符的最小 alpha 字符数;例如， **one\**_ 或 _* set\***。|3|
|使用前缀通配符搜索确切短语或使用前缀通配符和 **NEAR** 布尔运算符时返回的最大变体。|10，<sup>0006</sup>|
|每个用户邮箱中显示的搜索预览页上的最大项数。 显示最新项目。|100|
|预览页上显示的所有邮箱中用于搜索的最大项数。|1,000|
|可预览搜索结果的最大邮箱数。  如果包含与搜索查询匹配的项的邮箱超过 1，000 个，则只有结果最多的前 1，000 个邮箱可供预览。|1,000|
|用于搜索的预览页上显示SharePoint和OneDrive for Business网站的最大项数。 显示最新项目。|200|
|可预览搜索结果的最大SharePoint和OneDrive for Business网站数。 如果有 200 多个网站包含与搜索查询匹配的项，则只有结果最多的前 200 个网站可供预览。|200|
|用于搜索的预览页上显示的每个公用文件夹邮箱的最大项数。|100|
|在用于搜索的预览页上显示的所有公用文件夹邮箱项目中找到的最大项数。|200|
|可预览搜索结果的最大公用文件夹邮箱数。 如果包含与搜索查询匹配的项的公用文件夹邮箱超过 500 个，则只有结果最多的前 500 个邮箱可供预览。|500|
|可在草稿集合的示例页上查看的项的最大大小。|10，000，000 字节 (约 9.5 MB) |

## <a name="search-times"></a>搜索时间

Microsoft 收集所有组织运行的搜索的性能信息。 尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。 尽管 Microsoft 未提供搜索时间的服务级别协议，但下表基于搜索中包含的邮箱数列出了集合搜索的平均搜索时间。
  
|邮箱数|平均搜索时间|
|---|---|
|100|30 秒|
|1,000|45 秒|
|10,000|4 分钟|
|25,000|10 分钟|
|50,000|20 分钟|
|100,000|25 分钟|

## <a name="viewer-limits"></a>查看器限制

|限制说明|限制|
|---|---|
|可在本机查看器中查看的Excel文件的最大大小。|4 MB|

## <a name="export-limits---final-export-out-of-review-set"></a>导出限制 - 最终导出审阅集

本部分中所述的限制与从审阅集中导出文档有关。

|限制说明|限制|
|---|---|
|单个导出的最大大小。|500 万个文档或 500 GB，以较小者为准|
|每个审阅集的最大并发导出量。|1|

## <a name="review-set-download-limits"></a>审阅集下载限制

|限制说明|限制|
|---|---|
|从审阅集下载的文件总大小或最大文档数。|3 MB 或 50 个文<sup>档 7</sup>|

## <a name="notes"></a>注释

> [!NOTE]
> <sup>1</sup> 这是可以在一个案例中创建的最大标记数。 此限制与可以标记的文档数无关。
>
> <sup>2</sup> 此限制与其他电子数据展示工具中的导出内容共享。 这意味着内容搜索和核心电子数据展示中的并发导出 (以及将内容添加到Advanced eDiscovery) 中的审阅集都按此限制应用。
>
> <sup>3</sup> 在单个保留策略中保留 1，000 多个邮箱或 100 个站点时，系统会根据需要自动缩放保留。 这意味着系统会自动将数据位置添加到多个保留策略，而不是将其添加到单个保留策略。 但是，每个组织仍适用 10，000 个案例保留策略的限制。
>
> <sup>4</sup> 超过单个文件限制的任何项都将显示为处理错误。
>
> <sup>5</sup> 搜索SharePoint和OneDrive for Business位置时，所搜索网站 URL 中的字符将根据此限制进行计数。 字符总数包括：
>
> - “用户”和“筛选器”字段中的所有字符。
> - 适用于用户的所有搜索权限筛选器。
> - 搜索中任意位置属性中的字符;这包括 ExchangeLocation、PublicFolderLocation、SharPointLocation、ExchangeLocationExclusion、PublicFolderLocationExclusion、SharePointLocationExclusion、OneDriveLocationExclusion。
>   例如，在搜索中包括所有SharePoint网站和OneDrive帐户将算作六个字符，因为 SharePointLocation 和 OneDriveLocation 字段都将显示“ALL”一词。
>
> <sup>6</sup> 对于非短语查询 (不使用双引号的关键字值，) 使用特殊前缀索引。 这会告诉我们某个单词在文档中发生，但不会出现在文档中的位置。 若要执行短语查询 (具有双引号) 的关键字值，我们需要比较文档中对短语中单词的位置。 这意味着无法对短语查询使用前缀索引。 在这种情况下，我们将使用前缀扩展到的所有可能单词在内部扩展查询;例如，**time\**_ 可以扩展到 _*“time OR timer OR times OR timex OR timex OR timeboxed OR ...”。** 10，000 的限制是单词可以扩展到的最大变体数，而不是与查询匹配的文档数。 非短语搜索词没有上限。
>
> <sup>7</sup> 此限制适用于从审阅集下载所选文档。 它不适用于从审阅集导出文档。 有关下载和导出文档的详细信息，请参阅[Advanced eDiscovery中的导出案例数据](exporting-data-ediscover20.md)。
