---
title: Microsoft 365 中的高级电子数据展示解决方案概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解 Microsoft 365 中的高级电子数据展示解决方案。 本文概述了 Microsoft 365 中的高级电子数据展示，这是一种可帮助您管理内部和外部调查的工具。 它还包含使用高级电子数据展示管理法律调查的业务原因。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b2fa0b42a7f439aa65ae53e76e377ded92f97b7
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840875"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 高级电子数据展示概述

Microsoft 365 中的高级电子数据展示解决方案基于现有 Microsoft 电子数据展示和分析功能。 高级电子数据展示提供了端到端工作流，用于保留、收集、分析、审阅、分析和导出对组织内部和外部调查做出响应的内容。 它还允许法律团队管理整个法定保留通知工作流，以与案例所涉及的保管人进行通信。

高级电子数据展示可通过发现组织所存储的数据来帮助组织响应法律事务或内部调查。 您可以通过识别感兴趣的人员及其数据源无缝管理电子数据展示工作流，无缝应用保留以保留数据，然后管理合法保留通信过程。 通过从源收集数据，可以搜索实时 Microsoft 365 平台以快速找到所需的内容。 智能的机器学习功能（如深度索引、电子邮件线程和近重复检测）还有助于将大量数据减少至相关数据集。

以下各节介绍这些高级电子数据展示功能如何帮助你的组织。

## <a name="discover-and-collect-data-in-place"></a>就地发现和收集数据

通常，依赖多个第三方电子数据展示解决方案的组织需要从 Microsoft 365 复制大量数据以处理数据，并且必须承载重复数据。 这一需要会增加查找相关数据的时间，以及管理多个解决方案的风险、成本和复杂性。

通过 Microsoft 365 中的高级电子数据展示，你可以发现源数据并位于 Microsoft 365 安全性和合规性边界内。  通过从实时系统就地收集数据，高级电子数据展示可以减少返回到源的接触，并减少必须查找缺少的内容的不必要工作，这通常发生在传统电子数据展示解决方案中的日记延迟时。

Teams、Yammer、SharePoint Online、OneDrive for Business 和 Exchange Online 中数据的本机搜索和收集功能进一步增强了数据发现。 例如，高级电子数据展示：

- 重新构造 Teams 对话 (而不是从对话或对话中返回) 。

- 通过电子邮件和 Teams 聊天中的链接或新式附件收集与用户共享的基于云的内容。

- 具有对数百种非 Microsoft 365 文件类型的内置支持。

- 从数据连接器导入并 (Microsoft 365 中导入和存档的第三方源（如) 、Facebook、Slack 和 Zoom 会议） [收集数据](archiving-third-party-data.md)。

## <a name="manage-ediscovery-workflow-in-one-platform"></a>在一个平台中管理电子数据展示工作流

高级电子数据展示可帮助你减少需要依赖的电子数据展示解决方案的数量。 它提供了简化的端到端工作流，所有这些都发生在 Microsoft 365 中。 高级电子数据展示通过自动将唯一和共享数据源映射到感兴趣的人员（称为保管人 (*) ）* 和在收集潜在相关信息进行分析和审阅之前提供对潜在相关信息的报告和分析，帮助减少识别和收集潜在相关信息源的接触。

此外，Microsoft Graph API 还可以帮助您自动执行电子数据展示工作流，并扩展自定义解决方案的高级电子数据展示。

## <a name="cull-data-intelligently"></a>智能剔除数据

高级电子数据展示中的智能机器学习功能可帮助你减少要查看的数据量。 这些智能功能可帮助你减少大量数据并剔除到相关集合。 例如，内置审阅集查询通过标识近重复项来帮助仅筛选唯一内容。 此功能可以大大减少要审阅的数据量。

其他机器学习功能可以使用智能标记和技术辅助审阅工具（如相关性模块）进一步优化和识别数据。

## <a name="advanced-ediscovery-architecture"></a>高级电子数据展示体系结构

下面是一个高级电子数据展示体系结构图，它显示了单地理位置环境和多地理位置环境中端到端工作流，以及与电子发现参考模型 [ (](advanced-ediscovery-edrm.md) EDRM) 保持一致的端到端数据流。

