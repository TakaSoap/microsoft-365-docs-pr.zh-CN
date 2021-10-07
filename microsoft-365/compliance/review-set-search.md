---
title: 查询审阅集内的内容
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在审阅集内创建和运行查询，以组织内容，以在Advanced eDiscovery审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f1f7fa8f811f5a2bda526454ae8b03163cfed187
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206057"
---
# <a name="query-and-filter-content-in-a-review-set"></a>查询和筛选审阅集中的内容

在大多数情况下，深入探究审阅集内的内容并组织该内容以促进更高效的审阅将非常有用。 在审阅集中使用筛选器和查询可帮助您重点关注满足审阅条件的文档的子集。

## <a name="default-filters"></a>默认筛选器

在审阅集内，有五个默认筛选器预加载到审阅集：

- 关键字
- 日期
- 发件人/作者
- 主题/标题
- 标记

![默认筛选器类型。](../media/DefaultFilterTypes.png)

单击每个筛选器以展开它并分配一个值。 单击筛选器外部以自动将筛选器应用于审阅集。 以下屏幕截图显示了配置为显示日期范围内的文档的日期筛选器。

![展开的默认筛选器。](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a>添加或删除筛选器

若要添加或删除为审阅集显示的筛选器，请选择"筛选器"以打开显示在飞出页上的筛选器面板。 

![筛选面板。](../media/FilterPanel.png)

可用筛选器分为四个部分：

- **搜索**：提供不同搜索功能的筛选器。

- **分析&** 编码：运行文档分析作业或使用预测编码模型时生成& **添加到** 文档的属性筛选器。

- **ID：** 用于筛选文档的所有 ID 属性。

- **项目属性**：文档属性的筛选器。 

展开每个部分，选择或取消选择筛选器以在筛选器集中添加或删除它们。 添加筛选器时，筛选器集会显示该筛选器。 

![筛选器面板中的筛选器节和属性的列表。](../media/FilterPanel2.png)

> [!NOTE]
> 展开筛选器面板中的节时，您将注意到已选择默认筛选器类型。 您可以保持选中状态或取消选择它们，然后从筛选器集中删除它们。 

## <a name="filter-types"></a>筛选器类型

审阅集内每个可搜索字段都有一个对应的筛选器，可用于基于特定字段筛选项目。

筛选器有多种类型：

- **Freetext：** 将自由文本筛选器应用于文本字段，如"Subject"。 可以通过用逗号分隔多个搜索词来列出这些搜索词。

- **Date**：日期筛选器用于"上次修改日期"等日期字段。

- **搜索选项**：搜索选项筛选器提供一个可能值列表 (每个值都显示一个复选框，你可以为审阅中的特定字段) 复选框。 此筛选器用于审阅集可能值有限数量的字段，例如"发件人"。

- **关键字**：关键字条件是可用于搜索词的 freetext 条件的特定实例。 您还可以在此类型的筛选器中使用类似 KQL 的查询语言。 有关详细信息，请参阅本主题中的查询语言和高级查询生成器部分。

## <a name="include-and-exclude-filter-relationships"></a>包含和排除筛选器关系

您可以选择更改特定筛选器的包含和排除关系。 例如，在"标记"筛选器中，可以通过在下拉列表筛选器中选择"等于 **无** "来排除用特定标记标记的项目。 

![排除标记筛选器。](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a>将筛选器另存为查询

对筛选器感到满意后，可以将筛选器组合另存为筛选器查询。 这样，你可以在将来的审阅会话中应用筛选器。

若要保存筛选器，请选择 **"保存查询并** 命名它"。 您或其他审阅者可以通过选择"保存的筛选器查询"下拉列表并选择要应用于审阅集文档的筛选器查询来运行以前保存的筛选器查询。 

![保存筛选器查询。](../media/SaveFilterQuery.png)

若要删除筛选器查询，请打开筛选面板并选择查询旁边的回收站图标。

![删除筛选器查询。](../media/DeleteFilterQuery.png)

## <a name="query-language"></a>查询语言

除了使用筛选器之外，您还可以使用关键字筛选器中的 KQL 类似查询语言来构建审阅集搜索查询。 审阅集查询的查询语言支持标准布尔运算符，如AND、OR、NOT和 **NEAR**。 它还支持单字符通配符 (？) 和多字符通配符 (*) 。

## <a name="advanced-query-builder"></a>高级查询生成器

您还可以生成更高级的查询来搜索审阅集内的文档。

1. 打开筛选面板，选择" **筛选器"，** 然后展开" **搜索"** 部分。

  ![添加 KQL 筛选器。](../media/AddKQLFilter.png)

2. 选择 **KQL 筛选器**，然后单击"**打开查询生成器"。**

   在此面板中，您可以使用查询生成器创建复杂的 KQL 查询。 可以添加条件或添加条件组，这些条件组由 AND 或 **OR** 关系在逻辑上 **连接的多个条件** 组成。

   ![使用查询生成器配置复杂的筛选器查询。](../media/ComplexQuery.png)
