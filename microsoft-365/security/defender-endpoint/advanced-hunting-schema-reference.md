---
title: 高级搜寻架构参考
description: 了解高级搜寻架构中的表，以了解可以运行威胁搜寻查询的数据。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， 适用于终结点的 microsoft defender， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: fa111197dfd68cfcca40ce8a39befe20b97d1be8
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939632"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="53369-104">了解 Microsoft Defender for Endpoint 中的高级搜寻架构</span><span class="sxs-lookup"><span data-stu-id="53369-104">Understand the advanced hunting schema in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53369-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="53369-105">**Applies to:**</span></span>
- [<span data-ttu-id="53369-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="53369-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="53369-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="53369-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="53369-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="53369-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="53369-109">高级 [搜寻](advanced-hunting-overview.md) 架构由多个表组成，这些表提供事件信息或有关设备和其他实体的信息。</span><span class="sxs-lookup"><span data-stu-id="53369-109">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about devices and other entities.</span></span> <span data-ttu-id="53369-110">若要高效构建跨多个表的查询，需要了解高级搜寻架构中的表和列。</span><span class="sxs-lookup"><span data-stu-id="53369-110">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="get-schema-information-in-the-security-center"></a><span data-ttu-id="53369-111">在安全中心获取架构信息</span><span class="sxs-lookup"><span data-stu-id="53369-111">Get schema information in the security center</span></span>
<span data-ttu-id="53369-112">构造查询时，请使用内置架构参考快速获取有关架构中每个表的以下信息：</span><span class="sxs-lookup"><span data-stu-id="53369-112">While constructing queries, use the built-in schema reference to quickly get the following information about each table in the schema:</span></span>

- <span data-ttu-id="53369-113">**表** 说明 表中包含的数据类型以及该数据的来源。</span><span class="sxs-lookup"><span data-stu-id="53369-113">**Tables description**—type of data contained in the table and the source of that data.</span></span>
- <span data-ttu-id="53369-114">**列**- 表中的所有列。</span><span class="sxs-lookup"><span data-stu-id="53369-114">**Columns**—all the columns in the table.</span></span>
- <span data-ttu-id="53369-115">**操作** 类型 - 列中可能 `ActionType` 的值，表示表支持的事件类型。</span><span class="sxs-lookup"><span data-stu-id="53369-115">**Action types**—possible values in the `ActionType` column representing the event types supported by the table.</span></span> <span data-ttu-id="53369-116">这仅针对包含事件信息的表提供。</span><span class="sxs-lookup"><span data-stu-id="53369-116">This is provided only for tables that contain event information.</span></span>
- <span data-ttu-id="53369-117">**示例** 查询 - 具有表利用方式的示例查询。</span><span class="sxs-lookup"><span data-stu-id="53369-117">**Sample query**—example queries that feature how the table can be utilized.</span></span>

### <a name="access-the-schema-reference"></a><span data-ttu-id="53369-118">访问架构引用</span><span class="sxs-lookup"><span data-stu-id="53369-118">Access the schema reference</span></span>
<span data-ttu-id="53369-119">若要快速访问架构引用，请选择架构表示中表名称旁边的"查看引用"操作。</span><span class="sxs-lookup"><span data-stu-id="53369-119">To quickly access the schema reference, select the **View reference** action next to the table name in the schema representation.</span></span> <span data-ttu-id="53369-120">还可以选择" **架构引用** "来搜索表。</span><span class="sxs-lookup"><span data-stu-id="53369-120">You can also select **Schema reference** to search for a table.</span></span>

![显示如何访问门户内架构参考的图像](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a><span data-ttu-id="53369-122">了解架构表</span><span class="sxs-lookup"><span data-stu-id="53369-122">Learn the schema tables</span></span>

<span data-ttu-id="53369-123">以下引用列出了高级搜寻架构中的所有表。</span><span class="sxs-lookup"><span data-stu-id="53369-123">The following reference lists all the tables in the advanced hunting schema.</span></span> <span data-ttu-id="53369-124">每个表名称链接到描述该表的列名称的页面。</span><span class="sxs-lookup"><span data-stu-id="53369-124">Each table name links to a page describing the column names for that table.</span></span>

<span data-ttu-id="53369-125">表和列名称还会在 Microsoft Defender 安全中心内以高级搜寻屏幕上的架构表示形式列出。</span><span class="sxs-lookup"><span data-stu-id="53369-125">Table and column names are also listed within the Microsoft Defender Security Center, in the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="53369-126">表名</span><span class="sxs-lookup"><span data-stu-id="53369-126">Table name</span></span> | <span data-ttu-id="53369-127">说明</span><span class="sxs-lookup"><span data-stu-id="53369-127">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="53369-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span></span> | <span data-ttu-id="53369-129">Microsoft Defender 安全中心警报</span><span class="sxs-lookup"><span data-stu-id="53369-129">Alerts on Microsoft Defender Security Center</span></span> |
| <span data-ttu-id="53369-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="53369-131">设备信息，包括操作系统信息</span><span class="sxs-lookup"><span data-stu-id="53369-131">Device information, including OS information</span></span> |
| <span data-ttu-id="53369-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="53369-133">设备的网络属性，包括适配器、IP 和 MAC 地址，以及连接的网络和域</span><span class="sxs-lookup"><span data-stu-id="53369-133">Network properties of devices, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="53369-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="53369-135">过程创建和相关事件</span><span class="sxs-lookup"><span data-stu-id="53369-135">Process creation and related events</span></span> |
| <span data-ttu-id="53369-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="53369-137">网络连接和相关事件</span><span class="sxs-lookup"><span data-stu-id="53369-137">Network connection and related events</span></span> |
| <span data-ttu-id="53369-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="53369-139">文件创建、修改和其他文件系统事件</span><span class="sxs-lookup"><span data-stu-id="53369-139">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="53369-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="53369-141">创建和修改注册表项</span><span class="sxs-lookup"><span data-stu-id="53369-141">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="53369-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="53369-143">登录和其他身份验证事件</span><span class="sxs-lookup"><span data-stu-id="53369-143">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="53369-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="53369-145">DLL 加载事件</span><span class="sxs-lookup"><span data-stu-id="53369-145">DLL loading events</span></span> |
| <span data-ttu-id="53369-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="53369-147">多个事件类型，包括由安全控件（如 Microsoft Defender 防病毒和 Exploit Protection）触发的事件</span><span class="sxs-lookup"><span data-stu-id="53369-147">Multiple event types, including events triggered by security controls such as Microsoft Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="53369-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span></span> | <span data-ttu-id="53369-149">从终结点上的证书验证事件获取的已签名文件的证书信息</span><span class="sxs-lookup"><span data-stu-id="53369-149">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="53369-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span></span> | <span data-ttu-id="53369-151">设备上安装的软件清单，包括其版本信息和停止支持状态</span><span class="sxs-lookup"><span data-stu-id="53369-151">Inventory of software installed on devices, including their version information and end-of-support status</span></span> |
| <span data-ttu-id="53369-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span></span> | <span data-ttu-id="53369-153">在设备上发现的软件漏洞以及可解决每个漏洞的可用安全更新列表</span><span class="sxs-lookup"><span data-stu-id="53369-153">Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span> |
| <span data-ttu-id="53369-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span></span> | <span data-ttu-id="53369-155">公开披露的漏洞的知识库，包括攻击代码是否已公开</span><span class="sxs-lookup"><span data-stu-id="53369-155">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="53369-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span></span> | <span data-ttu-id="53369-157">威胁和漏洞管理评估事件，指示设备上的各种安全配置的状态</span><span class="sxs-lookup"><span data-stu-id="53369-157">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="53369-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="53369-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span></span> | <span data-ttu-id="53369-159">威胁和漏洞管理用于评估设备的各种安全配置的知识库；包括各种标准和基准的映射</span><span class="sxs-lookup"><span data-stu-id="53369-159">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span> |

>[!TIP]
><span data-ttu-id="53369-160">使用 [Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) 中的高级搜寻，使用来自 Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的数据搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="53369-160">Use [advanced hunting in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> [<span data-ttu-id="53369-161">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53369-161">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-enable)<br><br>
<span data-ttu-id="53369-162">在从 Microsoft Defender for Endpoint 迁移高级搜寻查询中，详细了解如何将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到 Microsoft 365 [Defender。](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)</span><span class="sxs-lookup"><span data-stu-id="53369-162">Learn more about how to move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).</span></span>

## <a name="related-topics"></a><span data-ttu-id="53369-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="53369-163">Related topics</span></span>
- [<span data-ttu-id="53369-164">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="53369-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="53369-165">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="53369-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="53369-166">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="53369-166">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="53369-167">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="53369-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="53369-168">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="53369-168">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="53369-169">高级搜寻数据架构更改</span><span class="sxs-lookup"><span data-stu-id="53369-169">Advanced hunting data schema changes</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
