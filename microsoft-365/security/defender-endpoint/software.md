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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771389"
---
# <a name="software-resource-type"></a><span data-ttu-id="5fedf-104">软件资源类型</span><span class="sxs-lookup"><span data-stu-id="5fedf-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5fedf-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5fedf-105">**Applies to:**</span></span>
- [<span data-ttu-id="5fedf-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fedf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5fedf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fedf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5fedf-108">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5fedf-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5fedf-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5fedf-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5fedf-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5fedf-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="5fedf-111">方法</span><span class="sxs-lookup"><span data-stu-id="5fedf-111">Methods</span></span>

<span data-ttu-id="5fedf-112">方法</span><span class="sxs-lookup"><span data-stu-id="5fedf-112">Method</span></span> |<span data-ttu-id="5fedf-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="5fedf-113">Return Type</span></span> |<span data-ttu-id="5fedf-114">说明</span><span class="sxs-lookup"><span data-stu-id="5fedf-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="5fedf-115">列出软件</span><span class="sxs-lookup"><span data-stu-id="5fedf-115">List software</span></span>](get-software.md) | <span data-ttu-id="5fedf-116">软件集合</span><span class="sxs-lookup"><span data-stu-id="5fedf-116">Software collection</span></span> | <span data-ttu-id="5fedf-117">列出组织软件清单。</span><span class="sxs-lookup"><span data-stu-id="5fedf-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="5fedf-118">按 Id 获取软件</span><span class="sxs-lookup"><span data-stu-id="5fedf-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="5fedf-119">软件</span><span class="sxs-lookup"><span data-stu-id="5fedf-119">Software</span></span> | <span data-ttu-id="5fedf-120">按软件 ID 获取特定软件。</span><span class="sxs-lookup"><span data-stu-id="5fedf-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="5fedf-121">列出软件版本分发</span><span class="sxs-lookup"><span data-stu-id="5fedf-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="5fedf-122">通讯组集合</span><span class="sxs-lookup"><span data-stu-id="5fedf-122">Distribution collection</span></span> | <span data-ttu-id="5fedf-123">按软件 ID 列出软件版本分发。</span><span class="sxs-lookup"><span data-stu-id="5fedf-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="5fedf-124">按软件列出计算机</span><span class="sxs-lookup"><span data-stu-id="5fedf-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="5fedf-125">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="5fedf-125">MachineRef collection</span></span> | <span data-ttu-id="5fedf-126">检索与软件 ID 关联的设备列表。</span><span class="sxs-lookup"><span data-stu-id="5fedf-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="5fedf-127">按软件列出漏洞</span><span class="sxs-lookup"><span data-stu-id="5fedf-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="5fedf-128">[漏洞](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="5fedf-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="5fedf-129">检索与软件 ID 关联的漏洞列表。</span><span class="sxs-lookup"><span data-stu-id="5fedf-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="5fedf-130">查找缺失的 KBS</span><span class="sxs-lookup"><span data-stu-id="5fedf-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="5fedf-131">KB 集合</span><span class="sxs-lookup"><span data-stu-id="5fedf-131">KB collection</span></span> | <span data-ttu-id="5fedf-132">获取与软件 ID 关联的缺失的 KB 列表</span><span class="sxs-lookup"><span data-stu-id="5fedf-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="5fedf-133">属性</span><span class="sxs-lookup"><span data-stu-id="5fedf-133">Properties</span></span>

<span data-ttu-id="5fedf-134">属性</span><span class="sxs-lookup"><span data-stu-id="5fedf-134">Property</span></span> |   <span data-ttu-id="5fedf-135">类型</span><span class="sxs-lookup"><span data-stu-id="5fedf-135">Type</span></span>   |   <span data-ttu-id="5fedf-136">说明</span><span class="sxs-lookup"><span data-stu-id="5fedf-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="5fedf-137">id</span><span class="sxs-lookup"><span data-stu-id="5fedf-137">id</span></span> | <span data-ttu-id="5fedf-138">String</span><span class="sxs-lookup"><span data-stu-id="5fedf-138">String</span></span> | <span data-ttu-id="5fedf-139">软件 ID</span><span class="sxs-lookup"><span data-stu-id="5fedf-139">Software ID</span></span>
<span data-ttu-id="5fedf-140">名称</span><span class="sxs-lookup"><span data-stu-id="5fedf-140">Name</span></span> | <span data-ttu-id="5fedf-141">String</span><span class="sxs-lookup"><span data-stu-id="5fedf-141">String</span></span> | <span data-ttu-id="5fedf-142">软件名称</span><span class="sxs-lookup"><span data-stu-id="5fedf-142">Software name</span></span>
<span data-ttu-id="5fedf-143">供应商</span><span class="sxs-lookup"><span data-stu-id="5fedf-143">Vendor</span></span> | <span data-ttu-id="5fedf-144">String</span><span class="sxs-lookup"><span data-stu-id="5fedf-144">String</span></span> | <span data-ttu-id="5fedf-145">软件供应商名称</span><span class="sxs-lookup"><span data-stu-id="5fedf-145">Software vendor name</span></span>
<span data-ttu-id="5fedf-146">漏洞</span><span class="sxs-lookup"><span data-stu-id="5fedf-146">Weaknesses</span></span> | <span data-ttu-id="5fedf-147">长型</span><span class="sxs-lookup"><span data-stu-id="5fedf-147">Long</span></span> | <span data-ttu-id="5fedf-148">发现的漏洞数量</span><span class="sxs-lookup"><span data-stu-id="5fedf-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="5fedf-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="5fedf-149">publicExploit</span></span> | <span data-ttu-id="5fedf-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="5fedf-150">Boolean</span></span> | <span data-ttu-id="5fedf-151">存在针对某些漏洞的公共攻击</span><span class="sxs-lookup"><span data-stu-id="5fedf-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="5fedf-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="5fedf-152">activeAlert</span></span> | <span data-ttu-id="5fedf-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="5fedf-153">Boolean</span></span> | <span data-ttu-id="5fedf-154">活动警报与此软件关联</span><span class="sxs-lookup"><span data-stu-id="5fedf-154">Active alert is associated with this software</span></span>
<span data-ttu-id="5fedf-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="5fedf-155">exposedMachines</span></span> | <span data-ttu-id="5fedf-156">长型</span><span class="sxs-lookup"><span data-stu-id="5fedf-156">Long</span></span> | <span data-ttu-id="5fedf-157">公开的设备数量</span><span class="sxs-lookup"><span data-stu-id="5fedf-157">Number of exposed devices</span></span>
<span data-ttu-id="5fedf-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="5fedf-158">impactScore</span></span> | <span data-ttu-id="5fedf-159">双精度</span><span class="sxs-lookup"><span data-stu-id="5fedf-159">Double</span></span> | <span data-ttu-id="5fedf-160">此软件的曝光评分影响</span><span class="sxs-lookup"><span data-stu-id="5fedf-160">Exposure score impact of this software</span></span>
