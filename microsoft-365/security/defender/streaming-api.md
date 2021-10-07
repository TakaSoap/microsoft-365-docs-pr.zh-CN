---
title: 流Microsoft 365 Defender事件
description: 了解如何配置 Microsoft 365 Defender 以将高级搜寻事件流式传输至事件中心或 Azure 存储帐户
keywords: 原始数据导出， 流式 API， API， 事件中心， Azure 存储， 存储帐户， 高级搜寻， 原始数据共享
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c6c3cedffb1b827d441d37cc8beb53b20f3521f2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190397"
---
# <a name="streaming-api"></a>Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>将高级搜寻事件流式传输至事件中心和/或 Azure 存储帐户。

Microsoft 365 Defender通过高级搜寻流式处理[事件到事件](../defender/advanced-hunting-overview.md)中心和/或[](/azure/event-hubs/) [Azure 存储帐户](/azure/event-hubs/)。

有关流式Microsoft 365 Defender API 有关详细信息，请参阅[视频](https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga)。

## <a name="in-this-section"></a>本节内容

主题 | 说明
:---|:---
[将事件流式处理到 Azure 事件中心](streaming-api-event-hub.md)| 了解如何在租户中启用流式处理 API，并配置Microsoft 365 Defender[将高级](../defender/advanced-hunting-overview.md)搜寻流式传输至事件中心。
[将事件流式处理到 Azure 存储帐户](streaming-api-storage.md)| 了解如何在租户中启用流式处理 API，Microsoft 365 Defender将[高级](advanced-hunting-overview.md)搜寻流式传输至 Azure 存储帐户。
[支持的事件类型](supported-event-types.md) | 了解流式处理 API 支持哪些高级搜寻事件类型。


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](../defender/advanced-hunting-overview.md)
- [Azure 事件中心文档](/azure/event-hubs/)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)
