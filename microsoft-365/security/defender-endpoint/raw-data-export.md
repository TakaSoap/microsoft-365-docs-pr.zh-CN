---
title: Stream Microsoft 365 Defender 事件
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c25ec8bc88a2714fb2f02ef8641c3eae700efe0
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730686"
---
# <a name="streaming-api"></a>流式处理 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>将高级搜寻事件流式传输至事件中心和/或 Azure 存储帐户。

Microsoft 365Defender 支持将高级搜寻提供的所有事件流式[处理到事件](../defender/advanced-hunting-overview.md)中心和/或[Azure 存储帐户](/azure/event-hubs/)。 [](/azure/event-hubs/)



## <a name="in-this-section"></a>本节内容

主题 | 说明
:---|:---
[将事件流式处理到 Azure 事件中心](raw-data-export-event-hub.md)| 了解如何在租户中启用流式处理 API，并配置 Microsoft 365 Defender 以将[高级](../defender/advanced-hunting-overview.md)搜寻流式传输至事件中心。
[将事件流式处理到 Azure 存储帐户](raw-data-export-storage.md)| 了解如何在租户中启用流式处理 API，并配置 Microsoft 365 Defender 以将[高级](../defender/advanced-hunting-overview.md)搜寻流式传输至 Azure 存储帐户。


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](../defender/advanced-hunting-overview.md)
- [Azure 事件中心文档](/azure/event-hubs/)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)
