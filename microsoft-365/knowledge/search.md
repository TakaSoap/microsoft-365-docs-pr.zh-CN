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
ms.openlocfilehash: 36901cf32a0633aaa5fc08e45021d13c7b06dd0b
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795990"
---
# <a name="use-microsoft-search-to-find-topics-in-microsoft-viva-topics"></a>使用 Microsoft 搜索查找 Microsoft Viva 主题中的主题

虽然 Viva 主题用户可以通过主题要点在网站中查找主题SharePoint，但用户也可以通过 Microsoft 搜索找到这些主题。 

## <a name="topic-answer"></a>主题答案

在 Microsoft 搜索服务中搜索特定主题 (例如，"Saturn") ，如果主题存在且找到，它将以答案建议格式显示结果。

主题答案将显示：
- 主题名称
- 备用名称：主题的备用名称或首字母缩略词。
- 定义：由 AI 提供或个人手动添加的主题说明。
- 建议或固定的人：AI 建议或用户固定到主题的人
- 建议或固定的资源：AI 建议的文件、页面或网站，或用户固定到主题的文件、页面或网站。 

   ![搜索中的主题](../media/knowledge-management/search-topic-answer.png) 

主题页面可以显示在搜索结果中，即使主题答案卡未显示。

Word、PowerPoint、Outlook 和 Excel 中的搜索结果还将在找到主题答案时显示。


## <a name="acronyms"></a>首字母缩略词

在 Viva 主题中，可以手动编辑主题，以包含用作备用名称的首字母<b>缩写。</b> 这使仅通过主题首字母缩写词进行搜索的用户可以通过 Microsoft 搜索找到主题答案。

[首字母缩写词"答案](/microsoftsearch/manage-acronyms) "是 Microsoft 搜索提供的一项功能，独立于 Viva 主题进行管理。

## <a name="bookmarks-and-topics"></a>书签和主题

[](/microsoftsearch/manage-bookmarks)书签是一项 Microsoft 搜索功能，可帮助用户通过搜索工具快速查找重要网站和工具 (例如，在 Microsoft 365 租户外部的外部网站上使用旅行预订) 。 它们由搜索管理员在管理中心Microsoft 365创建。 

对于要查找有关预订出差信息的用户：

- 如果某些用户知道旅行工具 (例如，"Concur") ，则创建书签以直接转到外部网站会更容易。
- 对于通常搜索"旅行"的用户，在"旅行"上创建一个主题，该主题包含他们希望看到的信息。 请考虑在主题的说明中添加指向 Concur 外部站点的链接。 如果链接改为指向托管在 Microsoft 365 租户上的内部旅行预订网站，你可以将其添加到"固定资源"。
 
### <a name="search-results-priority"></a>搜索结果优先级 

在用户的搜索体验中，当用户搜索"travel"等字词时，如果书签可用，书签将显示在主题的前面。
