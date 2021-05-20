---
title: 高级搜寻架构中的 AADSpnSignInEventsBeta 表
description: 了解与高级搜寻Azure Active Directory服务主体和托管标识登录事件表关联的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， AlertInfo， 警报， 实体， 证据， 文件， IP 地址， 设备， 计算机， 用户， 帐户， 标识， AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583540"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="74a6c-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="74a6c-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="74a6c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74a6c-105">**Applies to:**</span></span>

- <span data-ttu-id="74a6c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74a6c-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="74a6c-107">该表当前处于 beta 版本，并短期提供，以便你可以通过 Azure Active Directory (AAD) 服务主体和托管身份登录事件进行 `AADSpnSignInEventsBeta` 搜寻。</span><span class="sxs-lookup"><span data-stu-id="74a6c-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="74a6c-108">我们最终将所有登录架构信息移动到 `IdentityLogonEvents` 表中。</span><span class="sxs-lookup"><span data-stu-id="74a6c-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="74a6c-109">高级 `AADSpnSignInEventsBeta` 搜寻架构中的表包含有关Azure Active Directory主体和托管标识登录的信息。你可以了解有关登录活动报告中不同类型的登录Azure Active Directory[预览](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。</span><span class="sxs-lookup"><span data-stu-id="74a6c-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="74a6c-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="74a6c-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="74a6c-111">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。</span><span class="sxs-lookup"><span data-stu-id="74a6c-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="74a6c-112">列名称</span><span class="sxs-lookup"><span data-stu-id="74a6c-112">Column name</span></span>     | <span data-ttu-id="74a6c-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="74a6c-113">Data type</span></span> | <span data-ttu-id="74a6c-114">说明</span><span class="sxs-lookup"><span data-stu-id="74a6c-114">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="74a6c-115">datetime</span><span class="sxs-lookup"><span data-stu-id="74a6c-115">datetime</span></span>      | <span data-ttu-id="74a6c-116">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="74a6c-116">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="74a6c-117">string</span><span class="sxs-lookup"><span data-stu-id="74a6c-117">string</span></span>        | <span data-ttu-id="74a6c-118">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="74a6c-118">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="74a6c-119">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-119">string</span></span>        | <span data-ttu-id="74a6c-120">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-120">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="74a6c-121">boolean</span><span class="sxs-lookup"><span data-stu-id="74a6c-121">boolean</span></span>       | <span data-ttu-id="74a6c-122">指示登录是否由托管标识启动</span><span class="sxs-lookup"><span data-stu-id="74a6c-122">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="74a6c-123">int</span><span class="sxs-lookup"><span data-stu-id="74a6c-123">int</span></span>        | <span data-ttu-id="74a6c-124">包含登录错误时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="74a6c-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="74a6c-125">若要查找特定错误代码的说明，请访问 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="74a6c-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="74a6c-126">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-126">string</span></span>        | <span data-ttu-id="74a6c-127">登录事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-127">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="74a6c-128">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-128">string</span></span>        | <span data-ttu-id="74a6c-129">启动登录的服务主体的名称</span><span class="sxs-lookup"><span data-stu-id="74a6c-129">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="74a6c-130">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-130">string</span></span>        | <span data-ttu-id="74a6c-131">启动登录的服务主体的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-131">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="74a6c-132">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-132">string</span></span>        | <span data-ttu-id="74a6c-133">访问的资源的显示名称</span><span class="sxs-lookup"><span data-stu-id="74a6c-133">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="74a6c-134">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-134">string</span></span>        | <span data-ttu-id="74a6c-135">访问的资源的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-135">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="74a6c-136">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-136">string</span></span>        | <span data-ttu-id="74a6c-137">访问的资源的租户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-137">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="74a6c-138">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-138">string</span></span>        | <span data-ttu-id="74a6c-139">分配给终结点的 IP 地址，在相关的网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="74a6c-139">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="74a6c-140">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-140">string</span></span>        | <span data-ttu-id="74a6c-141">指示客户端 IP 地址已异地分配的国家/地区两个字母的代码</span><span class="sxs-lookup"><span data-stu-id="74a6c-141">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="74a6c-142">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-142">string</span></span>        | <span data-ttu-id="74a6c-143">登录发生的位置（如果可用）</span><span class="sxs-lookup"><span data-stu-id="74a6c-143">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="74a6c-144">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-144">string</span></span>        | <span data-ttu-id="74a6c-145">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="74a6c-145">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="74a6c-146">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-146">string</span></span>        | <span data-ttu-id="74a6c-147">登录位置的北向南部坐标</span><span class="sxs-lookup"><span data-stu-id="74a6c-147">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="74a6c-148">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-148">string</span></span>        | <span data-ttu-id="74a6c-149">登录位置的从西到西坐标</span><span class="sxs-lookup"><span data-stu-id="74a6c-149">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="74a6c-150">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-150">string</span></span>        | <span data-ttu-id="74a6c-151">请求的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-151">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="74a6c-152">字符串</span><span class="sxs-lookup"><span data-stu-id="74a6c-152">string</span></span> | <span data-ttu-id="74a6c-153">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="74a6c-153">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="74a6c-154">相关文章</span><span class="sxs-lookup"><span data-stu-id="74a6c-154">Related articles</span></span>

-   [<span data-ttu-id="74a6c-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="74a6c-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="74a6c-156">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="74a6c-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="74a6c-157">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="74a6c-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="74a6c-158">了解架构</span><span class="sxs-lookup"><span data-stu-id="74a6c-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)