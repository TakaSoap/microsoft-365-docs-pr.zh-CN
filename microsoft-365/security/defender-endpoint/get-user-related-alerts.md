---
title: 获取与用户相关的警报 API
description: 使用 Microsoft Defender for Endpoint 检索与给定用户 ID 相关的警报集合。
keywords: api， 图形 api， 受支持的 api， 获取， 用户， 相关， 警报
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769925"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="0fcdf-104">获取与用户相关的警报 API</span><span class="sxs-lookup"><span data-stu-id="0fcdf-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0fcdf-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0fcdf-105">**Applies to:**</span></span>
- [<span data-ttu-id="0fcdf-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0fcdf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0fcdf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fcdf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0fcdf-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="0fcdf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0fcdf-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="0fcdf-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="0fcdf-110">API description</span></span>
<span data-ttu-id="0fcdf-111">检索与给定用户 ID 相关的警报集合。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="0fcdf-112">限制</span><span class="sxs-lookup"><span data-stu-id="0fcdf-112">Limitations</span></span>
1. <span data-ttu-id="0fcdf-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0fcdf-114">权限</span><span class="sxs-lookup"><span data-stu-id="0fcdf-114">Permissions</span></span>
<span data-ttu-id="0fcdf-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0fcdf-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0fcdf-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0fcdf-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="0fcdf-117">Permission type</span></span> |   <span data-ttu-id="0fcdf-118">权限</span><span class="sxs-lookup"><span data-stu-id="0fcdf-118">Permission</span></span>  |   <span data-ttu-id="0fcdf-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="0fcdf-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0fcdf-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="0fcdf-120">Application</span></span> |   <span data-ttu-id="0fcdf-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="0fcdf-121">Alert.Read.All</span></span> |    <span data-ttu-id="0fcdf-122">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="0fcdf-122">'Read all alerts'</span></span>
<span data-ttu-id="0fcdf-123">应用程序</span><span class="sxs-lookup"><span data-stu-id="0fcdf-123">Application</span></span> |   <span data-ttu-id="0fcdf-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0fcdf-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="0fcdf-125">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="0fcdf-125">'Read and write all alerts'</span></span>
<span data-ttu-id="0fcdf-126">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="0fcdf-126">Delegated (work or school account)</span></span> | <span data-ttu-id="0fcdf-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="0fcdf-127">Alert.Read</span></span> | <span data-ttu-id="0fcdf-128">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="0fcdf-128">'Read alerts'</span></span>
<span data-ttu-id="0fcdf-129">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="0fcdf-129">Delegated (work or school account)</span></span> | <span data-ttu-id="0fcdf-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0fcdf-130">Alert.ReadWrite</span></span> | <span data-ttu-id="0fcdf-131">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="0fcdf-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="0fcdf-132">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="0fcdf-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0fcdf-133">用户至少需要具有以下角色权限："查看数据"。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="0fcdf-134">有关详细信息，请参阅创建 [和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="0fcdf-135">根据设备组设置，响应将仅包含与设备关联的警报 (有关详细信息，请参阅创建和管理设备) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0fcdf-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0fcdf-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="0fcdf-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="0fcdf-137">**ID 不是完整的 UPN，而只是用户名。 (，例如，若要检索用户 user1@contoso.com /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="0fcdf-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="0fcdf-138">请求标头</span><span class="sxs-lookup"><span data-stu-id="0fcdf-138">Request headers</span></span>

<span data-ttu-id="0fcdf-139">名称</span><span class="sxs-lookup"><span data-stu-id="0fcdf-139">Name</span></span> | <span data-ttu-id="0fcdf-140">类型</span><span class="sxs-lookup"><span data-stu-id="0fcdf-140">Type</span></span> | <span data-ttu-id="0fcdf-141">说明</span><span class="sxs-lookup"><span data-stu-id="0fcdf-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="0fcdf-142">Authorization</span><span class="sxs-lookup"><span data-stu-id="0fcdf-142">Authorization</span></span> | <span data-ttu-id="0fcdf-143">String</span><span class="sxs-lookup"><span data-stu-id="0fcdf-143">String</span></span> | <span data-ttu-id="0fcdf-144">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-144">Bearer {token}.</span></span> <span data-ttu-id="0fcdf-145">**必需**。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0fcdf-146">请求正文</span><span class="sxs-lookup"><span data-stu-id="0fcdf-146">Request body</span></span>
<span data-ttu-id="0fcdf-147">Empty</span><span class="sxs-lookup"><span data-stu-id="0fcdf-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0fcdf-148">响应</span><span class="sxs-lookup"><span data-stu-id="0fcdf-148">Response</span></span>
<span data-ttu-id="0fcdf-149">如果成功且用户存在 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="0fcdf-150">如果用户不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="0fcdf-151">示例</span><span class="sxs-lookup"><span data-stu-id="0fcdf-151">Example</span></span>

<span data-ttu-id="0fcdf-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="0fcdf-152">**Request**</span></span>

<span data-ttu-id="0fcdf-153">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="0fcdf-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
