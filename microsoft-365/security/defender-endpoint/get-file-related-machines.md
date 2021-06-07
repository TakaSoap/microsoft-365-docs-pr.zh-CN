---
title: 获取与文件相关的计算机 API
description: 了解如何使用获取与文件相关的计算机 API 获取与 Microsoft Defender for Endpoint 中的文件哈希相关的计算机集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 哈希
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
ms.openlocfilehash: 211a29bcd9265ae20c4f3e1817fcaaf562260d39
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770273"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="4ffa6-104">获取与文件相关的计算机 API</span><span class="sxs-lookup"><span data-stu-id="4ffa6-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ffa6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4ffa6-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ffa6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ffa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ffa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ffa6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ffa6-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4ffa6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4ffa6-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4ffa6-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="4ffa6-110">API description</span></span>
<span data-ttu-id="4ffa6-111">检索与给定文件 [哈希](machine.md) 相关的计算机集合。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="4ffa6-112">限制</span><span class="sxs-lookup"><span data-stu-id="4ffa6-112">Limitations</span></span>
1. <span data-ttu-id="4ffa6-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4ffa6-114">权限</span><span class="sxs-lookup"><span data-stu-id="4ffa6-114">Permissions</span></span>
<span data-ttu-id="4ffa6-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4ffa6-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4ffa6-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4ffa6-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="4ffa6-117">Permission type</span></span> |   <span data-ttu-id="4ffa6-118">权限</span><span class="sxs-lookup"><span data-stu-id="4ffa6-118">Permission</span></span>  |   <span data-ttu-id="4ffa6-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="4ffa6-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4ffa6-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="4ffa6-120">Application</span></span> |   <span data-ttu-id="4ffa6-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="4ffa6-121">Machine.Read.All</span></span> |  <span data-ttu-id="4ffa6-122">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="4ffa6-122">'Read all machine profiles'</span></span>
<span data-ttu-id="4ffa6-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="4ffa6-123">Application</span></span> |   <span data-ttu-id="4ffa6-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4ffa6-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="4ffa6-125">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="4ffa6-125">'Read and write all machine information'</span></span>
<span data-ttu-id="4ffa6-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="4ffa6-126">Delegated (work or school account)</span></span> | <span data-ttu-id="4ffa6-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="4ffa6-127">Machine.Read</span></span> | <span data-ttu-id="4ffa6-128">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="4ffa6-128">'Read machine information'</span></span>
<span data-ttu-id="4ffa6-129">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="4ffa6-129">Delegated (work or school account)</span></span> | <span data-ttu-id="4ffa6-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4ffa6-130">Machine.ReadWrite</span></span> | <span data-ttu-id="4ffa6-131">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="4ffa6-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="4ffa6-132">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="4ffa6-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4ffa6-133">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4ffa6-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4ffa6-134">响应将仅包括用户有权访问的设备，根据设备组设置 (请参阅创建和管理设备组，了解) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4ffa6-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4ffa6-135">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="4ffa6-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="4ffa6-136">请求标头</span><span class="sxs-lookup"><span data-stu-id="4ffa6-136">Request headers</span></span>

<span data-ttu-id="4ffa6-137">名称</span><span class="sxs-lookup"><span data-stu-id="4ffa6-137">Name</span></span> | <span data-ttu-id="4ffa6-138">类型</span><span class="sxs-lookup"><span data-stu-id="4ffa6-138">Type</span></span> | <span data-ttu-id="4ffa6-139">说明</span><span class="sxs-lookup"><span data-stu-id="4ffa6-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="4ffa6-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="4ffa6-140">Authorization</span></span> | <span data-ttu-id="4ffa6-141">String</span><span class="sxs-lookup"><span data-stu-id="4ffa6-141">String</span></span> | <span data-ttu-id="4ffa6-142">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-142">Bearer {token}.</span></span> <span data-ttu-id="4ffa6-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4ffa6-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="4ffa6-144">Request body</span></span>
<span data-ttu-id="4ffa6-145">Empty</span><span class="sxs-lookup"><span data-stu-id="4ffa6-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4ffa6-146">响应</span><span class="sxs-lookup"><span data-stu-id="4ffa6-146">Response</span></span>
<span data-ttu-id="4ffa6-147">如果成功且文件存在 - 200 正常[](machine.md)，正文中包含计算机实体列表。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="4ffa6-148">如果文件不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4ffa6-149">示例</span><span class="sxs-lookup"><span data-stu-id="4ffa6-149">Example</span></span>

<span data-ttu-id="4ffa6-150">**请求**</span><span class="sxs-lookup"><span data-stu-id="4ffa6-150">**Request**</span></span>

<span data-ttu-id="4ffa6-151">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="4ffa6-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
