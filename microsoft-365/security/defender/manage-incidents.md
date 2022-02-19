---
title: 管理事件Microsoft 365 Defender
description: 了解如何分配、更新状态
keywords: 事件， 事件， 分析， 响应， 警报， 相关警报， 分配， 更新， 状态， 管理， 分类， microsoft， 365， m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: b9cc3e0ab911515d010b1a6e7feaac5cff8aed51
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62903935"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>管理事件Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

事件管理对于确保命名、分配和标记事件以优化事件工作流中的时间并更快包含和解决威胁至关重要。

可以在快速启动 Microsoft 365 Defender 门户&事件>**事件** (security.microsoft.com [)](https://security.microsoft.com)。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列的示例。" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

以下是管理事件的方法：

- [编辑事件名称](#edit-the-incident-name)
- [添加事件标记](#add-incident-tags)
- [将事件分配给用户帐户](#assign-an-incident)
- [解决这些事件](#resolve-an-incident)
- [设置其分类并确定](#set-the-classification-and-determination)
- [添加注释](#add-comments)

可以从事件的“**管理事件**”窗格管理事件。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件&quot;管理事件&quot;窗格的示例。" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

可以从以下位置的"管理 **事件"链接显示** 此窗格：

- 事件队列中事件的属性窗格。
- **事件的** 摘要页。

如果想将警报从一个事件移动到另一个事件，则还可以从"警报"选项卡进行移动，从而创建包含所有相关警报的较大或较小的事件。

## <a name="edit-the-incident-name"></a>编辑事件名称

Microsoft 365 Defender根据警报属性（如受影响的终结点数、受影响的用户数、检测源或类别）自动分配名称。 借助此功能，可以快速了解事件的范围。 例如： *多个源报告的多个终结点上的多阶段事件。*

可以从"管理事件"窗格上的" **事件名称** "字段中 **编辑事件** 名称。

> [!NOTE]
> 在推出自动事件命名功能之前已存在的事件将保留其名称。

## <a name="add-incident-tags"></a>添加事件标记

可以向事件添加自定义标记，例如，标记一组具有共同特征的事件。 以后可以对包含特定标记的所有事件的事件队列进行筛选。

开始键入时，可以选择从以前使用的标记和所选标记的列表中选择。

## <a name="assign-an-incident"></a>分配事件

如果尚未分配事件，可以选择"分配到"框并指定用户帐户。 若要重新分配事件，请删除当前分配帐户，选择帐户名称旁边的"x"，然后选择" **分配到"** 框。 分配事件的所有权会为与其关联的所有警报分配相同的所有权。

通过筛选事件队列，您可以获取分配给您的事件列表。 

1. 从事件队列中，选择"筛选器 **"**。
2. 在" **事件分配"** 部分，清除 **"全选** "，然后选择 **"分配给我"**。
3. 选择 **"应用**"，然后关闭" **筛选器"** 窗格。

然后，您可以将生成的 URL 保存为书签，以快速查看分配给您的事件列表。

## <a name="resolve-an-incident"></a>解决事件

如果事件已修复，请选择"解决 **事件** "以将切换开关向右移动。 请注意，解决事件还会解决与事件相关的所有链接和活动警报。

未解决的事件显示为"活动 **"**。

## <a name="set-the-classification-and-determination"></a>设置分类和确定

事件分类是真正的警报还是假警报，从"分类"字段 **进行** 配置。 

如果这是真正的警报，则还应使用"确定"字段指定 **威胁的类型。** 指定威胁类型可帮助安全团队查看威胁模式，并采取措施以保护组织免受威胁。 

## <a name="add-comments"></a>添加备注

可以使用"注释"字段向事件添加 **多个** 注释。 每个备注都会添加到事件的历史事件中。 You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.

## <a name="next-steps"></a>后续步骤

对于新事件，请开始 [调查](investigate-incidents.md)。

对于进程内事件， [请继续调查](investigate-incidents.md)。

对于已解决的事件，执行 [事后评审](first-incident-post.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [确定事件优先级](incident-queue.md)
- [调查事件](investigate-incidents.md)
