---
title: 停用高级电子数据展示中的相关性模块
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 高级电子数据展示中的相关性模块将于 2021 年 3 月 10 日停用。 本文介绍在相关性停用之前要执行哪些工作。 具体而言，通过运行批计算完成任何未完成的模型，以便可以保留模型中的元数据。
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122523"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>停用高级电子数据展示中的相关性模块

2021 年 3 月 10 日，我们将停用高级电子数据展示中的相关性模块。 此停用意味着组织将无法再访问相关性模块 (，方法为在高级电子数据展示案例) 中管理审阅集相关性，或能够访问任何现有相关性  >  模型。 即将停用的当前相关性模块将在 2021 年第 2 季度替换为新的预测编码解决方案。 这一新功能将允许组织在更轻松、更直观的工作流中构建自己的预测编码模型。

为准备即将停用，我们建议使用相关性模块的组织通过运行所有现有模型的批量计算，在停用日期之前导出其模型的输出。 模型的所有相关性分数将永久存储在相应的审阅集内，在导出文档时可访问。 相关性分数也会作为元数据保留在加载文件中。 此外，你仍然能够基于相关性分数筛选审阅集内的内容，并有权访问相关性模型生成的所有元数据。

## <a name="complete-unfinished-models"></a>完成未完成的模型

对于任何未完成的相关性模型，请完成评估、培训和批量计算，以便可以将模型应用于审阅集内的文档。 完成批计算将在相关性模块停用日期后保留信息。

以下是完成任何未完成模型的步骤：

1. 对模型进行训练，直到其稳定下来并准备好进行批计算。 请参阅 [标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)。

   以下屏幕截图显示了一个可供批量计算的模块。 请注意，评估和培训已完成，下一步是运行批计算。

   ![可供批量计算的模型屏幕截图](../media/ReadyForBatchCalculation.png)

2. 运行批处理计算。 请参阅["执行批处理计算"。](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)

3. 验证批计算是否成功。 请参阅 [批计算结果](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。

有关完成未完成的相关性模型的帮助，请联系 Microsoft 支持部门。
