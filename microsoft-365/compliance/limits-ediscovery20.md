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
description: 了解适用于 Microsoft 365 高级电子数据展示解决方案的情况限制、索引编制限制和搜索限制。
ms.openlocfilehash: fc658f4502bf510cf34297435db75bd7cdd7c136
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316193"
---
# <a name="limits-in-advanced-ediscovery"></a>高级电子数据展示中的限制

本文介绍了 Microsoft 365 高级电子数据展示解决方案中的限制。

## <a name="case-and-review-set-limits"></a>案例和审阅集限制

下表列出了高级电子数据展示中事例和审阅集的限制。

| 限制说明 | 限制 |
|:-----|:-----|
|可添加到案例的文档总数， (审阅集的) 。  <br/> |3 百万 <br/> |
|每个负载集的总文件大小。 这包括将非 Office 365 加载到审阅集。  <br/> |300 GB <br/> |
|每天加载到组织的所有审阅集的总数据量。<br/> |2 TB <br/> |
|每个情况的最大负载集数。  <br/> |200 <br/> |
|每个案例的最大审阅集数。  <br/> |20 <br/> |
|每个案例的最大标记组数。  <br/> |1,000 |
|每个案例的唯一标记的最大数量。 <br/> |1，<sup>0001</sup> |
|将内容添加到审阅集的组织中的最大并发作业数。 这些作业名为 **"将数据添加到审阅集"** ，并显示在案例的" **作业"选项卡** 上。| <sup>102</sup> |
|每个用户向审阅集添加内容的最大并发作业数。 这些作业名为 **"将数据添加到审阅集"** ，并显示在案例的" **作业"选项卡** 上。 | 3 |
|||

## <a name="hold-limits"></a>保留限制

下表列出了与高级电子数据展示案例相关联的保留的限制。

| 限制说明 | 限制 |
|:-----|:-----|
|组织的最大保留策略数。 此限制包括核心电子数据展示和高级电子数据展示事例中保留策略的组合总数。 <br/> |10，<sup>0003</sup>  <br/> |
|单个案例保留中的最大邮箱数。 此限制包括用户邮箱总数，以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱总数。 <br/> |1,000  <br/> |
|单个案例保留中的最大网站数。 此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站总数。  <br/> |100  <br/> |

## <a name="indexing-limits"></a>索引限制

下表列出了高级电子数据展示中的索引限制。

| 限制说明 | 限制 |
|:-----|:-----|
|从单个文件提取的最大字符数。  <br/> |1000 万<sup>4</sup> <br/> |
|单个文件的最大大小。   <br/> |150 <sup>MB4</sup> <br/> |
|文档中嵌入项目的最大深度。  <br/> |<sup>254</sup> <br/> |
|由光学字符识别处理的最大文件大小 (OCR) 。  <br/> |24 <sup>MB4</sup> <br/>  
|||

## <a name="search-limits"></a>搜索限制

本节中所述的限制与使用"搜索"选项卡上的搜索工具收集案件集数据相关。 有关详细信息，请参阅收集高级电子数据展示中 [案例的数据](collecting-data-for-ediscovery.md)。

| 限制说明 | 限制 |
|:-----|:-----|
|可以在单个搜索中搜索的最大邮箱或网站数。 |无限制|
|可以同时运行的最大搜索数。 |无限制 |
|单个用户可以同时启动的最大搜索数。 |10  | 
|搜索查询记录的最大字符数 (运算符和条件) 。 |10，<sup>0005</sup>|
|SharePoint 和 OneDrive for Business 网站搜索查询的最大字符数 (运算符和条件) 。 |10,000<br>4，000（带通配符<sup>5）</sup>|
|前缀通配符的最小 alpha 字符数;例如， **one\**_ 或 _* set\***。|3 |  
|使用前缀通配符搜索精确短语时，或者使用前缀通配符和 **NEAR** 布尔运算符时返回的最大变量数。 |10，<sup>0006</sup>|
|在搜索的预览页面上显示的每个用户邮箱的最大项目数。 显示最新项目。 |100|
|预览页面上显示用于搜索的所有邮箱的最大项目数。|1,000|
|可预览搜索结果的最大邮箱数。  如果超过 1，000 个邮箱包含与搜索查询匹配的项目，则仅前 1，000 个包含最多结果的邮箱可供预览。|1,000|
|预览页面上显示用于搜索的 SharePoint 和 OneDrive for Business 网站的最大项目数。 显示最新项目。 |200|
|可预览搜索结果的 SharePoint 和 OneDrive for Business 网站的最大数量。 如果包含与搜索查询匹配的项目的网站超过 200 个，则仅具有最多结果的前 200 个网站可供预览。|200|
|在预览页面上显示用于搜索的公用文件夹邮箱的最大项目数。 |100|
|在预览页面上显示用于搜索的所有公用文件夹邮箱项中查找的最大项目数。 |200|
|可预览搜索结果的公用文件夹邮箱的最大数量。 如果超过 500 个公用文件夹邮箱包含与搜索查询匹配的项目，则只有结果最多的前 500 个邮箱可供预览。|500|
|||

