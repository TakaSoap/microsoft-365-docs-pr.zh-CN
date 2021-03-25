---
title: 获取与用户相关的计算机 API
description: 了解如何使用获取与用户相关的计算机 API 检索与 Microsoft Defender for Endpoint 中的用户 ID 相关的设备集合。
keywords: api， 图形 api， 受支持的 api， 获取， 用户， 用户相关警报
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
ms.openlocfilehash: 135dc1d76a1a90cd7fffba0638211d716865cb0c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166313"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="9db2c-104">获取与用户相关的计算机 API</span><span class="sxs-lookup"><span data-stu-id="9db2c-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9db2c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9db2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9db2c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9db2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9db2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9db2c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9db2c-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9db2c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9db2c-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9db2c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9db2c-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="9db2c-110">API description</span></span>
<span data-ttu-id="9db2c-111">检索与给定用户 ID 相关的设备的集合。</span><span class="sxs-lookup"><span data-stu-id="9db2c-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="9db2c-112">限制</span><span class="sxs-lookup"><span data-stu-id="9db2c-112">Limitations</span></span>
1. <span data-ttu-id="9db2c-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="9db2c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9db2c-114">权限</span><span class="sxs-lookup"><span data-stu-id="9db2c-114">Permissions</span></span>
<span data-ttu-id="9db2c-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="9db2c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9db2c-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9db2c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9db2c-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="9db2c-117">Permission type</span></span> |   <span data-ttu-id="9db2c-118">权限</span><span class="sxs-lookup"><span data-stu-id="9db2c-118">Permission</span></span>  |   <span data-ttu-id="9db2c-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="9db2c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9db2c-120">Application</span><span class="sxs-lookup"><span data-stu-id="9db2c-120">Application</span></span> |   <span data-ttu-id="9db2c-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="9db2c-121">Machine.Read.All</span></span> |  <span data-ttu-id="9db2c-122">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="9db2c-122">'Read all machine profiles'</span></span>
<span data-ttu-id="9db2c-123">Application</span><span class="sxs-lookup"><span data-stu-id="9db2c-123">Application</span></span> |   <span data-ttu-id="9db2c-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9db2c-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="9db2c-125">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="9db2c-125">'Read and write all machine information'</span></span>
<span data-ttu-id="9db2c-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="9db2c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="9db2c-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="9db2c-127">Machine.Read</span></span> | <span data-ttu-id="9db2c-128">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="9db2c-128">'Read machine information'</span></span>
<span data-ttu-id="9db2c-129">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="9db2c-129">Delegated (work or school account)</span></span> | <span data-ttu-id="9db2c-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9db2c-130">Machine.ReadWrite</span></span> | <span data-ttu-id="9db2c-131">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="9db2c-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="9db2c-132">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="9db2c-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9db2c-133">用户至少需要具有以下角色权限："查看数据"。</span><span class="sxs-lookup"><span data-stu-id="9db2c-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="9db2c-134">有关详细信息，请参阅创建 [和管理角色](user-roles.md) ) </span><span class="sxs-lookup"><span data-stu-id="9db2c-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="9db2c-135">响应将仅包括用户可以基于设备组设置访问的设备。</span><span class="sxs-lookup"><span data-stu-id="9db2c-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="9db2c-136">有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="9db2c-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="9db2c-137">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="9db2c-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="9db2c-138">**ID 不是完整的 UPN，而只是用户名。 (，若要检索供用户 user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="9db2c-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="9db2c-139">请求标头</span><span class="sxs-lookup"><span data-stu-id="9db2c-139">Request headers</span></span>

<span data-ttu-id="9db2c-140">名称</span><span class="sxs-lookup"><span data-stu-id="9db2c-140">Name</span></span> | <span data-ttu-id="9db2c-141">类型</span><span class="sxs-lookup"><span data-stu-id="9db2c-141">Type</span></span> | <span data-ttu-id="9db2c-142">说明</span><span class="sxs-lookup"><span data-stu-id="9db2c-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="9db2c-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="9db2c-143">Authorization</span></span> | <span data-ttu-id="9db2c-144">String</span><span class="sxs-lookup"><span data-stu-id="9db2c-144">String</span></span> | <span data-ttu-id="9db2c-145">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="9db2c-145">Bearer {token}.</span></span> <span data-ttu-id="9db2c-146">**必需**。</span><span class="sxs-lookup"><span data-stu-id="9db2c-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9db2c-147">请求正文</span><span class="sxs-lookup"><span data-stu-id="9db2c-147">Request body</span></span>
<span data-ttu-id="9db2c-148">Empty</span><span class="sxs-lookup"><span data-stu-id="9db2c-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9db2c-149">响应</span><span class="sxs-lookup"><span data-stu-id="9db2c-149">Response</span></span>
<span data-ttu-id="9db2c-150">如果成功且用户存在 - 200 正常[](machine.md)，正文中包含计算机实体列表。</span><span class="sxs-lookup"><span data-stu-id="9db2c-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="9db2c-151">如果用户不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="9db2c-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="9db2c-152">示例</span><span class="sxs-lookup"><span data-stu-id="9db2c-152">Example</span></span>

<span data-ttu-id="9db2c-153">**请求**</span><span class="sxs-lookup"><span data-stu-id="9db2c-153">**Request**</span></span>

<span data-ttu-id="9db2c-154">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="9db2c-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
