---
title: 高级搜寻架构中的 DeviceAlertEvents 表
description: 了解高级搜寻架构的 DeviceAlertEvents 表中的警报生成事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， DeviceAlertEvents， 警报， 严重性， 类别
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 66ecdc8fbcde04d78f2deede5f4e296a7f051ef0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499161"
---
# <a name="devicealertevents"></a><span data-ttu-id="e9f6c-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="e9f6c-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9f6c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e9f6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9f6c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e9f6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="e9f6c-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="e9f6c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e9f6c-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e9f6c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="e9f6c-109">高级 `DeviceAlertEvents` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关 Microsoft Defender 安全中心警报的信息。</span><span class="sxs-lookup"><span data-stu-id="e9f6c-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="e9f6c-110">使用此参考来构建从该表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="e9f6c-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e9f6c-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f6c-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="e9f6c-112">列名称</span><span class="sxs-lookup"><span data-stu-id="e9f6c-112">Column name</span></span> | <span data-ttu-id="e9f6c-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="e9f6c-113">Data type</span></span> | <span data-ttu-id="e9f6c-114">说明</span><span class="sxs-lookup"><span data-stu-id="e9f6c-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="e9f6c-115">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-115">string</span></span> | <span data-ttu-id="e9f6c-116">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="e9f6c-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="e9f6c-117">datetime</span><span class="sxs-lookup"><span data-stu-id="e9f6c-117">datetime</span></span> | <span data-ttu-id="e9f6c-118">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="e9f6c-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e9f6c-119">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-119">string</span></span> | <span data-ttu-id="e9f6c-120">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="e9f6c-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e9f6c-121">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-121">string</span></span> | <span data-ttu-id="e9f6c-122">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="e9f6c-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="e9f6c-123">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-123">string</span></span> | <span data-ttu-id="e9f6c-124">指示警报所标识的威胁指示器或违反活动的潜在影响（高、中或低）</span><span class="sxs-lookup"><span data-stu-id="e9f6c-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="e9f6c-125">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-125">string</span></span> | <span data-ttu-id="e9f6c-126">由警报标识的威胁指示器或违反活动的类型</span><span class="sxs-lookup"><span data-stu-id="e9f6c-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="e9f6c-127">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-127">string</span></span> | <span data-ttu-id="e9f6c-128">警报的标题</span><span class="sxs-lookup"><span data-stu-id="e9f6c-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="e9f6c-129">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-129">string</span></span> | <span data-ttu-id="e9f6c-130">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="e9f6c-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e9f6c-131">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-131">string</span></span> | <span data-ttu-id="e9f6c-132">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="e9f6c-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e9f6c-133">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-133">string</span></span> | <span data-ttu-id="e9f6c-134">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e9f6c-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="e9f6c-135">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-135">string</span></span> | <span data-ttu-id="e9f6c-136">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="e9f6c-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="e9f6c-137">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-137">string</span></span> | <span data-ttu-id="e9f6c-138">MITRE ATT&触发警报的活动相关的 CK 技术</span><span class="sxs-lookup"><span data-stu-id="e9f6c-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="e9f6c-139">long</span><span class="sxs-lookup"><span data-stu-id="e9f6c-139">long</span></span> | <span data-ttu-id="e9f6c-140">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="e9f6c-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e9f6c-141">若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用</span><span class="sxs-lookup"><span data-stu-id="e9f6c-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="e9f6c-142">string</span><span class="sxs-lookup"><span data-stu-id="e9f6c-142">string</span></span> | <span data-ttu-id="e9f6c-143">包含事件详细信息的表</span><span class="sxs-lookup"><span data-stu-id="e9f6c-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e9f6c-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="e9f6c-144">Related topics</span></span>
- [<span data-ttu-id="e9f6c-145">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="e9f6c-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9f6c-146">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="e9f6c-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9f6c-147">了解架构</span><span class="sxs-lookup"><span data-stu-id="e9f6c-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
