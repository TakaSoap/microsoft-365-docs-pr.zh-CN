---
title: 提交或更新指示器 API
description: 了解如何使用提交或更新指示器 API 在 Microsoft Defender for Endpoint 中提交或更新新的指示器实体。
keywords: api， 图形 api， 受支持的 api， 提交， ti， 指示器， 更新
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
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187068"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="95a08-104">提交或更新指示器 API</span><span class="sxs-lookup"><span data-stu-id="95a08-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95a08-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="95a08-105">**Applies to:**</span></span>
- [<span data-ttu-id="95a08-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95a08-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95a08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95a08-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95a08-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="95a08-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="95a08-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="95a08-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="95a08-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="95a08-110">API description</span></span>
<span data-ttu-id="95a08-111">提交或更新新的 [指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="95a08-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="95a08-112">不支持 IP 的 CIDR 表示法。</span><span class="sxs-lookup"><span data-stu-id="95a08-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="95a08-113">限制</span><span class="sxs-lookup"><span data-stu-id="95a08-113">Limitations</span></span>
1. <span data-ttu-id="95a08-114">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="95a08-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="95a08-115">每个租户 15，000 个活动指示器的限制。</span><span class="sxs-lookup"><span data-stu-id="95a08-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="95a08-116">权限</span><span class="sxs-lookup"><span data-stu-id="95a08-116">Permissions</span></span>
<span data-ttu-id="95a08-117">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="95a08-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="95a08-118">若要了解更多信息（包括如何选择权限），请参阅 [入门](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="95a08-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="95a08-119">权限类型</span><span class="sxs-lookup"><span data-stu-id="95a08-119">Permission type</span></span> |   <span data-ttu-id="95a08-120">权限</span><span class="sxs-lookup"><span data-stu-id="95a08-120">Permission</span></span>  |   <span data-ttu-id="95a08-121">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="95a08-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="95a08-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="95a08-122">Application</span></span> |   <span data-ttu-id="95a08-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="95a08-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="95a08-124">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="95a08-124">'Read and write Indicators'</span></span>
<span data-ttu-id="95a08-125">应用程序</span><span class="sxs-lookup"><span data-stu-id="95a08-125">Application</span></span> |   <span data-ttu-id="95a08-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="95a08-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="95a08-127">"读取和写入所有指示器"</span><span class="sxs-lookup"><span data-stu-id="95a08-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="95a08-128">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="95a08-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="95a08-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="95a08-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="95a08-130">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="95a08-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="95a08-131">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="95a08-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="95a08-132">请求标头</span><span class="sxs-lookup"><span data-stu-id="95a08-132">Request headers</span></span>

<span data-ttu-id="95a08-133">名称</span><span class="sxs-lookup"><span data-stu-id="95a08-133">Name</span></span> | <span data-ttu-id="95a08-134">类型</span><span class="sxs-lookup"><span data-stu-id="95a08-134">Type</span></span> | <span data-ttu-id="95a08-135">说明</span><span class="sxs-lookup"><span data-stu-id="95a08-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="95a08-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="95a08-136">Authorization</span></span> | <span data-ttu-id="95a08-137">String</span><span class="sxs-lookup"><span data-stu-id="95a08-137">String</span></span> | <span data-ttu-id="95a08-138">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="95a08-138">Bearer {token}.</span></span> <span data-ttu-id="95a08-139">**必需**。</span><span class="sxs-lookup"><span data-stu-id="95a08-139">**Required**.</span></span>
<span data-ttu-id="95a08-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="95a08-140">Content-Type</span></span> | <span data-ttu-id="95a08-141">string</span><span class="sxs-lookup"><span data-stu-id="95a08-141">string</span></span> | <span data-ttu-id="95a08-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="95a08-142">application/json.</span></span> <span data-ttu-id="95a08-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="95a08-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="95a08-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="95a08-144">Request body</span></span>
<span data-ttu-id="95a08-145">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="95a08-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="95a08-146">参数</span><span class="sxs-lookup"><span data-stu-id="95a08-146">Parameter</span></span> | <span data-ttu-id="95a08-147">类型</span><span class="sxs-lookup"><span data-stu-id="95a08-147">Type</span></span>    | <span data-ttu-id="95a08-148">说明</span><span class="sxs-lookup"><span data-stu-id="95a08-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="95a08-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="95a08-149">indicatorValue</span></span> | <span data-ttu-id="95a08-150">String</span><span class="sxs-lookup"><span data-stu-id="95a08-150">String</span></span> | <span data-ttu-id="95a08-151">Indicator [实体的](ti-indicator.md) 标识。</span><span class="sxs-lookup"><span data-stu-id="95a08-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="95a08-152">**必需**</span><span class="sxs-lookup"><span data-stu-id="95a08-152">**Required**</span></span>
<span data-ttu-id="95a08-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="95a08-153">indicatorType</span></span> | <span data-ttu-id="95a08-154">枚举</span><span class="sxs-lookup"><span data-stu-id="95a08-154">Enum</span></span> | <span data-ttu-id="95a08-155">指示器的类型。</span><span class="sxs-lookup"><span data-stu-id="95a08-155">Type of the indicator.</span></span> <span data-ttu-id="95a08-156">可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。</span><span class="sxs-lookup"><span data-stu-id="95a08-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="95a08-157">**必需**</span><span class="sxs-lookup"><span data-stu-id="95a08-157">**Required**</span></span>
<span data-ttu-id="95a08-158">action</span><span class="sxs-lookup"><span data-stu-id="95a08-158">action</span></span> | <span data-ttu-id="95a08-159">枚举</span><span class="sxs-lookup"><span data-stu-id="95a08-159">Enum</span></span> | <span data-ttu-id="95a08-160">如果在组织中发现指示器，将采取的操作。</span><span class="sxs-lookup"><span data-stu-id="95a08-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="95a08-161">可能的值是："Alert"、"AlertAndBlock"和"Allowed"。</span><span class="sxs-lookup"><span data-stu-id="95a08-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="95a08-162">**必需**</span><span class="sxs-lookup"><span data-stu-id="95a08-162">**Required**</span></span>
<span data-ttu-id="95a08-163">应用程序</span><span class="sxs-lookup"><span data-stu-id="95a08-163">application</span></span> | <span data-ttu-id="95a08-164">String</span><span class="sxs-lookup"><span data-stu-id="95a08-164">String</span></span> | <span data-ttu-id="95a08-165">与指示器关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="95a08-165">The application associated with the indicator.</span></span> <span data-ttu-id="95a08-166">**可选**</span><span class="sxs-lookup"><span data-stu-id="95a08-166">**Optional**</span></span>
<span data-ttu-id="95a08-167">title</span><span class="sxs-lookup"><span data-stu-id="95a08-167">title</span></span> | <span data-ttu-id="95a08-168">String</span><span class="sxs-lookup"><span data-stu-id="95a08-168">String</span></span> | <span data-ttu-id="95a08-169">指示器警报标题。</span><span class="sxs-lookup"><span data-stu-id="95a08-169">Indicator alert title.</span></span> <span data-ttu-id="95a08-170">**必需**</span><span class="sxs-lookup"><span data-stu-id="95a08-170">**Required**</span></span>
<span data-ttu-id="95a08-171">说明</span><span class="sxs-lookup"><span data-stu-id="95a08-171">description</span></span> | <span data-ttu-id="95a08-172">String</span><span class="sxs-lookup"><span data-stu-id="95a08-172">String</span></span> | <span data-ttu-id="95a08-173">指示器的说明。</span><span class="sxs-lookup"><span data-stu-id="95a08-173">Description of the indicator.</span></span> <span data-ttu-id="95a08-174">**必需**</span><span class="sxs-lookup"><span data-stu-id="95a08-174">**Required**</span></span>
<span data-ttu-id="95a08-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="95a08-175">expirationTime</span></span> | <span data-ttu-id="95a08-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="95a08-176">DateTimeOffset</span></span> | <span data-ttu-id="95a08-177">指示器的过期时间。</span><span class="sxs-lookup"><span data-stu-id="95a08-177">The expiration time of the indicator.</span></span> <span data-ttu-id="95a08-178">**可选**</span><span class="sxs-lookup"><span data-stu-id="95a08-178">**Optional**</span></span>
<span data-ttu-id="95a08-179">severity</span><span class="sxs-lookup"><span data-stu-id="95a08-179">severity</span></span> | <span data-ttu-id="95a08-180">枚举</span><span class="sxs-lookup"><span data-stu-id="95a08-180">Enum</span></span> | <span data-ttu-id="95a08-181">指示器的严重性。</span><span class="sxs-lookup"><span data-stu-id="95a08-181">The severity of the indicator.</span></span> <span data-ttu-id="95a08-182">可能的值包括："Informational"、"Low"、"Medium"和"High"。</span><span class="sxs-lookup"><span data-stu-id="95a08-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="95a08-183">**可选**</span><span class="sxs-lookup"><span data-stu-id="95a08-183">**Optional**</span></span>
<span data-ttu-id="95a08-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="95a08-184">recommendedActions</span></span> | <span data-ttu-id="95a08-185">String</span><span class="sxs-lookup"><span data-stu-id="95a08-185">String</span></span> | <span data-ttu-id="95a08-186">TI 指示器警报建议操作。</span><span class="sxs-lookup"><span data-stu-id="95a08-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="95a08-187">**可选**</span><span class="sxs-lookup"><span data-stu-id="95a08-187">**Optional**</span></span>
<span data-ttu-id="95a08-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="95a08-188">rbacGroupNames</span></span> | <span data-ttu-id="95a08-189">String</span><span class="sxs-lookup"><span data-stu-id="95a08-189">String</span></span> | <span data-ttu-id="95a08-190">将应用指示器的 RBAC 组名称的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="95a08-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="95a08-191">**可选**</span><span class="sxs-lookup"><span data-stu-id="95a08-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="95a08-192">响应</span><span class="sxs-lookup"><span data-stu-id="95a08-192">Response</span></span>
- <span data-ttu-id="95a08-193">如果成功，此方法在响应正文中返回 200 - OK 响应代码和已创建/已更新 [的 Indicator](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="95a08-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="95a08-194">如果未成功：此方法返回 400 - 错误请求。</span><span class="sxs-lookup"><span data-stu-id="95a08-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="95a08-195">错误的请求通常指示正文不正确。</span><span class="sxs-lookup"><span data-stu-id="95a08-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="95a08-196">示例</span><span class="sxs-lookup"><span data-stu-id="95a08-196">Example</span></span>

<span data-ttu-id="95a08-197">**请求**</span><span class="sxs-lookup"><span data-stu-id="95a08-197">**Request**</span></span>

<span data-ttu-id="95a08-198">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="95a08-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="95a08-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="95a08-199">Related topic</span></span>
- [<span data-ttu-id="95a08-200">管理指示器</span><span class="sxs-lookup"><span data-stu-id="95a08-200">Manage indicators</span></span>](manage-indicators.md)
