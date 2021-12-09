---
title: 分析审阅集内Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解分析文档集时可用于组织文档集Advanced eDiscovery的信息。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 829e6e6441403cf5a934e81a1a437f65d2de3db3
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61369692"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>分析审阅集内Advanced eDiscovery

当收集的文档数量很大时，可能很难查看所有文档。 Advanced eDiscovery提供了许多工具来分析文档，以减少要审阅的文档量而不会丢失任何信息，并帮助您以一致的方式组织文档。 若要详细了解这些功能，请参阅：

- [近似重复检测](near-duplicate-detection-in-advanced-ediscovery.md)

- [电子邮件会话](email-threading-in-advanced-ediscovery.md)

- [主题](themes-in-advanced-ediscovery.md)

## <a name="run-analytics-for-a-review-set"></a>为审阅集运行分析

分析审阅集内的数据：

1. 为案例配置分析设置。 有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。

2. 打开要分析的审阅集。

3. 单击 **"分析**  >  **""运行&电子邮件分析"。**

   ![从"&"下拉列表中选择"运行文档并分析电子邮件"](..\media\RunAnalytics1.png)

您可以在案例的"作业"选项卡 **上** 检查分析进度。

 分析完成后，可以查看分析报告，对分析的输出运行审阅集内的查询 (请参阅在审阅集内查询，并查看给定文档的相关文档 (请参阅审阅[](review-set-search.md)集内的数据。 [](reviewing-data-in-review-set.md)

## <a name="using-the-for-review-filter-query"></a>使用"审阅"筛选器查询

为评价集运行分析后，可以使用自动生成的筛选器查询 (称为"审阅) ，用于筛选评论以排除非特定项目、重复项或非包含项。 这将仅保留审阅集内具有代表性、独特性且包含的项目。

若要将 **"针对审阅**"筛选器查询应用于审阅集，请选择"已保存 **的筛选器** 查询"下拉列表，然后选择"**\[ 自动启动] 用于审阅"。**

![从"已保存的筛选器查询"下拉列表中选择"审阅"](..\media\ForReviewFilterQuery1.png)

以下是用于"审阅"筛选器 **查询的** 语法：

`(((FileClass="Email") AND (InclusiveType="InclusiveMinus" OR InclusiveType="Inclusive")) OR ((FileClass="Attachment") AND (UniqueInEmailSet="true")) OR ((FileClass="Document") AND (MarkAsRepresentative="Unique")) OR (FileClass="Conversations"))`

下面的列表根据将筛选器查询应用于审阅集后显示的内容描述筛选查询的结果。

- **电子邮件**。 显示标记为非独占 **或****非独占用户的项目**。 非独占项目是电子邮件线程中的最终邮件。 它包含电子邮件线程中以前的所有内容。 包含的减号包含一个或多个与电子邮件线程中的特定邮件相关联的附件。 审阅者可以使用非独占减号值来确定电子邮件线程中哪些特定邮件具有关联的附件。

- **附件**。 筛选出同一电子邮件集内重复的附件。 只显示电子邮件线程中唯一的附件。

- **文档和其他**。 筛选出重复的文档。 只显示审阅集内唯一的文档。

- **Teams对话**。 将显示Teams (Yammer) 的所有会话和对话。

有关非独占类型和文档唯一性的信息，请参阅电子邮件[主题](email-threading-in-advanced-ediscovery.md)Advanced eDiscovery。

> [!NOTE]
> 在 Advanced eDiscovery 中[](advanced-ediscovery-new-case-format.md)新事例格式的公共预览期间，对于使用在2021 年 11 月 4 日之前创建的大案例格式) ，"审阅"筛选器查询不会返回审阅集 Teams 或 Yammer 对话 (。 此问题已解决。 这意味着，如果将"审阅"查询重新应用至使用大案例格式的审阅集，则可能会显示更多与筛选器查询匹配的项目，因为将包含所有 Teams 或 Yammer 对话。

## <a name="analytics-report"></a>分析报告

若要查看审阅集的分析报告，请：

1. 打开审阅集。

2. 单击 **"分析**  >  **显示报告"。**

**分析报告** 分析有七个要素：

- **目标总体：** 在审阅集内找到的电子邮件、附件和松散文档的数量。

- **不包含 (附件的文档) ：** 作为透视表、透视表的唯一的近重复项或另一个文档的确切副本的松散文档数。

- **电子邮件：** 标记为非独占、非独占副本、包含非独占副本或上述任何邮件的电子邮件数量。

- **附件：** 审阅集内其他电子邮件附件的唯一或重复的电子邮件附件数量。

- **按文件类型对文档编号：** 文件扩展名标识的文件数。

- **按源显示的文档：** 按原始数据源显示的内容摘要。

- **按进程聚合的文档：** 审阅集过程的内容摘要。 
