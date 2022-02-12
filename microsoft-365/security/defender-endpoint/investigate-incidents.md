---
title: 调查 Microsoft Defender for Endpoint 中的事件
description: 查看关联警报、管理事件和查看警报元数据，帮助你调查事件
keywords: 调查， 事件， 警报， 元数据， 风险， 检测来源， 受影响的设备， 模式， 相关
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2a297813fbde94499f2d239627be6c33c153e8b0
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765104"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>调查 Microsoft Defender for Endpoint 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


调查影响网络的事件，了解这些事件的含义，并整理证据以解决这些问题。

调查事件时，你将看到：

- 事件详细信息
- 事件注释和操作
- 选项卡 (警报、设备、调查、证据、图形) 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUV]

## <a name="analyze-incident-details"></a>分析事件详细信息

单击事件以查看"事件 **"窗格**。 选择 **"打开事件页面** "，查看事件详细信息和相关信息 (警报、设备、调查、证据、图形) 。

![事件详细信息的图像1。](images/atp-incident-details.png)

### <a name="alerts"></a>警报

你可以调查警报，并查看它们在事件中是如何链接在一起的。 根据以下原因，将警报分组为事件：

- 自动调查 - 自动调查在调查原始警报时触发了链接警报
- 文件特征 - 与警报关联的文件具有相似的特征
- 手动关联 - 用户手动链接警报
- 代理时间 - 在特定时间范围内在同一设备上触发警报
- 同一文件 - 与警报关联的文件完全相同
- 同一 URL - 触发警报的 URL 完全相同

![警报选项卡的图像，包含事件详细信息页面，显示警报在事件中链接在一起的原因。](images/atp-incidents-alerts-reason.png)

还可以管理警报并查看警报元数据以及其他信息。 有关详细信息，请参阅 [调查警报](investigate-alerts.md)。

### <a name="devices"></a>设备

还可以调查属于给定事件或与给定事件相关的设备。 有关详细信息，请参阅调查 [设备](investigate-machines.md)。

![事件详细信息页中的"设备"选项卡的图像。](images/atp-incident-device-tab.png)

### <a name="investigations"></a>调查

选择 **"** 调查"以查看系统为响应事件警报而启动的所有自动调查。

![事件详细信息页面中"调查"选项卡的图像。](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a>浏览证据

Microsoft Defender for Endpoint 自动调查警报中所有事件支持的事件和可疑实体，从而自动响应和有关重要文件、流程、服务等的信息。

分析的每个实体将被标记为已感染、已修复或可疑。

![事件详细信息页中证据选项卡的图像。](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a>可视化关联的网络安全威胁

Microsoft Defender for Endpoint 将威胁信息聚合到事件中，以便你可以查看来自各种数据点的模式和相关。 可以通过事件图查看此类关联。

### <a name="incident-graph"></a>事件图

此 **Graph** 网络攻击的情景。 例如，它显示入口点是什么，哪个指示符在哪个设备上观察到了泄露或活动。 等。

![事件图的图像。](images/atp-incident-graph-tab.png)

你可以单击事件图上的圆圈来查看恶意文件的详细信息、关联的文件检测、全球有多少实例，以及在你的组织中是否观测到它，如果是，则查看实例数。

![事件详细信息的图像。](images/atp-incident-graph-details.png)

## <a name="related-topics"></a>相关主题

- [事件队列](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [调查 Microsoft Defender for Endpoint 中的事件](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [管理 Microsoft Defender 终结点事件](/microsoft-365/security/defender-endpoint/manage-incidents)
