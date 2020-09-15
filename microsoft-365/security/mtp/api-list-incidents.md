---
title: Microsoft 威胁防护中的列表事件 API
description: 了解如何在 Microsoft 威胁防护中列出事件 API
keywords: 列表、事件、事件、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775107"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="b3a1e-104">Microsoft 威胁防护中的列表事件 API</span><span class="sxs-lookup"><span data-stu-id="b3a1e-104">List incidents API in Microsoft Threat Protection</span></span>

<span data-ttu-id="b3a1e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-105">**Applies to:**</span></span>

- <span data-ttu-id="b3a1e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="b3a1e-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3a1e-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b3a1e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b3a1e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="b3a1e-109">API 说明</span><span class="sxs-lookup"><span data-stu-id="b3a1e-109">API description</span></span>

<span data-ttu-id="b3a1e-110">事件 API 允许您对事件进行排序，以确定优先级并创建有通知的 cybersecurity 响应。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="b3a1e-111">它公开在环境保留策略中指定的时间范围内，在网络中的设备、电子邮件帐户和用户中标记的事件的集合。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="b3a1e-112">最近的事件显示在列表的顶部。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="b3a1e-113">每个事件包含一系列相关警报及其相关的实体。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="b3a1e-114">API 支持以下 **OData** 运算符：</span><span class="sxs-lookup"><span data-stu-id="b3a1e-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="b3a1e-115">```$filter``` 打开： ```lastUpdateTime``` 、 ```createdTime``` ```status``` 和 ```assignedTo``` 属性。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="b3a1e-116">```$top``` 最大值为 **100**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="b3a1e-117">限制</span><span class="sxs-lookup"><span data-stu-id="b3a1e-117">Limitations</span></span>

1. <span data-ttu-id="b3a1e-118">页面大小的最大值为 **100 个事件**。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="b3a1e-119">请求的最大速率为 **每分钟50个呼叫** 和 **每小时的1500个呼叫**。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="b3a1e-120">权限</span><span class="sxs-lookup"><span data-stu-id="b3a1e-120">Permissions</span></span>

<span data-ttu-id="b3a1e-121">若要调用此 API，必须有以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b3a1e-122">若要了解详细信息，包括如何选择权限，请参阅 [Access Microsoft 威胁 Protection api](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="b3a1e-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="b3a1e-123">权限类型</span><span class="sxs-lookup"><span data-stu-id="b3a1e-123">Permission type</span></span> |   <span data-ttu-id="b3a1e-124">权限</span><span class="sxs-lookup"><span data-stu-id="b3a1e-124">Permission</span></span>  |   <span data-ttu-id="b3a1e-125">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="b3a1e-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b3a1e-126">应用程序</span><span class="sxs-lookup"><span data-stu-id="b3a1e-126">Application</span></span> |   <span data-ttu-id="b3a1e-127">事件：全部已读。所有</span><span class="sxs-lookup"><span data-stu-id="b3a1e-127">Incident.Read.All</span></span> | <span data-ttu-id="b3a1e-128">"读取所有事件"</span><span class="sxs-lookup"><span data-stu-id="b3a1e-128">'Read all incidents'</span></span>
<span data-ttu-id="b3a1e-129">应用程序</span><span class="sxs-lookup"><span data-stu-id="b3a1e-129">Application</span></span> |   <span data-ttu-id="b3a1e-130">事件 ReadWrite。 All</span><span class="sxs-lookup"><span data-stu-id="b3a1e-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="b3a1e-131">' 读取和写入所有事件 '</span><span class="sxs-lookup"><span data-stu-id="b3a1e-131">'Read and write all incidents'</span></span>
<span data-ttu-id="b3a1e-132">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b3a1e-132">Delegated (work or school account)</span></span> | <span data-ttu-id="b3a1e-133">事件。阅读</span><span class="sxs-lookup"><span data-stu-id="b3a1e-133">Incident.Read</span></span> | <span data-ttu-id="b3a1e-134">"读取事件"</span><span class="sxs-lookup"><span data-stu-id="b3a1e-134">'Read incidents'</span></span>
<span data-ttu-id="b3a1e-135">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="b3a1e-135">Delegated (work or school account)</span></span> | <span data-ttu-id="b3a1e-136">事件读写</span><span class="sxs-lookup"><span data-stu-id="b3a1e-136">Incident.ReadWrite</span></span> | <span data-ttu-id="b3a1e-137">"读取和写入事件"</span><span class="sxs-lookup"><span data-stu-id="b3a1e-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="b3a1e-138">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="b3a1e-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="b3a1e-139">用户需要具有门户中的事件的 "查看" 权限。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="b3a1e-140">响应将仅包括用户向其公开的事件。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="b3a1e-141">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="b3a1e-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="b3a1e-142">请求标头</span><span class="sxs-lookup"><span data-stu-id="b3a1e-142">Request headers</span></span>

