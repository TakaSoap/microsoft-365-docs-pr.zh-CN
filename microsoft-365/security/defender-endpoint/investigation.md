---
title: 调查资源类型
description: Microsoft Defender for Endpoint Investigation 实体。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 调查
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771725"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="86c0b-104">调查资源类型</span><span class="sxs-lookup"><span data-stu-id="86c0b-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86c0b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="86c0b-105">**Applies to:**</span></span>
- [<span data-ttu-id="86c0b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="86c0b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86c0b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86c0b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="86c0b-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="86c0b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="86c0b-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="86c0b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="86c0b-110">代表 Defender for Endpoint 中的自动调查实体。</span><span class="sxs-lookup"><span data-stu-id="86c0b-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="86c0b-111">有关详细信息 [，请参阅自动](automated-investigations.md) 调查概述。</span><span class="sxs-lookup"><span data-stu-id="86c0b-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="86c0b-112">方法</span><span class="sxs-lookup"><span data-stu-id="86c0b-112">Methods</span></span>
<span data-ttu-id="86c0b-113">方法</span><span class="sxs-lookup"><span data-stu-id="86c0b-113">Method</span></span>|<span data-ttu-id="86c0b-114">返回类型</span><span class="sxs-lookup"><span data-stu-id="86c0b-114">Return Type</span></span> |<span data-ttu-id="86c0b-115">说明</span><span class="sxs-lookup"><span data-stu-id="86c0b-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="86c0b-116">列表调查</span><span class="sxs-lookup"><span data-stu-id="86c0b-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="86c0b-117">调查集合</span><span class="sxs-lookup"><span data-stu-id="86c0b-117">Investigation collection</span></span> | <span data-ttu-id="86c0b-118">获取调查集合</span><span class="sxs-lookup"><span data-stu-id="86c0b-118">Get collection of Investigation</span></span>
[<span data-ttu-id="86c0b-119">获取单个调查</span><span class="sxs-lookup"><span data-stu-id="86c0b-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="86c0b-120">调查实体</span><span class="sxs-lookup"><span data-stu-id="86c0b-120">Investigation entity</span></span> | <span data-ttu-id="86c0b-121">获取单个 Investigation 实体。</span><span class="sxs-lookup"><span data-stu-id="86c0b-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="86c0b-122">启动调查</span><span class="sxs-lookup"><span data-stu-id="86c0b-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="86c0b-123">调查实体</span><span class="sxs-lookup"><span data-stu-id="86c0b-123">Investigation entity</span></span> | <span data-ttu-id="86c0b-124">在设备上启动调查。</span><span class="sxs-lookup"><span data-stu-id="86c0b-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="86c0b-125">属性</span><span class="sxs-lookup"><span data-stu-id="86c0b-125">Properties</span></span>
<span data-ttu-id="86c0b-126">属性</span><span class="sxs-lookup"><span data-stu-id="86c0b-126">Property</span></span> |  <span data-ttu-id="86c0b-127">类型</span><span class="sxs-lookup"><span data-stu-id="86c0b-127">Type</span></span>    |   <span data-ttu-id="86c0b-128">说明</span><span class="sxs-lookup"><span data-stu-id="86c0b-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="86c0b-129">id</span><span class="sxs-lookup"><span data-stu-id="86c0b-129">id</span></span> | <span data-ttu-id="86c0b-130">String</span><span class="sxs-lookup"><span data-stu-id="86c0b-130">String</span></span> | <span data-ttu-id="86c0b-131">调查实体的标识。</span><span class="sxs-lookup"><span data-stu-id="86c0b-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="86c0b-132">startTime</span><span class="sxs-lookup"><span data-stu-id="86c0b-132">startTime</span></span> | <span data-ttu-id="86c0b-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="86c0b-133">DateTime Nullable</span></span> | <span data-ttu-id="86c0b-134">创建调查的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86c0b-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="86c0b-135">endTime</span><span class="sxs-lookup"><span data-stu-id="86c0b-135">endTime</span></span> | <span data-ttu-id="86c0b-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="86c0b-136">DateTime Nullable</span></span> | <span data-ttu-id="86c0b-137">调查完成的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86c0b-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="86c0b-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="86c0b-138">cancelledBy</span></span> | <span data-ttu-id="86c0b-139">String</span><span class="sxs-lookup"><span data-stu-id="86c0b-139">String</span></span> | <span data-ttu-id="86c0b-140">取消调查的用户/应用程序的 ID。</span><span class="sxs-lookup"><span data-stu-id="86c0b-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="86c0b-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="86c0b-141">investigationState</span></span> | <span data-ttu-id="86c0b-142">枚举</span><span class="sxs-lookup"><span data-stu-id="86c0b-142">Enum</span></span> | <span data-ttu-id="86c0b-143">调查的当前状态。</span><span class="sxs-lookup"><span data-stu-id="86c0b-143">The current state of the investigation.</span></span> <span data-ttu-id="86c0b-144">可能的值包括："Unknown"、"Terminated"、 "SuccessfullyRemediated"、"Benign"、"Failed"、"PartiallyRemediated"、"Running"、"PendingApproval"、"PendingResource"、"PartiallyInvestigated"、"TerminatedByUser"、"TerminatedBySystem"、"Queued"、"InnerFailure"、"PreexistingAlert"、"UnsupportedOs"、"UnsupportedAlertType"和"SuppressedAlert"。</span><span class="sxs-lookup"><span data-stu-id="86c0b-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="86c0b-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="86c0b-145">statusDetails</span></span> | <span data-ttu-id="86c0b-146">String</span><span class="sxs-lookup"><span data-stu-id="86c0b-146">String</span></span> | <span data-ttu-id="86c0b-147">有关调查状态的其他信息。</span><span class="sxs-lookup"><span data-stu-id="86c0b-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="86c0b-148">machineId</span><span class="sxs-lookup"><span data-stu-id="86c0b-148">machineId</span></span> | <span data-ttu-id="86c0b-149">String</span><span class="sxs-lookup"><span data-stu-id="86c0b-149">String</span></span> | <span data-ttu-id="86c0b-150">执行调查的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="86c0b-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="86c0b-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="86c0b-151">computerDnsName</span></span> | <span data-ttu-id="86c0b-152">String</span><span class="sxs-lookup"><span data-stu-id="86c0b-152">String</span></span> | <span data-ttu-id="86c0b-153">执行调查的设备的名称。</span><span class="sxs-lookup"><span data-stu-id="86c0b-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="86c0b-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="86c0b-154">triggeringAlertId</span></span> | <span data-ttu-id="86c0b-155">String</span><span class="sxs-lookup"><span data-stu-id="86c0b-155">String</span></span> | <span data-ttu-id="86c0b-156">触发调查的警报的 ID。</span><span class="sxs-lookup"><span data-stu-id="86c0b-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="86c0b-157">Json 表示形式</span><span class="sxs-lookup"><span data-stu-id="86c0b-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
