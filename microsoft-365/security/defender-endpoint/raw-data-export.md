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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3e6d4df1c2c0f4934de1e8a54e8c1676aae230e3
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771617"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="1198d-104">原始数据流式处理 API</span><span class="sxs-lookup"><span data-stu-id="1198d-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1198d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1198d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1198d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1198d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="1198d-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="1198d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1198d-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1198d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="1198d-109">将高级搜寻事件流式传输至事件中心和/或 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="1198d-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="1198d-110">Defender for Endpoint 支持将高级搜寻提供的所有事件流式[](/azure/event-hubs/)[处理到事件](advanced-hunting-overview.md)中心和/或[Azure 存储帐户](/azure/event-hubs/)。</span><span class="sxs-lookup"><span data-stu-id="1198d-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="1198d-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="1198d-111">In this section</span></span>

<span data-ttu-id="1198d-112">主题</span><span class="sxs-lookup"><span data-stu-id="1198d-112">Topic</span></span> | <span data-ttu-id="1198d-113">说明</span><span class="sxs-lookup"><span data-stu-id="1198d-113">Description</span></span>
:---|:---
[<span data-ttu-id="1198d-114">将 Microsoft Defender for Endpoint 事件流式处理到 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="1198d-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="1198d-115">了解如何在租户中启用流式处理 API，并配置 Defender for Endpoint 以将 [高级搜寻](advanced-hunting-overview.md) 流式传输至事件中心。</span><span class="sxs-lookup"><span data-stu-id="1198d-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="1198d-116">Stream Defender for Endpoint 事件到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="1198d-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="1198d-117">了解如何在租户中启用流式处理 API，并配置 Defender for Endpoint 以将 [高级搜寻](advanced-hunting-overview.md) 流式传输至 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="1198d-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1198d-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="1198d-118">Related topics</span></span>
- [<span data-ttu-id="1198d-119">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="1198d-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1198d-120">Azure 事件中心文档</span><span class="sxs-lookup"><span data-stu-id="1198d-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="1198d-121">Azure 存储帐户文档</span><span class="sxs-lookup"><span data-stu-id="1198d-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)