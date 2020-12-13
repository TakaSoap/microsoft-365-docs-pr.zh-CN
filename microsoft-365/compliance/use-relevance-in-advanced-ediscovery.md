---
title: 使用高级电子数据展示中的相关性模块
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 了解高级电子数据展示中的相关性模块，包括用于培训和文件审阅的工作流和指南和步骤。
ms.openlocfilehash: 0319ac378fb891d96437f53931213429b111d61d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663281"
---
# <a name="use-the-relevance-module-in-advanced-ediscovery-classic"></a>在高级电子数据展示和经典电子数据展示 (相关) 

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中，相关性模块包括相关性培训和与案例相关的文件审阅。 显示并描述相关性工作流，如下所示：
  
![相关性工作流](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **评估和跟踪周期**：
    
  - **评估**：高级电子数据展示支持基于随机文件样本的早期评估，并使用此评估应用决策以确定预测编码过程的性能。 
    
  - **Track**： Advanced eDiscovery calculates and displays interim results of the assessment while monitoring 统计 valid of the process. 
    
- **培训和跟踪周期**：
    
  - **Tag**： Advanced eDiscovery learn Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.
    
  - **Track**： Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring 统计 valid of the process. 
    
- **批量计算**：高级电子数据展示采用累积和学习的相关性条件，应用于整个文件集合，并生成每个文件的相关性分数。
    
- **决定**：高级电子数据展示在批计算后显示应用于整个案例的分析结果，并显示用于做出文档审阅决策的数据。
    
- **测试**：可以测试高级电子数据展示结果，以验证高级电子数据展示处理的有效性和有效性。
    
## <a name="guidelines-for-relevance-training-and-review"></a>相关性培训和审阅指南

以下是相关性培训和审阅指南的概述：
  
- **错误和不一** 致：如果在培训期间出现标记错误，请返回到以前的文件示例进行更正。 如果错误太多需要更正，或者有新的案例或问题角度，则管理员应重新定义相关性条件，并重新启动相关性培训。
    
- **标记和培训**： 
    
  - 文件应仅基于内容进行标记。 不考虑元数据，如保管人、日期或文件路径。 
    
  - 标记文件时，不考虑文本中的日期范围指示。
    
  - 标记文件时，不考虑嵌入的图形图像。
    
  - 如果在标记时使用 **格式化的文本视图** 图标查看文件，则不考虑文本的格式。 例如，相关性仍将带删除线 (一条水平线在其中心) 表示删除的单词仍被视为所分析文本的一部分。 
    
  - 忽略应用于相关性 (由案例管理器或管理员设置) 将在相关性的文本视图中显示的文件内容中删除。 如果在相关性培训启动后定义了 Ignore 文本的值，则新的忽略文本将应用于从定义该文本的位置创建的示例文件。 应谨慎使用"忽略文本"功能，因为该功能的使用可能会降低文件分析的性能
    
  - 仅在必要时 **使用"跳过标记** "选项。 高级电子数据展示不会基于跳过的文件进行训练。 在评估中，如果很难判断文件是否相关，最好尽可能标记为相关 (R) 或不相关的 (NR) ，而不是选择"跳过 **"。** 当高级电子数据展示评估培训时，可以看到这些类型的文件的处理情况。
    
  - 即使提取的文本非常少的文件也应在培训中标记为 R/NR，而不是"跳过"（如果可能）。 
    
  - 只要文件可读且可标记为 R/NR，标记就可以影响分类器。
    
  - "标记"选项卡上显示的示例文件列表上的文件序列号允许用户返回到文件的原始显示顺序。 
    
  - 你可以返回任何示例并更改评估和培训集文件的标记。 创建下一个示例时将应用更改。
    
  - 标记文件时，应该将 PDF 格式的扫描的 Excel 文件视为与本机 Excel 文件相同。
    
  - 如果对文件的相关性标记有疑问，请咨询专家。 相关性培训期间不正确的标记可能导致此过程稍后丢失时间，并且也可能对总体结果的质量产生负面影响。
    
  - 关键字列表中定义的关键字将按颜色显示，以帮助用户在标记时标识相关文件。
    
- **批量计算**：专家标记为 R/NR 的文件将收到 0 或 100 的分数。 这适用于在批计算之前进行标记。 如果专家在批计算后将问题切换为"空闲"并继续标记此问题，则新标记的分数不是 100/0，而是原始分数。
    
- 问题和采样模式：问题通常在工作完成后关闭 (相关性培训稳定下来，) 、取消问题时或其他用户正在解决问题时执行批计算。
    
## <a name="steps-in-relevance-training"></a>相关性培训的步骤

在 **"相关性 \> 跟踪** "选项卡中，高级电子数据展示提供了有关如何处理的建议，并提供了以下步骤。 在相关性培训过程中建议执行以下步骤时，将在下面介绍这些含义。 
  
- 标记/继续标记：由专家针对示例中每个文件和问题执行的文件审阅和相关性标记。
    
  - 含义：需要标记现有示例。
    
- 评估/继续评估：支持对案例问题相关性进行早期验证，并初步了解为当前案例导入的文件总体的相关性。
    
  - 含义：需要或建议进行更多评估。
    
- 培训/继续培训：高级电子数据展示从标记文件示例的专家学习并获取识别与每个案例上下文中每个问题相关的相关性标准的能力的过程。
    
  - 含义：问题需要更多培训;应创建并标记下一个示例。 
    
- 批量计算：高级电子数据展示在培训阶段获取的知识并应用于整个文件填充的相关性过程。 相关文件组内的所有文件都针对相关性进行评估，并分配有相关性分数。
    
  - 含义：问题已稳定，可以执行批计算。
    
- Up-up： Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Load scenario.
    
  - 含义：已添加新负载，需要进行跟进才能继续工作。
    
- 标记不一致：进程通过高级电子数据展示算法识别文件标记过程中可能对分析产生负面影响的不一致情况。
    
  - 含义：下一个示例将包括之前示例中已标记的文件，并且必须重新标记它们。
    
- 更新分类器：允许用户应用标记或种子设定更改。
    
  - 含义：无需手动运行另一个相关性示例即可应用标记和种子设定更改。
    
- 保留：相关性培训过程已完成。
    
  - 含义：此时不需要相关性培训。
    
虽然高级电子数据展示可指导你完成此过程，但建议在不同阶段执行下一步，它还允许你在选项卡和页面之间导航，并做出选择以解决可能与单个案例、问题或文档审阅过程相关的情况。 
  
可以接受或替代高级电子数据展示下一步处理选项。 如果要执行建议下一步外的步骤，请单击对话框中展开的问题显示中列出的下一步，单击下一步旁边的"修改"按钮，然后选择另一个"下一步"选项。 
  
> [!NOTE]
> 某些选项在解锁后可能仍处于禁用状态，因为此时不支持在过程中使用这些选项。 
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[了解相关性评估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标记和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[根据结果决定](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

