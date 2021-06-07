---
title: 分数方法和属性
description: 按设备组检索组织的曝光分数、设备安全分数和曝光分数
keywords: api， 图形 api， 受支持的 api， 分数， 曝光分数， 设备安全分数， 按设备组的曝光分数
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771425"
---
# <a name="score-resource-type"></a><span data-ttu-id="c3a9c-104">分数资源类型</span><span class="sxs-lookup"><span data-stu-id="c3a9c-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c3a9c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c3a9c-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3a9c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c3a9c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c3a9c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3a9c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c3a9c-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c3a9c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3a9c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="c3a9c-110">方法</span><span class="sxs-lookup"><span data-stu-id="c3a9c-110">Methods</span></span>

<span data-ttu-id="c3a9c-111">方法</span><span class="sxs-lookup"><span data-stu-id="c3a9c-111">Method</span></span> |<span data-ttu-id="c3a9c-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="c3a9c-112">Return Type</span></span> |<span data-ttu-id="c3a9c-113">说明</span><span class="sxs-lookup"><span data-stu-id="c3a9c-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="c3a9c-114">获取曝光分数</span><span class="sxs-lookup"><span data-stu-id="c3a9c-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="c3a9c-115">分数</span><span class="sxs-lookup"><span data-stu-id="c3a9c-115">Score</span></span>](score.md) | <span data-ttu-id="c3a9c-116">获取组织曝光分数。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="c3a9c-117">获取设备安全分数</span><span class="sxs-lookup"><span data-stu-id="c3a9c-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="c3a9c-118">分数</span><span class="sxs-lookup"><span data-stu-id="c3a9c-118">Score</span></span>](score.md) | <span data-ttu-id="c3a9c-119">获取组织设备安全分数。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="c3a9c-120">按设备组列出曝光分数</span><span class="sxs-lookup"><span data-stu-id="c3a9c-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="c3a9c-121">分数</span><span class="sxs-lookup"><span data-stu-id="c3a9c-121">Score</span></span>](score.md) | <span data-ttu-id="c3a9c-122">按设备组列出分数。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="c3a9c-123">属性</span><span class="sxs-lookup"><span data-stu-id="c3a9c-123">Properties</span></span>

<span data-ttu-id="c3a9c-124">属性</span><span class="sxs-lookup"><span data-stu-id="c3a9c-124">Property</span></span> |  <span data-ttu-id="c3a9c-125">类型</span><span class="sxs-lookup"><span data-stu-id="c3a9c-125">Type</span></span>    |   <span data-ttu-id="c3a9c-126">说明</span><span class="sxs-lookup"><span data-stu-id="c3a9c-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="c3a9c-127">得分</span><span class="sxs-lookup"><span data-stu-id="c3a9c-127">Score</span></span> | <span data-ttu-id="c3a9c-128">双精度</span><span class="sxs-lookup"><span data-stu-id="c3a9c-128">Double</span></span> | <span data-ttu-id="c3a9c-129">当前分数。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-129">The current score.</span></span>
<span data-ttu-id="c3a9c-130">时间</span><span class="sxs-lookup"><span data-stu-id="c3a9c-130">Time</span></span> | <span data-ttu-id="c3a9c-131">日期时间</span><span class="sxs-lookup"><span data-stu-id="c3a9c-131">DateTime</span></span> | <span data-ttu-id="c3a9c-132">调用此 API 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="c3a9c-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c3a9c-133">RbacGroupName</span></span> | <span data-ttu-id="c3a9c-134">String</span><span class="sxs-lookup"><span data-stu-id="c3a9c-134">String</span></span> | <span data-ttu-id="c3a9c-135">设备组名称。</span><span class="sxs-lookup"><span data-stu-id="c3a9c-135">The device group name.</span></span>
