---
title: Microsoft 威胁防护 API 中的事件资源类型
description: 了解 Microsoft 威胁防护中事件资源类型的方法和属性
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650162"
---
# <a name="incident-resource-type"></a><span data-ttu-id="73f1f-104">事件资源类型</span><span class="sxs-lookup"><span data-stu-id="73f1f-104">Incident resource type</span></span>

<span data-ttu-id="73f1f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="73f1f-105">**Applies to:**</span></span>
- <span data-ttu-id="73f1f-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="73f1f-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="73f1f-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="73f1f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="73f1f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="73f1f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="73f1f-109">Methods</span><span class="sxs-lookup"><span data-stu-id="73f1f-109">Methods</span></span>

<span data-ttu-id="73f1f-110">方法</span><span class="sxs-lookup"><span data-stu-id="73f1f-110">Method</span></span> |<span data-ttu-id="73f1f-111">返回类型</span><span class="sxs-lookup"><span data-stu-id="73f1f-111">Return Type</span></span> |<span data-ttu-id="73f1f-112">说明</span><span class="sxs-lookup"><span data-stu-id="73f1f-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="73f1f-113">列出事件</span><span class="sxs-lookup"><span data-stu-id="73f1f-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="73f1f-114">[事件](api-incident.md) 列表</span><span class="sxs-lookup"><span data-stu-id="73f1f-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="73f1f-115">获取事件列表。</span><span class="sxs-lookup"><span data-stu-id="73f1f-115">Get a list of incidents.</span></span>
[<span data-ttu-id="73f1f-116">更新事件</span><span class="sxs-lookup"><span data-stu-id="73f1f-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="73f1f-117">事例</span><span class="sxs-lookup"><span data-stu-id="73f1f-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="73f1f-118">更新特定事件。</span><span class="sxs-lookup"><span data-stu-id="73f1f-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="73f1f-119">属性</span><span class="sxs-lookup"><span data-stu-id="73f1f-119">Properties</span></span>

<span data-ttu-id="73f1f-120">属性</span><span class="sxs-lookup"><span data-stu-id="73f1f-120">Property</span></span> |    <span data-ttu-id="73f1f-121">类型</span><span class="sxs-lookup"><span data-stu-id="73f1f-121">Type</span></span>    |    <span data-ttu-id="73f1f-122">描述</span><span class="sxs-lookup"><span data-stu-id="73f1f-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="73f1f-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="73f1f-123">incidentId</span></span> | <span data-ttu-id="73f1f-124">long</span><span class="sxs-lookup"><span data-stu-id="73f1f-124">long</span></span> | <span data-ttu-id="73f1f-125">事件唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="73f1f-125">Incident unique ID.</span></span>
<span data-ttu-id="73f1f-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="73f1f-126">redirectIncidentId</span></span> | <span data-ttu-id="73f1f-127">nullable 长</span><span class="sxs-lookup"><span data-stu-id="73f1f-127">nullable long</span></span> | <span data-ttu-id="73f1f-128">当前事件合并到的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="73f1f-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="73f1f-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="73f1f-129">incidentName</span></span> | <span data-ttu-id="73f1f-130">字符串</span><span class="sxs-lookup"><span data-stu-id="73f1f-130">string</span></span> | <span data-ttu-id="73f1f-131">事件的名称。</span><span class="sxs-lookup"><span data-stu-id="73f1f-131">The name of the Incident.</span></span>
<span data-ttu-id="73f1f-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="73f1f-132">createdTime</span></span> | <span data-ttu-id="73f1f-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73f1f-133">DateTimeOffset</span></span> | <span data-ttu-id="73f1f-134">创建事件) 的日期和时间，以 UTC (。</span><span class="sxs-lookup"><span data-stu-id="73f1f-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="73f1f-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="73f1f-135">lastUpdateTime</span></span> | <span data-ttu-id="73f1f-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73f1f-136">DateTimeOffset</span></span> | <span data-ttu-id="73f1f-137">上次更新事件) UTC (的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="73f1f-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="73f1f-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="73f1f-138">assignedTo</span></span> | <span data-ttu-id="73f1f-139">字符串</span><span class="sxs-lookup"><span data-stu-id="73f1f-139">string</span></span> | <span data-ttu-id="73f1f-140">事件的所有者。</span><span class="sxs-lookup"><span data-stu-id="73f1f-140">Owner of the Incident.</span></span>
<span data-ttu-id="73f1f-141">severity</span><span class="sxs-lookup"><span data-stu-id="73f1f-141">severity</span></span> | <span data-ttu-id="73f1f-142">枚举</span><span class="sxs-lookup"><span data-stu-id="73f1f-142">Enum</span></span> | <span data-ttu-id="73f1f-143">事件的严重性。</span><span class="sxs-lookup"><span data-stu-id="73f1f-143">Severity of the Incident.</span></span> <span data-ttu-id="73f1f-144">可能的值是 ```UnSpecified``` ： ```Informational``` 、 ```Low``` 、 ```Medium``` 和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="73f1f-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="73f1f-145">状态</span><span class="sxs-lookup"><span data-stu-id="73f1f-145">status</span></span> | <span data-ttu-id="73f1f-146">枚举</span><span class="sxs-lookup"><span data-stu-id="73f1f-146">Enum</span></span> | <span data-ttu-id="73f1f-147">指定事件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="73f1f-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="73f1f-148">可能的值为 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="73f1f-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="73f1f-149">classification</span><span class="sxs-lookup"><span data-stu-id="73f1f-149">classification</span></span> | <span data-ttu-id="73f1f-150">枚举</span><span class="sxs-lookup"><span data-stu-id="73f1f-150">Enum</span></span> | <span data-ttu-id="73f1f-151">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="73f1f-151">Specification of the incident.</span></span> <span data-ttu-id="73f1f-152">可取值为：```Unknown```、```FalsePositive```、```TruePositive```。</span><span class="sxs-lookup"><span data-stu-id="73f1f-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="73f1f-153">可用性</span><span class="sxs-lookup"><span data-stu-id="73f1f-153">determination</span></span> | <span data-ttu-id="73f1f-154">枚举</span><span class="sxs-lookup"><span data-stu-id="73f1f-154">Enum</span></span> | <span data-ttu-id="73f1f-155">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="73f1f-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="73f1f-156">可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。</span><span class="sxs-lookup"><span data-stu-id="73f1f-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="73f1f-157">tags</span><span class="sxs-lookup"><span data-stu-id="73f1f-157">tags</span></span> | <span data-ttu-id="73f1f-158">字符串列表</span><span class="sxs-lookup"><span data-stu-id="73f1f-158">string List</span></span> | <span data-ttu-id="73f1f-159">事件标记列表。</span><span class="sxs-lookup"><span data-stu-id="73f1f-159">List of Incident tags.</span></span>
<span data-ttu-id="73f1f-160">警报</span><span class="sxs-lookup"><span data-stu-id="73f1f-160">alerts</span></span> | <span data-ttu-id="73f1f-161">通知列表</span><span class="sxs-lookup"><span data-stu-id="73f1f-161">Alert List</span></span> | <span data-ttu-id="73f1f-162">相关警报的列表。</span><span class="sxs-lookup"><span data-stu-id="73f1f-162">List of related alerts.</span></span> <span data-ttu-id="73f1f-163">请参阅 [List 事件](api-list-incidents.md) API 文档中的示例。</span><span class="sxs-lookup"><span data-stu-id="73f1f-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>