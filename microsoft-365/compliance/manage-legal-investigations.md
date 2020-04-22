---
title: 在 Microsoft 365 中管理法律调查
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: 使用 Microsoft 365 合规性中心中的电子数据展示案例来管理您的组织的法律调查。 如果你拥有 E5 订阅，则可以使用高级电子数据展示的文本分析、机器学习和预测编码功能进一步分析事例数据。
ms.openlocfilehash: 41eaa4ca4428c21b905d63365a9b3af7da1df9aa
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635902"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>在 Microsoft 365 中管理法律调查

组织有许多理由来响应与组织中的特定执行官或其他员工有关的法律案件。 这可能包括快速查找和保留电子邮件、文档、即时消息对话以及人员在日常工作任务中使用的其他内容位置中特定于调查的信息。 您可以使用安全与合规中心中的电子数据展示案例工具执行这些和许多其他类似活动。
  
**想要了解 Microsoft 如何管理其电子数据展示调查？** 下面是可下载的[技术白皮书](https://go.microsoft.com/fwlink/?linkid=852161)，可说明我们如何使用相同的搜索和调查工具来管理我们的内部电子数据展示工作流。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>使用电子数据展示事例管理法律调查

通过电子数据展示事例，可以控制哪些用户可以在组织中创建、访问和管理电子数据展示事例。 用例可添加成员并控制他们可以执行的操作类型，在与法律案件相关的内容位置放置保留，并使用内容搜索工具在保留状态中搜索可能对你的案例做出响应的内容。 然后，您还可以导出和下载这些结果，以供外部审阅者进一步调查。
  
- 通过为组织必须执行的每个法律调查创建和使用电子数据展示事例来[管理您的电子数据展示工作流](ediscovery-cases.md) 
    
- [分配电子数据展示权限](assign-ediscovery-permissions.md)以控制可以在组织中创建和管理电子数据展示事例的用户 
    
- [设置合规性边界](tagging-and-assessment-in-advanced-ediscovery.md)以控制电子数据展示管理器可搜索的用户内容位置 
    
- [搜索组织中的内容](search-for-content.md) 
    
### <a name="use-scripts-for-advanced-scenarios"></a>将脚本用于高级方案

与列出的内容搜索方案脚本的前一节一样，我们还创建了一些安全 & 合规性中心 PowerShell 脚本，以帮助您管理电子数据展示事例。
  
- [创建一个电子数据展示保留报告](create-a-report-on-holds-in-ediscovery-cases.md)，其中包含有关与组织中的电子数据展示事例相关的所有保留的信息 
    
- 将用户列表的[邮箱和 OneDrive 位置添加](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)到电子数据展示保留 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>使用 Microsoft 365 中的高级电子数据展示解决方案管理法律调查

Microsoft 365 中的高级电子数据展示解决方案构建在 Office 365 中现有的电子数据展示和分析功能之上。 这一新的解决方案称为*高级电子数据展示*，它提供了一个端到端工作流，用于保留、收集、查看、分析和导出对组织的内部和外部调查做出响应的内容。 它还允许法律团队管理整个法律封存通知工作流，以便与案例中所涉及的保管人进行通信。

高级电子数据展示需要一个用于 Microsoft 365 或 Office 365 组织的 E5 订阅。 有关许可的详细信息，请参阅[高级电子数据展示入门](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

以下是高级电子数据展示中的内置工作流的快速概述。 有关详细信息，请参阅[探究高级电子数据展示工作流](get-started-with-advanced-ediscovery.md#explore-the-advanced-ediscovery-workflow)。

- [创建入门案例](create-new-ediscovery-case.md)

- 通过将管理员添加到案例并在其邮箱、OneDrive 帐户和 Microsoft 团队中的内容上对其成员进行合法保留来[管理保管人](managing-custodians.md)

- 通过自动执行合法保留通知过程来管理与保管人的[通信](managing-custodian-communications.md)

- [索引保管人数据](processing-data-for-case.md)并修复索引错误，以便您可以为调查有效收集数据

- [收集事例数据](collecting-data-for-ediscovery.md)并将其添加[到评审集](collecting-data-for-ediscovery.md#adding-search-results-to-a-review-set)以进行进一步调查

- [查看](view-documents-in-review-set.md)审阅集中的文档、[查询](review-set-search.md)数据和[标记](tagging-documents.md)项

- 使用高级分析工具[分析事例数据](analyzing-data-in-review-set.md)

- [导出事例数据](exporting-data-ediscover20.md)以供外部法律顾问审阅

- 在高级电子数据展示中[管理长时间运行的作业](managing-jobs-ediscovery20.md)