<span data-ttu-id="b3a1e-143">名称</span><span class="sxs-lookup"><span data-stu-id="b3a1e-143">Name</span></span> | <span data-ttu-id="b3a1e-144">类型</span><span class="sxs-lookup"><span data-stu-id="b3a1e-144">Type</span></span> | <span data-ttu-id="b3a1e-145">说明</span><span class="sxs-lookup"><span data-stu-id="b3a1e-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="b3a1e-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="b3a1e-146">Authorization</span></span> | <span data-ttu-id="b3a1e-147">String</span><span class="sxs-lookup"><span data-stu-id="b3a1e-147">String</span></span> | <span data-ttu-id="b3a1e-148">持有者 {令牌}。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-148">Bearer {token}.</span></span> <span data-ttu-id="b3a1e-149">\*\*\*\* 必需。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b3a1e-150">请求正文</span><span class="sxs-lookup"><span data-stu-id="b3a1e-150">Request body</span></span>
<span data-ttu-id="b3a1e-151">无。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="b3a1e-152">响应</span><span class="sxs-lookup"><span data-stu-id="b3a1e-152">Response</span></span>
<span data-ttu-id="b3a1e-153">如果成功，此方法将返回 200 OK，以及响应正文中的 [事件](api-incident.md) 列表。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="b3a1e-154">架构映射</span><span class="sxs-lookup"><span data-stu-id="b3a1e-154">Schema mapping</span></span>

