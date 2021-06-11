---
title: 取消计算机操作 API
description: 了解如何取消已启动计算机操作
keywords: api、 图形 api、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879666"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="518e2-104">取消计算机操作 API</span><span class="sxs-lookup"><span data-stu-id="518e2-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="518e2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="518e2-105">**Applies to:**</span></span>
- [<span data-ttu-id="518e2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="518e2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="518e2-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="518e2-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="518e2-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="518e2-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="518e2-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="518e2-109">API description</span></span>

<span data-ttu-id="518e2-110">取消尚未在最终状态中启动、已 (、已) 。</span><span class="sxs-lookup"><span data-stu-id="518e2-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="518e2-111">限制</span><span class="sxs-lookup"><span data-stu-id="518e2-111">Limitations</span></span>

1.  <span data-ttu-id="518e2-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="518e2-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="518e2-113">权限</span><span class="sxs-lookup"><span data-stu-id="518e2-113">Permissions</span></span>

<span data-ttu-id="518e2-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="518e2-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="518e2-115">若要了解更多信息，包括如何选择权限，请参阅 [入门](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="518e2-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="518e2-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="518e2-116">Permission    type</span></span>     |     <span data-ttu-id="518e2-117">权限</span><span class="sxs-lookup"><span data-stu-id="518e2-117">Permission</span></span>     |    <span data-ttu-id="518e2-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="518e2-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="518e2-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="518e2-119">Application</span></span>    |    <br><span data-ttu-id="518e2-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="518e2-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="518e2-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="518e2-121">Machine.Isolate</span></span>   <br><span data-ttu-id="518e2-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="518e2-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="518e2-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="518e2-123">Machine.Scan</span></span><br>   <span data-ttu-id="518e2-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="518e2-124">Machine.Offboard</span></span><br>   <span data-ttu-id="518e2-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="518e2-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="518e2-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="518e2-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="518e2-127">收集取证</span><span class="sxs-lookup"><span data-stu-id="518e2-127">Collect   forensics</span></span>   <br><span data-ttu-id="518e2-128">隔离计算机</span><span class="sxs-lookup"><span data-stu-id="518e2-128">Isolate   machine</span></span><br><span data-ttu-id="518e2-129">限制代码执行</span><span class="sxs-lookup"><span data-stu-id="518e2-129">Restrict   code execution</span></span><br>  <span data-ttu-id="518e2-130">扫描计算机</span><span class="sxs-lookup"><span data-stu-id="518e2-130">Scan   machine</span></span><br>  <span data-ttu-id="518e2-131">载出计算机</span><span class="sxs-lookup"><span data-stu-id="518e2-131">Offboard   machine</span></span><br>   <span data-ttu-id="518e2-132">停止和隔离</span><span class="sxs-lookup"><span data-stu-id="518e2-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="518e2-133">在特定的计算机上运行实时响应</span><span class="sxs-lookup"><span data-stu-id="518e2-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="518e2-134">委派 (工作或学校帐户) </span><span class="sxs-lookup"><span data-stu-id="518e2-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="518e2-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="518e2-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="518e2-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="518e2-136">Machine.Isolate</span></span>    <br><span data-ttu-id="518e2-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="518e2-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="518e2-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="518e2-138">Machine.Scan</span></span><br>   <span data-ttu-id="518e2-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="518e2-139">Machine.Offboard</span></span><br>   <span data-ttu-id="518e2-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="518e2-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="518e2-141">收集取证</span><span class="sxs-lookup"><span data-stu-id="518e2-141">Collect   forensics</span></span><br>   <span data-ttu-id="518e2-142">隔离计算机</span><span class="sxs-lookup"><span data-stu-id="518e2-142">Isolate   machine</span></span><br>  <span data-ttu-id="518e2-143">限制代码执行</span><span class="sxs-lookup"><span data-stu-id="518e2-143">Restrict   code execution</span></span><br> <span data-ttu-id="518e2-144">扫描计算机</span><span class="sxs-lookup"><span data-stu-id="518e2-144">Scan   machine</span></span><br><span data-ttu-id="518e2-145">载出计算机</span><span class="sxs-lookup"><span data-stu-id="518e2-145">Offboard   machine</span></span><br> <span data-ttu-id="518e2-146">停止和隔离</span><span class="sxs-lookup"><span data-stu-id="518e2-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="518e2-147">在特定的计算机上运行实时响应</span><span class="sxs-lookup"><span data-stu-id="518e2-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="518e2-148">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="518e2-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="518e2-149">请求标头</span><span class="sxs-lookup"><span data-stu-id="518e2-149">Request headers</span></span>

| <span data-ttu-id="518e2-150">名称</span><span class="sxs-lookup"><span data-stu-id="518e2-150">Name</span></span>      | <span data-ttu-id="518e2-151">类型</span><span class="sxs-lookup"><span data-stu-id="518e2-151">Type</span></span> | <span data-ttu-id="518e2-152">说明</span><span class="sxs-lookup"><span data-stu-id="518e2-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="518e2-153">Authorization</span><span class="sxs-lookup"><span data-stu-id="518e2-153">Authorization</span></span> | <span data-ttu-id="518e2-154">String</span><span class="sxs-lookup"><span data-stu-id="518e2-154">String</span></span>   | <span data-ttu-id="518e2-p103">Bearer {token}。必需。</span><span class="sxs-lookup"><span data-stu-id="518e2-p103">Bearer {token}. Required.</span></span>   |
| <span data-ttu-id="518e2-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="518e2-157">Content-Type</span></span>  | <span data-ttu-id="518e2-158">string</span><span class="sxs-lookup"><span data-stu-id="518e2-158">string</span></span>   | <span data-ttu-id="518e2-p104">application/json. Required.</span><span class="sxs-lookup"><span data-stu-id="518e2-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="518e2-161">请求正文</span><span class="sxs-lookup"><span data-stu-id="518e2-161">Request body</span></span>

| <span data-ttu-id="518e2-162">参数</span><span class="sxs-lookup"><span data-stu-id="518e2-162">Parameter</span></span> | <span data-ttu-id="518e2-163">类型</span><span class="sxs-lookup"><span data-stu-id="518e2-163">Type</span></span> | <span data-ttu-id="518e2-164">说明</span><span class="sxs-lookup"><span data-stu-id="518e2-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="518e2-165">评论</span><span class="sxs-lookup"><span data-stu-id="518e2-165">Comment</span></span>       | <span data-ttu-id="518e2-166">字符串</span><span class="sxs-lookup"><span data-stu-id="518e2-166">String</span></span>   | <span data-ttu-id="518e2-167">要与取消操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="518e2-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="518e2-168">响应</span><span class="sxs-lookup"><span data-stu-id="518e2-168">Response</span></span>

<span data-ttu-id="518e2-169">如果成功，此方法使用 Machine Action 实体返回 200 Ok 响应代码。</span><span class="sxs-lookup"><span data-stu-id="518e2-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="518e2-170">如果未找到具有指定 ID 的机器操作实体 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="518e2-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="518e2-171">示例</span><span class="sxs-lookup"><span data-stu-id="518e2-171">Example</span></span>

<span data-ttu-id="518e2-172">**请求**</span><span class="sxs-lookup"><span data-stu-id="518e2-172">**Request**</span></span>

<span data-ttu-id="518e2-173">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="518e2-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="518e2-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="518e2-174">Related topic</span></span>

- [<span data-ttu-id="518e2-175">获取计算机操作 API</span><span class="sxs-lookup"><span data-stu-id="518e2-175">Get machine action API</span></span>](get-machineaction-object.md)