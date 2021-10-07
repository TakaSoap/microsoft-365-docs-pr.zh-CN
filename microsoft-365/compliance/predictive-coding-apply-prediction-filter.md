---
title: 将预测分数筛选器应用于审阅集内的项目
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 使用预测分数筛选器显示预测编码模型预测为相关或不相关的项目。
ms.openlocfilehash: 04d0881e36c28a70df58a1aa7b054c641dfeeb2a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200457"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>将预测分数筛选器应用于预览版 (评价) 

在 Advanced eDiscovery 中创建预测编码模型并将其训练到稳定点后，可以应用预测分数筛选器来显示模型确定的审阅集项目是相关 (或与) 。 创建模型时，还会创建相应的预测分数筛选器。 可以使用此筛选器显示指定范围内分配了预测分数的项目。 通常 **，0** 和 **0 之间的** 预测分数分配给模型已预测的项并不相关。 分配了预测分数介于 **.5** 和 **1.0** 之间的项目是模型所预测的相关的项目。

以下是两种使用预测分数筛选器的方法：

- 确定模型所预测的相关审阅集内项目的审阅优先级。

- 从模型预测的审阅集剔除项目不相关。 或者，您可以使用预测分数筛选器取消对非相关项目的审阅的优先级。

## <a name="before-you-apply-a-prediction-score-filter"></a>应用预测分数筛选器之前

- 创建预测编码模型，以便创建相应的预测分数筛选器。

- 可以在任何培训轮之后应用预测分数筛选器。 但是，你可能想要在执行几轮后等待，或者等到模型稳定之后再使用预测分数筛选器。

## <a name="apply-a-prediction-score-filter"></a>应用预测分数筛选器

1. In the Microsoft 365 合规中心， open the Advanced eDiscovery case， select the **Review sets** tab， and then open the review set.

   ![单击"筛选器"以显示"筛选器"飞出页。](..\media\PredictionScoreFilter0.png)   

   预加载的默认筛选器显示在审阅集页面的顶部。 你可以将这些设置保留为 **Any**。

2. 单击 **"筛选器** "以显示" **筛选器** "飞出页。

3. 展开 **"分析&预测编码** "部分以显示一组筛选器。

      ![分析与预测编码部分&分数筛选器。](..\media\PredictionScoreFilter1.png)

   预测分数筛选器的命名约定是预测 **(模型名称) 。** 例如，名为模型 **A** 的模型预测分数筛选器名称是模型 **A** 预测 (预测) 。

4. 选择想要使用预测分数筛选器，然后单击"完成 **"。**

5. 在评价集页面上，单击预测分数筛选器下拉列表，然后键入预测分数范围的最小值和最大值。 例如，以下屏幕截图显示了一个介于 **.5** 和 **1.0 之间的预测分数范围**。

   ![预测分数筛选器的最小值和最大值。](..\media\PredictionScoreFilter2.png)

6. 单击筛选器外部以自动将筛选器应用于审阅集。

  在审阅集页面上显示指定范围内具有预测分数的文档列表。 

  > [!TIP]
  > 若要查看分配给文档的实际预测分数，可以单击阅读窗格中的" **元数据** "选项卡。 审阅集内所有模型预测的分数都显示在 **RelevanceScores** 元数据属性中。

## <a name="more-information"></a>更多信息

- 有关使用筛选器的信息，请参阅查询 [和筛选审阅集的内容](review-set-search.md)。
