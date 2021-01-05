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
description: 通过查看在高级电子数据展示中运行集合搜索后生成的统计信息来验证搜索结果。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750773"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>高级电子数据展示中的搜索统计信息

可以验证搜索结果的一种方式是查看有关结果的统计信息，以确保它们符合您的预期。 搜索完成后，在搜索详细信息飞出上显示高级统计信息：

- 搜索检索的项目数和数量

- 在搜索位置找到的部分索引项或未编制索引的项目的数量和数量

- 搜索的邮箱数和位置。
若要查看更详细的统计信息，请单击搜索详细信息飞出中的"统计信息"。

## <a name="summary-view"></a>摘要视图

在"摘要"视图中，可以看到按位置类型（如 Exchange (）细分的) 。 对于每个位置类型，你可以看到：

- 包含符合搜索条件的项目的位置数

- 与搜索条件匹配的这些位置中的项目数

- 与搜索条件匹配的项目总数。

## <a name="top-locations-view"></a>顶部位置视图

在"顶部位置"视图中，可以看到匹配项最多的单个位置。 对于每个位置，你将看到：

- 位置名称 (例如 SharePoint URL) 

- 位置类型

- 匹配搜索条件的项目数

- 与搜索条件匹配的项目总数。

## <a name="queries-view"></a>查询视图

如果在查询 (c：s) 关键字行或关键字行，则您可以在查询视图中按位置类型查看查询的细分。 对于每个位置类型，你将看到：

- 部分：此列将包含单词"Primary"或"Keyword"。 "Primary"表示该行显示整个查询的统计信息，而"Keyword"表示查询组件之一。

- 查询：行引用的实际查询组件。 如果 Part 为"Primary"，这将是整个查询;如果部件是"关键字"，你将在此处看到其中一个查询组件。
  
  - 当您通过未指定任何关键字 (搜索所有内容邮箱时) ，实际查询的大小为 (>= 0) ，以便返回所有项目
  
  - 搜索 SharePoint Online 和 OneDrive for Business 网站时，将添加以下两个组件：
    
    - NOT IsExternalContent：1 - 排除本地 SharePoint 组织的任何内容
    
    - NOT isOneNotePage： 1 - 排除所有 OneNote 文件，因为这些文件是匹配搜索查询的任何文档的重复项。

- 项目与搜索条件匹配的位置数。

- 与搜索条件匹配的这些位置中的项目数。

- 与搜索条件匹配的项目总数。
