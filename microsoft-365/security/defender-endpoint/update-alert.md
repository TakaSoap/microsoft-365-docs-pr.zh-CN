---
title: 更新警报实体 API
description: 了解如何使用此 API 更新 Microsoft Defender for Endpoint 警报。 可以更新状态、确定、分类和 assignedTo 属性。
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
ms.openlocfilehash: 94be185bd30cd36f456a66d5ae30a4361abc0c48
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688245"
---
# <a name="update-alert"></a><span data-ttu-id="4e8b7-105">更新警报</span><span class="sxs-lookup"><span data-stu-id="4e8b7-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4e8b7-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4e8b7-106">**Applies to:**</span></span>
- [<span data-ttu-id="4e8b7-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4e8b7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4e8b7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e8b7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4e8b7-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4e8b7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4e8b7-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4e8b7-111">API 说明</span><span class="sxs-lookup"><span data-stu-id="4e8b7-111">API description</span></span>
<span data-ttu-id="4e8b7-112">更新现有警报 [的属性](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="4e8b7-113">提供 **或不** 更新属性的注释提交。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="4e8b7-114">可更新的属性包括 ```status``` ：、 ```determination``` 和 ```classification``` ```assignedTo``` 。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="4e8b7-115">限制</span><span class="sxs-lookup"><span data-stu-id="4e8b7-115">Limitations</span></span>
1. <span data-ttu-id="4e8b7-116">你可以更新 API 中可用的警报。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="4e8b7-117">有关详细信息 [，请参阅列出](get-alerts.md) 警报。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="4e8b7-118">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4e8b7-119">权限</span><span class="sxs-lookup"><span data-stu-id="4e8b7-119">Permissions</span></span>
<span data-ttu-id="4e8b7-120">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4e8b7-121">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4e8b7-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4e8b7-122">权限类型</span><span class="sxs-lookup"><span data-stu-id="4e8b7-122">Permission type</span></span> |   <span data-ttu-id="4e8b7-123">权限</span><span class="sxs-lookup"><span data-stu-id="4e8b7-123">Permission</span></span>  |   <span data-ttu-id="4e8b7-124">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="4e8b7-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4e8b7-125">应用程序</span><span class="sxs-lookup"><span data-stu-id="4e8b7-125">Application</span></span> |   <span data-ttu-id="4e8b7-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4e8b7-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="4e8b7-127">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="4e8b7-127">'Read and write all alerts'</span></span>
<span data-ttu-id="4e8b7-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="4e8b7-128">Delegated (work or school account)</span></span> | <span data-ttu-id="4e8b7-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4e8b7-129">Alert.ReadWrite</span></span> | <span data-ttu-id="4e8b7-130">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="4e8b7-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="4e8b7-131">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="4e8b7-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4e8b7-132">用户至少需要具有以下角色权限："警报调查" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4e8b7-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4e8b7-133">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="4e8b7-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4e8b7-134">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="4e8b7-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="4e8b7-135">请求标头</span><span class="sxs-lookup"><span data-stu-id="4e8b7-135">Request headers</span></span>

<span data-ttu-id="4e8b7-136">名称</span><span class="sxs-lookup"><span data-stu-id="4e8b7-136">Name</span></span> | <span data-ttu-id="4e8b7-137">类型</span><span class="sxs-lookup"><span data-stu-id="4e8b7-137">Type</span></span> | <span data-ttu-id="4e8b7-138">说明</span><span class="sxs-lookup"><span data-stu-id="4e8b7-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="4e8b7-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="4e8b7-139">Authorization</span></span> | <span data-ttu-id="4e8b7-140">String</span><span class="sxs-lookup"><span data-stu-id="4e8b7-140">String</span></span> | <span data-ttu-id="4e8b7-141">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-141">Bearer {token}.</span></span> <span data-ttu-id="4e8b7-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-142">**Required**.</span></span>
<span data-ttu-id="4e8b7-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4e8b7-143">Content-Type</span></span> | <span data-ttu-id="4e8b7-144">String</span><span class="sxs-lookup"><span data-stu-id="4e8b7-144">String</span></span> | <span data-ttu-id="4e8b7-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="4e8b7-145">application/json.</span></span> <span data-ttu-id="4e8b7-146">**必需**。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4e8b7-147">请求正文</span><span class="sxs-lookup"><span data-stu-id="4e8b7-147">Request body</span></span>
<span data-ttu-id="4e8b7-148">在请求正文中，提供应更新的相关字段的值。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="4e8b7-149">请求正文中不包括的现有属性将保留其以前的值，或根据对其他属性值的更改重新计算。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="4e8b7-150">为获得最佳性能，不应包含尚未更改的现有值。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="4e8b7-151">属性</span><span class="sxs-lookup"><span data-stu-id="4e8b7-151">Property</span></span> | <span data-ttu-id="4e8b7-152">类型</span><span class="sxs-lookup"><span data-stu-id="4e8b7-152">Type</span></span> | <span data-ttu-id="4e8b7-153">说明</span><span class="sxs-lookup"><span data-stu-id="4e8b7-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="4e8b7-154">状态</span><span class="sxs-lookup"><span data-stu-id="4e8b7-154">status</span></span> | <span data-ttu-id="4e8b7-155">String</span><span class="sxs-lookup"><span data-stu-id="4e8b7-155">String</span></span> | <span data-ttu-id="4e8b7-156">指定警报的当前状态。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="4e8b7-157">属性值为："New"、InProgress 和"Resolved"。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="4e8b7-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="4e8b7-158">assignedTo</span></span> | <span data-ttu-id="4e8b7-159">String</span><span class="sxs-lookup"><span data-stu-id="4e8b7-159">String</span></span> | <span data-ttu-id="4e8b7-160">警报的所有者</span><span class="sxs-lookup"><span data-stu-id="4e8b7-160">Owner of the alert</span></span>
<span data-ttu-id="4e8b7-161">classification</span><span class="sxs-lookup"><span data-stu-id="4e8b7-161">classification</span></span> | <span data-ttu-id="4e8b7-162">字符串</span><span class="sxs-lookup"><span data-stu-id="4e8b7-162">String</span></span> | <span data-ttu-id="4e8b7-163">指定警报的规范。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="4e8b7-164">属性值为："Unknown"、"FalsePositive"和"TruePositive"。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="4e8b7-165">确定</span><span class="sxs-lookup"><span data-stu-id="4e8b7-165">determination</span></span> | <span data-ttu-id="4e8b7-166">String</span><span class="sxs-lookup"><span data-stu-id="4e8b7-166">String</span></span> | <span data-ttu-id="4e8b7-167">指定警报的确定。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="4e8b7-168">属性值包括："NotAvailable"、"Apt"、"Malware"、SecurityPersonnel、"SecurityTesting"、"UnwantedSoftware"和"Other"</span><span class="sxs-lookup"><span data-stu-id="4e8b7-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="4e8b7-169">注释</span><span class="sxs-lookup"><span data-stu-id="4e8b7-169">comment</span></span> | <span data-ttu-id="4e8b7-170">String</span><span class="sxs-lookup"><span data-stu-id="4e8b7-170">String</span></span> | <span data-ttu-id="4e8b7-171">要添加到警报的注释。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="4e8b7-172">响应</span><span class="sxs-lookup"><span data-stu-id="4e8b7-172">Response</span></span>
<span data-ttu-id="4e8b7-173">如果成功，此方法在响应正文中返回 200 OK 和 [alert](alerts.md) 实体以及更新的属性。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="4e8b7-174">如果未找到具有指定 ID 的警报 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4e8b7-175">示例</span><span class="sxs-lookup"><span data-stu-id="4e8b7-175">Example</span></span>

<span data-ttu-id="4e8b7-176">**请求**</span><span class="sxs-lookup"><span data-stu-id="4e8b7-176">**Request**</span></span>

<span data-ttu-id="4e8b7-177">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="4e8b7-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
