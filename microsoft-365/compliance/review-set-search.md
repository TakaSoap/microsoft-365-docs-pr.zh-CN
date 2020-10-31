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
description: 了解如何在审阅集中创建和运行查询，以在高级电子数据展示事例中组织数据以实现更高效的审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816565"
---
# <a name="query-the-data-in-a-review-set"></a>查询审阅集中的数据

在大多数情况下，能够深入查看评审集中的数据并整理这些数据以促进更高效的审阅，这将非常有用。 在审阅集中使用查询可帮助您将重点放在符合评审条件的文档子集上。

## <a name="creating-and-running-a-query-in-a-review-set"></a>在审阅集中创建和运行查询

若要在审阅集中对文档创建和运行查询，请选择 "审阅集" 中的 " **新建查询** "。 命名查询并定义条件后，请选择 " **保存** " 以保存并运行查询。 若要运行以前保存的查询，请选择一个已保存的查询。

![查看集查询](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>生成审阅集查询

您可以使用关键字条件中的关键字、属性和条件的组合生成查询。 您还可以将条件分组为 (称为 *条件组* ) 的块，以生成更复杂的查询。 有关可以搜索的元数据属性的列表和说明，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。

### <a name="conditions"></a>条件

审阅集中的每个可搜索字段都具有可用于生成查询的相应条件。

有多种类型的条件：

- Freetext： freetext 条件用于文本字段，如 subject。 您可以通过用逗号分隔多个搜索词来列出它们。

- 日期：日期条件用于日期字段（如 "上次修改日期"）。

- 搜索选项：搜索选项条件将为您的审阅集中的特定字段提供可能的值列表。 这用于在您的审核集中有有限数量的可能值的字段，如发件人。

- 关键字：关键字条件是 freetext 条件的特定实例，可用于在中搜索术语或使用类似 KQL 的查询语言。 有关更多详细信息，请参阅下文。

### <a name="query-language"></a>查询语言

除条件外，还可以在关键字条件中使用类似 KQL 的查询语言来生成查询。 评审 set 查询的查询语言支持标准布尔运算符，例如 **AND** 、 **OR** 、 **NOT** 和 **NEAR** 。 它还支持单字符通配符 (？ ) 和多字符通配符 ( * ) 。

## <a name="filters"></a>筛选器

除了可以保存的查询之外，还可以使用审阅设置筛选器将其他条件快速应用于审阅集查询。 使用筛选器可帮助您进一步优化由审阅集查询显示的结果。

![查看设置筛选器](../media/AeDReviewSetFilters.png)

筛选器与查询的区别在于以下两个重要方式：

- 筛选器是瞬态的。 它们不会保留在现有会话之外。 换言之，不能保存筛选器。 查询保存到审阅集，并在打开评审集时访问它们。

- 筛选器始终是累加的。 除了当前的审阅集查询之外，还将应用筛选器。 应用不同的查询将替换当前查询返回的结果。
