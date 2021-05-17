---
title: 载出计算机 API
description: 了解如何使用 API 从 Microsoft Defender for Endpoint 中将设备从设备上载出。
keywords: api， 图形 api， 受支持的 api， 收集调查包
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
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934173"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="61fb9-104">载出计算机 API</span><span class="sxs-lookup"><span data-stu-id="61fb9-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61fb9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="61fb9-105">**Applies to:**</span></span>
- [<span data-ttu-id="61fb9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61fb9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="61fb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61fb9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="61fb9-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="61fb9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61fb9-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="61fb9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="61fb9-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="61fb9-110">API description</span></span>
<span data-ttu-id="61fb9-111">从 Defender for Endpoint 载出设备。</span><span class="sxs-lookup"><span data-stu-id="61fb9-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="61fb9-112">限制</span><span class="sxs-lookup"><span data-stu-id="61fb9-112">Limitations</span></span>
 - <span data-ttu-id="61fb9-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="61fb9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="61fb9-114">此 API 在 Windows 10 版本 1703 及更高版本或 Windows Server 2019 及更高版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="61fb9-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="61fb9-115">此 API 在 MacOS 或 Linux 设备上不受支持。</span><span class="sxs-lookup"><span data-stu-id="61fb9-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="61fb9-116">权限</span><span class="sxs-lookup"><span data-stu-id="61fb9-116">Permissions</span></span>
<span data-ttu-id="61fb9-117">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="61fb9-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="61fb9-118">若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="61fb9-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="61fb9-119">权限类型</span><span class="sxs-lookup"><span data-stu-id="61fb9-119">Permission type</span></span> |   <span data-ttu-id="61fb9-120">权限</span><span class="sxs-lookup"><span data-stu-id="61fb9-120">Permission</span></span>  |   <span data-ttu-id="61fb9-121">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="61fb9-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="61fb9-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="61fb9-122">Application</span></span> |   <span data-ttu-id="61fb9-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="61fb9-123">Machine.Offboard</span></span> |  <span data-ttu-id="61fb9-124">"载出计算机"</span><span class="sxs-lookup"><span data-stu-id="61fb9-124">'Offboard machine'</span></span>
<span data-ttu-id="61fb9-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="61fb9-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="61fb9-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="61fb9-126">Machine.Offboard</span></span> |  <span data-ttu-id="61fb9-127">"载出计算机"</span><span class="sxs-lookup"><span data-stu-id="61fb9-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="61fb9-128">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="61fb9-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="61fb9-129">用户需要"全局管理员"AD 角色</span><span class="sxs-lookup"><span data-stu-id="61fb9-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="61fb9-130">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="61fb9-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="61fb9-131">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="61fb9-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="61fb9-132">请求标头</span><span class="sxs-lookup"><span data-stu-id="61fb9-132">Request headers</span></span>

<span data-ttu-id="61fb9-133">名称</span><span class="sxs-lookup"><span data-stu-id="61fb9-133">Name</span></span> | <span data-ttu-id="61fb9-134">类型</span><span class="sxs-lookup"><span data-stu-id="61fb9-134">Type</span></span> | <span data-ttu-id="61fb9-135">说明</span><span class="sxs-lookup"><span data-stu-id="61fb9-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="61fb9-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="61fb9-136">Authorization</span></span> | <span data-ttu-id="61fb9-137">String</span><span class="sxs-lookup"><span data-stu-id="61fb9-137">String</span></span> | <span data-ttu-id="61fb9-138">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="61fb9-138">Bearer {token}.</span></span> <span data-ttu-id="61fb9-139">**必需**。</span><span class="sxs-lookup"><span data-stu-id="61fb9-139">**Required**.</span></span>
<span data-ttu-id="61fb9-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="61fb9-140">Content-Type</span></span> | <span data-ttu-id="61fb9-141">string</span><span class="sxs-lookup"><span data-stu-id="61fb9-141">string</span></span> | <span data-ttu-id="61fb9-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="61fb9-142">application/json.</span></span> <span data-ttu-id="61fb9-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="61fb9-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="61fb9-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="61fb9-144">Request body</span></span>
<span data-ttu-id="61fb9-145">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="61fb9-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="61fb9-146">参数</span><span class="sxs-lookup"><span data-stu-id="61fb9-146">Parameter</span></span> | <span data-ttu-id="61fb9-147">类型</span><span class="sxs-lookup"><span data-stu-id="61fb9-147">Type</span></span>    | <span data-ttu-id="61fb9-148">说明</span><span class="sxs-lookup"><span data-stu-id="61fb9-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="61fb9-149">评论</span><span class="sxs-lookup"><span data-stu-id="61fb9-149">Comment</span></span> |   <span data-ttu-id="61fb9-150">字符串</span><span class="sxs-lookup"><span data-stu-id="61fb9-150">String</span></span> |    <span data-ttu-id="61fb9-151">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="61fb9-151">Comment to associate with the action.</span></span> <span data-ttu-id="61fb9-152">**必需**。</span><span class="sxs-lookup"><span data-stu-id="61fb9-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="61fb9-153">响应</span><span class="sxs-lookup"><span data-stu-id="61fb9-153">Response</span></span>
<span data-ttu-id="61fb9-154">如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="61fb9-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="61fb9-155">示例</span><span class="sxs-lookup"><span data-stu-id="61fb9-155">Example</span></span>

<span data-ttu-id="61fb9-156">**请求**</span><span class="sxs-lookup"><span data-stu-id="61fb9-156">**Request**</span></span>

<span data-ttu-id="61fb9-157">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="61fb9-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
