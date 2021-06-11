---
title: 获取事件 API
description: 了解如何使用 Get incidents API 在 Microsoft 365 Defender 中获取单个事件。
keywords: api， 图形 api， 受支持的 api， 获取， 文件， 哈希
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
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888442"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="2de8e-104">获取事件信息 API</span><span class="sxs-lookup"><span data-stu-id="2de8e-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2de8e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2de8e-105">**Applies to:**</span></span>
- [<span data-ttu-id="2de8e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2de8e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2de8e-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2de8e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2de8e-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2de8e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2de8e-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="2de8e-109">API description</span></span>
<span data-ttu-id="2de8e-110">按 ID 检索特定事件</span><span class="sxs-lookup"><span data-stu-id="2de8e-110">Retrieves a specific incident by its ID</span></span>


## <a name="limitations"></a><span data-ttu-id="2de8e-111">限制</span><span class="sxs-lookup"><span data-stu-id="2de8e-111">Limitations</span></span>
1. <span data-ttu-id="2de8e-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="2de8e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2de8e-113">权限</span><span class="sxs-lookup"><span data-stu-id="2de8e-113">Permissions</span></span>
<span data-ttu-id="2de8e-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="2de8e-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="2de8e-115">权限类型</span><span class="sxs-lookup"><span data-stu-id="2de8e-115">Permission type</span></span> |   <span data-ttu-id="2de8e-116">权限</span><span class="sxs-lookup"><span data-stu-id="2de8e-116">Permission</span></span>  |   <span data-ttu-id="2de8e-117">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="2de8e-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2de8e-118">应用程序</span><span class="sxs-lookup"><span data-stu-id="2de8e-118">Application</span></span> |   <span data-ttu-id="2de8e-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="2de8e-119">Incident.Read.All</span></span> | <span data-ttu-id="2de8e-120">"读取所有事件"</span><span class="sxs-lookup"><span data-stu-id="2de8e-120">'Read all Incidents'</span></span>
<span data-ttu-id="2de8e-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="2de8e-121">Application</span></span> |   <span data-ttu-id="2de8e-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2de8e-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="2de8e-123">"读取和写入所有事件"</span><span class="sxs-lookup"><span data-stu-id="2de8e-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="2de8e-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="2de8e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="2de8e-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="2de8e-125">Incident.Read</span></span> | <span data-ttu-id="2de8e-126">"读取事件"</span><span class="sxs-lookup"><span data-stu-id="2de8e-126">'Read Incidents'</span></span>
<span data-ttu-id="2de8e-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="2de8e-127">Delegated (work or school account)</span></span> | <span data-ttu-id="2de8e-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2de8e-128">Incident.ReadWrite</span></span> | <span data-ttu-id="2de8e-129">"读取和写入事件"</span><span class="sxs-lookup"><span data-stu-id="2de8e-129">'Read and write Incidents'</span></span>

>[!Note]
> <span data-ttu-id="2de8e-130">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="2de8e-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2de8e-131">用户至少需要具有以下角色权限："查看数据"</span><span class="sxs-lookup"><span data-stu-id="2de8e-131">The user needs to have at least the following role permission: 'View Data'</span></span>
>- <span data-ttu-id="2de8e-132">响应将仅包括用户向其中公开的事件</span><span class="sxs-lookup"><span data-stu-id="2de8e-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="2de8e-133">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="2de8e-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="2de8e-134">请求标头</span><span class="sxs-lookup"><span data-stu-id="2de8e-134">Request headers</span></span>

<span data-ttu-id="2de8e-135">名称</span><span class="sxs-lookup"><span data-stu-id="2de8e-135">Name</span></span> | <span data-ttu-id="2de8e-136">类型</span><span class="sxs-lookup"><span data-stu-id="2de8e-136">Type</span></span> | <span data-ttu-id="2de8e-137">说明</span><span class="sxs-lookup"><span data-stu-id="2de8e-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="2de8e-138">Authorization</span><span class="sxs-lookup"><span data-stu-id="2de8e-138">Authorization</span></span> | <span data-ttu-id="2de8e-139">String</span><span class="sxs-lookup"><span data-stu-id="2de8e-139">String</span></span> | <span data-ttu-id="2de8e-140">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="2de8e-140">Bearer {token}.</span></span> <span data-ttu-id="2de8e-141">**必需**。</span><span class="sxs-lookup"><span data-stu-id="2de8e-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2de8e-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="2de8e-142">Request body</span></span>
<span data-ttu-id="2de8e-143">Empty</span><span class="sxs-lookup"><span data-stu-id="2de8e-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2de8e-144">响应</span><span class="sxs-lookup"><span data-stu-id="2de8e-144">Response</span></span>

<span data-ttu-id="2de8e-145">如果成功，此方法在响应正文中返回 200 OK 和事件实体。</span><span class="sxs-lookup"><span data-stu-id="2de8e-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="2de8e-146">如果未找到具有指定 ID 的事件 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="2de8e-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="2de8e-147">示例</span><span class="sxs-lookup"><span data-stu-id="2de8e-147">Example</span></span>

<span data-ttu-id="2de8e-148">**请求**</span><span class="sxs-lookup"><span data-stu-id="2de8e-148">**Request**</span></span>

<span data-ttu-id="2de8e-149">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="2de8e-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
