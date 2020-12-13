---
title: 在高级电子数据展示中运行进程模块
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 了解准备数据案例文件以使用高级电子数据展示进行分析的准则。
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662807"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>在经典电子数据展示高级电子数据展示 (进程) 

在准备过程中，将案例文件加载到高级 **电子数据** \> **展示中**。 
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>指南：为高级电子数据展示准备数据

- **质量**：清楚地标识与案例相关的案例文件总体。
    
- **Load**： Load the files into a location that is accessible accessiblediscovery.
    
- **文件 ID：** 高级电子数据展示中的唯一文件标识符。 如果未导入任何文件标识符，则高级电子数据展示将自动生成 ID。 如果在后续进程加载中映射 ID，并映射与初始进程加载不同的路径，则高级电子数据展示将替换路径 (，而不是在) 。 ID 可在导出过程中用作引用。 ID 值不应为"-1"。
    
- **MD5：** 此签名用于区分两 (文件不被视为完全相同的重复项，除非它们具有相同的 MD5) 。 默认情况下，高级电子数据展示计算文件的 MD5。 当加载的文件是文本文件时，建议加载和映射原始 MD5 值，而不是在高级电子数据展示中计算该值。
    
- **文件类型和名称**：
    
  - 高级电子数据展示可以处理各种格式的文件，将加载的本机文件提取为标准格式，例如 \* 。TXT、HTML 或 。XML。 文本文件的处理速度比本机文件快。 提取的文本文件存储在 case 文件夹中。
    
  - 不要加载无法提取的文件，如系统文件或图形图像。 这些文件可能会延迟处理。
    
  - 验证文件名的命名和路径是否正确。
    
- **文件路径**：高级电子数据展示可以加载路径长度最多为 400 个字符的文件。
    
- 文本提取：从本机文件提取文本时，除了正常文本之外，还会提取以下内容：隐藏文本 (Excel 和 .doc) 、隐藏列 (Excel) 、跟踪更改 (.doc) 、扬声器备注 (.ppt) 、嵌入对象 (例如，.ppt) 中的 Excel 对象。 可以在文本编辑器中查看这些文本。
    
- **忽略文本**：此可选功能在进程运行后和分析之前定义。 应谨慎使用忽略文本，因为它的使用可能会降低文件分析的性能。
    
- **多语言文本**：高级电子数据展示当前不处理标记、保管人和问题的多语言名称。
    
- **元数据**：确定是否有要保存在案例数据库中供将来参考的元数据，例如日期范围、文件大小、文件类型、保管人和主题。 可以在加载文件后加载元数据，而无需重新运行清单或增加重新处理开销。 
    
  - 如果文件最初是按路径加载的，则稍后导入元数据时映射路径列。 可以按 ID 引用文件并映射其他路径。 当文件路径更改时，这是一个有用的方案。
    
  - 如果文件最初由文件 ID 加载，则加载元数据时映射 ID 列。 按路径引用文件 (而不是 ID) 将导致使用其他 ID 重新加载文件。 高级电子数据展示会创建文件的副本，而不是加载现有文件的元数据。
    
- **家庭**：没有其父级或家庭 (无法加载) 。 
    
- **文件大小**：对加载到高级电子数据展示的文件的大小没有限制。 对于分析 (分析、相关性等) ，提取的文本限制为 5，242，880 个字符。 较大的文件 (例如，在相关性中，文件不参与相关性培训过程，在批计算后不会获得相关性分数) 。
    
- **文件数量**：在单个情况下可以处理的文件数量没有建议的限制。 性能取决于系统资源。 
    
## <a name="filtering-files"></a>筛选文件

用户定义的标签可以与一组文件相关联，以将其从进程或其他任务中排除。 每个进程会话都与一个批处理 ID 相关联。 虽然批量 ID 对相关性专家不可见，但可通过为当前批处理添加筛选器，并标记所有具有用户定义标签的适当文件，使用搜索实用工具完成此操作。 
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[运行进程模块并加载数据](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[查看进程模块结果](view-process-module-results-in-advanced-ediscovery.md)

