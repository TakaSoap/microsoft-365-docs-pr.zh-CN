---
title: 在 Advanced eDiscovery
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
description: 了解如何在 Advanced eDiscovery 中创建预测编码Advanced eDiscovery。 这是使用 Advanced eDiscovery 中的机器学习功能来帮助你在审阅集内标识相关和非相关内容的第一步。
ms.openlocfilehash: 4366c5779aaca6973f5a2c0cc526086d0742d069
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170579"
---
# <a name="create-a-predictive-coding-model-preview"></a>创建预测编码模型 (预览) 

在模型中使用预测编码的机器学习功能的第一Advanced eDiscovery是创建预测编码模型。 创建模型后，可以训练它确定审阅集内的相关和非相关内容。

若要查看预测编码工作流，请参阅[了解预测编码Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-create-a-model"></a>创建模型之前

- 审阅集至少必须有 2，000 个项目，以创建预测编码模型。

- 创建模型之前，请务必将所有集合提交到审阅集。 创建模型后添加到审阅集的项目将不会得到处理，并且不会分配模型生成的预测分数。

- 模型将不会处理评论集内任何不包含文本的项目，或为其分配预测分数。 包含文本的项目将包含在控件集或培训集内。

## <a name="create-a-model"></a>创建模型

1. In the Microsoft 365 合规中心， open an Advanced eDiscovery case and then select the **Review sets** tab.

2. 打开审阅集，然后单击分析 **管理** 预测  >  **编码 (预览) 。**

   ![单击审阅集的"分析"下拉菜单以转到预测编码页面。](..\media\ManagePredictiveCoding.png)

3. 在"**预测编码模型 (预览) ，** 单击"新建 **模型"。**

4. 在飞出页面上，键入模型名称和可选说明。

5. （可选）您可以通过单击 (页面上的"高级选项"来配置高级设置) 与置信水平和误差边距相关。 这些设置会影响控件集中包含的项目数。 该 *控件集* 在培训过程中用于评估模型分配给具有你在培训轮中执行的标签的项目预测分数。 如果您的组织具有有关文档审阅可信度和误差线的准则，请在适当框中指定这些准则。 否则，请使用默认设置。

6. 单击 **"保存** "创建模型。

   系统需要几分钟的时间准备模型。 准备就绪后，你可以执行第一轮培训。

## <a name="what-happens-after-you-create-a-model"></a>创建模型后会发生什么情况

创建模型后，创建和准备模型期间将在后台执行下列操作：

- 系统计算控件集的项数。 此大小基于审阅集的项目数以及置信水平和误差范围设置。 控件集的项是随机选择的，并指定为控件集项。 系统包括第一轮培训中设置的控件中的 10 个项目。

- 系统随机从评价集选择 40 个项目，以包含在第一轮培训的培训集内。 因此，第一轮培训包括用于标记的 50 个项目：来自培训集的 40 个项目和控件集的 10 个项目。

## <a name="next-steps"></a>后续步骤

为审阅集创建模型后，下一步是执行培训轮以"教学"模型，以确定与调查相关的内容。 有关详细信息，请参阅 [训练预测编码模型](predictive-coding-train-model.md)。
