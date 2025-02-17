---
title: 预测编码引用
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
description: ''
ms.openlocfilehash: ff681793a86d9953088c2c4da65553e1d2c54d22
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170567"
---
# <a name="predictive-coding-reference-preview"></a>预测编码参考 (预览) 

本文介绍预测编码工具在 Advanced eDiscovery 中的关键概念和Advanced eDiscovery。 本文中的各节按字母顺序列出。

## <a name="confidence-level"></a>置信度

可信度是创建预测编码模型时的高级设置。 它定义模型的性能指标 (例如，丰富度、精度和调用) 都位于指定的 (范围内 (该范围决定了为模型) 定义的误差范围，该范围代表预测的真值对模型分配给审阅集内的项目进行评分。 置信水平和误差范围的值还有助于确定控件集中包含的项目数。 可信度的默认值为 0.95 或 95%。

## <a name="control-set"></a>控件集

在预测编码模型的培训过程中使用控件集。 控件集用于评估模型分配给项目（带有你在培训轮中执行的标签）预测分数。 控件集的大小取决于审阅集内的项目数，以及创建模型时所设置的错误值的可信度和边距。 控件集内的项目永远不会更改，并且用户无法识别。 在培训轮的飞出页面上显示控件集合中的项目总数。

## <a name="control-set-confusion-matrix"></a>控件集混淆矩阵

完成培训轮后，模型会为在培训轮中标记的控件集的 10 个项目分配预测分数。 模型会将这 10 个项目的预测分数与在培训轮中分配给该项目的实际标签进行比较。 基于此比较，模型确定以下分类来评估模型预测性能：

<br>

****

|标签|模型预测项目相关|模型预测项目不相关|
|---|---|---|
|**审阅者标签项（如相关）**|True positive|误报|
|**审阅者标签项不相关**|假负|True negative|
|

基于这些比较，模型派生 F 分数、精度和调用指标的值以及每个指标的误差范围。 矩阵中每个混淆类型的数量显示在培训轮的飞出页面上。

## <a name="f-score"></a>F 分数

F 分数是精度和调用指标的分数的加权平均值。  此指标的分数范围是 **0** 到 **1。** 分数接近 **1** 表示模型将更准确地检测相关项。 F 分数指标显示在模型仪表板上以及每个培训轮的飞出页面上。

## <a name="margin-of-error"></a>误差边距

当你创建预测编码模式时，误差边距是一个高级设置。 它指定性能指标中的错误程度 (例如，丰富度、精度和) 从控件集内项目的随机采样派生的调用率。 误差范围越小，需要设置更大的控件，以确保模型的性能指标在较小的范围内。 误差范围和可信度的值还有助于确定控件集中包含的项目数。 错误边距的默认值为 0.05 或 5%。

## <a name="model-stability"></a>模型稳定性

模型稳定性指示模型能够准确预测审阅集内的文档是否相关。 当模型不稳定时，可能需要执行更多培训轮，以包括模型的稳定性。 当模型稳定时，无需再执行培训轮。 模型仪表板指示模型稳定性的当前状态。 当模型稳定时，性能指标已到达与置信水平和误差范围设置相匹配的级别。

## <a name="overturn-rate"></a>上转率

"上转率"是审阅集内各项的百分比，其中预测分数在培训轮之间发生更改。 当回车率小于 5% 时，模型被视为稳定模型。 在模型仪表板上以及每个培训轮的飞出页面上，都显示"上转率"指标。 第一个培训轮的上转率为零，因为之前没有要翻入的预测分数。

## <a name="precision"></a>精度

精度指标用于度量模型预测的相关项目之间实际相关的项目的比例。 这意味着控件中的项将设置其中标签由审阅者相关并预测为与模型相关。 此指标的分数范围是 **0** 到 **1。** 分数接近 **1** 表示模型将识别较少的非相关项。 精度指标显示在模型仪表板上以及每个培训轮的飞出页面上。

## <a name="prediction-score"></a>预测分数

这是模型分配给审阅集内每个文档的分数。 分数基于与模型从培训轮中学习相比的文档相关性。 通常，预测分数在 0 到 **0.5** 之间的项被视为不相关，预测分数在 **0.5** 和 **1** 之间的项被视为相关项。  预测分数包含在文档元数据字段中。 可以使用预测筛选器显示审阅集内指定预测范围内的项目。

## <a name="recall"></a>Recall

调用指标用于度量模型预测的项目与实际相关的项目之间的相关性。 这意味着，审阅者还将模型预测相关的控件集内的项目标记为相关。 此指标的分数范围是 **0** 到 **1。** 分数接近 **1** 表示模型将识别大部分相关项。 每个培训轮的撤回指标显示在模型仪表板和飞出页面上。

## <a name="review-set"></a>审阅集

审阅集提供预测编码模型的范围。 为审阅集创建新模型时，会从审阅集选择控件集和培训集的项目。 当模型分配预测分数时，它会为评价中的项目分配这些分数。 创建预测编码模型之前，您必须将所有项目添加到审阅集。 如果在创建模型后添加项目，将不会为这些项目分配预测分数。

## <a name="richness"></a>丰富度

丰富度指标用于度量模型预测的相关审阅集项的百分比。 此指标的分数范围是 **0** 到 **1。** 丰富度指标显示在模型仪表板上。

## <a name="sampled-items"></a>示例项

术语采样项目是一个对审阅集 (中包含文本) 且在您创建预测编码模型时选择并与该控件集关联的项目的随机样本的引用。 还会针对每个培训轮选择项目的随机样本。 为模型的控件集选择的项目永远不会包含在同一模型的培训集内。 反之也是如此：培训集项永远不会包含在控件集内。

## <a name="training-set"></a>培训集

模型从审阅集随机选择项目并添加到培训集。 在培训轮中，除了控件集) 中的项目外，培训集 (中的项目还显示给你，以便你可以将每个项目标记为"相关"或"不相关"。 此标记或"培训"过程可帮助模型了解如何预测审阅中的哪些项目是相关项还是不相关项。 每次执行培训轮时，模型都会从评价中选择更多项目，并添加到该培训轮的培训集。 从不为培训集选择控件集的项目。
