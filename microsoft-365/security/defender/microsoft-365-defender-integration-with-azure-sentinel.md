---
title: Microsoft 365Defender 与 Azure Sentinel 集成
description: 使用 Azure Sentinel 作为 SIEM Microsoft 365 Defender 事件和事件。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
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
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782917"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365Defender 与 Azure Sentinel 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

Azure Sentinel (预览版 Microsoft 365 Defender 连接器) 将所有 Microsoft 365 Defender 事件和警报信息发送到 Azure Sentinel，并保持事件同步。 

添加连接器后，Microsoft 365 Defender 事件（包括从 Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Office 365 和 Microsoft Cloud App Security 接收的所有关联警报、实体和相关信息）会作为安全信息和事件管理 (SIEM) 数据流式处理到 &mdash; Azure Sentinel，从而提供使用 Azure Sentinel 执行会审和事件响应的上下文。 &mdash; 

进入 Azure Sentinel 后，事件将与 Microsoft 365 Defender 保持双向同步，从而让你可以利用 azure 门户中 Microsoft 365 安全中心和 Azure Sentinel 的优势，以便进行事件调查和响应。

下面是它的工作原理。

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Microsoft 365 Defender 和 Azure Sentinel 之间的事件数据流和共享":::

## <a name="next-steps"></a>后续步骤

1. 更深入地了解 Defender Microsoft 365 [Azure Sentinel 集成](/azure/sentinel/microsoft-365-defender-sentinel-integration)。
2. [连接从 Microsoft 365 Defender 到 Azure Sentinel 的数据](/azure/sentinel/connect-microsoft-365-defender)。

## <a name="see-also"></a>另请参阅

- [Microsoft 365 Defender 中的事件概述](incidents-overview.md)
- [使用 Azure Sentinel 调查事件](/azure/sentinel/tutorial-investigate-cases)
