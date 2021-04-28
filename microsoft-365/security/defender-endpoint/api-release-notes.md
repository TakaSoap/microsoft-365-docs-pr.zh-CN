---
title: Microsoft Defender for Endpoint API 发行说明
description: 对 Microsoft Defender for Endpoint API 集进行更新的发行说明。
keywords: Microsoft Defender for Endpoint API 发行说明， mde， API， 适用于终结点的 Microsoft Defender API， 更新， 注释， 发布
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 7bae413028a0add7e5288e52bc3184e30f319c46
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073834"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="a0c19-104">Microsoft Defender for Endpoint API 发行说明</span><span class="sxs-lookup"><span data-stu-id="a0c19-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="a0c19-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a0c19-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a0c19-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a0c19-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a0c19-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a0c19-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a0c19-108">以下信息列出了对 Microsoft Defender 终结点 API 的更新以及更新的日期。</span><span class="sxs-lookup"><span data-stu-id="a0c19-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="a0c19-109">RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：</span><span class="sxs-lookup"><span data-stu-id="a0c19-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest"></a><span data-ttu-id="a0c19-110">发行说明 - 最新到最旧</span><span class="sxs-lookup"><span data-stu-id="a0c19-110">Release notes - newest to oldest</span></span>

### <a name="10022021"></a><span data-ttu-id="a0c19-111">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="a0c19-111">10.02.2021</span></span>

- <span data-ttu-id="a0c19-112">添加了新 API： [批量更新警报](batch-update-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c19-112">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="a0c19-113">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="a0c19-113">25.01.2021</span></span>

- <span data-ttu-id="a0c19-114">更新了高级搜寻 [API](run-advanced-query-api.md) 的速率限制，从每分钟 15 个请求更新为 45 个。</span><span class="sxs-lookup"><span data-stu-id="a0c19-114">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="a0c19-115">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="a0c19-115">21.01.2021</span></span>

- <span data-ttu-id="a0c19-116">添加了新 API： [通过 标记 查找设备](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c19-116">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="a0c19-117">添加了新 API： [导入指示器](import-ti-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c19-117">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="a0c19-118">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="a0c19-118">03.01.2021</span></span>

- <span data-ttu-id="a0c19-119">更新了警报证据：添加了 ***detectionStatus** _*__、parentProcessFilePath_\*_ 和 _ *_parentProcessFileName_*\* 属性。</span><span class="sxs-lookup"><span data-stu-id="a0c19-119">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="a0c19-120">更新 [了 Alert 实体](alerts.md)：添加了 ***一个检测器Id*** 属性。</span><span class="sxs-lookup"><span data-stu-id="a0c19-120">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="a0c19-121">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="a0c19-121">15.12.2020</span></span>

- <span data-ttu-id="a0c19-122">更新 [了 Device](machine.md) 实体：添加了 ***IpInterfaces*** 列表。</span><span class="sxs-lookup"><span data-stu-id="a0c19-122">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="a0c19-123">请参阅 [列出设备](get-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c19-123">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="a0c19-124">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="a0c19-124">04.11.2020</span></span>

- <span data-ttu-id="a0c19-125">添加了新 API： [设置设备值](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c19-125">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="a0c19-126">更新 [了 Device](machine.md) 实体：添加了 ***deviceValue*** 属性。</span><span class="sxs-lookup"><span data-stu-id="a0c19-126">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="a0c19-127">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="a0c19-127">01.09.2020</span></span>

- <span data-ttu-id="a0c19-128">添加了选项以使用相关证据展开 Alert 实体。</span><span class="sxs-lookup"><span data-stu-id="a0c19-128">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="a0c19-129">请参阅 [列出警报](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c19-129">See [List Alerts](get-alerts.md).</span></span>
