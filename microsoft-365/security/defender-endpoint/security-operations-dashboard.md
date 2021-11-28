---
title: Microsoft Defender 安全中心安全操作仪表板
description: 使用仪表板识别处于风险中的设备，跟踪服务状态，并查看有关设备和警报的统计信息和信息。
keywords: 仪表板， 警报， 新， 正在进行， 已解决， 风险， 处于风险中的设备， 感染， 报告， 统计信息， 图表， 图形， 运行状况， 活动恶意软件检测， 威胁类别， 类别， 密码窃取程序， 勒索软件， 攻击， 威胁， 低严重性， 活动恶意软件
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bf0eb7b210ccb033e47b86b45a5f4dec00e9d795
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61160472"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Microsoft Defender 安全中心安全操作仪表板

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)。

安全 **操作仪表板** 是显示终结点检测和响应功能的地方。 它提供了发现检测位置的简要概述，并突出显示了需要响应操作的地方。

仪表板显示以下项的快照：

- 活动警报
- 处于风险之中的设备
- 传感器运行状况
- 服务运行状况
- 每日设备报告
- 主动自动调查
- 自动调查统计信息
- 处于风险之中的用户
- 可疑活动

![安全操作仪表板的图像。](images/atp-sec-ops-dashboard.png)

你可以浏览和调查警报和设备，以快速确定网络中是否、何处以及何时发生可疑活动，以帮助你了解它们出现的上下文。

从 **安全操作仪表板** 中，你将看到聚合事件，以便于识别设备上的重要事件或行为。 还可以深入到粒度事件和低级别指示器。

它还具有可单击的磁贴，可直观提示组织的整体运行状况。 每个磁贴将打开相应概述的详细视图。

## <a name="active-alerts"></a>活动警报

你可以从磁贴查看最近 30 天内网络的活动警报的个数。 警报分为"**新建"和**"**正在进行"。**

![单击每个切片或严重性以查看过去 30 天内的警报列表。](images/active-alerts-tile.png)

每个组进一步细分为相应的警报严重性级别。 单击每个警报圈内的警报数，以查看该类别的队列的已排序视图 **("** 新建"或"正在进行) "。 

有关详细信息，请参阅 [警报概述](alerts-queue.md)。

每行包括警报严重性类别和警报的简短说明。 你可以单击警报以查看其详细视图。 有关详细信息，请参阅调查  [适用于终结点的 Microsoft Defender](investigate-alerts.md) 警报 [和警报概述](alerts-queue.md)。

## <a name="devices-at-risk"></a>处于风险之中的设备

此磁贴显示活动警报数最高的设备列表。 每个设备的警报总数在设备名称旁的圆圈中显示，然后按严重性级别进一步分类磁贴 (将鼠标悬停在每个严重性栏上以查看其标签) 。

!["处于风险中的设备"图块显示警报数最高的设备列表，以及警报严重性的细目。](images/devices-at-risk-tile.png)

单击设备名称以查看有关该设备的详细信息。 有关详细信息，请参阅调查 [Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)。

还可以单击磁贴 **顶部的**"设备"列表，直接转到"设备"列表（按活动警报数排序）。 有关详细信息，请参阅调查 [Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)。

## <a name="devices-with-sensor-issues"></a>具有传感器问题的设备

" **具有传感器问题的设备** "磁贴提供有关单个设备向 Microsoft Defender for Endpoint 服务提供传感器数据的能力的信息。 它报告需要关注的设备数，并帮助你识别有问题的设备。

![具有传感器问题的设备图块。](images/atp-tile-sensor-health.png)

有两个状态指示器提供有关未正确报告给服务的设备数量的信息：

- **错误配置：** 这些设备可能部分向 Microsoft Defender for Endpoint 服务报告传感器数据，并且可能有需要更正的配置错误。
- **非** 活动：在过去一个月内停止向 Microsoft Defender for Endpoint 服务报告超过七天的设备。

当你单击任何组时，你将定向到设备列表，根据你的选择进行筛选。 有关详细信息，请参阅检查[传感器状态和](check-sensor-status.md)[调查设备](investigate-machines.md)。

## <a name="service-health"></a>服务运行状况

服务 **运行状况** 磁贴会通知服务是否处于活动状态或是否有问题。

!["服务运行状况"磁贴显示服务的整体指示器。](images/status-tile.png)

有关服务运行状况详细信息，请参阅 [检查 Microsoft Defender 终结点服务运行状况](service-status.md)。

## <a name="daily-devices-reporting"></a>每日设备报告

" **每日设备报告** "磁贴显示一个条形图，表示过去 30 天内每天报告的设备数。 将鼠标悬停在图形上的个别条形上，查看每天报告的具体设备数。

![每日设备报告磁贴的图像。](images/atp-daily-devices-reporting.png)

## <a name="active-automated-investigations"></a>主动自动调查

你可以从"活动自动调查"磁贴查看最近 30 天内网络中自动 **调查的个数** 。 调查分为"挂起 **操作"、"****等待设备"** 和"**正在运行"。**

![活动自动调查的一些信息。](images/atp-active-investigations-tile.png)

## <a name="automated-investigations-statistics"></a>自动调查统计信息

此图块显示最近七天内与自动调查相关的统计信息。 它显示完成的调查数、成功修正调查的数量、启动调查所花费的平均待定时间、修正警报的平均时间、调查的警报数以及从典型手动调查保存的自动化小时数。 

![自动调查统计信息的图像。](images/atp-automated-investigations-statistics.png)

你可以单击自动 **调查**、**修正** 调查和调查的警报以导航到按相应类别筛选的"调查"页面。 这样，你可以查看上下文中调查的详细说明。

## <a name="users-at-risk"></a>处于风险之中的用户

磁贴显示具有最活跃警报的用户帐户列表，以及在高、中或低警报上看到的警报数。 

![处于风险中的用户帐户图块显示警报数最高的用户帐户列表以及警报严重性的细目。](images/atp-users-at-risk.png)

单击用户帐户以查看有关用户帐户的详细信息。 有关详细信息，请参阅 [调查用户帐户](investigate-user.md)。

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-belowfoldlink)。

## <a name="related-topics"></a>相关主题

- [了解适用于终结点的 Microsoft Defender 门户](use.md)
- [门户概述](portal-overview.md)
- [查看威胁&漏洞管理仪表板](tvm-dashboard-insights.md)
- [查看威胁分析仪表板，采取建议的缓解操作](threat-analytics.md)
