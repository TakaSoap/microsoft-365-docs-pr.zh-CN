---
title: 高级搜寻架构中的 AlertEvidence 表
description: 了解与高级搜寻架构的 AlertEvidence 表中的警报关联的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 说明， AlertInfo， 警报， 实体， 证据， 文件， IP 地址， 设备， 计算机， 用户， 帐户
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
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932579"
---
# <a name="alertevidence"></a><span data-ttu-id="65e9d-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="65e9d-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65e9d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="65e9d-105">**Applies to:**</span></span>
- <span data-ttu-id="65e9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65e9d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="65e9d-107">高级搜寻架构中的表包含与 `AlertEvidence` 来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的警报关联的各种实体（文件、IP 地址[](advanced-hunting-overview.md)、URL、用户或设备）的信息。</span><span class="sxs-lookup"><span data-stu-id="65e9d-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="65e9d-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="65e9d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="65e9d-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="65e9d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="65e9d-110">列名称</span><span class="sxs-lookup"><span data-stu-id="65e9d-110">Column name</span></span> | <span data-ttu-id="65e9d-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="65e9d-111">Data type</span></span> | <span data-ttu-id="65e9d-112">说明</span><span class="sxs-lookup"><span data-stu-id="65e9d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="65e9d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="65e9d-113">datetime</span></span> | <span data-ttu-id="65e9d-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="65e9d-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="65e9d-115">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-115">string</span></span> | <span data-ttu-id="65e9d-116">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="65e9d-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="65e9d-117">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-117">string</span></span> | <span data-ttu-id="65e9d-118">提供警报信息的产品或服务</span><span class="sxs-lookup"><span data-stu-id="65e9d-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="65e9d-119">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-119">string</span></span> | <span data-ttu-id="65e9d-120">对象类型，例如文件、进程、设备或用户</span><span class="sxs-lookup"><span data-stu-id="65e9d-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="65e9d-121">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-121">string</span></span> | <span data-ttu-id="65e9d-122">如何在警报中涉及实体，以指示它是否受到影响或只是相关</span><span class="sxs-lookup"><span data-stu-id="65e9d-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="65e9d-123">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-123">string</span></span> | <span data-ttu-id="65e9d-124">指示实体是网络连接的来源还是目标</span><span class="sxs-lookup"><span data-stu-id="65e9d-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="65e9d-125">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-125">string</span></span> | <span data-ttu-id="65e9d-126">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="65e9d-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="65e9d-127">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-127">string</span></span> | <span data-ttu-id="65e9d-128">包含已记录操作所应用到的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="65e9d-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="65e9d-129">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-129">string</span></span> | <span data-ttu-id="65e9d-130">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="65e9d-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="65e9d-131">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-131">string</span></span> | <span data-ttu-id="65e9d-132">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="65e9d-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="65e9d-133">通常不填充此字段 -使用 SHA1 列（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="65e9d-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="65e9d-134">int</span><span class="sxs-lookup"><span data-stu-id="65e9d-134">int</span></span> | <span data-ttu-id="65e9d-135">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="65e9d-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="65e9d-136">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-136">string</span></span> | <span data-ttu-id="65e9d-137">可疑或恶意文件或进程的分类依据的恶意软件系列</span><span class="sxs-lookup"><span data-stu-id="65e9d-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="65e9d-138">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-138">string</span></span> | <span data-ttu-id="65e9d-139">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="65e9d-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="65e9d-140">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-140">string</span></span> | <span data-ttu-id="65e9d-141">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="65e9d-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="65e9d-142">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-142">string</span></span> | <span data-ttu-id="65e9d-143">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="65e9d-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="65e9d-144">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-144">string</span></span> | <span data-ttu-id="65e9d-145">帐户的域</span><span class="sxs-lookup"><span data-stu-id="65e9d-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="65e9d-146">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-146">string</span></span> | <span data-ttu-id="65e9d-147">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="65e9d-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="65e9d-148">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-148">string</span></span> | <span data-ttu-id="65e9d-149">Azure Active Directory 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="65e9d-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="65e9d-150">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-150">string</span></span> | <span data-ttu-id="65e9d-151">帐户 (UPN) 用户主体名称</span><span class="sxs-lookup"><span data-stu-id="65e9d-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="65e9d-152">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-152">string</span></span> | <span data-ttu-id="65e9d-153">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="65e9d-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="65e9d-154">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-154">string</span></span> | <span data-ttu-id="65e9d-155">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="65e9d-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="65e9d-156">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-156">string</span></span> | <span data-ttu-id="65e9d-157">分配给通信期间使用的本地设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="65e9d-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="65e9d-158">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-158">string</span></span> | <span data-ttu-id="65e9d-159">由 Office 365 生成的电子邮件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="65e9d-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="65e9d-160">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-160">string</span></span> | <span data-ttu-id="65e9d-161">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="65e9d-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="65e9d-162">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-162">string</span></span> | <span data-ttu-id="65e9d-163">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="65e9d-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="65e9d-164">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-164">string</span></span> | <span data-ttu-id="65e9d-165">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="65e9d-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="65e9d-166">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-166">string</span></span> | <span data-ttu-id="65e9d-167">用于创建新过程的命令行</span><span class="sxs-lookup"><span data-stu-id="65e9d-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="65e9d-168">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-168">string</span></span> | <span data-ttu-id="65e9d-169">有关 JSON 数组格式的事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="65e9d-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="65e9d-170">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-170">string</span></span> | <span data-ttu-id="65e9d-171">已记录操作所应用到的注册表项</span><span class="sxs-lookup"><span data-stu-id="65e9d-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="65e9d-172">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-172">string</span></span> | <span data-ttu-id="65e9d-173">已记录操作所应用到的注册表值的名称</span><span class="sxs-lookup"><span data-stu-id="65e9d-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="65e9d-174">string</span><span class="sxs-lookup"><span data-stu-id="65e9d-174">string</span></span> | <span data-ttu-id="65e9d-175">已记录操作应用于的注册表值的数据</span><span class="sxs-lookup"><span data-stu-id="65e9d-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="65e9d-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="65e9d-176">Related topics</span></span>
- [<span data-ttu-id="65e9d-177">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="65e9d-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65e9d-178">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="65e9d-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65e9d-179">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="65e9d-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65e9d-180">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="65e9d-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="65e9d-181">了解架构</span><span class="sxs-lookup"><span data-stu-id="65e9d-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65e9d-182">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="65e9d-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
