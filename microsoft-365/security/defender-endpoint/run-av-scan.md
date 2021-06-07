---
title: 运行防病毒扫描 API
description: 使用此 API 创建与在设备上运行防病毒扫描相关的调用。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 3df703fd84c87a2bd34bb2a81f8c83063e468b17
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771442"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="004cf-104">运行防病毒扫描 API</span><span class="sxs-lookup"><span data-stu-id="004cf-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="004cf-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="004cf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="004cf-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="004cf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="004cf-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="004cf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="004cf-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="004cf-108">API description</span></span>
<span data-ttu-id="004cf-109">在Microsoft Defender 防病毒启动扫描。</span><span class="sxs-lookup"><span data-stu-id="004cf-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="004cf-110">限制</span><span class="sxs-lookup"><span data-stu-id="004cf-110">Limitations</span></span>
1. <span data-ttu-id="004cf-111">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="004cf-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="004cf-112">权限</span><span class="sxs-lookup"><span data-stu-id="004cf-112">Permissions</span></span>
<span data-ttu-id="004cf-113">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="004cf-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="004cf-114">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="004cf-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="004cf-115">权限类型</span><span class="sxs-lookup"><span data-stu-id="004cf-115">Permission type</span></span> |   <span data-ttu-id="004cf-116">权限</span><span class="sxs-lookup"><span data-stu-id="004cf-116">Permission</span></span>  |   <span data-ttu-id="004cf-117">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="004cf-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="004cf-118">应用程序</span><span class="sxs-lookup"><span data-stu-id="004cf-118">Application</span></span> |   <span data-ttu-id="004cf-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="004cf-119">Machine.Scan</span></span> |  <span data-ttu-id="004cf-120">"扫描计算机"</span><span class="sxs-lookup"><span data-stu-id="004cf-120">'Scan machine'</span></span>
<span data-ttu-id="004cf-121">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="004cf-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="004cf-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="004cf-122">Machine.Scan</span></span> |  <span data-ttu-id="004cf-123">"扫描计算机"</span><span class="sxs-lookup"><span data-stu-id="004cf-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="004cf-124">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="004cf-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="004cf-125">用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="004cf-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="004cf-126">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="004cf-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="004cf-127">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="004cf-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="004cf-128">请求标头</span><span class="sxs-lookup"><span data-stu-id="004cf-128">Request headers</span></span>

<span data-ttu-id="004cf-129">名称</span><span class="sxs-lookup"><span data-stu-id="004cf-129">Name</span></span> | <span data-ttu-id="004cf-130">类型</span><span class="sxs-lookup"><span data-stu-id="004cf-130">Type</span></span> | <span data-ttu-id="004cf-131">说明</span><span class="sxs-lookup"><span data-stu-id="004cf-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="004cf-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="004cf-132">Authorization</span></span> | <span data-ttu-id="004cf-133">String</span><span class="sxs-lookup"><span data-stu-id="004cf-133">String</span></span> | <span data-ttu-id="004cf-134">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="004cf-134">Bearer {token}.</span></span> <span data-ttu-id="004cf-135">**必需**。</span><span class="sxs-lookup"><span data-stu-id="004cf-135">**Required**.</span></span>
<span data-ttu-id="004cf-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="004cf-136">Content-Type</span></span> | <span data-ttu-id="004cf-137">string</span><span class="sxs-lookup"><span data-stu-id="004cf-137">string</span></span> | <span data-ttu-id="004cf-138">application/json</span><span class="sxs-lookup"><span data-stu-id="004cf-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="004cf-139">请求正文</span><span class="sxs-lookup"><span data-stu-id="004cf-139">Request body</span></span>
<span data-ttu-id="004cf-140">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="004cf-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="004cf-141">参数</span><span class="sxs-lookup"><span data-stu-id="004cf-141">Parameter</span></span> | <span data-ttu-id="004cf-142">类型</span><span class="sxs-lookup"><span data-stu-id="004cf-142">Type</span></span>    | <span data-ttu-id="004cf-143">说明</span><span class="sxs-lookup"><span data-stu-id="004cf-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="004cf-144">评论</span><span class="sxs-lookup"><span data-stu-id="004cf-144">Comment</span></span> |   <span data-ttu-id="004cf-145">字符串</span><span class="sxs-lookup"><span data-stu-id="004cf-145">String</span></span> | <span data-ttu-id="004cf-146">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="004cf-146">Comment to associate with the action.</span></span> <span data-ttu-id="004cf-147">**必需**。</span><span class="sxs-lookup"><span data-stu-id="004cf-147">**Required**.</span></span>
<span data-ttu-id="004cf-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="004cf-148">ScanType</span></span>|   <span data-ttu-id="004cf-149">String</span><span class="sxs-lookup"><span data-stu-id="004cf-149">String</span></span>  | <span data-ttu-id="004cf-150">定义扫描的类型。</span><span class="sxs-lookup"><span data-stu-id="004cf-150">Defines the type of the Scan.</span></span> <span data-ttu-id="004cf-151">**必需**。</span><span class="sxs-lookup"><span data-stu-id="004cf-151">**Required**.</span></span>

<span data-ttu-id="004cf-152">**ScanType** 控制要执行扫描的类型，可以是下列类型之一：</span><span class="sxs-lookup"><span data-stu-id="004cf-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="004cf-153">**快速** – 在设备上执行快速扫描</span><span class="sxs-lookup"><span data-stu-id="004cf-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="004cf-154">**完全** - 在设备上执行完全扫描</span><span class="sxs-lookup"><span data-stu-id="004cf-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="004cf-155">响应</span><span class="sxs-lookup"><span data-stu-id="004cf-155">Response</span></span>
<span data-ttu-id="004cf-156">如果成功，此方法在响应正文中返回 201、Created 响应代码和 _MachineAction_ 对象。</span><span class="sxs-lookup"><span data-stu-id="004cf-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="004cf-157">示例</span><span class="sxs-lookup"><span data-stu-id="004cf-157">Example</span></span>

<span data-ttu-id="004cf-158">**请求**</span><span class="sxs-lookup"><span data-stu-id="004cf-158">**Request**</span></span>

<span data-ttu-id="004cf-159">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="004cf-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

