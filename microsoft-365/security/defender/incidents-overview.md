---
title: Microsoft 365 Defender 中的事件概述
description: 调查在设备、用户和邮箱中看到的事件。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
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
ms.openlocfilehash: 6dd13c5f83d05be3c77e5f84608fb6aa5172d9a4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500928"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的事件概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 希望体验 Microsoft 365 Defender？ 你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>


事件基于相关警报。 当网络中出现恶意事件或活动时，将创建警报。 个别警报提供有关进行中攻击的有价值的线索。 但是，攻击通常使用各种矢量和技术来实施入侵。 将单个线索分在一起可能充满挑战且耗时。

此简短视频概述了 Microsoft 365 Defender 中的事件。
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

事件是关联警报的集合，这些警报是攻击的一部分。 Microsoft 365 Defender 会自动聚合网络中不同设备、用户和邮箱实体中的恶意和可疑事件。 将相关警报分组到事件中，使安全防御者可以全面查看攻击。 

例如，安全防御者可以看到攻击的开始位置、使用了什么策略以及攻击已进入网络多远。 他们还可以查看攻击的范围，如受影响的设备、用户和邮箱数量、影响严重，以及受影响实体的其他详细信息。

如果启用，Microsoft 365 Defender 可以通过自动化和人工智能自动调查和解决个别警报。 安全防御者还可以执行其他修正步骤，直接从事件视图解决攻击。 

最近 30 天的事件显示在事件队列中。 从此处，安全防御者可以了解哪些事件应基于风险级别和其他因素确定优先级。 

安全防御者还可以重命名事件、将其分配给各个分析员、对事件进行分类和添加标记，以提供更好的且更加自定义的事件管理体验。



## <a name="see-also"></a>另请参阅
- [确定事件优先级](incident-queue.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)