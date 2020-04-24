---
title: 在高级电子数据展示中收集事例数据
f1.keywords:
- NOCSH
ms.author: esclee
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
ms.openlocfilehash: 462c58f8531265026b34fe3d8484736aefa4c5fa
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799935"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>在高级电子数据展示中收集事例数据

确定了您的保管人和数据源对您的情况有意义之后，就可以确定要深入研究的文档集。 您可以使用高级电子数据展示中的搜索工具，在 Microsoft 365 中识别 custodial 和非 custodial 位置的相关文档。

运行搜索后，可以查看检索的项目的统计信息，例如与搜索查询匹配项目数最多的位置。 您还可以预览结果的子集。 在确定要进一步检查的文档集后，可以将搜索结果添加到审阅集以供收集和处理。

## <a name="create-a-search"></a>创建搜索

在 "**搜索**" 选项卡上选择 "**新建搜索**" 将启动向导，指导您完成创建搜索。 有关如何创建搜索的详细信息，请参阅[创建搜索以收集数据](create-search-to-collect-data.md)。

创建搜索后，会显示包含详细信息的飞出页面。 "**统计信息**" 和 "**预览**" 按钮最初不可用，因为搜索尚未完成。 您可以在 "**搜索**" 选项卡上跟踪搜索进度。

## <a name="view-search-results-and-statistics"></a>查看搜索结果和统计信息

内容搜索有两个组件：统计信息（估计）和预览。 每个组件完成后，您将看到 "**搜索**" 选项卡上的相应列中显示的状态将从 "已**提交**到**进行中**" 更改为 "**已完成**"。

完成搜索估计后，选择搜索以显示弹出页面，这将显示有关搜索结果的一些高级统计信息。 在这种情况下，"**统计**" 按钮将处于活动状态。 您可以选择它以查看搜索统计信息，例如：

- 总结
- 顶部位置
- Queries

有关搜索统计信息的详细信息，请参阅[搜索统计](search-statistics.md)信息。

完成预览后，**预览**按钮将处于活动状态。 选择它可预览结果的样本子集。

## <a name="add-search-results-to-a-review-set"></a>将搜索结果添加到审阅集

当您准备收集和处理整个搜索结果时，您可以通过将其添加到审阅集来执行此操作。 有关详细信息，请参阅[将数据添加到审阅集](add-data-to-review-set.md)。

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>将非 Microsoft 365 数据添加到评审集

作为案例的集合过程的一部分，您还可以将非 Office 365 数据添加到审阅集，并与使用搜索工具收集的 Office 365 数据一起进行查看和分析。 添加非 Office 365 时，必须将其与案例中的特定保管人相关联。 有关详细信息，请参阅[将非 Microsoft 365 数据加载到评审集](load-non-Office-365-data-into-a-review-set.md)。
