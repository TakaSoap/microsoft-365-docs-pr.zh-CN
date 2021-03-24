---
title: FileProfile () Microsoft Defender for Endpoint 高级搜寻中的函数
description: 了解如何使用 FileProfile () 丰富有关高级搜寻查询结果中的文件的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， Microsoft Defender ATP， Microsoft Defender for Endpoint， Windows Defender， Windows Defender ATP， Windows Defender 高级威胁防护， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056385"
---
# <a name="fileprofile"></a><span data-ttu-id="5ad35-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="5ad35-104">FileProfile()</span></span>

<span data-ttu-id="5ad35-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5ad35-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ad35-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ad35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="5ad35-107">函数 `FileProfile()` 是高级搜寻中的扩充 [函数](advanced-hunting-overview.md) ，用于将以下数据添加到查询找到的文件。</span><span class="sxs-lookup"><span data-stu-id="5ad35-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="5ad35-108">Column</span><span class="sxs-lookup"><span data-stu-id="5ad35-108">Column</span></span> | <span data-ttu-id="5ad35-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="5ad35-109">Data type</span></span> | <span data-ttu-id="5ad35-110">说明</span><span class="sxs-lookup"><span data-stu-id="5ad35-110">Description</span></span>
-|-|-
<span data-ttu-id="5ad35-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="5ad35-111">SHA1</span></span> | <span data-ttu-id="5ad35-112">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-112">string</span></span> | <span data-ttu-id="5ad35-113">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5ad35-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="5ad35-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="5ad35-114">SHA256</span></span> | <span data-ttu-id="5ad35-115">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-115">string</span></span> | <span data-ttu-id="5ad35-116">已记录操作应用于的文件的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="5ad35-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="5ad35-117">MD5</span><span class="sxs-lookup"><span data-stu-id="5ad35-117">MD5</span></span> | <span data-ttu-id="5ad35-118">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-118">string</span></span> | <span data-ttu-id="5ad35-119">已记录操作所应用到的文件的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="5ad35-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="5ad35-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="5ad35-120">FileSize</span></span> | <span data-ttu-id="5ad35-121">int</span><span class="sxs-lookup"><span data-stu-id="5ad35-121">int</span></span> | <span data-ttu-id="5ad35-122">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="5ad35-122">Size of the file in bytes</span></span>
<span data-ttu-id="5ad35-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="5ad35-123">GlobalPrevalence</span></span> | <span data-ttu-id="5ad35-124">int</span><span class="sxs-lookup"><span data-stu-id="5ad35-124">int</span></span> | <span data-ttu-id="5ad35-125">Microsoft 全局观察到的实体实例数</span><span class="sxs-lookup"><span data-stu-id="5ad35-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="5ad35-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="5ad35-126">GlobalFirstSeen</span></span> | <span data-ttu-id="5ad35-127">datetime</span><span class="sxs-lookup"><span data-stu-id="5ad35-127">datetime</span></span> | <span data-ttu-id="5ad35-128">Microsoft 全局首次观测到实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5ad35-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="5ad35-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="5ad35-129">GlobalLastSeen</span></span> | <span data-ttu-id="5ad35-130">datetime</span><span class="sxs-lookup"><span data-stu-id="5ad35-130">datetime</span></span> | <span data-ttu-id="5ad35-131">Microsoft 全局上次观测到实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5ad35-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="5ad35-132">签名者</span><span class="sxs-lookup"><span data-stu-id="5ad35-132">Signer</span></span> | <span data-ttu-id="5ad35-133">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-133">string</span></span> | <span data-ttu-id="5ad35-134">有关文件签名者的信息</span><span class="sxs-lookup"><span data-stu-id="5ad35-134">Information about the signer of the file</span></span>
<span data-ttu-id="5ad35-135">颁发者</span><span class="sxs-lookup"><span data-stu-id="5ad35-135">Issuer</span></span> | <span data-ttu-id="5ad35-136">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-136">string</span></span> | <span data-ttu-id="5ad35-137">有关 CA 证书颁发机构 (的信息) </span><span class="sxs-lookup"><span data-stu-id="5ad35-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="5ad35-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="5ad35-138">SignerHash</span></span> | <span data-ttu-id="5ad35-139">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-139">string</span></span> | <span data-ttu-id="5ad35-140">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="5ad35-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="5ad35-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="5ad35-141">IsCertificateValid</span></span> | <span data-ttu-id="5ad35-142">boolean</span><span class="sxs-lookup"><span data-stu-id="5ad35-142">boolean</span></span> | <span data-ttu-id="5ad35-143">用于对文件进行签名的证书是否有效</span><span class="sxs-lookup"><span data-stu-id="5ad35-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="5ad35-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="5ad35-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="5ad35-145">boolean</span><span class="sxs-lookup"><span data-stu-id="5ad35-145">boolean</span></span> | <span data-ttu-id="5ad35-146">指示根证书的签名者是否是 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5ad35-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="5ad35-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="5ad35-147">IsExecutable</span></span> | <span data-ttu-id="5ad35-148">boolean</span><span class="sxs-lookup"><span data-stu-id="5ad35-148">boolean</span></span> | <span data-ttu-id="5ad35-149">文件是否是可移植可执行 (PE) 文件</span><span class="sxs-lookup"><span data-stu-id="5ad35-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="5ad35-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="5ad35-150">ThreatName</span></span> | <span data-ttu-id="5ad35-151">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-151">string</span></span> | <span data-ttu-id="5ad35-152">找到的任何恶意软件或其他威胁的检测名称</span><span class="sxs-lookup"><span data-stu-id="5ad35-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="5ad35-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="5ad35-153">Publisher</span></span> | <span data-ttu-id="5ad35-154">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-154">string</span></span> | <span data-ttu-id="5ad35-155">发布该文件的组织的名称</span><span class="sxs-lookup"><span data-stu-id="5ad35-155">Name of the organization that published the file</span></span>
<span data-ttu-id="5ad35-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="5ad35-156">SoftwareName</span></span> | <span data-ttu-id="5ad35-157">string</span><span class="sxs-lookup"><span data-stu-id="5ad35-157">string</span></span> | <span data-ttu-id="5ad35-158">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="5ad35-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="5ad35-159">语法</span><span class="sxs-lookup"><span data-stu-id="5ad35-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="5ad35-160">参数</span><span class="sxs-lookup"><span data-stu-id="5ad35-160">Arguments</span></span>

- <span data-ttu-id="5ad35-161">**x** — 要使用的文件 ID 列 `SHA1` ：、 `SHA256` 或 `InitiatingProcessSHA1` `InitiatingProcessSHA256` ;函数使用 `SHA1` （如果未指定）</span><span class="sxs-lookup"><span data-stu-id="5ad35-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="5ad35-162">**y** — 限制要扩充的记录数，1-1000;函数使用 100（如果未指定）</span><span class="sxs-lookup"><span data-stu-id="5ad35-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="5ad35-163">示例</span><span class="sxs-lookup"><span data-stu-id="5ad35-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="5ad35-164">仅规划 SHA1 列并扩充它</span><span class="sxs-lookup"><span data-stu-id="5ad35-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="5ad35-165">丰富前 500 条记录并列出低程度文件</span><span class="sxs-lookup"><span data-stu-id="5ad35-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="5ad35-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ad35-166">Related topics</span></span>

- [<span data-ttu-id="5ad35-167">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="5ad35-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5ad35-168">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="5ad35-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5ad35-169">了解架构</span><span class="sxs-lookup"><span data-stu-id="5ad35-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
