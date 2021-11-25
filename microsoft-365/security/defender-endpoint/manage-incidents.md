---
title: 管理 Microsoft Defender 终结点事件
description: 通过分配事件、更新其状态或设置其分类来管理事件。
keywords: 事件， 管理， 分配， 状态， 分类， 真警报， 假警报
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71d453bbc5b94b4685a65c1074244ae98b16448c
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166802"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>管理 Microsoft Defender 终结点事件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

管理事件是每个网络安全操作的重要组成部分。 可以通过从"事件"队列或"事件管理"窗格中选择事件 **来管理事件**。 


从事件队列中 **选择事件将** 打开"事件管理"窗格，您可以在其中打开事件页面了解详细信息。


![事件管理窗格的图像。](images/atp-incidents-mgt-pane-updated.png)

你可以为自己分配事件、更改状态和分类、重命名或注释它们以跟踪其进度。

> [!TIP]
> 为了一目了然，事件名称会基于警报属性自动生成，如受影响的终结点数量、受影响的用户、检测源或类别。 借助此功能，可以快速了解事件的范围。
>
> 例如： *多个源报告的多个终结点上的多阶段事件。*
>
> 在推出自动事件命名之前已存在的事件将保留其名称。
>


![事件详细信息页面的图像。](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>分配事件
如果尚未分配事件，可以选择"分配给 **我** "将事件分配给自己。 执行此操作时，假定所有权不仅限于事件，而且还针对与之关联的所有警报。

## <a name="set-status-and-classification"></a>设置状态和分类
### <a name="incident-status"></a>事件状态
可通过在调查期间更改事件的状态来为事件分类（例如“活动”或“已解决”）。 这可帮助你整理和管理团队对事件的响应方式。

例如，SoC 分析师可以审阅当天的紧急 **活动** 事件，并决定将其分配给自己进行调查。

或者，如果事件已修复，SoC 分析师可能会将事件设置为"已解决"。 

### <a name="classification"></a>分类
可以选择不设置分类，也可以决定指定事件为真实/误报事件。 这样做有助于团队查看模式并从中了解相关信息。

### <a name="add-comments"></a>添加备注
可以添加备注并查看有关事件的历史事件，以便了解以前对其所做的更改。

每当对警报进行更改或添加备注时，都会在“备注”和“历史记录”部分进行记录。

添加的备注会立即显示在窗格中。



## <a name="related-topics"></a>相关主题
- [事件队列](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [查看和组织事件队列](view-incidents-queue.md)
- [调查事件](investigate-incidents.md)
