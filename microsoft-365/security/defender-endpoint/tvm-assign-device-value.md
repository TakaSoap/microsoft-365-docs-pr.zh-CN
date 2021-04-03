---
title: 分配设备值 - 威胁和漏洞管理
description: 了解如何为设备分配低、普通或高值，以帮助区分资产优先级。
keywords: microsoft defender atp 设备值、威胁和漏洞管理设备值、高价值设备、设备值曝光分数
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3cecee8b80f179f67cb48f62e1d9238a51825bfd
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500206"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="10665-104">分配设备值 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="10665-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10665-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="10665-105">**Applies to:**</span></span>

- [<span data-ttu-id="10665-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="10665-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="10665-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="10665-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="10665-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10665-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="10665-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="10665-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="10665-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="10665-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="10665-111">定义设备值有助于区分资产优先级。</span><span class="sxs-lookup"><span data-stu-id="10665-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="10665-112">设备值用于将单个资产的风险损失纳入威胁和漏洞管理暴露分数计算中。</span><span class="sxs-lookup"><span data-stu-id="10665-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="10665-113">分配为"高值"的设备将获得更多权重。</span><span class="sxs-lookup"><span data-stu-id="10665-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="10665-114">您还可以使用设置 [的设备值 API](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="10665-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="10665-115">设备值选项：</span><span class="sxs-lookup"><span data-stu-id="10665-115">Device value options:</span></span>

- <span data-ttu-id="10665-116">低</span><span class="sxs-lookup"><span data-stu-id="10665-116">Low</span></span>
- <span data-ttu-id="10665-117">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="10665-117">Normal (Default)</span></span>
- <span data-ttu-id="10665-118">高</span><span class="sxs-lookup"><span data-stu-id="10665-118">High</span></span>

<span data-ttu-id="10665-119">应分配高值的设备示例：</span><span class="sxs-lookup"><span data-stu-id="10665-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="10665-120">域控制器、Active Directory</span><span class="sxs-lookup"><span data-stu-id="10665-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="10665-121">面向 Internet 的设备</span><span class="sxs-lookup"><span data-stu-id="10665-121">Internet facing devices</span></span>
- <span data-ttu-id="10665-122">VIP 设备</span><span class="sxs-lookup"><span data-stu-id="10665-122">VIP devices</span></span>
- <span data-ttu-id="10665-123">托管内部/外部生产服务的设备</span><span class="sxs-lookup"><span data-stu-id="10665-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="10665-124">选择设备值</span><span class="sxs-lookup"><span data-stu-id="10665-124">Choose device value</span></span>

1. <span data-ttu-id="10665-125">导航到任何设备页面，最简单的位置是设备清单。</span><span class="sxs-lookup"><span data-stu-id="10665-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="10665-126">从 **页面顶部的** 操作栏旁边的三个点中选择设备值。</span><span class="sxs-lookup"><span data-stu-id="10665-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![设备值下拉列表的示例。](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="10665-128">将显示一个显示当前设备值及其的含义的飞出图。</span><span class="sxs-lookup"><span data-stu-id="10665-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="10665-129">查看设备的值，然后选择最适合你的设备的值。</span><span class="sxs-lookup"><span data-stu-id="10665-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="10665-130">![设备值飞出的示例。](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="10665-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="10665-131">设备值如何影响你的曝光分数</span><span class="sxs-lookup"><span data-stu-id="10665-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="10665-132">曝光分数是所有设备的加权平均值。</span><span class="sxs-lookup"><span data-stu-id="10665-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="10665-133">如果你有设备组，还可以按设备组筛选分数。</span><span class="sxs-lookup"><span data-stu-id="10665-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="10665-134">普通设备的权重为 1</span><span class="sxs-lookup"><span data-stu-id="10665-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="10665-135">低值设备的权重为 0.75</span><span class="sxs-lookup"><span data-stu-id="10665-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="10665-136">高价值设备的权重为 NumberOfAssets / 10。</span><span class="sxs-lookup"><span data-stu-id="10665-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="10665-137">如果你有 100 台设备，则每个高价值设备的权重将为 10 (100/10) </span><span class="sxs-lookup"><span data-stu-id="10665-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="10665-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="10665-138">Related topics</span></span>

- [<span data-ttu-id="10665-139">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="10665-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="10665-140">曝光分数</span><span class="sxs-lookup"><span data-stu-id="10665-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="10665-141">API</span><span class="sxs-lookup"><span data-stu-id="10665-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)