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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771377"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="96e83-104">指示器资源类型</span><span class="sxs-lookup"><span data-stu-id="96e83-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="96e83-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="96e83-105">**Applies to:**</span></span>
- [<span data-ttu-id="96e83-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="96e83-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96e83-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96e83-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="96e83-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="96e83-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="96e83-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="96e83-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="96e83-110">请参阅门户 [中的相应](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) "指示器"页。</span><span class="sxs-lookup"><span data-stu-id="96e83-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="96e83-111">方法</span><span class="sxs-lookup"><span data-stu-id="96e83-111">Method</span></span>|<span data-ttu-id="96e83-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="96e83-112">Return Type</span></span> |<span data-ttu-id="96e83-113">说明</span><span class="sxs-lookup"><span data-stu-id="96e83-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="96e83-114">列出指示器</span><span class="sxs-lookup"><span data-stu-id="96e83-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="96e83-115">[指示器](ti-indicator.md) 集合</span><span class="sxs-lookup"><span data-stu-id="96e83-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="96e83-116">列表 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="96e83-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="96e83-117">提交指示器</span><span class="sxs-lookup"><span data-stu-id="96e83-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="96e83-118">指示器</span><span class="sxs-lookup"><span data-stu-id="96e83-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="96e83-119">提交或更新 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="96e83-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="96e83-120">导入指示器</span><span class="sxs-lookup"><span data-stu-id="96e83-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="96e83-121">[指示器](ti-indicator.md) 集合</span><span class="sxs-lookup"><span data-stu-id="96e83-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="96e83-122">提交或更新 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="96e83-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="96e83-123">删除指示器</span><span class="sxs-lookup"><span data-stu-id="96e83-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="96e83-124">无内容</span><span class="sxs-lookup"><span data-stu-id="96e83-124">No Content</span></span> | <span data-ttu-id="96e83-125">删除 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="96e83-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="96e83-126">属性</span><span class="sxs-lookup"><span data-stu-id="96e83-126">Properties</span></span>
<span data-ttu-id="96e83-127">属性</span><span class="sxs-lookup"><span data-stu-id="96e83-127">Property</span></span> |  <span data-ttu-id="96e83-128">类型</span><span class="sxs-lookup"><span data-stu-id="96e83-128">Type</span></span>    |   <span data-ttu-id="96e83-129">说明</span><span class="sxs-lookup"><span data-stu-id="96e83-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="96e83-130">id</span><span class="sxs-lookup"><span data-stu-id="96e83-130">id</span></span> | <span data-ttu-id="96e83-131">String</span><span class="sxs-lookup"><span data-stu-id="96e83-131">String</span></span> | <span data-ttu-id="96e83-132">Indicator [实体的](ti-indicator.md) 标识。</span><span class="sxs-lookup"><span data-stu-id="96e83-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="96e83-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="96e83-133">indicatorValue</span></span> | <span data-ttu-id="96e83-134">String</span><span class="sxs-lookup"><span data-stu-id="96e83-134">String</span></span> | <span data-ttu-id="96e83-135">指示器 [的值](ti-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="96e83-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="96e83-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="96e83-136">indicatorType</span></span> | <span data-ttu-id="96e83-137">枚举</span><span class="sxs-lookup"><span data-stu-id="96e83-137">Enum</span></span> | <span data-ttu-id="96e83-138">指示器的类型。</span><span class="sxs-lookup"><span data-stu-id="96e83-138">Type of the indicator.</span></span> <span data-ttu-id="96e83-139">可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。</span><span class="sxs-lookup"><span data-stu-id="96e83-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="96e83-140">应用程序</span><span class="sxs-lookup"><span data-stu-id="96e83-140">application</span></span> | <span data-ttu-id="96e83-141">String</span><span class="sxs-lookup"><span data-stu-id="96e83-141">String</span></span> | <span data-ttu-id="96e83-142">与指示器关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="96e83-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="96e83-143">action</span><span class="sxs-lookup"><span data-stu-id="96e83-143">action</span></span> | <span data-ttu-id="96e83-144">枚举</span><span class="sxs-lookup"><span data-stu-id="96e83-144">Enum</span></span> | <span data-ttu-id="96e83-145">如果在组织中发现指示器，将采取的操作。</span><span class="sxs-lookup"><span data-stu-id="96e83-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="96e83-146">可能的值是："Alert"、"AlertAndBlock"和"Allowed"。</span><span class="sxs-lookup"><span data-stu-id="96e83-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="96e83-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="96e83-147">sourceType</span></span> | <span data-ttu-id="96e83-148">枚举</span><span class="sxs-lookup"><span data-stu-id="96e83-148">Enum</span></span> | <span data-ttu-id="96e83-149">"用户"（如果由用户创建的指示器 (例如，从门户) ，"AadApp"，以防它通过 API 使用自动应用程序提交。</span><span class="sxs-lookup"><span data-stu-id="96e83-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="96e83-150">source</span><span class="sxs-lookup"><span data-stu-id="96e83-150">source</span></span> | <span data-ttu-id="96e83-151">string</span><span class="sxs-lookup"><span data-stu-id="96e83-151">string</span></span> | <span data-ttu-id="96e83-152">提交指示器的用户/应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="96e83-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="96e83-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="96e83-153">createdBy</span></span> | <span data-ttu-id="96e83-154">String</span><span class="sxs-lookup"><span data-stu-id="96e83-154">String</span></span> | <span data-ttu-id="96e83-155">提交指示器的用户/应用程序的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="96e83-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="96e83-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="96e83-156">lastUpdatedBy</span></span> | <span data-ttu-id="96e83-157">String</span><span class="sxs-lookup"><span data-stu-id="96e83-157">String</span></span> | <span data-ttu-id="96e83-158">上次更新指示器的用户/应用程序的标识。</span><span class="sxs-lookup"><span data-stu-id="96e83-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="96e83-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="96e83-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="96e83-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="96e83-160">DateTimeOffset</span></span> | <span data-ttu-id="96e83-161">创建指示器的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="96e83-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="96e83-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="96e83-162">expirationTime</span></span> | <span data-ttu-id="96e83-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="96e83-163">DateTimeOffset</span></span> | <span data-ttu-id="96e83-164">指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="96e83-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="96e83-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="96e83-165">lastUpdateTime</span></span> | <span data-ttu-id="96e83-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="96e83-166">DateTimeOffset</span></span> | <span data-ttu-id="96e83-167">上次更新指示器的时间。</span><span class="sxs-lookup"><span data-stu-id="96e83-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="96e83-168">severity</span><span class="sxs-lookup"><span data-stu-id="96e83-168">severity</span></span> | <span data-ttu-id="96e83-169">枚举</span><span class="sxs-lookup"><span data-stu-id="96e83-169">Enum</span></span> | <span data-ttu-id="96e83-170">指示器的严重性。</span><span class="sxs-lookup"><span data-stu-id="96e83-170">The severity of the indicator.</span></span> <span data-ttu-id="96e83-171">可能的值包括："Informational"、"Low"、"Medium"和"High"。</span><span class="sxs-lookup"><span data-stu-id="96e83-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="96e83-172">title</span><span class="sxs-lookup"><span data-stu-id="96e83-172">title</span></span> | <span data-ttu-id="96e83-173">String</span><span class="sxs-lookup"><span data-stu-id="96e83-173">String</span></span> | <span data-ttu-id="96e83-174">指示器标题。</span><span class="sxs-lookup"><span data-stu-id="96e83-174">Indicator title.</span></span>
<span data-ttu-id="96e83-175">description</span><span class="sxs-lookup"><span data-stu-id="96e83-175">description</span></span> | <span data-ttu-id="96e83-176">String</span><span class="sxs-lookup"><span data-stu-id="96e83-176">String</span></span> | <span data-ttu-id="96e83-177">指示器的说明。</span><span class="sxs-lookup"><span data-stu-id="96e83-177">Description of the indicator.</span></span>
<span data-ttu-id="96e83-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="96e83-178">recommendedActions</span></span> | <span data-ttu-id="96e83-179">String</span><span class="sxs-lookup"><span data-stu-id="96e83-179">String</span></span> | <span data-ttu-id="96e83-180">指示器的建议操作。</span><span class="sxs-lookup"><span data-stu-id="96e83-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="96e83-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="96e83-181">rbacGroupNames</span></span> | <span data-ttu-id="96e83-182">字符串列表</span><span class="sxs-lookup"><span data-stu-id="96e83-182">List of strings</span></span> | <span data-ttu-id="96e83-183">RBAC 设备组名称，其中指示器已公开且处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="96e83-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="96e83-184">空列表，以防它向所有设备公开。</span><span class="sxs-lookup"><span data-stu-id="96e83-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="96e83-185">Json 表示形式</span><span class="sxs-lookup"><span data-stu-id="96e83-185">Json representation</span></span>

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
