---
title: 高级搜寻架构中的 DeviceFileCertificateInfo 表
description: 了解高级搜寻架构的 DeviceFileCertificateInfo 表中的文件签名信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 数字签名， 证书， 文件签名， DeviceFileCertificateInfo
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
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499171"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="07651-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="07651-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07651-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="07651-105">**Applies to:**</span></span>
- [<span data-ttu-id="07651-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="07651-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="07651-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="07651-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="07651-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="07651-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="07651-109">高级 `DeviceFileCertificateInfo` 搜寻架构 [中的](advanced-hunting-overview.md) 表包含有关文件签名证书的信息。</span><span class="sxs-lookup"><span data-stu-id="07651-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="07651-110">此表使用定期对终结点上的文件执行的证书验证活动获取的数据。</span><span class="sxs-lookup"><span data-stu-id="07651-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="07651-111">有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="07651-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="07651-112">列名称</span><span class="sxs-lookup"><span data-stu-id="07651-112">Column name</span></span> | <span data-ttu-id="07651-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="07651-113">Data type</span></span> | <span data-ttu-id="07651-114">说明</span><span class="sxs-lookup"><span data-stu-id="07651-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="07651-115">datetime</span><span class="sxs-lookup"><span data-stu-id="07651-115">datetime</span></span> | <span data-ttu-id="07651-116">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="07651-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="07651-117">string</span><span class="sxs-lookup"><span data-stu-id="07651-117">string</span></span> | <span data-ttu-id="07651-118">服务中设备的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="07651-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="07651-119">string</span><span class="sxs-lookup"><span data-stu-id="07651-119">string</span></span> | <span data-ttu-id="07651-120">设备的完全限定 (FQDN) FQDN</span><span class="sxs-lookup"><span data-stu-id="07651-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="07651-121">string</span><span class="sxs-lookup"><span data-stu-id="07651-121">string</span></span> | <span data-ttu-id="07651-122">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="07651-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="07651-123">boolean</span><span class="sxs-lookup"><span data-stu-id="07651-123">boolean</span></span> | <span data-ttu-id="07651-124">指示文件是否已签名</span><span class="sxs-lookup"><span data-stu-id="07651-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="07651-125">string</span><span class="sxs-lookup"><span data-stu-id="07651-125">string</span></span> | <span data-ttu-id="07651-126">指示签名信息是作为嵌入内容读取到文件本身中，还是从外部目录文件中读取</span><span class="sxs-lookup"><span data-stu-id="07651-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="07651-127">string</span><span class="sxs-lookup"><span data-stu-id="07651-127">string</span></span> | <span data-ttu-id="07651-128">有关文件签名者的信息</span><span class="sxs-lookup"><span data-stu-id="07651-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="07651-129">string</span><span class="sxs-lookup"><span data-stu-id="07651-129">string</span></span> | <span data-ttu-id="07651-130">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="07651-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="07651-131">string</span><span class="sxs-lookup"><span data-stu-id="07651-131">string</span></span> | <span data-ttu-id="07651-132">有关 CA 证书颁发机构 (的信息) </span><span class="sxs-lookup"><span data-stu-id="07651-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="07651-133">string</span><span class="sxs-lookup"><span data-stu-id="07651-133">string</span></span> | <span data-ttu-id="07651-134">标识证书颁发机构的唯一哈希值 (CA) </span><span class="sxs-lookup"><span data-stu-id="07651-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="07651-135">string</span><span class="sxs-lookup"><span data-stu-id="07651-135">string</span></span> | <span data-ttu-id="07651-136">证书颁发机构或 CA 证书颁发机构唯一的 (标识符) </span><span class="sxs-lookup"><span data-stu-id="07651-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="07651-137">string</span><span class="sxs-lookup"><span data-stu-id="07651-137">string</span></span> |  <span data-ttu-id="07651-138">JSON 数组，列出包含证书的网络共享 URL 和 CCL 或证书吊销 (列表) </span><span class="sxs-lookup"><span data-stu-id="07651-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="07651-139">datetime</span><span class="sxs-lookup"><span data-stu-id="07651-139">datetime</span></span> | <span data-ttu-id="07651-140">创建证书的日期和时间</span><span class="sxs-lookup"><span data-stu-id="07651-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="07651-141">datetime</span><span class="sxs-lookup"><span data-stu-id="07651-141">datetime</span></span> | <span data-ttu-id="07651-142">证书设置为过期的日期和时间</span><span class="sxs-lookup"><span data-stu-id="07651-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="07651-143">datetime</span><span class="sxs-lookup"><span data-stu-id="07651-143">datetime</span></span> | <span data-ttu-id="07651-144">对证书进行反签名的日期和时间</span><span class="sxs-lookup"><span data-stu-id="07651-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="07651-145">boolean</span><span class="sxs-lookup"><span data-stu-id="07651-145">boolean</span></span> | <span data-ttu-id="07651-146">根据 WinVerifyTrust 函数的结果指示文件是否受信任，该函数将检查未知根证书信息、无效签名、吊销的证书和其他可怀疑的属性</span><span class="sxs-lookup"><span data-stu-id="07651-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="07651-147">boolean</span><span class="sxs-lookup"><span data-stu-id="07651-147">boolean</span></span> | <span data-ttu-id="07651-148">指示根证书的签名者是否是 Microsoft</span><span class="sxs-lookup"><span data-stu-id="07651-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="07651-149">long</span><span class="sxs-lookup"><span data-stu-id="07651-149">long</span></span> | <span data-ttu-id="07651-150">基于重复计数器的事件标识符。</span><span class="sxs-lookup"><span data-stu-id="07651-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="07651-151">若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用。</span><span class="sxs-lookup"><span data-stu-id="07651-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="07651-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="07651-152">Related topics</span></span>
- [<span data-ttu-id="07651-153">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="07651-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07651-154">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="07651-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="07651-155">了解架构</span><span class="sxs-lookup"><span data-stu-id="07651-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
