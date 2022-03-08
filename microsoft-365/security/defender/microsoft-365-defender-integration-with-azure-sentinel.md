---
title: Microsoft 365 Defender 与 Microsoft Sentinel 的集成
description: 使用 Microsoft Sentinel 作为适用于 Microsoft 365 Defender 事件和事件的 SIEM。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d0add9fe000966cdeb2ffc5ce23e4ba0690bbadb
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320279"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender 与 Microsoft Sentinel 的集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft Sentinel (预览版) 的 Microsoft 365 Defender 连接器将所有 Microsoft 365 Defender 事件和警报信息发送给 Microsoft Sentinel 并保持事件同步。 

添加连接器后，Microsoft 365 Defender&mdash; 事件（包括从 Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365 和 Microsoft Defender for Cloud Apps&mdash; 接收的所有关联警报、实体和相关信息）会作为安全信息和事件管理 (SIEM) 数据流式传输至 Microsoft Sentinel，从而为您提供使用 Microsoft Sentinel 执行会审和事件响应的上下文。 

进入 Microsoft Sentinel 后，事件将与 Microsoft 365 Defender 保持双向同步，让你可以利用 Azure 门户中 Microsoft 365 Defender 门户和 Microsoft Sentinel 的优势，以便进行事件调查和响应。

观看此有关 Microsoft Sentinel 与 Microsoft 365 Defender (的简短概述，) 。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


下面是它的工作原理。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender 和 Microsoft Sentinel 之间的事件数据流和共享。":::

## <a name="next-steps"></a>后续步骤

1. 深入了解 [Microsoft 365 Defender 与 Microsoft Sentinel 的集成](/azure/sentinel/microsoft-365-defender-sentinel-integration)。
2. [将数据从 Microsoft 365 Defender 连接到 Microsoft Sentinel](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>另请参阅

- [Microsoft 365 Defender 中的事件概述](incidents-overview.md)
- [使用 Microsoft Sentinel 调查事件](/azure/sentinel/tutorial-investigate-cases)
