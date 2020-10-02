---
title: 'Microsoft 威胁防护中的 FileProfile ( # A1 函数在高级搜寻中'
description: '了解如何使用 FileProfile ( # A1 丰富有关高级搜索查询结果中的文件的信息'
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、FileProfile、文件配置文件、函数、扩充
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
ms.openlocfilehash: 6d627dcf3d6ec8ca1d2aa76eab484361c25b529e
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338413"
---
# <a name="fileprofile"></a><span data-ttu-id="e7127-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="e7127-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e7127-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e7127-105">**Applies to:**</span></span>
- <span data-ttu-id="e7127-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="e7127-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e7127-107">`FileProfile()`函数是[高级](advanced-hunting-overview.md)搜索中的一个扩充函数，可将以下数据添加到查询找到的文件中。</span><span class="sxs-lookup"><span data-stu-id="e7127-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="e7127-108">列</span><span class="sxs-lookup"><span data-stu-id="e7127-108">Column</span></span> | <span data-ttu-id="e7127-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="e7127-109">Data type</span></span> | <span data-ttu-id="e7127-110">说明</span><span class="sxs-lookup"><span data-stu-id="e7127-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="e7127-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="e7127-111">SHA1</span></span> | <span data-ttu-id="e7127-112">string</span><span class="sxs-lookup"><span data-stu-id="e7127-112">string</span></span> | <span data-ttu-id="e7127-113">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="e7127-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e7127-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="e7127-114">SHA256</span></span> | <span data-ttu-id="e7127-115">string</span><span class="sxs-lookup"><span data-stu-id="e7127-115">string</span></span> | <span data-ttu-id="e7127-116">将所录制操作应用于的文件的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="e7127-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e7127-117">MD5</span><span class="sxs-lookup"><span data-stu-id="e7127-117">MD5</span></span> | <span data-ttu-id="e7127-118">string</span><span class="sxs-lookup"><span data-stu-id="e7127-118">string</span></span> | <span data-ttu-id="e7127-119">将录制的操作应用于的文件的 MD5 哈希值</span><span class="sxs-lookup"><span data-stu-id="e7127-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="e7127-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="e7127-120">FileSize</span></span> | <span data-ttu-id="e7127-121">int</span><span class="sxs-lookup"><span data-stu-id="e7127-121">int</span></span> | <span data-ttu-id="e7127-122">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="e7127-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="e7127-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="e7127-123">GlobalPrevalence</span></span> | <span data-ttu-id="e7127-124">int</span><span class="sxs-lookup"><span data-stu-id="e7127-124">int</span></span> | <span data-ttu-id="e7127-125">由 Microsoft 全局监视的实体的实例数</span><span class="sxs-lookup"><span data-stu-id="e7127-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="e7127-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="e7127-126">GlobalFirstSeen</span></span> | <span data-ttu-id="e7127-127">datetime</span><span class="sxs-lookup"><span data-stu-id="e7127-127">datetime</span></span> | <span data-ttu-id="e7127-128">Microsoft 全球首次观测实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="e7127-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="e7127-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="e7127-129">GlobalLastSeen</span></span> | <span data-ttu-id="e7127-130">datetime</span><span class="sxs-lookup"><span data-stu-id="e7127-130">datetime</span></span> | <span data-ttu-id="e7127-131">上次 Microsoft 全局观察实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="e7127-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="e7127-132">签字</span><span class="sxs-lookup"><span data-stu-id="e7127-132">Signer</span></span> | <span data-ttu-id="e7127-133">string</span><span class="sxs-lookup"><span data-stu-id="e7127-133">string</span></span> | <span data-ttu-id="e7127-134">有关文件签名者的信息</span><span class="sxs-lookup"><span data-stu-id="e7127-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="e7127-135">颁发者</span><span class="sxs-lookup"><span data-stu-id="e7127-135">Issuer</span></span> | <span data-ttu-id="e7127-136">string</span><span class="sxs-lookup"><span data-stu-id="e7127-136">string</span></span> | <span data-ttu-id="e7127-137">有关颁发证书颁发机构 (CA) 的信息</span><span class="sxs-lookup"><span data-stu-id="e7127-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="e7127-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="e7127-138">SignerHash</span></span> | <span data-ttu-id="e7127-139">string</span><span class="sxs-lookup"><span data-stu-id="e7127-139">string</span></span> | <span data-ttu-id="e7127-140">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="e7127-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="e7127-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="e7127-141">IsCertificateValid</span></span> | <span data-ttu-id="e7127-142">boolean</span><span class="sxs-lookup"><span data-stu-id="e7127-142">boolean</span></span> | <span data-ttu-id="e7127-143">用于对文件进行签名的证书是否有效</span><span class="sxs-lookup"><span data-stu-id="e7127-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="e7127-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="e7127-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="e7127-145">boolean</span><span class="sxs-lookup"><span data-stu-id="e7127-145">boolean</span></span> | <span data-ttu-id="e7127-146">指示根证书的签名者是否为 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7127-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="e7127-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="e7127-147">IsExecutable</span></span> | <span data-ttu-id="e7127-148">boolean</span><span class="sxs-lookup"><span data-stu-id="e7127-148">boolean</span></span> | <span data-ttu-id="e7127-149">文件是否为可移植可执行文件 (PE) 文件</span><span class="sxs-lookup"><span data-stu-id="e7127-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="e7127-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="e7127-150">ThreatName</span></span> | <span data-ttu-id="e7127-151">string</span><span class="sxs-lookup"><span data-stu-id="e7127-151">string</span></span> | <span data-ttu-id="e7127-152">发现的任何恶意软件或其他威胁的检测名称</span><span class="sxs-lookup"><span data-stu-id="e7127-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="e7127-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="e7127-153">Publisher</span></span> | <span data-ttu-id="e7127-154">string</span><span class="sxs-lookup"><span data-stu-id="e7127-154">string</span></span> | <span data-ttu-id="e7127-155">发布文件的组织的名称</span><span class="sxs-lookup"><span data-stu-id="e7127-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="e7127-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="e7127-156">SoftwareName</span></span> | <span data-ttu-id="e7127-157">string</span><span class="sxs-lookup"><span data-stu-id="e7127-157">string</span></span> | <span data-ttu-id="e7127-158">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="e7127-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="e7127-159">语法</span><span class="sxs-lookup"><span data-stu-id="e7127-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="e7127-160">参数</span><span class="sxs-lookup"><span data-stu-id="e7127-160">Arguments</span></span>

- <span data-ttu-id="e7127-161">**x**—要使用的文件 ID 列： `SHA1` 、 `SHA256` 、 `InitiatingProcessSHA1` 、 `InitiatingProcessSHA256` 或; `SHA1` 如果未指定，则使用函数</span><span class="sxs-lookup"><span data-stu-id="e7127-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="e7127-162">**y**-限制为要丰富的记录数，1-1000;函数使用100（如果未指定）</span><span class="sxs-lookup"><span data-stu-id="e7127-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="e7127-163">示例</span><span class="sxs-lookup"><span data-stu-id="e7127-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="e7127-164">仅投影 SHA1 列并浓缩它</span><span class="sxs-lookup"><span data-stu-id="e7127-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="e7127-165">浓缩前500条记录并列出低传播文件</span><span class="sxs-lookup"><span data-stu-id="e7127-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="e7127-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="e7127-166">Related topics</span></span>
- [<span data-ttu-id="e7127-167">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="e7127-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e7127-168">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="e7127-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e7127-169">了解架构</span><span class="sxs-lookup"><span data-stu-id="e7127-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e7127-170">获取更多查询示例</span><span class="sxs-lookup"><span data-stu-id="e7127-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
