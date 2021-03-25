---
title: 支持的 Microsoft Defender 终结点 API
ms.reviewer: ''
description: 了解可在其中创建 API 调用的特定受支持的 Microsoft Defender 终结点实体。
keywords: api， 受支持的 api， 参与者， 警报， 设备， 用户， 域， ip， 文件， 高级查询， 高级搜寻
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198314"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="045d1-104">支持的 Microsoft Defender 终结点 API</span><span class="sxs-lookup"><span data-stu-id="045d1-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="045d1-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="045d1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="045d1-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="045d1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="045d1-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="045d1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="045d1-108">终结点 URI 和版本控制</span><span class="sxs-lookup"><span data-stu-id="045d1-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="045d1-109">终结点 URI：           </span><span class="sxs-lookup"><span data-stu-id="045d1-109">Endpoint URI:</span></span>

> <span data-ttu-id="045d1-110">服务基 URI 为： https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="045d1-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="045d1-111">基于查询的 OData 具有"/api"前缀。</span><span class="sxs-lookup"><span data-stu-id="045d1-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="045d1-112">例如，若要获取通知，可以将 GET 请求发送到 https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="045d1-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="045d1-113">版本控制：</span><span class="sxs-lookup"><span data-stu-id="045d1-113">Versioning:</span></span>

> <span data-ttu-id="045d1-114">API 支持版本控制。</span><span class="sxs-lookup"><span data-stu-id="045d1-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="045d1-115">当前版本为 **V1.0。**</span><span class="sxs-lookup"><span data-stu-id="045d1-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="045d1-116">若要使用特定版本，请使用此格式 `https://api.securitycenter.microsoft.com/api/{Version}` ：。</span><span class="sxs-lookup"><span data-stu-id="045d1-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="045d1-117">例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="045d1-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="045d1-118">如果不指定任何版本 (例如) https://api.securitycenter.microsoft.com/api/alerts 将进入最新版本。</span><span class="sxs-lookup"><span data-stu-id="045d1-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="045d1-119">详细了解可在其中运行 API 调用的单个受支持实体，以及诸如 HTTP 请求值、请求标头和预期响应等详细信息。</span><span class="sxs-lookup"><span data-stu-id="045d1-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="045d1-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="045d1-120">In this section</span></span>

<span data-ttu-id="045d1-121">主题</span><span class="sxs-lookup"><span data-stu-id="045d1-121">Topic</span></span> | <span data-ttu-id="045d1-122">说明</span><span class="sxs-lookup"><span data-stu-id="045d1-122">Description</span></span>
:---|:---
<span data-ttu-id="045d1-123">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="045d1-123">Advanced Hunting</span></span> | <span data-ttu-id="045d1-124">从 API 运行查询。</span><span class="sxs-lookup"><span data-stu-id="045d1-124">Run queries from API.</span></span>
<span data-ttu-id="045d1-125">警报</span><span class="sxs-lookup"><span data-stu-id="045d1-125">Alerts</span></span> | <span data-ttu-id="045d1-126">运行 API 调用，如获取警报、创建警报、更新警报等。</span><span class="sxs-lookup"><span data-stu-id="045d1-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="045d1-127">域</span><span class="sxs-lookup"><span data-stu-id="045d1-127">Domains</span></span> | <span data-ttu-id="045d1-128">运行 API 调用，如获取与域相关的设备、域统计信息等。</span><span class="sxs-lookup"><span data-stu-id="045d1-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="045d1-129">文件</span><span class="sxs-lookup"><span data-stu-id="045d1-129">Files</span></span> | <span data-ttu-id="045d1-130">运行 API 调用，如获取文件信息、文件相关警报、文件相关设备和文件统计信息。</span><span class="sxs-lookup"><span data-stu-id="045d1-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="045d1-131">IP</span><span class="sxs-lookup"><span data-stu-id="045d1-131">IPs</span></span> | <span data-ttu-id="045d1-132">运行 API 调用，如获取与 IP 相关的警报和获取 IP 统计信息。</span><span class="sxs-lookup"><span data-stu-id="045d1-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="045d1-133">计算机</span><span class="sxs-lookup"><span data-stu-id="045d1-133">Machines</span></span> | <span data-ttu-id="045d1-134">运行 API 调用，如获取设备、按 ID 获取设备、有关已登录用户的信息、编辑标记等。</span><span class="sxs-lookup"><span data-stu-id="045d1-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="045d1-135">计算机操作</span><span class="sxs-lookup"><span data-stu-id="045d1-135">Machine Actions</span></span> | <span data-ttu-id="045d1-136">运行 API 调用，如隔离、运行防病毒扫描等。</span><span class="sxs-lookup"><span data-stu-id="045d1-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="045d1-137">指示器</span><span class="sxs-lookup"><span data-stu-id="045d1-137">Indicators</span></span> | <span data-ttu-id="045d1-138">运行 API 调用，例如创建指示器、获取指示器和删除指示器。</span><span class="sxs-lookup"><span data-stu-id="045d1-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="045d1-139">用户</span><span class="sxs-lookup"><span data-stu-id="045d1-139">Users</span></span> | <span data-ttu-id="045d1-140">运行 API 调用，例如获取与用户相关的警报和与用户相关的设备。</span><span class="sxs-lookup"><span data-stu-id="045d1-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="045d1-141">得分</span><span class="sxs-lookup"><span data-stu-id="045d1-141">Score</span></span> | <span data-ttu-id="045d1-142">运行 API 调用（如获取曝光分数或获取设备安全分数）。</span><span class="sxs-lookup"><span data-stu-id="045d1-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="045d1-143">软件</span><span class="sxs-lookup"><span data-stu-id="045d1-143">Software</span></span> | <span data-ttu-id="045d1-144">运行 API 调用，如按软件列出漏洞。</span><span class="sxs-lookup"><span data-stu-id="045d1-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="045d1-145">漏洞</span><span class="sxs-lookup"><span data-stu-id="045d1-145">Vulnerability</span></span> | <span data-ttu-id="045d1-146">按漏洞运行 API 调用，如列表设备。</span><span class="sxs-lookup"><span data-stu-id="045d1-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="045d1-147">建议</span><span class="sxs-lookup"><span data-stu-id="045d1-147">Recommendation</span></span> | <span data-ttu-id="045d1-148">运行 API 调用，如按 ID 获取建议。</span><span class="sxs-lookup"><span data-stu-id="045d1-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="045d1-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="045d1-149">See also</span></span>
- [<span data-ttu-id="045d1-150">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="045d1-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
