---
title: 在 Microsoft 365 中创建和管理高级电子数据展示事例
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
search.appverid:
- MOE150
- MET150
description: 本文介绍如何创建和管理高级电子数据展示事例。 第一步是创建案例并开始使用高级电子数据展示特性和功能。
ms.openlocfilehash: c95994b3706880b40ff6306c02a4bdb5dba7748b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841594"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>创建和管理高级电子数据展示案例

在设置高级电子数据展示并将权限分配给[](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)组织中将管理事例的电子邮件数据展示管理员之后，下一步是创建和管理事例。

本文还提供了有关使用事例管理高级电子数据展示工作流进行法律调查的高级概述。

## <a name="create-a-case"></a>创建案例

完成以下步骤以创建案例并添加成员。 创建案例的用户将自动添加为成员。

1. 转到已分配有电子数据展示权限的用户帐户的凭据 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并登录。 组织管理角色组的成员还可以创建高级电子数据展示事例。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**高级"**。

3. 在 **"高级电子数据展示"** 页上，单击"事例 **"选项卡，** 然后单击"**创建事例"。**

4. 在 **"新建电子数据** 展示案例"飞出页上，为案例指定 (一) ，然后键入可选的案例编号和说明。 在组织中，案例名称必须是唯一的。

5. 单击 **"** 保存"创建案例。

   将新建案例，并显示新案例的"设置"选项卡。

6. 在 **"&"** 选项卡上的"访问权限"磁贴中，**单击"** 选择"，然后单击"更新 **"。**

7. 单击“更新”。

8. 在"**管理此案例"** 飞出页上的"管理成员"下 **，单击"** 添加"以向案例添加成员。

9. 在人员列表中，选中要添加到案例的用户名旁边的复选框。 如前所述，请确保你添加到案例的人已分配有适当的电子数据展示权限。

10. 选择要添加为案例成员的人后，单击"**添加"。**

11. 在 **"管理此案例"** 飞出页中 **，单击"** 保存"以保存新案例成员列表。

12. 单击 **"主页** "选项卡转到案例主页。

## <a name="manage-the-workflow"></a>管理工作流

若要开始使用高级电子数据展示，下面是一个符合常见电子数据展示做法 [的基本工作流](advanced-ediscovery-edrm.md)。 在每个步骤中，我们还将重点介绍您可以浏览的一些扩展的高级电子数据展示功能。

![高级电子数据展示工作流](../media/AeDWorkflow.png)

1. **[将保管](add-custodians-to-case.md) 人 [和非监管数据源添加到](non-custodial-data-sources.md) 案例**。 创建案例后的第一步是添加保管人。 *保管人* 是拥有与案例相关的文档或电子文件的管理控制的人。 此外，还可以添加不与特定用户关联的数据源，但可能与情况相关。

   以下是在向案例 (保管人时) 可以执行某些操作：

   - 保管人 Exchange 邮箱、OneDrive 帐户以及保管人是其中成员的任何 Microsoft Teams 或 Yammer 组的数据都可以"标记为"诉讼数据"。
  
   - 保管人数据通过称为高级 (过程 *重新编制索引*) 。 这有助于在下一步中优化搜索。
  
   - 你可以对保管人数据进行保留。 这将保留调查期间可能与案件相关的数据。
  
   - 可以将其他数据源与保管人 (关联，例如，可以将 SharePoint 站点或 Microsoft 365 组与保管人) 关联，以便可以重新索引、将其置于保留和搜索状态，就像保管人邮箱或 OneDrive 帐户中的数据一样。

   - 您可以使用高级电子 [数据](managing-custodian-communications.md) 展示中的通信工作流向保管人发送法定保留通知。

2. **[搜索与案例相关的数据的数据源](collecting-data-for-ediscovery.md)**。 将保管人和非托管数据源添加到案例后，使用内置搜索工具搜索这些数据源中可能与案例相关的数据。 您可以使用关键字、属性和条件来构建搜索查询[](building-search-queries.md)，以使用与案例最相关的数据返回搜索结果。 还可以执行以下操作：

   - 查看 [可帮助您](search-statistics-in-advanced-ediscovery.md) 优化搜索查询以缩小结果范围的搜索统计信息。

   - 预览搜索结果以快速验证是否已找到相关数据。

   - 修改查询并重新运行搜索。

3. **[将数据添加到审阅集](add-data-to-review-set.md)**。 配置并验证搜索返回所需数据后，下一步是将搜索结果添加到审阅集。 向审阅集添加数据时，项目会从原始位置复制到安全的 Azure 存储位置。 重新对数据进行索引索引，以在审阅和分析审阅集内的项目时优化数据，以便进行全面而快速搜索。 此外，您还可以 [将非 Office 365 数据添加到审阅集](load-non-office-365-data-into-a-review-set.md)。

   还有一种特殊类型的审阅集，你可以向其中添加数据，称为 *对话审阅集*。 这些类型的评论集提供对话重建功能，以重建、审阅和导出与 Microsoft Teams 中的会话一样的主题对话。 有关详细信息，请参阅 [审阅高级 eDiscovery 中的对话](conversation-review-sets.md)。

4. **审阅和分析审阅集内的数据**。 现在数据已位于审阅集内，您可以使用各种工具和功能来查看和分析案例数据，目的是将数据集减少为与正在调查的案例中最相关的数据。 以下是您可以在此过程期间使用的一些工具和功能的列表。

   - [查看文档](view-documents-in-review-set.md)。 这包括查看审阅集内每个文档的元数据，以及查看文档本机版本或文本版本。

   - [创建查询和筛选器](review-set-search.md)。 您可以使用各种搜索条件创建搜索查询 (包括搜索所有文件元数据属性 [) 以](document-metadata-fields-in-advanced-ediscovery.md) 进一步细化和剔除与案例最相关的案例数据。 您还可以使用审阅集筛选器将其他条件快速应用于搜索查询的结果，以进一步优化这些结果。 

   - [创建和使用标记](tagging-documents.md)。 您可以将标记应用于审阅集内的文档，以确定哪些文档是响应式 (还是对案例) 无响应，然后在创建搜索查询时使用这些标记来包含或排除标记的文档。 您还可以标记以确定要导出的文档。

   - [批注和修订文档](view-documents-in-review-set.md#annotate-view)。 可以在审阅中使用批注工具为文档添加批注，并修订文档中的内容作为工作产品。 我们在审阅期间生成批注或修订文档的 PDF 版本，以减少导出未修订的本机版本文档的风险。

   - [分析案例数据](analyzing-data-in-review-set.md)。 高级电子数据展示中的分析功能很强大。 对审阅集内的数据运行分析后，我们会执行诸如近重复检测、电子邮件线程和主题等分析，以帮助减少必须审阅的文档量。 我们还生成汇总了运行分析的结果的分析报告。 如前所述，运行分析还会运行 [律师-客户特权检测模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。

5. **导出和下载案例数据**。 收集、审阅和分析案例数据后的最后一步是从高级电子数据展示中导出数据，以用于外部审阅或供调查团队外部人员查看。 导出数据的过程分两步完成。 第一步是将数据从[](export-documents-from-review-set.md)审阅集中导出，并复制到其他 Azure 存储位置 (Microsoft 提供一个 Azure 存储位置，或由组织托管的 Azure 存储) 。 然后，使用 Azure 存储资源管理器 [将数据](download-export-jobs.md) 下载到本地计算机。 除了导出的数据文件之外，导出包的包含内容还包含导出报告、摘要报表和错误报告。
