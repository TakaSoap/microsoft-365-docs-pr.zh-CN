---
title: 通过 ID API 获取警报信息
description: 了解如何使用按 ID 获取警报信息 API 在 Microsoft Defender for Endpoint 中按其 ID 检索特定警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 信息， id
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
ms.openlocfilehash: f9130b054ccea762e6c5cc4f2952bbfa82d24b83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200421"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="58c29-104">通过 ID API 获取警报信息</span><span class="sxs-lookup"><span data-stu-id="58c29-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="58c29-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="58c29-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="58c29-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="58c29-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="58c29-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="58c29-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="58c29-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="58c29-108">API description</span></span>
<span data-ttu-id="58c29-109">按其 ID [检索](alerts.md) 特定警报。</span><span class="sxs-lookup"><span data-stu-id="58c29-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="58c29-110">限制</span><span class="sxs-lookup"><span data-stu-id="58c29-110">Limitations</span></span>
1. <span data-ttu-id="58c29-111">你可以根据配置的保留期获取上次更新的警报。</span><span class="sxs-lookup"><span data-stu-id="58c29-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="58c29-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="58c29-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="58c29-113">权限</span><span class="sxs-lookup"><span data-stu-id="58c29-113">Permissions</span></span>
<span data-ttu-id="58c29-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="58c29-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="58c29-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="58c29-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="58c29-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="58c29-116">Permission type</span></span> |   <span data-ttu-id="58c29-117">权限</span><span class="sxs-lookup"><span data-stu-id="58c29-117">Permission</span></span>  |   <span data-ttu-id="58c29-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="58c29-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="58c29-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="58c29-119">Application</span></span> |   <span data-ttu-id="58c29-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="58c29-120">Alert.Read.All</span></span> |    <span data-ttu-id="58c29-121">"读取所有警报"</span><span class="sxs-lookup"><span data-stu-id="58c29-121">'Read all alerts'</span></span>
<span data-ttu-id="58c29-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="58c29-122">Application</span></span> |   <span data-ttu-id="58c29-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="58c29-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="58c29-124">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="58c29-124">'Read and write all alerts'</span></span>
<span data-ttu-id="58c29-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="58c29-125">Delegated (work or school account)</span></span> | <span data-ttu-id="58c29-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="58c29-126">Alert.Read</span></span> | <span data-ttu-id="58c29-127">"读取警报"</span><span class="sxs-lookup"><span data-stu-id="58c29-127">'Read alerts'</span></span>
<span data-ttu-id="58c29-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="58c29-128">Delegated (work or school account)</span></span> | <span data-ttu-id="58c29-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="58c29-129">Alert.ReadWrite</span></span> | <span data-ttu-id="58c29-130">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="58c29-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="58c29-131">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="58c29-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="58c29-132">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="58c29-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="58c29-133">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="58c29-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="58c29-134">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="58c29-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="58c29-135">请求标头</span><span class="sxs-lookup"><span data-stu-id="58c29-135">Request headers</span></span>

<span data-ttu-id="58c29-136">名称</span><span class="sxs-lookup"><span data-stu-id="58c29-136">Name</span></span> | <span data-ttu-id="58c29-137">类型</span><span class="sxs-lookup"><span data-stu-id="58c29-137">Type</span></span> | <span data-ttu-id="58c29-138">说明</span><span class="sxs-lookup"><span data-stu-id="58c29-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="58c29-139">Authorization</span><span class="sxs-lookup"><span data-stu-id="58c29-139">Authorization</span></span> | <span data-ttu-id="58c29-140">字符串</span><span class="sxs-lookup"><span data-stu-id="58c29-140">String</span></span> | <span data-ttu-id="58c29-141">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="58c29-141">Bearer {token}.</span></span> <span data-ttu-id="58c29-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="58c29-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="58c29-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="58c29-143">Request body</span></span>
<span data-ttu-id="58c29-144">Empty</span><span class="sxs-lookup"><span data-stu-id="58c29-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="58c29-145">响应</span><span class="sxs-lookup"><span data-stu-id="58c29-145">Response</span></span>
<span data-ttu-id="58c29-146">如果成功，此方法在响应正文中返回 200 OK 和 [alert](alerts.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="58c29-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="58c29-147">如果未找到具有指定 ID 的警报 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="58c29-147">If alert with the specified id was not found - 404 Not Found.</span></span>
