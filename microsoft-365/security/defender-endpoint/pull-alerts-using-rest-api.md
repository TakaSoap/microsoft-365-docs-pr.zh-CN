---
title: 使用 REST API 拉取 Microsoft Defender 的终结点检测
description: 了解如何调用 Microsoft Defender for Endpoint API 终结点，以使用 SIEM REST API 拉取 JSON 格式的检测。
keywords: 检测， 拉取检测， rest api， 请求， 响应
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 06028f64a3340aeeef52269bc8a1e739d18e6db7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903114"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="aff74-104">使用 SIEM REST API 拉取 Microsoft Defender 的终结点检测</span><span class="sxs-lookup"><span data-stu-id="aff74-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aff74-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="aff74-105">**Applies to:**</span></span>
- [<span data-ttu-id="aff74-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aff74-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aff74-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aff74-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aff74-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="aff74-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aff74-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="aff74-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="aff74-110">[Microsoft Defender for Endpoint Alert](alerts.md) 由一个或多个检测组成。</span><span class="sxs-lookup"><span data-stu-id="aff74-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="aff74-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。</span><span class="sxs-lookup"><span data-stu-id="aff74-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="aff74-112">-Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。</span><span class="sxs-lookup"><span data-stu-id="aff74-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="aff74-113">有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="aff74-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="aff74-114">Microsoft Defender for Endpoint 支持 OAuth 2.0 协议从 API 拉取检测。</span><span class="sxs-lookup"><span data-stu-id="aff74-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="aff74-115">通常，OAuth 2.0 协议支持四种类型的流：</span><span class="sxs-lookup"><span data-stu-id="aff74-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="aff74-116">授权流</span><span class="sxs-lookup"><span data-stu-id="aff74-116">Authorization grant flow</span></span>
- <span data-ttu-id="aff74-117">隐式流</span><span class="sxs-lookup"><span data-stu-id="aff74-117">Implicit flow</span></span>
- <span data-ttu-id="aff74-118">客户端凭据流</span><span class="sxs-lookup"><span data-stu-id="aff74-118">Client credentials flow</span></span>
- <span data-ttu-id="aff74-119">资源所有者流</span><span class="sxs-lookup"><span data-stu-id="aff74-119">Resource owner flow</span></span>

<span data-ttu-id="aff74-120">有关 OAuth 规范详细信息，请参阅 [OAuth 网站](http://www.oauth.net)。</span><span class="sxs-lookup"><span data-stu-id="aff74-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="aff74-121">Microsoft Defender for Endpoint 支持 _授权_ 授予流和客户端凭据流来获取拉取检测的访问权限，Azure Active Directory (AAD) 授权服务器。 </span><span class="sxs-lookup"><span data-stu-id="aff74-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="aff74-122">授权 _授予流_ 使用用户凭据获取授权代码，然后使用授权代码获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="aff74-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="aff74-123">客户端 _凭据流_ 使用客户端凭据针对 Microsoft Defender for Endpoint 终结点 URL 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="aff74-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="aff74-124">此流适用于 OAuth 客户端创建对不需要用户凭据的 API 的请求的情况。</span><span class="sxs-lookup"><span data-stu-id="aff74-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="aff74-125">使用 Microsoft Defender for Endpoint API 中的以下方法拉取 JSON 格式的检测。</span><span class="sxs-lookup"><span data-stu-id="aff74-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="aff74-126">Microsoft Defender 安全中心将类似的警报检测合并到单个警报中。</span><span class="sxs-lookup"><span data-stu-id="aff74-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="aff74-127">此 API 基于您设置的查询参数，以原始形式拉取警报检测，从而使您可以应用自己的分组和筛选。</span><span class="sxs-lookup"><span data-stu-id="aff74-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="aff74-128">开始之前</span><span class="sxs-lookup"><span data-stu-id="aff74-128">Before you begin</span></span>
- <span data-ttu-id="aff74-129">在调用 Microsoft Defender for Endpoint 终结点以拉取检测之前，你需要在 AAD Azure Active Directory (启用 SIEM) 。</span><span class="sxs-lookup"><span data-stu-id="aff74-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="aff74-130">有关详细信息，请参阅在 [Microsoft Defender for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="aff74-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="aff74-p106">请记下 Azure 应用程序注册过程中的下列值。需要使用这些值在服务或守护程序应用中配置 OAuth 流：</span><span class="sxs-lookup"><span data-stu-id="aff74-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="aff74-133">应用程序 ID（应用程序专用）</span><span class="sxs-lookup"><span data-stu-id="aff74-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="aff74-134">应用密钥或机密（应用程序专用）</span><span class="sxs-lookup"><span data-stu-id="aff74-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="aff74-135">应用 OAuth 2.0 令牌终结点</span><span class="sxs-lookup"><span data-stu-id="aff74-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="aff74-p107">在应用页面中，单击 Azure 管理门户底部的“**查看终结点**”，找到此值。终结点看起来像 `https://login.microsoftonline.com/{tenantId}/oauth2/token`。</span><span class="sxs-lookup"><span data-stu-id="aff74-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="aff74-138">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="aff74-138">Get an access token</span></span>
<span data-ttu-id="aff74-139">在创建对 终结点的调用之前，需要获取访问令牌。</span><span class="sxs-lookup"><span data-stu-id="aff74-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="aff74-140">你将使用访问令牌访问受保护的资源，这是 Microsoft Defender for Endpoint 中的检测。</span><span class="sxs-lookup"><span data-stu-id="aff74-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="aff74-141">若要获取访问令牌，您需要对令牌颁发终结点执行 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="aff74-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="aff74-142">下面是一个示例请求：</span><span class="sxs-lookup"><span data-stu-id="aff74-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="aff74-143">响应将包含访问令牌和过期信息。</span><span class="sxs-lookup"><span data-stu-id="aff74-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="aff74-144">你现在可以在对 Defender for Endpoint API 的请求 *access_token* 字段的值。</span><span class="sxs-lookup"><span data-stu-id="aff74-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="aff74-145">请求</span><span class="sxs-lookup"><span data-stu-id="aff74-145">Request</span></span>
<span data-ttu-id="aff74-146">借助访问令牌，你的应用可以向 Microsoft Defender for Endpoint API 提出经过身份验证的请求。</span><span class="sxs-lookup"><span data-stu-id="aff74-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="aff74-147">您的应用必须将访问令牌附加到各个请求的授权头中。</span><span class="sxs-lookup"><span data-stu-id="aff74-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="aff74-148">请求语法</span><span class="sxs-lookup"><span data-stu-id="aff74-148">Request syntax</span></span>
<span data-ttu-id="aff74-149">方法</span><span class="sxs-lookup"><span data-stu-id="aff74-149">Method</span></span> | <span data-ttu-id="aff74-150">请求 URI</span><span class="sxs-lookup"><span data-stu-id="aff74-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="aff74-151">GET</span><span class="sxs-lookup"><span data-stu-id="aff74-151">GET</span></span>| <span data-ttu-id="aff74-152">使用适用于你地区的 URI。</span><span class="sxs-lookup"><span data-stu-id="aff74-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="aff74-153">**对于欧盟**： `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="aff74-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="aff74-154">**对于美国**： `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="aff74-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="aff74-155">**对于英国**： `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="aff74-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="aff74-156">请求标头</span><span class="sxs-lookup"><span data-stu-id="aff74-156">Request header</span></span>
<span data-ttu-id="aff74-157">标头</span><span class="sxs-lookup"><span data-stu-id="aff74-157">Header</span></span> | <span data-ttu-id="aff74-158">类型</span><span class="sxs-lookup"><span data-stu-id="aff74-158">Type</span></span> | <span data-ttu-id="aff74-159">说明</span><span class="sxs-lookup"><span data-stu-id="aff74-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="aff74-160">Authorization</span><span class="sxs-lookup"><span data-stu-id="aff74-160">Authorization</span></span> | <span data-ttu-id="aff74-161">string</span><span class="sxs-lookup"><span data-stu-id="aff74-161">string</span></span> | <span data-ttu-id="aff74-162">必填。</span><span class="sxs-lookup"><span data-stu-id="aff74-162">Required.</span></span> <span data-ttu-id="aff74-163">Azure AD 访问令牌，格式为 **Bearer** &lt; *token* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="aff74-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="aff74-164">请求参数</span><span class="sxs-lookup"><span data-stu-id="aff74-164">Request parameters</span></span>

<span data-ttu-id="aff74-165">使用可选的查询参数指定和控制响应中返回的数据量。</span><span class="sxs-lookup"><span data-stu-id="aff74-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="aff74-166">如果调用此方法时不带参数，响应将包含组织中过去 2 小时内的所有警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="aff74-167">名称</span><span class="sxs-lookup"><span data-stu-id="aff74-167">Name</span></span> | <span data-ttu-id="aff74-168">值</span><span class="sxs-lookup"><span data-stu-id="aff74-168">Value</span></span>| <span data-ttu-id="aff74-169">说明</span><span class="sxs-lookup"><span data-stu-id="aff74-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="aff74-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="aff74-170">sinceTimeUtc</span></span> | <span data-ttu-id="aff74-171">日期时间</span><span class="sxs-lookup"><span data-stu-id="aff74-171">DateTime</span></span> | <span data-ttu-id="aff74-172">根据字段定义从中检索下限的警报：</span><span class="sxs-lookup"><span data-stu-id="aff74-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="aff74-173">该时间范围将为：从 sinceTimeUtc 时间到当前时间。</span><span class="sxs-lookup"><span data-stu-id="aff74-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="aff74-174">**注意**：如果未指定，将检索过去两小时内生成的所有警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="aff74-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="aff74-175">untilTimeUtc</span></span> | <span data-ttu-id="aff74-176">日期时间</span><span class="sxs-lookup"><span data-stu-id="aff74-176">DateTime</span></span> | <span data-ttu-id="aff74-177">定义检索的上限警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="aff74-178">该时间范围将为： `sinceTimeUtc` 从一次一 `untilTimeUtc` 次到一次。</span><span class="sxs-lookup"><span data-stu-id="aff74-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="aff74-179">**注意**：如果未指定，默认值将为当前时间。</span><span class="sxs-lookup"><span data-stu-id="aff74-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="aff74-180">ago</span><span class="sxs-lookup"><span data-stu-id="aff74-180">ago</span></span> | <span data-ttu-id="aff74-181">string</span><span class="sxs-lookup"><span data-stu-id="aff74-181">string</span></span> | <span data-ttu-id="aff74-182">在下列时间范围内拉取警报： `(current_time - ago)` 时而 `current_time` 时。</span><span class="sxs-lookup"><span data-stu-id="aff74-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="aff74-183">值应按照 ISO **8601 持续时间格式** 进行设置</span><span class="sxs-lookup"><span data-stu-id="aff74-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="aff74-184">示例： `ago=PT10M` 将拉取过去 10 分钟内收到的警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="aff74-185">limit</span><span class="sxs-lookup"><span data-stu-id="aff74-185">limit</span></span> | <span data-ttu-id="aff74-186">int</span><span class="sxs-lookup"><span data-stu-id="aff74-186">int</span></span> | <span data-ttu-id="aff74-187">定义要检索的警报数。</span><span class="sxs-lookup"><span data-stu-id="aff74-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="aff74-188">将基于定义的号码检索最新警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="aff74-189">**注意**：如果未指定，将检索该时间范围内可用的所有警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="aff74-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="aff74-190">machinegroups</span></span> | <span data-ttu-id="aff74-191">string</span><span class="sxs-lookup"><span data-stu-id="aff74-191">string</span></span> | <span data-ttu-id="aff74-192">指定要拉取警报的设备组。</span><span class="sxs-lookup"><span data-stu-id="aff74-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="aff74-193">**注意**：如果未指定，将检索来自所有设备组的警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="aff74-194">示例：</span><span class="sxs-lookup"><span data-stu-id="aff74-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="aff74-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="aff74-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="aff74-196">string</span><span class="sxs-lookup"><span data-stu-id="aff74-196">string</span></span> | <span data-ttu-id="aff74-197">注册表中的单个设备标记。</span><span class="sxs-lookup"><span data-stu-id="aff74-197">Single device tag from the registry.</span></span>
<span data-ttu-id="aff74-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="aff74-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="aff74-199">string</span><span class="sxs-lookup"><span data-stu-id="aff74-199">string</span></span> | <span data-ttu-id="aff74-200">在活动中创建的设备Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="aff74-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="aff74-201">请求示例</span><span class="sxs-lookup"><span data-stu-id="aff74-201">Request example</span></span>
<span data-ttu-id="aff74-202">以下示例演示如何检索组织的所有检测。</span><span class="sxs-lookup"><span data-stu-id="aff74-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="aff74-203">以下示例演示了自 2016-09-12 00：00：00 以来获取最近 20 个检测的请求。</span><span class="sxs-lookup"><span data-stu-id="aff74-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="aff74-204">响应</span><span class="sxs-lookup"><span data-stu-id="aff74-204">Response</span></span>
<span data-ttu-id="aff74-205">返回值是 JSON 格式的警报对象的数组。</span><span class="sxs-lookup"><span data-stu-id="aff74-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="aff74-206">下面是一个返回值的示例：</span><span class="sxs-lookup"><span data-stu-id="aff74-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="aff74-207">代码示例</span><span class="sxs-lookup"><span data-stu-id="aff74-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="aff74-208">获取访问令牌</span><span class="sxs-lookup"><span data-stu-id="aff74-208">Get access token</span></span>
<span data-ttu-id="aff74-209">以下代码示例演示如何获取用于调用适用于 Endpoint SIEM API 的 Microsoft Defender 的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="aff74-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="aff74-210">使用令牌连接到检测终结点</span><span class="sxs-lookup"><span data-stu-id="aff74-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="aff74-211">以下代码示例演示如何使用访问令牌调用 Defender for Endpoint SIEM API 获取警报。</span><span class="sxs-lookup"><span data-stu-id="aff74-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="aff74-212">错误代码</span><span class="sxs-lookup"><span data-stu-id="aff74-212">Error codes</span></span>
<span data-ttu-id="aff74-213">Microsoft Defender for Endpoint REST API 返回由无效请求导致的以下错误代码。</span><span class="sxs-lookup"><span data-stu-id="aff74-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="aff74-214">HTTP 错误代码</span><span class="sxs-lookup"><span data-stu-id="aff74-214">HTTP error code</span></span> | <span data-ttu-id="aff74-215">说明</span><span class="sxs-lookup"><span data-stu-id="aff74-215">Description</span></span>
:---|:---
<span data-ttu-id="aff74-216">401</span><span class="sxs-lookup"><span data-stu-id="aff74-216">401</span></span> | <span data-ttu-id="aff74-217">请求格式不正确或令牌无效。</span><span class="sxs-lookup"><span data-stu-id="aff74-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="aff74-218">403</span><span class="sxs-lookup"><span data-stu-id="aff74-218">403</span></span> | <span data-ttu-id="aff74-219">未经授权异常 - 任何域不由租户管理员管理或租户状态被删除。</span><span class="sxs-lookup"><span data-stu-id="aff74-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="aff74-220">500</span><span class="sxs-lookup"><span data-stu-id="aff74-220">500</span></span> | <span data-ttu-id="aff74-221">服务出错。</span><span class="sxs-lookup"><span data-stu-id="aff74-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aff74-222">相关主题</span><span class="sxs-lookup"><span data-stu-id="aff74-222">Related topics</span></span>
- [<span data-ttu-id="aff74-223">在 Microsoft Defender for Endpoint 中启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="aff74-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="aff74-224">配置 ArcSight 以拉取适用于终结点检测的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aff74-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="aff74-225">将检测拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="aff74-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="aff74-226">适用于终结点检测字段的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aff74-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="aff74-227">SIEM 工具集成问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="aff74-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
