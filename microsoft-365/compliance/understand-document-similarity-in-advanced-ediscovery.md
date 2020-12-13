---
title: 了解高级电子数据展示中的文档相似性
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 查看文档相似性值（两个文件的相似性最低级别）在高级电子数据展示中的工作方式。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22eb27e7afdc6ad37ea6fdcba9b64298906f1c35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663311"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a>了解高级电子数据展示和经典 (中的文档) 

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中，文档相似性是将两个文档视为接近重复项所需的最低相似性级别。
  
> [!TIP]
> 对于大多数业务应用程序，建议使用 60%-75% 的相似性值。 对于 OCR (质量极差的光学字符识别) ，可以应用较低的相似性值。 
  
> [!NOTE]
> 设置并运行给定案例后，不能更改相似性值。 
  
在"近 (ND) 集内，可能有相似级别低于相似性阈值的文档。 对于要联接 ND 集的文档，ND 集合中必须至少有一个类似级别超过相似性的文档。 
  
例如，假定相似性设置为 80%，文档 F1 在 85% 级别类似于文档 F2，文档 F2 与文档 F3 的级别 90% 相似。 
  
但是，文档 F1 可能类似于文档 F3，其级别仅为 70%，低于阈值。 尽管如此，在此例中，文档 F1、F2 和 F3 都显示在一个 ND 集合中。 同样，使用 80% 的相似性值，我们可能创建了两个集，EquiSet-1 和 EquiSet-2。 EquiSet-1 包含文档 E1 和 E2。 Equiset-2 包含文档 F1、F2 和 F3。 
  
类似级别如下所述：
  
![文档相似性](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
假定现在插入了另一个文档 X1。 X1 和 E3 之间的相似度为 87%。 同样，X1 和 F1 之间的相似性为 92%。 因此，EquiSet -1、EquiSet -2 和 X1 现在组合到一个 ND 集。
  
![文档相似性](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 如果将任何两个文档分配给一个 ND 集，它们仍将一起保留在相同的 ND 集合中，即使向该集合中添加了其他文档或合并了这些文档集。 
  
合并集后，当向集合中添加新文档时，数据透视文档可能会更改。 
  
## <a name="related-topics"></a>相关主题

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置 分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

