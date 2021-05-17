---
title: 停止和隔离文件 API
description: 了解如何停止在设备上运行文件，并删除 Microsoft Defender for Endpoint 中的文件。 请参阅示例。
keywords: api， 图形 api， 受支持的 api， 停止和隔离文件
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199725"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="9f757-105">停止和隔离文件 API</span><span class="sxs-lookup"><span data-stu-id="9f757-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f757-106">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9f757-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9f757-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9f757-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f757-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9f757-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9f757-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="9f757-109">API description</span></span>
<span data-ttu-id="9f757-110">停止在设备上执行文件并将其删除。</span><span class="sxs-lookup"><span data-stu-id="9f757-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="9f757-111">限制</span><span class="sxs-lookup"><span data-stu-id="9f757-111">Limitations</span></span>
1. <span data-ttu-id="9f757-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="9f757-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="9f757-113">权限</span><span class="sxs-lookup"><span data-stu-id="9f757-113">Permissions</span></span>
<span data-ttu-id="9f757-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="9f757-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9f757-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9f757-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9f757-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="9f757-116">Permission type</span></span> |   <span data-ttu-id="9f757-117">权限</span><span class="sxs-lookup"><span data-stu-id="9f757-117">Permission</span></span>  |   <span data-ttu-id="9f757-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="9f757-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9f757-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="9f757-119">Application</span></span> |   <span data-ttu-id="9f757-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="9f757-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="9f757-121">"停止和隔离"</span><span class="sxs-lookup"><span data-stu-id="9f757-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="9f757-122">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="9f757-122">Delegated (work or school account)</span></span> | <span data-ttu-id="9f757-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="9f757-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="9f757-124">"停止和隔离"</span><span class="sxs-lookup"><span data-stu-id="9f757-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="9f757-125">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="9f757-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9f757-126">用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9f757-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9f757-127">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="9f757-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9f757-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="9f757-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="9f757-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="9f757-129">Request headers</span></span>

<span data-ttu-id="9f757-130">名称</span><span class="sxs-lookup"><span data-stu-id="9f757-130">Name</span></span> | <span data-ttu-id="9f757-131">类型</span><span class="sxs-lookup"><span data-stu-id="9f757-131">Type</span></span> | <span data-ttu-id="9f757-132">说明</span><span class="sxs-lookup"><span data-stu-id="9f757-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f757-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="9f757-133">Authorization</span></span> | <span data-ttu-id="9f757-134">String</span><span class="sxs-lookup"><span data-stu-id="9f757-134">String</span></span> | <span data-ttu-id="9f757-135">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="9f757-135">Bearer {token}.</span></span> <span data-ttu-id="9f757-136">**必需**。</span><span class="sxs-lookup"><span data-stu-id="9f757-136">**Required**.</span></span>
<span data-ttu-id="9f757-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9f757-137">Content-Type</span></span> | <span data-ttu-id="9f757-138">string</span><span class="sxs-lookup"><span data-stu-id="9f757-138">string</span></span> | <span data-ttu-id="9f757-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="9f757-139">application/json.</span></span> <span data-ttu-id="9f757-140">**必需**。</span><span class="sxs-lookup"><span data-stu-id="9f757-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9f757-141">请求正文</span><span class="sxs-lookup"><span data-stu-id="9f757-141">Request body</span></span>
<span data-ttu-id="9f757-142">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="9f757-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="9f757-143">参数</span><span class="sxs-lookup"><span data-stu-id="9f757-143">Parameter</span></span> | <span data-ttu-id="9f757-144">类型</span><span class="sxs-lookup"><span data-stu-id="9f757-144">Type</span></span>    | <span data-ttu-id="9f757-145">说明</span><span class="sxs-lookup"><span data-stu-id="9f757-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f757-146">评论</span><span class="sxs-lookup"><span data-stu-id="9f757-146">Comment</span></span> |   <span data-ttu-id="9f757-147">字符串</span><span class="sxs-lookup"><span data-stu-id="9f757-147">String</span></span> |    <span data-ttu-id="9f757-148">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="9f757-148">Comment to associate with the action.</span></span> <span data-ttu-id="9f757-149">**必需**。</span><span class="sxs-lookup"><span data-stu-id="9f757-149">**Required**.</span></span>
<span data-ttu-id="9f757-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="9f757-150">Sha1</span></span> |  <span data-ttu-id="9f757-151">String</span><span class="sxs-lookup"><span data-stu-id="9f757-151">String</span></span>   | <span data-ttu-id="9f757-152">在设备上停止和隔离的文件的 Sha1。</span><span class="sxs-lookup"><span data-stu-id="9f757-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="9f757-153">**必需**。</span><span class="sxs-lookup"><span data-stu-id="9f757-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="9f757-154">响应</span><span class="sxs-lookup"><span data-stu-id="9f757-154">Response</span></span>
<span data-ttu-id="9f757-155">如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="9f757-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="9f757-156">示例</span><span class="sxs-lookup"><span data-stu-id="9f757-156">Example</span></span>

<span data-ttu-id="9f757-157">**请求**</span><span class="sxs-lookup"><span data-stu-id="9f757-157">**Request**</span></span>

<span data-ttu-id="9f757-158">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="9f757-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
