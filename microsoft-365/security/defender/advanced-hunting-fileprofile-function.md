---
title: FileProfile () Microsoft 365 Defender 高级搜寻中的函数
description: 了解如何使用 FileProfile () 丰富有关高级搜寻查询结果中的文件的信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
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
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382789"
---
# <a name="fileprofile"></a><span data-ttu-id="215fb-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="215fb-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="215fb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="215fb-105">**Applies to:**</span></span>
- <span data-ttu-id="215fb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="215fb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="215fb-107">函数 `FileProfile()` 是高级搜寻中的扩充 [函数](advanced-hunting-overview.md) ，用于将以下数据添加到查询找到的文件。</span><span class="sxs-lookup"><span data-stu-id="215fb-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="215fb-108">Column</span><span class="sxs-lookup"><span data-stu-id="215fb-108">Column</span></span> | <span data-ttu-id="215fb-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="215fb-109">Data type</span></span> | <span data-ttu-id="215fb-110">说明</span><span class="sxs-lookup"><span data-stu-id="215fb-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="215fb-111">string</span><span class="sxs-lookup"><span data-stu-id="215fb-111">string</span></span> | <span data-ttu-id="215fb-112">录制操作所应用到的文件的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="215fb-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="215fb-113">string</span><span class="sxs-lookup"><span data-stu-id="215fb-113">string</span></span> | <span data-ttu-id="215fb-114">已记录操作应用于的文件的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="215fb-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="215fb-115">string</span><span class="sxs-lookup"><span data-stu-id="215fb-115">string</span></span> | <span data-ttu-id="215fb-116">已记录操作所应用到的文件的 MD5 哈希</span><span class="sxs-lookup"><span data-stu-id="215fb-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="215fb-117">int</span><span class="sxs-lookup"><span data-stu-id="215fb-117">int</span></span> | <span data-ttu-id="215fb-118">文件大小（以字节为单位）</span><span class="sxs-lookup"><span data-stu-id="215fb-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="215fb-119">int</span><span class="sxs-lookup"><span data-stu-id="215fb-119">int</span></span> | <span data-ttu-id="215fb-120">Microsoft 全局观察到的实体实例数</span><span class="sxs-lookup"><span data-stu-id="215fb-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="215fb-121">datetime</span><span class="sxs-lookup"><span data-stu-id="215fb-121">datetime</span></span> | <span data-ttu-id="215fb-122">Microsoft 全局首次观测到实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="215fb-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="215fb-123">datetime</span><span class="sxs-lookup"><span data-stu-id="215fb-123">datetime</span></span> | <span data-ttu-id="215fb-124">Microsoft 全局上次观测到实体的日期和时间</span><span class="sxs-lookup"><span data-stu-id="215fb-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="215fb-125">string</span><span class="sxs-lookup"><span data-stu-id="215fb-125">string</span></span> | <span data-ttu-id="215fb-126">有关文件签名者的信息</span><span class="sxs-lookup"><span data-stu-id="215fb-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="215fb-127">string</span><span class="sxs-lookup"><span data-stu-id="215fb-127">string</span></span> | <span data-ttu-id="215fb-128">有关 CA 证书颁发机构 (的信息) </span><span class="sxs-lookup"><span data-stu-id="215fb-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="215fb-129">string</span><span class="sxs-lookup"><span data-stu-id="215fb-129">string</span></span> | <span data-ttu-id="215fb-130">标识签名者的唯一哈希值</span><span class="sxs-lookup"><span data-stu-id="215fb-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="215fb-131">boolean</span><span class="sxs-lookup"><span data-stu-id="215fb-131">boolean</span></span> | <span data-ttu-id="215fb-132">用于对文件进行签名的证书是否有效</span><span class="sxs-lookup"><span data-stu-id="215fb-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="215fb-133">boolean</span><span class="sxs-lookup"><span data-stu-id="215fb-133">boolean</span></span> | <span data-ttu-id="215fb-134">指示根证书的签名者是否是 Microsoft</span><span class="sxs-lookup"><span data-stu-id="215fb-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="215fb-135">string</span><span class="sxs-lookup"><span data-stu-id="215fb-135">string</span></span> | <span data-ttu-id="215fb-136">文件签名的状态：SignedValid - 使用有效签名对文件进行签名，SignedInvalid - 文件已签名，但证书无效，未签名 - 文件未签名，未知 - 无法检索有关文件的信息</span><span class="sxs-lookup"><span data-stu-id="215fb-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="215fb-137">boolean</span><span class="sxs-lookup"><span data-stu-id="215fb-137">boolean</span></span> | <span data-ttu-id="215fb-138">文件是否是可移植可执行 (PE) 文件</span><span class="sxs-lookup"><span data-stu-id="215fb-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="215fb-139">string</span><span class="sxs-lookup"><span data-stu-id="215fb-139">string</span></span> | <span data-ttu-id="215fb-140">找到的任何恶意软件或其他威胁的检测名称</span><span class="sxs-lookup"><span data-stu-id="215fb-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="215fb-141">string</span><span class="sxs-lookup"><span data-stu-id="215fb-141">string</span></span> | <span data-ttu-id="215fb-142">发布该文件的组织的名称</span><span class="sxs-lookup"><span data-stu-id="215fb-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="215fb-143">string</span><span class="sxs-lookup"><span data-stu-id="215fb-143">string</span></span> | <span data-ttu-id="215fb-144">软件产品的名称</span><span class="sxs-lookup"><span data-stu-id="215fb-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="215fb-145">语法</span><span class="sxs-lookup"><span data-stu-id="215fb-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="215fb-146">参数</span><span class="sxs-lookup"><span data-stu-id="215fb-146">Arguments</span></span>

- <span data-ttu-id="215fb-147">**x**—要使用的文件 ID 列 `SHA1` `SHA256` ：、、 `InitiatingProcessSHA1` 或 `InitiatingProcessSHA256` ;函数使用 `SHA1` （如果未指定）</span><span class="sxs-lookup"><span data-stu-id="215fb-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="215fb-148">**y**— 限制要扩充的记录数，1-1000;函数使用 100（如果未指定）</span><span class="sxs-lookup"><span data-stu-id="215fb-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="215fb-149">扩充函数仅在可用时显示补充信息。</span><span class="sxs-lookup"><span data-stu-id="215fb-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="215fb-150">信息的可用性各不相同，具体取决于许多因素。</span><span class="sxs-lookup"><span data-stu-id="215fb-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="215fb-151">确保在查询或创建自定义检测 () FileProfile 方法时考虑这一点。</span><span class="sxs-lookup"><span data-stu-id="215fb-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="215fb-152">为了获得最佳结果，我们建议将 FileProfile () 函数与 SHA1 一同使用。</span><span class="sxs-lookup"><span data-stu-id="215fb-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="215fb-153">示例</span><span class="sxs-lookup"><span data-stu-id="215fb-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="215fb-154">仅规划 SHA1 列并扩充它</span><span class="sxs-lookup"><span data-stu-id="215fb-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="215fb-155">丰富前 500 条记录并列出低程度文件</span><span class="sxs-lookup"><span data-stu-id="215fb-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="215fb-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="215fb-156">Related topics</span></span>
- [<span data-ttu-id="215fb-157">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="215fb-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="215fb-158">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="215fb-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="215fb-159">了解架构</span><span class="sxs-lookup"><span data-stu-id="215fb-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="215fb-160">获取更多查询示例</span><span class="sxs-lookup"><span data-stu-id="215fb-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
