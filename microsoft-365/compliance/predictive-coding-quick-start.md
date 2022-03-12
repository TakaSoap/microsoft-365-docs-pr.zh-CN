---
title: Advanced eDiscovery中的预测编码 - 快速入门
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
description: 了解如何开始使用 Advanced eDiscovery 中的预测编码模块。 本文将引导你完成使用预测编码来标识与调查最相关的审阅集内容的端到端过程。
ms.openlocfilehash: 2266f44e7b95c118314d76fe019a97b2db24f07c
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449466"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>快速入门：预览Advanced eDiscovery (预测) 

本文介绍在 Advanced eDiscovery 中使用预测编码的快速入门。 预测编码模块使用智能的机器学习功能来帮助你剔除大量与调查不相关的案例内容。 这是通过创建和培训自己的预测编码模型来完成的，这些预测代码模型可帮助你确定最相关的项目优先级，以进行审查。

以下是预测编码过程的快速概述：

![预测编码的快速启动过程。](..\media\PredictiveCodingQuickStartProcess.png)

To get started， you create a model， label as few as 50 items as relevant or not relevant. 然后，系统使用此培训将预测分数应用于审阅集内的每一项。 这使你可以根据预测分数筛选项目，这允许你首先查看最相关的 (或非) 项。 如果你想要使用更高的功能和调用率对模型进行培训，可以在后续培训轮中继续标记项目，直到模型稳定下来。 一旦模型稳定下来，你可以应用最终预测筛选器来设置要审阅项目的优先级。

有关预测编码的详细概述，请参阅了解预测编码[在](predictive-coding-overview.md)Advanced eDiscovery。

## <a name="step-1-create-a-new-predictive-coding-model"></a>步骤 1：创建新的预测编码模型

第一步是在审阅集内创建新的预测编码模型

1. In the Microsoft 365 合规中心， open an Advanced eDiscovery case and then select the **Review sets** tab.

2. 打开审阅集，然后单击 **分析** > 管理预测编码 **(预览)**。

   ![单击审阅集的"分析"下拉菜单以转到预测编码页面。](..\media\ManagePredictiveCoding.png)

3. 在" **预测编码模型 (预览)** ，单击"新建 **模型"**。

4. 在飞出页面上，键入模型名称和可选说明。

5. 单击 **"保存** "创建模型。

   系统需要几分钟的时间准备模型。 准备就绪后，你可以执行第一轮培训。

有关更详细的说明，请参阅 [创建预测编码模型](predictive-coding-create-model.md)。

## <a name="step-2-perform-the-first-training-round"></a>步骤 2：执行第一个培训轮

创建模型后，下一步是通过标记相关项或不相关项来完成第一轮培训。

1. 打开评论集，然后单击 **分析** > 管理预测编码 **(预览)**。

2. 在预测 **编码模型 (预览)** 页面上，选择要训练的模型。

3. 在" **概述"** 选项卡上的" **第 1 轮"下**，单击" **开始下一个培训轮"**。

   将显示 **"** 培训"选项卡，其中包含要标记的 50 个项目。

4. 查看每个文档，**然后选择阅读窗格** 底部的"相关"或"不相关"按钮以标记该文档。

   ![将每个文档标记为相关或不相关。](..\media\TrainModel1.png)

5. 标记完所有 50 个项目后，单击"完成 **"**。

    系统需要几分钟时间从你的标签"学习"并更新模型。 此过程完成后，"预测编码模型和预览模型"页上将显示模型 (**就绪)** 状态。

有关更详细的说明，请参阅 [训练预测编码模型](predictive-coding-train-model.md)。

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>步骤 3：将预测分数筛选器应用于审阅集内的项目

在租用一轮培训后，可以将预测分数筛选器应用于审阅集内的项目。 这样，你可以查看模型已预测为相关或不相关的项目。   

1. 打开审阅集。

   ![单击"筛选器"以显示"筛选器"飞出页。](..\media\PredictionScoreFilter0.png)

   预加载的默认筛选器显示在审阅集页面的顶部。 你可以将这些设置保留为 **Any**。

2. 单击 **"筛选器** "以显示" **筛选器** "飞出页。

3. 展开 **"分析&预测编码** "部分以显示一组筛选器。

      ![Analytics &编码部分中的预测分数筛选器。](..\media\PredictionScoreFilter1.png)

   预测分数筛选器的命名约定是预测 **分数 (模型名称)**。 例如，名为 Model A 的模型预测分数筛选器名称是 Model **A** 模型 (**预测**) 。

4. 选择想要使用预测分数筛选器，然后单击"完成 **"**。

5. 在评价集页面上，单击预测分数筛选器下拉列表，然后键入预测分数范围的最小值和最大值。 例如，以下屏幕截图显示了一个介于 **0.5** 和 **1.0 之间的预测分数范围**。

   ![预测分数筛选器的最小值和最大值。](..\media\PredictionScoreFilter2.png)

6. 单击筛选器外部以自动将筛选器应用于审阅集。

  在审阅集页面上显示指定范围内具有预测分数的文档列表。

有关更详细的说明，请参阅 [将预测筛选器应用于审阅集](predictive-coding-apply-prediction-filter.md)。

## <a name="step-4-perform-more-training-rounds"></a>步骤 4：执行更多培训轮

很可能，您必须执行更多培训轮，以对模块进行培训，以更好地预测审阅集内的相关和非相关项目。 一般情况下，你将对模型进行足够的训练，直到它稳定到足以满足你的要求。

有关详细信息，请参阅执行 [其他培训轮](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>步骤 5：应用最终预测分数筛选器，确定审阅的优先级

重复步骤 3 中的说明，将最终预测分数应用于审阅集，以在完成所有培训轮次并稳定模型后确定相关和非相关项目的审阅优先级。
