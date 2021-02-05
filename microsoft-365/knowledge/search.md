---
title: 使用 Microsoft 搜索查找 Microsoft Viva 主题中的主题
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
description: 了解如何在 Microsoft Viva 中搜索主题。
ms.openlocfilehash: 484d2477f7e4dbef096a4b8a2d30095708c6cc3f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50108287"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>使用 Microsoft 搜索查找 Microsoft Viva 主题中的主题

虽然 Viva 主题用户可以通过其 SharePoint 网站中的主题突出显示查找主题，但也可通过 Microsoft 搜索找到主题。 

## <a name="topic-answer"></a>主题答案

在 Microsoft 搜索服务中搜索特定主题 (例如，"Saturn") ，如果主题存在且找到，它将以"答案"建议格式显示结果。

主题答案将显示：
- 主题名称
- 备用名称：主题的备用名称或缩写。
- 定义：AI 提供或由人员手动添加的主题的说明。
- 建议或固定人员：由 AI 建议或用户固定到主题的人
- 建议或固定的资源：AI 建议或用户固定到主题的文件、页面或网站。 

   ![搜索中的主题](../media/knowledge-management/search-topic-answer.png) 

即使主题应答卡未显示，主题页面也可以显示在搜索结果中。


## <a name="acronyms"></a>首字母缩略词

在 Viva 主题中，可以手动编辑主题，以包含用作备用名称的首字母缩写 <b>词</b>。 这样，仅通过主题缩写词进行搜索的用户可以通过 Microsoft 搜索查找主题答案。

[首字母缩略词解答](https://docs.microsoft.com/microsoftsearch/manage-acronyms) 是 Microsoft 搜索提供的一项功能，独立于 Viva 主题进行管理。

## <a name="bookmarks-and-topics"></a>书签和主题

[](https://docs.microsoft.com/microsoftsearch/manage-bookmarks)书签是一项 Microsoft 搜索功能，可帮助用户通过搜索工具快速查找重要网站和工具 (例如，在 Microsoft 365 租户外部的外部网站上使用旅行预订) 。 它们由 Microsoft 365 管理中心中的搜索管理员创建。 

对于要查找有关预订工作行程的信息的用户：

- 如果某些用户知道旅行工具 (例如，"Concur") ，则创建书签以直接转到外部站点会更容易。
- 对于通常搜索"旅行"的用户，请创建一个有关"旅行"的主题，该主题包含他们希望看到的信息。 请考虑在主题说明中添加指向 Concur 外部站点的链接。 如果链接改为指向 Microsoft 365 租户上托管的内部旅行预订网站，你可以将其添加到"固定资源"。
 
### <a name="search-results-priority"></a>搜索结果优先级 
 
在用户搜索体验中，当用户搜索类似"旅行"的术语时，搜索结果将在 Microsoft 搜索中以以下优先级显示
1. 已发布或已确认的主题 
2. 书签
3. 建议的主题 



