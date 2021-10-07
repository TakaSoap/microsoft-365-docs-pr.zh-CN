---
title: 查看和组织事件队列
ms.reviewer: ''
description: 查看事件列表，并了解如何应用筛选器来限制列表并获取更集中的视图。
keywords: 视图， 组织， 事件， 聚合， 调查， 队列， ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e287f9a4713ba0ad96fd4b1b7f51e0fee948ec28
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207675"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>查看并组织 Microsoft Defender for Endpoint 事件队列

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

**"事件队列**"显示从网络中设备标记的事件集合。 它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。

默认情况下，队列显示最近 30 天内看到的事件，最新事件显示在列表顶部，帮助你首先查看最近事件。

有几种选项可供选择以自定义事件队列视图。 

在顶部导航上，你可以：
- 自定义列以添加或删除列 
- 修改每页要查看的项目数
- 选择要按页显示的项目
- 批量选择要分配的事件 
- 在页面之间导航
- 应用筛选器

![事件队列的图像。](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>对事件队列进行排序和筛选
可以应用以下筛选器来限制事件列表，并获取更集中的视图。

### <a name="severity"></a>Severity

事件严重性 | 说明
:---|:---
高 </br> (红色)  | 通常与高级永久性威胁和 APT (相关的) 。 这些事件表明，由于设备可造成严重损坏，因此存在高风险。
中型 </br> (橙色)  | 很少在组织中观察到的威胁，例如异常注册表更改、可疑文件的执行和观察到的攻击阶段典型行为。
低 </br> (黄色)  | 与流行恶意软件和黑客工具关联的威胁，这些威胁不一定表示针对组织的高级威胁。
信息 </br> (灰色)  | 信息事件可能被视为对网络没有危害，但可以跟踪。

## <a name="assigned-to"></a>分配到
可选择通过选择分配给任何人/分配给你的人来筛选列表。

### <a name="category"></a>类别
根据网络安全终止链所处于的阶段的说明对事件进行分类。 此视图可帮助威胁分析员根据上下文确定要部署的优先级、紧急程度和相应的响应策略。

### <a name="status"></a>状态
可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。

### <a name="data-sensitivity"></a>数据敏感性
使用此筛选器显示包含敏感度标签的事件。

## <a name="incident-naming"></a>事件命名

为了一目了然地了解事件的范围，事件名称将基于警报属性自动生成，如受影响的终结点数量、受影响的用户、检测源或类别。

例如： *多个源报告的多个终结点上的多阶段事件。*

> [!NOTE]
> 在推出自动事件命名之前已存在的事件将保留其名称。


## <a name="see-also"></a>另请参阅
- [事件队列](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [管理事件](manage-incidents.md)
- [调查事件](investigate-incidents.md)

