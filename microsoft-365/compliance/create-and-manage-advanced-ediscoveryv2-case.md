---
title: 创建和管理Advanced eDiscovery事例Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文介绍如何创建和管理Advanced eDiscovery案例。 第一步是创建案例并开始Advanced eDiscovery特性和功能。
ms.openlocfilehash: 69d2f22a3792f2217ea8ef58ae9771dd4a10f32d
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573243"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>创建和管理Advanced eDiscovery案例

在设置Advanced eDiscovery并将权限分配给将管理[](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)事例的组织中电子数据展示管理员之后，下一步是创建和管理事例。

本文还简要概述了法律案件或其他类型的调查Advanced eDiscovery管理事例工作流。

## <a name="create-a-case"></a>创建案例

完成以下步骤以创建案例并添加成员。 创建案例的用户将自动添加为成员。 案例的成员可以在任务中访问Microsoft 365 合规中心并执行Advanced eDiscovery任务。

1. 转到 <https://compliance.microsoft.com> ，然后使用已分配有电子数据展示权限的用户帐户的凭据登录。 组织管理角色组的成员还可以创建Advanced eDiscovery案例。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击 **显示所有**，然后单击" **电子数据展示>高级**。

3. 在 **"Advanced eDiscovery"** 页上，单击"事例 **"** 选项卡，然后单击"**创建事例"。**

4. 在" **新建电子数据** 展示案例"飞出页面上，为案件 (一) ，然后键入可选的案例编号和说明。 案例名称在组织中必须是唯一的。

5. 单击 **"保存** "创建案例。

   将新建一个 **case，设置** 显示新案例的"新建"选项卡。

6. 在 **"&"选项卡** 上的"访问 **设置权限"** 磁贴中，单击"选择 **"。**

7. 在" **管理此案例** "飞出页面的" **管理成员"下**，单击 **"添加** "将成员添加到案例。

8. 在人员列表中，选中要添加到案例的用户名旁边的复选框。 如前所述，请确保你添加到案例的人已分配有适当的电子数据展示权限。

9. 选择要添加为案例成员的人后，单击"添加 **"。**

10. 在 **管理此案例** 弹出页面中， **保存** 以保存新的案例成员列表。

11. 单击" **主页"** 选项卡以转到案例主页。

## <a name="manage-the-workflow"></a>管理工作流

为了让你开始使用Advanced eDiscovery，下面是一个符合常见电子数据展示做法的基本[工作流](advanced-ediscovery-edrm.md)。 在每个步骤中，我们还将重点介绍一些Advanced eDiscovery扩展的功能。

![Advanced eDiscovery工作流。](../media/AeDWorkflow.png)

1. **[将保管](add-custodians-to-case.md)[人和非托管数据源添加到](non-custodial-data-sources.md)案例**。 创建案例后的第一步是添加保管人。 保管 *人* 是具有与案例相关的文档或电子文件的管理控制权限的人。 此外，还可以添加不与特定用户关联但可能与案例相关的数据源。

   下面是在向案例 (保管人时) 可以执行某些操作：

   - 保管人 Exchange 邮箱、OneDrive 帐户以及保管人是其中成员的任何 Microsoft Teams 或 Yammer 组的数据可以"标记为"在案例内为诉讼数据。
  
   - 保管人数据通过称为高级 (过程 *对保管人数据重新* 编制) 。 这有助于在下一步中优化搜索。
  
   - 你可以将保管人数据保留。 这将保留调查期间可能与案例相关的数据。
  
   - 可以将其他数据源与保管人 (例如，可以将 SharePoint 站点或 Microsoft 365 组与保管人) 以便可以重新索引、保留和搜索此数据，就像保管人邮箱或 OneDrive 帐户中的数据一样。

   - 您可以使用安全[中心中的](managing-custodian-communications.md)通信Advanced eDiscovery向保管人发送法定保留通知。

