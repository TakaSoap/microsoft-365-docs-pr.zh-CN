---
title: 分数方法和属性
description: 按设备组检索组织的曝光分数、设备安全分数和曝光分数
keywords: api， 图形 api， 受支持的 api， 分数， 曝光分数， 设备安全分数， 按设备组的曝光分数
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200157"
---
# <a name="score-resource-type"></a><span data-ttu-id="6bfd2-104">分数资源类型</span><span class="sxs-lookup"><span data-stu-id="6bfd2-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6bfd2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6bfd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="6bfd2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6bfd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6bfd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bfd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6bfd2-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6bfd2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6bfd2-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="6bfd2-110">方法</span><span class="sxs-lookup"><span data-stu-id="6bfd2-110">Methods</span></span>

<span data-ttu-id="6bfd2-111">方法</span><span class="sxs-lookup"><span data-stu-id="6bfd2-111">Method</span></span> |<span data-ttu-id="6bfd2-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="6bfd2-112">Return Type</span></span> |<span data-ttu-id="6bfd2-113">说明</span><span class="sxs-lookup"><span data-stu-id="6bfd2-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="6bfd2-114">获取曝光分数</span><span class="sxs-lookup"><span data-stu-id="6bfd2-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="6bfd2-115">分数</span><span class="sxs-lookup"><span data-stu-id="6bfd2-115">Score</span></span>](score.md) | <span data-ttu-id="6bfd2-116">获取组织曝光分数。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="6bfd2-117">获取设备安全分数</span><span class="sxs-lookup"><span data-stu-id="6bfd2-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="6bfd2-118">分数</span><span class="sxs-lookup"><span data-stu-id="6bfd2-118">Score</span></span>](score.md) | <span data-ttu-id="6bfd2-119">获取组织设备安全分数。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="6bfd2-120">按设备组列出曝光分数</span><span class="sxs-lookup"><span data-stu-id="6bfd2-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="6bfd2-121">分数</span><span class="sxs-lookup"><span data-stu-id="6bfd2-121">Score</span></span>](score.md) | <span data-ttu-id="6bfd2-122">按设备组列出分数。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="6bfd2-123">属性</span><span class="sxs-lookup"><span data-stu-id="6bfd2-123">Properties</span></span>

<span data-ttu-id="6bfd2-124">属性</span><span class="sxs-lookup"><span data-stu-id="6bfd2-124">Property</span></span> |  <span data-ttu-id="6bfd2-125">类型</span><span class="sxs-lookup"><span data-stu-id="6bfd2-125">Type</span></span>    |   <span data-ttu-id="6bfd2-126">说明</span><span class="sxs-lookup"><span data-stu-id="6bfd2-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="6bfd2-127">得分</span><span class="sxs-lookup"><span data-stu-id="6bfd2-127">Score</span></span> | <span data-ttu-id="6bfd2-128">双精度</span><span class="sxs-lookup"><span data-stu-id="6bfd2-128">Double</span></span> | <span data-ttu-id="6bfd2-129">当前分数。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-129">The current score.</span></span>
<span data-ttu-id="6bfd2-130">时间</span><span class="sxs-lookup"><span data-stu-id="6bfd2-130">Time</span></span> | <span data-ttu-id="6bfd2-131">日期时间</span><span class="sxs-lookup"><span data-stu-id="6bfd2-131">DateTime</span></span> | <span data-ttu-id="6bfd2-132">调用此 API 的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="6bfd2-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6bfd2-133">RbacGroupName</span></span> | <span data-ttu-id="6bfd2-134">字符串</span><span class="sxs-lookup"><span data-stu-id="6bfd2-134">String</span></span> | <span data-ttu-id="6bfd2-135">设备组名称。</span><span class="sxs-lookup"><span data-stu-id="6bfd2-135">The device group name.</span></span>
