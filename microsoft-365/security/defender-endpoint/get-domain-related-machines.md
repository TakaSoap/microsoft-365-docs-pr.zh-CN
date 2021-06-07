---
title: 获取域相关的计算机 API
description: 了解如何使用获取域相关的计算机 API 获取与 Microsoft Defender for Endpoint 中的域通信的计算机或从中进行通信的计算机。
keywords: api， 图形 api， 受支持的 api， 获取， 域， 相关， 设备
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772217"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="f4a54-104">获取域相关的计算机 API</span><span class="sxs-lookup"><span data-stu-id="f4a54-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4a54-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f4a54-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4a54-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4a54-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4a54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4a54-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4a54-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f4a54-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4a54-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f4a54-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f4a54-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="f4a54-110">API description</span></span>
<span data-ttu-id="f4a54-111">检索 [与给定域](machine.md) 地址通信的计算机的集合。</span><span class="sxs-lookup"><span data-stu-id="f4a54-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="f4a54-112">限制</span><span class="sxs-lookup"><span data-stu-id="f4a54-112">Limitations</span></span>
1. <span data-ttu-id="f4a54-113">你可以根据配置的保留期查询上次更新的设备。</span><span class="sxs-lookup"><span data-stu-id="f4a54-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="f4a54-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="f4a54-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f4a54-115">权限</span><span class="sxs-lookup"><span data-stu-id="f4a54-115">Permissions</span></span>
<span data-ttu-id="f4a54-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="f4a54-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f4a54-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f4a54-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f4a54-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="f4a54-118">Permission type</span></span> |   <span data-ttu-id="f4a54-119">权限</span><span class="sxs-lookup"><span data-stu-id="f4a54-119">Permission</span></span>  |   <span data-ttu-id="f4a54-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="f4a54-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f4a54-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="f4a54-121">Application</span></span> |   <span data-ttu-id="f4a54-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="f4a54-122">Machine.Read.All</span></span> |  <span data-ttu-id="f4a54-123">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="f4a54-123">'Read all machine profiles'</span></span>
<span data-ttu-id="f4a54-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="f4a54-124">Application</span></span> |   <span data-ttu-id="f4a54-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4a54-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="f4a54-126">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="f4a54-126">'Read and write all machine information'</span></span>
<span data-ttu-id="f4a54-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="f4a54-127">Delegated (work or school account)</span></span> | <span data-ttu-id="f4a54-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="f4a54-128">Machine.Read</span></span> | <span data-ttu-id="f4a54-129">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="f4a54-129">'Read machine information'</span></span>
<span data-ttu-id="f4a54-130">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="f4a54-130">Delegated (work or school account)</span></span> | <span data-ttu-id="f4a54-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f4a54-131">Machine.ReadWrite</span></span> | <span data-ttu-id="f4a54-132">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="f4a54-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="f4a54-133">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="f4a54-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f4a54-134">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f4a54-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f4a54-135">响应将仅包括用户可以访问的设备，基于设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="f4a54-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f4a54-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="f4a54-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="f4a54-137">请求标头</span><span class="sxs-lookup"><span data-stu-id="f4a54-137">Request headers</span></span>

<span data-ttu-id="f4a54-138">名称</span><span class="sxs-lookup"><span data-stu-id="f4a54-138">Name</span></span> | <span data-ttu-id="f4a54-139">类型</span><span class="sxs-lookup"><span data-stu-id="f4a54-139">Type</span></span> | <span data-ttu-id="f4a54-140">说明</span><span class="sxs-lookup"><span data-stu-id="f4a54-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="f4a54-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="f4a54-141">Authorization</span></span> | <span data-ttu-id="f4a54-142">String</span><span class="sxs-lookup"><span data-stu-id="f4a54-142">String</span></span> | <span data-ttu-id="f4a54-143">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="f4a54-143">Bearer {token}.</span></span> <span data-ttu-id="f4a54-144">**必需**。</span><span class="sxs-lookup"><span data-stu-id="f4a54-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f4a54-145">请求正文</span><span class="sxs-lookup"><span data-stu-id="f4a54-145">Request body</span></span>
<span data-ttu-id="f4a54-146">Empty</span><span class="sxs-lookup"><span data-stu-id="f4a54-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f4a54-147">响应</span><span class="sxs-lookup"><span data-stu-id="f4a54-147">Response</span></span>
<span data-ttu-id="f4a54-148">如果成功且域存在 - 200 正常，包含 [计算机实体](machine.md) 列表。</span><span class="sxs-lookup"><span data-stu-id="f4a54-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="f4a54-149">如果域不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="f4a54-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f4a54-150">示例</span><span class="sxs-lookup"><span data-stu-id="f4a54-150">Example</span></span>

<span data-ttu-id="f4a54-151">**请求**</span><span class="sxs-lookup"><span data-stu-id="f4a54-151">**Request**</span></span>

<span data-ttu-id="f4a54-152">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="f4a54-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
