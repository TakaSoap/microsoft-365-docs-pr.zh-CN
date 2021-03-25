---
title: 批更新警报实体 API
description: 了解如何使用此 API 批量更新 Microsoft Defender 终结点警报。 可以更新状态、确定、分类和 assignedTo 属性。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 信息， id
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
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166448"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="276fc-105">批更新通知</span><span class="sxs-lookup"><span data-stu-id="276fc-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="276fc-106">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="276fc-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="276fc-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="276fc-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="276fc-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="276fc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="276fc-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="276fc-109">API description</span></span>
<span data-ttu-id="276fc-110">更新一批现有 [警报的属性](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="276fc-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="276fc-111">提供 **或不** 更新属性的注释提交。</span><span class="sxs-lookup"><span data-stu-id="276fc-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="276fc-112">可更新的属性包括 `status` ：、 `determination` 和 `classification` `assignedTo` 。</span><span class="sxs-lookup"><span data-stu-id="276fc-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="276fc-113">限制</span><span class="sxs-lookup"><span data-stu-id="276fc-113">Limitations</span></span>
1. <span data-ttu-id="276fc-114">你可以更新 API 中可用的警报。</span><span class="sxs-lookup"><span data-stu-id="276fc-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="276fc-115">有关详细信息 [，请参阅列出](get-alerts.md) 警报。</span><span class="sxs-lookup"><span data-stu-id="276fc-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="276fc-116">此 API 的速率限制是每分钟 10 个调用和每小时 500 个调用。</span><span class="sxs-lookup"><span data-stu-id="276fc-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="276fc-117">权限</span><span class="sxs-lookup"><span data-stu-id="276fc-117">Permissions</span></span>
<span data-ttu-id="276fc-118">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="276fc-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="276fc-119">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="276fc-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="276fc-120">权限类型</span><span class="sxs-lookup"><span data-stu-id="276fc-120">Permission type</span></span> |   <span data-ttu-id="276fc-121">权限</span><span class="sxs-lookup"><span data-stu-id="276fc-121">Permission</span></span>  |   <span data-ttu-id="276fc-122">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="276fc-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="276fc-123">Application</span><span class="sxs-lookup"><span data-stu-id="276fc-123">Application</span></span> |   <span data-ttu-id="276fc-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="276fc-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="276fc-125">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="276fc-125">'Read and write all alerts'</span></span>
<span data-ttu-id="276fc-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="276fc-126">Delegated (work or school account)</span></span> | <span data-ttu-id="276fc-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="276fc-127">Alert.ReadWrite</span></span> | <span data-ttu-id="276fc-128">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="276fc-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="276fc-129">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="276fc-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="276fc-130">用户至少需要具有以下角色权限："警报调查" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="276fc-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="276fc-131">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="276fc-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="276fc-132">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="276fc-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="276fc-133">请求标头</span><span class="sxs-lookup"><span data-stu-id="276fc-133">Request headers</span></span>

<span data-ttu-id="276fc-134">名称</span><span class="sxs-lookup"><span data-stu-id="276fc-134">Name</span></span> | <span data-ttu-id="276fc-135">类型</span><span class="sxs-lookup"><span data-stu-id="276fc-135">Type</span></span> | <span data-ttu-id="276fc-136">说明</span><span class="sxs-lookup"><span data-stu-id="276fc-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="276fc-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="276fc-137">Authorization</span></span> | <span data-ttu-id="276fc-138">String</span><span class="sxs-lookup"><span data-stu-id="276fc-138">String</span></span> | <span data-ttu-id="276fc-139">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="276fc-139">Bearer {token}.</span></span> <span data-ttu-id="276fc-140">**必需**。</span><span class="sxs-lookup"><span data-stu-id="276fc-140">**Required**.</span></span>
<span data-ttu-id="276fc-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="276fc-141">Content-Type</span></span> | <span data-ttu-id="276fc-142">String</span><span class="sxs-lookup"><span data-stu-id="276fc-142">String</span></span> | <span data-ttu-id="276fc-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="276fc-143">application/json.</span></span> <span data-ttu-id="276fc-144">**必需**。</span><span class="sxs-lookup"><span data-stu-id="276fc-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="276fc-145">请求正文</span><span class="sxs-lookup"><span data-stu-id="276fc-145">Request body</span></span>
<span data-ttu-id="276fc-146">在请求正文中，提供要更新的警报的 ID 以及要针对这些警报更新的相关字段的值。</span><span class="sxs-lookup"><span data-stu-id="276fc-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="276fc-147">请求正文中不包括的现有属性将保留其以前的值，或根据对其他属性值的更改重新计算。</span><span class="sxs-lookup"><span data-stu-id="276fc-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="276fc-148">为了实现最佳性能，不得添加未变化的现有值。</span><span class="sxs-lookup"><span data-stu-id="276fc-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="276fc-149">属性</span><span class="sxs-lookup"><span data-stu-id="276fc-149">Property</span></span> | <span data-ttu-id="276fc-150">类型</span><span class="sxs-lookup"><span data-stu-id="276fc-150">Type</span></span> | <span data-ttu-id="276fc-151">说明</span><span class="sxs-lookup"><span data-stu-id="276fc-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="276fc-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="276fc-152">alertIds</span></span> | <span data-ttu-id="276fc-153">列表 &lt; 字符串&gt;</span><span class="sxs-lookup"><span data-stu-id="276fc-153">List&lt;String&gt;</span></span>| <span data-ttu-id="276fc-154">要更新的警报的 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="276fc-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="276fc-155">**必需**</span><span class="sxs-lookup"><span data-stu-id="276fc-155">**Required**</span></span>
<span data-ttu-id="276fc-156">状态</span><span class="sxs-lookup"><span data-stu-id="276fc-156">status</span></span> | <span data-ttu-id="276fc-157">String</span><span class="sxs-lookup"><span data-stu-id="276fc-157">String</span></span> | <span data-ttu-id="276fc-158">指定指定警报的更新状态。</span><span class="sxs-lookup"><span data-stu-id="276fc-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="276fc-159">属性值为："New"、InProgress 和"Resolved"。</span><span class="sxs-lookup"><span data-stu-id="276fc-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="276fc-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="276fc-160">assignedTo</span></span> | <span data-ttu-id="276fc-161">String</span><span class="sxs-lookup"><span data-stu-id="276fc-161">String</span></span> | <span data-ttu-id="276fc-162">指定警报的所有者</span><span class="sxs-lookup"><span data-stu-id="276fc-162">Owner of the specified alerts</span></span>
<span data-ttu-id="276fc-163">classification</span><span class="sxs-lookup"><span data-stu-id="276fc-163">classification</span></span> | <span data-ttu-id="276fc-164">字符串</span><span class="sxs-lookup"><span data-stu-id="276fc-164">String</span></span> | <span data-ttu-id="276fc-165">指定指定警报的规范。</span><span class="sxs-lookup"><span data-stu-id="276fc-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="276fc-166">属性值为："Unknown"、"FalsePositive"和"TruePositive"。</span><span class="sxs-lookup"><span data-stu-id="276fc-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="276fc-167">确定</span><span class="sxs-lookup"><span data-stu-id="276fc-167">determination</span></span> | <span data-ttu-id="276fc-168">String</span><span class="sxs-lookup"><span data-stu-id="276fc-168">String</span></span> | <span data-ttu-id="276fc-169">指定指定警报的确定。</span><span class="sxs-lookup"><span data-stu-id="276fc-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="276fc-170">属性值包括："NotAvailable"、"Apt"、"Malware"、SecurityPersonnel、"SecurityTesting"、"UnwantedSoftware"和"Other"</span><span class="sxs-lookup"><span data-stu-id="276fc-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="276fc-171">注释</span><span class="sxs-lookup"><span data-stu-id="276fc-171">comment</span></span> | <span data-ttu-id="276fc-172">String</span><span class="sxs-lookup"><span data-stu-id="276fc-172">String</span></span> | <span data-ttu-id="276fc-173">要添加到指定警报的注释。</span><span class="sxs-lookup"><span data-stu-id="276fc-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="276fc-174">响应</span><span class="sxs-lookup"><span data-stu-id="276fc-174">Response</span></span>
<span data-ttu-id="276fc-175">如果成功，此方法返回 200 OK，响应正文为空。</span><span class="sxs-lookup"><span data-stu-id="276fc-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="276fc-176">示例</span><span class="sxs-lookup"><span data-stu-id="276fc-176">Example</span></span>

<span data-ttu-id="276fc-177">**请求**</span><span class="sxs-lookup"><span data-stu-id="276fc-177">**Request**</span></span>

<span data-ttu-id="276fc-178">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="276fc-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
