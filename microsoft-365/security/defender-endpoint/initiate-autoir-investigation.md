---
title: 启动调查 API
description: 使用此 API 在设备上开始调查。
keywords: api， 图形 api， 受支持的 api， 调查
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
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770885"
---
# <a name="start-investigation-api"></a><span data-ttu-id="c06ce-104">启动调查 API</span><span class="sxs-lookup"><span data-stu-id="c06ce-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c06ce-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c06ce-105">**Applies to:**</span></span>
- [<span data-ttu-id="c06ce-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c06ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c06ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c06ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c06ce-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="c06ce-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c06ce-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c06ce-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c06ce-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="c06ce-110">API description</span></span>
<span data-ttu-id="c06ce-111">在设备上启动自动调查。</span><span class="sxs-lookup"><span data-stu-id="c06ce-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="c06ce-112">有关详细信息 [，请参阅自动](automated-investigations.md) 调查概述。</span><span class="sxs-lookup"><span data-stu-id="c06ce-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="c06ce-113">限制</span><span class="sxs-lookup"><span data-stu-id="c06ce-113">Limitations</span></span>
1. <span data-ttu-id="c06ce-114">此 API 的速率限制是每小时 50 次调用。</span><span class="sxs-lookup"><span data-stu-id="c06ce-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c06ce-115">权限</span><span class="sxs-lookup"><span data-stu-id="c06ce-115">Permissions</span></span>
<span data-ttu-id="c06ce-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="c06ce-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c06ce-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c06ce-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c06ce-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="c06ce-118">Permission type</span></span> |   <span data-ttu-id="c06ce-119">权限</span><span class="sxs-lookup"><span data-stu-id="c06ce-119">Permission</span></span>  |   <span data-ttu-id="c06ce-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="c06ce-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c06ce-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="c06ce-121">Application</span></span> |   <span data-ttu-id="c06ce-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c06ce-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="c06ce-123">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="c06ce-123">'Read and write all alerts'</span></span>
<span data-ttu-id="c06ce-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="c06ce-124">Delegated (work or school account)</span></span> | <span data-ttu-id="c06ce-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c06ce-125">Alert.ReadWrite</span></span> | <span data-ttu-id="c06ce-126">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="c06ce-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="c06ce-127">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="c06ce-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c06ce-128">用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c06ce-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c06ce-129">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="c06ce-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="c06ce-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="c06ce-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="c06ce-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="c06ce-131">Request headers</span></span>

<span data-ttu-id="c06ce-132">名称</span><span class="sxs-lookup"><span data-stu-id="c06ce-132">Name</span></span> | <span data-ttu-id="c06ce-133">类型</span><span class="sxs-lookup"><span data-stu-id="c06ce-133">Type</span></span> | <span data-ttu-id="c06ce-134">说明</span><span class="sxs-lookup"><span data-stu-id="c06ce-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="c06ce-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="c06ce-135">Authorization</span></span> | <span data-ttu-id="c06ce-136">String</span><span class="sxs-lookup"><span data-stu-id="c06ce-136">String</span></span> | <span data-ttu-id="c06ce-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="c06ce-137">Bearer {token}.</span></span> <span data-ttu-id="c06ce-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c06ce-138">**Required**.</span></span>
<span data-ttu-id="c06ce-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c06ce-139">Content-Type</span></span> | <span data-ttu-id="c06ce-140">string</span><span class="sxs-lookup"><span data-stu-id="c06ce-140">string</span></span> | <span data-ttu-id="c06ce-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="c06ce-141">application/json.</span></span> <span data-ttu-id="c06ce-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c06ce-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="c06ce-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="c06ce-143">Request body</span></span>
<span data-ttu-id="c06ce-144">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="c06ce-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c06ce-145">参数</span><span class="sxs-lookup"><span data-stu-id="c06ce-145">Parameter</span></span> | <span data-ttu-id="c06ce-146">类型</span><span class="sxs-lookup"><span data-stu-id="c06ce-146">Type</span></span>    | <span data-ttu-id="c06ce-147">说明</span><span class="sxs-lookup"><span data-stu-id="c06ce-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="c06ce-148">评论</span><span class="sxs-lookup"><span data-stu-id="c06ce-148">Comment</span></span> |   <span data-ttu-id="c06ce-149">字符串</span><span class="sxs-lookup"><span data-stu-id="c06ce-149">String</span></span> |    <span data-ttu-id="c06ce-150">要与操作关联的注释。</span><span class="sxs-lookup"><span data-stu-id="c06ce-150">Comment to associate with the action.</span></span> <span data-ttu-id="c06ce-151">**必需**。</span><span class="sxs-lookup"><span data-stu-id="c06ce-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="c06ce-152">响应</span><span class="sxs-lookup"><span data-stu-id="c06ce-152">Response</span></span>
<span data-ttu-id="c06ce-153">如果成功，此方法在响应正文中返回 201 - [已创建响应](investigation.md) 代码和调查。</span><span class="sxs-lookup"><span data-stu-id="c06ce-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="c06ce-154">示例</span><span class="sxs-lookup"><span data-stu-id="c06ce-154">Example</span></span>

<span data-ttu-id="c06ce-155">**请求**</span><span class="sxs-lookup"><span data-stu-id="c06ce-155">**Request**</span></span>

<span data-ttu-id="c06ce-156">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="c06ce-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
