---
title: 通过内部 IP API 查找设备信息
description: 使用此 API 创建与通过内部 IP 查找特定时间戳周围的设备条目相关的调用。
keywords: ip， api， 图形 api， 受支持的 api， 查找设备， 设备信息
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166467"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="99463-104">通过内部 IP API 查找设备信息</span><span class="sxs-lookup"><span data-stu-id="99463-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99463-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="99463-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="99463-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="99463-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="99463-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="99463-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="99463-108">通过内部 IP 查找设备。</span><span class="sxs-lookup"><span data-stu-id="99463-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="99463-109">时间戳必须在最近 30 天内。</span><span class="sxs-lookup"><span data-stu-id="99463-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="99463-110">权限</span><span class="sxs-lookup"><span data-stu-id="99463-110">Permissions</span></span>
<span data-ttu-id="99463-111">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="99463-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="99463-112">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="99463-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="99463-113">权限类型</span><span class="sxs-lookup"><span data-stu-id="99463-113">Permission type</span></span> | <span data-ttu-id="99463-114">权限</span><span class="sxs-lookup"><span data-stu-id="99463-114">Permission</span></span> | <span data-ttu-id="99463-115">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="99463-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="99463-116">应用程序</span><span class="sxs-lookup"><span data-stu-id="99463-116">Application</span></span> | <span data-ttu-id="99463-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="99463-117">Machine.Read.All</span></span> | <span data-ttu-id="99463-118">"读取所有计算机配置文件"</span><span class="sxs-lookup"><span data-stu-id="99463-118">'Read all machine profiles'</span></span>
<span data-ttu-id="99463-119">应用程序</span><span class="sxs-lookup"><span data-stu-id="99463-119">Application</span></span> | <span data-ttu-id="99463-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="99463-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="99463-121">"读取和写入所有计算机信息"</span><span class="sxs-lookup"><span data-stu-id="99463-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="99463-122">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="99463-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="99463-123">请求标头</span><span class="sxs-lookup"><span data-stu-id="99463-123">Request headers</span></span>

<span data-ttu-id="99463-124">名称</span><span class="sxs-lookup"><span data-stu-id="99463-124">Name</span></span> | <span data-ttu-id="99463-125">类型</span><span class="sxs-lookup"><span data-stu-id="99463-125">Type</span></span> | <span data-ttu-id="99463-126">说明</span><span class="sxs-lookup"><span data-stu-id="99463-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="99463-127">Authorization</span><span class="sxs-lookup"><span data-stu-id="99463-127">Authorization</span></span> | <span data-ttu-id="99463-128">String</span><span class="sxs-lookup"><span data-stu-id="99463-128">String</span></span> | <span data-ttu-id="99463-129">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="99463-129">Bearer {token}.</span></span> <span data-ttu-id="99463-130">**必需**。</span><span class="sxs-lookup"><span data-stu-id="99463-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="99463-131">请求正文</span><span class="sxs-lookup"><span data-stu-id="99463-131">Request body</span></span>
<span data-ttu-id="99463-132">Empty</span><span class="sxs-lookup"><span data-stu-id="99463-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="99463-133">响应</span><span class="sxs-lookup"><span data-stu-id="99463-133">Response</span></span>
<span data-ttu-id="99463-134">如果成功且计算机存在 - 200 正常。</span><span class="sxs-lookup"><span data-stu-id="99463-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="99463-135">如果未找到计算机 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="99463-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="99463-136">示例</span><span class="sxs-lookup"><span data-stu-id="99463-136">Example</span></span>

<span data-ttu-id="99463-137">**请求**</span><span class="sxs-lookup"><span data-stu-id="99463-137">**Request**</span></span>

<span data-ttu-id="99463-138">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="99463-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="99463-139">**响应**</span><span class="sxs-lookup"><span data-stu-id="99463-139">**Response**</span></span>

<span data-ttu-id="99463-140">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="99463-140">Here is an example of the response.</span></span>

<span data-ttu-id="99463-141">响应将返回时间戳之前和之后 16 分钟内报告此 IP 地址的所有设备的列表。</span><span class="sxs-lookup"><span data-stu-id="99463-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
