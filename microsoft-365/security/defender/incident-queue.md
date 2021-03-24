---
title: 确定 Microsoft 365 Defender 中事件的优先级
description: 了解如何在 Microsoft 365 Defender 中筛选事件队列中的事件
keywords: 事件, 队列, 概述, 设备, 标识, 用户, 邮箱, 电子邮件, 事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054898"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>确定 Microsoft 365 Defender 中事件的优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender



Microsoft 365 Defender 应用相关分析，将不同产品的相关警报和调查聚合到一个事件中。 Microsoft 365 Defender 还会触发有关活动的唯一警报，这些活动只有在 Microsoft 365 Defender 在整个产品和套件中具有端到端可见性时，才能标识为恶意活动。 此视图为安全运营分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。


“事件队列”显示在设备、用户和邮箱中标记的事件的集合。 它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。


![事件队列的图像](../../media/incidents-queue.png) 

默认情况下，Microsoft 365 安全中心中的队列会显示最近 30 天内看到的事件。 最近的事件位于列表顶部，以便你可以先看到它。

事件队列公开可自定义的列，可让你查看事件或包含的实体的不同特征。 这可以帮助您就要处理的事件的优先顺序做出明智决定。

为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。 这使您可以快速了解事件的范围。

例如： *多个源报告的多个终结点上的多阶段事件。*

> [!NOTE]
> 在推出自动事件命名之前已存在的事件不会更改其名称。

事件队列还公开了多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定重点关注特定方案或威胁。 在事件队列中应用筛选器可帮助确定需要立即关注的事件。 

## <a name="available-filters"></a>可用筛选器

### <a name="assigned-to"></a>分配到
你可以选择显示分配给你或由自动化处理警报的警报。

### <a name="categories"></a>类别
选择类别以专注于特定的策略、技术或看到的攻击组件。 

### <a name="classification"></a>分类
根据相关警报的集分类筛选事件。 值包括真警报、假警报或未设置。

### <a name="data-sensitivity"></a>数据敏感性
某些攻击主要针对容易泄露或有价值的数据。 通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。

>[!NOTE]
>仅适用于已启用 Microsoft 信息保护的情况。

### <a name="device-group"></a>设备组
按定义的设备组进行筛选。

### <a name="investigation-state"></a>调查状态
按自动调查的状态筛选事件。 

### <a name="multiple-categories"></a>多个类别 
可以选择仅查看映射到多个类别并因此可能导致更多损坏的事件。 

### <a name="multiple-service-sources"></a>多个服务源 
筛选以仅查看包含来自不同来源的警报的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。

### <a name="os-platform"></a>操作系统平台
按操作系统限制事件队列视图。

### <a name="service-sources"></a>服务源
通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。 

### <a name="severity"></a>Severity
事件的严重性表明它可以对资产产生的影响。 严重性越高，影响越大，通常需要最直接的关注。 

### <a name="status"></a>状态
可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。




## <a name="next-steps"></a>后续步骤
确定哪个事件需要最高优先级后，可继续对事件执行进一步的调查工作。
- [调查事件](investigate-incidents.md)


## <a name="see-also"></a>另请参阅
- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
