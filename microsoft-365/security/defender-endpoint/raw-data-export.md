---
title: Stream Microsoft Defender for Endpoint 事件
description: 了解如何配置 Microsoft Defender for Endpoint 以将高级搜寻事件流式传输至事件中心或 Azure 存储帐户
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
ms.custom: api
ms.openlocfilehash: b7a4002e25cf5ad956f60b477a15ee5e5f2d395a
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167714"
---
# <a name="raw-data-streaming-api"></a>原始数据流式处理 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)。

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>将高级搜寻事件流式处理到事件中心和/或 Azure 存储帐户

Microsoft Defender for Endpoint 支持通过高级搜寻流式[](/azure/event-hubs/)处理[事件到事件](../defender/advanced-hunting-overview.md)中心和/或[Azure 存储帐户](/azure/storage/common/storage-account-overview)。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4ga]

## <a name="in-this-section"></a>本节内容

主题|说明
:---|:---
[将 Microsoft Defender for Endpoint 事件流式处理到 Azure 事件中心](raw-data-export-event-hub.md)|了解如何在租户中启用流式处理 API，并配置 Defender for Endpoint 以将 [高级搜寻](advanced-hunting-overview.md) 流式传输至事件中心。
[Stream Defender for Endpoint 事件到 Azure 存储帐户](raw-data-export-storage.md)|了解如何在租户中启用流式处理 API，并配置 Defender for Endpoint 以将 [高级搜寻](advanced-hunting-overview.md) 流式传输至 Azure 存储帐户。

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [Azure 事件中心文档](/azure/event-hubs/)
- [Azure 存储帐户文档](/azure/storage/common/storage-account-overview)