---
title: 指示器资源类型
description: 使用 Microsoft Defender for Endpoint 指定实体详细信息并定义指示器的过期时间。
keywords: api， 受支持的 api， 获取， TiIndicator， 指示器， 最近
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187056"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="c5ebd-104">指示器资源类型</span><span class="sxs-lookup"><span data-stu-id="c5ebd-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5ebd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c5ebd-105">**Applies to:**</span></span>
- [<span data-ttu-id="c5ebd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c5ebd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c5ebd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5ebd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c5ebd-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c5ebd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c5ebd-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="c5ebd-110">请参阅门户 [中的相应](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) "指示器"页。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="c5ebd-111">方法</span><span class="sxs-lookup"><span data-stu-id="c5ebd-111">Method</span></span>|<span data-ttu-id="c5ebd-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="c5ebd-112">Return Type</span></span> |<span data-ttu-id="c5ebd-113">说明</span><span class="sxs-lookup"><span data-stu-id="c5ebd-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="c5ebd-114">列表指示器</span><span class="sxs-lookup"><span data-stu-id="c5ebd-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="c5ebd-115">[指示器](ti-indicator.md) 集合</span><span class="sxs-lookup"><span data-stu-id="c5ebd-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="c5ebd-116">列表 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="c5ebd-117">提交指示器</span><span class="sxs-lookup"><span data-stu-id="c5ebd-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="c5ebd-118">指示器</span><span class="sxs-lookup"><span data-stu-id="c5ebd-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="c5ebd-119">提交或更新 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="c5ebd-120">导入指示器</span><span class="sxs-lookup"><span data-stu-id="c5ebd-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="c5ebd-121">[指示器](ti-indicator.md) 集合</span><span class="sxs-lookup"><span data-stu-id="c5ebd-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="c5ebd-122">提交或更新 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="c5ebd-123">删除指示器</span><span class="sxs-lookup"><span data-stu-id="c5ebd-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="c5ebd-124">无内容</span><span class="sxs-lookup"><span data-stu-id="c5ebd-124">No Content</span></span> | <span data-ttu-id="c5ebd-125">删除 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="c5ebd-126">属性</span><span class="sxs-lookup"><span data-stu-id="c5ebd-126">Properties</span></span>
<span data-ttu-id="c5ebd-127">属性</span><span class="sxs-lookup"><span data-stu-id="c5ebd-127">Property</span></span> |  <span data-ttu-id="c5ebd-128">类型</span><span class="sxs-lookup"><span data-stu-id="c5ebd-128">Type</span></span>    |   <span data-ttu-id="c5ebd-129">说明</span><span class="sxs-lookup"><span data-stu-id="c5ebd-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="c5ebd-130">id</span><span class="sxs-lookup"><span data-stu-id="c5ebd-130">id</span></span> | <span data-ttu-id="c5ebd-131">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-131">String</span></span> | <span data-ttu-id="c5ebd-132">Indicator [实体的](ti-indicator.md) 标识。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="c5ebd-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="c5ebd-133">indicatorValue</span></span> | <span data-ttu-id="c5ebd-134">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-134">String</span></span> | <span data-ttu-id="c5ebd-135">指示器 [的值](ti-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="c5ebd-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="c5ebd-136">indicatorType</span></span> | <span data-ttu-id="c5ebd-137">枚举</span><span class="sxs-lookup"><span data-stu-id="c5ebd-137">Enum</span></span> | <span data-ttu-id="c5ebd-138">指示器的类型。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-138">Type of the indicator.</span></span> <span data-ttu-id="c5ebd-139">可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="c5ebd-140">应用程序</span><span class="sxs-lookup"><span data-stu-id="c5ebd-140">application</span></span> | <span data-ttu-id="c5ebd-141">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-141">String</span></span> | <span data-ttu-id="c5ebd-142">与指示器关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="c5ebd-143">action</span><span class="sxs-lookup"><span data-stu-id="c5ebd-143">action</span></span> | <span data-ttu-id="c5ebd-144">枚举</span><span class="sxs-lookup"><span data-stu-id="c5ebd-144">Enum</span></span> | <span data-ttu-id="c5ebd-145">如果在组织中发现指示器，将采取的操作。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="c5ebd-146">可能的值是："Alert"、"AlertAndBlock"和"Allowed"。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="c5ebd-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="c5ebd-147">sourceType</span></span> | <span data-ttu-id="c5ebd-148">枚举</span><span class="sxs-lookup"><span data-stu-id="c5ebd-148">Enum</span></span> | <span data-ttu-id="c5ebd-149">"用户"（如果由用户创建的指示器 (例如，从门户) ，"AadApp"，以防它通过 API 使用自动应用程序提交。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="c5ebd-150">source</span><span class="sxs-lookup"><span data-stu-id="c5ebd-150">source</span></span> | <span data-ttu-id="c5ebd-151">string</span><span class="sxs-lookup"><span data-stu-id="c5ebd-151">string</span></span> | <span data-ttu-id="c5ebd-152">提交指示器的用户/应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="c5ebd-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="c5ebd-153">createdBy</span></span> | <span data-ttu-id="c5ebd-154">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-154">String</span></span> | <span data-ttu-id="c5ebd-155">提交指示器的用户/应用程序的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="c5ebd-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="c5ebd-156">lastUpdatedBy</span></span> | <span data-ttu-id="c5ebd-157">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-157">String</span></span> | <span data-ttu-id="c5ebd-158">上次更新指示器的用户/应用程序的标识。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="c5ebd-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="c5ebd-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="c5ebd-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c5ebd-160">DateTimeOffset</span></span> | <span data-ttu-id="c5ebd-161">创建指示器的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="c5ebd-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="c5ebd-162">expirationTime</span></span> | <span data-ttu-id="c5ebd-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c5ebd-163">DateTimeOffset</span></span> | <span data-ttu-id="c5ebd-164">指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="c5ebd-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="c5ebd-165">lastUpdateTime</span></span> | <span data-ttu-id="c5ebd-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c5ebd-166">DateTimeOffset</span></span> | <span data-ttu-id="c5ebd-167">上次更新指示器的时间。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="c5ebd-168">severity</span><span class="sxs-lookup"><span data-stu-id="c5ebd-168">severity</span></span> | <span data-ttu-id="c5ebd-169">枚举</span><span class="sxs-lookup"><span data-stu-id="c5ebd-169">Enum</span></span> | <span data-ttu-id="c5ebd-170">指示器的严重性。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-170">The severity of the indicator.</span></span> <span data-ttu-id="c5ebd-171">可能的值包括："Informational"、"Low"、"Medium"和"High"。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="c5ebd-172">title</span><span class="sxs-lookup"><span data-stu-id="c5ebd-172">title</span></span> | <span data-ttu-id="c5ebd-173">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-173">String</span></span> | <span data-ttu-id="c5ebd-174">指示器标题。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-174">Indicator title.</span></span>
<span data-ttu-id="c5ebd-175">说明</span><span class="sxs-lookup"><span data-stu-id="c5ebd-175">description</span></span> | <span data-ttu-id="c5ebd-176">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-176">String</span></span> | <span data-ttu-id="c5ebd-177">指示器的说明。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-177">Description of the indicator.</span></span>
<span data-ttu-id="c5ebd-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="c5ebd-178">recommendedActions</span></span> | <span data-ttu-id="c5ebd-179">String</span><span class="sxs-lookup"><span data-stu-id="c5ebd-179">String</span></span> | <span data-ttu-id="c5ebd-180">指示器的建议操作。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="c5ebd-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="c5ebd-181">rbacGroupNames</span></span> | <span data-ttu-id="c5ebd-182">字符串列表</span><span class="sxs-lookup"><span data-stu-id="c5ebd-182">List of strings</span></span> | <span data-ttu-id="c5ebd-183">RBAC 设备组名称，其中指示器已公开且处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="c5ebd-184">空列表，以防它向所有设备公开。</span><span class="sxs-lookup"><span data-stu-id="c5ebd-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="c5ebd-185">Json 表示形式</span><span class="sxs-lookup"><span data-stu-id="c5ebd-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
