---
title: 查看高级电子数据展示中的分析结果
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 了解在何处查看高级电子数据展示中分析过程的结果，包括显示的任务选项的定义。
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663252"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a>View Analyze results in Advanced eDiscovery (classic) 

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中，可在各种显示器中查看分析过程的进度和结果，如下所述。
  
## <a name="view-analyze-task-status"></a>查看"分析任务状态"

在 **" \> 准备 \> 分析结果 \> 任务"状态** 中，状态在分析进程执行期间和之后显示。 
  
![分析任务状态](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
显示的任务可能因所选选项而异。 
  
- **ND/ET： setup：** Prepares for the run， for example， sets run and case parameters.
    
- **ND/ET：ND 计算**：处理文件的几乎重复分析。
    
- **ND/ET：ET 计算**：对整个电子邮件集执行电子邮件线程分析。
    
- **ND/ET：透视和相似性**：执行透视和文件相似性处理。
    
- **ND/ET：元数据更新**：完成对数据库中的文件收集的新数据。
    
- **主题：主题计算**：运行主题分析。  (选中时显示) 
    
- **任务状态**：此行在任务完成之后显示。 任务正在运行时，将显示运行持续时间。
    
> [!NOTE]
> ND 和 ED (的") "结果适用于要处理的文档数。 它不包含完全相同的文件。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>查看"近重复项"和"电子邮件线程"状态

目标 **总体** 结果显示目标总体中的文档、电子邮件、附件和错误数。 
  
" **文档** "结果显示透视表的数量、唯一的近重复项和确切的重复文件。 
  
" **电子邮件"** 结果显示非独占、非独占减号、唯一非独占副本数以及电子邮件的其余部分数。 不同类型的电子邮件结果包括： 
  
- **非** 独占：非独占电子邮件是电子邮件线程中的终止节点，包含该线程之前的所有历史记录。 因此，审阅者可以安全地关注非独占电子邮件，而无需阅读线程中的之前邮件。 
    
- **非独占减**：如果包含邮件的父邮件有一个或多个不同的附件，则非独占电子邮件被指定为非独占邮件减号。 在此上下文中，术语 Parent 用于位于电子邮件线程上向上的邮件或该特定非独占电子邮件中包含的对话。 审阅者可以使用非独占减号指示作为一个信号，指示尽管可能不需要查看非独占电子邮件父项的内容，但查看与非独占路径父项关联的附件可能很有用。 
    
- **非独占副本**：如果包含电子邮件是标记为非独占或非独占减号的另一封邮件的副本，则非独占电子邮件被指定为非独占副本。 换句话说，此消息的主题和正文与另一个包含邮件的主题和正文相同，因此，共同驻留在同一节点中。 由于非独占副本邮件包含相同的内容，因此通常可以在审阅过程中跳过这些内容。 
    
- **其余** 部分：这表示不包含任何唯一内容的电子邮件，因此不会属于前三个类别的任何类别。 无需查看这些电子邮件。 如果邮件包含的附件不在以后包含的电子邮件中，可能需要查看附件。 这由主题中是否存在非独占减号电子邮件表示。
    
附件 **结果** 根据唯一和重复的类型显示附件数。 
  
![近似重复和电子邮件线程](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置 分析高级设置](view-analyze-results-in-advanced-ediscovery.md)

