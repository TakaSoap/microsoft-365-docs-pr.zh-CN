---
title: 收集调查包 API
description: 使用此 API 创建与从设备收集调查包相关的调用。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0083d806f3e52307e6dce30f74e255073a09c16a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770489"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="e4303-104">收集调查包 API</span><span class="sxs-lookup"><span data-stu-id="e4303-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4303-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e4303-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4303-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4303-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e4303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4303-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="e4303-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e4303-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e4303-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e4303-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e4303-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="e4303-110">API description</span></span>
<span data-ttu-id="e4303-111">从设备收集调查包。</span><span class="sxs-lookup"><span data-stu-id="e4303-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="e4303-112">限制</span><span class="sxs-lookup"><span data-stu-id="e4303-112">Limitations</span></span>
1. <span data-ttu-id="e4303-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="e4303-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e4303-114">权限</span><span class="sxs-lookup"><span data-stu-id="e4303-114">Permissions</span></span>
<span data-ttu-id="e4303-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e4303-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e4303-116">若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e4303-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e4303-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="e4303-117">Permission type</span></span> |   <span data-ttu-id="e4303-118">权限</span><span class="sxs-lookup"><span data-stu-id="e4303-118">Permission</span></span>  |   <span data-ttu-id="e4303-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e4303-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e4303-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="e4303-120">Application</span></span> |   <span data-ttu-id="e4303-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="e4303-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="e4303-122">"收集取证"</span><span class="sxs-lookup"><span data-stu-id="e4303-122">'Collect forensics'</span></span>
<span data-ttu-id="e4303-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e4303-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="e4303-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="e4303-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="e4303-125">"收集取证"</span><span class="sxs-lookup"><span data-stu-id="e4303-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="e4303-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="e4303-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e4303-127">用户至少需要具有以下角色权限："警报调查" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e4303-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e4303-128">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="e4303-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e4303-129">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="e4303-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="e4303-130">请求标头</span><span class="sxs-lookup"><span data-stu-id="e4303-130">Request headers</span></span>

<span data-ttu-id="e4303-131">名称</span><span class="sxs-lookup"><span data-stu-id="e4303-131">Name</span></span> | <span data-ttu-id="e4303-132">类型</span><span class="sxs-lookup"><span data-stu-id="e4303-132">Type</span></span> | <span data-ttu-id="e4303-133">说明</span><span class="sxs-lookup"><span data-stu-id="e4303-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="e4303-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="e4303-134">Authorization</span></span> | <span data-ttu-id="e4303-135">String</span><span class="sxs-lookup"><span data-stu-id="e4303-135">String</span></span> | <span data-ttu-id="e4303-136">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="e4303-136">Bearer {token}.</span></span> <span data-ttu-id="e4303-137">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e4303-137">**Required**.</span></span>
<span data-ttu-id="e4303-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e4303-138">Content-Type</span></span> | <span data-ttu-id="e4303-139">string</span><span class="sxs-lookup"><span data-stu-id="e4303-139">string</span></span> | <span data-ttu-id="e4303-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="e4303-140">application/json.</span></span> <span data-ttu-id="e4303-141">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e4303-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e4303-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="e4303-142">Request body</span></span>
<span data-ttu-id="e4303-143">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="e4303-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e4303-144">参数</span><span class="sxs-lookup"><span data-stu-id="e4303-144">Parameter</span></span> | <span data-ttu-id="e4303-145">类型</span><span class="sxs-lookup"><span data-stu-id="e4303-145">Type</span></span>    | <span data-ttu-id="e4303-146">说明</span><span class="sxs-lookup"><span data-stu-id="e4303-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="e4303-147">评论</span><span class="sxs-lookup"><span data-stu-id="e4303-147">Comment</span></span> |   <span data-ttu-id="e4303-148">字符串</span><span class="sxs-lookup"><span data-stu-id="e4303-148">String</span></span> |    <span data-ttu-id="e4303-149">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="e4303-149">Comment to associate with the action.</span></span> <span data-ttu-id="e4303-150">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e4303-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="e4303-151">响应</span><span class="sxs-lookup"><span data-stu-id="e4303-151">Response</span></span>
<span data-ttu-id="e4303-152">如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="e4303-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="e4303-153">示例</span><span class="sxs-lookup"><span data-stu-id="e4303-153">Example</span></span>

<span data-ttu-id="e4303-154">**请求**</span><span class="sxs-lookup"><span data-stu-id="e4303-154">**Request**</span></span>

<span data-ttu-id="e4303-155">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="e4303-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
