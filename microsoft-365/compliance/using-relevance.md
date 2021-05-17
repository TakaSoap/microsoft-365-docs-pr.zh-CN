---
title: 使用相关性模块分析数据Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解相关性模块如何分析证据数据，并说明相关性工作流以及 Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286058"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>使用相关性模块分析数据Advanced eDiscovery

在Advanced eDiscovery中，相关性模块包括与案例相关的文件的相关性培训和审阅。 若要使用相关性工作流，请转到管理审阅集内的审阅集，然后单击"显示相关性"。 在启动工作流之前，需要完成几个步骤：

- 进程：添加到审阅集的每个负载集在此处将显示为"容器"。 需要先处理这些文档，然后才能将它们添加到相关性模块;您也可以在这里将它们标记为针对特定问题的种子或预标记。

- 添加到相关性：在"相关性加载"下，可以添加已处理到相关性的文档 \> ，使其可用于培训。

相关性工作流的显示和描述如下：
  
![相关性工作流](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **评估和跟踪周期**：
    
  - **评估**：启用基于随机文件样本的早期评估，并使用此评估应用决策来确定预测编码过程的性能。 
    
  - **跟踪**：在监视过程的统计有效性时计算并显示评估的临时结果。 
    
- **培训和跟踪周期**
    
  - **Tag**：Advanced eDiscovery根据专家的迭代审阅和单个文件标记来了解特定于每个问题的相关性条件。
    
  - **跟踪**：计算并显示相关性培训的临时结果，同时监视过程的统计有效性。 
    
- **批量计算**：累积和学习的相关性条件将应用于整个文件集合，并针对每个文件生成相关性分数。
    
- **决定**：应用于整个案例的分析结果在批计算后显示，并且用于做出文档审阅决策的数据也显示。
    
- **测试**：可以测试结果，以验证处理过程的有效性Advanced eDiscovery有效性。

- **搜索**：相关性工作流完成后，在审阅集内运行查询时，可以使用针对问题的文档的读取百分点值等输出。
    
## <a name="guidelines-for-relevance-training-and-review"></a>相关性培训和审阅指南

以下是相关性培训和审阅指南的概述：
  
- **错误和不一致**：如果在培训期间出现标记错误，请返回到以前的文件示例以更正错误。 如果错误太多需要更正，或者有新的案例或问题视角，则管理员应重新定义相关性条件，并重新启动相关性培训。
    
- **标记和培训**： 
    
  - 文件应仅基于内容进行标记。 不考虑元数据，如保管人、日期或文件路径。 
    
  - 标记文件时，不考虑文本中的日期范围指示。
    
  - 标记文件时，不考虑嵌入的图形图像。
     
  - 忽略应用于相关性的文本将在"相关性"的文本视图中的显示文件内容中删除。 如果 Ignore 文本的值是在相关性培训启动之后定义的，则新的忽略文本将应用于从定义该文本的位置创建的示例文件。 应谨慎使用"忽略文本"功能，因为该功能的使用可能会降低文件分析的性能
    
  - 仅在必要时 **使用"** 跳过标记"选项。 Advanced eDiscovery未基于跳过的文件进行训练。 在评估中，如果很难判断文件是否相关，最好尽可能标记为"相关 (R) "或"不相关的 (NR) "，而不是选择"跳过 **"。** 当Advanced eDiscovery评估培训时，可以看到这些类型的文件的处理情况。
    
  - 即使具有非常少量的提取文本的文件也应在培训中标记为 R/NR，而不是"跳过"（如果可能）。 
    
  - 只要文件可读且可标记为 R/NR，标记就可能会影响分类器。
    
  - The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files. 
    
  - 你可以返回任何示例并更改评估和培训集文件的标记。 这些更改将在创建下一个示例时应用。
    
  - 在Excel文件时，应处理 PDF 格式Excel扫描的文件。
    
  - 如果对文件的相关性标记有疑问，请咨询专家。 相关性培训期间不正确的标记可能导致稍后在过程中丢失时间，并且也可能对总体结果的质量产生负面影响。
    
  - 关键字列表中定义的关键字将显示为颜色，以帮助用户在标记时标识相关文件。
    
- **批量计算**：由专家标记为 R/NR 的文件将获得 0 或 100 的分数。 这适用于在批计算之前进行标记。 如果专家在批计算后将问题切换为 Idle，然后继续标记此问题，则新标记的分数将不会是 100/0，而是原始分数。
    
- 问题和采样模式：问题通常在解决问题时关闭 (相关性培训稳定下来，在问题被取消时或其他用户正在解决问题时执行) 批处理计算。
    
## <a name="steps-in-relevance-training"></a>相关性培训中的步骤

在 **"相关性跟踪 \>**"选项卡Advanced eDiscovery，通过执行下列步骤，可提供有关如何处理的建议。 当在相关性培训过程中建议执行以下步骤时，将在下面介绍这些含义。 
  
- 标记/继续标记：由专家对样本中每个文件和问题执行的文件审阅和相关性标记。
    
  - 含义：需要标记现有示例。
    
- 评估/继续评估：允许对案例问题相关性进行早期验证，并初步查看为当前案例导入的文件总体的相关性。
    
  - 含义：需要或建议进行更多评估。
    
- 培训/继续培训：此过程Advanced eDiscovery向标记文件示例的专家学习，并能够识别与每个案例上下文中每个问题相关的相关性标准。
    
  - 含义：问题需要更多培训;应创建并标记下一个示例。 
    
- 批量计算：相关性过程Advanced eDiscovery在培训阶段获取的知识，并应用于整个文件填充。 相关文件组内的所有文件都进行了相关性评估，并分配了相关性分数。
    
  - 含义：问题已稳定，可以执行批量计算。
    
- 跟进：相关性指示专家何时在滚动加载方案期间审阅和标记从其他文件负载选择的文件示例。
    
  - 含义：已添加一个新负载，需要 Catch-up 才能继续工作。
    
- 标记不一致：进程Advanced eDiscovery算法识别文件标记过程中可能对分析造成负面影响的不一致情况。
    
  - 含义：下一个示例将包括之前示例中已标记的文件，并且必须恢复其标记。
    
- 更新分类器：允许用户应用标记或种子设定更改。
    
  - 含义：无需手动运行另一个相关性示例即可应用标记和种子设定更改。
    
- 保留：相关性培训过程已完成。
    
  - 含义：此时不需要相关性培训。
    
尽管Advanced eDiscovery指导您完成此过程，并指导您在不同阶段执行建议的"下一步"步骤，但它还允许您在选项卡和页面之间导航，并做出选择以解决可能与单个案例、问题或文档审阅过程相关的情况。 
  
可以接受或替代下一Advanced eDiscovery处理选项。 如果要执行建议的"下一步"步骤外的其他步骤，请单击对话框中展开的问题显示中列出的"下一步"，单击"下一步"旁边的"修改"按钮，然后选择另一个"下一步"选项。 
  
> [!NOTE]
> 某些选项在解锁后可能保持禁用状态，因为此时不支持在过程中使用这些选项。 
  
## <a name="more-information"></a>详细信息

[了解相关性评估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标记和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[根据结果决定](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

[查询审阅集中的数据](review-set-search.md)
