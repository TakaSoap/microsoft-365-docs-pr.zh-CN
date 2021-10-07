---
title: 高级电子数据展示中的搜索统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 通过查看在 Advanced eDiscovery 中运行集合搜索后生成的统计信息来验证Advanced eDiscovery。
ms.openlocfilehash: ec339cd28fdd25457a668f992f20e59a4f10b289
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167230"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>搜索中的搜索Advanced eDiscovery

您可以验证搜索结果的一种方式是查看有关结果的统计信息，以确保它们符合您的预期。 搜索完成后，搜索详细信息飞出上会显示高级统计信息：

- 搜索检索的项目数和数量

- 在搜索位置找到的部分索引项或未编制索引的项目的数量和数量

- 搜索的邮箱数和位置。
若要查看更详细的统计信息，请单击搜索详细信息飞出框的"统计信息"。

## <a name="summary-view"></a>摘要视图

在"摘要"视图中，您可以查看按位置类型细分的搜索结果 (例如Exchange) 。 对于每个位置类型，你可以看到：

- 项目符合搜索条件的位置数量

- 这些位置中符合搜索条件的项目数

- 与搜索条件匹配的项目总数。

## <a name="top-locations-view"></a>顶部位置视图

在"顶部位置"视图中，可以看到匹配项最多的单个位置。 对于每个位置，你将看到：

- 位置名称 (，例如SharePoint URL) 

- 位置类型

- 与搜索条件匹配的项目数

- 与搜索条件匹配的项目总数。

## <a name="queries-view"></a>查询视图

如果在查询中使用了 (c：s 关键字) 关键字行，则您可以在查询视图中按位置类型查看查询的细分信息。 对于每个位置类型，你将看到：

- 部分：此列将具有单词"Primary"或"Keyword"。 "Primary"表示该行显示整个查询的统计信息，而"Keyword"表示查询组件之一。

- Query：行引用的实际查询组件。 如果 Part 为"Primary"，这将是整个查询;如果 Part 是"Keyword"，你将在此处看到其中一个查询组件。
  
  - 当您通过不指定任何关键字 (搜索邮箱中) ，实际查询的大小为 (>= 0) 以便返回所有项目
  
  - 当您搜索 SharePoint Online OneDrive for Business网站时，会添加以下两个组件：
    
    - NOT IsExternalContent：1 - 从本地部署组织SharePoint内容
    
    - NOT isOneNotePage： 1 - 排除所有OneNote文件，因为这些文件是匹配搜索查询的任何文档的重复项。

- 项目符合搜索条件的位置数。

- 这些位置中与搜索条件匹配的项目数。

- 与搜索条件匹配的项目总数。
