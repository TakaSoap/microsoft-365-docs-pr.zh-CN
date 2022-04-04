---
title: Microsoft 365 Defender 与 Microsoft Sentinel 的集成
description: 使用 Microsoft Sentinel 作为 SIEM Microsoft 365 Defender事件和事件。
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
ms.openlocfilehash: 75aea706cdcb65752b673d32ccff968209ba74b7
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499436"
---
# <a name="microsoft-365-defender-integration-with-microsoft-sentinel"></a>Microsoft 365 Defender 与 Microsoft Sentinel 的集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Microsoft Sentinel Microsoft 365 Defender 预览版 (连接器) 所有 Microsoft 365 Defender 事件和警报信息发送给 Microsoft Sentinel，并保持事件同步。 

添加连接器后，Microsoft 365 Defender&mdash;事件包括从 Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365 和 Microsoft Defender for Cloud Apps 接收的所有关联警报、实体和相关信息&mdash;作为 SIEM) 数据的安全信息和事件管理流式传输至 Microsoft Sentin (el，从而提供使用 Microsoft Sentinel 执行会审和事件响应的上下文。 

进入 Microsoft Sentinel 后，事件将与 Microsoft 365 Defender 保持双向同步，从而可以利用 Microsoft 365 Defender 门户和 Azure 门户中的 Microsoft Sentinel 优势，以便进行事件调查和响应。

观看此简短概述，了解 Microsoft Sentinel Microsoft 365 Defender (4 分钟) 。

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


下面是它的工作原理。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender 和 Microsoft Sentinel 门户的事件数据流和共享" lightbox="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png":::

## <a name="next-steps"></a>后续步骤

1. 深入了解 Microsoft [Sentinel Microsoft 365 Defender集成。](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [连接数据从 Microsoft 365 Defender Microsoft Sentinel](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>另请参阅

- [事件概述Microsoft 365 Defender](incidents-overview.md)
- [使用 Microsoft Sentinel 调查事件](/azure/sentinel/tutorial-investigate-cases)
