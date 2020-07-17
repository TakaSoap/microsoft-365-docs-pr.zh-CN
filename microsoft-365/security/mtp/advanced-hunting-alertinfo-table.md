---
title: 高级搜寻架构中的 AlertInfo 表
description: 了解高级搜寻架构的 AlertInfo 表中的警报生成事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AlertInfo、警报、严重性、类别、MITRE、ATT&CK、Microsoft Defender ATP、MDATP、Office 365 ATP、Microsoft Cloud App Security、MCAS 和 Azure ATP
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
ms.openlocfilehash: a1290ee415073a9cb3948bc4b0cc6bb3ae13285b
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899013"
---
# <a name="alertinfo"></a><span data-ttu-id="da828-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="da828-104">AlertInfo</span></span>

<span data-ttu-id="da828-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="da828-105">**Applies to:**</span></span>
- <span data-ttu-id="da828-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="da828-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="da828-107">`AlertInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含来自 Microsoft Defender ATP、Office 365 Atp、Microsoft 云应用安全性和 Azure atp 的警报信息。</span><span class="sxs-lookup"><span data-stu-id="da828-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="da828-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="da828-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="da828-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="da828-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="da828-110">列名称</span><span class="sxs-lookup"><span data-stu-id="da828-110">Column name</span></span> | <span data-ttu-id="da828-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="da828-111">Data type</span></span> | <span data-ttu-id="da828-112">说明</span><span class="sxs-lookup"><span data-stu-id="da828-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="da828-113">datetime</span><span class="sxs-lookup"><span data-stu-id="da828-113">datetime</span></span> | <span data-ttu-id="da828-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="da828-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="da828-115">string</span><span class="sxs-lookup"><span data-stu-id="da828-115">string</span></span> | <span data-ttu-id="da828-116">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="da828-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="da828-117">string</span><span class="sxs-lookup"><span data-stu-id="da828-117">string</span></span> | <span data-ttu-id="da828-118">警报的标题</span><span class="sxs-lookup"><span data-stu-id="da828-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="da828-119">string</span><span class="sxs-lookup"><span data-stu-id="da828-119">string</span></span> | <span data-ttu-id="da828-120">由警报标识的威胁指示器或违反活动的类型</span><span class="sxs-lookup"><span data-stu-id="da828-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="da828-121">string</span><span class="sxs-lookup"><span data-stu-id="da828-121">string</span></span> | <span data-ttu-id="da828-122">指示警报所标识的威胁指示器或违反活动的潜在影响（高、中或低）</span><span class="sxs-lookup"><span data-stu-id="da828-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="da828-123">string</span><span class="sxs-lookup"><span data-stu-id="da828-123">string</span></span> | <span data-ttu-id="da828-124">提供通知信息的产品或服务</span><span class="sxs-lookup"><span data-stu-id="da828-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="da828-125">string</span><span class="sxs-lookup"><span data-stu-id="da828-125">string</span></span> | <span data-ttu-id="da828-126">识别明显的组件或活动的检测技术或传感器</span><span class="sxs-lookup"><span data-stu-id="da828-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="da828-127">string</span><span class="sxs-lookup"><span data-stu-id="da828-127">string</span></span> | <span data-ttu-id="da828-128">MITRE ATT&与触发警报的活动相关联的 CK 技术</span><span class="sxs-lookup"><span data-stu-id="da828-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="da828-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="da828-129">Related topics</span></span>
- [<span data-ttu-id="da828-130">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="da828-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="da828-131">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="da828-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="da828-132">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="da828-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="da828-133">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="da828-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="da828-134">了解架构</span><span class="sxs-lookup"><span data-stu-id="da828-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="da828-135">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="da828-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
