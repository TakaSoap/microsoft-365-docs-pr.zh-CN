---
title: 根据项目结果Advanced eDiscovery
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
description: 了解 Advanced eDiscovery 中的"决定"选项卡如何提供可帮助您确定审阅案例文件集的正确大小的数据。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1bab0cc7460e9260dd8f7bc6b5adb90d5a06a9b0e7832b28f7d3a2cb4e35f85
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53842336"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>基于相关性结果的决策Advanced eDiscovery
  
在 Advanced eDiscovery 的"相关性"模块中，"决定"选项卡提供用于查看和使用决策支持统计信息以确定案例文件审阅集大小的其他信息。
  
## <a name="using-the-decide-tab"></a>使用"决定"选项卡

![相关性决定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此选项卡包括以下组件：
  
- **问题**：从此处，可以从列表中选择感兴趣的问题。

- **Review-recall ratio**：根据相关性Advanced eDiscovery审阅的比较。 图表中的截止点表示要审阅的文件百分比，映射到相关性分数。 此阈值在相关性测试阶段使用，并用作剔除的导出阈值。 要审阅的文件数的默认截止点位于"调用次数"和"精度"之间的最佳平衡点。 实际截止点应该由用户根据目标以及成本权衡 (%审阅) 和风险 (%recall) 。 使用滑块，可以调整截止点并查看图形和参数的影响、调整要检索的相关文件的百分比时以及验证决策之前的效果。

- **参数**：Review、Recall、Next 相关参数和总成本参数是相对于整个案例的集合与审阅集相关的累积计算统计信息。 这些参数的定义如下：

  - **查看**：要基于此截止时间查看的文件百分比。

  - **撤回**：审阅集内相关文件的百分比。

  - **下一个** 相关 ：查看和标识当前不在审阅集内的另一个相关文件的成本。

  - **总成本：** 查看此百分比案例文件的成本。 成本参数设置可通过案例管理器进行设置。

  - **按相关性分数分布**：左侧显示深灰色的文件低于截止分数。 工具提示显示与总文件相关的审阅文件集内文件的相关性分数和相关百分比。

展开的 **"详细信息"** 窗格将显示更多详细信息。 集合图中的文件不包括空文件或空文件。 系列文件数字表示未在相关性中加载，但仍作为系列一部分进行计数的文件。
