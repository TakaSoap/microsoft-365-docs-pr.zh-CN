---
title: 将搜索结果添加到审阅集
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
ms.custom:
- seo-marvel-apr2020
description: 了解如何将搜索结果或这些搜索结果的示例添加到Advanced eDiscovery审阅集。
ms.openlocfilehash: bce0301e7045eeb0dd5c42f8a119d56649120a11
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175583"
---
# <a name="add-search-results-to-a-review-set"></a>将搜索结果添加到审阅集

当您对搜索结果感到满意并且已准备好查看和分析这些搜索结果时，您可以将它们添加到案例的审阅集。 将原始数据复制到审阅集还通过为您提供高级分析工具（如主题检测、近重复检测和电子邮件线程标识）来简化审阅和分析过程。 您还可以将来自非Microsoft 365数据源的数据添加到审阅集，以便除了从审阅集收集的数据之外，您还可以查看Microsoft 365。

当您将搜索结果添加到审阅集 ("审阅集"选项卡上的"审阅集"选项卡上 () ，将发生以下情况：

- 再次运行搜索。 这意味着复制到审阅集的实际搜索结果可能不同于上次运行搜索时返回的估计结果。

- 搜索结果中的所有项目都从实时服务中的原始数据源复制，并复制到 Microsoft 云中的Azure 存储位置。

- 所有 (包括内容和元数据) 重新建立索引，以便审阅集内的所有数据在审阅案例数据期间完全可搜索。 当您在案例调查期间搜索审阅集内的数据时，对数据重新建立索引会导致全面而快速的搜索。

- 使用 [Microsoft](encryption.md) 加密技术加密并附加到搜索结果中返回的电子邮件的文件在将电子邮件和附加文件添加到审阅集时将解密。 可以在审阅集内查看和查询解密的文件。 您必须分配有 RMS 解密角色，以将解密的电子邮件附件添加到审阅集。 有关详细信息，请参阅解密[Microsoft 365电子数据展示工具。](ediscovery-decryption.md)

若要将数据添加到审阅集，请单击"搜索"选项卡上的搜索，然后单击飞出页面上的"添加要 **审阅** 的结果集"。

您可以添加到现有审阅集或创建新的审阅集。  如果添加到新的审阅集，请指定名称，然后单击 **"添加"** 以显示飞出页面。

![选择审阅集并配置集合选项。](../media/AeD_AddToReviewSet.png)

向审阅集添加数据是一个长期运行流程。 此过程包括从 Microsoft 365 (中的原始数据源（例如，从邮箱和网站) ）收集项目，将它们复制到 Azure 存储 位置 (此复制过程也称为 *"ingestion*) "，然后对项目重新建立索引。 您可以通过监视"要审阅的数据"列中的状态来跟踪"作业"选项卡或"搜索"**选项卡** 上的进度。 完成审阅集处理后，单击案例的"审阅集"选项卡，然后单击审阅集以开始筛选、审阅、标记和导出审阅集数据的过程。

## <a name="define-options-to-scope-your-collection-for-review"></a>定义用于确定要审阅的集合范围的选项

当您将搜索内容添加到现有或新的审阅集时，您具有以下用于收集要审阅的内容的选项：

- **包含** SharePoint (beta) 的版本：使用此选项可以按集合的版本限制和搜索参数启用 SharePoint 文档的所有版本的集合。 选择此选项将显著增加添加到审阅集的项目的大小。

- **对话检索选项**：为线程对话启用添加到审阅集的项目，以帮助查看来回对话上下文中的内容。 有关详细信息，请参阅 [审阅高级 eDiscovery 中的对话](conversation-review-sets.md)。

- **启用新式附件检索**：使用此选项在集合中包括新式附件或链接文件，以便进一步查看。 有关与新式附件相关的可搜索属性详细信息，请参阅文档[Advanced eDiscovery。](document-metadata-fields-in-Advanced-eDiscovery.md)

## <a name="add-a-sample-to-a-review-set"></a>向审阅集添加示例

如果您希望在将搜索结果添加到审阅集之前更彻底地验证搜索结果，您可以将搜索结果示例添加到审阅集，而不是添加所有内容。

若要将示例添加到审阅集，请单击"搜索"选项卡上的搜索，然后单击飞出页面上的"示例"。 在" **采样参数"** 页上，选择下列选项之一：

- **可信度百分比** 和 **置信区间百** 分比 - 添加到审阅集的项目将由您设置的统计参数确定。 如果在采样结果时通常使用置信水平和间隔，请从下拉框中指定它们。 否则，请使用默认设置。

- **随机示例百** 分比 - 添加到审阅集的项目基于搜索返回的项目总数的指定百分比的随机选择。

选择并配置以上选项之一后，选择要将示例添加到的审阅集，然后单击"发送 **"。** 同样，通过监视"要审阅的数据"列中的状态，可以跟踪"作业"选项卡或"搜索"**选项卡** 上的进度。

## <a name="optical-character-recognition"></a>光学字符识别

将搜索结果添加到审阅集时，Advanced eDiscovery 中的光学字符识别 (OCR) 功能会自动从图像中提取文本，并包括图像文本以及添加到审阅集的数据。 可以在审阅集内所选图像文件的文本查看器中查看提取的文本。 通过此功能，你可以对图像中的文本进行进一步审阅和分析。 OCR 支持松散文件、电子邮件附件和嵌入图像。 有关 OCR 支持的图像文件格式列表，请参阅[高级电子数据展示中受支持的文件类型](supported-filetypes-ediscovery20.md#image)。

必须针对在高级电子数据展示中创建的每个案例启用 OCR 功能。 有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。
