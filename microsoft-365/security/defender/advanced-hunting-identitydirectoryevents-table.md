---
title: 高级搜寻架构中的 IdentityDirectoryEvents 表
description: 了解高级搜寻架构的 IdentityDirectoryEvents 表中的域控制器和 Active Directory 事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， IdentityDirectoryEvents， 域控制器， Active Directory， Azure ATP， 标识
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ba63bdeb215c24e68d0e507d99e026c5b2695cb0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056474"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="d7f7b-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="d7f7b-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7f7b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d7f7b-105">**Applies to:**</span></span>
- <span data-ttu-id="d7f7b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7f7b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d7f7b-107">高级 `IdentityDirectoryEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含涉及运行 Active Directory 和 AD (本地域控制器) 。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="d7f7b-108">此表捕获各种与标识相关的事件，如密码更改、密码过期和用户主体名称 (UPN) 更改。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="d7f7b-109">它还捕获域控制器上的系统事件，如计划任务和 PowerShell 活动。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="d7f7b-110">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="d7f7b-111">有关表支持的事件类型 () ，请使用安全中心中提供的内置架构 `ActionType` 参考。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="d7f7b-112">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d7f7b-113">列名称</span><span class="sxs-lookup"><span data-stu-id="d7f7b-113">Column name</span></span> | <span data-ttu-id="d7f7b-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="d7f7b-114">Data type</span></span> | <span data-ttu-id="d7f7b-115">说明</span><span class="sxs-lookup"><span data-stu-id="d7f7b-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d7f7b-116">datetime</span><span class="sxs-lookup"><span data-stu-id="d7f7b-116">datetime</span></span> | <span data-ttu-id="d7f7b-117">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d7f7b-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d7f7b-118">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-118">string</span></span> | <span data-ttu-id="d7f7b-119">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="d7f7b-120">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="d7f7b-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="d7f7b-121">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-121">string</span></span> | <span data-ttu-id="d7f7b-122">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="d7f7b-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="d7f7b-123">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-123">string</span></span> | <span data-ttu-id="d7f7b-124">用户主体 (UPN) 记录操作应用于的帐户的名称</span><span class="sxs-lookup"><span data-stu-id="d7f7b-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="d7f7b-125">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-125">string</span></span> | <span data-ttu-id="d7f7b-126">已记录操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="d7f7b-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="d7f7b-127">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-127">string</span></span> | <span data-ttu-id="d7f7b-128">已记录 (的) 的设备的完全限定域名和 FQDN</span><span class="sxs-lookup"><span data-stu-id="d7f7b-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="d7f7b-129">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-129">string</span></span> | <span data-ttu-id="d7f7b-130">运行处理所记录操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="d7f7b-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="d7f7b-131">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-131">string</span></span> | <span data-ttu-id="d7f7b-132">运行处理所记录操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d7f7b-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="d7f7b-133">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-133">string</span></span> | <span data-ttu-id="d7f7b-134">活动的目标端口</span><span class="sxs-lookup"><span data-stu-id="d7f7b-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="d7f7b-135">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-135">string</span></span> | <span data-ttu-id="d7f7b-136">通信期间使用的协议</span><span class="sxs-lookup"><span data-stu-id="d7f7b-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="d7f7b-137">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-137">string</span></span> | <span data-ttu-id="d7f7b-138">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="d7f7b-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="d7f7b-139">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-139">string</span></span> | <span data-ttu-id="d7f7b-140">帐户的域</span><span class="sxs-lookup"><span data-stu-id="d7f7b-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="d7f7b-141">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-141">string</span></span> | <span data-ttu-id="d7f7b-142">帐户 (UPN) 用户主体名称</span><span class="sxs-lookup"><span data-stu-id="d7f7b-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="d7f7b-143">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-143">string</span></span> | <span data-ttu-id="d7f7b-144">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="d7f7b-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="d7f7b-145">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-145">string</span></span> | <span data-ttu-id="d7f7b-146">Azure Active Directory 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d7f7b-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d7f7b-147">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-147">string</span></span> | <span data-ttu-id="d7f7b-148">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d7f7b-149">通常是给定或名字、中间启动和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="d7f7b-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="d7f7b-150">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-150">string</span></span> | <span data-ttu-id="d7f7b-151">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="d7f7b-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="d7f7b-152">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-152">string</span></span> | <span data-ttu-id="d7f7b-153">通信期间分配给设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d7f7b-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="d7f7b-154">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-154">string</span></span> | <span data-ttu-id="d7f7b-155">通信期间使用的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="d7f7b-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="d7f7b-156">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-156">string</span></span> | <span data-ttu-id="d7f7b-157">与事件关联的城市、国家/地区或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="d7f7b-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="d7f7b-158">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-158">string</span></span> | <span data-ttu-id="d7f7b-159">与 IP 地址关联的 Internet 服务提供商</span><span class="sxs-lookup"><span data-stu-id="d7f7b-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="d7f7b-160">long</span><span class="sxs-lookup"><span data-stu-id="d7f7b-160">long</span></span> | <span data-ttu-id="d7f7b-161">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d7f7b-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="d7f7b-162">string</span><span class="sxs-lookup"><span data-stu-id="d7f7b-162">string</span></span> | <span data-ttu-id="d7f7b-163">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="d7f7b-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d7f7b-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7f7b-164">Related topics</span></span>
- [<span data-ttu-id="d7f7b-165">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d7f7b-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d7f7b-166">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d7f7b-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d7f7b-167">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d7f7b-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d7f7b-168">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="d7f7b-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d7f7b-169">了解架构</span><span class="sxs-lookup"><span data-stu-id="d7f7b-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d7f7b-170">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d7f7b-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