| <span data-ttu-id="b3a1e-155">字段名</span><span class="sxs-lookup"><span data-stu-id="b3a1e-155">Field name</span></span>                                | <span data-ttu-id="b3a1e-156">说明</span><span class="sxs-lookup"><span data-stu-id="b3a1e-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-157">示例值</span><span class="sxs-lookup"><span data-stu-id="b3a1e-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="b3a1e-158">**事件元数据**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="b3a1e-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-159">incidentId</span></span>                                | <span data-ttu-id="b3a1e-160">代表事件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-161">924565</span><span class="sxs-lookup"><span data-stu-id="b3a1e-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-162">redirectIncidentId</span></span>                        | <span data-ttu-id="b3a1e-163">仅在事件处理逻辑过程中，将事件与另一个事件组合在一起时才填充。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="b3a1e-164">924569</span><span class="sxs-lookup"><span data-stu-id="b3a1e-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-165">incidentName</span></span>                              | <span data-ttu-id="b3a1e-166">可用于每个事件的字符串值。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="b3a1e-167">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="b3a1e-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="b3a1e-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-168">createdTime</span></span>                               | <span data-ttu-id="b3a1e-169">首次创建事件的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="b3a1e-170">2020-06T14：46： 57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-171">lastUpdateTime</span></span>                            | <span data-ttu-id="b3a1e-172">后端事件最后更新的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="b3a1e-173">在为事件的检索时间范围设置 request 参数时，可以使用此字段。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="b3a1e-174">2020-06T14：46： 57.29 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="b3a1e-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b3a1e-175">assignedTo</span></span>                                | <span data-ttu-id="b3a1e-176">事件的所有者或 *null* （如果未分配所有者）。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="b3a1e-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3a1e-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="b3a1e-178">classification</span><span class="sxs-lookup"><span data-stu-id="b3a1e-178">classification</span></span>                            | <span data-ttu-id="b3a1e-179">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-179">The specification for the incident.</span></span> <span data-ttu-id="b3a1e-180">属性值为： *Unknown*、 *FalsePositive*、 *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="b3a1e-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="b3a1e-181">未知</span><span class="sxs-lookup"><span data-stu-id="b3a1e-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="b3a1e-182">可用性</span><span class="sxs-lookup"><span data-stu-id="b3a1e-182">determination</span></span>                             | <span data-ttu-id="b3a1e-183">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="b3a1e-184">属性值为： *NotAvailable*、 *Apt.*、 *恶意软件*、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *其他*</span><span class="sxs-lookup"><span data-stu-id="b3a1e-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="b3a1e-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-186">状态</span><span class="sxs-lookup"><span data-stu-id="b3a1e-186">status</span></span>                                    | <span data-ttu-id="b3a1e-187">将事件分类 (为 *活动*或 *已解决*) 。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="b3a1e-188">这可帮助您组织和管理对事件的响应。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="b3a1e-189">活动</span><span class="sxs-lookup"><span data-stu-id="b3a1e-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-190">severity</span><span class="sxs-lookup"><span data-stu-id="b3a1e-190">severity</span></span>                                  | <span data-ttu-id="b3a1e-191">指示可能对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="b3a1e-192">严重度越高，影响越大。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="b3a1e-193">通常情况下，严重级别较高的项目需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="b3a1e-194">以下值之一： *信息*、 *低*、\* 中和 *高*。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="b3a1e-195">中</span><span class="sxs-lookup"><span data-stu-id="b3a1e-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-196">tags</span><span class="sxs-lookup"><span data-stu-id="b3a1e-196">tags</span></span>                                      | <span data-ttu-id="b3a1e-197">与事件相关联的自定义标记的数组，例如，用于标记具有共同特征的一组事件。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-198">警报</span><span class="sxs-lookup"><span data-stu-id="b3a1e-198">alerts</span></span>                                    | <span data-ttu-id="b3a1e-199">与事件相关的所有警报和其他信息（如严重性、警报中涉及的实体）的数组以及警报的来源。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-200">\[\] (查看以下警报字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="b3a1e-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="b3a1e-201">**警报元数据**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="b3a1e-202">alertId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-202">alertId</span></span>                                   | <span data-ttu-id="b3a1e-203">代表警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="b3a1e-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="b3a1e-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="b3a1e-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-205">incidentId</span></span>                                | <span data-ttu-id="b3a1e-206">代表与此通知关联的事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="b3a1e-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="b3a1e-207">924565</span><span class="sxs-lookup"><span data-stu-id="b3a1e-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-208">serviceSource</span><span class="sxs-lookup"><span data-stu-id="b3a1e-208">serviceSource</span></span>                             | <span data-ttu-id="b3a1e-209">通知源于的服务，例如 Microsoft Defender ATP、Microsoft 云应用安全性、Azure ATP 或 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="b3a1e-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="b3a1e-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-211">creationTime</span></span>                              | <span data-ttu-id="b3a1e-212">首次创建警报的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="b3a1e-213">2020-06T14：46： 55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="b3a1e-215">后端最后更新警报的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="b3a1e-216">2020-06T14：46： 57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-217">resolvedTime</span></span>                              | <span data-ttu-id="b3a1e-218">解决警报的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="b3a1e-219">2020-10T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="b3a1e-220">firstActivity</span></span>                             | <span data-ttu-id="b3a1e-221">警报第一次报告后端已更新活动的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="b3a1e-222">2020-04T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-223">title</span><span class="sxs-lookup"><span data-stu-id="b3a1e-223">title</span></span>                                     | <span data-ttu-id="b3a1e-224">可用于每个警报的简短标识字符串值。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-225">勒索软件活动</span><span class="sxs-lookup"><span data-stu-id="b3a1e-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="b3a1e-226">description</span><span class="sxs-lookup"><span data-stu-id="b3a1e-226">description</span></span>                               | <span data-ttu-id="b3a1e-227">描述每个警报的字符串值。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-228">用户测试用户 2 (testUser2@contoso.com) 使用不常见扩展 *herunterladen*的多个扩展名结尾的99文件。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="b3a1e-229">这是一种不寻常的文件操作，并表明存在潜在的勒索软件攻击。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="b3a1e-230">“类别”</span><span class="sxs-lookup"><span data-stu-id="b3a1e-230">category</span></span>                                  | <span data-ttu-id="b3a1e-231">对攻击在终止链中的进展程度的直观和数字视图。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="b3a1e-232">与 [MITRE ATT&CK™ framework](https://attack.mitre.org/)对齐。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="b3a1e-233">影响</span><span class="sxs-lookup"><span data-stu-id="b3a1e-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-234">状态</span><span class="sxs-lookup"><span data-stu-id="b3a1e-234">status</span></span>                                    | <span data-ttu-id="b3a1e-235">将警报 (为 *新*的、 *活动*的或 *已解决* 的) 进行分类。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="b3a1e-236">这可帮助您组织和管理对警报的响应。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="b3a1e-237">新式部署</span><span class="sxs-lookup"><span data-stu-id="b3a1e-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="b3a1e-238">severity</span><span class="sxs-lookup"><span data-stu-id="b3a1e-238">severity</span></span>                                  | <span data-ttu-id="b3a1e-239">指示可能对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="b3a1e-240">严重度越高，影响越大。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="b3a1e-241">通常情况下，严重级别较高的项目需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="b3a1e-242">以下值之一： *信息*、 *低*、\* 中和 *高*。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="b3a1e-243">中</span><span class="sxs-lookup"><span data-stu-id="b3a1e-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-244">investigationId</span></span>                           | <span data-ttu-id="b3a1e-245">此警报触发的自动调查 id。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-246">1234</span><span class="sxs-lookup"><span data-stu-id="b3a1e-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="b3a1e-247">investigationState</span></span>                        | <span data-ttu-id="b3a1e-248">有关调查的当前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-248">Information on the investigation's current status.</span></span> <span data-ttu-id="b3a1e-249">下列项之一：*未知*、已*终止*、 *SuccessfullyRemediated*、*良性*、*失败*、 *PartiallyRemediated*、*正在运行*、 *PendingApproval*、 *PendingResource*、PartiallyInvestigated *、TerminatedByUser、TerminatedBySystem* *、\*\*排队*、InnerFailure *、PreexistingAlert、UnsupportedOs* *、UnsupportedAlertType* *、SuppressedAlert* *、、*、、。 *PartiallyInvestigated* *InnerFailure*</span><span class="sxs-lookup"><span data-stu-id="b3a1e-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="b3a1e-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="b3a1e-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-251">classification</span><span class="sxs-lookup"><span data-stu-id="b3a1e-251">classification</span></span>                            | <span data-ttu-id="b3a1e-252">事件的规范。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-252">The specification for the incident.</span></span> <span data-ttu-id="b3a1e-253">属性值为： *Unknown*、 *FalsePositive*、 *TruePositive* 或 *null*</span><span class="sxs-lookup"><span data-stu-id="b3a1e-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="b3a1e-254">未知</span><span class="sxs-lookup"><span data-stu-id="b3a1e-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="b3a1e-255">可用性</span><span class="sxs-lookup"><span data-stu-id="b3a1e-255">determination</span></span>                             | <span data-ttu-id="b3a1e-256">指定事件的确定。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="b3a1e-257">属性值为： *NotAvailable*、 *Apt.*、 *恶意软件*、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *Other* 或  *null*</span><span class="sxs-lookup"><span data-stu-id="b3a1e-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-258">Apt.</span><span class="sxs-lookup"><span data-stu-id="b3a1e-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="b3a1e-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="b3a1e-259">assignedTo</span></span>                                | <span data-ttu-id="b3a1e-260">事件的所有者或 *null* （如果未分配所有者）。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="b3a1e-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3a1e-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="b3a1e-262">actorName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-262">actorName</span></span>                                 | <span data-ttu-id="b3a1e-263">与此通知关联的活动组（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-264">BORON</span><span class="sxs-lookup"><span data-stu-id="b3a1e-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="b3a1e-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-265">threatFamilyName</span></span>                          | <span data-ttu-id="b3a1e-266">与此警报关联的威胁系列。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="b3a1e-267">空</span><span class="sxs-lookup"><span data-stu-id="b3a1e-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="b3a1e-268">mitreTechniques</span></span>                           | <span data-ttu-id="b3a1e-269">与 [MITRE ATT&CK](https://attack.mitre.org/)™框架相一致的攻击技术。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-270">驱动器</span><span class="sxs-lookup"><span data-stu-id="b3a1e-270">devices</span></span>                                   | <span data-ttu-id="b3a1e-271">发送与事件相关的警报的所有设备。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-272">\[\] (查看以下实体字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="b3a1e-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="b3a1e-273">**设备格式**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="b3a1e-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-274">DeviceId</span></span>                                  | <span data-ttu-id="b3a1e-275">在 Microsoft Defender ATP 中指定的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="b3a1e-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="b3a1e-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="b3a1e-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-277">aadDeviceId</span></span>                               |  <span data-ttu-id="b3a1e-278">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) 中指定的设备 Id。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="b3a1e-279">仅适用于加入域的设备。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="b3a1e-280">空</span><span class="sxs-lookup"><span data-stu-id="b3a1e-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-281">deviceDnsName</span></span>                             | <span data-ttu-id="b3a1e-282">设备的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3a1e-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="b3a1e-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="b3a1e-284">osPlatform</span></span>                                | <span data-ttu-id="b3a1e-285">设备正在运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="b3a1e-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="b3a1e-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="b3a1e-287">osBuild</span></span>                                   | <span data-ttu-id="b3a1e-288">设备正在运行的操作系统的内部版本。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-289">14393</span><span class="sxs-lookup"><span data-stu-id="b3a1e-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="b3a1e-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-290">rbacGroupName</span></span>                             | <span data-ttu-id="b3a1e-291">[基于角色的访问控制](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) 组与设备相关联。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="b3a1e-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="b3a1e-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="b3a1e-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="b3a1e-293">firstSeen</span></span>                                 | <span data-ttu-id="b3a1e-294">首次看到设备时的时间。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="b3a1e-295">2020-02-06T14：16： 01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="b3a1e-296">healthStatus</span></span>                              | <span data-ttu-id="b3a1e-297">设备的运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-298">活动</span><span class="sxs-lookup"><span data-stu-id="b3a1e-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="b3a1e-299">riskScore</span></span>                                 | <span data-ttu-id="b3a1e-300">设备的风险分数。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="b3a1e-301">高</span><span class="sxs-lookup"><span data-stu-id="b3a1e-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-302">实体</span><span class="sxs-lookup"><span data-stu-id="b3a1e-302">entities</span></span>                                  | <span data-ttu-id="b3a1e-303">已标识为给定警报的一部分或与之相关的所有实体。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-304">\[\] (查看以下实体字段的详细信息) </span><span class="sxs-lookup"><span data-stu-id="b3a1e-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="b3a1e-305">**实体格式**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="b3a1e-306">entityType</span><span class="sxs-lookup"><span data-stu-id="b3a1e-306">entityType</span></span>                                | <span data-ttu-id="b3a1e-307">已标识为给定警报的一部分或与之相关的实体。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="b3a1e-308">属性值为： *User*、 *Ip*、 *Url*、 *File*、 *Process*、 *邮箱*、 *MailMessage*、 *MailCluster*、 *Registry*</span><span class="sxs-lookup"><span data-stu-id="b3a1e-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-309">User</span><span class="sxs-lookup"><span data-stu-id="b3a1e-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-310">sha1</span><span class="sxs-lookup"><span data-stu-id="b3a1e-310">sha1</span></span>                                      | <span data-ttu-id="b3a1e-311">如果 entityType 是 *文件*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="b3a1e-312">与文件或进程相关联的警报的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="b3a1e-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="b3a1e-314">sha256</span><span class="sxs-lookup"><span data-stu-id="b3a1e-314">sha256</span></span>                                    | <span data-ttu-id="b3a1e-315">如果 entityType 是 *文件*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="b3a1e-316">与文件或进程相关联的警报的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="b3a1e-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="b3a1e-318">fileName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-318">fileName</span></span>                                  | <span data-ttu-id="b3a1e-319">如果 entityType 是 *文件*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="b3a1e-320">与文件或进程相关联的警报的文件名</span><span class="sxs-lookup"><span data-stu-id="b3a1e-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="b3a1e-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-322">路径</span><span class="sxs-lookup"><span data-stu-id="b3a1e-322">filePath</span></span>                                  | <span data-ttu-id="b3a1e-323">如果 entityType 是 *文件*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="b3a1e-324">与文件或进程相关联的警报的文件路径</span><span class="sxs-lookup"><span data-stu-id="b3a1e-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-325">C： \\ \\ 代理 \\ \\ \_ 工作 \\ \\ \_ 临时 \\ \\ 部署 \_ 系统 2020-09-06 12 \_ 14 \_ 54 \\ \\ 输出</span><span class="sxs-lookup"><span data-stu-id="b3a1e-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="b3a1e-326">processId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-326">processId</span></span>                                 | <span data-ttu-id="b3a1e-327">如果 entityType 为 *进程*，则为可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-328">24348</span><span class="sxs-lookup"><span data-stu-id="b3a1e-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="b3a1e-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="b3a1e-329">processCommandLine</span></span>                        | <span data-ttu-id="b3a1e-330">如果 entityType 为 *进程*，则为可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-331">" \\ " 您的文件已准备好下载 \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="b3a1e-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="b3a1e-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-332">processCreationTime</span></span>                       | <span data-ttu-id="b3a1e-333">如果 entityType 为 *进程*，则为可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-334">2020-18T03：25： 38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-335">parentProcessId</span></span>                           | <span data-ttu-id="b3a1e-336">如果 entityType 为 *进程*，则为可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="b3a1e-337">16840</span><span class="sxs-lookup"><span data-stu-id="b3a1e-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="b3a1e-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="b3a1e-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="b3a1e-339">如果 entityType 为 *进程*，则为可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-340">2020-18T02：12： 32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="b3a1e-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="b3a1e-341">ipAddress</span></span>                                 | <span data-ttu-id="b3a1e-342">如果 entityType 为 *Ip*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="b3a1e-343">与网络事件相关联的警报的 IP 地址，例如 *与恶意网络目标的通信*。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="b3a1e-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="b3a1e-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="b3a1e-345">url</span><span class="sxs-lookup"><span data-stu-id="b3a1e-345">url</span></span>                                       | <span data-ttu-id="b3a1e-346">如果 entityType 为 *Url*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="b3a1e-347">与网络事件相关联的警报的 Url，例如， *与恶意网络目标的通信*。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="b3a1e-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="b3a1e-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="b3a1e-349">帐户</span><span class="sxs-lookup"><span data-stu-id="b3a1e-349">accountName</span></span>                               | <span data-ttu-id="b3a1e-350">如果 entityType 是 *用户*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="b3a1e-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="b3a1e-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="b3a1e-352">domainName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-352">domainName</span></span>                                | <span data-ttu-id="b3a1e-353">如果 entityType 是 *用户*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-354">欧洲公司</span><span class="sxs-lookup"><span data-stu-id="b3a1e-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-355">userSid</span><span class="sxs-lookup"><span data-stu-id="b3a1e-355">userSid</span></span>                                   | <span data-ttu-id="b3a1e-356">如果 entityType 是 *用户*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="b3a1e-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="b3a1e-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-358">aadUserId</span></span>                                 | <span data-ttu-id="b3a1e-359">如果 entityType 是 *用户*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="b3a1e-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="b3a1e-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-361">userPrincipalName</span></span>                         | <span data-ttu-id="b3a1e-362">如果 entityType 是*用户* / *邮箱* / *MailMessage*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3a1e-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="b3a1e-365">如果 entityType 为 *邮箱*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-366">测试的您</span><span class="sxs-lookup"><span data-stu-id="b3a1e-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="b3a1e-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="b3a1e-367">mailboxAddress</span></span>                            | <span data-ttu-id="b3a1e-368">如果 entityType 是*用户* / *邮箱* / *MailMessage*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3a1e-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="b3a1e-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="b3a1e-370">clusterBy</span></span>                                 | <span data-ttu-id="b3a1e-371">如果 entityType 为  *MailCluster*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="b3a1e-372">遵照P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="b3a1e-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="b3a1e-373">sender</span><span class="sxs-lookup"><span data-stu-id="b3a1e-373">sender</span></span>                                    | <span data-ttu-id="b3a1e-374">如果 entityType 是*用户* / *邮箱* / *MailMessage*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="b3a1e-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="b3a1e-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="b3a1e-376">recipient</span><span class="sxs-lookup"><span data-stu-id="b3a1e-376">recipient</span></span>                                 | <span data-ttu-id="b3a1e-377">如果 entityType 为 *MailMessage*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="b3a1e-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b3a1e-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="b3a1e-379">subject</span><span class="sxs-lookup"><span data-stu-id="b3a1e-379">subject</span></span>                                   | <span data-ttu-id="b3a1e-380">如果 entityType 为 *MailMessage*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="b3a1e-381">\[外部 \] 注意事项</span><span class="sxs-lookup"><span data-stu-id="b3a1e-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="b3a1e-382">deliveryAction</span></span>                            | <span data-ttu-id="b3a1e-383">如果 entityType 为 *MailMessage*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="b3a1e-384">附带</span><span class="sxs-lookup"><span data-stu-id="b3a1e-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="b3a1e-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-385">securityGroupId</span></span>                           | <span data-ttu-id="b3a1e-386">如果 entityType 为  *SecurityGroup*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="b3a1e-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="b3a1e-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="b3a1e-388">securityGroupName</span></span>                         | <span data-ttu-id="b3a1e-389">如果 entityType 为  *SecurityGroup*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="b3a1e-390">网络配置操作员</span><span class="sxs-lookup"><span data-stu-id="b3a1e-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="b3a1e-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="b3a1e-391">registryHive</span></span>                              | <span data-ttu-id="b3a1e-392">如果 entityType 为  *注册表*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-393">HKEY \_ 本地 \_ 计算机</span><span class="sxs-lookup"><span data-stu-id="b3a1e-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="b3a1e-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="b3a1e-394">registryKey</span></span>                               | <span data-ttu-id="b3a1e-395">如果 entityType 为  *注册表*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="b3a1e-396">软件 \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="b3a1e-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="b3a1e-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="b3a1e-397">registryValueType</span></span>                         | <span data-ttu-id="b3a1e-398">如果 entityType 为  *注册表*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-399">String</span><span class="sxs-lookup"><span data-stu-id="b3a1e-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="b3a1e-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="b3a1e-400">registryValue</span></span>                             | <span data-ttu-id="b3a1e-401">如果 entityType 为  *注册表*，则可用。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="b3a1e-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="b3a1e-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="b3a1e-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="b3a1e-403">deviceId</span></span>                                  | <span data-ttu-id="b3a1e-404">与实体相关的设备的 ID （如果有）。</span><span class="sxs-lookup"><span data-stu-id="b3a1e-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="b3a1e-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="b3a1e-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="b3a1e-406">示例</span><span class="sxs-lookup"><span data-stu-id="b3a1e-406">Example</span></span>

<span data-ttu-id="b3a1e-407">**请求**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="b3a1e-408">**响应**</span><span class="sxs-lookup"><span data-stu-id="b3a1e-408">**Response**</span></span>
```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="b3a1e-409">相关主题</span><span class="sxs-lookup"><span data-stu-id="b3a1e-409">Related topic</span></span>
- [<span data-ttu-id="b3a1e-410">事件 Api</span><span class="sxs-lookup"><span data-stu-id="b3a1e-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="b3a1e-411">更新事件</span><span class="sxs-lookup"><span data-stu-id="b3a1e-411">Update incident</span></span>](api-update-incidents.md)
