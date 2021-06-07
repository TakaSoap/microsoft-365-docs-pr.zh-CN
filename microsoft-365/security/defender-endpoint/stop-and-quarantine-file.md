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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771393"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="c837e-105">停止和隔离文件 API</span><span class="sxs-lookup"><span data-stu-id="c837e-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c837e-106">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c837e-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c837e-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c837e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c837e-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c837e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c837e-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="c837e-109">API description</span></span>
<span data-ttu-id="c837e-110">停止在设备上执行文件并将其删除。</span><span class="sxs-lookup"><span data-stu-id="c837e-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="c837e-111">限制</span><span class="sxs-lookup"><span data-stu-id="c837e-111">Limitations</span></span>
1. <span data-ttu-id="c837e-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="c837e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="c837e-113">权限</span><span class="sxs-lookup"><span data-stu-id="c837e-113">Permissions</span></span>
<span data-ttu-id="c837e-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="c837e-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c837e-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c837e-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c837e-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="c837e-116">Permission type</span></span> |   <span data-ttu-id="c837e-117">权限</span><span class="sxs-lookup"><span data-stu-id="c837e-117">Permission</span></span>  |   <span data-ttu-id="c837e-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="c837e-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c837e-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="c837e-119">Application</span></span> |   <span data-ttu-id="c837e-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="c837e-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="c837e-121">"停止和隔离"</span><span class="sxs-lookup"><span data-stu-id="c837e-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="c837e-122">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="c837e-122">Delegated (work or school account)</span></span> | <span data-ttu-id="c837e-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="c837e-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="c837e-124">"停止和隔离"</span><span class="sxs-lookup"><span data-stu-id="c837e-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="c837e-125">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="c837e-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c837e-126">用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c837e-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c837e-127">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="c837e-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c837e-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="c837e-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="c837e-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="c837e-129">Request headers</span></span>

<span data-ttu-id="c837e-130">名称</span><span class="sxs-lookup"><span data-stu-id="c837e-130">Name</span></span> | <span data-ttu-id="c837e-131">类型</span><span class="sxs-lookup"><span data-stu-id="c837e-131">Type</span></span> | <span data-ttu-id="c837e-132">说明</span><span class="sxs-lookup"><span data-stu-id="c837e-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="c837e-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="c837e-133">Authorization</span></span> | <span data-ttu-id="c837e-134">String</span><span class="sxs-lookup"><span data-stu-id="c837e-134">String</span></span> | <span data-ttu-id="c837e-135">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="c837e-135">Bearer {token}.</span></span> <span data-ttu-id="c837e-136">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c837e-136">**Required**.</span></span>
<span data-ttu-id="c837e-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c837e-137">Content-Type</span></span> | <span data-ttu-id="c837e-138">string</span><span class="sxs-lookup"><span data-stu-id="c837e-138">string</span></span> | <span data-ttu-id="c837e-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="c837e-139">application/json.</span></span> <span data-ttu-id="c837e-140">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c837e-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c837e-141">请求正文</span><span class="sxs-lookup"><span data-stu-id="c837e-141">Request body</span></span>
<span data-ttu-id="c837e-142">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="c837e-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c837e-143">参数</span><span class="sxs-lookup"><span data-stu-id="c837e-143">Parameter</span></span> | <span data-ttu-id="c837e-144">类型</span><span class="sxs-lookup"><span data-stu-id="c837e-144">Type</span></span>    | <span data-ttu-id="c837e-145">说明</span><span class="sxs-lookup"><span data-stu-id="c837e-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="c837e-146">评论</span><span class="sxs-lookup"><span data-stu-id="c837e-146">Comment</span></span> |   <span data-ttu-id="c837e-147">字符串</span><span class="sxs-lookup"><span data-stu-id="c837e-147">String</span></span> |    <span data-ttu-id="c837e-148">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="c837e-148">Comment to associate with the action.</span></span> <span data-ttu-id="c837e-149">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c837e-149">**Required**.</span></span>
<span data-ttu-id="c837e-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="c837e-150">Sha1</span></span> |  <span data-ttu-id="c837e-151">String</span><span class="sxs-lookup"><span data-stu-id="c837e-151">String</span></span>   | <span data-ttu-id="c837e-152">在设备上停止和隔离的文件的 Sha1。</span><span class="sxs-lookup"><span data-stu-id="c837e-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="c837e-153">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c837e-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c837e-154">响应</span><span class="sxs-lookup"><span data-stu-id="c837e-154">Response</span></span>
<span data-ttu-id="c837e-155">如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="c837e-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c837e-156">示例</span><span class="sxs-lookup"><span data-stu-id="c837e-156">Example</span></span>

<span data-ttu-id="c837e-157">**请求**</span><span class="sxs-lookup"><span data-stu-id="c837e-157">**Request**</span></span>

<span data-ttu-id="c837e-158">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="c837e-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
