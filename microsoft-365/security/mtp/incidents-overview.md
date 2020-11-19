---
title: Microsoft 365 Defender 中的事件概述
description: 调查在设备、用户和邮箱中看到的事件。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357607"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的事件概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 想要体验 Microsoft 365 Defender？ 您可以 [在实验室环境中对其进行评估](https://aka.ms/mtp-trial-lab) ，也可以 [在生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。
>


事件基于相关警报。 当网络中出现恶意事件或活动时，将创建警报。 各个警报提供有关现有攻击的有价值的线索。 但是，攻击通常采用各种不同的矢量和技术来发动入侵。 将各个线索 Piecing 在一起可能会非常困难且耗时。

此简短视频提供了 Microsoft 365 Defender 中的事件概述。
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

事件是构成攻击情景的相关警报的集合。 在网络中的不同设备、用户和邮箱实体中找到的恶意事件和可疑事件会自动由 Microsoft 365 Defender 进行聚合。 将相关警报分组到事件中可使安全 defenders 全面的攻击视图。 

例如，安全 defenders 可以查看攻击的启动位置、使用的策略以及攻击已进入网络的程度。 他们还可以看到攻击的范围，如受影响的设备、用户和邮箱的数量、影响的严重性以及受影响的实体的其他详细信息。

如果启用此功能，则 Microsoft 365 Defender 可以通过自动化和人工智能自动调查和解决各个警报。 安全 defenders 还可以执行其他补救步骤，以便从事件视图中直接解决攻击。 

来自最近30天的事件显示在事件队列中。 在此，安全 defenders 可以根据风险级别和其他因素查看应优先考虑的事件。 

安全 defenders 还可以将事件重命名、将其分配给各个分析人员、分类并将标记添加到事件中，以实现更好更好的自定义事件管理体验。



## <a name="see-also"></a>另请参阅
- [确定事件优先级](incident-queue.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
