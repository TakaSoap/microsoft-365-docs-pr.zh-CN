---
title: 高级搜寻架构中的 AlertEvidence 表
description: 了解与高级搜寻架构的 AlertEvidence 表中的通知关联的信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、AlertInfo、设备、实体、证据、文件、IP 地址、设备、计算机、用户、帐户
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430159"
---
# <a name="alertevidence"></a><span data-ttu-id="79c6f-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="79c6f-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="79c6f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="79c6f-105">**Applies to:**</span></span>
- <span data-ttu-id="79c6f-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="79c6f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="79c6f-107">`AlertEvidence`[高级搜寻](advanced-hunting-overview.md)架构中的表格包含有关各种实体（文件、IP 地址、url、用户或设备）的信息，这些信息与 Microsoft Defender ATP、Office 365 ATP、Microsoft 云应用安全性和 Azure atp 中的警报相关联。</span><span class="sxs-lookup"><span data-stu-id="79c6f-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="79c6f-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="79c6f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="79c6f-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="79c6f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="79c6f-110">列名称</span><span class="sxs-lookup"><span data-stu-id="79c6f-110">Column name</span></span> | <span data-ttu-id="79c6f-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="79c6f-111">Data type</span></span> | <span data-ttu-id="79c6f-112">说明</span><span class="sxs-lookup"><span data-stu-id="79c6f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="79c6f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="79c6f-113">datetime</span></span> | <span data-ttu-id="79c6f-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="79c6f-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="79c6f-115">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-115">string</span></span> | <span data-ttu-id="79c6f-116">警报的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="79c6f-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="79c6f-117">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-117">string</span></span> | <span data-ttu-id="79c6f-118">提供通知信息的产品或服务</span><span class="sxs-lookup"><span data-stu-id="79c6f-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="79c6f-119">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-119">string</span></span> | <span data-ttu-id="79c6f-120">对象的类型，如文件、进程、设备或用户</span><span class="sxs-lookup"><span data-stu-id="79c6f-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="79c6f-121">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-121">string</span></span> | <span data-ttu-id="79c6f-122">如何将实体包含在警报中，以指示它是受影响的还是只是相关的</span><span class="sxs-lookup"><span data-stu-id="79c6f-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="79c6f-123">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-123">string</span></span> | <span data-ttu-id="79c6f-124">指示实体是否为网络连接的源或目标</span><span class="sxs-lookup"><span data-stu-id="79c6f-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="79c6f-125">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-125">string</span></span> | <span data-ttu-id="79c6f-126">录制操作所应用到的文件的名称</span><span class="sxs-lookup"><span data-stu-id="79c6f-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="79c6f-127">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-127">string</span></span> | <span data-ttu-id="79c6f-128">包含录制的操作所应用于的文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="79c6f-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="79c6f-129">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-129">string</span></span> | <span data-ttu-id="79c6f-130">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="79c6f-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="79c6f-131">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-131">string</span></span> | <span data-ttu-id="79c6f-132">录制操作所应用到的文件的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="79c6f-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="79c6f-133">通常不填充此字段—使用 SHA1 列（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="79c6f-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="79c6f-134">int</span><span class="sxs-lookup"><span data-stu-id="79c6f-134">int</span></span> | <span data-ttu-id="79c6f-135">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="79c6f-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="79c6f-136">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-136">string</span></span> | <span data-ttu-id="79c6f-137">已在其下对可疑或恶意文件或流程进行了分类的恶意软件系列</span><span class="sxs-lookup"><span data-stu-id="79c6f-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="79c6f-138">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-138">string</span></span> | <span data-ttu-id="79c6f-139">连接到的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="79c6f-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="79c6f-140">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-140">string</span></span> | <span data-ttu-id="79c6f-141">连接到的 URL 或完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="79c6f-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="79c6f-142">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-142">string</span></span> | <span data-ttu-id="79c6f-143">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="79c6f-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="79c6f-144">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-144">string</span></span> | <span data-ttu-id="79c6f-145">帐户的域</span><span class="sxs-lookup"><span data-stu-id="79c6f-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="79c6f-146">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-146">string</span></span> | <span data-ttu-id="79c6f-147">帐户的安全标识符 (SID) </span><span class="sxs-lookup"><span data-stu-id="79c6f-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="79c6f-148">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-148">string</span></span> | <span data-ttu-id="79c6f-149">Azure Active Directory 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="79c6f-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="79c6f-150">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-150">string</span></span> | <span data-ttu-id="79c6f-151">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="79c6f-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="79c6f-152">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-152">string</span></span> | <span data-ttu-id="79c6f-153">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="79c6f-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="79c6f-154">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-154">string</span></span> | <span data-ttu-id="79c6f-155">分配给在通信期间使用的本地设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="79c6f-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="79c6f-156">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-156">string</span></span> | <span data-ttu-id="79c6f-157">由 Office 365 生成的电子邮件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="79c6f-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="79c6f-158">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-158">string</span></span> | <span data-ttu-id="79c6f-159">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="79c6f-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="79c6f-160">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-160">string</span></span> | <span data-ttu-id="79c6f-161">应用程序的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="79c6f-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="79c6f-162">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-162">string</span></span> | <span data-ttu-id="79c6f-163">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="79c6f-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="79c6f-164">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-164">string</span></span> | <span data-ttu-id="79c6f-165">用于创建新进程的命令行</span><span class="sxs-lookup"><span data-stu-id="79c6f-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="79c6f-166">string</span><span class="sxs-lookup"><span data-stu-id="79c6f-166">string</span></span> | <span data-ttu-id="79c6f-167">有关 JSON 数组格式事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="79c6f-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="79c6f-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="79c6f-168">Related topics</span></span>
- [<span data-ttu-id="79c6f-169">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="79c6f-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="79c6f-170">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="79c6f-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="79c6f-171">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="79c6f-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="79c6f-172">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="79c6f-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="79c6f-173">了解架构</span><span class="sxs-lookup"><span data-stu-id="79c6f-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="79c6f-174">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="79c6f-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
