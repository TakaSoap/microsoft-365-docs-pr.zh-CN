---
title: 按内部 IP API 查找设备
description: 查找在给定时间戳之前和之后 15 分钟的时间范围内使用请求的内部 IP 查看的设备
keywords: api， 图形 api， 受支持的 api， 获取， 设备， IP， 查找， 查找设备， 按 ip， ip
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
ms.openlocfilehash: fa523a7f9b997f3a8d36dff42d10c1229e7a467f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200433"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="8f095-104">按内部 IP API 查找设备</span><span class="sxs-lookup"><span data-stu-id="8f095-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8f095-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8f095-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="8f095-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8f095-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8f095-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8f095-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8f095-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="8f095-108">API description</span></span>
<span data-ttu-id="8f095-109">查找 [在](machine.md) 给定时间戳之前和之后 15 分钟的时间范围内使用请求的内部 IP 看到的计算机。</span><span class="sxs-lookup"><span data-stu-id="8f095-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="8f095-110">限制</span><span class="sxs-lookup"><span data-stu-id="8f095-110">Limitations</span></span>
1. <span data-ttu-id="8f095-111">给定的时间戳必须过去 30 天。</span><span class="sxs-lookup"><span data-stu-id="8f095-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="8f095-112">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="8f095-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8f095-113">权限</span><span class="sxs-lookup"><span data-stu-id="8f095-113">Permissions</span></span>
<span data-ttu-id="8f095-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="8f095-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8f095-115">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8f095-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8f095-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="8f095-116">Permission type</span></span> |   <span data-ttu-id="8f095-117">权限</span><span class="sxs-lookup"><span data-stu-id="8f095-117">Permission</span></span>  |   <span data-ttu-id="8f095-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="8f095-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8f095-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="8f095-119">Application</span></span> |   <span data-ttu-id="8f095-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="8f095-120">Machine.Read.All</span></span> |  <span data-ttu-id="8f095-121">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="8f095-121">'Read all machine profiles'</span></span>
<span data-ttu-id="8f095-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="8f095-122">Application</span></span> |   <span data-ttu-id="8f095-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8f095-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="8f095-124">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="8f095-124">'Read and write all machine information'</span></span>
<span data-ttu-id="8f095-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="8f095-125">Delegated (work or school account)</span></span> | <span data-ttu-id="8f095-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="8f095-126">Machine.Read</span></span> | <span data-ttu-id="8f095-127">"读取计算机信息"</span><span class="sxs-lookup"><span data-stu-id="8f095-127">'Read machine information'</span></span>
<span data-ttu-id="8f095-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="8f095-128">Delegated (work or school account)</span></span> | <span data-ttu-id="8f095-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8f095-129">Machine.ReadWrite</span></span> | <span data-ttu-id="8f095-130">"读取和写入计算机信息"</span><span class="sxs-lookup"><span data-stu-id="8f095-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="8f095-131">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="8f095-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="8f095-132">响应将仅包括用户基于设备组设置有权访问的设备 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="8f095-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="8f095-133">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8f095-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="8f095-134">响应将仅包括用户基于设备组设置有权访问的设备 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="8f095-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8f095-135">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="8f095-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="8f095-136">请求标头</span><span class="sxs-lookup"><span data-stu-id="8f095-136">Request headers</span></span>

<span data-ttu-id="8f095-137">名称</span><span class="sxs-lookup"><span data-stu-id="8f095-137">Name</span></span> | <span data-ttu-id="8f095-138">类型</span><span class="sxs-lookup"><span data-stu-id="8f095-138">Type</span></span> | <span data-ttu-id="8f095-139">说明</span><span class="sxs-lookup"><span data-stu-id="8f095-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="8f095-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="8f095-140">Authorization</span></span> | <span data-ttu-id="8f095-141">字符串</span><span class="sxs-lookup"><span data-stu-id="8f095-141">String</span></span> | <span data-ttu-id="8f095-142">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="8f095-142">Bearer {token}.</span></span> <span data-ttu-id="8f095-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="8f095-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8f095-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="8f095-144">Request body</span></span>
<span data-ttu-id="8f095-145">Empty</span><span class="sxs-lookup"><span data-stu-id="8f095-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8f095-146">响应</span><span class="sxs-lookup"><span data-stu-id="8f095-146">Response</span></span>
<span data-ttu-id="8f095-147">如果成功 - 200 正常，响应正文中提供计算机列表。</span><span class="sxs-lookup"><span data-stu-id="8f095-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="8f095-148">如果时间戳不是过去 30 天 - 400 错误请求。</span><span class="sxs-lookup"><span data-stu-id="8f095-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="8f095-149">示例</span><span class="sxs-lookup"><span data-stu-id="8f095-149">Example</span></span>

<span data-ttu-id="8f095-150">**请求**</span><span class="sxs-lookup"><span data-stu-id="8f095-150">**Request**</span></span>

<span data-ttu-id="8f095-151">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="8f095-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
