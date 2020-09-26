---
title: 配置搜索和分析设置-高级电子数据展示
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
ms.custom: seo-marvel-mar2020
description: 配置适用于案例中所有审阅集的高级电子数据展示设置。 这包括分析和光学字符识别的设置。
ms.openlocfilehash: dfacab79f635a817b127614f524d00b0297981fb
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277082"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>在高级电子数据展示中配置搜索和分析设置

您可以为每个高级电子数据展示事例配置设置来控制以下功能。

- 临近重复项和电子邮件线程

- 主题

- 自动生成的审阅集查询

- 忽略文本

- 光学字符识别

为事例配置搜索和分析设置：

1. 在 " **高级电子数据展示** " 页上，选择该大小写。

2. 在 " **设置** " 选项卡上的 " **搜索 & 分析**" 下，单击 " **选择**"。

   将显示 "事例设置" 页。 这些设置适用于所有审阅集。

   ![为高级电子数据展示事例配置分析和搜索设置](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>临近重复项和电子邮件线程

在此部分中，您可以设置重复检测、接近重复检测和电子邮件线程的参数。 有关详细信息，请参阅 [接近重复检测](near-duplicates.md) 和 [电子邮件线程](email-threading.md)。

- **接近重复项/电子邮件线程：** 当您对评审集中的数据运行分析时，如果启用此功能，则重复检测、临近重复检测和电子邮件线程将作为工作流的一部分包括在内。

- **文档和电子邮件相似性阈值：** 如果两个文档的相似性级别高于阈值，则两个文档都放在相同的临近重复集内。

- **最小/最大单词数：** 这些设置指定仅在至少包含最少单词数和最大单词数的文档上执行接近重复项和电子邮件线程分析。

## <a name="themes"></a>主题

在本节中，您可以设置主题的参数。 有关详细信息，请参阅 [主题](themes-in-advanced-ediscovery.md)。

- **主题：** 如果启用此设置，则当您对评审集中的数据运行分析时，主题群集将作为工作流的一部分执行。

- **主题的最大数量：** 指定在对评审集中的数据运行分析时可生成的最大主题数。

- **主题中包含数字：** 启用后，在生成主题时将包含标识主题) 的号码 (。 

- **动态调整主题的最大数量：** 在某些情况下，审阅集中可能没有足够的文档来生成所需数量的主题。 启用此设置后，高级电子数据展示将动态调整主题的最大数量，而不是尝试强制实施主题的最大数量。

## <a name="review-set-query"></a>审阅集查询

如果选中了 " **自动创建用于查看已保存搜索的分析** " 复选框，则高级电子数据展示 autogenerates 审核集查询名 **为 "审阅"。** 

![For 审阅自动生成查询](../media/AeDForReviewQuery.png)

此查询基本上筛选出评审集的重复项。 这使您可以查看评审集中的唯一项。 仅当在案例中运行评审集的分析时，才会创建此查询。 有关详细信息，请参阅关于查看集查询的详细信息，请参阅 [在审阅集中查询数据](review-set-search.md)。

## <a name="ignore-text"></a>忽略文本

某些情况下，某些文本会降低分析质量，例如，无论电子邮件的内容如何，都将添加到电子邮件中的冗长免责声明。 如果您知道应忽略的文本，可以通过指定文本字符串和分析功能 (接近于重复项、电子邮件线程、主题和相关性) 应将文本排除，从而将其从分析中排除。 使用正则表达式 (RegEx) 也支持忽略的文本。 

## <a name="optical-character-recognition-ocr"></a>光学字符识别 (OCR) 

启用此设置后，将在图像文件上运行 OCR 处理。 OCR 处理在以下情况下运行：

- 将保管人和 [非 custodial 数据源](non-custodial-data-sources.md) 添加到一个事例时。 在高级索引过程中执行 OCR 处理。 这意味着将在集合搜索中返回与搜索条件匹配的图像文件中的文本。

- 如果来自其他数据源 (的内容未与管理员关联，并将其添加到了非 custodial 数据源中的事例) 则会将添加到审阅集。

将数据添加到审阅集后，可以对图像文本进行审阅、搜索、标记和分析。 您可以在审阅集中的选定图像文件的文本查看器中查看提取的文本。 有关详细信息，请参阅：

- [保管人数据的高级索引](indexing-custodian-data.md)

- [将搜索结果添加到审阅集](add-data-to-review-set.md#optical-character-recognition)

- [受支持的图像文件类型](supported-filetypes-ediscovery20.md#image)
