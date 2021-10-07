---
title: 跟踪数据中的相关性Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何查看和解释相关性培训状态和结果，了解 Advanced eDiscovery。
ms.openlocfilehash: 7a2786a727fd233b6617779bae95a26c1b62644e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175007"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>跟踪数据中的相关性Advanced eDiscovery
  
在Advanced eDiscovery中，"相关性跟踪"选项卡显示在"标记"选项卡中执行的相关性培训的计算有效性，并指示在相关性的迭代培训过程中要执行的下一步。 
  
## <a name="tracking-relevance-training-status"></a>跟踪相关性培训状态

1. 查看相关性跟踪中的以下详细信息，了解案例问题，如下面的问题名称 **对话框的以下示例** 所示。

   - **评估**：此进度指示器显示到此点执行的相关性培训在错误边距方面达到评估目标的程度。 还会显示相关性培训结果的丰富程度。

   - **培训**：此颜色编码的进度指示器和工具提示指示相关性培训结果稳定性，以及显示针对每个问题标记的相关性培训样本数量的数字刻度。 专家监视迭代相关性培训过程的进度。 
  
   - **批量计算**：此进度指示器提供有关批计算完成的信息。
  
   - **下一** 步：显示下一步执行的建议。 
  
    示例中显示了一个成功完成的问题评估，由已完成的颜色进度指示器和选中标记指示。 标记正在进行，但这种情况仍被视为不稳定 (稳定性状态也显示在工具提示) 。 下一步的建议是"培训"。 
  
    ![相关性跟踪培训步骤 1。](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    展开的视图显示其他信息和选项。 显示的当前误差区是当前评估状态中撤回的错误边距，因为现有评估 (标记) 文件。
  
    > [!NOTE]
    >  通过清除每个问题的"评估"复选框，然后清除"所有问题"，可以绕过评估阶段。 但是，因此，此问题将没有任何统计信息。 >执行 **评估前** ，才能清除"评估"复选框。 如果一种情况下存在多个问题，则仅在清除每个问题的复选框时绕过评估 
  
    当第一组示例文件未完成评估时，评估可能是标记更多文件的下一步。
  
    在 **相关性** \> **跟踪** 中，培训进度指示器和工具提示指示达到稳定性所需的额外样本的估计数量。 此估计提供了所需的其他培训的指南。
  
    ![相关性跟踪培训。](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. 完成标记后，如果需要继续培训，请单击"**培训"。** 另一个示例文件集是通过加载的文件集生成的，用于其他培训。 然后返回到"标记"选项卡，以标记和训练更多文件。

### <a name="reaching-stable-training-levels"></a>达到稳定的培训级别

在评估文件获得稳定级别的培训后，Advanced eDiscovery准备批量计算。
  
> [!NOTE]
> 通常，在三个稳定的培训示例之后，下一步是"批量计算"。 可能有例外情况，例如，在先前示例中对文件标记进行了更改或添加了种子文件时。 
  
### <a name="performing-batch-calculation"></a>执行批处理计算

当进度栏显示稳定培训状态、工具提示中的选中标记和稳定状态时，批计算将在成功完成 (后执行，作为下一步。) 批处理计算将相关性培训期间获得的知识应用于整个文件填充，以评估文件的相关性并分配相关性分数。
  
当存在多个问题时，将按问题进行批量计算。 在批计算过程中，在处理所有文件时将监视进度。 
  
此处建议的下一步是"无"，这表示此时无需其他迭代相关性培训。 下一个阶段是" **相关性决定 \> "** 选项卡。 
  
如果要在批量计算后导入新文件，管理员可以将导入的文件添加到新负载中。
  
> [!NOTE]
> 如果在批 **计算过程中** 单击"取消"，则进程将保存已执行的时间。 如果再次运行批处理计算，则该过程将继续从上次执行点开始。 
  
### <a name="assessing-tagging-consistency"></a>评估标记一致性

如果文件标记不一致，可能会影响分析。 当Advanced eDiscovery不理想或不确定一致性时，可以使用标记一致性过程。 返回可能标记不一致的文件的列表，并在必要时检查和重新标记这些文件。
  
> [!NOTE]
> 在评估后的七个或多个培训轮之后，可以在相关性跟踪问题详细结果培训进度中查看标记一 \>  \>  \>  \> **致性**。 每次针对一个问题完成此审阅。
  
1. 在 **"相关性 \> 跟踪"** 中，展开问题行。
  
2. 在"下一步 **"的右侧，单击**"修改 **"。**
  
3. 选择 **"标记不** 一致"作为"**下一步"** 选项，在七个培训示例后单击"确定 **"。**
  
4. 选择 **"标记不一致"。** The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.
  
5. 单击 **"计算** "提交更改。 标记不一致后的下一步是"培训"。 
  
## <a name="viewing-and-using-relevance-results"></a>查看和使用相关性结果

在"**相关性 \> 跟踪"** 选项卡中，展开问题行，然后单击"详细结果 **"旁边的**"查看 **"。** 将显示"详细结果"窗格，如下所示并如下所述。
  
![相关性培训详细结果。](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>标记摘要

 在下面的示例中，标记摘要显示每个评估、培训和跟进文件标记过程的总计。
  
![相关性跟踪标记摘要。](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>关键字

关键字是文件中唯一的字符串、字词、短语或字词序列，Advanced eDiscovery标识为文件是否相关的重要指标。 "包含"列列出标记为"相关"的文件的关键字和权重，"排除"列列出了标记为"不相关"的文件中关键字和权重。
  
Advanced eDiscovery负值或正关键字权重值。 权重越高，在批计算过程中为关键字出现的文件分配的相关性分数越高。
  
关键字Advanced eDiscovery列表可用于补充由专家构建的列表，或作为文件审阅过程中任何时间点的间接性检查。
  
### <a name="training-progress"></a>培训进度

" **培训进度** "窗格包括培训进度图和质量指示器显示，如下面的示例所示。
  
![相关性跟踪培训进度。](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**培训质量指示器**：显示标记一致性的分级，如下所示：
  
- **良好**：文件一致标记。  (绿色) 
  
- **中**：某些文件标记不一致。  (黄色) 

- **警告**：许多文件标记不一致。  (红色) 

**培训进度图**：显示与 F 度量值比较的许多相关性培训周期后相关性培训稳定性的程度。 随着我们在整个图中从左向右移动，置信区间将缩小，并随 F 度量一起通过 Advanced eDiscovery Relevance 用于确定相关性培训结果优化时的稳定性。
  
> [!NOTE]
> 相关性使用 F2，这是 F 度量指标，其中 Recall 接收的权重是 Precision 的两倍。 对于高丰富度 (超过 25%) ，相关性使用 F1 (1：1 比率) 。 F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.
  
### <a name="batch-calculation-results"></a>批处理计算结果

" **批处理计算结果** "窗格包括按相关性分数的文件数，如下所示： 
  
- **Success**
  
- **空**：不包含文本，例如，仅包含空格/制表符
  
- **失败**：由于过大或无法读取
  
- **已** 忽略：由于尺寸过大
  
- **Neb一**：包含无意义的文本或没有与该问题相关的功能
  
> [!NOTE]
> Empty、Failed、Ignored 或 Neb一起会收到相关性分数 -1。
  
### <a name="training-statistics"></a>培训统计信息

The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training. 
  
![相关性跟踪培训统计信息。](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
此视图显示以下内容：
  
- **Review-recall ratio**： Comparison of results according to Relevance scores in a hypothetically linear review. 根据审阅集大小集，估计回收时间。
  
- **参数**：与审阅集相关的累积计算统计信息（相对于整个案例的文件填充）。
  
- **查看**：要基于此截止时间查看的文件百分比。
  
- **恢复**：审阅集内相关文件的百分比。 
  
- **按相关性分数分布**：左侧显示深灰色的文件低于截止分数。 工具提示显示相关性分数和审阅文件集内文件相对于总文件的相关百分比。
