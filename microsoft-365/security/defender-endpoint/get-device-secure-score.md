---
title: 获取设备安全分数
description: 检索组织设备安全分数。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166327"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="112e7-104">获取设备安全分数</span><span class="sxs-lookup"><span data-stu-id="112e7-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="112e7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="112e7-105">**Applies to:**</span></span>
- [<span data-ttu-id="112e7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="112e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="112e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="112e7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="112e7-108">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="112e7-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="112e7-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="112e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="112e7-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="112e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="112e7-111">检索你的 [Microsoft 设备安全分数](tvm-microsoft-secure-score-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="112e7-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="112e7-112">设备的 Microsoft 安全分数越高，你的终结点就更能够抵御网络安全威胁攻击。</span><span class="sxs-lookup"><span data-stu-id="112e7-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="112e7-113">权限</span><span class="sxs-lookup"><span data-stu-id="112e7-113">Permissions</span></span>

<span data-ttu-id="112e7-114">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="112e7-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="112e7-115">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="112e7-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="112e7-116">权限类型</span><span class="sxs-lookup"><span data-stu-id="112e7-116">Permission type</span></span> |   <span data-ttu-id="112e7-117">权限</span><span class="sxs-lookup"><span data-stu-id="112e7-117">Permission</span></span>  |   <span data-ttu-id="112e7-118">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="112e7-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="112e7-119">Application</span><span class="sxs-lookup"><span data-stu-id="112e7-119">Application</span></span> |   <span data-ttu-id="112e7-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="112e7-120">Score.Read.Alll</span></span> |   <span data-ttu-id="112e7-121">"读取威胁和漏洞管理分数"</span><span class="sxs-lookup"><span data-stu-id="112e7-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="112e7-122">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="112e7-122">Delegated (work or school account)</span></span> | <span data-ttu-id="112e7-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="112e7-123">Score.Read</span></span> | <span data-ttu-id="112e7-124">"读取威胁和漏洞管理分数"</span><span class="sxs-lookup"><span data-stu-id="112e7-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="112e7-125">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="112e7-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="112e7-126">请求标头</span><span class="sxs-lookup"><span data-stu-id="112e7-126">Request headers</span></span>

<span data-ttu-id="112e7-127">名称</span><span class="sxs-lookup"><span data-stu-id="112e7-127">Name</span></span> | <span data-ttu-id="112e7-128">类型</span><span class="sxs-lookup"><span data-stu-id="112e7-128">Type</span></span> | <span data-ttu-id="112e7-129">说明</span><span class="sxs-lookup"><span data-stu-id="112e7-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="112e7-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="112e7-130">Authorization</span></span> | <span data-ttu-id="112e7-131">String</span><span class="sxs-lookup"><span data-stu-id="112e7-131">String</span></span> | <span data-ttu-id="112e7-132">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="112e7-132">Bearer {token}.</span></span> <span data-ttu-id="112e7-133">**必需**。</span><span class="sxs-lookup"><span data-stu-id="112e7-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="112e7-134">请求正文</span><span class="sxs-lookup"><span data-stu-id="112e7-134">Request body</span></span>

<span data-ttu-id="112e7-135">Empty</span><span class="sxs-lookup"><span data-stu-id="112e7-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="112e7-136">响应</span><span class="sxs-lookup"><span data-stu-id="112e7-136">Response</span></span>

<span data-ttu-id="112e7-137">如果成功，此方法返回 200 OK，响应正文中显示设备安全分数数据。</span><span class="sxs-lookup"><span data-stu-id="112e7-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="112e7-138">示例</span><span class="sxs-lookup"><span data-stu-id="112e7-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="112e7-139">请求</span><span class="sxs-lookup"><span data-stu-id="112e7-139">Request</span></span>

<span data-ttu-id="112e7-140">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="112e7-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="112e7-141">响应</span><span class="sxs-lookup"><span data-stu-id="112e7-141">Response</span></span>

<span data-ttu-id="112e7-142">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="112e7-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="112e7-143">为简洁起见，可能会截断此处显示的响应列表。</span><span class="sxs-lookup"><span data-stu-id="112e7-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="112e7-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="112e7-144">See also</span></span>

- [<span data-ttu-id="112e7-145">使用 Microsoft Defender for Endpoint 的 OData 查询</span><span class="sxs-lookup"><span data-stu-id="112e7-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
