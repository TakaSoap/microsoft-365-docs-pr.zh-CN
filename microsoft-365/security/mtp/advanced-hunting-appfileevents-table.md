---
title: 高级搜寻架构中的 AppFileEvents 表
description: 了解与高级搜寻架构的 AppFileEvents 表中的云应用和服务关联的与文件相关的事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AppFileEvents、云应用安全性、MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899335"
---
# <a name="appfileevents"></a><span data-ttu-id="2c7f8-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="2c7f8-104">AppFileEvents</span></span>

<span data-ttu-id="2c7f8-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2c7f8-105">**Applies to:**</span></span>
- <span data-ttu-id="2c7f8-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="2c7f8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2c7f8-107">`AppFileEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关 Microsoft 云应用安全监视的云应用和服务中与文件相关的活动的信息。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="2c7f8-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="2c7f8-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2c7f8-110">列名称</span><span class="sxs-lookup"><span data-stu-id="2c7f8-110">Column name</span></span> | <span data-ttu-id="2c7f8-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="2c7f8-111">Data type</span></span> | <span data-ttu-id="2c7f8-112">说明</span><span class="sxs-lookup"><span data-stu-id="2c7f8-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2c7f8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="2c7f8-113">datetime</span></span> | <span data-ttu-id="2c7f8-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="2c7f8-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2c7f8-115">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-115">string</span></span> | <span data-ttu-id="2c7f8-116">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="2c7f8-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="2c7f8-117">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-117">string</span></span> | <span data-ttu-id="2c7f8-118">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="2c7f8-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="2c7f8-119">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-119">string</span></span> | <span data-ttu-id="2c7f8-120">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="2c7f8-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="2c7f8-121">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-121">string</span></span> | <span data-ttu-id="2c7f8-122">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="2c7f8-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="2c7f8-123">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-123">string</span></span> | <span data-ttu-id="2c7f8-124">作为操作的结果重命名的文件的原始名称</span><span class="sxs-lookup"><span data-stu-id="2c7f8-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="2c7f8-125">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-125">string</span></span> | <span data-ttu-id="2c7f8-126">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="2c7f8-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2c7f8-127">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-127">string</span></span> | <span data-ttu-id="2c7f8-128">帐户的域</span><span class="sxs-lookup"><span data-stu-id="2c7f8-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="2c7f8-129">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-129">string</span></span> | <span data-ttu-id="2c7f8-130">帐户的用户主体名称（UPN）</span><span class="sxs-lookup"><span data-stu-id="2c7f8-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2c7f8-131">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-131">string</span></span> | <span data-ttu-id="2c7f8-132">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="2c7f8-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2c7f8-133">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-133">string</span></span> | <span data-ttu-id="2c7f8-134">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2c7f8-135">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="2c7f8-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="2c7f8-136">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-136">string</span></span> | <span data-ttu-id="2c7f8-137">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="2c7f8-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="2c7f8-138">string</span><span class="sxs-lookup"><span data-stu-id="2c7f8-138">string</span></span> | <span data-ttu-id="2c7f8-139">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="2c7f8-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2c7f8-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="2c7f8-140">Related topics</span></span>
- [<span data-ttu-id="2c7f8-141">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="2c7f8-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2c7f8-142">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="2c7f8-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2c7f8-143">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="2c7f8-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2c7f8-144">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="2c7f8-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2c7f8-145">了解架构</span><span class="sxs-lookup"><span data-stu-id="2c7f8-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2c7f8-146">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="2c7f8-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
