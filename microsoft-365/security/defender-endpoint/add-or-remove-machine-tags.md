---
title: 添加或删除计算机标记 API
description: 了解如何使用添加或删除计算机标记 API 在 Microsoft Defender for Endpoint 中添加或删除计算机标记。
keywords: api， 图形 api， 受支持的 api， 标记， 计算机标记
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199767"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="95869-104">添加或删除计算机标记 API</span><span class="sxs-lookup"><span data-stu-id="95869-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="95869-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="95869-105">**Applies to:**</span></span>

- [<span data-ttu-id="95869-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95869-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="95869-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="95869-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95869-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="95869-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="95869-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="95869-109">API description</span></span>

<span data-ttu-id="95869-110">向特定计算机添加或删除 [标记](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="95869-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="95869-111">限制</span><span class="sxs-lookup"><span data-stu-id="95869-111">Limitations</span></span>

1. <span data-ttu-id="95869-112">你可以根据配置的保留期在上次看到的计算机上发布。</span><span class="sxs-lookup"><span data-stu-id="95869-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="95869-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="95869-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="95869-114">权限</span><span class="sxs-lookup"><span data-stu-id="95869-114">Permissions</span></span>

<span data-ttu-id="95869-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="95869-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="95869-116">若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="95869-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="95869-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="95869-117">Permission type</span></span> |    <span data-ttu-id="95869-118">权限</span><span class="sxs-lookup"><span data-stu-id="95869-118">Permission</span></span>    |    <span data-ttu-id="95869-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="95869-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="95869-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="95869-120">Application</span></span> |    <span data-ttu-id="95869-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="95869-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="95869-122">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="95869-122">'Read and write all machine information'</span></span>
<span data-ttu-id="95869-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="95869-123">Delegated (work or school account)</span></span> | <span data-ttu-id="95869-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="95869-124">Machine.ReadWrite</span></span> | <span data-ttu-id="95869-125">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="95869-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="95869-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="95869-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="95869-127">用户至少需要具有以下角色权限："管理安全性设置"。</span><span class="sxs-lookup"><span data-stu-id="95869-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="95869-128">有关详细信息 (请参阅 [创建和管理角色，](user-roles.md) 了解) </span><span class="sxs-lookup"><span data-stu-id="95869-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="95869-129">用户需要具有计算机访问权限，根据计算机组设置 (请参阅创建和管理计算机组，了解[](machine-groups.md)) </span><span class="sxs-lookup"><span data-stu-id="95869-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="95869-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="95869-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="95869-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="95869-131">Request headers</span></span>

<span data-ttu-id="95869-132">名称</span><span class="sxs-lookup"><span data-stu-id="95869-132">Name</span></span> | <span data-ttu-id="95869-133">类型</span><span class="sxs-lookup"><span data-stu-id="95869-133">Type</span></span> | <span data-ttu-id="95869-134">说明</span><span class="sxs-lookup"><span data-stu-id="95869-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="95869-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="95869-135">Authorization</span></span> | <span data-ttu-id="95869-136">字符串</span><span class="sxs-lookup"><span data-stu-id="95869-136">String</span></span> | <span data-ttu-id="95869-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="95869-137">Bearer {token}.</span></span> <span data-ttu-id="95869-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="95869-138">**Required**.</span></span>
<span data-ttu-id="95869-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="95869-139">Content-Type</span></span> | <span data-ttu-id="95869-140">string</span><span class="sxs-lookup"><span data-stu-id="95869-140">string</span></span> | <span data-ttu-id="95869-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="95869-141">application/json.</span></span> <span data-ttu-id="95869-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="95869-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="95869-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="95869-143">Request body</span></span>

<span data-ttu-id="95869-144">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="95869-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="95869-145">参数</span><span class="sxs-lookup"><span data-stu-id="95869-145">Parameter</span></span> |    <span data-ttu-id="95869-146">类型</span><span class="sxs-lookup"><span data-stu-id="95869-146">Type</span></span>    | <span data-ttu-id="95869-147">说明</span><span class="sxs-lookup"><span data-stu-id="95869-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="95869-148">值</span><span class="sxs-lookup"><span data-stu-id="95869-148">Value</span></span> |    <span data-ttu-id="95869-149">String</span><span class="sxs-lookup"><span data-stu-id="95869-149">String</span></span> |    <span data-ttu-id="95869-150">标记名称。</span><span class="sxs-lookup"><span data-stu-id="95869-150">The tag name.</span></span> <span data-ttu-id="95869-151">**必需**。</span><span class="sxs-lookup"><span data-stu-id="95869-151">**Required**.</span></span>
<span data-ttu-id="95869-152">操作</span><span class="sxs-lookup"><span data-stu-id="95869-152">Action</span></span>    | <span data-ttu-id="95869-153">枚举</span><span class="sxs-lookup"><span data-stu-id="95869-153">Enum</span></span> |    <span data-ttu-id="95869-154">添加或删除。</span><span class="sxs-lookup"><span data-stu-id="95869-154">Add or Remove.</span></span> <span data-ttu-id="95869-155">允许的值包括："Add"或"Remove"。</span><span class="sxs-lookup"><span data-stu-id="95869-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="95869-156">**必需**。</span><span class="sxs-lookup"><span data-stu-id="95869-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="95869-157">响应</span><span class="sxs-lookup"><span data-stu-id="95869-157">Response</span></span>

<span data-ttu-id="95869-158">如果成功，此方法在响应正文中返回 200 - 正常响应代码和更新的 Machine。</span><span class="sxs-lookup"><span data-stu-id="95869-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="95869-159">示例</span><span class="sxs-lookup"><span data-stu-id="95869-159">Example</span></span>

<span data-ttu-id="95869-160">**请求**</span><span class="sxs-lookup"><span data-stu-id="95869-160">**Request**</span></span>

<span data-ttu-id="95869-161">下面是添加计算机标记的请求示例。</span><span class="sxs-lookup"><span data-stu-id="95869-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="95869-162">若要删除计算机标记，在请求正文中将 Action 设置为"Remove"而不是"Add"。</span><span class="sxs-lookup"><span data-stu-id="95869-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
