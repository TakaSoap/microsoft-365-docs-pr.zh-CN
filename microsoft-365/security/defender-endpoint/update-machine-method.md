---
title: 更新计算机实体 API
description: 了解如何使用此 API 更新计算机标记。 你可以更新标记和设备值属性。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985570"
---
# <a name="update-machine"></a><span data-ttu-id="8b73f-105">更新计算机</span><span class="sxs-lookup"><span data-stu-id="8b73f-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8b73f-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8b73f-106">**Applies to:**</span></span>
- [<span data-ttu-id="8b73f-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8b73f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="8b73f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b73f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8b73f-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8b73f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8b73f-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8b73f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8b73f-111">API 说明</span><span class="sxs-lookup"><span data-stu-id="8b73f-111">API description</span></span>
<span data-ttu-id="8b73f-112">更新现有 [Machine 的属性](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="8b73f-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="8b73f-113">可更新的属性包括： ```machineTags``` 和 ```deviceValue``` 。</span><span class="sxs-lookup"><span data-stu-id="8b73f-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="8b73f-114">限制</span><span class="sxs-lookup"><span data-stu-id="8b73f-114">Limitations</span></span>
1. <span data-ttu-id="8b73f-115">你可以更新 API 中可用的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b73f-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="8b73f-116">更新计算机仅将标记追加到标记集合。</span><span class="sxs-lookup"><span data-stu-id="8b73f-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="8b73f-117">如果存在标记，则必须在正文的标记集合中包含这些标记。</span><span class="sxs-lookup"><span data-stu-id="8b73f-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="8b73f-118">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="8b73f-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8b73f-119">权限</span><span class="sxs-lookup"><span data-stu-id="8b73f-119">Permissions</span></span>
<span data-ttu-id="8b73f-120">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="8b73f-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8b73f-121">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8b73f-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8b73f-122">权限类型</span><span class="sxs-lookup"><span data-stu-id="8b73f-122">Permission type</span></span> |   <span data-ttu-id="8b73f-123">权限</span><span class="sxs-lookup"><span data-stu-id="8b73f-123">Permission</span></span>  |   <span data-ttu-id="8b73f-124">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="8b73f-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8b73f-125">应用程序</span><span class="sxs-lookup"><span data-stu-id="8b73f-125">Application</span></span> |   <span data-ttu-id="8b73f-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8b73f-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="8b73f-127">"读取和写入所有计算机的计算机信息"</span><span class="sxs-lookup"><span data-stu-id="8b73f-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="8b73f-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="8b73f-128">Delegated (work or school account)</span></span> | <span data-ttu-id="8b73f-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8b73f-129">Machine.ReadWrite</span></span> | <span data-ttu-id="8b73f-130">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="8b73f-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="8b73f-131">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="8b73f-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8b73f-132">用户至少需要具有以下角色权限："警报调查"。</span><span class="sxs-lookup"><span data-stu-id="8b73f-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="8b73f-133">有关详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8b73f-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="8b73f-134">用户需要根据设备组设置访问与警报关联的设备。</span><span class="sxs-lookup"><span data-stu-id="8b73f-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="8b73f-135">有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="8b73f-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="8b73f-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="8b73f-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="8b73f-137">请求标头</span><span class="sxs-lookup"><span data-stu-id="8b73f-137">Request headers</span></span>

<span data-ttu-id="8b73f-138">名称</span><span class="sxs-lookup"><span data-stu-id="8b73f-138">Name</span></span> | <span data-ttu-id="8b73f-139">类型</span><span class="sxs-lookup"><span data-stu-id="8b73f-139">Type</span></span> | <span data-ttu-id="8b73f-140">说明</span><span class="sxs-lookup"><span data-stu-id="8b73f-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="8b73f-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="8b73f-141">Authorization</span></span> | <span data-ttu-id="8b73f-142">String</span><span class="sxs-lookup"><span data-stu-id="8b73f-142">String</span></span> | <span data-ttu-id="8b73f-143">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="8b73f-143">Bearer {token}.</span></span> <span data-ttu-id="8b73f-144">**必需**。</span><span class="sxs-lookup"><span data-stu-id="8b73f-144">**Required**.</span></span>
<span data-ttu-id="8b73f-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8b73f-145">Content-Type</span></span> | <span data-ttu-id="8b73f-146">String</span><span class="sxs-lookup"><span data-stu-id="8b73f-146">String</span></span> | <span data-ttu-id="8b73f-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="8b73f-147">application/json.</span></span> <span data-ttu-id="8b73f-148">**必需**。</span><span class="sxs-lookup"><span data-stu-id="8b73f-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8b73f-149">请求正文</span><span class="sxs-lookup"><span data-stu-id="8b73f-149">Request body</span></span>
<span data-ttu-id="8b73f-150">在请求正文中，提供应更新的相关字段的值。</span><span class="sxs-lookup"><span data-stu-id="8b73f-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="8b73f-151">请求正文中不包括的现有属性将保留其以前的值，或根据对其他属性值的更改重新计算。</span><span class="sxs-lookup"><span data-stu-id="8b73f-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="8b73f-152">为获得最佳性能，不应包含尚未更改的现有值。</span><span class="sxs-lookup"><span data-stu-id="8b73f-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="8b73f-153">属性</span><span class="sxs-lookup"><span data-stu-id="8b73f-153">Property</span></span> | <span data-ttu-id="8b73f-154">类型</span><span class="sxs-lookup"><span data-stu-id="8b73f-154">Type</span></span> | <span data-ttu-id="8b73f-155">说明</span><span class="sxs-lookup"><span data-stu-id="8b73f-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="8b73f-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="8b73f-156">machineTags</span></span> | <span data-ttu-id="8b73f-157">字符串集合</span><span class="sxs-lookup"><span data-stu-id="8b73f-157">String collection</span></span> | <span data-ttu-id="8b73f-158">计算机 [标记](machine.md) 集。</span><span class="sxs-lookup"><span data-stu-id="8b73f-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="8b73f-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="8b73f-159">deviceValue</span></span> | <span data-ttu-id="8b73f-160">Nullable Enum</span><span class="sxs-lookup"><span data-stu-id="8b73f-160">Nullable Enum</span></span> | <span data-ttu-id="8b73f-161">[设备 的值](tvm-assign-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="8b73f-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="8b73f-162">可能的值包括："Normal"、"Low"和"High"。</span><span class="sxs-lookup"><span data-stu-id="8b73f-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="8b73f-163">响应</span><span class="sxs-lookup"><span data-stu-id="8b73f-163">Response</span></span>
<span data-ttu-id="8b73f-164">如果成功，此方法在响应正文中返回 200 OK 和 [计算机](machine.md) 实体以及更新的属性。</span><span class="sxs-lookup"><span data-stu-id="8b73f-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="8b73f-165">如果正文中的计算机标记集合不包含现有计算机标记 - 400"输入无效"，并且有消息通知缺少标记/s。</span><span class="sxs-lookup"><span data-stu-id="8b73f-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="8b73f-166">如果未找到具有指定 ID 的机器 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="8b73f-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8b73f-167">示例</span><span class="sxs-lookup"><span data-stu-id="8b73f-167">Example</span></span>

<span data-ttu-id="8b73f-168">**请求**</span><span class="sxs-lookup"><span data-stu-id="8b73f-168">**Request**</span></span>

<span data-ttu-id="8b73f-169">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="8b73f-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
