---
title: 获取调查对象 API
description: 使用此 API 创建与获取 Investigation 对象相关的调用
keywords: api， 图形 api， 受支持的 api， 调查对象
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
ms.openlocfilehash: 9f011f10a9fe3c3aec535e157abee2367998b1a4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166312"
---
# <a name="get-investigation-api"></a><span data-ttu-id="80149-104">获取调查 API</span><span class="sxs-lookup"><span data-stu-id="80149-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80149-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="80149-105">**Applies to:**</span></span>
- [<span data-ttu-id="80149-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="80149-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80149-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80149-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="80149-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="80149-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80149-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="80149-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="80149-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="80149-110">API description</span></span>
<span data-ttu-id="80149-111">按 ID [检索特定](investigation.md) 调查。</span><span class="sxs-lookup"><span data-stu-id="80149-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="80149-112">ID 可以是调查 ID 或触发警报 ID 的调查。</span><span class="sxs-lookup"><span data-stu-id="80149-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="80149-113">限制</span><span class="sxs-lookup"><span data-stu-id="80149-113">Limitations</span></span>
1. <span data-ttu-id="80149-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="80149-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="80149-115">权限</span><span class="sxs-lookup"><span data-stu-id="80149-115">Permissions</span></span>
<span data-ttu-id="80149-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="80149-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="80149-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="80149-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="80149-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="80149-118">Permission type</span></span> |   <span data-ttu-id="80149-119">权限</span><span class="sxs-lookup"><span data-stu-id="80149-119">Permission</span></span>  |   <span data-ttu-id="80149-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="80149-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="80149-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="80149-121">Application</span></span> |   <span data-ttu-id="80149-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="80149-122">Alert.Read.All</span></span> |    <span data-ttu-id="80149-123">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="80149-123">'Read all alerts'</span></span>
<span data-ttu-id="80149-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="80149-124">Application</span></span> |   <span data-ttu-id="80149-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="80149-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="80149-126">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="80149-126">'Read and write all alerts'</span></span>
<span data-ttu-id="80149-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="80149-127">Delegated (work or school account)</span></span> | <span data-ttu-id="80149-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="80149-128">Alert.Read</span></span> | <span data-ttu-id="80149-129">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="80149-129">'Read alerts'</span></span>
<span data-ttu-id="80149-130">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="80149-130">Delegated (work or school account)</span></span> | <span data-ttu-id="80149-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="80149-131">Alert.ReadWrite</span></span> | <span data-ttu-id="80149-132">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="80149-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="80149-133">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="80149-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="80149-134">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="80149-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="80149-135">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="80149-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="80149-136">请求标头</span><span class="sxs-lookup"><span data-stu-id="80149-136">Request headers</span></span>

<span data-ttu-id="80149-137">名称</span><span class="sxs-lookup"><span data-stu-id="80149-137">Name</span></span> | <span data-ttu-id="80149-138">类型</span><span class="sxs-lookup"><span data-stu-id="80149-138">Type</span></span> | <span data-ttu-id="80149-139">说明</span><span class="sxs-lookup"><span data-stu-id="80149-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="80149-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="80149-140">Authorization</span></span> | <span data-ttu-id="80149-141">String</span><span class="sxs-lookup"><span data-stu-id="80149-141">String</span></span> | <span data-ttu-id="80149-142">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="80149-142">Bearer {token}.</span></span> <span data-ttu-id="80149-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="80149-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="80149-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="80149-144">Request body</span></span>
<span data-ttu-id="80149-145">Empty</span><span class="sxs-lookup"><span data-stu-id="80149-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="80149-146">响应</span><span class="sxs-lookup"><span data-stu-id="80149-146">Response</span></span>
<span data-ttu-id="80149-147">如果成功，此方法使用 [Investigations](investigation.md) 实体返回 200 Ok 响应代码。</span><span class="sxs-lookup"><span data-stu-id="80149-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

