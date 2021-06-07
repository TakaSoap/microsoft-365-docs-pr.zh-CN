---
title: 获取与文件相关的警报 API
description: 了解如何使用获取与文件相关的警报 API 获取与 Microsoft Defender for Endpoint 中的给定文件哈希相关的警报集合。
keywords: api， 图形 api， 受支持的 api， 获取， 文件， 哈希
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
ms.openlocfilehash: b77946f4bfdb793ffbfdf102a7221df083fb92eb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770290"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="60335-104">获取与文件相关的警报 API</span><span class="sxs-lookup"><span data-stu-id="60335-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60335-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="60335-105">**Applies to:**</span></span>
- [<span data-ttu-id="60335-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="60335-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="60335-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60335-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="60335-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="60335-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="60335-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="60335-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="60335-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="60335-110">API description</span></span>
<span data-ttu-id="60335-111">检索与给定文件哈希相关的警报集合。</span><span class="sxs-lookup"><span data-stu-id="60335-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="60335-112">限制</span><span class="sxs-lookup"><span data-stu-id="60335-112">Limitations</span></span>
1. <span data-ttu-id="60335-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="60335-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="60335-114">权限</span><span class="sxs-lookup"><span data-stu-id="60335-114">Permissions</span></span>
<span data-ttu-id="60335-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="60335-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="60335-116">若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="60335-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="60335-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="60335-117">Permission type</span></span> |   <span data-ttu-id="60335-118">权限</span><span class="sxs-lookup"><span data-stu-id="60335-118">Permission</span></span>  |   <span data-ttu-id="60335-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="60335-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="60335-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="60335-120">Application</span></span> |   <span data-ttu-id="60335-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="60335-121">Alert.Read.All</span></span> |    <span data-ttu-id="60335-122">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="60335-122">'Read all alerts'</span></span>
<span data-ttu-id="60335-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="60335-123">Application</span></span> |   <span data-ttu-id="60335-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="60335-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="60335-125">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="60335-125">'Read and write all alerts'</span></span>
<span data-ttu-id="60335-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="60335-126">Delegated (work or school account)</span></span> | <span data-ttu-id="60335-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="60335-127">Alert.Read</span></span> | <span data-ttu-id="60335-128">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="60335-128">'Read alerts'</span></span>
<span data-ttu-id="60335-129">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="60335-129">Delegated (work or school account)</span></span> | <span data-ttu-id="60335-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="60335-130">Alert.ReadWrite</span></span> | <span data-ttu-id="60335-131">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="60335-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="60335-132">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="60335-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="60335-133">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="60335-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="60335-134">根据设备组设置，响应将仅包含与设备关联的警报 (有关详细信息，请参阅创建和管理设备) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="60335-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="60335-135">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="60335-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="60335-136">请求标头</span><span class="sxs-lookup"><span data-stu-id="60335-136">Request headers</span></span>

<span data-ttu-id="60335-137">名称</span><span class="sxs-lookup"><span data-stu-id="60335-137">Name</span></span> | <span data-ttu-id="60335-138">类型</span><span class="sxs-lookup"><span data-stu-id="60335-138">Type</span></span> | <span data-ttu-id="60335-139">说明</span><span class="sxs-lookup"><span data-stu-id="60335-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="60335-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="60335-140">Authorization</span></span> | <span data-ttu-id="60335-141">String</span><span class="sxs-lookup"><span data-stu-id="60335-141">String</span></span> | <span data-ttu-id="60335-142">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="60335-142">Bearer {token}.</span></span> <span data-ttu-id="60335-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="60335-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="60335-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="60335-144">Request body</span></span>
<span data-ttu-id="60335-145">Empty</span><span class="sxs-lookup"><span data-stu-id="60335-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="60335-146">响应</span><span class="sxs-lookup"><span data-stu-id="60335-146">Response</span></span>
<span data-ttu-id="60335-147">如果成功且文件存在 - 200 正常，正文中 [具有警报](alerts.md) 实体列表。</span><span class="sxs-lookup"><span data-stu-id="60335-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="60335-148">如果文件不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="60335-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="60335-149">示例</span><span class="sxs-lookup"><span data-stu-id="60335-149">Example</span></span>

<span data-ttu-id="60335-150">**请求**</span><span class="sxs-lookup"><span data-stu-id="60335-150">**Request**</span></span>

<span data-ttu-id="60335-151">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="60335-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
