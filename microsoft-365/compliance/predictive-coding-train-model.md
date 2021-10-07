---
title: 在 Advanced eDiscovery 中训练预测编码Advanced eDiscovery
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
ms.openlocfilehash: b5f1a958696dad84ac2bedec8f1ab7d23dfa6428
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204235"
---
# <a name="train-a-predictive-coding-model-preview"></a>训练预测编码模型 (预览) 

在 Advanced eDiscovery 创建预测编码模型后，下一步是执行第一个培训轮，以针对审阅集内的相关内容和非相关内容对模型进行培训。 完成第一轮培训后，可以执行后续培训轮，以提高模型预测相关和非相关内容的能力。

若要查看预测编码工作流，请参阅了解预测编码[Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>在训练模型之前

- 在培训轮中，根据文档中内容的相关性将项目标记为"相关"或"不相关"。 不要将决策基于元数据字段中的值。 例如，对于电子邮件或Teams，不要根据邮件参与者做出标签决定。

## <a name="train-a-model-for-the-first-time"></a>首次训练模型

1. In the Microsoft 365 合规中心， open an Advanced eDiscovery case and then select the **Review sets** tab.

2. 打开审阅集，然后单击分析 **管理** 预测  >  **编码 (预览) 。**

3. 在预测 **编码模型 (预览)** 页面上，选择要训练的模型。

4. 在"**概述"** 选项卡上的"**第 1 轮"下**，单击"**开始下一个培训轮"。**

   将显示 **"** 培训"选项卡，其中包含要标记的 50 个项目。

5. 查看每个文档，**然后选择阅读窗格** 底部的"相关"或"不相关"按钮以标记该文档。

   ![将每个文档标记为相关或不相关。](..\media\TrainModel1.png)

6. 标记完所有 50 个项目后，单击"完成 **"。**

    系统需要几分钟时间从你的标签"学习"并更新模型。 此过程完成后，将在预测编码模型和预览版页面上为模型 (**就绪)** 状态。

## <a name="perform-additional-training-rounds"></a>执行其他培训轮

执行第一轮培训后，可以按照上一部分中的步骤执行后续培训轮。 唯一的区别是，将在"模型概述"选项卡上更新培训 **轮** 的数量。例如，执行第一轮培训后，可以单击"开始 **下** 一个培训轮"开始第二轮培训。 等等。

每轮培训 (进行中和已完成) 都将显示在模型的"培训"选项卡上。  选择培训轮时，将显示一个包含该轮的信息和指标的飞出页。

## <a name="what-happens-after-you-perform-a-training-round"></a>执行培训轮后会发生什么情况

执行第一个培训轮之后，将启动一个执行下列操作的工作：

- 根据你在培训集内标记 40 个项目时如何，模型会从你的标签中学习并更新自身，以变得更准确。

- 然后，模型将处理整个审阅集内的每一项，并分配一个介于 0 和 **1** 之间（不相关的 () 和 **1 (相关的) ）。**

- 模型为在培训轮中标记的控件集的 10 个项目分配预测分数。 模型会将这 10 个项目的预测分数与在培训轮中分配给该项目的实际标签进行比较。 基于此比较，模型标识以下分类 (控件集混淆矩阵) 评估模型预测性能：

  <br>

  ****

  |标签|模型预测项目相关|模型预测项目不相关|
  |---|---|---|
  |**审阅者标签项（如相关）**|True positive|误报|
  |**审阅者标签项不相关**|假负|True negative|
  |

  基于这些比较，模型派生 F 分数、精度和调用指标的值以及每个指标的误差范围。 这些模型性能指标的分数显示在培训轮的飞出页面上。 有关这些指标的说明，请参阅预测 [编码参考](predictive-coding-reference.md)。

- 最后，模型确定将用于下一个培训轮的接下来的 50 个项目。 这一次，模型可能会从控件集选择 20 个项目和审阅集的 30 个新项，并指定这些项目作为下一轮的培训集。 下一轮培训的采样未进行统一采样。 模型将优化审阅集内项目的采样选择，以选择预测不明确的项目，这意味着预测分数在 0.5 范围内。 此过程称为偏 *置选择*。

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>执行后续培训轮后会发生什么情况

执行第一个培训 (之后执行后续培训) ，模型将执行以下操作：

- 模型将基于你应用于该轮培训中培训集的标签进行更新。

- 系统计算模型对控件集内项目预测的分数，并检查该分数是否与控件集内项目的标记方式一致。 评估针对所有培训轮的控件集的所有标记项目执行。 此评估的结果将合并到模型"概述 **"** 选项卡上的仪表板中。

- 更新的模型重新处理审阅集内的每一项，并为每个项分配更新后预测分数。

## <a name="next-steps"></a>后续步骤

执行第一轮培训后，可以执行更多培训轮或将模型预测分数筛选器应用于审阅集，以查看模型已预测为相关或不相关的项目。 有关详细信息，请参阅将 [预测分数筛选器应用于审阅集](predictive-coding-apply-prediction-filter.md)。
