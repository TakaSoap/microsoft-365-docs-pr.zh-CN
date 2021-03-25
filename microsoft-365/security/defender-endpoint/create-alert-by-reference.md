---
title: 从事件 API 创建警报
description: 了解如何使用创建警报 API 在 Microsoft Defender for Endpoint 中的事件顶部创建新的警报。
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
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166443"
---
# <a name="create-alert-api"></a><span data-ttu-id="24cbf-104">创建警报 API</span><span class="sxs-lookup"><span data-stu-id="24cbf-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24cbf-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="24cbf-105">**Applies to:**</span></span>
- [<span data-ttu-id="24cbf-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="24cbf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24cbf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24cbf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="24cbf-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="24cbf-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24cbf-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="24cbf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="24cbf-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="24cbf-110">API description</span></span>
<span data-ttu-id="24cbf-111">在事件 [顶部](alerts.md) 创建新的 **警报**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="24cbf-112">**创建警报需要 Microsoft Defender for Endpoint** 事件。</span><span class="sxs-lookup"><span data-stu-id="24cbf-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="24cbf-113">你将需要提供请求中的事件中的 3 个参数：**事件** 时间、计算机 **ID** 和 **报告 ID。**</span><span class="sxs-lookup"><span data-stu-id="24cbf-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="24cbf-114">请参阅下面的示例。</span><span class="sxs-lookup"><span data-stu-id="24cbf-114">See example below.</span></span>
<br><span data-ttu-id="24cbf-115">可以使用高级搜寻 API 或门户中的事件。</span><span class="sxs-lookup"><span data-stu-id="24cbf-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="24cbf-116">如果同一设备上存在具有相同标题的打开警报，则新创建的警报将合并到该警报中。</span><span class="sxs-lookup"><span data-stu-id="24cbf-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="24cbf-117">自动调查将在通过 API 创建的警报上自动启动。</span><span class="sxs-lookup"><span data-stu-id="24cbf-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="24cbf-118">限制</span><span class="sxs-lookup"><span data-stu-id="24cbf-118">Limitations</span></span>
1. <span data-ttu-id="24cbf-119">此 API 的速率限制是每分钟 15 次调用。</span><span class="sxs-lookup"><span data-stu-id="24cbf-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="24cbf-120">权限</span><span class="sxs-lookup"><span data-stu-id="24cbf-120">Permissions</span></span>

<span data-ttu-id="24cbf-121">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="24cbf-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="24cbf-122">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="24cbf-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="24cbf-123">权限类型</span><span class="sxs-lookup"><span data-stu-id="24cbf-123">Permission type</span></span> |   <span data-ttu-id="24cbf-124">权限</span><span class="sxs-lookup"><span data-stu-id="24cbf-124">Permission</span></span>  |   <span data-ttu-id="24cbf-125">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="24cbf-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="24cbf-126">Application</span><span class="sxs-lookup"><span data-stu-id="24cbf-126">Application</span></span> |   <span data-ttu-id="24cbf-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="24cbf-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="24cbf-128">"读取和写入所有警报"</span><span class="sxs-lookup"><span data-stu-id="24cbf-128">'Read and write all alerts'</span></span>
<span data-ttu-id="24cbf-129">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="24cbf-129">Delegated (work or school account)</span></span> | <span data-ttu-id="24cbf-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="24cbf-130">Alert.ReadWrite</span></span> | <span data-ttu-id="24cbf-131">"读取和写入警报"</span><span class="sxs-lookup"><span data-stu-id="24cbf-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="24cbf-132">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="24cbf-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="24cbf-133">用户至少需要具有以下角色权限："警报调查" (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="24cbf-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="24cbf-134">用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="24cbf-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="24cbf-135">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="24cbf-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="24cbf-136">请求标头</span><span class="sxs-lookup"><span data-stu-id="24cbf-136">Request headers</span></span>

<span data-ttu-id="24cbf-137">名称</span><span class="sxs-lookup"><span data-stu-id="24cbf-137">Name</span></span> | <span data-ttu-id="24cbf-138">类型</span><span class="sxs-lookup"><span data-stu-id="24cbf-138">Type</span></span> | <span data-ttu-id="24cbf-139">说明</span><span class="sxs-lookup"><span data-stu-id="24cbf-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="24cbf-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="24cbf-140">Authorization</span></span> | <span data-ttu-id="24cbf-141">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-141">String</span></span> | <span data-ttu-id="24cbf-142">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="24cbf-142">Bearer {token}.</span></span> <span data-ttu-id="24cbf-143">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-143">**Required**.</span></span>
<span data-ttu-id="24cbf-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="24cbf-144">Content-Type</span></span> | <span data-ttu-id="24cbf-145">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-145">String</span></span> | <span data-ttu-id="24cbf-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="24cbf-146">application/json.</span></span> <span data-ttu-id="24cbf-147">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="24cbf-148">请求正文</span><span class="sxs-lookup"><span data-stu-id="24cbf-148">Request body</span></span>

<span data-ttu-id="24cbf-149">在请求正文中，提供以下值 (所有请求) ：</span><span class="sxs-lookup"><span data-stu-id="24cbf-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="24cbf-150">属性</span><span class="sxs-lookup"><span data-stu-id="24cbf-150">Property</span></span> | <span data-ttu-id="24cbf-151">类型</span><span class="sxs-lookup"><span data-stu-id="24cbf-151">Type</span></span> | <span data-ttu-id="24cbf-152">说明</span><span class="sxs-lookup"><span data-stu-id="24cbf-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="24cbf-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="24cbf-153">eventTime</span></span> | <span data-ttu-id="24cbf-154">DateTime (UTC) </span><span class="sxs-lookup"><span data-stu-id="24cbf-154">DateTime(UTC)</span></span> | <span data-ttu-id="24cbf-155">事件作为字符串的精确时间，从高级搜寻获取。</span><span class="sxs-lookup"><span data-stu-id="24cbf-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="24cbf-156">例如， ```2018-08-03T16:45:21.7115183Z``` **必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="24cbf-157">reportId</span><span class="sxs-lookup"><span data-stu-id="24cbf-157">reportId</span></span> | <span data-ttu-id="24cbf-158">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-158">String</span></span> | <span data-ttu-id="24cbf-159">事件的 reportId，从高级搜寻获取。</span><span class="sxs-lookup"><span data-stu-id="24cbf-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="24cbf-160">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-160">**Required**.</span></span>
<span data-ttu-id="24cbf-161">machineId</span><span class="sxs-lookup"><span data-stu-id="24cbf-161">machineId</span></span> | <span data-ttu-id="24cbf-162">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-162">String</span></span> | <span data-ttu-id="24cbf-163">标识事件的设备 ID。</span><span class="sxs-lookup"><span data-stu-id="24cbf-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="24cbf-164">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-164">**Required**.</span></span>
<span data-ttu-id="24cbf-165">severity</span><span class="sxs-lookup"><span data-stu-id="24cbf-165">severity</span></span> | <span data-ttu-id="24cbf-166">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-166">String</span></span> | <span data-ttu-id="24cbf-167">警报的严重性。</span><span class="sxs-lookup"><span data-stu-id="24cbf-167">Severity of the alert.</span></span> <span data-ttu-id="24cbf-168">属性值为："Low"、Medium 和"High"。</span><span class="sxs-lookup"><span data-stu-id="24cbf-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="24cbf-169">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-169">**Required**.</span></span>
<span data-ttu-id="24cbf-170">title</span><span class="sxs-lookup"><span data-stu-id="24cbf-170">title</span></span> | <span data-ttu-id="24cbf-171">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-171">String</span></span> | <span data-ttu-id="24cbf-172">警报的标题。</span><span class="sxs-lookup"><span data-stu-id="24cbf-172">Title for the alert.</span></span> <span data-ttu-id="24cbf-173">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-173">**Required**.</span></span>
<span data-ttu-id="24cbf-174">说明</span><span class="sxs-lookup"><span data-stu-id="24cbf-174">description</span></span> | <span data-ttu-id="24cbf-175">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-175">String</span></span> | <span data-ttu-id="24cbf-176">警报的说明。</span><span class="sxs-lookup"><span data-stu-id="24cbf-176">Description of the alert.</span></span> <span data-ttu-id="24cbf-177">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-177">**Required**.</span></span>
<span data-ttu-id="24cbf-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="24cbf-178">recommendedAction</span></span>| <span data-ttu-id="24cbf-179">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-179">String</span></span> | <span data-ttu-id="24cbf-180">建议安全人员在分析警报时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="24cbf-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="24cbf-181">**必需**。</span><span class="sxs-lookup"><span data-stu-id="24cbf-181">**Required**.</span></span>
<span data-ttu-id="24cbf-182">“类别”</span><span class="sxs-lookup"><span data-stu-id="24cbf-182">category</span></span>| <span data-ttu-id="24cbf-183">String</span><span class="sxs-lookup"><span data-stu-id="24cbf-183">String</span></span> | <span data-ttu-id="24cbf-184">警报的类别。</span><span class="sxs-lookup"><span data-stu-id="24cbf-184">Category of the alert.</span></span> <span data-ttu-id="24cbf-185">属性值包括："General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"Exfiltration"、"Exploit"、"Execution"、"InitialAccess"、"DefenseMovement"、"Malware"、"Persistence"、"PrivilegeEscalation"、"Ransomware"、"SuspiciousActivity"（ **必需**）。</span><span class="sxs-lookup"><span data-stu-id="24cbf-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="24cbf-186">响应</span><span class="sxs-lookup"><span data-stu-id="24cbf-186">Response</span></span>

<span data-ttu-id="24cbf-187">如果成功，此方法在响应正文中返回 200 OK 和一个新的 [alert](alerts.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="24cbf-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="24cbf-188">如果具有指定属性的事件 (_reportId_ _、eventTime_ 和 _machineId_) 未找到 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="24cbf-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="24cbf-189">示例</span><span class="sxs-lookup"><span data-stu-id="24cbf-189">Example</span></span>

<span data-ttu-id="24cbf-190">**请求**</span><span class="sxs-lookup"><span data-stu-id="24cbf-190">**Request**</span></span>

<span data-ttu-id="24cbf-191">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="24cbf-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
