---
title: Microsoft 365 defender () 高级搜寻中的 FileProfile () 函数
description: 了解如何使用 FileProfile () 丰富有关高级搜寻查询结果中的文件的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
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
ms.openlocfilehash: f2e92967b8951cd0f5a3c394a537404db1d53819
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424019"
---
# <a name="fileprofile"></a><span data-ttu-id="55e9f-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="55e9f-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="55e9f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="55e9f-105">**Applies to:**</span></span>
- <span data-ttu-id="55e9f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55e9f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="55e9f-107">该 `FileProfile()` 函数是高级搜寻中的扩充 [函数](advanced-hunting-overview.md) ，它将以下数据添加到查询找到的文件。</span><span class="sxs-lookup"><span data-stu-id="55e9f-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="55e9f-108">列</span><span class="sxs-lookup"><span data-stu-id="55e9f-108">Column</span></span> | <span data-ttu-id="55e9f-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="55e9f-109">Data type</span></span> | <span data-ttu-id="55e9f-110">说明</span><span class="sxs-lookup"><span data-stu-id="55e9f-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="55e9f-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="55e9f-111">SHA1</span></span> | <span data-ttu-id="55e9f-112">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-112">string</span></span> | <span data-ttu-id="55e9f-113">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="55e9f-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="55e9f-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="55e9f-114">SHA256</span></span> | <span data-ttu-id="55e9f-115">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-115">string</span></span> | <span data-ttu-id="55e9f-116">已记录操作应用到的文件的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="55e9f-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="55e9f-117">MD5</span><span class="sxs-lookup"><span data-stu-id="55e9f-117">MD5</span></span> | <span data-ttu-id="55e9f-118">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-118">string</span></span> | <span data-ttu-id="55e9f-119">记录的操作应用到的文件的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="55e9f-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="55e9f-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="55e9f-120">FileSize</span></span> | <span data-ttu-id="55e9f-121">int</span><span class="sxs-lookup"><span data-stu-id="55e9f-121">int</span></span> | <span data-ttu-id="55e9f-122">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="55e9f-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="55e9f-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="55e9f-123">GlobalPrevalence</span></span> | <span data-ttu-id="55e9f-124">int</span><span class="sxs-lookup"><span data-stu-id="55e9f-124">int</span></span> | <span data-ttu-id="55e9f-125">Microsoft 全局观测到的实体实例数</span><span class="sxs-lookup"><span data-stu-id="55e9f-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="55e9f-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="55e9f-126">GlobalFirstSeen</span></span> | <span data-ttu-id="55e9f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="55e9f-127">datetime</span></span> | <span data-ttu-id="55e9f-128">Microsoft 全局首次观察到实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="55e9f-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="55e9f-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="55e9f-129">GlobalLastSeen</span></span> | <span data-ttu-id="55e9f-130">datetime</span><span class="sxs-lookup"><span data-stu-id="55e9f-130">datetime</span></span> | <span data-ttu-id="55e9f-131">Microsoft 上次全局观测到实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="55e9f-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="55e9f-132">签名者</span><span class="sxs-lookup"><span data-stu-id="55e9f-132">Signer</span></span> | <span data-ttu-id="55e9f-133">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-133">string</span></span> | <span data-ttu-id="55e9f-134">有关文件签署人的信息</span><span class="sxs-lookup"><span data-stu-id="55e9f-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="55e9f-135">颁发者</span><span class="sxs-lookup"><span data-stu-id="55e9f-135">Issuer</span></span> | <span data-ttu-id="55e9f-136">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-136">string</span></span> | <span data-ttu-id="55e9f-137">有关 CA 证书颁发机构 (的信息) </span><span class="sxs-lookup"><span data-stu-id="55e9f-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="55e9f-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="55e9f-138">SignerHash</span></span> | <span data-ttu-id="55e9f-139">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-139">string</span></span> | <span data-ttu-id="55e9f-140">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="55e9f-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="55e9f-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="55e9f-141">IsCertificateValid</span></span> | <span data-ttu-id="55e9f-142">boolean</span><span class="sxs-lookup"><span data-stu-id="55e9f-142">boolean</span></span> | <span data-ttu-id="55e9f-143">用于对文件进行签名的证书是否有效</span><span class="sxs-lookup"><span data-stu-id="55e9f-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="55e9f-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="55e9f-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="55e9f-145">boolean</span><span class="sxs-lookup"><span data-stu-id="55e9f-145">boolean</span></span> | <span data-ttu-id="55e9f-146">指示根证书的签名者是否是 Microsoft</span><span class="sxs-lookup"><span data-stu-id="55e9f-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="55e9f-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="55e9f-147">IsExecutable</span></span> | <span data-ttu-id="55e9f-148">boolean</span><span class="sxs-lookup"><span data-stu-id="55e9f-148">boolean</span></span> | <span data-ttu-id="55e9f-149">文件是否是可移植可执行 (PE) 文件</span><span class="sxs-lookup"><span data-stu-id="55e9f-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="55e9f-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="55e9f-150">ThreatName</span></span> | <span data-ttu-id="55e9f-151">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-151">string</span></span> | <span data-ttu-id="55e9f-152">找到的任何恶意软件或其他威胁的检测名称</span><span class="sxs-lookup"><span data-stu-id="55e9f-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="55e9f-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="55e9f-153">Publisher</span></span> | <span data-ttu-id="55e9f-154">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-154">string</span></span> | <span data-ttu-id="55e9f-155">发布该文件的组织的名称</span><span class="sxs-lookup"><span data-stu-id="55e9f-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="55e9f-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="55e9f-156">SoftwareName</span></span> | <span data-ttu-id="55e9f-157">string</span><span class="sxs-lookup"><span data-stu-id="55e9f-157">string</span></span> | <span data-ttu-id="55e9f-158">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="55e9f-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="55e9f-159">语法</span><span class="sxs-lookup"><span data-stu-id="55e9f-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="55e9f-160">参数</span><span class="sxs-lookup"><span data-stu-id="55e9f-160">Arguments</span></span>

