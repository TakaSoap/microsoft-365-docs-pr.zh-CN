---
title: 提前电子数据展示中的搜索统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: 通过查看在高级电子数据展示中运行集合搜索后生成的统计信息，验证您的搜索结果。
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286078"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>高级电子数据展示中的搜索统计信息

验证搜索结果的一种方法是查看结果周围的统计信息，以确保它们符合您的预期。 搜索完成后，"搜索详细信息" 浮出控件上将显示高级别统计信息：

- 搜索检索到的项目数和数量

- 在搜索位置中找到的部分索引或未编制索引的项目的编号和数量

- 搜索的邮箱和位置的数量。
若要查看更详细的统计信息，请单击 "搜索详细信息" 浮出控件中的 "统计信息"。

## <a name="summary-view"></a>摘要视图

在摘要视图中，您可以查看按位置类型划分的搜索结果 (例如，Exchange) 。 对于每个位置类型，您可以查看以下内容：

- 包含符合搜索条件的项目的位置数

- 来自符合搜索条件的这些位置的项目数

- 符合搜索条件的项的总数量。

## <a name="top-locations-view"></a>顶部位置视图

在 "顶部位置" 视图中，可以看到具有最匹配项的各个位置。 对于每个位置，您将看到：

- 位置名称 (例如 SharePoint URL) 

- 位置类型

- 匹配搜索条件的项目数

- 符合搜索条件的项的总数量。

## <a name="queries-view"></a>查询视图

如果您已在查询中使用 (c:s) 关键字或关键字行，则可以在 "每个位置的查询视图" 类型中查看查询细目。 对于每个位置类型，您将看到：

- 部分：此列将包含 "Primary" 或 "关键字" 一词。 "Primary" 表示该行显示整个查询的统计信息，而 "关键字" 表示查询组件之一。

- 查询：行所引用的实际查询组件。 如果 Part 为 "Primary"，则为整个查询;如果 Part 为 "关键字"，你将在此处看到一个查询组件。
  
  - 当您在未指定任何关键字) 的情况下搜索所有 contentin 邮箱时 (，实际查询 (大小 >= 0) 以便返回所有项目
  
  - 当您搜索 SharePoint Online 和 OneDrive for Business 网站时，将添加以下两个组件：
    
    - NOT IsExternalContent： 1-排除本地 SharePoint 组织中的任何内容
    
    - NOT isOneNotePage： 1-排除所有 OneNote 文件，因为这些文件是与搜索查询相匹配的任何文档的重复项。

- 包含符合搜索条件的项目的位置的数量。

- 来自这些位置的符合搜索条件的项目数。

- 符合搜索条件的项的总数量。
