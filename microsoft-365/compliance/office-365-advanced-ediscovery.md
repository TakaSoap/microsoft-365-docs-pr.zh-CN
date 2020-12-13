---
title: 高级电子数据展示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: 了解高级电子数据展示如何帮助您分析数据、简化文档审阅和做出有效电子数据展示决策。
ms.openlocfilehash: f8ada5d377e72516ea42d8c5dc5680573daec717
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662817"
---
# <a name="advanced-ediscovery-classic"></a>高级电子数据展示（经典）

> [!IMPORTANT]
> **高级电子数据 (经典) 将于 2020 年 12 月 31 日永久停用。**<br/>
> 随着我们继续投资较新版本的高级电子数据展示，我们宣布永久停用和删除高级电子数据展示或经典电子数据展示 (事例) 。
> 如果仍在使用高级电子数据展示 (经典) ，也称为高级电子数据展示 *v1.0，* 请尽快将用法转换为高级电子数据展示 [v2.0](overview-ediscovery-20.md) (也称为 *Microsoft 365*) 中的高级电子数据展示解决方案。  在准备删除所有事例和事例数据时，可以通过从事例导出数据来 [存档事例数据](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide)。
> 高级电子数据展示 v2.0 包含高级电子数据展示 v1.0 中的类似功能，但也提供了许多新功能，如保管人管理、通信管理和审阅集。 若要了解有关高级电子数据展示 v1.0 之前的停用阶段，请参阅停用旧版 [电子数据展示工具](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。

使用高级电子数据展示，可以更好地了解数据并降低电子数据展示成本。 高级电子数据展示可帮助您分析非结构化数据、执行更有效的文档审阅，并做出减少电子数据展示数据的决策。 可以使用存储在 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 365 组和 Microsoft Teams 中的数据。 您可以在安全与合规中心执行电子数据展示搜索，以搜索组、单个邮箱和网站中的内容，然后使用高级电子数据展示分析搜索结果。 准备搜索结果以在高级电子数据展示中进行分析时，光学字符识别支持从图像提取文本。 此功能允许将高级电子数据展示的强大文本分析功能应用于图像文件。
  
高级电子数据展示通过识别冗余信息（具有近重复检测和电子邮件线程分析等功能）来简化并加快文档审阅过程。 相关性功能应用预测编码技术来标识相关文档。 高级电子数据展示从对示例文档的标记决策中学习，并应用统计和自学习技术来计算数据集中每个文档的相关性。 这样，您能够专注于关键文档、快速做出明智的案例策略决策、剔除数据以及确定审阅的优先级。
  
 **为什么要使用高级电子数据展示？** 高级电子数据展示基于 Office 365 中的一组现有电子数据展示功能构建。 例如，您可以使用安全合规中心中的搜索功能对组织内所有内容源执行初始搜索，以确定并收集可能与特定法律案件相关的 &amp; 数据。 然后，您可以通过应用高级电子数据展示的文本分析、机器学习和相关性/预测编码功能，对这些数据执行分析。 这可以帮助您的组织快速处理数千封电子邮件、文档和其他类型的数据，以查找与特定项目最相关的项目 
 
> [!NOTE]
> 高级电子数据展示需要具有高级合规性加载项的 Office 365 E3 或组织的 E5 订阅。 如果你没有该计划，并且想要试用高级电子数据展示，可以注册 [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=698279)企业版 E5 试用版。 大小写。 然后，可以将减少的数据集从 Office 365 导出以进一步查看。 
  
## <a name="get-started"></a>入门

开始使用高级电子数据展示的最快方式是在安全 & 合规中心创建案例并准备搜索结果，在高级电子数据展示中加载这些结果，然后运行 Express 分析来分析该案例数据，然后导出结果进行外部审阅。
  
- [快速概览](quick-setup-for-advanced-ediscovery.md) 高级电子数据展示工作流 
    
- [使用安全与](set-up-users-and-cases-in-advanced-ediscovery.md) 合规中心创建事例、分配电子数据展示权限和添加事例成员，为高级电子数据展示设置&事例 
    
- [在高级电子数据展示中](prepare-data-for-advanced-ediscovery.md) 准备搜索数据并加载到案例 
    
- [将非 Office 365](import-non-office-365-data-into-advanced-ediscovery.md) 数据加载到案例以在高级电子数据展示中对其进行分析 
    
- [使用快速](use-express-analysis-in-advanced-ediscovery.md) 分析快速分析案例数据，然后轻松导出结果 
    
## <a name="analyze-data"></a>分析数据

在高级电子数据展示中将搜索数据加载到案例后，你将使用分析模块开始分析它。 分析过程的第一部分包括将文件组织成一组唯一文件、重复项和近 (也作为文档相似性) 。 然后，将数据重新组织到电子邮件线程和主题的分层结构组中，并（可选）设置忽略文本筛选器以从分析中排除某些文本。 然后运行分析并查看结果。
  
- [了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md) ，以准备分析高级电子数据展示中的数据 
    
- [设置接近重复](set-analyze-options-in-advanced-ediscovery.md) 项、主题和电子邮件线程的选项，然后运行分析模块 
    
- [设置"忽略文本"筛选器](set-ignore-text-in-advanced-ediscovery.md) 以从分析中排除文本和文本字符串;运行相关性分析时，这些筛选器还将忽略文本 
    
- [查看分析](view-analyze-results-in-advanced-ediscovery.md) 过程的结果 
    
- [配置分析](set-analyze-advanced-settings-in-advanced-ediscovery.md) 过程的高级设置 
    
## <a name="set-up-relevance-training"></a>设置相关性培训

通过高级电子数据展示 (相关性) 预测编码功能，你可以根据你正在查找的内容对系统进行培训，方法为 (做出有关某些内容是否相关的决策) 一小组文档。
  
- [了解如何设置相关性培训](manage-relevance-setup-in-advanced-ediscovery.md) 、标记与案例相关的文件以及定义案例问题 
    
- [定义案例](define-issues-and-assign-users.md) 问题并将每个问题分配给将培训文件的用户 
    
- [将导入的文件添加到将](set-up-loads-to-add-imported-files.md) 添加到相关性培训的当前负载或新负载中。 负载是添加到案例，然后用于相关性培训的新文件批处理 
    
- [定义可添加到](define-highlighted-keywords-and-advanced-options.md) 相关性培训的突出显示关键字。 这可帮助你更好地识别与案例相关的文件 
    
## <a name="run-the-relevance-module"></a>运行相关性模块

设置培训后，即可运行相关性模块并评估培训设置的有效性。 这可产生相关性排名，帮助你确定是否需要执行其他培训，或者是否已准备好开始标记与案例相关的文件。
  
- [了解相关性过程以及](use-relevance-in-advanced-ediscovery.md) 基于示例文件集的评估、标记、跟踪和重新设置的迭代过程 
    
- [了解评估](assessment-in-relevance-in-advanced-ediscovery.md) ，其中熟悉案例的专家会审阅一组案例文件并确定相关性培训的有效性 
    
- [评估案例文件](tagging-and-assessment-in-advanced-ediscovery.md) 以计算 (设置) 的"丰富度"，然后将文件标记为与你的案例相关或不相关。 这可以帮助您确定当前培训是否足够，或者您是否应调整培训设置。 
    
- [在评估完成后执行](tagging-and-relevance-training-in-advanced-ediscovery.md) 相关性培训，然后再次将文件标记为与为案例定义的问题相关或不相关 
    
- [跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md) 过程，以确定相关性培训是否已实现评估目标 (称为*稳定培训状态) 是否需要更多培训;还可以查看每个案例问题的相关性结果 
    
- [根据相关性分析做出决策](decision-based-on-the-results-in-advanced-ediscovery.md) ，以确定可导出供审阅的结果案例文件集的大小 
    
- [测试相关性分析的质量](test-relevance-analysis-in-advanced-ediscovery.md) ，以验证在相关性过程中做出剔除决策 
    
## <a name="export-results"></a>导出结果

在高级电子数据展示中分析案例数据的最后一步是导出分析结果以用于外部审阅。
  
- [了解如何导出案例数据](export-case-data-in-advanced-ediscovery.md)
    
- [导出事例数据](export-results-in-advanced-ediscovery.md)
    
- [查看批处理历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
    
- [导出报告字段](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>其他高级电子数据展示工具

高级电子数据展示提供了除分析案例数据、相关性分析和导出数据之外的其他工具和功能。
  
- [运行高级电子数据展示报告](run-reports-in-advanced-ediscovery.md)
    
- [定义案例和租户设置](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高级电子数据展示实用程序](use-advanced-ediscovery-utilities.md)
