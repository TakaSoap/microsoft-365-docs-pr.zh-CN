---
title: 查看Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解对话中的对话重建功能Advanced eDiscovery (对话线程) ，以重新构建、查看和导出 Microsoft Teams 和 Yammer 对话。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 66427fef6b3a112e0166582ea6598a865f9e64d809a3b9ff2b36c82dd8bd5f50
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53880462"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>对话线程Advanced eDiscovery

即时消息是一种在大型受众中提问、分享想法或快速沟通的便捷方式。 由于即时消息平台（如 Microsoft Teams 和 Yammer 组）成为企业协作的核心，组织必须评估其电子数据展示工作流如何处理这些新的通信和协作形式。

对话重建功能Advanced eDiscovery旨在帮助您识别上下文内容并生成不同的对话视图。 此功能使您可以高效快速地查看完整的即时消息对话 (也称为线程) 对话，这些对话是在 Microsoft Teams等平台中生成的。

通过对话重建，可以使用内置功能来重新构造、审阅和导出线程对话。 使用Advanced eDiscovery对话重建来：

- 保留对话中所有邮件的唯一消息级别元数据。

- 收集与搜索结果相关的上下文消息。

- 查看、注释和修订线程对话。

- 导出单个消息或线程对话

## <a name="terminology"></a>术语

下面是帮助您开始使用对话重建的一些定义。

- **邮件：** 表示对话中最小的单元。 邮件的大小、结构和元数据可能会有所不同。

- **对话：** 表示一个或多个邮件的分组。 跨不同的应用程序，对话可能以不同方式表示。 在某些应用程序中，有一个显式操作会导致答复现有邮件。 对话是此用户操作显式形成的。 例如，下面是当前频道对话的屏幕截图Microsoft Teams。

   ![Microsoft Teams频道对话](../media/threadedchat.png)

   在其他应用 (例如 Teams) 中的 1xN 聊天消息，没有正式的回复链，而是消息在单个线程中显示为"消息的平面流"。 在这些类型的应用中，对话从特定时间发生的一组消息中推断得出。 这种消息"软分组" (而不是回复链) 表示有关特定关注主题的"来回"对话。

## <a name="step-1-create-a-draft-collection"></a>步骤 1：创建草稿集合

确定相关保管人和内容位置后，可以创建搜索以查找潜在相关内容。 在"**集合**"选项卡上的Advanced eDiscovery，可以通过单击"新建集合"并遵循向导来创建集合。 若要了解如何创建集合、生成搜索查询和预览搜索结果，请参阅 [创建草稿集合](create-draft-collection.md)。

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>步骤 2：将草稿集合提交到审阅集

查看并完成集合中的搜索查询后，可以将搜索结果添加到审阅集。 当您将搜索结果添加到审阅集时，原始数据将复制到Azure 存储区域以方便审阅和分析过程。 有关向审阅集添加搜索结果的信息，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md)。

将对话中的项目添加到审阅集时，可以使用线程对话选项从包含与集合的搜索条件匹配的项目的对话中收集上下文消息。 选择线程对话选项后，可能会发生以下情况：

  ![对话检索](../media/messagesandconversations.png)

1. 使用关键字和日期范围查询，搜索返回了邮件 *3 的命中*。 此消息属于大型对话的一部分，如 *CRC1 所示*。

2. 当你将数据添加到审阅集并启用对话检索选项时，Advanced eDiscovery返回并收集 *CRC1* 中的其他项目。

3. 将项目添加到审阅集后，你可以查看来自 *CRC1* 的所有单个邮件。

若要启用线程对话选项，请参阅 [将草稿集合提交到审阅集](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)。

## <a name="step-3-review-and-export-threaded-conversations"></a>步骤 3：查看和导出线程对话

处理内容并添加到审阅集后，您可以开始查看审阅集内的数据。 根据内容是添加到标准审阅集还是对话审阅集，审阅功能会有所不同。

### <a name="reviewing-conversations-in-a-standard-review-set"></a>查看标准审阅集内的对话

在标准审阅集，处理邮件并显示为单个项目，类似于邮件存储在邮箱文件夹中的方式。 在此工作流中，每封邮件都作为单独的项目进行处理。 因此，按线索设置的摘要和导出选项在标准审阅集内不可用。

  ![标准审阅集](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>查看对话审阅集内的对话

在对话审阅集内，将各个消息进行线程处理，并呈现为对话。 这样，你可以查看和导出上下文对话。

  ![对话审阅集](../media/ConversationRSOptions.PNG)

以下各节介绍审阅和导出对话审阅集内的对话。

#### <a name="reviewing-conversations"></a>查看对话

在对话审阅集内，可以使用以下选项促进审阅过程。

- **按对话分组：** 将同一对话中的邮件分组在一起，以帮助用户简化和加快审阅过程。

- **摘要视图：** 显示线程对话。 在此视图中，您可以查看整个对话，还可以访问每封邮件的元数据。

   - 查看单个邮件的元数据

   - 下载单个邮件

- **文本视图：** 提供整个对话的提取文本。

- **批注视图：** 允许你标记对话的线程视图。 对话中所有邮件共享同一批注文档。

- **标记：** 查看审阅集内的对话时，可以通过单击"编码"面板中的"标记"面板 **来查看和应用** 标记。

- **重新运行对话转换：** 将邮件添加到对话审阅集时，将自动运行转换作业以创建线程摘要并注释视图。 如果对话重建作业失败，可以通过单击"操作"> **审阅集创建** 对话 PDF 来重新运行此作业。

#### <a name="exporting-conversations"></a>导出对话

在对话审阅集内，可以设置以下选项来导出对话：

![导出对话选项](../media/export.png)

1. 元数据选项：
   - **加载文件：** 每个单独的邮件、电子邮件和文档都包含元数据。 对话中每条消息有一行。
   - **标记：** 来自审阅过程的标记包含在元数据文件中。 对话中的邮件共享相同的标记。

2. 对话选项：
   - **对话文件：** 导出对话文件时，批注视图将转换为 PDF 文件并下载到导出文件夹。 一个对话文件中的消息指向同一对话文件的 PDF 版本。
   - **单个聊天消息：** 导出单个邮件时，对话中每个唯一的邮件都导出为独立项目。 以与邮箱中相同的格式导出文件。 对于特定对话，您将收到多个 .msg 文件。

     > [!NOTE]
     > 如果对会话文件应用了批注，这些批注将不会传输到各个邮件。

3. 其他选项：
   - **生成所有导出内容的文本文件：** 为从审阅集导出的每个对话生成一个文本文件。
   - **将导出的内容替换为修订的 PDF：** 如果在审阅过程中生成修订的对话文件，则这些文件在导出过程中可用。 可以通过不选择此选项) 来决定是仅导出本机文件 (，还是将本机文件替换为已修订版本的本机文件 (，方法为选择此选项) （导出为 PDF 文件）。

## <a name="more-information"></a>更多信息

若要详细了解如何查看 Advanced eDiscovery中的情况数据，请参阅以下文章：

- [查看案例数据](view-documents-in-review-set.md)
- [分析事例数据](analyzing-data-in-review-set.md)
- [导出事例数据](exporting-data-ediscover20.md)
