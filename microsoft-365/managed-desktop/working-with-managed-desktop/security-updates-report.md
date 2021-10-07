---
title: Windows 安全更新报告
description: 说明此报告中显示的信息
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 747cfe06ef69703a9baf7bd360935c364b3c7832
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213177"
---
# <a name="windows-security-updates-report"></a>Windows 安全更新报告

此报告概述了给定设备Windows更新的部署Microsoft 托管桌面进度。 在每个安全更新发布周期开始时，Microsoft 托管桌面活动设备状态的所有设备拍摄快照，并设置其部署目标为该总体的95%。 此图显示与平均发布日期相比所选发布日期Microsoft 托管桌面进度。 当我们关注活动群体时，还可以透视此报表以显示你的活动 + **同步** 和 **不同步** 设备填充。 可以通过更改可用筛选器查看早期版本的部署进度，但设备级别详细信息仅适用于当前版本。 图后表中可查看的设备信息也可导出以用于脱机分析。

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="显示左上方一段时间的更新安装进度的报告、右上方的筛选器（带生成报告的按钮）以及底部报告详细信息表":::

通常，Microsoft 会每月的第二个星期二发布安全更新程序，尽管这些更新可在其他时间根据需要发布。 每个版本都会添加已知安全漏洞的重要更新。 Microsoft 托管桌面确保其 95% 的活动设备每月更新最新的可用安全更新。 当在其他时间发布安全更新以紧急应对新威胁时，Microsoft 托管桌面以类似方式部署这些更新。 我们使用以下条款对安全更新版本的状态进行分类： 

- **当前**：运行当月发布的更新的设备 
- **上** 一个 ：运行上个月发布的更新的设备 
- **较** 旧：运行上个月之前发布的任何安全更新的设备 

"旧"类别中应该 **只有一些** 设备。 一个较大或不断增加的较早群体可能指示你应报告给一个Microsoft 托管桌面问题，以便我们可以进行调查。 