---
title: 收集高级电子数据展示中案例的数据
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
description: 了解如何使用高级电子数据展示中的搜索工具在调查中确定要审阅的文档集。
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751261"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a>收集高级电子数据展示中案例的数据

一旦确定了与案例相关保管人和数据源，就该确定要深入探究的文档集了。 您可以使用高级电子数据展示中的搜索工具在 Microsoft 365 中识别来自当前位置和非查询位置的相关文档。

运行搜索后，您可以查看检索到的项目（如与搜索查询匹配项目最多的位置）的统计信息。 您还可以预览结果的子集。 确定要进一步检查的文档集后，可以将搜索结果添加到审阅集以收集和处理。

## <a name="create-a-search"></a>创建搜索

选择 **"搜索**"选项卡上的"新建搜索"将启动向导，引导您完成创建搜索。 若要详细了解如何创建搜索，请参阅 ["创建搜索"以收集数据](create-search-to-collect-data.md)。

创建搜索后，将显示包含详细信息的飞出页。 "**统计信息****"** 和"预览"按钮最初不可用，因为搜索尚未完成。 您可以在"搜索"选项卡上跟踪搜索 **进度** 。

## <a name="view-search-results-and-statistics"></a>查看搜索结果和统计信息

内容搜索有两个组件：统计信息 (估计) 预览。 当每个组件完成时，你将看到"搜索"选项卡上相应列中显示的状态从"已提交"更改为"**正在完成****"。**

完成搜索估计后，选择搜索以显示飞出页，其中将显示有关搜索结果的一些高级统计信息。 此时，" **统计信息"** 按钮将处于活动状态。 可以选择它以查看搜索统计信息，例如：

- 摘要
- 首要位置
- 查询

有关搜索统计信息详细信息，请参阅 [搜索统计信息](search-statistics-in-advanced-ediscovery.md)。

预览完成后 **，预览按钮** 将处于活动状态。 选择它可预览结果的样本子集。

## <a name="add-search-results-to-a-review-set"></a>将搜索结果添加到审阅集

准备好收集和处理搜索的整个结果后，可以通过将搜索结果添加到审阅集来完成。 有关详细信息，请参阅["将数据添加到审阅集"。](add-data-to-review-set.md)

## <a name="add-non-microsoft-365-data-to-a-review-set"></a>将非 Microsoft 365 数据添加到审阅集

作为案例收集过程的一部分，您还可以将非 Office 365 数据添加到审阅集，并查看和分析使用搜索工具收集的 Office 365 数据。 添加非 Office 365 时，必须将其与案例的特定保管人关联。 有关详细信息，请参阅将 [非 Microsoft 365 数据加载到审阅集](load-non-Office-365-data-into-a-review-set.md)。
