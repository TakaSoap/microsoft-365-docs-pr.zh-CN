---
title: 停用中的相关性模块Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Advanced eDiscovery中的相关性模块将于 2021 年 3 月 10 日停用。 本文介绍在停用相关性之前要执行哪些工作。 具体而言，通过运行批计算完成任何未完成的模型，以便可以保留模型中的元数据。
ms.openlocfilehash: ed8e65f7dcf17c49d1a3f8b9af920272bd1692b8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177347"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>停用中的相关性模块Advanced eDiscovery

2021 年 3 月 10 日，我们将停用 Advanced eDiscovery 中的相关性模块。 此停用意味着组织将不再能够访问相关性模块 (通过访问 Advanced eDiscovery 案例的"管理审阅集相关性") 或能够访问任何现有相关性  >  模型。 即将停用的当前相关性模块将在 2021 年第 2 季度替换为新的预测编码解决方案。 这一新功能将允许组织在更轻松、更直观的工作流中构建自己的预测编码模型。

若要准备即将停用，我们建议使用相关性模块的组织通过运行所有现有模型的批处理计算，在停用日期之前导出其模型的输出。 模型的所有相关性分数将永久存储在相应的审阅集内，在导出文档时可访问。 相关性分数也会作为元数据保留在加载文件中。 此外，您仍能够基于相关性分数筛选审阅集内的内容，并有权访问相关性模型生成的所有元数据。

## <a name="complete-unfinished-models"></a>完成未完成的模型

对于任何未完成的相关性模型，请完成评估、培训和批量计算，以便可以将模型应用到审阅集内的文档。 完成批处理计算将在相关性模块停用日期后保留信息。

以下是完成任何未完成模型的步骤：

1. 对模型进行训练，直至其稳定并准备好进行批计算。 请参阅 [标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)。

   以下屏幕截图显示了一个可供批量计算的模块。 请注意，评估和培训已完成，下一步是运行批量计算。

   ![准备好进行批量计算的模型的屏幕截图。](../media/ReadyForBatchCalculation.png)

2. 运行批处理计算。 请参阅 [执行批处理计算](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)。

3. 验证批计算是否成功。 请参阅 [批处理计算结果](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。

有关完成未完成的相关性模型的帮助，请与 Microsoft 支持部门联系。
