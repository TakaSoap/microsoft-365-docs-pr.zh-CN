---
title: 高级搜寻架构中的 DeviceFileCertificateInfo 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfo 表中的文件签名信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 数字签名， 证书， 文件签名， DeviceFileCertificateInfo
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
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055277"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="66c5b-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="66c5b-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66c5b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="66c5b-105">**Applies to:**</span></span>
- <span data-ttu-id="66c5b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66c5b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="66c5b-107">高级 `DeviceFileCertificateInfo` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关文件签名证书的信息。</span><span class="sxs-lookup"><span data-stu-id="66c5b-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="66c5b-108">此表使用定期对终结点上的文件执行的证书验证活动获取的数据。</span><span class="sxs-lookup"><span data-stu-id="66c5b-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="66c5b-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="66c5b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="66c5b-110">列名称</span><span class="sxs-lookup"><span data-stu-id="66c5b-110">Column name</span></span> | <span data-ttu-id="66c5b-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="66c5b-111">Data type</span></span> | <span data-ttu-id="66c5b-112">说明</span><span class="sxs-lookup"><span data-stu-id="66c5b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="66c5b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="66c5b-113">datetime</span></span> | <span data-ttu-id="66c5b-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="66c5b-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="66c5b-115">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-115">string</span></span> | <span data-ttu-id="66c5b-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="66c5b-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="66c5b-117">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-117">string</span></span> | <span data-ttu-id="66c5b-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="66c5b-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="66c5b-119">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-119">string</span></span> | <span data-ttu-id="66c5b-120">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="66c5b-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="66c5b-121">boolean</span><span class="sxs-lookup"><span data-stu-id="66c5b-121">boolean</span></span> | <span data-ttu-id="66c5b-122">指示文件是否已签名</span><span class="sxs-lookup"><span data-stu-id="66c5b-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="66c5b-123">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-123">string</span></span> | <span data-ttu-id="66c5b-124">指示签名信息是作为嵌入内容读取到文件本身中，还是从外部目录文件中读取</span><span class="sxs-lookup"><span data-stu-id="66c5b-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="66c5b-125">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-125">string</span></span> | <span data-ttu-id="66c5b-126">有关文件签名者的信息</span><span class="sxs-lookup"><span data-stu-id="66c5b-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="66c5b-127">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-127">string</span></span> | <span data-ttu-id="66c5b-128">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="66c5b-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="66c5b-129">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-129">string</span></span> | <span data-ttu-id="66c5b-130">有关 CA 证书颁发机构 (的信息) </span><span class="sxs-lookup"><span data-stu-id="66c5b-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="66c5b-131">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-131">string</span></span> | <span data-ttu-id="66c5b-132">标识证书颁发机构的唯一哈希值 (CA) </span><span class="sxs-lookup"><span data-stu-id="66c5b-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="66c5b-133">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-133">string</span></span> | <span data-ttu-id="66c5b-134">证书颁发机构或 CA 证书颁发机构唯一的 (标识符) </span><span class="sxs-lookup"><span data-stu-id="66c5b-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="66c5b-135">string</span><span class="sxs-lookup"><span data-stu-id="66c5b-135">string</span></span> |  <span data-ttu-id="66c5b-136">JSON 数组，列出包含证书的网络共享 URL 和 CCL 或证书吊销 (列表) </span><span class="sxs-lookup"><span data-stu-id="66c5b-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="66c5b-137">datetime</span><span class="sxs-lookup"><span data-stu-id="66c5b-137">datetime</span></span> | <span data-ttu-id="66c5b-138">创建证书的日期和时间</span><span class="sxs-lookup"><span data-stu-id="66c5b-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="66c5b-139">datetime</span><span class="sxs-lookup"><span data-stu-id="66c5b-139">datetime</span></span> | <span data-ttu-id="66c5b-140">证书设置为过期的日期和时间</span><span class="sxs-lookup"><span data-stu-id="66c5b-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="66c5b-141">datetime</span><span class="sxs-lookup"><span data-stu-id="66c5b-141">datetime</span></span> | <span data-ttu-id="66c5b-142">对证书进行反签名的日期和时间</span><span class="sxs-lookup"><span data-stu-id="66c5b-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="66c5b-143">boolean</span><span class="sxs-lookup"><span data-stu-id="66c5b-143">boolean</span></span> | <span data-ttu-id="66c5b-144">根据 WinVerifyTrust 函数的结果指示文件是否受信任，该函数将检查未知根证书信息、无效签名、吊销的证书和其他可怀疑的属性</span><span class="sxs-lookup"><span data-stu-id="66c5b-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="66c5b-145">boolean</span><span class="sxs-lookup"><span data-stu-id="66c5b-145">boolean</span></span> | <span data-ttu-id="66c5b-146">指示根证书的签名者是否是 Microsoft</span><span class="sxs-lookup"><span data-stu-id="66c5b-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="66c5b-147">long</span><span class="sxs-lookup"><span data-stu-id="66c5b-147">long</span></span> | <span data-ttu-id="66c5b-148">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="66c5b-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="66c5b-149">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。</span><span class="sxs-lookup"><span data-stu-id="66c5b-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="66c5b-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="66c5b-150">Related topics</span></span>
- [<span data-ttu-id="66c5b-151">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="66c5b-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="66c5b-152">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="66c5b-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="66c5b-153">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="66c5b-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="66c5b-154">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="66c5b-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="66c5b-155">了解架构</span><span class="sxs-lookup"><span data-stu-id="66c5b-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="66c5b-156">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="66c5b-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
