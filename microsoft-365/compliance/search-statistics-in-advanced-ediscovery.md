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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 通过查看在 Advanced eDiscovery 中运行集合搜索后生成的统计信息来验证Advanced eDiscovery。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59169610"
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

- 位置名称 (例如 URL SharePoint url) 

- 位置类型

- 与搜索条件匹配的项目数

- 与搜索条件匹配的项目总数。

## <a name="queries-view"></a>查询视图

如果在查询中使用 (c：s) 关键字或关键字行，可以在查询视图中按位置类型查看查询细分。 对于每个位置类型，你将看到：

- 部分：此列将具有单词"Primary"或"Keyword"。 "Primary"表示该行显示整个查询的统计信息，而"Keyword"表示查询组件之一。

- Query：行引用的实际查询组件。 如果 Part 为"Primary"，这将是整个查询;如果 Part 是"Keyword"，你将在此处看到其中一个查询组件。
  
  - 当您通过不指定 (关键字 () 搜索所有内容时，实际查询的大小为 (>= 0) 以便返回所有项目
  
  - 当您搜索 SharePoint Online OneDrive for Business网站时，会添加以下两个组件：
    
    - NOT IsExternalContent：1 - 从本地部署组织SharePoint内容
    
    - NOT isOneNotePage： 1 - 排除OneNote文件，因为这些文件是匹配搜索查询的任何文档副本。

- 项目符合搜索条件的位置数。

- 这些位置中与搜索条件匹配的项目数。

- 与搜索条件匹配的项目总数。