2. **[从数据源中收集相关内容](create-draft-collection.md)**。 将保管人和非托管数据源添加到案例后，使用内置集合工具搜索这些数据源中可能与案例相关的内容。 您可以使用关键字、属性和条件来构建搜索查询[](building-search-queries.md)，这些查询使用与案例最相关的数据返回搜索结果。 还可以执行以下操作：

   - 查看 [可帮助您](collection-statistics-reports.md) 优化集合以缩小结果范围的集合统计信息。

   - 预览集合示例，以快速验证是否找到相关数据。

   - 修改查询并重新运行集合。

3. **[将集合提交到审阅集](commit-draft-collection.md)**。 配置并验证搜索返回所需数据后，下一步是将搜索结果添加到审阅集。 向审阅集添加数据时，项目会从原始位置复制到安全Azure 存储位置。 再次对数据进行索引索引，以在审阅和分析审阅集内的项目时优化数据，以便进行全面而快速的搜索。 此外，您还可以[将非Office 365数据添加到审阅集](load-non-office-365-data-into-a-review-set.md)。

   还有一种特殊类型的审阅集，你可以将数据添加到 ，称为对话 *审阅集*。 这些类型的评论集提供了对话重建功能，可以重新构造、审阅和导出线程对话，如Microsoft Teams。 有关详细信息，请参阅 [审阅高级 eDiscovery 中的对话](conversation-review-sets.md)。

4. **查看和分析审阅集内的数据**。 现在数据已位于审阅集内，您可以使用各种工具和功能来查看和分析案例数据，目的是将数据集减少为与正在调查的案例最相关的数据。 以下是您可以在此过程期间使用的一些工具和功能的列表。

   - [查看文档](view-documents-in-review-set.md)。 这包括查看审阅集内每个文档的元数据，以及查看其本机版本或文本版本的文档。

   - [创建查询和筛选器](review-set-search.md)。 使用各种搜索条件创建搜索查询 (包括搜索所有文件元数据属性 [) ](document-metadata-fields-in-advanced-ediscovery.md) 以进一步优化和剔除与案例最相关的案例数据。 您还可以使用审阅集筛选器将其他条件快速应用于搜索查询的结果，以进一步优化这些结果。 

   - [创建和使用标记](tagging-documents.md)。 可以将标记应用于审阅集内的文档，以确定哪些文档是响应式 (还是对) 没有响应，然后在创建搜索查询以包含或排除带标记的文档时使用这些标记。 您还可以标记以确定要导出的文档。

   - [批注和修订文档](view-documents-in-review-set.md#annotate-view)。 可以在评论中使用该批注工具为文档添加批注，将文档中的内容修订为工作产品。 在审阅期间，我们生成批注或修订文档的 PDF 版本，以减少导出未修改的本机版本文档的风险。

   - [分析案例数据](analyzing-data-in-review-set.md)。 应用程序分析功能Advanced eDiscovery功能。 对审阅集内的数据运行分析后，我们执行分析，如接近重复检测、电子邮件线程和主题，可帮助减少必须查看的文档量。 我们还生成了一个分析报告，汇总了运行分析的结果。 如前所述，运行分析还会运行 [律师-客户特权检测模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。

5. **导出和下载案例数据**。 收集、审阅和分析案件集数据后，最后一步是从 Advanced eDiscovery 导出数据进行外部审阅或供调查团队外部人员审阅。 导出数据的过程包含两个步骤。 第一步是将数据从[](export-documents-from-review-set.md)审阅集中导出，并复制到其他 Azure 存储 位置 (Microsoft 提供的位置或由组织管理的位置) 。 然后，Azure 存储资源管理器[将数据](download-export-jobs.md)下载到本地计算机。 除了导出的数据文件之外，导出包的 包含还包含导出报告、摘要报表和错误报告。

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery体系结构

下面的体系结构图显示了单地理位置环境和多地理位置环境中 Advanced eDiscovery 端到端工作流，以及与电子发现参考模型一致的端到端[数据流](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)。

[![模型海报：Advanced eDiscovery体系结构Microsoft 365。](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[以图像视图](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[下载为 PDF 文件](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[下载为Visio文件](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
