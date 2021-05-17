---
title: '用于预览Advanced eDiscovery (预测) '
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Advanced eDiscovery中新的预测编码模块使用机器学习来分析审阅集内的文档，以预测哪些文档与案例或调查相关。
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382950"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>用于预览Advanced eDiscovery (预测) 

使用 Advanced eDiscovery 中新的预测编码模块，可以创建和构建一个模型，以优先查看以最相关的文档开始的文档。 若要开始，您可以创建一个模型，将文档标记为 50 个，然后按模型预测分数筛选文档，以查看相关的非相关文档。

以下是工作流的快速概述：

1. 打开审阅集内预测编码模块。

   ![单击评论中的"分析"下拉列表以转到预测编码模块](..\media\PredictiveCoding1.png)

2. 在" **预测编码模型"** 页上，单击" **新建模型** "以创建新的预测编码模型。

   ![创建新模型](..\media\PredictiveCoding2.png)

3. 将至少 50 个文档标记为 **"相关**"或"**不相关"。** 此标记用于训练系统。

   ![将文档标记为与系统培训相关或不相关](..\media\PredictiveCoding3.png)

4. 将 **模型预测分数** 筛选器应用于评价集。 为此，请执行以下操作：

   1. 在审阅集内，单击"筛选器 **"。**
   2. 在"**筛选器**"飞出页中，展开"分析 **/ML"** 部分，然后选中要应用的模型的"预测分数"复选框。
   3. 在预测 **分数** 筛选器中，指定预测分数。 筛选器将显示审阅集内与预测分数匹配的文档。

      ![指定用于筛选文档预测分数](..\media\PredictiveCoding4.png)

5. 监视模型的性能、状态和稳定性。

   ![监视模型的性能、状态和稳定性](..\media\PredictiveCoding5.png)
