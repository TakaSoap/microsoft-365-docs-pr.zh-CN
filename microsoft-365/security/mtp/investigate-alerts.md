---
title: 调查 Microsoft 365 Defender 中的警报
description: 调查跨设备、用户和邮箱看到的警报。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
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
ms.technology: m365d
ms.openlocfilehash: c4a67a6b0df9308e9e61733a951a5016fa69c082
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50928686"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>调查 Microsoft 365 Defender 中的警报

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

警报是所有事件的基础，指示环境中出现恶意或可疑事件。 警报通常是更广泛的攻击的一部分，并提供有关事件的线索片段。

在 Microsoft 365 Defender 中，相关警报聚合在一起以形成事件。 事件将始终提供攻击的更广泛的上下文，但是，当需要深入分析时，调查警报可能非常有价值。 



## <a name="using-alert-pages-in-investigations"></a>在调查中使用警报页面

从任何事件页面的"警报"选项卡中，选择警报将您带到各个警报页面。 警报页面由三个部分组成：受影响的资产、警报情景和详细信息窗格。

![示例警报页面的图像](../../media/new-alert-page2.png)

在整个警报页面中，可以选择任何实体旁边的三点 (**...) ，** 以便你可以查看可用的操作，如打开特定资产页面或执行特定的修正步骤。

### <a name="analyze-affected-assets"></a>分析受影响的资产
"受影响的资产"部分列出了受此警报影响的邮箱、设备和用户。 选择任意资产卡会向详细信息侧窗格填充信息，包括涉及资产的其他警报（如果有）。


### <a name="trace-an-alerts-role-in-the-alert-story"></a>跟踪警报情景中的警报角色
警报情景在进程树视图中显示与警报相关的所有资产或实体。 标题中的警报是首次登录所选警报的页面时聚焦的警报。 警报情景中的资源可展开且可单击。 它们通过允许您在警报页面上下文中采取措施来提供其他信息并加快响应速度。 

> [!NOTE]
> 警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。

### <a name="view-more-alert-information-in-the-details-pane"></a>在详细信息窗格中查看更多警报信息

细节窗格首先显示所选警报的详细信息，以及相关详细信息和操作。 如果在警报情景中选择任何受影响的资产或实体，详细信息窗格将发生更改，以提供所选对象的上下文信息和操作。

选择感兴趣的实体后，详细信息窗格将发生更改，以显示有关所选实体类型的信息、可用时的历史信息以及直接从警报页面对此实体采取措施的选项。

### <a name="manage-alerts"></a>管理警报

调查完警报后，可以返回到开始使用的警报，将警报状态标记为"已解决"，然后将其分类为"False 警报"或"真警报"。 对警报进行分类有助于调整产品，以提供更多真实警报和更少的假警报。

> [!NOTE]
> 通过标记管理警报的一种方法。 Microsoft Defender for Office 365 的标记功能正在逐步推出，目前处于预览阶段。 <br>
> 目前，修改的标记名称仅适用于更新后 *创建的* 警报。 修改之前生成的通知不会反映更新的标记名称。 


## <a name="manage-the-unified-alert-queue"></a>管理统一警报队列

选择 Microsoft 365 安全中心导航窗格中&警报"下的"警报"，可进入统一警报队列。 本部分中将显示来自不同 Microsoft 安全解决方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft 365 Defender）的警报。 

![示例警报页面的图像](../../media/unified-alert-queue.png)

警报队列显示网络中标记的警报列表。 默认情况下，队列显示最近 30 天内看到的警报。 最新警报显示在列表顶部，有助于你先查看最新警报。

> [!NOTE]
> 在启动时，统一警报队列将只有 7 天的 Microsoft Defender for Office 365 警报可用。 随着时间的推移，队列将继续构建。 如果需要在启动统一警报队列之前对警报进行会审，请使用安全与合规 [中心中的警报队列](https://protection.office.com/viewalerts)。


在顶部导航上，您可以：

- 应用筛选器
- 自定义列以添加或删除列
- 导出数据

您还可以根据不同的条件筛选警报：

- Severity
- 状态
- 类别
- 检测源
- Policy
- 影响的资产
- 第一个活动
- 最后一次活动


若要开始调查事件，请阅读调查[Microsoft 365 Defender](investigate-incidents.md)中的事件
## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
