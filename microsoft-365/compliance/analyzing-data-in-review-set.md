---
title: 在高级电子数据展示中分析评审集中的数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0f9cb386ce57d6581ade5caa05e029511100d9b3
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42556780"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>在高级电子数据展示中分析评审集中的数据

收集的文档数较大时，可能很难查看所有文档。 高级电子数据展示提供了大量工具来分析文档，以减少要查看的文档量而不丢失任何信息，并帮助您以一致的方式组织文档。 若要了解有关这些功能的详细信息，请参阅：

- [近似重复检测](near-duplicates.md)

- [电子邮件会话](email-threading.md)

- [主题](themes.md)

若要分析审阅集中的数据，请执行以下操作：

1. 为你的事例配置分析设置。 有关详细信息，请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。

2. 打开要分析的审阅集。

3. 单击 "**管理审阅集**"。

4. 单击**评审集的 "运行分析"**。

可以在案例的 "**作业**" 选项卡上检查分析进度。

 完成分析后，您可以查看分析报告，在审核的输出集内运行查询（请参阅[评审集内的查询](review-set-search.md)），并查看给定文档的相关文档（请参阅[审阅集中的数据](reviewing-data-in-review-set.md)）。

## <a name="analytics-report"></a>分析报告

查看审阅集的分析报告：

1. 打开评审集。

2. 单击 "**管理审阅集**"。

3. 单击 "**查看报告**"。

此报告包含来自分析的七个组件：

- **目标填充：** 在审阅集中找到的电子邮件、附件和松散文档的数量。

- **文档（不包括附件）：** 要进行透视的松散文档的数量、数据透视表的重复的唯一性或另一个文档的完全相同的数量。

- **电子邮件：** Inclusives 的电子邮件数、包含的副本、包含的 minuses 或以上任何内容。

- **附件：** 审阅集中其他电子邮件附件的唯一或重复的电子邮件附件数。

- **按类型的文件数：** 由文件扩展名标识的文件数。

- **按源的文档：** 按其原始数据源的内容摘要。

- **按进程聚合的文档：** 按评审过程集的内容摘要。 
