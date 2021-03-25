---
title: 删除应用限制 API
description: 使用此 API 创建与删除应用程序执行限制相关的调用。
keywords: api， 图形 api， 受支持的 api， 从隔离中删除设备
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
ms.openlocfilehash: abff4e02bfdfe6f5598ca96121815930dce3c85e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199317"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="a4213-104">删除应用限制 API</span><span class="sxs-lookup"><span data-stu-id="a4213-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4213-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a4213-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4213-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a4213-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a4213-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4213-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4213-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a4213-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a4213-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a4213-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a4213-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="a4213-110">API description</span></span>
<span data-ttu-id="a4213-111">在设备上启用执行任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="a4213-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="a4213-112">限制</span><span class="sxs-lookup"><span data-stu-id="a4213-112">Limitations</span></span>
1. <span data-ttu-id="a4213-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="a4213-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="a4213-114">权限</span><span class="sxs-lookup"><span data-stu-id="a4213-114">Permissions</span></span>
<span data-ttu-id="a4213-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="a4213-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a4213-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a4213-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a4213-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="a4213-117">Permission type</span></span> |   <span data-ttu-id="a4213-118">权限</span><span class="sxs-lookup"><span data-stu-id="a4213-118">Permission</span></span>  |   <span data-ttu-id="a4213-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="a4213-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a4213-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="a4213-120">Application</span></span> |   <span data-ttu-id="a4213-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="a4213-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="a4213-122">"限制代码执行"</span><span class="sxs-lookup"><span data-stu-id="a4213-122">'Restrict code execution'</span></span>
<span data-ttu-id="a4213-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="a4213-123">Delegated (work or school account)</span></span> | <span data-ttu-id="a4213-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="a4213-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="a4213-125">"限制代码执行"</span><span class="sxs-lookup"><span data-stu-id="a4213-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="a4213-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="a4213-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a4213-127">用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a4213-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a4213-128">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="a4213-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a4213-129">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="a4213-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="a4213-130">请求标头</span><span class="sxs-lookup"><span data-stu-id="a4213-130">Request headers</span></span>
<span data-ttu-id="a4213-131">名称</span><span class="sxs-lookup"><span data-stu-id="a4213-131">Name</span></span> | <span data-ttu-id="a4213-132">类型</span><span class="sxs-lookup"><span data-stu-id="a4213-132">Type</span></span> | <span data-ttu-id="a4213-133">说明</span><span class="sxs-lookup"><span data-stu-id="a4213-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a4213-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="a4213-134">Authorization</span></span> | <span data-ttu-id="a4213-135">字符串</span><span class="sxs-lookup"><span data-stu-id="a4213-135">String</span></span> | <span data-ttu-id="a4213-136">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="a4213-136">Bearer {token}.</span></span> <span data-ttu-id="a4213-137">**必需**。</span><span class="sxs-lookup"><span data-stu-id="a4213-137">**Required**.</span></span>
<span data-ttu-id="a4213-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a4213-138">Content-Type</span></span> | <span data-ttu-id="a4213-139">string</span><span class="sxs-lookup"><span data-stu-id="a4213-139">string</span></span> | <span data-ttu-id="a4213-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="a4213-140">application/json.</span></span> <span data-ttu-id="a4213-141">**必需**。</span><span class="sxs-lookup"><span data-stu-id="a4213-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a4213-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="a4213-142">Request body</span></span>
<span data-ttu-id="a4213-143">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="a4213-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a4213-144">参数</span><span class="sxs-lookup"><span data-stu-id="a4213-144">Parameter</span></span> | <span data-ttu-id="a4213-145">类型</span><span class="sxs-lookup"><span data-stu-id="a4213-145">Type</span></span>    | <span data-ttu-id="a4213-146">说明</span><span class="sxs-lookup"><span data-stu-id="a4213-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="a4213-147">评论</span><span class="sxs-lookup"><span data-stu-id="a4213-147">Comment</span></span> |   <span data-ttu-id="a4213-148">字符串</span><span class="sxs-lookup"><span data-stu-id="a4213-148">String</span></span> | <span data-ttu-id="a4213-149">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="a4213-149">Comment to associate with the action.</span></span> <span data-ttu-id="a4213-150">**必需**。</span><span class="sxs-lookup"><span data-stu-id="a4213-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="a4213-151">响应</span><span class="sxs-lookup"><span data-stu-id="a4213-151">Response</span></span>
<span data-ttu-id="a4213-152">如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="a4213-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="a4213-153">示例</span><span class="sxs-lookup"><span data-stu-id="a4213-153">Example</span></span>

<span data-ttu-id="a4213-154">**请求**</span><span class="sxs-lookup"><span data-stu-id="a4213-154">**Request**</span></span>

<span data-ttu-id="a4213-155">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="a4213-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="a4213-156">若要限制设备上的代码执行，请参阅限制 [应用执行](restrict-code-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="a4213-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>
