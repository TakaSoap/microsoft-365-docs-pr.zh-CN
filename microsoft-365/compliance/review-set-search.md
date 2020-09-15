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
ms.openlocfilehash: 508e8e9fdb4a558a998a33aa561dc3755edcc40d
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816715"
---
# <a name="query-the-data-in-a-review-set"></a>查询审阅集中的数据

在大多数情况下，能够深入查看评审集中的数据并整理这些数据以促进更高效的审阅，这将非常有用。 在审阅集中使用查询可帮助您将重点放在符合评审条件的文档子集上。

## <a name="creating-and-running-a-query-in-a-review-set"></a>在审阅集中创建和运行查询

若要在审阅集中对文档创建和运行查询，请选择 "审阅集" 中的 " **新建查询** "。 命名查询并定义条件后，请选择 " **保存** " 以保存并运行查询。 若要运行以前保存的查询，请选择一个已保存的查询。

![查看集查询](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>生成审阅集查询

可以在关键字条件卡中使用条件卡片和查询语言的组合来构建查询。 您还可以将条件卡片组合在一起，将其作为称为 *条件组* 的块 () 生成更复杂的查询。 有关可以搜索的元数据属性的列表和说明，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。

### <a name="condition-cards"></a>条件卡片

审阅集中的每个可搜索字段都有一个对应的条件卡，可用于生成查询。

有多种类型的条件卡：

- Freetext： freetext 条件卡用于文本字段，如 subject。 您可以通过用逗号分隔多个搜索词来列出它们。

- 日期：日期条件卡片用于日期字段（如 "上次修改日期"）。

- 搜索选项：搜索选项条件卡片将为您的审阅集中的特定字段提供可能的值列表。 这用于在您的审核集中有有限数量的可能值的字段，如发件人。

- 关键字：关键字条件卡是 freetext 条件卡的特定实例，可用于搜索术语，或在中使用类似 KQL 的查询语言。 有关更多详细信息，请参阅下文。

### <a name="query-language"></a>查询语言

除了条件卡片之外，还可以在关键字卡片中使用类似 KQL 的查询语言来生成查询。 评审 set 查询的查询语言支持标准布尔运算符，例如 **AND**、 **OR**、 **NOT**和 **NEAR**。 它还支持单字符通配符 (？ ) 和多字符通配符 ( * ) 。

## <a name="filters"></a>筛选器

除了可以保存的查询之外，还可以使用审阅设置筛选器将其他条件快速应用于审阅集查询。 使用筛选器可帮助您进一步优化由审阅集查询显示的结果。

![查看设置筛选器](../media/AeDReviewSetFilters.png)

筛选器与查询的区别在于以下两个重要方式：

- 筛选器是瞬态的。 它们不会保留在现有会话之外。 换言之，不能保存筛选器。 查询保存到审阅集，并在打开评审集时访问它们。

- 筛选器始终是累加的。 除了当前的审阅集查询之外，还将应用筛选器。 应用不同的查询将替换当前查询返回的结果。
