---
title: 高级搜寻架构中的 DeviceFileCertificateInfo 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfo 表中的文件签名信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 数字签名， 证书， 文件签名， DeviceFileCertificateInfo
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931310"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="cc00a-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="cc00a-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cc00a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="cc00a-105">**Applies to:**</span></span>
- <span data-ttu-id="cc00a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc00a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cc00a-107">高级 `DeviceFileCertificateInfo` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关文件签名证书的信息。</span><span class="sxs-lookup"><span data-stu-id="cc00a-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="cc00a-108">此表使用定期对终结点上的文件执行的证书验证活动获取的数据。</span><span class="sxs-lookup"><span data-stu-id="cc00a-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="cc00a-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="cc00a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cc00a-110">列名称</span><span class="sxs-lookup"><span data-stu-id="cc00a-110">Column name</span></span> | <span data-ttu-id="cc00a-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="cc00a-111">Data type</span></span> | <span data-ttu-id="cc00a-112">说明</span><span class="sxs-lookup"><span data-stu-id="cc00a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cc00a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cc00a-113">datetime</span></span> | <span data-ttu-id="cc00a-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="cc00a-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="cc00a-115">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-115">string</span></span> | <span data-ttu-id="cc00a-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="cc00a-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="cc00a-117">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-117">string</span></span> | <span data-ttu-id="cc00a-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cc00a-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="cc00a-119">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-119">string</span></span> | <span data-ttu-id="cc00a-120">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="cc00a-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="cc00a-121">boolean</span><span class="sxs-lookup"><span data-stu-id="cc00a-121">boolean</span></span> | <span data-ttu-id="cc00a-122">指示文件是否已签名</span><span class="sxs-lookup"><span data-stu-id="cc00a-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="cc00a-123">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-123">string</span></span> | <span data-ttu-id="cc00a-124">指示签名信息是作为嵌入内容读取到文件本身中，还是从外部目录文件中读取</span><span class="sxs-lookup"><span data-stu-id="cc00a-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="cc00a-125">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-125">string</span></span> | <span data-ttu-id="cc00a-126">有关文件签署人的信息</span><span class="sxs-lookup"><span data-stu-id="cc00a-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="cc00a-127">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-127">string</span></span> | <span data-ttu-id="cc00a-128">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="cc00a-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="cc00a-129">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-129">string</span></span> | <span data-ttu-id="cc00a-130">有关 CA 证书颁发机构 (的信息) </span><span class="sxs-lookup"><span data-stu-id="cc00a-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="cc00a-131">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-131">string</span></span> | <span data-ttu-id="cc00a-132">标识证书颁发机构的唯一哈希值 (CA) </span><span class="sxs-lookup"><span data-stu-id="cc00a-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="cc00a-133">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-133">string</span></span> | <span data-ttu-id="cc00a-134">CA 证书颁发机构唯一的证书 (标识符) </span><span class="sxs-lookup"><span data-stu-id="cc00a-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="cc00a-135">string</span><span class="sxs-lookup"><span data-stu-id="cc00a-135">string</span></span> |  <span data-ttu-id="cc00a-136">列出网络共享 URL 的 JSON 数组，其中包含证书和证书吊销列表 (CCL) </span><span class="sxs-lookup"><span data-stu-id="cc00a-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="cc00a-137">datetime</span><span class="sxs-lookup"><span data-stu-id="cc00a-137">datetime</span></span> | <span data-ttu-id="cc00a-138">创建证书的日期和时间</span><span class="sxs-lookup"><span data-stu-id="cc00a-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="cc00a-139">datetime</span><span class="sxs-lookup"><span data-stu-id="cc00a-139">datetime</span></span> | <span data-ttu-id="cc00a-140">将证书设置为过期的日期和时间</span><span class="sxs-lookup"><span data-stu-id="cc00a-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="cc00a-141">datetime</span><span class="sxs-lookup"><span data-stu-id="cc00a-141">datetime</span></span> | <span data-ttu-id="cc00a-142">对证书进行反签名的日期和时间</span><span class="sxs-lookup"><span data-stu-id="cc00a-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="cc00a-143">boolean</span><span class="sxs-lookup"><span data-stu-id="cc00a-143">boolean</span></span> | <span data-ttu-id="cc00a-144">根据 WinVerifyTrust 函数的结果指示文件是否受信任，该函数将检查未知根证书信息、无效签名、吊销的证书和其他疑问的属性</span><span class="sxs-lookup"><span data-stu-id="cc00a-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="cc00a-145">boolean</span><span class="sxs-lookup"><span data-stu-id="cc00a-145">boolean</span></span> | <span data-ttu-id="cc00a-146">指示根证书的签名者是否是 Microsoft</span><span class="sxs-lookup"><span data-stu-id="cc00a-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="cc00a-147">long</span><span class="sxs-lookup"><span data-stu-id="cc00a-147">long</span></span> | <span data-ttu-id="cc00a-148">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="cc00a-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="cc00a-149">若要标识唯一事件，必须将此列与 DeviceName 和时间戳列结合使用。</span><span class="sxs-lookup"><span data-stu-id="cc00a-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="cc00a-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="cc00a-150">Related topics</span></span>
- [<span data-ttu-id="cc00a-151">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="cc00a-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cc00a-152">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="cc00a-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cc00a-153">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="cc00a-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cc00a-154">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="cc00a-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cc00a-155">了解架构</span><span class="sxs-lookup"><span data-stu-id="cc00a-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cc00a-156">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="cc00a-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
