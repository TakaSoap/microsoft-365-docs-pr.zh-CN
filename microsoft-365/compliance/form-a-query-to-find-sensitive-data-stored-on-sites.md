---
title: 创建查询以查找存储在站点上的敏感数据
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
description: 在 (Online) DLP SharePoint数据丢失防护，以发现整个租户中包含敏感数据的文档。
ms.openlocfilehash: af1ca8f28f80d58c0f366e1a002181e23db3d552
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170615"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>创建查询以查找存储在站点上的敏感数据

用户经常将敏感数据（如信用卡号、社会保险号或个人）存储在其网站上，随着时间的推移，这可能会使组织面临重大数据丢失风险。 存储在网站中的文档（OneDrive for Business网站）可以与组织外部不应有权访问信息的人共享。 通过 (Online) DLP SharePoint数据丢失防护，可以发现整个租户中包含敏感数据的文档。 发现文档后，您可以与文档所有者一起保护数据。 本主题可帮助您形成查询来搜索敏感数据。

> [!NOTE]
> 电子数据展示或电子数据展示和 DLP 是高级功能，SharePoint [Online 计划 2。](https://go.microsoft.com/fwlink/?LinkId=510080)

## <a name="forming-a-basic-dlp-query"></a>创建一个基本的 DLP 查询

基本的 DLP 查询包括三个部分：SensitiveType、计数范围和置信区间。 如下图所示 **，SensitiveType：" \<type\>** 是必需的，并且 和 **|\<count range\>** **|\<confidence range\>** 都是可选的。

![示例查询分为必需和可选。](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>敏感类型 - 必填

那么，每个部分分别是什么？ SharePointDLP 查询通常以 属性和敏感信息类型清单的信息类型名称开头，以 `SensitiveType:"` [](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)结尾 `"` 。 您还可以使用为组织 [创建的](create-a-custom-sensitive-information-type.md) 自定义敏感信息类型的名称。 例如，您可能正在寻找包含信用卡号的文档。 在此类实例中，你将使用以下格式  `SensitiveType:"Credit Card Number"` ：。 由于您未包括计数范围或置信区间，因此查询将返回检测到信用卡号的每一个文档。 这是您可以运行的最简单的查询，并会返回最多的结果。 请记住，敏感类型问题的拼写和空格很重要。

### <a name="ranges---optional"></a>范围 - 选填

接下来的两个部分都是范围，因此让我们快速检查一下范围的外观。 在SharePoint DLP 查询中，基本范围由两个数字表示，由两个句点分隔，如下所示 `[number]..[number]` ：。 例如，如果使用  `10..20` ，该范围将捕获 10 到 20 的数字。 有许多不同的范围组合，本主题将阐释其中的几个。

让我们向查询添加计数范围。 您可以使用计数范围来定义文档在包含在查询结果中之前需要包含的敏感信息出现次数。 例如，如果希望查询仅返回正好包含五个信用卡号的文档，请使用  `SensitiveType:"Credit Card Number|5"` ：。 计数范围还可以帮助您辨别存在高风险的文档。 例如，您的组织可能认为含有五个或更多信用卡号的文档存在高风险。 若要查找符合此条件的文档，请使用此查询  `SensitiveType:"Credit Card Number|5.."` ：。 或者，您可以使用此查询查找信用卡号少于或五个以下的文档  `SensitiveType:"Credit Card Number|..5"` ：。

#### <a name="confidence-range"></a>置信区间

最后，置信区间是指已检测到敏感类型实际匹配的置信水平。 置信区间的值与计数范围使用的原理相似。 您可以创建一个不包括计数范围的查询。 例如，要搜索具有任意数目的信用卡号的文档（只要置信区间为 85% 或更高）就会使用此查询  `SensitiveType:"Credit Card Number|*|85.."` ：。

> [!IMPORTANT]
> 星号字符 `*` () 通配符，表示任何值都有效。 可以在计数范围或置信区间 () ，但不能在敏感类型中，使用通配符 `*` 。

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>电子数据展示中心可用的其他查询属性和搜索运算符

DLP in SharePoint还引入了 LastSensitiveContentScan 属性，该属性可帮助您搜索特定时间范围内扫描的文件。 有关属性的查询示例，请参阅下一节中的S examples `LastSensitiveContentScan` of complex [queries。](#examples-of-complex-queries)

您不仅可以使用特定于 DLP 的属性来创建查询，还可以使用标准 SharePoint电子数据展示搜索属性（如 `Author` 或 `FileExtension` ）。 您可以使用运算符来构建复杂的查询。 有关可用属性和运算符的列表，请参阅将搜索属性和运算符与 [电子数据展示一同](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery) 使用博客文章。

## <a name="examples-of-complex-queries"></a>示例

以下示例使用不同的敏感类型、属性和运算符来说明如何优化查询以准确找到您寻找的内容。

<br>

****

|查询|说明|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|该名称可能看起来有些奇怪，因为它太长，但却是该敏感类型的正确名称。 请确保使用敏感信息类型清单 [中的确切名称](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)。 您还可以使用为组织 [创建的](create-a-custom-sensitive-information-type.md) 自定义敏感信息类型的名称。|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|这将返回至少与敏感类型"信用卡号"匹配的文档。 每个范围的值分别是最小值和最大值。 编写此查询的一种更简单的方式是  `SensitiveType:"Credit Card Number"` ，但其中最有趣的是什么？|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|这将返回从 2018 年 8 月 11 日到 2018 年 8 月 13 日扫描的包含 5-25 个信用卡号的文档。|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|这将返回从 2018 年 8 月 11 日到 2018 年 8 月 13 日扫描的包含 5-25 个信用卡号的文档。 查询结果中不包含具有 XLSX 扩展名的文件。  `FileExtension` 是可以在查询中包括的许多属性之一。 有关详细信息，请参阅将 [搜索属性和运算符与电子数据展示一同使用](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)。|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|这将返回包含信用卡号或社会保障号的文档。|
|

## <a name="examples-of-queries-to-avoid"></a>示例

并非所有查询都一样。 下表提供了与 DLP 不一样的示例，并SharePoint原因。

<br>

****

|不支持的查询|原因|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|必须至少添加一个数值。|
|`SensitiveType:"NotARule"`|"NotARule"不是有效的敏感类型名称。 DLP 查询 [中仅包含](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) 敏感信息类型清单中的名称。|
|`SensitiveType:"Credit Card Number|0"`|零对范围中的最小值或最大值无效。|
|`SensitiveType:"Credit Card Number"`|虽然很难看到，但"信用卡"和"卡"之间还有额外的空格，导致查询无效。 使用敏感信息类型清单中 [的确切敏感类型名称](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)。|
|`SensitiveType:"Credit Card Number|1. .3"`|两个周期部分不应用空格分隔。|
|`SensitiveType:"Credit Card Number| |1..|80.."`|管道分隔符太多 \| () 。 请改为遵循以下格式： `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|由于置信度值表示百分比，因此不能超过 100。 请选择 1 至 100 之间的数值。|
|

## <a name="for-more-information"></a>详细信息

- [敏感信息类型属性定义](sensitive-information-type-entity-definitions.md)
- [运行内容搜索](content-search.md)
- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
