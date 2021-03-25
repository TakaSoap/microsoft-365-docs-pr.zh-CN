---
title: 软件方法和属性
description: 检索最近的警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9bfec2c4e65a390189556c14347eaf17236fb95e
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187054"
---
# <a name="software-resource-type"></a><span data-ttu-id="f8703-104">软件资源类型</span><span class="sxs-lookup"><span data-stu-id="f8703-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8703-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f8703-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8703-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8703-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8703-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8703-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f8703-108">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f8703-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f8703-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f8703-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8703-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f8703-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="f8703-111">方法</span><span class="sxs-lookup"><span data-stu-id="f8703-111">Methods</span></span>

<span data-ttu-id="f8703-112">方法</span><span class="sxs-lookup"><span data-stu-id="f8703-112">Method</span></span> |<span data-ttu-id="f8703-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="f8703-113">Return Type</span></span> |<span data-ttu-id="f8703-114">说明</span><span class="sxs-lookup"><span data-stu-id="f8703-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f8703-115">列出软件</span><span class="sxs-lookup"><span data-stu-id="f8703-115">List software</span></span>](get-software.md) | <span data-ttu-id="f8703-116">软件集合</span><span class="sxs-lookup"><span data-stu-id="f8703-116">Software collection</span></span> | <span data-ttu-id="f8703-117">列出组织软件清单。</span><span class="sxs-lookup"><span data-stu-id="f8703-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="f8703-118">按 ID 获取软件</span><span class="sxs-lookup"><span data-stu-id="f8703-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="f8703-119">软件</span><span class="sxs-lookup"><span data-stu-id="f8703-119">Software</span></span> | <span data-ttu-id="f8703-120">按软件 ID 获取特定软件。</span><span class="sxs-lookup"><span data-stu-id="f8703-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="f8703-121">列出软件版本分发</span><span class="sxs-lookup"><span data-stu-id="f8703-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="f8703-122">通讯组集合</span><span class="sxs-lookup"><span data-stu-id="f8703-122">Distribution collection</span></span> | <span data-ttu-id="f8703-123">按软件 ID 列出软件版本分发。</span><span class="sxs-lookup"><span data-stu-id="f8703-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="f8703-124">按软件列出计算机</span><span class="sxs-lookup"><span data-stu-id="f8703-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="f8703-125">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="f8703-125">MachineRef collection</span></span> | <span data-ttu-id="f8703-126">检索与软件 ID 关联的设备列表。</span><span class="sxs-lookup"><span data-stu-id="f8703-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="f8703-127">按软件列出漏洞</span><span class="sxs-lookup"><span data-stu-id="f8703-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="f8703-128">[漏洞](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="f8703-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="f8703-129">检索与软件 ID 关联的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="f8703-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="f8703-130">获取缺少的 KB</span><span class="sxs-lookup"><span data-stu-id="f8703-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="f8703-131">KB 集合</span><span class="sxs-lookup"><span data-stu-id="f8703-131">KB collection</span></span> | <span data-ttu-id="f8703-132">获取与软件 ID 关联的缺失的 KB 列表</span><span class="sxs-lookup"><span data-stu-id="f8703-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="f8703-133">属性</span><span class="sxs-lookup"><span data-stu-id="f8703-133">Properties</span></span>

<span data-ttu-id="f8703-134">属性</span><span class="sxs-lookup"><span data-stu-id="f8703-134">Property</span></span> |   <span data-ttu-id="f8703-135">类型</span><span class="sxs-lookup"><span data-stu-id="f8703-135">Type</span></span>   |   <span data-ttu-id="f8703-136">说明</span><span class="sxs-lookup"><span data-stu-id="f8703-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="f8703-137">id</span><span class="sxs-lookup"><span data-stu-id="f8703-137">id</span></span> | <span data-ttu-id="f8703-138">String</span><span class="sxs-lookup"><span data-stu-id="f8703-138">String</span></span> | <span data-ttu-id="f8703-139">软件 ID</span><span class="sxs-lookup"><span data-stu-id="f8703-139">Software ID</span></span>
<span data-ttu-id="f8703-140">名称</span><span class="sxs-lookup"><span data-stu-id="f8703-140">Name</span></span> | <span data-ttu-id="f8703-141">String</span><span class="sxs-lookup"><span data-stu-id="f8703-141">String</span></span> | <span data-ttu-id="f8703-142">软件名称</span><span class="sxs-lookup"><span data-stu-id="f8703-142">Software name</span></span>
<span data-ttu-id="f8703-143">供应商</span><span class="sxs-lookup"><span data-stu-id="f8703-143">Vendor</span></span> | <span data-ttu-id="f8703-144">String</span><span class="sxs-lookup"><span data-stu-id="f8703-144">String</span></span> | <span data-ttu-id="f8703-145">软件供应商名称</span><span class="sxs-lookup"><span data-stu-id="f8703-145">Software vendor name</span></span>
<span data-ttu-id="f8703-146">漏洞</span><span class="sxs-lookup"><span data-stu-id="f8703-146">Weaknesses</span></span> | <span data-ttu-id="f8703-147">长型</span><span class="sxs-lookup"><span data-stu-id="f8703-147">Long</span></span> | <span data-ttu-id="f8703-148">发现的漏洞数量</span><span class="sxs-lookup"><span data-stu-id="f8703-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="f8703-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="f8703-149">publicExploit</span></span> | <span data-ttu-id="f8703-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="f8703-150">Boolean</span></span> | <span data-ttu-id="f8703-151">存在针对某些漏洞的公共攻击</span><span class="sxs-lookup"><span data-stu-id="f8703-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="f8703-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="f8703-152">activeAlert</span></span> | <span data-ttu-id="f8703-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="f8703-153">Boolean</span></span> | <span data-ttu-id="f8703-154">活动警报与此软件关联</span><span class="sxs-lookup"><span data-stu-id="f8703-154">Active alert is associated with this software</span></span>
<span data-ttu-id="f8703-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="f8703-155">exposedMachines</span></span> | <span data-ttu-id="f8703-156">长型</span><span class="sxs-lookup"><span data-stu-id="f8703-156">Long</span></span> | <span data-ttu-id="f8703-157">公开的设备数量</span><span class="sxs-lookup"><span data-stu-id="f8703-157">Number of exposed devices</span></span>
<span data-ttu-id="f8703-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="f8703-158">impactScore</span></span> | <span data-ttu-id="f8703-159">双精度</span><span class="sxs-lookup"><span data-stu-id="f8703-159">Double</span></span> | <span data-ttu-id="f8703-160">此软件的曝光评分影响</span><span class="sxs-lookup"><span data-stu-id="f8703-160">Exposure score impact of this software</span></span>
