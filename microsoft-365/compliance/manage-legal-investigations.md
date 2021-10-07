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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: 使用 Microsoft 365 合规中心电子数据展示事例来管理组织的法律调查。
ms.openlocfilehash: fc4e89645ef1912c33ab89ec190c87dc9c8a8965
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189377"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>在 Microsoft 365 中管理法律调查

组织有很多理由对涉及组织中某些主管或其他员工的法律案件作出响应。 这可能涉及快速查找和保留电子邮件、文档、即时消息对话以及用户用于其日常工作任务的其他内容位置中的进一步调查特定信息。 可以使用安全与合规中心中的电子数据展示案件集工具执行这些和其他许多类似活动。
  
**想要了解 Microsoft 如何管理其电子数据展示调查？** 可 [下载以下技术](https://go.microsoft.com/fwlink/?linkid=852161) 白皮书，介绍如何使用相同的搜索和调查工具来管理内部电子数据展示工作流。

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>使用电子数据展示事例管理法律调查

电子数据展示事例使你可以控制哪些人可以在组织中创建、访问和管理电子数据展示事例。 使用案例可添加成员并控制他们可以执行的操作类型，将与法律案件相关的内容位置放在保留状态，并使用内容搜索工具在保留位置搜索可能响应您的案例的内容。 然后，还可以导出和下载这些结果，供外部审阅者进一步调查。
  
- [通过为组织必须](./get-started-core-ediscovery.md) 执行的每一项法律调查创建和使用电子数据展示事例来管理电子数据展示工作流。

- [分配电子数据展示权限](assign-ediscovery-permissions.md) ，以控制谁可以在组织中创建和管理电子数据展示事例。

- [设置合规性边界](set-up-compliance-boundaries.md) 以控制电子数据展示管理员可搜索的用户内容位置。

- [搜索组织中](search-for-content.md) 的内容。

### <a name="use-scripts-for-advanced-scenarios"></a>将脚本用于高级方案

与上一部分列出适用于内容搜索方案的脚本一样，我们还创建了一些安全与合规中心 PowerShell 脚本&帮助您管理电子数据展示事例。
  
- [创建电子数据展示保留](create-a-report-on-holds-in-ediscovery-cases.md) 报告，其中包含有关组织中与电子数据展示事例关联的所有保留的信息。

- [将用户OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)邮箱和邮箱位置添加到电子数据展示保留。
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>使用 Microsoft 365 中的 Advanced eDiscovery 解决方案管理法律Microsoft 365

Advanced eDiscovery解决方案Microsoft 365中现有的电子数据展示和分析功能Office 365。 这一称为 *Advanced eDiscovery* 的新解决方案提供了端到端工作流，以保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的内容。 它帮助法律团队管理整个法定保留通知工作流，与案件有关保管人进行沟通。

Advanced eDiscovery组织或组织需要 E5 Microsoft 365 Office 365订阅。 有关许可详细信息，[请参阅设置](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)Advanced eDiscovery。

下面简要概述了 Advanced eDiscovery 中的内置Advanced eDiscovery。 有关详细信息，请参阅管理[Advanced eDiscovery工作流](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

- [创建一个](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) 案例以开始。

- [通过将保管](managing-custodians.md)人添加到案例并合法保留其邮箱中的内容、OneDrive帐户和Microsoft Teams他们的成员来管理保管人。

- [通过自动](managing-custodian-communications.md) 执行合法保留通知流程，管理与保管人的通信。

- [对保管](processing-data-for-case.md) 人数据编制索引并修复索引错误，以便有效地收集数据以便进行调查。

- [收集案例](collecting-data-for-ediscovery.md) 的数据，并 [将其添加到审阅集以](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) 进一步调查。

- [查看](view-documents-in-review-set.md) 审阅 [集](review-set-search.md) 内的文档 [、](tagging-documents.md) 查询数据和标记项目。

- [使用高级分析工具](analyzing-data-in-review-set.md) 分析案例数据。

- [导出案例数据](exporting-data-ediscover20.md) ，供外部律师审阅。

- [在作业中管理长时间运行的](managing-jobs-ediscovery20.md)Advanced eDiscovery。