[![模型海报：Microsoft 365 中的高级电子数据展示体系结构](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[作为图像查看](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[下载为 PDF 文件](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[下载为 Visio 文件](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

有关高级电子数据展示中的端到端工作流详细信息，请参阅 [此 Microsoft Mechanics 视频](https://go.microsoft.com/fwlink/?linkid=2066133)。

## <a name="advanced-ediscovery-workflow"></a>高级电子数据展示工作流

以下各节介绍 Microsoft 365 合规中心高级电子数据展示工具中内置工作流中的每个步骤。 以下屏幕截图显示了名为 *2020.11.03 - Contoso v. Fabrikam 的大小写的"概述"选项卡*。

![内置高级电子数据展示工作流中的选项卡](../media/AeD-Case-Screenshot1.png)

有关详细信息，请参阅 [管理高级电子数据展示工作流](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)。

### <a name="managing-custodians-and-non-custodial-data-sources"></a>管理保管人和非监管数据源

使用 **"数据源** "选项卡可添加和管理已识别为案件的关注人的人员，以及可能未与保管人关联的其他数据源。 添加保管人或非监管数据源时，您可以快速执行以下操作：对保管人和非监管数据源实施法定保留、与保管人通信，以及搜索保管人和非监管数据源以收集与案例相关的内容。 随着案例的进行，添加新保管人或非托管日期源或将其从案例中释放很容易。 有关详细信息，请参阅["使用保管人"。](managing-custodians.md)

### <a name="managing-legal-hold-notifications"></a>管理合法保留通知

使用 **"** 通信"选项卡管理在这种情况下与保管人通信的过程。 法定保留通知指示保管人保留与案件相关的任何内容。 法律团队必须能够跟踪保管人已收到、阅读和确认的通知。 高级电子数据展示中的通信工作流允许你创建和发送初始通知、提醒、释放通知和上报（如果保管人无法确认保留通知）。 有关详细信息，请参阅["使用通信"。](managing-custodian-communications.md)

### <a name="managing-content-preservation"></a>管理内容保留

向案例添加保管人时，可以保留监管数据。 使用 **"保留** "选项卡管理添加保管人时创建的保留，并管理与案例关联的其他合法保留;例如，您可以标识非媒体数据源，并设置保留。 您还可以编辑该情况下的任何保留，并使它成为基于查询的保留，以仅保留与查询匹配的内容。 例如，可以将日期范围添加到保留项，以便仅保留特定日期范围内创建的内容。 还可以获取有关保留的内容的统计信息，在保留内容不再与案例相关后删除保留，或者将其删除。 有关详细信息，请参阅"[管理保留"。](managing-holds.md)

### <a name="indexing-custodian-data"></a>索引保管人数据

向案例添加保管人和相应的保管人数据源时，保管人数据源的任何部分索引项都由称为"高级索引"的过程 *重新编制索引*。 这样，当您运行搜索来收集案件集数据时，可以完全搜索诸如图像、不支持的文件类型和其他可能未索引的内容。 使用" **处理** "选项卡监视高级索引的状态，并使用称为错误修正的过程修复 *处理错误*。 有关详细信息，请参阅修复 [处理错误](processing-data-for-case.md)。

### <a name="collecting-case-data"></a>收集事例数据

使用 **"搜索** "选项卡创建搜索，以搜索就地查询和非查询数据源，以查找与案例相关的内容。 您可以使用关键字和条件) 创建和运行基于查询的搜索 (，以标识一组与案例相关的电子邮件和文档，并且您希望在电子数据展示工作流的后续步骤中进一步查看和分析这些搜索。 可以创建一个或多个与案例关联的搜索。 您还可以使用搜索工具预览示例文档和查看搜索统计信息，以帮助您优化和改进搜索结果。 在您满意搜索结果包含与案例相关的所有数据后，您将搜索结果添加到审阅集，以进一步查看、分析和剔除。 有关详细信息，请参阅 [收集案例数据](collecting-data-for-ediscovery.md)。

### <a name="reviewing-and-analyzing-case-data"></a>查看和分析案例数据

使用 **"审阅集** "选项卡查看和分析从实时系统收集并添加到审阅集的内容。 审阅集是该数据的静态集合 (换句话说，是在电子数据展示工作流的上一阶段收集的) 数据) 的脱机副本 (以及（如果适用）非定期数据) 。 将搜索结果添加到审阅集时，将触发一个进程，以从容器中提取文件、提取元数据和提取文本。 此过程完成后，系统会生成从保管人收集的所有数据的新索引，并添加到审阅集。 将数据添加到审阅集后，可以运行更多查询来缩小案例数据范围，以文本或本机文件格式查看数据，并批注、修订和标记审阅集内的文档。 还可以执行高级分析，如标识文档复制、电子邮件线程和主题。 在仅将数据剔除到与案例相关的内容后，您可以直接下载文档，也可以将其与文件元数据、批注和任何标记一起导出。 有关详细信息，请参阅：

- [查看审阅集中的文档](view-documents-in-review-set.md)

- [查询审阅集中的数据](review-set-search.md)

- [标记审阅集中的文档](tagging-documents.md)

- [分析审阅集内的数据](analyzing-data-in-review-set.md)

### <a name="exporting-data-for-review-and-presentation"></a>导出数据进行审阅和演示

从审阅集导出数据后，使用"导出 **"选项卡管理** 导出作业，然后从审阅集下载数据。 导出审阅集时，数据将上载到 Microsoft 提供的 Azure 存储位置 (或由组织托管的 Azure 存储) 。 将其上传到 Azure 后，它将可供下载到本地计算机。 可以在"导出"选项卡上获取下载导出的数据所需的存储 **评估密钥。** 有关详细信息，请参阅"[导出案例数据"。](exporting-data-ediscover20.md)

### <a name="managing-jobs"></a>管理作业

使用 **"** 作业"选项卡监视长时间运行的进程，查看已启动的与案例相关的任务。 例如，与重新索引、搜索和导出事例数据相关的作业。 例如，如果在包含许多数据源的"搜索"选项卡上创建搜索，则此搜索过程的状态将显示在"作业 **"选项卡上**。有关详细信息，请参阅"[管理作业"。](managing-jobs-ediscovery20.md)

### <a name="configuring-case-settings"></a>配置案例设置

使用 **"设置** "选项卡配置大小写范围的设置。 这包括向案例添加成员、关闭或删除案例以及配置搜索和分析设置。 有关详细信息，请参阅：

- [向案例添加成员](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

- [关闭或删除事例](close-or-delete-case.md)

- [配置搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