- <span data-ttu-id="55e9f-161">**x**— 要使用的文件 ID 列：、、 `SHA1` `SHA256` `InitiatingProcessSHA1` 或 `InitiatingProcessSHA256` ;函数（ `SHA1` 如果未指定）</span><span class="sxs-lookup"><span data-stu-id="55e9f-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="55e9f-162">**y**— 限制为要扩充的记录数，1-1000;函数使用 100（如果未指定）</span><span class="sxs-lookup"><span data-stu-id="55e9f-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="55e9f-163">扩充函数仅在可用时显示补充信息。</span><span class="sxs-lookup"><span data-stu-id="55e9f-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="55e9f-164">信息的可用性各不相同，具体取决于许多因素。</span><span class="sxs-lookup"><span data-stu-id="55e9f-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="55e9f-165">请确保在查询或创建自定义检测 () FileProfile 应用程序时考虑这一点。</span><span class="sxs-lookup"><span data-stu-id="55e9f-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="55e9f-166">为了获得最佳结果，我们建议将 FileProfile () 函数与 SHA1 一同使用。</span><span class="sxs-lookup"><span data-stu-id="55e9f-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="55e9f-167">示例</span><span class="sxs-lookup"><span data-stu-id="55e9f-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="55e9f-168">仅项目 SHA1 列并丰富它</span><span class="sxs-lookup"><span data-stu-id="55e9f-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="55e9f-169">丰富前 500 条记录并列出低普遍程度文件</span><span class="sxs-lookup"><span data-stu-id="55e9f-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="55e9f-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="55e9f-170">Related topics</span></span>
- [<span data-ttu-id="55e9f-171">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="55e9f-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="55e9f-172">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="55e9f-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="55e9f-173">了解架构</span><span class="sxs-lookup"><span data-stu-id="55e9f-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="55e9f-174">获取更多查询示例</span><span class="sxs-lookup"><span data-stu-id="55e9f-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
