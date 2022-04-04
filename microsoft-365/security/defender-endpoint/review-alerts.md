---
title: 查看 Microsoft Defender for Endpoint 中的警报
description: 查看警报信息，包括可视化警报情景和链每个步骤的详细信息。
keywords: 事件， 事件， 计算机， 设备， 用户， 警报， 警报， 调查， 图形， 证据
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: 91cd06188a8337f3d0df0b9c67d7c98e389e4351
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466732"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>查看 Microsoft Defender for Endpoint 中的警报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-managealerts-abovefoldlink)。

Microsoft Defender for Endpoint 中的警报页面通过组合与所选警报相关的攻击信号和警报，为警报提供完整的上下文，以构建详细的警报情景。

对影响组织的警报快速会审、调查和采取有效措施。 了解触发它们的原因，及其从一个位置的影响。 有关详细信息，请在此概述中了解。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>警报入门

在 Defender for Endpoint 中选择警报的名称将让你访问其警报页面。 在警报页面上，所有信息都将在所选警报的上下文中显示。 每个警报页面包含 4 个部分：

1. **警报标题** 显示警报的名称，并提醒你哪个警报启动了当前调查，无论你在页面上选择了什么内容。
2. [**受影响的资产**](#review-affected-assets) 列出了受此警报影响的设备和用户的卡片，可单击这些卡片了解详细信息和操作。
3. 警报 **情景** 通过树视图显示与警报相关的所有实体。 当你首次登录所选警报的页面时，标题中的警报将是焦点。 警报情景中的实体可展开且可单击，通过允许您在警报页面上下文中立即采取措施来提供其他信息并加快响应速度。 使用警报情景开始调查。 在调查 [Microsoft Defender for Endpoint 中的警报中了解如何](/microsoft-365/security/defender-endpoint/investigate-alerts)操作。
4. 详细信息 **窗格** 将首先显示所选警报的详细信息，以及与此警报相关的详细信息和操作。 如果在警报情景中选择任何受影响的资产或实体，详细信息窗格将更改为提供所选对象的上下文信息和操作。

记下警报的检测状态。

- 已阻止：已避免尝试的可疑操作。 例如，文件未写入磁盘或已执行。

  :::image type="content" source="images/detstat-prevented.png" alt-text="显示威胁防护的页面" lightbox="images/detstat-prevented.png":::

- 已阻止：已执行可疑行为，然后阻止。 例如，进程已执行，但由于它随后呈现了可疑行为，因此进程已终止。

  :::image type="content" source="images/detstat-blocked.png" alt-text="显示威胁阻止的页面" lightbox="images/detstat-blocked.png":::

- 检测到：检测到攻击，并且可能仍处于活动状态。

  :::image type="content" source="images/detstat-detected.png" alt-text="显示威胁检测的页面" lightbox="images/detstat-detected.png":::

然后，还可以在警报的详细信息窗格中查看自动调查详细信息，查看已采取的操作，并阅读警报的说明，了解建议的操作。

:::image type="content" source="images/alert-air-and-alert-description.png" alt-text="突出显示警报说明和自动调查部分的详细信息窗格" lightbox="images/alert-air-and-alert-description.png":::

当警报打开时，详细信息窗格中提供的其他信息包括 MITRE 技术、源和其他上下文详细信息。

## <a name="review-affected-assets"></a>查看受影响的资产

在受影响的资源部分中选择设备或用户卡片将在详细信息窗格中切换到设备或用户的详细信息。

- **对于设备**，详细信息窗格将显示有关设备本身的信息，如域、操作系统和 IP。 Active alerts and the logged on users on that device are also available. 可以通过隔离设备、限制应用执行或运行防病毒扫描来立即采取措施。 或者，你可以收集调查包、启动自动调查，或从设备的角度转到设备页面进行调查。

   :::image type="content" source="images/device-page-details.png" alt-text="选择设备时的详细信息窗格" lightbox="images/device-page-details.png":::

- **对于用户**，详细信息窗格将显示详细的用户信息，如用户的 SAM 名称和 SID，以及此用户执行的登录类型以及任何与该用户相关的警报和事件。 您可以选择" *打开用户页面* "以从该用户的角度继续调查。

   :::image type="content" source="images/user-page-details.png" alt-text="选择用户时的详细信息窗格" lightbox="images/user-page-details.png":::

## <a name="related-topics"></a>相关主题

- [查看和组织事件队列](view-incidents-queue.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
