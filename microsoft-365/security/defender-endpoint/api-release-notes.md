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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ec7adcc153d4c6bedfb1984951acad7a401cbd55
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788807"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="ab4cc-104">Microsoft Defender for Endpoint API 发行说明</span><span class="sxs-lookup"><span data-stu-id="ab4cc-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="ab4cc-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ab4cc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ab4cc-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ab4cc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ab4cc-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ab4cc-108">以下信息列出了对 Microsoft Defender 终结点 API 的更新以及更新的日期。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="ab4cc-109">RSS 源：在此页面更新时收到通知，方法为将以下 URL 复制并粘贴到源阅读器中：</span><span class="sxs-lookup"><span data-stu-id="ab4cc-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="ab4cc-110">发行说明 - 最新到最旧 (dd.mm.yyyyy) </span><span class="sxs-lookup"><span data-stu-id="ab4cc-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="05252021"></a><span data-ttu-id="ab4cc-111">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="ab4cc-111">05.25.2021</span></span>

- <span data-ttu-id="ab4cc-112">添加了新 API [导出评估方法和属性（每个设备](get-assessment-methods-properties.md)）。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-112">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="ab4cc-113">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="ab4cc-113">03.05.2021</span></span>

- <span data-ttu-id="ab4cc-114">添加了新 API： [修正活动方法和属性](get-remediation-methods-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-114">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="ab4cc-115">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="ab4cc-115">10.02.2021</span></span>

- <span data-ttu-id="ab4cc-116">添加了新 API： [批量更新警报](batch-update-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-116">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="ab4cc-117">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="ab4cc-117">25.01.2021</span></span>

- <span data-ttu-id="ab4cc-118">更新了高级搜寻 [API](run-advanced-query-api.md) 的速率限制，从每分钟 15 个请求更新为 45 个。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-118">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="ab4cc-119">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="ab4cc-119">21.01.2021</span></span>

- <span data-ttu-id="ab4cc-120">添加了新 API： [通过 标记 查找设备](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-120">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="ab4cc-121">添加了新 API： [导入指示器](import-ti-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-121">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="ab4cc-122">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="ab4cc-122">03.01.2021</span></span>

- <span data-ttu-id="ab4cc-123">更新了警报证据：添加了 ***detectionStatus** _*__、parentProcessFilePath_\*_ 和 _ *_parentProcessFileName_*\* 属性。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-123">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="ab4cc-124">更新 [了 Alert 实体](alerts.md)：添加了 ***一个检测器Id*** 属性。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-124">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="ab4cc-125">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="ab4cc-125">15.12.2020</span></span>

- <span data-ttu-id="ab4cc-126">更新 [了 Device](machine.md) 实体：添加了 ***IpInterfaces*** 列表。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-126">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="ab4cc-127">请参阅 [列出设备](get-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-127">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="ab4cc-128">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="ab4cc-128">04.11.2020</span></span>

- <span data-ttu-id="ab4cc-129">添加了新 API： [设置设备值](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-129">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="ab4cc-130">更新 [了 Device](machine.md) 实体：添加了 ***deviceValue*** 属性。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-130">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="ab4cc-131">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="ab4cc-131">01.09.2020</span></span>

- <span data-ttu-id="ab4cc-132">添加了选项以使用相关证据展开 Alert 实体。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-132">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="ab4cc-133">请参阅 [列出警报](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4cc-133">See [List Alerts](get-alerts.md).</span></span>
