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
ms.openlocfilehash: 865f5c014e25b0a2abee0ed3ce9d6eb1748c6a6b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194557"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>分析审阅集内Advanced eDiscovery

当收集的文档数量很大时，可能很难查看所有文档。 Advanced eDiscovery提供了许多工具来分析文档，以减少要审阅的文档量，而不会丢失任何信息，并帮助您以一致的方式组织文档。 若要详细了解这些功能，请参阅：

- [近似重复检测](near-duplicate-detection-in-advanced-ediscovery.md)

- [电子邮件会话](email-threading-in-advanced-ediscovery.md)

- [主题](themes-in-advanced-ediscovery.md)

分析审阅集内的数据：

1. 为案例配置分析设置。 有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md)。

2. 打开要分析的审阅集。

3. 单击 **"管理审阅集"。**

4. 单击 **"为审阅集运行分析"。**

您可以在案例的"作业"选项卡 **上** 检查分析进度。

 分析完成后，可以查看分析报告，对分析的输出运行审阅集内的查询 (请参阅在审阅集 [) ](review-set-search.md) 中查询，并查看给定文档的相关文档 (请参阅审阅集 [) ](reviewing-data-in-review-set.md) 中的数据。

## <a name="analytics-report"></a>分析报告

若要查看审阅集的分析报告，请：

1. 打开审阅集。

2. 单击 **"管理审阅集"。**

3. 单击 **"查看报告"。**

该报告分析有七个要素：

- **目标总体：** 在审阅集内找到的电子邮件、附件和松散文档的数量。

- **不包含 (附件的文档) ：** 作为透视表、透视表的唯一的近重复项或另一个文档的确切副本的松散文档数。

- **电子邮件：** 包含非独占副本、非独占副本、减号或上述任何内容的电子邮件数量。

- **附件：** 审阅集内其他电子邮件附件的唯一或重复的电子邮件附件数量。

- **按类型显示的文件数：** 文件扩展名标识的文件数。

- **按源显示的文档：** 按原始数据源显示的内容摘要。

- **按进程聚合的文档：** 审阅集过程的内容摘要。 
