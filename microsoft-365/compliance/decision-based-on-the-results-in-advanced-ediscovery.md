---
title: 根据高级电子数据展示中的结果做出决策
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 了解高级电子数据展示中的"确定"选项卡如何提供可帮助您确定案例文件审阅集的正确大小的数据。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769147"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>基于高级电子数据展示中的相关性结果的决策
  
在高级电子数据展示中的相关性模块中，"确定"选项卡提供用于查看和使用决策支持统计信息以确定案例文件审阅集大小的其他信息。
  
## <a name="using-the-decide-tab"></a>使用"确定"选项卡

![相关性决定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此选项卡包括以下组件：
  
- **问题**：在这里，可以从列表中选择感兴趣的问题。

- **Review-recall ratio：** Comparisons of Advanced eDiscovery review according to Relevance scores. 图表中的截止点表示要审阅的文件百分比，映射到相关性分数。 This is used in the Relevance Test phase and as an Export threshold for culling. 要审阅的文件数的默认截止点位于"恢复次数"和"精度"之间的最佳平衡点。 实际截止点由用户根据目标以及成本权衡 (%review) 和风险 (%recall) 。 使用滑块，可以调整截止点，并查看图形和参数的影响、调整要检索的相关文件的百分比以及验证决策之前的效果。

- **参数**：Review、Recall、Next 相关参数和总成本参数是与整个案例的集合相关的审阅集的累积计算统计信息。 这些参数的定义如下所示：

  - **Review**： Percentage of files to review based on this cutoff.

  - **回顾**：审阅集内相关文件的百分比。

  - **下一个** 相关：审阅和标识当前不在审阅集内的另一个相关文件的成本。

  - **总成本：** 查看此案例文件的百分比的成本。 成本参数设置由案例管理器设置。

  - **按相关性分数分布**：左侧显示深灰色的文件低于截止分数。 工具提示显示相关性分数和审阅文件集内文件相对于总文件的相关百分比。

展开的 **"详细信息** "窗格将显示更多详细信息。 集合图中的文件不包括空文件或 neb一文件。 系列文件数字表示未在相关性中加载但仍作为系列一部分的文件。
