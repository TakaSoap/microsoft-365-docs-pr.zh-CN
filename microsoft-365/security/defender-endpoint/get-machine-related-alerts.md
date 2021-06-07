---
title: 获取计算机相关警报 API
description: 了解如何使用获取计算机相关警报 API 检索与 Microsoft Defender for Endpoint 中的特定设备相关的所有警报。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 相关， 警报
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770021"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="959be-104">获取计算机相关警报 API</span><span class="sxs-lookup"><span data-stu-id="959be-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="959be-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="959be-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="959be-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="959be-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="959be-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="959be-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="959be-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="959be-108">API description</span></span>
<span data-ttu-id="959be-109">检索 [与特定](alerts.md) 设备相关的所有警报。</span><span class="sxs-lookup"><span data-stu-id="959be-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="959be-110">限制</span><span class="sxs-lookup"><span data-stu-id="959be-110">Limitations</span></span>
1. <span data-ttu-id="959be-111">你可以根据配置的保留期查询上次更新的设备。</span><span class="sxs-lookup"><span data-stu-id="959be-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="959be-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="959be-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="959be-113">权限类型</span><span class="sxs-lookup"><span data-stu-id="959be-113">Permission type</span></span> |   <span data-ttu-id="959be-114">权限</span><span class="sxs-lookup"><span data-stu-id="959be-114">Permission</span></span>  |   <span data-ttu-id="959be-115">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="959be-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="959be-116">应用程序</span><span class="sxs-lookup"><span data-stu-id="959be-116">Application</span></span> |   <span data-ttu-id="959be-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="959be-117">Alert.Read.All</span></span> |    <span data-ttu-id="959be-118">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="959be-118">'Read all alerts'</span></span>
<span data-ttu-id="959be-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="959be-119">Application</span></span> |   <span data-ttu-id="959be-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="959be-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="959be-121">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="959be-121">'Read and write all alerts'</span></span>
<span data-ttu-id="959be-122">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="959be-122">Delegated (work or school account)</span></span> | <span data-ttu-id="959be-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="959be-123">Alert.Read</span></span> | <span data-ttu-id="959be-124">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="959be-124">'Read alerts'</span></span>
<span data-ttu-id="959be-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="959be-125">Delegated (work or school account)</span></span> | <span data-ttu-id="959be-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="959be-126">Alert.ReadWrite</span></span> | <span data-ttu-id="959be-127">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="959be-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="959be-128">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="959be-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="959be-129">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="959be-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="959be-130">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="959be-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="959be-131">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="959be-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="959be-132">请求标头</span><span class="sxs-lookup"><span data-stu-id="959be-132">Request headers</span></span>

<span data-ttu-id="959be-133">名称</span><span class="sxs-lookup"><span data-stu-id="959be-133">Name</span></span> | <span data-ttu-id="959be-134">类型</span><span class="sxs-lookup"><span data-stu-id="959be-134">Type</span></span> | <span data-ttu-id="959be-135">说明</span><span class="sxs-lookup"><span data-stu-id="959be-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="959be-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="959be-136">Authorization</span></span> | <span data-ttu-id="959be-137">String</span><span class="sxs-lookup"><span data-stu-id="959be-137">String</span></span> | <span data-ttu-id="959be-138">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="959be-138">Bearer {token}.</span></span> <span data-ttu-id="959be-139">**必需**。</span><span class="sxs-lookup"><span data-stu-id="959be-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="959be-140">请求正文</span><span class="sxs-lookup"><span data-stu-id="959be-140">Request body</span></span>
<span data-ttu-id="959be-141">Empty</span><span class="sxs-lookup"><span data-stu-id="959be-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="959be-142">响应</span><span class="sxs-lookup"><span data-stu-id="959be-142">Response</span></span>
<span data-ttu-id="959be-143">如果成功且设备存在 - 200 正常[](alerts.md)，正文中具有警报实体列表。</span><span class="sxs-lookup"><span data-stu-id="959be-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="959be-144">如果未找到设备 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="959be-144">If device was not found - 404 Not Found.</span></span>
