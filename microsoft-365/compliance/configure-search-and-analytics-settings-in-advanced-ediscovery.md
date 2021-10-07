---
title: 配置搜索和分析设置 - Advanced eDiscovery
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
ms.custom: seo-marvel-mar2020
description: 配置Advanced eDiscovery适用于案例的所有审阅集的审核设置。 这包括用于分析和光学字符识别的设置。
ms.openlocfilehash: 65175950a430dd6b43cac207e16a17cf02d1bbbf
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153194"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>配置搜索和分析Advanced eDiscovery

您可以配置每个自定义Advanced eDiscovery的设置，以控制以下功能。

- 近似重复和电子邮件线程

- 主题

- 自动生成的审阅集查询

- 忽略文本

- 光学字符识别

如要为案例配置搜索和分析设置：

1. 在“**高级电子数据**”页面选择该案例。

2. 在“**设置**”选项卡上，点击“**搜索和分析**”下的“**选择**”。

   将显示"大小写设置"页。 在一种情况下，这些设置将应用于所有审阅集。

   ![为案例配置分析和搜索Advanced eDiscovery设置。](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>近似重复和电子邮件线程

在此部分中，你可以为重复检测、近重复检测和电子邮件线程设置参数。 有关详细信息，请参阅近[重复检测和](near-duplicate-detection-in-advanced-ediscovery.md)[电子邮件线程](email-threading-in-advanced-ediscovery.md)。

- **接近重复项/电子邮件线程：** 启用后，当您对审阅集内的数据运行分析时，重复检测、近重复检测和电子邮件线程将包含在工作流中。

- **文档和电子邮件相似性阈值：** 如果两个文档的相似性级别高于阈值，则两个文档将放入相同的近重复集。

- **最小/最大单词数：** 这些设置指定仅对至少具有最少单词数和最多单词数的文档执行近重复和电子邮件线程分析。

## <a name="themes"></a>主题

在此部分中，您可以设置主题的参数。 有关详细信息，请参阅 [主题](themes-in-advanced-ediscovery.md)。

- **主题：** 打开后，当您对审阅集中的数据运行分析时，主题群集作为工作流的一部分执行。

- **最大主题数：** 指定对审阅集内的数据运行分析时可生成的主题的最大数量。

- **在主题中包括数字：** 如果打开，则 (主题主题) 时将包含标识主题主题的数字。 

- **动态调整最大主题数：** 在某些情况下，审阅集可能没有足够的文档来生成所需数量的主题。 启用此设置时，高级电子数据展示会动态调整最大主题数，而不是尝试强制实施最大主题数。

## <a name="review-set-query"></a>审阅集查询

如果选中"分析后 **自动创建** 用于审阅保存的搜索"复选框，Advanced eDiscovery名为"审阅"的审阅集 **查询。** 

![用于审阅自动生成的查询。](../media/AeDForReviewQuery.png)

此查询基本上从审阅集筛选出重复项。 这样，你可以查看审阅集内的唯一项目。 本查询仅会对案例的审阅集运行分析时创建。 有关审阅集查询详细信息，请参阅查询 [审阅集内的数据](review-set-search.md)。

## <a name="ignore-text"></a>忽略文本

在某些情况下，某些文本会降低分析质量，例如，无论电子邮件内容如何，都会添加到电子邮件中的冗长免责声明。 如果你知道哪些是应忽略的文本，可以通过指定文本字符串以及文本排除分析功能（近似重复、电子邮件线程、主题和相关性）将其从分析中排除。 此外，还 (正则表达式) 正则表达式作为忽略的文本。

## <a name="optical-character-recognition-ocr"></a>光学字符识别 (OCR)

打开此设置后，OCR 处理将在图像文件上运行。 OCR 处理在下列情况下运行：

- 将保管 [人和非保管人数据源](non-custodial-data-sources.md) 添加到案例时。 将 OCR 应用于图像文件时，将在集合期间搜索这些文件中的文本。 OCR 处理在高级 [索引过程中](indexing-custodian-data.md) 执行。 OCR 仅在高级索引期间处理的项上运行。 例如，如果在高级索引过程中处理了部分索引或其他索引错误的大型 PDF 文件，则该文件也将应用 OCR。 换句话说，OCR 处理仅发生在高级索引过程中重新编制索引的文件上。 这意味着在某些情况下，保管人可能会添加到案例，但某些电子邮件附件不会针对 OCR 进行处理，因为在高级索引期间不会处理这些文件。

- 当来自其他数据源的内容 (未与保管人关联且添加到非托管数据源中的案例的内容) 添加到审阅集。

将数据添加到审阅集后，可以审阅、搜索、标记和分析图像文本。 可以在审阅集内所选图像文件的文本查看器中查看提取的文本。 有关详细信息，请参阅：

- [保管人数据的高级索引](indexing-custodian-data.md)

- [将搜索结果添加到审阅集](add-data-to-review-set.md#optical-character-recognition)

- [支持的图像文件类型](supported-filetypes-ediscovery20.md#image)
