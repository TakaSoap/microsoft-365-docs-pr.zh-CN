---
title: File 资源类型
description: 检索最近与文件相关的 Microsoft Defender for Endpoint 警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199977"
---
# <a name="file-resource-type"></a><span data-ttu-id="f1733-104">File 资源类型</span><span class="sxs-lookup"><span data-stu-id="f1733-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f1733-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f1733-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f1733-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f1733-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1733-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f1733-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="f1733-108">表示 Defender for Endpoint 中的文件实体。</span><span class="sxs-lookup"><span data-stu-id="f1733-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="f1733-109">方法</span><span class="sxs-lookup"><span data-stu-id="f1733-109">Methods</span></span>
<span data-ttu-id="f1733-110">方法</span><span class="sxs-lookup"><span data-stu-id="f1733-110">Method</span></span>|<span data-ttu-id="f1733-111">返回类型</span><span class="sxs-lookup"><span data-stu-id="f1733-111">Return Type</span></span> |<span data-ttu-id="f1733-112">说明</span><span class="sxs-lookup"><span data-stu-id="f1733-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f1733-113">获取文件</span><span class="sxs-lookup"><span data-stu-id="f1733-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="f1733-114">File</span><span class="sxs-lookup"><span data-stu-id="f1733-114">file</span></span>](files.md) | <span data-ttu-id="f1733-115">获取单个文件</span><span class="sxs-lookup"><span data-stu-id="f1733-115">Get a single file</span></span> 
[<span data-ttu-id="f1733-116">列出与文件相关的警报</span><span class="sxs-lookup"><span data-stu-id="f1733-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="f1733-117">[警报](alerts.md)集合</span><span class="sxs-lookup"><span data-stu-id="f1733-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="f1733-118">获取 [与](alerts.md) 文件关联的警报实体。</span><span class="sxs-lookup"><span data-stu-id="f1733-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="f1733-119">列出与文件相关的计算机</span><span class="sxs-lookup"><span data-stu-id="f1733-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="f1733-120">[计算机](machine.md) 集合</span><span class="sxs-lookup"><span data-stu-id="f1733-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="f1733-121">获取 [与](machine.md) 警报关联的计算机实体。</span><span class="sxs-lookup"><span data-stu-id="f1733-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="f1733-122">文件统计信息</span><span class="sxs-lookup"><span data-stu-id="f1733-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="f1733-123">统计信息摘要</span><span class="sxs-lookup"><span data-stu-id="f1733-123">Statistics summary</span></span> | <span data-ttu-id="f1733-124">检索给定文件的普遍程度。</span><span class="sxs-lookup"><span data-stu-id="f1733-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="f1733-125">属性</span><span class="sxs-lookup"><span data-stu-id="f1733-125">Properties</span></span>
|<span data-ttu-id="f1733-126">属性</span><span class="sxs-lookup"><span data-stu-id="f1733-126">Property</span></span> | <span data-ttu-id="f1733-127">类型</span><span class="sxs-lookup"><span data-stu-id="f1733-127">Type</span></span>    |   <span data-ttu-id="f1733-128">说明</span><span class="sxs-lookup"><span data-stu-id="f1733-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="f1733-129">sha1</span><span class="sxs-lookup"><span data-stu-id="f1733-129">sha1</span></span> | <span data-ttu-id="f1733-130">String</span><span class="sxs-lookup"><span data-stu-id="f1733-130">String</span></span> | <span data-ttu-id="f1733-131">文件内容的 Sha1 哈希</span><span class="sxs-lookup"><span data-stu-id="f1733-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="f1733-132">sha256</span><span class="sxs-lookup"><span data-stu-id="f1733-132">sha256</span></span> | <span data-ttu-id="f1733-133">String</span><span class="sxs-lookup"><span data-stu-id="f1733-133">String</span></span> | <span data-ttu-id="f1733-134">文件内容的 Sha256 哈希</span><span class="sxs-lookup"><span data-stu-id="f1733-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="f1733-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="f1733-135">globalPrevalence</span></span> | <span data-ttu-id="f1733-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="f1733-136">Nullable long</span></span> | <span data-ttu-id="f1733-137">跨组织的文件普遍程度</span><span class="sxs-lookup"><span data-stu-id="f1733-137">File prevalence across organization</span></span> |
|<span data-ttu-id="f1733-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="f1733-138">globalFirstObserved</span></span> | <span data-ttu-id="f1733-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f1733-139">DateTimeOffset</span></span> | <span data-ttu-id="f1733-140">首次观察到文件时</span><span class="sxs-lookup"><span data-stu-id="f1733-140">First time the file was observed</span></span> |
|<span data-ttu-id="f1733-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="f1733-141">globalLastObserved</span></span> | <span data-ttu-id="f1733-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f1733-142">DateTimeOffset</span></span> | <span data-ttu-id="f1733-143">上次观测到该文件的时间</span><span class="sxs-lookup"><span data-stu-id="f1733-143">Last time the file was observed</span></span> |
|<span data-ttu-id="f1733-144">大小</span><span class="sxs-lookup"><span data-stu-id="f1733-144">size</span></span> | <span data-ttu-id="f1733-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="f1733-145">Nullable long</span></span> | <span data-ttu-id="f1733-146">文件大小</span><span class="sxs-lookup"><span data-stu-id="f1733-146">Size of the file</span></span> |
|<span data-ttu-id="f1733-147">fileType</span><span class="sxs-lookup"><span data-stu-id="f1733-147">fileType</span></span> | <span data-ttu-id="f1733-148">String</span><span class="sxs-lookup"><span data-stu-id="f1733-148">String</span></span> | <span data-ttu-id="f1733-149">文件类型</span><span class="sxs-lookup"><span data-stu-id="f1733-149">Type of the file</span></span> |
|<span data-ttu-id="f1733-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="f1733-150">isPeFile</span></span> | <span data-ttu-id="f1733-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="f1733-151">Boolean</span></span> | <span data-ttu-id="f1733-152">如果文件是可移植的可执行文件 (例如"DLL"、"EXE"等，则其为 true) </span><span class="sxs-lookup"><span data-stu-id="f1733-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="f1733-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="f1733-153">filePublisher</span></span> | <span data-ttu-id="f1733-154">String</span><span class="sxs-lookup"><span data-stu-id="f1733-154">String</span></span> | <span data-ttu-id="f1733-155">文件发布者</span><span class="sxs-lookup"><span data-stu-id="f1733-155">File publisher</span></span> |
|<span data-ttu-id="f1733-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="f1733-156">fileProductName</span></span> | <span data-ttu-id="f1733-157">String</span><span class="sxs-lookup"><span data-stu-id="f1733-157">String</span></span> | <span data-ttu-id="f1733-158">产品名称</span><span class="sxs-lookup"><span data-stu-id="f1733-158">Product name</span></span> |
|<span data-ttu-id="f1733-159">signer</span><span class="sxs-lookup"><span data-stu-id="f1733-159">signer</span></span> | <span data-ttu-id="f1733-160">String</span><span class="sxs-lookup"><span data-stu-id="f1733-160">String</span></span> | <span data-ttu-id="f1733-161">文件签名者</span><span class="sxs-lookup"><span data-stu-id="f1733-161">File signer</span></span> |
|<span data-ttu-id="f1733-162">issuer</span><span class="sxs-lookup"><span data-stu-id="f1733-162">issuer</span></span> | <span data-ttu-id="f1733-163">String</span><span class="sxs-lookup"><span data-stu-id="f1733-163">String</span></span> | <span data-ttu-id="f1733-164">文件颁发者</span><span class="sxs-lookup"><span data-stu-id="f1733-164">File issuer</span></span> |
|<span data-ttu-id="f1733-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="f1733-165">signerHash</span></span> | <span data-ttu-id="f1733-166">String</span><span class="sxs-lookup"><span data-stu-id="f1733-166">String</span></span> | <span data-ttu-id="f1733-167">签名证书的哈希</span><span class="sxs-lookup"><span data-stu-id="f1733-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="f1733-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="f1733-168">isValidCertificate</span></span> | <span data-ttu-id="f1733-169">Boolean</span><span class="sxs-lookup"><span data-stu-id="f1733-169">Boolean</span></span> | <span data-ttu-id="f1733-170">Microsoft Defender for Endpoint 代理是否成功验证了对证书的签名</span><span class="sxs-lookup"><span data-stu-id="f1733-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="f1733-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="f1733-171">determinationType</span></span> | <span data-ttu-id="f1733-172">String</span><span class="sxs-lookup"><span data-stu-id="f1733-172">String</span></span> | <span data-ttu-id="f1733-173">文件的确定类型</span><span class="sxs-lookup"><span data-stu-id="f1733-173">The determination type of the file</span></span> |
|<span data-ttu-id="f1733-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="f1733-174">determinationValue</span></span> | <span data-ttu-id="f1733-175">String</span><span class="sxs-lookup"><span data-stu-id="f1733-175">String</span></span> | <span data-ttu-id="f1733-176">确定值</span><span class="sxs-lookup"><span data-stu-id="f1733-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="f1733-177">Json 表示形式</span><span class="sxs-lookup"><span data-stu-id="f1733-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
