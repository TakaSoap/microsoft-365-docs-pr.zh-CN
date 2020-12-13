---
title: 准备高级电子数据展示的数据
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: 了解如何使用安全合规 &amp; 中心准备数据以使用高级电子数据展示进行分析。
ms.openlocfilehash: 43253a3908925bc188568f020f48c62a94552403
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662877"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>为高级电子数据展示和经典 (数据) 

本主题介绍如何将内容搜索的结果加载到高级电子数据展示或经典 (中) 。 
  
> [!IMPORTANT]
> 当我们继续对较新版本的高级电子数据展示进行投资时，我们将宣布停用高级电子数据展示（也称为 *高级电子数据展示（经典）* 或 *高级电子数据展示 v1.0*）。 如果仍在使用高级电子数据展示 v1.0，请尽快切换到 [高级电子数据展示 v2.0](overview-ediscovery-20.md)（也称为 *Microsoft 365 中的高级电子数据展示解决方案*）。 高级电子数据展示 2.0 不仅包含高级电子数据展示 v1.0 中提供的类似功能，还提供了许多新功能，如保管人管理、沟通管理和审阅集。 若要了解停用高级电子数据展示 v1.0 的详细信息，请参阅[停用旧式电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>步骤 1：为高级电子数据展示准备数据

若要使用高级电子数据展示分析数据，可以使用在 Microsoft 365 安全合规中心 (中运行的内容搜索的结果，或者使用 &amp; Microsoft 365 安全合规中心) 中与电子数据展示案例 (相关的搜索，该搜索列在安全合规中心 &amp;  &amp;) 中的电子数据展示页面上。 
  
有关准备搜索结果以在高级电子数据展示中进行分析的详细步骤，请参阅"为高级电子数据展示准备[搜索结果"。](prepare-search-results-for-advanced-ediscovery.md)
  
> [!NOTE]
> 如果你有 Microsoft 365 之外的数据，并且想要将其导入到 Microsoft 365，以便可以在高级电子数据展示中准备和分析它，请参阅将 PST 文件导入[到 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)和存档第三方数据的[概述。](https://www.microsoft.com/?ref=go) 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>步骤 2：在高级电子数据展示中将搜索结果数据加载到案例

在安全合规中心准备搜索结果进行分析后，下一步是在高级电子数据展示中将搜索结果加载到 &amp; 案例。 有关详细信息，请参阅" [运行进程"模块](run-the-process-module-in-advanced-ediscovery.md)。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用工作或学校帐户进行登录。
    
3. 在安全与合规中心内，依次单击“搜索和调查”和“电子数据展示”，以显示组织中的案件集列表。 
    
4. 单击 **要** 将数据加载到高级电子数据展示中的情况旁边的"打开"。 
    
5. 在此案件集的“**主页**”上，单击“**切换至高级电子数据展示**”。 
    
    ![单击"切换到高级电子数据展示"以在高级电子数据展示中打开案例](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    将显示 **"连接到高级电子数据展示** "进度栏。 连接到高级电子数据展示时，将在该案例的设置页上显示容器列表。 
    
    ![案例显示在高级电子数据展示中](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     这些容器表示您准备在步骤 1 中的高级电子数据展示中进行分析的搜索结果。 请注意，在安全合规中心中，容器的名称与内容搜索 &amp; 的名称相同。 列表中的容器是准备的容器。 如果其他用户为高级电子数据展示准备搜索结果，对应的容器将不会包含在列表中。 
    
6. 若要将容器中的搜索结果数据加载到高级电子数据展示的案例中，请选择一个容器，然后单击"处理 **"。**
    
将安全合规中心的搜索结果添加到高级电子数据展示中的情况后，下一步是使用高级电子数据展示中的工具分析和剔除与案例相关的 &amp; 数据。 
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[设置用户和事例](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[分析事例数据](analyze-case-data-with-advanced-ediscovery.md)
  
[管理相关性设置](manage-relevance-setup-in-advanced-ediscovery.md)
  
[使用相关性模块](use-relevance-in-advanced-ediscovery.md)
  
[导出事例数据](export-case-data-in-advanced-ediscovery.md)

