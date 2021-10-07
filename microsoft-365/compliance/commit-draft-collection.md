---
title: 将草稿集合提交到审阅集中
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 创建并访问草稿集合后，可以提交到审阅集。 提交草稿集合时，收集的项目将添加到案例的审阅集中。 收集的项目在审阅集内后，可以分析、审阅和导出它们。
ms.openlocfilehash: 0d230f02f08b5a29b2c53ab20ff175f8c7db9ac6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173567"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a>将草稿集合提交到审阅集中Advanced eDiscovery

如果你对在草稿集合中收集的项目感到满意，并且已准备好分析、标记和审阅这些项目，可以在这种情况中向审阅集添加集合。 将草稿集合提交到审阅集时，收集的项目会从审阅集中的原始内容Microsoft 365复制到审阅集。 审阅集是 Microsoft 提供的安全Azure 存储 Microsoft 云中的位置。

## <a name="commit-a-draft-collection-to-a-review-set"></a>将草稿集合提交到审阅集中

1. In the Microsoft 365 合规中心， open the Advanced eDiscovery case， and then select the **Collections** tab to display a list of the collections in the case.

   ![一种情况下的集合列表。](../media/CommitDraftCollections1.png)

   > [!TIP]
   > "状态 `Estimated` "列中的值标识可添加到审阅集的草稿集合。 状态 `Committed` 表示集合已添加到审阅集。

2. 在 **"集合** "页上，选择要提交到审阅集的草稿集合。

3. 在飞出页面的底部，选择 **操作**  >  **编辑集合**。

4. 在编辑集合向导中，单击 **"下** 一步"，直到显示" **保存草稿或收集"** 页。

5. 配置以下设置：

   1. 选择 **"收集项目并添加到审阅集"。**

   2. 决定是否将集合添加到新的审阅 (，该审阅集是在提交) 或添加到现有审阅集之后创建的。 根据你的决定完成此部分。

   3. 配置其他集合设置：

       - **Teams和Yammer** 消息：选择此选项可以将对话线程添加到集合，该集合包含搜索查询在集合中返回的聊天项目。 这意味着将重新构造包含与搜索条件匹配的项目的聊天对话。 这允许你在来回对话的上下文中查看聊天项目。 有关详细信息，请参阅对话[线程Advanced eDiscovery。](conversation-review-sets.md)

       - **云附件**：选择此选项以在将集合结果添加到审阅集时包含新式附件或链接文件。 这意味着新式附件或链接文件的目标文件将添加到审阅集。

       - **SharePoint版本**：选择此选项可以按集合的版本限制和搜索参数启用 SharePoint 文档的所有版本的集合。 选择此选项将显著增加添加到审阅集的项目的大小。

   4. 配置设置以定义要添加到审阅集的集合规模：

      - **添加所有集合结果**：选择此选项可以将与集合的搜索条件匹配的所有项目添加到审阅集。

      - **添加集合结果的示例**：选择此选项以将集合结果的示例添加到审阅集，而不是添加所有结果。 如果选择此选项，请单击" **编辑示例参数** "并选择以下选项之一：

         - **基于置信** 度的示例：集合中的项目将添加到审阅集，由您设置的统计参数确定。 如果在采样结果时通常使用置信水平和间隔，请从下拉框中指定它们。 否则，请使用默认设置。

         - **随机示例**：根据搜索返回的项目总数指定百分比的随机选择，将集合中的项目添加到审阅集中。

6. 在 **"查看集合"** 页上，您可以查看在上一页上配置的集合设置。 如果要 **更改** 它们，请单击"编辑"。

7. 单击 **"提交** "创建草稿集合。 将显示一个页面，确认已创建集合。

## <a name="what-happens-after-you-commit-a-draft-collection"></a>提交草稿集合后会发生什么情况

将草稿集合提交到审阅集时，将发生以下情况：

- 如果创建了一个新的审阅集以将集合提交到该审阅集，则创建该审阅集并显示在案例的" **审阅集"** 选项卡上。 新审阅集的状态为 **"就绪"。** 此状态值表示已创建审阅集;这并不意味着集合已添加到审阅集。 将集合中的项目添加到审阅集的状态显示在"集合" **选项卡** 上。

- 再次运行集合搜索查询。 这意味着复制到审阅集的实际搜索结果可能不同于上次运行集合搜索时返回的估计结果。

- 搜索结果中的所有项目都从实时服务中的原始数据源复制，并复制到 Microsoft 云中的Azure 存储位置。

- 所有项目 (包括不在保管人或非保管人数据源中的内容和元数据 *)* 在名为深度索引) 的过程中对 (重新编制索引，以便审阅集内的所有数据在审查案例数据期间完全可搜索。 当您在案例调查期间搜索或筛选审阅集中的内容时，对集合中的内容重新建立索引会导致全面而快速的搜索。

- 当您SharePoint审阅 OneDrive集时，SharePoint和加密文件以及搜索结果中返回的附加了加密文件的文档和加密文件将被解密。 可以在审阅集内查看和查询解密的文件。 有关详细信息，请参阅解密[Microsoft 365电子数据展示工具。](ediscovery-decryption.md)

- 光学字符识别 (OCR) 功能从图像中提取文本，并包括图像文本以及已添加到审阅集的内容。 有关详细信息，请参阅本文 [中的光学](#optical-character-recognition) 字符识别部分。

- 成功完成提交后，"集合"选项卡上 **的状态列的值** 将更改为 `Committed` 。

## <a name="optical-character-recognition"></a>光学字符识别

将集合提交到审阅集时，Advanced eDiscovery 中的光学字符识别 (OCR) 功能会自动从图像中提取文本，并包括图像文本以及添加到审阅集中的内容。 可以在审阅集内所选图像文件的文本查看器中查看提取的文本。 通过此功能，你可以对图像中的文本进行进一步审阅和分析。 OCR 支持松散文件、电子邮件附件和嵌入图像。 有关 OCR 支持的图像文件格式列表，请参阅[高级电子数据展示中受支持的文件类型](supported-filetypes-ediscovery20.md#image)。

必须针对在高级电子数据展示中创建的每个案例启用 OCR 功能。 有关详细信息，请参阅配置 [搜索和分析设置](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。
