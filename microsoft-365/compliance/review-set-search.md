---
title: 查询审阅集中的数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在审阅集内创建和运行查询，以组织数据，以在Advanced eDiscovery审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345796"
---
# <a name="query-the-data-in-a-review-set"></a>查询审阅集中的数据

在大多数情况下，能够深入了解审阅集内的数据并组织该数据以促进更高效的审阅将非常有用。 在审阅集中使用查询可帮助您重点关注满足审阅条件的文档的子集。

## <a name="creating-and-running-a-query-in-a-review-set"></a>在审阅集内创建和运行查询

若要创建并运行对审阅集内文档的查询，请选择审阅 **集** 内的新查询。 命名查询并定义条件后，选择" **保存** "保存并运行查询。 若要运行以前保存的查询，请选择已保存的查询。

![查看集查询](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>生成审阅集查询

您可以使用关键字、属性和条件组合在"关键字"条件中生成查询。 还可以将条件分组为一个 (一个称为条件) 构建更复杂的查询的块。 有关可以搜索的元数据属性的列表和说明，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。

### <a name="conditions"></a>条件

审阅集内每个可搜索字段都有一个可用于生成查询的相应条件。

存在多种类型的条件：

- Freetext：自由文本条件用于文本字段，如主题。 可以通过用逗号分隔出多个搜索词来列出这些搜索词。

- Date：日期条件用于日期字段，如上次修改日期。

- 搜索选项：搜索选项条件将提供审阅集内特定字段的可能值列表。 这用于审阅集可能值有限数量的字段（如发件人）。

- 关键字：关键字条件是可用于搜索词或使用 KQL 类似查询语言的 freetext 条件的特定实例。 有关详细信息，请参阅下文。

### <a name="query-language"></a>查询语言

除了条件之外，您还可以在"关键字"条件中使用类似 KQL 的查询语言来构建查询。 审阅集查询的查询语言支持标准布尔运算符，如AND、OR、NOT和 **NEAR**。 它还支持单字符通配符 (？) 和多字符通配符 (*) 。

## <a name="filters"></a>筛选器

除了可以保存的查询之外，您还可以使用审阅集筛选器将其他条件快速应用于审阅集查询。 使用筛选器可帮助您进一步优化审阅集查询显示的结果。

![审阅集筛选器](../media/AeDReviewSetFilters.png)

筛选器与查询有两种显著区别：

- 筛选器是暂时性的。 它们不会延续到现有会话之外。 换句话说，无法保存筛选器。 查询将保存到审阅集，并且只要打开审阅集，就会访问查询。

- 筛选器始终是累加的。 除当前审阅集查询外，还应用筛选器。 应用其他查询将替换当前查询返回的结果。
