---
title: 在 Microsoft 威胁防护中确定事件的优先级
description: 了解如何在 Microsoft 威胁防护中确定事件队列中事件的优先级
keywords: 事件, 队列, 概述, 设备, 标识, 用户, 邮箱, 电子邮件, 事件
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 90f7aaf7eb4425dadeb27699654656c86d2b6263
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087293"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>在 Microsoft 威胁防护中确定事件的优先级

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft 威胁防护应用相关性分析，将来自不同产品的所有相关警报和调查汇总到一个事件中。 鉴于 Microsoft 威胁防护在整个产品和产品套件中具有的端到端可见性，Microsoft 威胁防护还会针对仅识别为“恶意”的活动触发唯一警报。 通过执行此操作，Microsoft 威胁防护可以描述更详尽的攻击事件，使安全操作分析人员能够理解和处理整个组织中的复杂威胁。


“事件队列”**** 显示在设备、用户和邮箱中标记的事件的集合。 它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。


![事件队列的图像](../../media/incidents-queue.png) 

默认情况下，Microsoft 365 安全中心中的队列显示最近 30 天看到的事件，最新事件显示在列表的顶部，方便用户首先查看最新事件。

事件队列会公开可自定义的列，可让你深入了解事件或所含实体的不同特征，从而帮助你就待处理事件的优先级做出明智的决策。 

事件队列中还会显示多个筛选选项，应用这些选项后，可以选择大范围扫描环境中的所有现有事件，也可以决定专注于特定的情形或威胁。 在事件队列中应用筛选器可帮助确定需要立即关注的事件。 

## <a name="available-filters"></a>可用筛选器

### <a name="status"></a>状态
可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。

### <a name="severity"></a>严重性
事件的严重性表明了它可能对资产产生的影响。 严重性越高，影响越大，通常需要最直接的关注。 

### <a name="assigned-to-owner"></a>分配给（所有者）
可选择通过选择分配给任何人/分配给你的人来筛选列表。

### <a name="multiple-alerts"></a>多个警报 
筛选以仅查看包含多个警报的事件。 这可能表示攻击更为复杂或在杀伤链中进行了攻击。 


### <a name="multiple-service-sources"></a>多个服务源 
筛选以仅显示包含来自不同来源（Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP）的警报的事件
### <a name="service-sources"></a>服务源
通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。 

### <a name="multiple-categories"></a>多个类别 
可选择仅显示已映射到杀伤链的多个类别，并可能导致更严重损坏的事件。 

### <a name="categories"></a>类别
选择特定类别，专注于杀伤链中的特定步骤

### <a name="data-sensitivity"></a>数据敏感性
某些攻击主要针对容易泄露或有价值的数据。 通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。

>[!NOTE]
>仅适用于已启用 Microsoft 信息保护的情况。


## <a name="next-steps"></a>后续步骤
确定哪个事件需要最高优先级后，可继续对事件执行进一步的调查工作。
- [调查事件](investigate-incidents.md)


## <a name="related-topics"></a>相关主题
- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
