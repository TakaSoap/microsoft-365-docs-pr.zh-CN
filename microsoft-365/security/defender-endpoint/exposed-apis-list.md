---
title: 支持的 Microsoft Defender for Endpoint API
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073825"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="ff4dc-104">支持的 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="ff4dc-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ff4dc-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ff4dc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ff4dc-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ff4dc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ff4dc-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="ff4dc-108">终结点 URI 和版本控制</span><span class="sxs-lookup"><span data-stu-id="ff4dc-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="ff4dc-109">终结点 URI</span><span class="sxs-lookup"><span data-stu-id="ff4dc-109">Endpoint URI</span></span>

> <span data-ttu-id="ff4dc-110">服务基 URI 为： [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ff4dc-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="ff4dc-111">基于查询的 OData 具有"/api"前缀。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="ff4dc-112">例如，若要获取通知，可以将 GET 请求发送到 [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="ff4dc-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="ff4dc-113">版本控制</span><span class="sxs-lookup"><span data-stu-id="ff4dc-113">Versioning</span></span>

> <span data-ttu-id="ff4dc-114">API 支持版本控制。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="ff4dc-115">当前版本为 **V1.0。**</span><span class="sxs-lookup"><span data-stu-id="ff4dc-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="ff4dc-116">若要使用特定版本，请使用此格式 `https://api.securitycenter.microsoft.com/api/{Version}` ：。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="ff4dc-117">例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="ff4dc-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="ff4dc-118">如果不指定任何版本 (例如) `https://api.securitycenter.microsoft.com/api/alerts` 将进入最新版本。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="ff4dc-119">详细了解可在其中运行 API 调用的单个受支持实体，以及诸如 HTTP 请求值、请求标头和预期响应等详细信息。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ff4dc-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="ff4dc-120">In this section</span></span>

<span data-ttu-id="ff4dc-121">主题</span><span class="sxs-lookup"><span data-stu-id="ff4dc-121">Topic</span></span> | <span data-ttu-id="ff4dc-122">说明</span><span class="sxs-lookup"><span data-stu-id="ff4dc-122">Description</span></span>
:---|:---
[<span data-ttu-id="ff4dc-123">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="ff4dc-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="ff4dc-124">从 API 运行查询。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-124">Run queries from API.</span></span>
[<span data-ttu-id="ff4dc-125">警报方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="ff4dc-126">运行 API 调用，如 \- 获取警报、创建警报、更新警报等。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="ff4dc-127">自动调查方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="ff4dc-128">运行 API 调用，如 \- 获取调查集合。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="ff4dc-129">获取域相关警报</span><span class="sxs-lookup"><span data-stu-id="ff4dc-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="ff4dc-130">运行 API 调用，如 \- 获取与域相关的设备、域统计信息等。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="ff4dc-131">文件方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="ff4dc-132">运行 API 调用，如 \- 获取文件信息、文件相关警报、文件相关设备和文件统计信息。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="ff4dc-133">指示器方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="ff4dc-134">运行 API 调用，如 \- 获取指示器、创建指示器和删除指示器。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="ff4dc-135">获取 IP 相关警报</span><span class="sxs-lookup"><span data-stu-id="ff4dc-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="ff4dc-136">运行 API 调用， \- 如获取与 IP 相关的警报和获取 IP 统计信息。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="ff4dc-137">计算机方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="ff4dc-138">运行 API 调用，如获取设备、按 ID 获取设备、有关已登录用户的信息 \- 、编辑标记等。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="ff4dc-139">计算机操作方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="ff4dc-140">运行 API 调用， \- 如隔离、运行防病毒扫描等。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="ff4dc-141">建议方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="ff4dc-142">运行 API 调用，例如 \- 按 ID 获取建议。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="ff4dc-143">分数方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="ff4dc-144">运行 API 调用（如 \- 获取曝光分数或获取设备安全分数）。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="ff4dc-145">软件方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="ff4dc-146">运行 API 调用，如 \- 按软件列出漏洞。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="ff4dc-147">用户方法</span><span class="sxs-lookup"><span data-stu-id="ff4dc-147">User methods</span></span>](user.md) | <span data-ttu-id="ff4dc-148">运行 API 调用，例如 \- 获取与用户相关的警报和与用户相关的设备。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="ff4dc-149">漏洞方法和属性</span><span class="sxs-lookup"><span data-stu-id="ff4dc-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="ff4dc-150">按漏洞运行 API 调用 \- ，如列表设备。</span><span class="sxs-lookup"><span data-stu-id="ff4dc-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff4dc-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff4dc-151">See also</span></span>

- [<span data-ttu-id="ff4dc-152">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="ff4dc-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="ff4dc-153">Microsoft Defender for Endpoint API 发行说明</span><span class="sxs-lookup"><span data-stu-id="ff4dc-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
