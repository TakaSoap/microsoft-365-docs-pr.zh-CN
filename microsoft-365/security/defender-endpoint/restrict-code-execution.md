---
title: 限制应用执行 API
description: 使用此 API 创建与限制应用程序执行相关的调用。
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
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186771"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="bbb75-104">限制应用执行 API</span><span class="sxs-lookup"><span data-stu-id="bbb75-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbb75-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bbb75-105">**Applies to:**</span></span>
- [<span data-ttu-id="bbb75-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbb75-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbb75-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbb75-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bbb75-108">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bbb75-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bbb75-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bbb75-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbb75-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="bbb75-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bbb75-111">API 说明</span><span class="sxs-lookup"><span data-stu-id="bbb75-111">API description</span></span>
<span data-ttu-id="bbb75-112">限制设备上除预定义集之外的所有应用程序的执行。</span><span class="sxs-lookup"><span data-stu-id="bbb75-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="bbb75-113">限制</span><span class="sxs-lookup"><span data-stu-id="bbb75-113">Limitations</span></span>
1. <span data-ttu-id="bbb75-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="bbb75-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="bbb75-115">权限</span><span class="sxs-lookup"><span data-stu-id="bbb75-115">Permissions</span></span>
<span data-ttu-id="bbb75-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="bbb75-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bbb75-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bbb75-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bbb75-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="bbb75-118">Permission type</span></span> |   <span data-ttu-id="bbb75-119">权限</span><span class="sxs-lookup"><span data-stu-id="bbb75-119">Permission</span></span>  |   <span data-ttu-id="bbb75-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="bbb75-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bbb75-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="bbb75-121">Application</span></span> |   <span data-ttu-id="bbb75-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="bbb75-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="bbb75-123">"限制代码执行"</span><span class="sxs-lookup"><span data-stu-id="bbb75-123">'Restrict code execution'</span></span>
<span data-ttu-id="bbb75-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="bbb75-124">Delegated (work or school account)</span></span> | <span data-ttu-id="bbb75-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="bbb75-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="bbb75-126">"限制代码执行"</span><span class="sxs-lookup"><span data-stu-id="bbb75-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="bbb75-127">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="bbb75-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bbb75-128">用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="bbb75-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="bbb75-129">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="bbb75-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bbb75-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="bbb75-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="bbb75-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="bbb75-131">Request headers</span></span>

<span data-ttu-id="bbb75-132">名称</span><span class="sxs-lookup"><span data-stu-id="bbb75-132">Name</span></span> | <span data-ttu-id="bbb75-133">类型</span><span class="sxs-lookup"><span data-stu-id="bbb75-133">Type</span></span> | <span data-ttu-id="bbb75-134">说明</span><span class="sxs-lookup"><span data-stu-id="bbb75-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="bbb75-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="bbb75-135">Authorization</span></span> | <span data-ttu-id="bbb75-136">String</span><span class="sxs-lookup"><span data-stu-id="bbb75-136">String</span></span> | <span data-ttu-id="bbb75-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="bbb75-137">Bearer {token}.</span></span> <span data-ttu-id="bbb75-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="bbb75-138">**Required**.</span></span>
<span data-ttu-id="bbb75-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bbb75-139">Content-Type</span></span> | <span data-ttu-id="bbb75-140">string</span><span class="sxs-lookup"><span data-stu-id="bbb75-140">string</span></span> | <span data-ttu-id="bbb75-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="bbb75-141">application/json.</span></span> <span data-ttu-id="bbb75-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="bbb75-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bbb75-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="bbb75-143">Request body</span></span>
<span data-ttu-id="bbb75-144">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="bbb75-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bbb75-145">参数</span><span class="sxs-lookup"><span data-stu-id="bbb75-145">Parameter</span></span> | <span data-ttu-id="bbb75-146">类型</span><span class="sxs-lookup"><span data-stu-id="bbb75-146">Type</span></span>    | <span data-ttu-id="bbb75-147">说明</span><span class="sxs-lookup"><span data-stu-id="bbb75-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="bbb75-148">评论</span><span class="sxs-lookup"><span data-stu-id="bbb75-148">Comment</span></span> |   <span data-ttu-id="bbb75-149">字符串</span><span class="sxs-lookup"><span data-stu-id="bbb75-149">String</span></span> |    <span data-ttu-id="bbb75-150">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="bbb75-150">Comment to associate with the action.</span></span> <span data-ttu-id="bbb75-151">**必需**。</span><span class="sxs-lookup"><span data-stu-id="bbb75-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bbb75-152">响应</span><span class="sxs-lookup"><span data-stu-id="bbb75-152">Response</span></span>
<span data-ttu-id="bbb75-153">如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="bbb75-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="bbb75-154">示例</span><span class="sxs-lookup"><span data-stu-id="bbb75-154">Example</span></span>

<span data-ttu-id="bbb75-155">**请求**</span><span class="sxs-lookup"><span data-stu-id="bbb75-155">**Request**</span></span>

<span data-ttu-id="bbb75-156">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="bbb75-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="bbb75-157">若要从设备中删除代码执行限制，请参阅删除 [应用限制](unrestrict-code-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb75-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