## <a name="search-times"></a>搜索时间

Microsoft 收集所有组织运行的搜索的性能信息。 尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。 尽管 Microsoft 不提供用于搜索次数的服务级别协议，但下表根据搜索中包含的邮箱数列出了集合搜索的平均搜索时间。
  
  | 邮箱数 | 平均搜索时间 |
  |:-----|:-----|
  |100  <br/> |30 秒  <br/> |
  |1,000  <br/> |45 秒  <br/> |
  |10,000  <br/> |4 分钟  <br/> |
  |25,000  <br/> |10 分钟  <br/> |
  |50,000  <br/> |20 分钟  <br/> |
  |100,000  <br/> |25 分钟  <br/> |
  |||

## <a name="viewer-limits"></a>查看器限制

| 限制说明 | 限制 |
|:-----|:-----|
|可以在本机Excel查看的最大文件大小。  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>导出限制 - 最终导出审阅集

本节中所述的限制与将文档从审阅集导出有关。

| 限制说明 | 限制 |
|:-----|:-----|
|单个导出的最大大小。|500 万个文档或 500 GB，以较小者为准|
|每个审阅集的最大并发导出数。 | 1 |
|||

## <a name="review-set-download-limits"></a>查看集下载限制

| 限制说明 | 限制 |
|:-----|:-----|
|总文件大小或从审阅集下载的最大文档数。  <br/> |3 MB 或 50 个文档<sup>7</sup>|
|||

## <a name="notes"></a>注释

> [!NOTE]
> <sup>1</sup> 这是一种情况下可以创建的最大标记数。 此限制与可标记的文档数不相关。
>
> <sup>2</sup> 此限制与其他电子数据展示工具中的内容导出共享。 这意味着，内容搜索和核心电子数据展示中的并发导出 (以及将内容添加到内容审阅集Advanced eDiscovery) 都针对此限制应用。
>
> <sup>3</sup> 当您将 1，000 多个邮箱或 100 个网站置于一个保留策略中时，系统将根据需要自动扩展保留。 这意味着系统会自动将数据位置添加到多个保留策略，而不是将它们添加到单个保留策略。 但是，每个组织 10，000 个案例保留策略的限制仍然适用。
>
> <sup>4</sup> 任何超过单个文件限制的项目都将显示为处理错误。
>
> <sup>5</sup> 在搜索SharePoint和OneDrive for Business位置时，所搜索网站的 URL 中的字符数将计入此限制。 字符总数包含：<br>
> - "用户"和"筛选器"字段中的所有字符。
> - 应用于用户的所有搜索权限筛选器。
> - 搜索中任何位置属性中的字符;这包括 ExchangeLocation、PublicFolderLocation、SharPointLocation、ExchangeLocationExclusion、PublicFolderLocationExclusion、SharePointLocationExclusion、OneDriveLocationExclusion。
>   例如，包括搜索SharePoint网站和 OneDrive 帐户将计为六个字符，因为 SharePointLocation 和 OneDriveLocation 字段都将显示单词"ALL"。
>
> <sup>6</sup> 对于非短语查询 (使用特殊前缀索引时不使用双引号) 关键字值。 这将告诉我们一个单词在文档中出现，而不是在文档中出现的地方。 若要使用双引号 (关键字值执行短语查询) ，我们需要比较短语中单词在文档中的位置。 这意味着不能将前缀索引用于短语查询。 在这种情况下，我们使用前缀扩展到的所有可能的单词在内部扩展查询;例如，  **time\**_ 可以展开到 _*"time OR timer OR times OR timex OR timeboxed OR ..."**。 限制 10，000 是单词可以扩展到的最大变体数，而不是与查询匹配的文档数。 非短语搜索词没有上限。
>
> <sup>7</sup> 此限制适用于从审阅集下载所选文档。 它不适用于从审阅集导出文档。 有关下载和导出文档的信息[，请参阅导出](exporting-data-ediscover20.md)文档中的Advanced eDiscovery。
