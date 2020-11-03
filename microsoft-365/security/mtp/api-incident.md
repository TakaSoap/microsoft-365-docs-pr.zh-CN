---
title: Microsoft 365 Defender API 中的事件资源类型
description: 了解 Microsoft 365 Defender 中事件资源类型的方法和属性
keywords: 事件、事件、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844016"
---
# <a name="incident-resource-type"></a><span data-ttu-id="3f2a5-104">事件资源类型</span><span class="sxs-lookup"><span data-stu-id="3f2a5-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3f2a5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3f2a5-105">**Applies to:**</span></span>
- <span data-ttu-id="3f2a5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f2a5-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="3f2a5-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3f2a5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3f2a5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="3f2a5-109">方法</span><span class="sxs-lookup"><span data-stu-id="3f2a5-109">Methods</span></span>

<span data-ttu-id="3f2a5-110">方法</span><span class="sxs-lookup"><span data-stu-id="3f2a5-110">Method</span></span> |<span data-ttu-id="3f2a5-111">返回类型</span><span class="sxs-lookup"><span data-stu-id="3f2a5-111">Return Type</span></span> |<span data-ttu-id="3f2a5-112">说明</span><span class="sxs-lookup"><span data-stu-id="3f2a5-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="3f2a5-113">列出事件</span><span class="sxs-lookup"><span data-stu-id="3f2a5-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="3f2a5-114">[事件](api-incident.md) 列表</span><span class="sxs-lookup"><span data-stu-id="3f2a5-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="3f2a5-115">获取事件列表。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-115">Get a list of incidents.</span></span>
[<span data-ttu-id="3f2a5-116">更新事件</span><span class="sxs-lookup"><span data-stu-id="3f2a5-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="3f2a5-117">事例</span><span class="sxs-lookup"><span data-stu-id="3f2a5-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="3f2a5-118">更新特定事件。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="3f2a5-119">属性</span><span class="sxs-lookup"><span data-stu-id="3f2a5-119">Properties</span></span>

<span data-ttu-id="3f2a5-120">属性</span><span class="sxs-lookup"><span data-stu-id="3f2a5-120">Property</span></span> |    <span data-ttu-id="3f2a5-121">类型</span><span class="sxs-lookup"><span data-stu-id="3f2a5-121">Type</span></span>    |    <span data-ttu-id="3f2a5-122">说明</span><span class="sxs-lookup"><span data-stu-id="3f2a5-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="3f2a5-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="3f2a5-123">incidentId</span></span> | <span data-ttu-id="3f2a5-124">long</span><span class="sxs-lookup"><span data-stu-id="3f2a5-124">long</span></span> | <span data-ttu-id="3f2a5-125">事件唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-125">Incident unique ID.</span></span>
<span data-ttu-id="3f2a5-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="3f2a5-126">redirectIncidentId</span></span> | <span data-ttu-id="3f2a5-127">nullable 长</span><span class="sxs-lookup"><span data-stu-id="3f2a5-127">nullable long</span></span> | <span data-ttu-id="3f2a5-128">当前事件合并到的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="3f2a5-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="3f2a5-129">incidentName</span></span> | <span data-ttu-id="3f2a5-130">string</span><span class="sxs-lookup"><span data-stu-id="3f2a5-130">string</span></span> | <span data-ttu-id="3f2a5-131">事件的名称。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-131">The name of the Incident.</span></span>
<span data-ttu-id="3f2a5-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="3f2a5-132">createdTime</span></span> | <span data-ttu-id="3f2a5-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f2a5-133">DateTimeOffset</span></span> | <span data-ttu-id="3f2a5-134">创建事件) 的日期和时间，以 UTC (。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="3f2a5-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="3f2a5-135">lastUpdateTime</span></span> | <span data-ttu-id="3f2a5-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3f2a5-136">DateTimeOffset</span></span> | <span data-ttu-id="3f2a5-137">上次更新事件) UTC (的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="3f2a5-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="3f2a5-138">assignedTo</span></span> | <span data-ttu-id="3f2a5-139">string</span><span class="sxs-lookup"><span data-stu-id="3f2a5-139">string</span></span> | <span data-ttu-id="3f2a5-140">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-140">Owner of the Incident.</span></span>
<span data-ttu-id="3f2a5-141">severity</span><span class="sxs-lookup"><span data-stu-id="3f2a5-141">severity</span></span> | <span data-ttu-id="3f2a5-142">枚举</span><span class="sxs-lookup"><span data-stu-id="3f2a5-142">Enum</span></span> | <span data-ttu-id="3f2a5-143">事件的严重性。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-143">Severity of the Incident.</span></span> <span data-ttu-id="3f2a5-144">可能的值是 ```UnSpecified``` ： ```Informational``` 、 ```Low``` 、 ```Medium``` 和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="3f2a5-145">status</span><span class="sxs-lookup"><span data-stu-id="3f2a5-145">status</span></span> | <span data-ttu-id="3f2a5-146">枚举</span><span class="sxs-lookup"><span data-stu-id="3f2a5-146">Enum</span></span> | <span data-ttu-id="3f2a5-147">指定事件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="3f2a5-148">可能的值为 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="3f2a5-149">classification</span><span class="sxs-lookup"><span data-stu-id="3f2a5-149">classification</span></span> | <span data-ttu-id="3f2a5-150">枚举</span><span class="sxs-lookup"><span data-stu-id="3f2a5-150">Enum</span></span> | <span data-ttu-id="3f2a5-151">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-151">Specification of the incident.</span></span> <span data-ttu-id="3f2a5-152">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="3f2a5-153">可用性</span><span class="sxs-lookup"><span data-stu-id="3f2a5-153">determination</span></span> | <span data-ttu-id="3f2a5-154">枚举</span><span class="sxs-lookup"><span data-stu-id="3f2a5-154">Enum</span></span> | <span data-ttu-id="3f2a5-155">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="3f2a5-156">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="3f2a5-157">标记</span><span class="sxs-lookup"><span data-stu-id="3f2a5-157">tags</span></span> | <span data-ttu-id="3f2a5-158">字符串列表</span><span class="sxs-lookup"><span data-stu-id="3f2a5-158">string List</span></span> | <span data-ttu-id="3f2a5-159">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-159">List of Incident tags.</span></span>
<span data-ttu-id="3f2a5-160">警报</span><span class="sxs-lookup"><span data-stu-id="3f2a5-160">alerts</span></span> | <span data-ttu-id="3f2a5-161">通知列表</span><span class="sxs-lookup"><span data-stu-id="3f2a5-161">Alert List</span></span> | <span data-ttu-id="3f2a5-162">相关警报的列表。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-162">List of related alerts.</span></span> <span data-ttu-id="3f2a5-163">请参阅 [List 事件](api-list-incidents.md) API 文档中的示例。</span><span class="sxs-lookup"><span data-stu-id="3f2a5-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
