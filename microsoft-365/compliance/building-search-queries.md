---
title: 在高级电子数据展示中生成搜索查询
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: 使用 Microsoft 365 中的高级电子数据展示搜索数据时，使用关键字和条件缩小搜索范围。
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838476"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a>在高级电子数据展示中生成集合的搜索查询

在高级电子数据展示案例中创建集合时[](collections-overview.md)配置搜索查询时，可以使用关键字查找特定内容和条件，以缩小搜索范围以返回与法律调查最相关的项目。

![使用关键字和条件缩小搜索结果范围](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>关键字搜索

在搜索查询的 **"关键字"** 框中键入关键字查询。 您可以指定关键字、电子邮件属性（如发送日期和接收日期）或文档属性（如文件名或上次更改文档的日期）。 可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 还可以搜索敏感信息 (例如 SharePoint 和 OneDrive) 文档中的社会保险号 (不在电子邮件) 中，或者搜索在外部共享的文档。 如果将" **关键字"框** 留空，则位于指定内容位置的所有内容都位于搜索结果中。

## <a name="keyword-list"></a>关键字列表

或者，也可以选中"显示关键字 **列表** "复选框，并在每行中键入关键字或关键字短语。 每行中的关键字由逻辑运算符 (该逻辑运算符在搜索查询语法) 中表示为 *c：s，* 其功能类似于所创建的搜索查询中的 **OR** 运算符。 这意味着任何行中包含任何关键字的项目均在搜索结果中。 您可以在高级电子数据展示搜索查询的关键字列表中最多添加 180 行。

![使用关键字列表获取查询中每个关键字的统计信息](../media/KeywordListSearch.png)

为什么使用关键字列表？ 您可以获取显示关键字列表中每个关键字匹配的项数的统计信息。 这可以帮助您快速识别最有效且最 (最) 关键字。 您还可以使用关键字短语 (关键字列表中的一行) 括号。 有关搜索统计信息详细信息，请参阅搜索 [统计信息](search-statistics-in-advanced-ediscovery.md)。

## <a name="conditions"></a>条件

您可以添加搜索条件来缩小搜索范围并返回更精确的结果集。 每个条件向开始搜索时创建和运行的搜索查询添加一个子句。 条件在逻辑上由逻辑运算符 (在搜索查询语法) 中表示为 *c：c，* 在功能上与 **AND** 运算符类似。在逻辑上，条件与关键字框中指定的关键字查询相连。 这意味着项目必须满足关键字查询和要包括在搜索结果中的一个或多个条件。 这就是条件如何帮助缩小结果范围的原理。 有关可在搜索查询中使用的条件的列表和说明，请参阅关键字查询和搜索条件 中的" [搜索条件"部分](keyword-queries-and-search-conditions.md#search-conditions)。
