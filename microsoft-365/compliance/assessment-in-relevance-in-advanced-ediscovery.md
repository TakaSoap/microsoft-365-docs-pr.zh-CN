---
title: 了解评估中的相关性Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 大致了解评估阶段及其在相关性培训期间确定问题丰富的Microsoft 365 Advanced eDiscovery。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ec4f0c362ff403f45123bf837e82c5d2f6ed7e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189473"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>中相关性模块中的Advanced eDiscovery
  
Advanced eDiscovery启用早期评估，例如，针对已定义的问题和为案例导入的数据。 Advanced eDiscovery让专家做出有关已采用方法的决策，并应用这些决策到文档审阅项目。
  
## <a name="understanding-assessment"></a>了解评估

在评估中，专家审查至少 500 个随机文件集，这些文件用于确定问题的丰富程度并生成反映培训结果的统计信息。 如果发现有足够的相关文件达到统计级别，则评估将成功完成，该统计级别Advanced eDiscovery相关性，从而提供准确的统计信息并有效确定培训过程中的稳定点。 
  
评估集内的相关文件数量越高，稳定性算法的统计信息和有效性越准确。 评估文件中相关文件的数量取决于问题的丰富程度。 丰富度是集合中与问题相关的相关文件的估计百分比。 与具有较低丰富度的问题比，具有较高丰富度的问题将更快到达更多相关文件。 低丰富度 (例如，2% 或更低) 将需要一个非常大的评估集，以访问大量相关文件。
  
统计信息（在培训期间和批计算后显示在"跟踪"和"决定"选项卡中）包括不同审阅集的调用估计值。 在统计信息中，基于示例集 (在这种情况下，评估文件) 包括误差范围和该误差范围可信度。 例如，预计调用 80% 的误差可能为正负 5%，置信度为 95%。 这意味着估计的恢复率实际上为 75%-85%，并且此估计的置信度为 95%。 评估集越大，误差范围越小，统计信息越准确。 
  
专家审阅包含 500 个文件的初始评估集后，相关性可以确定调用值的当前误差范围。 相关性还将建议达到默认误差范围以优化评估集。 下面是一些示例：
  
- 如果评估集已产生加减 10% 的误差，相关性将建议继续培训 (无需额外评估) 。 

- 如果评估集产生正负 13% 的误差范围，相关性可能会建议查看另一组评估文件，以达到较小的边距。 

- 如果丰富度非常低，相关性可能会建议停止评估，即使误差范围较大 (则统计信息) 不切实际，因为达到有用误差范围所需的评估集过大。

每个问题都有自己的丰富内容、当前误差量以及估计的额外评估文件数。 下一个评估集根据单个评估集 (最多 1，000 个文件数创建) 。
  
您可以接受相关性建议或根据需要调整当前误差区。 确定错误的默认当前边距，以等于或高于 75% 的返回量。
  
> [!NOTE]
> 可以通过清除每个问题的"评估"复选框，然后清除"所有问题"，在展开的问题视图中的"相关性跟踪"选项卡中绕过评估阶段。 **\>** 因此，此问题将没有任何统计信息。 只有在 **执行评估** 之前，才能清除"评估"复选框。 如果一种情况下存在多个问题，则仅在清除每个问题的复选框时绕过评估。
