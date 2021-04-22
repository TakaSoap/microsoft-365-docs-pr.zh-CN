---
title: 高级搜寻架构中的 AADSpnSignInEventsBeta 表
description: 了解与高级搜寻架构的 Azure Active Directory 服务主体和托管标识登录事件表关联的信息
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
ms.openlocfilehash: 984e945107b6e0b41459659a7f2e9f649981e4b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932591"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="576a8-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="576a8-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="576a8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="576a8-105">**Applies to:**</span></span>

- <span data-ttu-id="576a8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="576a8-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="576a8-107">该表当前处于 beta 版本，并短期提供，以允许你通过 Azure Active Directory (AAD) 服务主体和托管身份登录事件进行 `AADSpnSignInEventsBeta` 搜寻。</span><span class="sxs-lookup"><span data-stu-id="576a8-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="576a8-108">我们最终将所有登录架构信息移动到 `IdentityLogonEvents` 表中。</span><span class="sxs-lookup"><span data-stu-id="576a8-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="576a8-109">通过 Azure Defender 的集成 Microsoft Defender 终结点解决方案访问 Microsoft 365 Defender，但没有 Microsoft Defender for Office、Microsoft Defender for Identity 或 Microsoft Cloud App Security 许可证的客户将无法查看此架构。</span><span class="sxs-lookup"><span data-stu-id="576a8-109">Customers who can access Microsoft 365 Defender through the Azure Defender’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="576a8-110">高级 `AADSpnSignInEventsBeta` 搜寻架构中的表包含有关 Azure Active Directory 服务主体和托管标识登录的信息。你可以了解有关 [Azure Active Directory](/azure/active-directory/reports-monitoring/concept-all-sign-ins)登录活动报告中不同类型的登录的详细信息- 预览 。</span><span class="sxs-lookup"><span data-stu-id="576a8-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="576a8-111">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="576a8-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="576a8-112">有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。</span><span class="sxs-lookup"><span data-stu-id="576a8-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="576a8-113">列名称</span><span class="sxs-lookup"><span data-stu-id="576a8-113">Column name</span></span>     | <span data-ttu-id="576a8-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="576a8-114">Data type</span></span> | <span data-ttu-id="576a8-115">说明</span><span class="sxs-lookup"><span data-stu-id="576a8-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="576a8-116">datetime</span><span class="sxs-lookup"><span data-stu-id="576a8-116">datetime</span></span>      | <span data-ttu-id="576a8-117">生成记录的日期和时间</span><span class="sxs-lookup"><span data-stu-id="576a8-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="576a8-118">string</span><span class="sxs-lookup"><span data-stu-id="576a8-118">string</span></span>        | <span data-ttu-id="576a8-119">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="576a8-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="576a8-120">string</span><span class="sxs-lookup"><span data-stu-id="576a8-120">string</span></span>        | <span data-ttu-id="576a8-121">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="576a8-122">boolean</span><span class="sxs-lookup"><span data-stu-id="576a8-122">boolean</span></span>       | <span data-ttu-id="576a8-123">指示登录是否由托管标识启动</span><span class="sxs-lookup"><span data-stu-id="576a8-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="576a8-124">int</span><span class="sxs-lookup"><span data-stu-id="576a8-124">int</span></span>        | <span data-ttu-id="576a8-125">包含登录错误时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="576a8-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="576a8-126">若要查找特定错误代码的说明，请访问 <https://aka.ms/AADsigninsErrorCodes> 。</span><span class="sxs-lookup"><span data-stu-id="576a8-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="576a8-127">string</span><span class="sxs-lookup"><span data-stu-id="576a8-127">string</span></span>        | <span data-ttu-id="576a8-128">登录事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="576a8-129">string</span><span class="sxs-lookup"><span data-stu-id="576a8-129">string</span></span>        | <span data-ttu-id="576a8-130">启动登录的服务主体的名称</span><span class="sxs-lookup"><span data-stu-id="576a8-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="576a8-131">string</span><span class="sxs-lookup"><span data-stu-id="576a8-131">string</span></span>        | <span data-ttu-id="576a8-132">启动登录的服务主体的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="576a8-133">string</span><span class="sxs-lookup"><span data-stu-id="576a8-133">string</span></span>        | <span data-ttu-id="576a8-134">访问的资源的显示名称</span><span class="sxs-lookup"><span data-stu-id="576a8-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="576a8-135">string</span><span class="sxs-lookup"><span data-stu-id="576a8-135">string</span></span>        | <span data-ttu-id="576a8-136">访问的资源的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="576a8-137">string</span><span class="sxs-lookup"><span data-stu-id="576a8-137">string</span></span>        | <span data-ttu-id="576a8-138">访问的资源的租户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="576a8-139">string</span><span class="sxs-lookup"><span data-stu-id="576a8-139">string</span></span>        | <span data-ttu-id="576a8-140">分配给终结点的 IP 地址，在相关的网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="576a8-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="576a8-141">string</span><span class="sxs-lookup"><span data-stu-id="576a8-141">string</span></span>        | <span data-ttu-id="576a8-142">指示客户端 IP 地址已异地分配的国家/地区两个字母的代码</span><span class="sxs-lookup"><span data-stu-id="576a8-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="576a8-143">string</span><span class="sxs-lookup"><span data-stu-id="576a8-143">string</span></span>        | <span data-ttu-id="576a8-144">登录发生的位置（如果可用）</span><span class="sxs-lookup"><span data-stu-id="576a8-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="576a8-145">string</span><span class="sxs-lookup"><span data-stu-id="576a8-145">string</span></span>        | <span data-ttu-id="576a8-146">帐户用户所在的城市</span><span class="sxs-lookup"><span data-stu-id="576a8-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="576a8-147">string</span><span class="sxs-lookup"><span data-stu-id="576a8-147">string</span></span>        | <span data-ttu-id="576a8-148">登录位置的北向南部坐标</span><span class="sxs-lookup"><span data-stu-id="576a8-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="576a8-149">string</span><span class="sxs-lookup"><span data-stu-id="576a8-149">string</span></span>        | <span data-ttu-id="576a8-150">登录位置的从西到西坐标</span><span class="sxs-lookup"><span data-stu-id="576a8-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="576a8-151">string</span><span class="sxs-lookup"><span data-stu-id="576a8-151">string</span></span>        | <span data-ttu-id="576a8-152">请求的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="576a8-153">string</span><span class="sxs-lookup"><span data-stu-id="576a8-153">string</span></span> | <span data-ttu-id="576a8-154">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="576a8-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="576a8-155">相关文章</span><span class="sxs-lookup"><span data-stu-id="576a8-155">Related articles</span></span>

-   [<span data-ttu-id="576a8-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="576a8-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="576a8-157">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="576a8-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="576a8-158">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="576a8-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="576a8-159">了解架构</span><span class="sxs-lookup"><span data-stu-id="576a8-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)