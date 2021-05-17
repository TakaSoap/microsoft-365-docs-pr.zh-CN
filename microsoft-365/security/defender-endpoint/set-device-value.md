---
title: 设置设备值 API
description: 了解如何使用 Microsoft Defender for Endpoint API 指定设备的值。
keywords: api， 图形 api， 受支持的 api， 标记， 计算机标记
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
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498309"
---
# <a name="set-device-value-api"></a><span data-ttu-id="0be49-104">设置设备值 API</span><span class="sxs-lookup"><span data-stu-id="0be49-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0be49-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0be49-105">**Applies to:**</span></span>
- [<span data-ttu-id="0be49-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0be49-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0be49-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0be49-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="0be49-108">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0be49-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0be49-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0be49-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0be49-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0be49-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0be49-111">API 说明</span><span class="sxs-lookup"><span data-stu-id="0be49-111">API description</span></span>

<span data-ttu-id="0be49-112">设置特定计算机 的设备 [值](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="0be49-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="0be49-113">有关详细信息 [，请参阅分配](tvm-assign-device-value.md) 设备值。</span><span class="sxs-lookup"><span data-stu-id="0be49-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="0be49-114">限制</span><span class="sxs-lookup"><span data-stu-id="0be49-114">Limitations</span></span>

1. <span data-ttu-id="0be49-115">你可以根据配置的保留期在上次看到的设备上发布。</span><span class="sxs-lookup"><span data-stu-id="0be49-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="0be49-116">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="0be49-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0be49-117">权限</span><span class="sxs-lookup"><span data-stu-id="0be49-117">Permissions</span></span>

<span data-ttu-id="0be49-118">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="0be49-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0be49-119">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0be49-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0be49-120">权限类型</span><span class="sxs-lookup"><span data-stu-id="0be49-120">Permission type</span></span> |    <span data-ttu-id="0be49-121">权限</span><span class="sxs-lookup"><span data-stu-id="0be49-121">Permission</span></span>    |    <span data-ttu-id="0be49-122">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="0be49-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0be49-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="0be49-123">Application</span></span> |    <span data-ttu-id="0be49-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0be49-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="0be49-125">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="0be49-125">'Read and write all machine information'</span></span>
<span data-ttu-id="0be49-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="0be49-126">Delegated (work or school account)</span></span> | <span data-ttu-id="0be49-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0be49-127">Machine.ReadWrite</span></span> | <span data-ttu-id="0be49-128">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="0be49-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="0be49-129">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="0be49-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="0be49-130">用户至少需要具有以下角色权限："管理安全性设置"。</span><span class="sxs-lookup"><span data-stu-id="0be49-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="0be49-131">有关详细信息 (请参阅 [创建和管理角色，](user-roles.md) 了解) </span><span class="sxs-lookup"><span data-stu-id="0be49-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0be49-132">用户需要具有计算机访问权限，根据计算机组设置 (请参阅创建和管理计算机组，了解[](machine-groups.md)) </span><span class="sxs-lookup"><span data-stu-id="0be49-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0be49-133">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="0be49-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="0be49-134">请求标头</span><span class="sxs-lookup"><span data-stu-id="0be49-134">Request headers</span></span>

<span data-ttu-id="0be49-135">名称</span><span class="sxs-lookup"><span data-stu-id="0be49-135">Name</span></span> | <span data-ttu-id="0be49-136">类型</span><span class="sxs-lookup"><span data-stu-id="0be49-136">Type</span></span> | <span data-ttu-id="0be49-137">说明</span><span class="sxs-lookup"><span data-stu-id="0be49-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="0be49-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="0be49-138">Authorization</span></span> | <span data-ttu-id="0be49-139">String</span><span class="sxs-lookup"><span data-stu-id="0be49-139">String</span></span> | <span data-ttu-id="0be49-140">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="0be49-140">Bearer {token}.</span></span> <span data-ttu-id="0be49-141">**必需**。</span><span class="sxs-lookup"><span data-stu-id="0be49-141">**Required**.</span></span>
<span data-ttu-id="0be49-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="0be49-142">Content-Type</span></span> | <span data-ttu-id="0be49-143">string</span><span class="sxs-lookup"><span data-stu-id="0be49-143">string</span></span> | <span data-ttu-id="0be49-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="0be49-144">application/json.</span></span> <span data-ttu-id="0be49-145">**必需**。</span><span class="sxs-lookup"><span data-stu-id="0be49-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0be49-146">请求正文</span><span class="sxs-lookup"><span data-stu-id="0be49-146">Request body</span></span>

<span data-ttu-id="0be49-147">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="0be49-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="0be49-148">参数</span><span class="sxs-lookup"><span data-stu-id="0be49-148">Parameter</span></span> |    <span data-ttu-id="0be49-149">类型</span><span class="sxs-lookup"><span data-stu-id="0be49-149">Type</span></span>    | <span data-ttu-id="0be49-150">说明</span><span class="sxs-lookup"><span data-stu-id="0be49-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="0be49-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="0be49-151">DeviceValue</span></span> |    <span data-ttu-id="0be49-152">枚举</span><span class="sxs-lookup"><span data-stu-id="0be49-152">Enum</span></span> |    <span data-ttu-id="0be49-153">设备值。</span><span class="sxs-lookup"><span data-stu-id="0be49-153">Device value.</span></span> <span data-ttu-id="0be49-154">允许的值包括："Normal"、"Low"和"High"。</span><span class="sxs-lookup"><span data-stu-id="0be49-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="0be49-155">**必需**。</span><span class="sxs-lookup"><span data-stu-id="0be49-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="0be49-156">响应</span><span class="sxs-lookup"><span data-stu-id="0be49-156">Response</span></span>

<span data-ttu-id="0be49-157">如果成功，此方法在响应正文中返回 200 - 正常响应代码和更新的 Machine。</span><span class="sxs-lookup"><span data-stu-id="0be49-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="0be49-158">示例</span><span class="sxs-lookup"><span data-stu-id="0be49-158">Example</span></span>

<span data-ttu-id="0be49-159">**请求**</span><span class="sxs-lookup"><span data-stu-id="0be49-159">**Request**</span></span>

<span data-ttu-id="0be49-160">下面是添加计算机标记的请求示例。</span><span class="sxs-lookup"><span data-stu-id="0be49-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
