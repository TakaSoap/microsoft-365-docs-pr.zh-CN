---
title: 快速设置高级电子数据展示
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: 了解如何从安全与合规中心访问高级电子数据展示，并查看使用高级电子数据展示的典型工作流。
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936255"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>快速设置高级电子数据展示（经典）

> [!IMPORTANT]
> 当我们继续对较新版本的高级电子数据展示进行投资时，我们将宣布停用高级电子数据展示（也称为*高级电子数据展示（经典）* 或*高级电子数据展示 v1.0*）。 如果仍在使用高级电子数据展示 v1.0，请尽快切换到[高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。 高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。 若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。 

阅读本设置部分，Microsoft 365 安全与合规中心电子数据展示管理员可了解如何开始使用高级电子数据展示。 若要更好地理解本部分，需要对这两种工具都有一定的了解。
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>访问高级电子数据展示中的案件集

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
若要转到高级电子数据展示中的案件集，请执行以下操作： 
  
1. [转到安全与合规中心](go-to-the-securitycompliance-center.md)。 
    
2. 在安全与合规中心内，依次单击“搜索和调查”**** 和“电子数据展示”****，以显示组织中的案件集列表。 
    
3. 在“电子数据展示”**** 页上，单击要在高级电子数据展示中转到的案件集旁边的“打开”****。
    
4. 在此案件集的“**主页**”上，单击“**切换至高级电子数据展示**”。
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>工作流

下图展示了在安全与合规中心和高级电子数据展示中管理和使用电子数据展示案件集的常用工作流。
  
![图中显示了包含四个设置阶段的高级电子数据展示工作流，包括设置用户和案件集、标识案件集数据、导出和处理，然后是分析和导出到本地计算机这两个阶段。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>分析

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>相关性设置和相关性

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>导出

[导出案件集数据](export-case-data-in-advanced-ediscovery.md)：可导出高级电子数据展示内容和结果，以供外部审阅。 
  
## <a name="report"></a>报告

[生成报告](run-reports-in-advanced-ediscovery.md)：可生成与高级电子数据展示处理相关的选定报告。 
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[设置用户和案件集](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[准备数据](prepare-data-for-advanced-ediscovery.md)

