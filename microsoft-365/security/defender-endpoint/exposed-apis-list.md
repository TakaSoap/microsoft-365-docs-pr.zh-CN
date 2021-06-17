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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d0efd97359440ffb3d4b39b6389b477203c56084
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984996"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="1746b-104">支持的 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="1746b-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1746b-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1746b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="1746b-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1746b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1746b-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1746b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="1746b-108">终结点 URI 和版本控制</span><span class="sxs-lookup"><span data-stu-id="1746b-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="1746b-109">终结点 URI</span><span class="sxs-lookup"><span data-stu-id="1746b-109">Endpoint URI</span></span>

> <span data-ttu-id="1746b-110">服务基 URI 为： [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1746b-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="1746b-111">基于查询的 OData 具有"/api"前缀。</span><span class="sxs-lookup"><span data-stu-id="1746b-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="1746b-112">例如，若要获取通知，可以将 GET 请求发送到 [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="1746b-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="1746b-113">版本控制</span><span class="sxs-lookup"><span data-stu-id="1746b-113">Versioning</span></span>

> <span data-ttu-id="1746b-114">API 支持版本控制。</span><span class="sxs-lookup"><span data-stu-id="1746b-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="1746b-115">当前版本为 **V1.0。**</span><span class="sxs-lookup"><span data-stu-id="1746b-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="1746b-116">若要使用特定版本，请使用此格式 `https://api.securitycenter.microsoft.com/api/{Version}` ：。</span><span class="sxs-lookup"><span data-stu-id="1746b-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="1746b-117">例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="1746b-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="1746b-118">如果不指定任何版本 (例如) `https://api.securitycenter.microsoft.com/api/alerts` 将进入最新版本。</span><span class="sxs-lookup"><span data-stu-id="1746b-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="1746b-119">详细了解可在其中运行 API 调用的单个受支持实体，以及诸如 HTTP 请求值、请求标头和预期响应等详细信息。</span><span class="sxs-lookup"><span data-stu-id="1746b-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1746b-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="1746b-120">In this section</span></span>

<span data-ttu-id="1746b-121">主题</span><span class="sxs-lookup"><span data-stu-id="1746b-121">Topic</span></span> | <span data-ttu-id="1746b-122">说明</span><span class="sxs-lookup"><span data-stu-id="1746b-122">Description</span></span>
:---|:---
[<span data-ttu-id="1746b-123">高级搜寻</span><span class="sxs-lookup"><span data-stu-id="1746b-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="1746b-124">从 API 运行查询。</span><span class="sxs-lookup"><span data-stu-id="1746b-124">Run queries from API.</span></span>
[<span data-ttu-id="1746b-125">警报方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="1746b-126">运行 API 调用，如 \- 获取警报、创建警报、更新警报等。</span><span class="sxs-lookup"><span data-stu-id="1746b-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="1746b-127">导出每个设备的评估方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-127">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md) | <span data-ttu-id="1746b-128">运行 API 调用以按设备收集漏洞评估，例如：导出安全配置评估、导出软件清单评估、导出软件漏洞评估和增量导出软件 \- 漏洞评估。</span><span class="sxs-lookup"><span data-stu-id="1746b-128">Run API calls to gather vulnerability assessments on a per-device basis, such as: \- export secure configuration assessment, export software inventory assessment,  export software vulnerabilities assessment, and delta export software vulnerabilities assessment.</span></span>
[<span data-ttu-id="1746b-129">自动调查方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-129">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="1746b-130">运行 API 调用，如 \- 获取调查集合。</span><span class="sxs-lookup"><span data-stu-id="1746b-130">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="1746b-131">获取域相关警报</span><span class="sxs-lookup"><span data-stu-id="1746b-131">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="1746b-132">运行 API 调用，如 \- 获取与域相关的设备、域统计信息等。</span><span class="sxs-lookup"><span data-stu-id="1746b-132">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="1746b-133">文件方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-133">File methods and properties</span></span>](files.md) | <span data-ttu-id="1746b-134">运行 API 调用，如 \- 获取文件信息、文件相关警报、文件相关设备和文件统计信息。</span><span class="sxs-lookup"><span data-stu-id="1746b-134">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="1746b-135">指示器方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-135">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="1746b-136">运行 API 调用，如 \- 获取指示器、创建指示器和删除指示器。</span><span class="sxs-lookup"><span data-stu-id="1746b-136">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="1746b-137">获取 IP 相关警报</span><span class="sxs-lookup"><span data-stu-id="1746b-137">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="1746b-138">运行 API 调用， \- 如获取与 IP 相关的警报和获取 IP 统计信息。</span><span class="sxs-lookup"><span data-stu-id="1746b-138">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="1746b-139">计算机方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-139">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="1746b-140">运行 API 调用，如获取设备、按 ID 获取设备、有关已登录用户的信息 \- 、编辑标记等。</span><span class="sxs-lookup"><span data-stu-id="1746b-140">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="1746b-141">计算机操作方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-141">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="1746b-142">运行 API 调用， \- 如隔离、运行防病毒扫描等。</span><span class="sxs-lookup"><span data-stu-id="1746b-142">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="1746b-143">建议方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-143">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="1746b-144">运行 API 调用，例如 \- 按 ID 获取建议。</span><span class="sxs-lookup"><span data-stu-id="1746b-144">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="1746b-145">修正活动方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-145">Remediation activity methods and properties</span></span>](get-remediation-methods-properties.md) | <span data-ttu-id="1746b-146">运行 API 调用（如 \- 获取所有修正任务、获取公开的设备修正任务和按 id 获取一个修正任务）。</span><span class="sxs-lookup"><span data-stu-id="1746b-146">Run API call such as \- get all remediation tasks, get exposed devices remediation task and get one remediation task by id.</span></span>
[<span data-ttu-id="1746b-147">分数方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-147">Score methods and properties</span></span>](score.md) | <span data-ttu-id="1746b-148">运行 API 调用（如 \- 获取曝光分数或获取设备安全分数）。</span><span class="sxs-lookup"><span data-stu-id="1746b-148">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="1746b-149">软件方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-149">Software methods and properties</span></span>](software.md) | <span data-ttu-id="1746b-150">运行 API 调用，如 \- 按软件列出漏洞。</span><span class="sxs-lookup"><span data-stu-id="1746b-150">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="1746b-151">用户方法</span><span class="sxs-lookup"><span data-stu-id="1746b-151">User methods</span></span>](user.md) | <span data-ttu-id="1746b-152">运行 API 调用，例如 \- 获取与用户相关的警报和与用户相关的设备。</span><span class="sxs-lookup"><span data-stu-id="1746b-152">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="1746b-153">漏洞方法和属性</span><span class="sxs-lookup"><span data-stu-id="1746b-153">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="1746b-154">按漏洞运行 API 调用 \- ，如列表设备。</span><span class="sxs-lookup"><span data-stu-id="1746b-154">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="1746b-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1746b-155">See also</span></span>

- [<span data-ttu-id="1746b-156">适用于终结点的 Microsoft Defender API</span><span class="sxs-lookup"><span data-stu-id="1746b-156">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="1746b-157">Microsoft Defender for Endpoint API 发行说明</span><span class="sxs-lookup"><span data-stu-id="1746b-157">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
