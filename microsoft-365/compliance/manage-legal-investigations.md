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
ms.custom:
- seo-marvel-apr2020
description: 使用 Office 365 &合规中心中的电子数据展示事例来管理组织的法律调查。
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840701"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>在 Microsoft 365 中管理法律调查

组织有很多理由对涉及组织中某些管理人员或其他员工的法律案件做出响应。 这可能涉及到快速查找和保留电子邮件、文档、即时消息对话以及人员在日常工作任务中使用的其他内容位置中进一步调查特定的信息。 可以使用安全与合规中心中的电子数据展示案例工具执行这些活动以及许多其他类似的活动。
  
**想知道 Microsoft 如何管理其电子数据展示调查？** 你可以 [下载以下技术](https://go.microsoft.com/fwlink/?linkid=852161) 白皮书，说明如何使用相同的搜索和调查工具来管理内部电子数据展示工作流。

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>使用电子数据展示事例管理法律调查

电子数据展示事例使你可以控制哪些人可以在组织中创建、访问和管理电子数据展示事例。 使用案例可添加成员并控制他们可以执行的操作类型，对与法律案件相关的内容位置进行保留，并使用内容搜索工具在保留位置中搜索可能响应您的案例的内容。 然后，还可以导出和下载这些结果，供外部审阅者进一步调查。
  
- [通过为组织必须](ediscovery-cases.md) 执行的每一个法律调查创建和使用电子数据展示事例来管理电子数据展示工作流。

- [分配电子数据展示权限](assign-ediscovery-permissions.md) 以控制哪些人可以在组织中创建和管理电子数据展示事例。

- [设置合规性边界](set-up-compliance-boundaries.md) 以控制电子数据展示管理员可以搜索的用户内容位置。

- [搜索组织中](search-for-content.md) 的内容。

### <a name="use-scripts-for-advanced-scenarios"></a>将脚本用于高级方案

与列出内容搜索方案的脚本的上一部分一样，我们还创建了一些安全与合规& PowerShell 脚本，以帮助你管理电子数据展示事例。
  
- [创建一个电子数据展示保留](create-a-report-on-holds-in-ediscovery-cases.md) 报告，其中包含有关组织中与电子数据展示事例关联的所有保留的信息。

- [将用户列表的](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) 邮箱和 OneDrive 位置添加到电子数据展示保留。
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>使用 Microsoft 365 中的高级电子数据展示解决方案管理法律调查

Microsoft 365 中的高级电子数据展示解决方案基于 Office 365 中的现有电子数据展示和分析功能。 这一名为 *"高级* 电子数据展示"的新解决方案提供了端到端工作流，用于保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的内容。 它还允许法律团队管理整个法定保留通知工作流，以与案例所涉及的保管人进行通信。

高级电子数据展示需要 Microsoft 365 或 Office 365 组织的 E5 订阅。 有关许可详细信息，请参阅"[设置高级电子数据展示"。](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

以下是高级电子数据展示中的内置工作流的快速概述。 有关详细信息，请参阅 [管理高级电子数据展示工作流](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

- [创建一个](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) 案例以开始。

- [通过将保管人](managing-custodians.md) 添加到案例并合法保留其邮箱、OneDrive 帐户和 Microsoft Teams 中的内容，管理保管人。

- [通过自动](managing-custodian-communications.md) 执行法定保留通知流程来管理与保管人的通信。

- [为保管人数据](processing-data-for-case.md) 编制索引并修复索引错误，以便有效地收集调查数据。

- [收集案例](collecting-data-for-ediscovery.md) 的数据，并 [将其添加到审阅集以](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) 进一步调查。

- [查看](view-documents-in-review-set.md) 审阅 [集](review-set-search.md) 内的文档 [、](tagging-documents.md) 查询数据和标记项。

- [使用高级分析工具](analyzing-data-in-review-set.md) 分析案例数据。

- [导出案例数据](exporting-data-ediscover20.md) ，供外部律师审阅。

- [在高级电子数据展示](managing-jobs-ediscovery20.md) 中管理长时间运行的作业。
