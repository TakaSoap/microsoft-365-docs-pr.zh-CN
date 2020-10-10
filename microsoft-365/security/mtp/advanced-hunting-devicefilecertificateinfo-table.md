---
title: 高级搜寻架构中的 DeviceFileCertificateInfo 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfo 表中的文件签名信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、数字签名、证书、文件签名、DeviceFileCertificateInfo
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3c9ee14fc316f767ad57fe32920dd3034a1cd795
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412234"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="d86f4-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="d86f4-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d86f4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d86f4-105">**Applies to:**</span></span>
- <span data-ttu-id="d86f4-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="d86f4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d86f4-107">`DeviceFileCertificateInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关文件签名证书的信息。</span><span class="sxs-lookup"><span data-stu-id="d86f4-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d86f4-108">此表使用从证书验证活动获取的数据，这些数据定期对终结点上的文件执行。</span><span class="sxs-lookup"><span data-stu-id="d86f4-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d86f4-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d86f4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d86f4-110">列名称</span><span class="sxs-lookup"><span data-stu-id="d86f4-110">Column name</span></span> | <span data-ttu-id="d86f4-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="d86f4-111">Data type</span></span> | <span data-ttu-id="d86f4-112">说明</span><span class="sxs-lookup"><span data-stu-id="d86f4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d86f4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d86f4-113">datetime</span></span> | <span data-ttu-id="d86f4-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d86f4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d86f4-115">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-115">string</span></span> | <span data-ttu-id="d86f4-116">服务中的计算机的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="d86f4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d86f4-117">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-117">string</span></span> | <span data-ttu-id="d86f4-118">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d86f4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="d86f4-119">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-119">string</span></span> | <span data-ttu-id="d86f4-120">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="d86f4-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d86f4-121">boolean</span><span class="sxs-lookup"><span data-stu-id="d86f4-121">boolean</span></span> | <span data-ttu-id="d86f4-122">指示文件是否已签名</span><span class="sxs-lookup"><span data-stu-id="d86f4-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d86f4-123">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-123">string</span></span> | <span data-ttu-id="d86f4-124">指示是否已将签名信息作为文件本身的嵌入内容读取或从外部目录文件读取</span><span class="sxs-lookup"><span data-stu-id="d86f4-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d86f4-125">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-125">string</span></span> | <span data-ttu-id="d86f4-126">有关文件签名者的信息</span><span class="sxs-lookup"><span data-stu-id="d86f4-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d86f4-127">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-127">string</span></span> | <span data-ttu-id="d86f4-128">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="d86f4-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d86f4-129">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-129">string</span></span> | <span data-ttu-id="d86f4-130">有关颁发证书颁发机构 (CA) 的信息</span><span class="sxs-lookup"><span data-stu-id="d86f4-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d86f4-131">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-131">string</span></span> | <span data-ttu-id="d86f4-132">标识颁发证书颁发机构 (CA) 的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="d86f4-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d86f4-133">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-133">string</span></span> | <span data-ttu-id="d86f4-134">颁发证书颁发机构 (CA 的唯一证书的标识符) </span><span class="sxs-lookup"><span data-stu-id="d86f4-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d86f4-135">string</span><span class="sxs-lookup"><span data-stu-id="d86f4-135">string</span></span> |  <span data-ttu-id="d86f4-136">JSON 数组，列出包含证书和证书吊销列表 (Crl 的网络共享的 Url) </span><span class="sxs-lookup"><span data-stu-id="d86f4-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d86f4-137">datetime</span><span class="sxs-lookup"><span data-stu-id="d86f4-137">datetime</span></span> | <span data-ttu-id="d86f4-138">证书的创建日期和时间</span><span class="sxs-lookup"><span data-stu-id="d86f4-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d86f4-139">datetime</span><span class="sxs-lookup"><span data-stu-id="d86f4-139">datetime</span></span> | <span data-ttu-id="d86f4-140">将证书设置为过期的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d86f4-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d86f4-141">datetime</span><span class="sxs-lookup"><span data-stu-id="d86f4-141">datetime</span></span> | <span data-ttu-id="d86f4-142">副署证书的日期和时间</span><span class="sxs-lookup"><span data-stu-id="d86f4-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d86f4-143">boolean</span><span class="sxs-lookup"><span data-stu-id="d86f4-143">boolean</span></span> | <span data-ttu-id="d86f4-144">指示文件是否受 WinVerifyTrust 函数的结果（检查未知的根证书信息、无效签名、吊销的证书以及其他可疑属性）的信任。</span><span class="sxs-lookup"><span data-stu-id="d86f4-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d86f4-145">boolean</span><span class="sxs-lookup"><span data-stu-id="d86f4-145">boolean</span></span> | <span data-ttu-id="d86f4-146">指示根证书的签名者是否为 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d86f4-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d86f4-147">long</span><span class="sxs-lookup"><span data-stu-id="d86f4-147">long</span></span> | <span data-ttu-id="d86f4-148">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="d86f4-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d86f4-149">若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用。</span><span class="sxs-lookup"><span data-stu-id="d86f4-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="d86f4-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="d86f4-150">Related topics</span></span>
- [<span data-ttu-id="d86f4-151">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d86f4-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d86f4-152">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d86f4-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d86f4-153">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d86f4-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d86f4-154">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="d86f4-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d86f4-155">了解架构</span><span class="sxs-lookup"><span data-stu-id="d86f4-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d86f4-156">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d86f4-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
