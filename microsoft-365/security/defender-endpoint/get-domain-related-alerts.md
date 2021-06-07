---
title: 获取与域相关的警报 API
description: 了解如何使用获取域相关警报 API 检索与 Microsoft Defender for Endpoint 中的给定域地址相关的警报。
keywords: api， 图形 api， 受支持的 api， 获取， 域， 相关， 警报
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
ms.openlocfilehash: c5de779566f1aa8e53da10b9aa5bceb92f5a0a3c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772253"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="db1fb-104">获取与域相关的警报 API</span><span class="sxs-lookup"><span data-stu-id="db1fb-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="db1fb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db1fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="db1fb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db1fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="db1fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db1fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="db1fb-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="db1fb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="db1fb-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="db1fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="db1fb-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="db1fb-110">API description</span></span>
<span data-ttu-id="db1fb-111">检索与给定 [域](alerts.md) 地址相关的警报集合。</span><span class="sxs-lookup"><span data-stu-id="db1fb-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="db1fb-112">限制</span><span class="sxs-lookup"><span data-stu-id="db1fb-112">Limitations</span></span>
1. <span data-ttu-id="db1fb-113">你可以根据配置的保留期查询上次更新的警报。</span><span class="sxs-lookup"><span data-stu-id="db1fb-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="db1fb-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="db1fb-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="db1fb-115">权限</span><span class="sxs-lookup"><span data-stu-id="db1fb-115">Permissions</span></span>
<span data-ttu-id="db1fb-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="db1fb-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="db1fb-117">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="db1fb-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="db1fb-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="db1fb-118">Permission type</span></span> |   <span data-ttu-id="db1fb-119">权限</span><span class="sxs-lookup"><span data-stu-id="db1fb-119">Permission</span></span>  |   <span data-ttu-id="db1fb-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="db1fb-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="db1fb-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="db1fb-121">Application</span></span> |   <span data-ttu-id="db1fb-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="db1fb-122">Alert.Read.All</span></span> |    <span data-ttu-id="db1fb-123">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="db1fb-123">'Read all alerts'</span></span>
<span data-ttu-id="db1fb-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="db1fb-124">Application</span></span> |   <span data-ttu-id="db1fb-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="db1fb-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="db1fb-126">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="db1fb-126">'Read and write all alerts'</span></span>
<span data-ttu-id="db1fb-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="db1fb-127">Delegated (work or school account)</span></span> | <span data-ttu-id="db1fb-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="db1fb-128">Alert.Read</span></span> | <span data-ttu-id="db1fb-129">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="db1fb-129">'Read alerts'</span></span>
<span data-ttu-id="db1fb-130">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="db1fb-130">Delegated (work or school account)</span></span> | <span data-ttu-id="db1fb-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="db1fb-131">Alert.ReadWrite</span></span> | <span data-ttu-id="db1fb-132">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="db1fb-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="db1fb-133">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="db1fb-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="db1fb-134">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="db1fb-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="db1fb-135">根据设备组设置，响应将仅包含与设备关联的警报 (有关详细信息，请参阅创建和管理设备) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="db1fb-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="db1fb-136">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="db1fb-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="db1fb-137">请求标头</span><span class="sxs-lookup"><span data-stu-id="db1fb-137">Request headers</span></span>

| <span data-ttu-id="db1fb-138">标头</span><span class="sxs-lookup"><span data-stu-id="db1fb-138">Header</span></span>        | <span data-ttu-id="db1fb-139">值</span><span class="sxs-lookup"><span data-stu-id="db1fb-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="db1fb-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="db1fb-140">Authorization</span></span> | <span data-ttu-id="db1fb-141">String</span><span class="sxs-lookup"><span data-stu-id="db1fb-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="db1fb-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="db1fb-142">Request body</span></span>
<span data-ttu-id="db1fb-143">Empty</span><span class="sxs-lookup"><span data-stu-id="db1fb-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="db1fb-144">响应</span><span class="sxs-lookup"><span data-stu-id="db1fb-144">Response</span></span>
<span data-ttu-id="db1fb-145">如果成功且域存在 - 200 正常，警报 [实体](alerts.md) 列表可用。</span><span class="sxs-lookup"><span data-stu-id="db1fb-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="db1fb-146">如果域不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="db1fb-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="db1fb-147">示例</span><span class="sxs-lookup"><span data-stu-id="db1fb-147">Example</span></span>

<span data-ttu-id="db1fb-148">**请求**</span><span class="sxs-lookup"><span data-stu-id="db1fb-148">**Request**</span></span>

<span data-ttu-id="db1fb-149">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="db1fb-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
