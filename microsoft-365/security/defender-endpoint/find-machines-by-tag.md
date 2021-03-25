---
title: 按标记 API 查找设备
description: 查找包含指定标记的所有设备
keywords: api， 受支持的 api， 获取， 设备， 查找， 查找设备， 按标记， 标记
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200145"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="d9055-104">按标记 API 查找设备</span><span class="sxs-lookup"><span data-stu-id="d9055-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9055-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d9055-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d9055-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d9055-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9055-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d9055-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d9055-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="d9055-108">API description</span></span>
<span data-ttu-id="d9055-109">按[标记 查找](machine.md)[计算机](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="d9055-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="d9055-110">```startswith``` 支持 查询。</span><span class="sxs-lookup"><span data-stu-id="d9055-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="d9055-111">限制</span><span class="sxs-lookup"><span data-stu-id="d9055-111">Limitations</span></span>
1. <span data-ttu-id="d9055-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="d9055-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d9055-113">权限</span><span class="sxs-lookup"><span data-stu-id="d9055-113">Permissions</span></span>
<span data-ttu-id="d9055-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="d9055-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d9055-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d9055-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d9055-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="d9055-116">Permission type</span></span> |   <span data-ttu-id="d9055-117">权限</span><span class="sxs-lookup"><span data-stu-id="d9055-117">Permission</span></span>  |   <span data-ttu-id="d9055-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="d9055-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d9055-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="d9055-119">Application</span></span> |   <span data-ttu-id="d9055-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="d9055-120">Machine.Read.All</span></span> |  <span data-ttu-id="d9055-121">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="d9055-121">'Read all machine profiles'</span></span>
<span data-ttu-id="d9055-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="d9055-122">Application</span></span> |   <span data-ttu-id="d9055-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d9055-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d9055-124">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="d9055-124">'Read and write all machine information'</span></span>
<span data-ttu-id="d9055-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="d9055-125">Delegated (work or school account)</span></span> | <span data-ttu-id="d9055-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="d9055-126">Machine.Read</span></span> | <span data-ttu-id="d9055-127">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="d9055-127">'Read machine information'</span></span>
<span data-ttu-id="d9055-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="d9055-128">Delegated (work or school account)</span></span> | <span data-ttu-id="d9055-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d9055-129">Machine.ReadWrite</span></span> | <span data-ttu-id="d9055-130">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="d9055-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d9055-131">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="d9055-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="d9055-132">响应将仅包括用户基于设备组设置有权访问的设备 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="d9055-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="d9055-133">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d9055-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="d9055-134">响应将仅包括用户基于设备组设置有权访问的设备 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="d9055-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d9055-135">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="d9055-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="d9055-136">请求标头</span><span class="sxs-lookup"><span data-stu-id="d9055-136">Request headers</span></span>

<span data-ttu-id="d9055-137">名称</span><span class="sxs-lookup"><span data-stu-id="d9055-137">Name</span></span> | <span data-ttu-id="d9055-138">类型</span><span class="sxs-lookup"><span data-stu-id="d9055-138">Type</span></span> | <span data-ttu-id="d9055-139">说明</span><span class="sxs-lookup"><span data-stu-id="d9055-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="d9055-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="d9055-140">Authorization</span></span> | <span data-ttu-id="d9055-141">字符串</span><span class="sxs-lookup"><span data-stu-id="d9055-141">String</span></span> | <span data-ttu-id="d9055-142">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="d9055-142">Bearer {token}.</span></span> <span data-ttu-id="d9055-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="d9055-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="d9055-144">请求 URI 参数</span><span class="sxs-lookup"><span data-stu-id="d9055-144">Request URI parameters</span></span>

<span data-ttu-id="d9055-145">名称</span><span class="sxs-lookup"><span data-stu-id="d9055-145">Name</span></span> | <span data-ttu-id="d9055-146">类型</span><span class="sxs-lookup"><span data-stu-id="d9055-146">Type</span></span> | <span data-ttu-id="d9055-147">说明</span><span class="sxs-lookup"><span data-stu-id="d9055-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="d9055-148">tag</span><span class="sxs-lookup"><span data-stu-id="d9055-148">tag</span></span> | <span data-ttu-id="d9055-149">字符串</span><span class="sxs-lookup"><span data-stu-id="d9055-149">String</span></span> | <span data-ttu-id="d9055-150">标记名称。</span><span class="sxs-lookup"><span data-stu-id="d9055-150">The tag name.</span></span> <span data-ttu-id="d9055-151">**必需**。</span><span class="sxs-lookup"><span data-stu-id="d9055-151">**Required**.</span></span>
<span data-ttu-id="d9055-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="d9055-152">useStartsWithFilter</span></span> | <span data-ttu-id="d9055-153">布尔值</span><span class="sxs-lookup"><span data-stu-id="d9055-153">Boolean</span></span> | <span data-ttu-id="d9055-154">设置为 true 时，搜索将查找标记名称以查询中的给定标记开头的所有设备。</span><span class="sxs-lookup"><span data-stu-id="d9055-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="d9055-155">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="d9055-155">Defaults to false.</span></span> <span data-ttu-id="d9055-156">**可选。**</span><span class="sxs-lookup"><span data-stu-id="d9055-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d9055-157">请求正文</span><span class="sxs-lookup"><span data-stu-id="d9055-157">Request body</span></span>
<span data-ttu-id="d9055-158">Empty</span><span class="sxs-lookup"><span data-stu-id="d9055-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d9055-159">响应</span><span class="sxs-lookup"><span data-stu-id="d9055-159">Response</span></span>
<span data-ttu-id="d9055-160">如果成功 - 200 正常，响应正文中提供计算机列表。</span><span class="sxs-lookup"><span data-stu-id="d9055-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="d9055-161">示例</span><span class="sxs-lookup"><span data-stu-id="d9055-161">Example</span></span>

<span data-ttu-id="d9055-162">**请求**</span><span class="sxs-lookup"><span data-stu-id="d9055-162">**Request**</span></span>

<span data-ttu-id="d9055-163">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="d9055-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```