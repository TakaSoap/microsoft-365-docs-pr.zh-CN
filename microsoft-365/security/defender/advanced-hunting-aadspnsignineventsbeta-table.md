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
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347903"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="10def-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="10def-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="10def-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="10def-105">**Applies to:**</span></span>

- <span data-ttu-id="10def-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10def-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="10def-107">该表当前处于 beta 版本，并短期提供，以便你可以通过 Azure Active Directory (AAD) 服务主体和托管身份登录事件进行 `AADSpnSignInEventsBeta` 搜寻。</span><span class="sxs-lookup"><span data-stu-id="10def-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="10def-108">我们最终将所有登录架构信息移动到 `IdentityLogonEvents` 表中。</span><span class="sxs-lookup"><span data-stu-id="10def-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="10def-109">高级 `AADSpnSignInEventsBeta` 搜寻架构中的表包含有关Azure Active Directory主体和托管标识登录的信息。你可以了解有关登录活动报告中不同类型的登录Azure Active Directory[预览](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。</span><span class="sxs-lookup"><span data-stu-id="10def-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="10def-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="10def-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="10def-111">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。</span><span class="sxs-lookup"><span data-stu-id="10def-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="10def-112">列名称</span><span class="sxs-lookup"><span data-stu-id="10def-112">Column name</span></span> | <span data-ttu-id="10def-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="10def-113">Data type</span></span> | <span data-ttu-id="10def-114">说明</span><span class="sxs-lookup"><span data-stu-id="10def-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="10def-115">datetime</span><span class="sxs-lookup"><span data-stu-id="10def-115">datetime</span></span> | <span data-ttu-id="10def-116">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="10def-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="10def-117">string</span><span class="sxs-lookup"><span data-stu-id="10def-117">string</span></span> | <span data-ttu-id="10def-118">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="10def-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="10def-119">string</span><span class="sxs-lookup"><span data-stu-id="10def-119">string</span></span> | <span data-ttu-id="10def-120">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="10def-121">boolean</span><span class="sxs-lookup"><span data-stu-id="10def-121">boolean</span></span>       | <span data-ttu-id="10def-122">指示登录是否由托管标识启动</span><span class="sxs-lookup"><span data-stu-id="10def-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="10def-123">int</span><span class="sxs-lookup"><span data-stu-id="10def-123">int</span></span> | <span data-ttu-id="10def-124">包含登录错误时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="10def-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="10def-125">若要查找特定错误代码的说明，请访问 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="10def-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="10def-126">string</span><span class="sxs-lookup"><span data-stu-id="10def-126">string</span></span>        | <span data-ttu-id="10def-127">登录事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="10def-128">string</span><span class="sxs-lookup"><span data-stu-id="10def-128">string</span></span>        | <span data-ttu-id="10def-129">启动登录的服务主体的名称</span><span class="sxs-lookup"><span data-stu-id="10def-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="10def-130">string</span><span class="sxs-lookup"><span data-stu-id="10def-130">string</span></span>        | <span data-ttu-id="10def-131">启动登录的服务主体的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="10def-132">string</span><span class="sxs-lookup"><span data-stu-id="10def-132">string</span></span>        | <span data-ttu-id="10def-133">访问的资源的显示名称</span><span class="sxs-lookup"><span data-stu-id="10def-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="10def-134">string</span><span class="sxs-lookup"><span data-stu-id="10def-134">string</span></span>        | <span data-ttu-id="10def-135">访问的资源的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="10def-136">string</span><span class="sxs-lookup"><span data-stu-id="10def-136">string</span></span>        | <span data-ttu-id="10def-137">访问的资源的租户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="10def-138">string</span><span class="sxs-lookup"><span data-stu-id="10def-138">string</span></span>        | <span data-ttu-id="10def-139">分配给终结点的 IP 地址，在相关的网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="10def-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="10def-140">string</span><span class="sxs-lookup"><span data-stu-id="10def-140">string</span></span>        | <span data-ttu-id="10def-141">指示客户端 IP 地址已异地分配的国家/地区两个字母的代码</span><span class="sxs-lookup"><span data-stu-id="10def-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="10def-142">string</span><span class="sxs-lookup"><span data-stu-id="10def-142">string</span></span>        | <span data-ttu-id="10def-143">登录发生的位置（如果可用）</span><span class="sxs-lookup"><span data-stu-id="10def-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="10def-144">string</span><span class="sxs-lookup"><span data-stu-id="10def-144">string</span></span>        | <span data-ttu-id="10def-145">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="10def-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="10def-146">string</span><span class="sxs-lookup"><span data-stu-id="10def-146">string</span></span>        | <span data-ttu-id="10def-147">登录位置的北向南部坐标</span><span class="sxs-lookup"><span data-stu-id="10def-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="10def-148">string</span><span class="sxs-lookup"><span data-stu-id="10def-148">string</span></span>        | <span data-ttu-id="10def-149">登录位置的从西到西坐标</span><span class="sxs-lookup"><span data-stu-id="10def-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="10def-150">string</span><span class="sxs-lookup"><span data-stu-id="10def-150">string</span></span>        | <span data-ttu-id="10def-151">请求的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="10def-152">string</span><span class="sxs-lookup"><span data-stu-id="10def-152">string</span></span> | <span data-ttu-id="10def-153">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="10def-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="10def-154">相关文章</span><span class="sxs-lookup"><span data-stu-id="10def-154">Related articles</span></span>

-   [<span data-ttu-id="10def-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="10def-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="10def-156">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="10def-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="10def-157">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="10def-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="10def-158">了解架构</span><span class="sxs-lookup"><span data-stu-id="10def-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
