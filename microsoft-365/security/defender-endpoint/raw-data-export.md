---
title: Stream Microsoft Defender for Endpoint 事件
description: 了解如何配置 Microsoft Defender ATP 以将高级搜寻事件流式传输至事件中心或 Azure 存储帐户
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055354"
---
# <a name="raw-data-streaming-api"></a>原始数据流式处理 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>将高级搜寻事件流式传输至事件中心和/或 Azure 存储帐户。

Defender for Endpoint 支持将高级搜寻提供的所有事件流式[](https://docs.microsoft.com/azure/event-hubs/)[处理到事件](advanced-hunting-overview.md)中心和/或[Azure 存储帐户](https://docs.microsoft.com/azure/event-hubs/)。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>本节内容

主题 | 说明
:---|:---
[将 Microsoft Defender for Endpoint 事件流式处理到 Azure 事件中心](raw-data-export-event-hub.md)| 了解如何在租户中启用流式处理 API，并配置 Defender for Endpoint 以将 [高级搜寻](advanced-hunting-overview.md) 流式传输至事件中心。
[Stream Defender for Endpoint 事件到 Azure 存储帐户](raw-data-export-storage.md)| 了解如何在租户中启用流式处理 API，并配置 Defender for Endpoint 以将 [高级搜寻](advanced-hunting-overview.md) 流式传输至 Azure 存储帐户。


## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [Azure 事件中心文档](https://docs.microsoft.com/azure/event-hubs/)
- [Azure 存储帐户文档](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
