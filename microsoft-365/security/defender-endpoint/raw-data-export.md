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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778193"
---
# <a name="streaming-api"></a><span data-ttu-id="1fbf4-104">流式处理 API</span><span class="sxs-lookup"><span data-stu-id="1fbf4-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1fbf4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1fbf4-105">**Applies to:**</span></span>
- [<span data-ttu-id="1fbf4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fbf4-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="1fbf4-107">将高级搜寻事件流式传输至事件中心和/或 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="1fbf4-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="1fbf4-108">Microsoft 365Defender 支持将高级搜寻提供的所有事件流式[处理到事件](../defender/advanced-hunting-overview.md)中心和/或[Azure 存储帐户](/azure/event-hubs/)。 [](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="1fbf4-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="1fbf4-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="1fbf4-109">In this section</span></span>

<span data-ttu-id="1fbf4-110">主题</span><span class="sxs-lookup"><span data-stu-id="1fbf4-110">Topic</span></span> | <span data-ttu-id="1fbf4-111">说明</span><span class="sxs-lookup"><span data-stu-id="1fbf4-111">Description</span></span>
:---|:---
[<span data-ttu-id="1fbf4-112">将事件流式处理到 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="1fbf4-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="1fbf4-113">了解如何在租户中启用流式处理 API，并配置 Microsoft 365 Defender 以将[高级](../defender/advanced-hunting-overview.md)搜寻流式传输至事件中心。</span><span class="sxs-lookup"><span data-stu-id="1fbf4-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="1fbf4-114">将事件流式处理到 Azure 存储帐户</span><span class="sxs-lookup"><span data-stu-id="1fbf4-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="1fbf4-115">了解如何在租户中启用流式处理 API，并配置 Microsoft 365 Defender 以将[高级](../defender/advanced-hunting-overview.md)搜寻流式传输至 Azure 存储帐户。</span><span class="sxs-lookup"><span data-stu-id="1fbf4-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1fbf4-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="1fbf4-116">Related topics</span></span>
- [<span data-ttu-id="1fbf4-117">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="1fbf4-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="1fbf4-118">Azure 事件中心文档</span><span class="sxs-lookup"><span data-stu-id="1fbf4-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="1fbf4-119">Azure 存储帐户文档</span><span class="sxs-lookup"><span data-stu-id="1fbf4-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
