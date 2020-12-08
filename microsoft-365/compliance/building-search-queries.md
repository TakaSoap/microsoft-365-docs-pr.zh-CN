---
title: 在高级电子数据展示中构建搜索查询
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
description: 在 Microsoft 365 中使用高级电子数据展示搜索数据时，请使用关键字和条件缩小搜索范围。
ms.openlocfilehash: 38322963f04ad67d8675247bdd754ffb1d2f13e8
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588549"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a>在高级电子数据展示中构建搜索集合查询

在生成搜索查询以在高级电子数据展示事例中收集数据时，可以使用关键字查找特定内容和条件，以缩小搜索范围，以返回与法律调查最相关的项目。

![使用关键字和条件缩小搜索结果范围](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a>关键字搜索

在搜索查询的 " **关键字** " 框中键入关键字查询。 您可以指定关键字、电子邮件属性（如发送和接收日期）或文档属性（如文件名或文档的上次更改日期）。 可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 您还可以搜索敏感信息 (例如，在 SharePoint 和 (OneDrive 中的文档中) 的社会保险号) 的电子邮件中，或搜索在外部共享的文档。 如果将 " **关键字** " 框留空，则位于指定内容位置的所有内容都将位于搜索结果中。

## <a name="keyword-list"></a>关键字列表

或者，也可以选中 " **显示关键字列表** " 复选框，并在每行中键入关键字或关键字短语。 每行中的关键字都通过逻辑运算符连接 (，该运算符表示为搜索查询语法) 中的 *c:s* ，该运算符在创建的搜索查询中的 **OR** 运算符的功能类似。 这意味着搜索结果中包含任意行中包含任意关键字的项。 您最多可以在高级电子数据展示搜索查询的关键字列表中添加180行。

![使用关键字列表获取查询中每个关键字的统计信息](../media/KeywordListSearch.png)

为什么使用关键字列表？ 您可以获取统计信息，以显示与关键字列表中的每个关键字匹配的项目数。 这可以帮助您快速找出最 (和最不) 有效的关键字。 您还可以使用关键字短语 () 关键字列表中行中的括号括起的关键字短语。 有关搜索统计信息的详细信息，请参阅 [搜索统计](search-statistics.md)信息。

## <a name="conditions"></a>条件

您可以添加搜索条件以缩小搜索范围，并返回更精致的结果集。 每个条件向开始搜索时创建和运行的搜索查询添加一个子句。 条件以逻辑方式连接到关键字框中指定的关键字查询，逻辑运算符 (它表示为与 **AND** 运算符功能类似的搜索查询语法) 中的 *c:c* 。 这意味着项目必须同时满足关键字查询和要包含在搜索结果中的一个或多个条件。 这就是条件如何帮助缩小结果范围的原理。 有关可在搜索查询中使用的条件的列表和说明，请参阅 [关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的 "搜索条件" 部分。
