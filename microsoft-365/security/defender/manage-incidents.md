---
title: 在 Microsoft 365 Defender 中管理事件
description: 了解如何分配、更新状态
keywords: 事件, 事件, 警报, 相关警报, 分配, 更新, 状态, 管理, 分类, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760059"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中管理事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

事件管理对于确保包含和解决威胁至关重要。

在快速启动 Microsoft  365 安全中心&事件>事件或事件管理事件 (security.microsoft.com) 。 [](https://security.microsoft.com) 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列示例":::

以下是管理事件的方法：

- 更改事件名称
- 添加事件标记。
- 将事件分配给用户帐户
- 解决它们 
- 设置其分类和确定
- 添加注释。

可以从事件的"管理事件 **"窗格中** 管理事件。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的&quot;管理事件&quot;窗格示例":::

可以从以下位置的"管理 **事件"链接显示** 此窗格：

- 事件队列中事件的属性窗格。
- **事件的** 摘要页。

在调查时，若要将警报从一个事件移动到另一个事件，也可以从"警报"选项卡进行移动，从而创建包含所有相关警报的较大或较小的事件。

## <a name="edit-the-incident-name"></a>编辑事件名称

根据警报属性（如受影响的终结点数、受影响的用户数、检测源或类别）自动为事件分配名称。 这使您可以快速了解事件的范围。 例如： *多个源报告的多个终结点上的多阶段事件。*

可以从"管理事件"窗格上的" **事件名称** "字段中 **编辑事件** 名称。

> [!NOTE]
> 推出自动事件命名功能之前已存在的事件将保留其名称。

## <a name="add-incident-tags"></a>添加事件标记

可以将自定义标记添加到事件，例如，标记一组具有共同特征的事件。 稍后可以筛选包含特定标记的所有事件的事件队列。

开始键入时，您可以选择从所选标记列表进行选择。

## <a name="assign-incidents"></a>分配事件

如果尚未分配事件，可以选择"分配给 **"并指定** 用户帐户。 这样做将分配事件的所有权以及与其关联的所有警报。

## <a name="resolve-incident"></a>解决事件

如果事件已修复，请选择"解决 **事件** "以将切换开关向右移动。 请注意，解决事件还会解决与事件相关的所有链接和活动警报。

未解决的事件显示为"活动 **"。**

## <a name="set-the-classification-and-determination"></a>设置分类和确定

事件分类是真正的警报还是假警报，从"分类"字段 **进行** 配置。 

如果这是真正的警报，则还应使用"确定"字段指定 **威胁的类型。** 指定威胁类型可帮助安全团队查看威胁模式，并采取行动保护组织抵御威胁模式。 

## <a name="add-comments"></a>添加备注

可以使用"注释"字段向事件添加 **多个** 注释。 每个注释将添加到事件的历史事件中。 You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.
