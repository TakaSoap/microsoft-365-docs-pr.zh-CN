---
title: Office 365 高级电子数据展示
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: 了解 Office 365 高级电子数据展示如何帮助您分析 Office 365 中的数据、优化文档审阅，并做出高效电子数据展示的决策。
ms.openlocfilehash: 8af18c49511373dfa53fdb515f37dce37ef35150
ms.sourcegitcommit: 31392b9599f4b4e9981a1278d6beb9f0a2839ecf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2019
ms.locfileid: "38685040"
---
# <a name="office-365-advanced-ediscovery"></a>Office 365 高级电子数据展示

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
使用高级电子数据展示，可以更好地了解 Office 365 数据并减少电子数据展示成本。 高级电子数据展示可帮助您分析 Office 365 中的非结构化数据，执行更高效的文档审阅，并做出决定，以减少电子数据展示的数据。 您可以使用存储在 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Office 365 组和 Microsoft 团队中的数据。 您可以在 "安全与合规中心" 中执行电子数据展示搜索，以搜索组、单个邮箱和网站中的内容，然后使用高级电子数据展示分析搜索结果。 当您准备高级电子数据展示中的分析搜索结果时，光学字符识别允许从图像中提取文本。 此功能允许将高级电子数据展示的强大文本分析功能应用于图像文件。
  
高级电子数据展示通过使用接近重复检测和电子邮件线索分析等功能识别冗余信息，优化并加快了文档审阅过程。 相关性功能适用于确定相关文档的可预测编码技术。 高级电子数据展示根据示例文档的标记决定，并应用统计和自我学习技术来计算数据集中每个文档的相关性。 这样，您就可以将重点放在关键文档上，并根据案例策略快速做出明智的决策，并挑选数据，并确定优先级。
  
 **为什么要进行高级电子数据展示？** Office 365 高级电子数据展示构建在 Office 365 中的一组现有电子数据展示功能之上。 例如，可以使用 Office 365 安全&amp;合规中心中的搜索功能来对组织中的所有内容源执行初始搜索，以确定和收集可能与特定法律案例相关的数据。 然后，您可以通过应用高级电子数据展示的文本分析、机器学习和相关性/预测编码功能来对该数据进行分析。 这可帮助您的组织快速处理数以千计的电子邮件、文档和其他类型的数据，以查找最可能与特定事例相关的那些项目。 然后，可以将缩减的数据集导出到 Office 365 中，以供进一步查看。 
  
## <a name="get-started"></a>入门

开始使用高级电子数据展示的最快方法是创建一个案例并在安全 & 合规性中心中准备搜索结果，在高级电子数据展示中加载这些结果，然后运行快速分析以分析该事例数据，然后将结果导出到外部审阅。
  
- 获取高级电子数据展示工作流的[快速概述](quick-setup-for-advanced-ediscovery.md) 
    
- 通过创建案例、分配电子数据展示权限和添加事例成员来设置高级电子数据展示的[用户和案例](set-up-users-and-cases-in-advanced-ediscovery.md)，具体方法是使用安全 & 合规性中心 
    
- 在高级电子数据展示中为事例[准备和加载搜索数据](prepare-data-for-advanced-ediscovery.md) 
    
- 将[非 Office 365 数据加载](import-non-office-365-data-into-advanced-ediscovery.md)到事例中，以在高级电子数据展示中对其进行分析 
    
- [使用快速分析](use-express-analysis-in-advanced-ediscovery.md)在案例中快速分析数据，然后轻松导出结果 
    
## <a name="analyze-data"></a>分析数据

在高级电子数据展示中，将搜索数据加载到事例中之后，您将使用分析模块开始对其进行分析。 分析过程的第一部分包括将文件组织成一组唯一的文件、重复项和临近的重复项（也称为 "文档相似性"）。 然后，将数据再次组织为电子邮件线程和主题的分层结构化组，并根据需要设置 "忽略文本" 筛选器以从分析中排除特定文本。 然后，运行分析并查看结果。
  
- 了解用于准备在高级电子数据展示中分析数据的[文档相似性](understand-document-similarity-in-advanced-ediscovery.md) 
    
- 设置临近的重复、主题和电子邮件线程[的选项](set-analyze-options-in-advanced-ediscovery.md)，然后运行分析模块 
    
- [设置 "忽略文本" 筛选器](set-ignore-text-in-advanced-ediscovery.md)以排除分析文本和文本字符串;当您运行相关性分析时，这些筛选器也将忽略文本 
    
- [查看](view-analyze-results-in-advanced-ediscovery.md)分析过程的结果 
    
- 配置分析过程的[高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
## <a name="set-up-relevance-training"></a>设置相关性培训

高级电子数据展示中的预测编码（称为相关性）使您能够通过在一小组文档中做出决定（有关是否相关或不相关）来培训系统。
  
- [了解如何设置相关性培训](manage-relevance-setup-in-advanced-ediscovery.md)、标记与案例相关的文件，以及定义案例问题 
    
- [定义案例问题](define-issues-and-assign-users.md)并将每个问题分配给将对文件进行训练的用户 
    
- 将[导入的文件添加到](set-up-loads-to-add-imported-files.md)将添加到相关性培训中的当前或新加载。 负载是添加到事例中并用于相关性培训的一批新文件。 
    
- 定义可添加到相关性培训的[突出显示的关键字](define-highlighted-keywords-and-advanced-options.md)。 这有助于更好地识别与事例相关的文件 
    
## <a name="run-the-relevance-module"></a>运行相关性模块

设置培训后，您就可以运行相关性模块并评估培训设置的有效性。 这将导致相关性排名，帮助您决定是否需要执行其他培训，或者是否准备好开始标记文件以与您的案例相关。
  
- [了解有关](use-relevance-in-advanced-ediscovery.md)根据文件示例集评估、标记、跟踪和重新培训的相关性过程和迭代过程 
    
- [了解评估](assessment-in-relevance-in-advanced-ediscovery.md)，其中专家熟悉案例可查看一组事例文件并确定相关性培训的有效性 
    
- [评估事例文件](tagging-and-assessment-in-advanced-ediscovery.md)以计算培训设置的有效性（称为 "* 丰富程度"），然后将文件标记为相关或与您的案例无关。 这可帮助您确定当前培训是否足够，或者是否应调整培训设置。 
    
- 完成评估后[执行相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)，然后再次将文件标记为与您为事例定义的问题相关或不相关 
    
- [跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)流程，以确定相关性培训是否已实现评估目标（称为 * 稳定培训状态），或者是否需要更多培训;您还可以查看每个案例问题的相关性结果 
    
- [根据相关性分析做出决策](decision-based-on-the-results-in-advanced-ediscovery.md)，以确定可导出以供审阅的结果事例文件集的大小 
    
- [测试相关性分析的质量](test-relevance-analysis-in-advanced-ediscovery.md)，以验证在相关性过程中做出的挑选决定 
    
## <a name="export-results"></a>导出结果

在高级电子数据展示中分析事例数据的最后一步是导出分析结果以供外部审阅。
  
- [了解如何导出事例数据](export-case-data-in-advanced-ediscovery.md)
    
- [导出事例数据](export-results-in-advanced-ediscovery.md)
    
- [查看批处理历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
    
- [导出报告字段](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>其他高级电子数据展示工具

高级电子数据展示不仅提供了分析事例数据、相关性分析和导出数据之外的其他工具和功能。
  
- [运行高级电子数据展示报告](run-reports-in-advanced-ediscovery.md)
    
- [定义大小写和租户设置](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高级电子数据展示实用程序](use-advanced-ediscovery-utilities.md)
