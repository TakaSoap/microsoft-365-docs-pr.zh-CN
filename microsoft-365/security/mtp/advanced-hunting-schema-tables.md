---
title: Microsoft 威胁防护高级搜寻架构中的数据表
description: 了解高级搜寻架构中的表，以了解可运行威胁搜寻查询的数据
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、数据
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aa2fbeebed10bcb1f0c4078a161be99d16d3b97b
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210317"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="1d1b2-104">了解高级搜寻架构</span><span class="sxs-lookup"><span data-stu-id="1d1b2-104">Understand the advanced hunting schema</span></span>

<span data-ttu-id="1d1b2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-105">**Applies to:**</span></span>
- <span data-ttu-id="1d1b2-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="1d1b2-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1d1b2-107">[高级搜寻](advanced-hunting-overview.md)架构由可提供事件信息或计算机和实体相关信息的多个表组成。</span><span class="sxs-lookup"><span data-stu-id="1d1b2-107">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about machines and entities.</span></span> <span data-ttu-id="1d1b2-108">若要高效构建跨多个表的查询，需要了解高级搜寻架构中的表和列。</span><span class="sxs-lookup"><span data-stu-id="1d1b2-108">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="schema-tables"></a><span data-ttu-id="1d1b2-109">架构表</span><span class="sxs-lookup"><span data-stu-id="1d1b2-109">Schema tables</span></span>

<span data-ttu-id="1d1b2-110">以下引用列出了架构中的所有表。</span><span class="sxs-lookup"><span data-stu-id="1d1b2-110">The following reference lists all the tables in the schema.</span></span> <span data-ttu-id="1d1b2-111">每个表名称链接到描述该表的列名称的页面。</span><span class="sxs-lookup"><span data-stu-id="1d1b2-111">Each table name links to a page describing the column names for that table.</span></span> <span data-ttu-id="1d1b2-112">表和列名称作为架构表示的一部分列在安全中心的“高级搜寻”屏幕上。</span><span class="sxs-lookup"><span data-stu-id="1d1b2-112">Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="1d1b2-113">表名</span><span class="sxs-lookup"><span data-stu-id="1d1b2-113">Table name</span></span> | <span data-ttu-id="1d1b2-114">说明</span><span class="sxs-lookup"><span data-stu-id="1d1b2-114">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="1d1b2-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="1d1b2-116">计算机信息，包括操作系统信息</span><span class="sxs-lookup"><span data-stu-id="1d1b2-116">Machine information, including OS information</span></span> |
| <span data-ttu-id="1d1b2-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="1d1b2-118">计算机的网络属性，包括适配器、IP 和 MAC 地址，以及已连接的网络和域</span><span class="sxs-lookup"><span data-stu-id="1d1b2-118">Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="1d1b2-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-120">过程创建和相关事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-120">Process creation and related events</span></span> |
| <span data-ttu-id="1d1b2-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-122">网络连接和相关事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-122">Network connection and related events</span></span> |
| <span data-ttu-id="1d1b2-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-124">文件创建、修改和其他文件系统事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-124">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="1d1b2-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-126">创建和修改注册表项</span><span class="sxs-lookup"><span data-stu-id="1d1b2-126">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="1d1b2-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-128">登录和其他身份验证事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-128">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="1d1b2-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-130">DLL 加载事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-130">DLL loading events</span></span> |
| <span data-ttu-id="1d1b2-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-132">多个事件类型，包括安全控件（如 Windows Defender 防病毒和 Exploit Protection）触发的事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-132">Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="1d1b2-133">**[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-133">**[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)**</span></span> | <span data-ttu-id="1d1b2-134">从终结点上的证书验证事件获取的签名文件的证书信息</span><span class="sxs-lookup"><span data-stu-id="1d1b2-134">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="1d1b2-135">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-135">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span></span> | <span data-ttu-id="1d1b2-136">Office 365 电子邮件事件，包括电子邮件送达和阻止事件</span><span class="sxs-lookup"><span data-stu-id="1d1b2-136">Office 365 email events, including email delivery and blocking events</span></span> |
| <span data-ttu-id="1d1b2-137">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-137">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span></span> | <span data-ttu-id="1d1b2-138">有关附加到 Office 365 电子邮件的文件的信息</span><span class="sxs-lookup"><span data-stu-id="1d1b2-138">Information about files attached to Office 365 emails</span></span> |
| <span data-ttu-id="1d1b2-139">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-139">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span></span> | <span data-ttu-id="1d1b2-140">有关 Office 365 电子邮件上的 URL 的信息</span><span class="sxs-lookup"><span data-stu-id="1d1b2-140">Information about URLs on Office 365 emails</span></span> |
| <span data-ttu-id="1d1b2-141">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-141">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span></span> | <span data-ttu-id="1d1b2-142">设备上的软件清单以及这些软件产品中的任何已知漏洞</span><span class="sxs-lookup"><span data-stu-id="1d1b2-142">Inventory of software on devices as well as any known vulnerabilities in these software products</span></span> |
| <span data-ttu-id="1d1b2-143">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-143">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span></span> | <span data-ttu-id="1d1b2-144">公开披露的漏洞的知识库，包括攻击代码是否已公开</span><span class="sxs-lookup"><span data-stu-id="1d1b2-144">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="1d1b2-145">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-145">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span></span> | <span data-ttu-id="1d1b2-146">威胁和漏洞管理评估事件，指示设备上的各种安全配置的状态</span><span class="sxs-lookup"><span data-stu-id="1d1b2-146">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="1d1b2-147">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="1d1b2-147">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span></span> | <span data-ttu-id="1d1b2-148">威胁和漏洞管理用于评估设备的各种安全配置的知识库；包括各种标准和基准的映射</span><span class="sxs-lookup"><span data-stu-id="1d1b2-148">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="1d1b2-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="1d1b2-149">Related topics</span></span>
- [<span data-ttu-id="1d1b2-150">主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="1d1b2-150">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1d1b2-151">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="1d1b2-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1d1b2-152">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="1d1b2-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1d1b2-153">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="1d1b2-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1d1b2-154">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="1d1b2-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)