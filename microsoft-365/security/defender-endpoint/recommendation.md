---
title: 建议方法和属性
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
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771593"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="b750f-104">建议资源类型</span><span class="sxs-lookup"><span data-stu-id="b750f-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b750f-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b750f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="b750f-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b750f-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b750f-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b750f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="b750f-108">方法</span><span class="sxs-lookup"><span data-stu-id="b750f-108">Methods</span></span>
<span data-ttu-id="b750f-109">方法</span><span class="sxs-lookup"><span data-stu-id="b750f-109">Method</span></span> |<span data-ttu-id="b750f-110">返回类型</span><span class="sxs-lookup"><span data-stu-id="b750f-110">Return Type</span></span> |<span data-ttu-id="b750f-111">说明</span><span class="sxs-lookup"><span data-stu-id="b750f-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="b750f-112">列出所有建议</span><span class="sxs-lookup"><span data-stu-id="b750f-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="b750f-113">建议集合</span><span class="sxs-lookup"><span data-stu-id="b750f-113">Recommendation collection</span></span> | <span data-ttu-id="b750f-114">检索影响组织的所有安全建议的列表</span><span class="sxs-lookup"><span data-stu-id="b750f-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="b750f-115">按 Id 获取建议</span><span class="sxs-lookup"><span data-stu-id="b750f-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="b750f-116">建议</span><span class="sxs-lookup"><span data-stu-id="b750f-116">Recommendation</span></span> | <span data-ttu-id="b750f-117">按 ID 检索安全建议</span><span class="sxs-lookup"><span data-stu-id="b750f-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="b750f-118">获取建议软件</span><span class="sxs-lookup"><span data-stu-id="b750f-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="b750f-119">软件</span><span class="sxs-lookup"><span data-stu-id="b750f-119">Software</span></span>](software.md) | <span data-ttu-id="b750f-120">检索与特定软件相关的安全建议</span><span class="sxs-lookup"><span data-stu-id="b750f-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="b750f-121">获取建议设备</span><span class="sxs-lookup"><span data-stu-id="b750f-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="b750f-122">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="b750f-122">MachineRef collection</span></span> | <span data-ttu-id="b750f-123">检索与安全建议关联的设备列表</span><span class="sxs-lookup"><span data-stu-id="b750f-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="b750f-124">获取建议漏洞</span><span class="sxs-lookup"><span data-stu-id="b750f-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="b750f-125">[漏洞](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="b750f-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="b750f-126">检索与安全建议关联的漏洞列表</span><span class="sxs-lookup"><span data-stu-id="b750f-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="b750f-127">属性</span><span class="sxs-lookup"><span data-stu-id="b750f-127">Properties</span></span>
<span data-ttu-id="b750f-128">属性</span><span class="sxs-lookup"><span data-stu-id="b750f-128">Property</span></span> |   <span data-ttu-id="b750f-129">类型</span><span class="sxs-lookup"><span data-stu-id="b750f-129">Type</span></span>   |   <span data-ttu-id="b750f-130">说明</span><span class="sxs-lookup"><span data-stu-id="b750f-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="b750f-131">id</span><span class="sxs-lookup"><span data-stu-id="b750f-131">id</span></span> | <span data-ttu-id="b750f-132">String</span><span class="sxs-lookup"><span data-stu-id="b750f-132">String</span></span> | <span data-ttu-id="b750f-133">建议 ID</span><span class="sxs-lookup"><span data-stu-id="b750f-133">Recommendation ID</span></span>
<span data-ttu-id="b750f-134">productName</span><span class="sxs-lookup"><span data-stu-id="b750f-134">productName</span></span> | <span data-ttu-id="b750f-135">String</span><span class="sxs-lookup"><span data-stu-id="b750f-135">String</span></span> | <span data-ttu-id="b750f-136">相关软件名称</span><span class="sxs-lookup"><span data-stu-id="b750f-136">Related software name</span></span>  
<span data-ttu-id="b750f-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="b750f-137">recommendationName</span></span> | <span data-ttu-id="b750f-138">String</span><span class="sxs-lookup"><span data-stu-id="b750f-138">String</span></span> | <span data-ttu-id="b750f-139">建议名称</span><span class="sxs-lookup"><span data-stu-id="b750f-139">Recommendation name</span></span>
<span data-ttu-id="b750f-140">漏洞</span><span class="sxs-lookup"><span data-stu-id="b750f-140">Weaknesses</span></span> | <span data-ttu-id="b750f-141">长型</span><span class="sxs-lookup"><span data-stu-id="b750f-141">Long</span></span> | <span data-ttu-id="b750f-142">发现的漏洞数量</span><span class="sxs-lookup"><span data-stu-id="b750f-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="b750f-143">供应商</span><span class="sxs-lookup"><span data-stu-id="b750f-143">Vendor</span></span> | <span data-ttu-id="b750f-144">String</span><span class="sxs-lookup"><span data-stu-id="b750f-144">String</span></span> | <span data-ttu-id="b750f-145">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="b750f-145">Related vendor name</span></span>
<span data-ttu-id="b750f-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="b750f-146">recommendedVersion</span></span> | <span data-ttu-id="b750f-147">String</span><span class="sxs-lookup"><span data-stu-id="b750f-147">String</span></span> | <span data-ttu-id="b750f-148">建议版本</span><span class="sxs-lookup"><span data-stu-id="b750f-148">Recommended version</span></span>
<span data-ttu-id="b750f-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="b750f-149">recommendationCategory</span></span> | <span data-ttu-id="b750f-150">String</span><span class="sxs-lookup"><span data-stu-id="b750f-150">String</span></span> | <span data-ttu-id="b750f-151">建议类别。</span><span class="sxs-lookup"><span data-stu-id="b750f-151">Recommendation category.</span></span> <span data-ttu-id="b750f-152">可能的值包括："Accounts"、"Application"、"Network"、"OS"、"SecurityStack"</span><span class="sxs-lookup"><span data-stu-id="b750f-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="b750f-153">subCategory</span><span class="sxs-lookup"><span data-stu-id="b750f-153">subCategory</span></span> | <span data-ttu-id="b750f-154">String</span><span class="sxs-lookup"><span data-stu-id="b750f-154">String</span></span> | <span data-ttu-id="b750f-155">建议子类别</span><span class="sxs-lookup"><span data-stu-id="b750f-155">Recommendation sub-category</span></span>
<span data-ttu-id="b750f-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="b750f-156">severityScore</span></span> | <span data-ttu-id="b750f-157">双精度</span><span class="sxs-lookup"><span data-stu-id="b750f-157">Double</span></span> | <span data-ttu-id="b750f-158">配置对组织的 Microsoft 设备安全分数的潜在影响 (1-10) </span><span class="sxs-lookup"><span data-stu-id="b750f-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="b750f-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="b750f-159">publicExploit</span></span> | <span data-ttu-id="b750f-160">Boolean</span><span class="sxs-lookup"><span data-stu-id="b750f-160">Boolean</span></span> | <span data-ttu-id="b750f-161">公共攻击可用</span><span class="sxs-lookup"><span data-stu-id="b750f-161">Public exploit is available</span></span> 
<span data-ttu-id="b750f-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="b750f-162">activeAlert</span></span> | <span data-ttu-id="b750f-163">Boolean</span><span class="sxs-lookup"><span data-stu-id="b750f-163">Boolean</span></span> | <span data-ttu-id="b750f-164">活动警报与此建议关联</span><span class="sxs-lookup"><span data-stu-id="b750f-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="b750f-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="b750f-165">associatedThreats</span></span> | <span data-ttu-id="b750f-166">String collection</span><span class="sxs-lookup"><span data-stu-id="b750f-166">String collection</span></span> | <span data-ttu-id="b750f-167">威胁分析报告与此建议关联</span><span class="sxs-lookup"><span data-stu-id="b750f-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="b750f-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="b750f-168">remediationType</span></span> | <span data-ttu-id="b750f-169">String</span><span class="sxs-lookup"><span data-stu-id="b750f-169">String</span></span> | <span data-ttu-id="b750f-170">修正类型。</span><span class="sxs-lookup"><span data-stu-id="b750f-170">Remediation type.</span></span> <span data-ttu-id="b750f-171">可能的值是："ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"</span><span class="sxs-lookup"><span data-stu-id="b750f-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="b750f-172">状态</span><span class="sxs-lookup"><span data-stu-id="b750f-172">Status</span></span> | <span data-ttu-id="b750f-173">枚举</span><span class="sxs-lookup"><span data-stu-id="b750f-173">Enum</span></span> | <span data-ttu-id="b750f-174">建议例外状态。</span><span class="sxs-lookup"><span data-stu-id="b750f-174">Recommendation exception status.</span></span> <span data-ttu-id="b750f-175">可能的值是："Active"和"Exception"</span><span class="sxs-lookup"><span data-stu-id="b750f-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="b750f-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="b750f-176">configScoreImpact</span></span> | <span data-ttu-id="b750f-177">双精度</span><span class="sxs-lookup"><span data-stu-id="b750f-177">Double</span></span> | <span data-ttu-id="b750f-178">Microsoft 设备影响安全分数</span><span class="sxs-lookup"><span data-stu-id="b750f-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="b750f-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="b750f-179">exposureImpacte</span></span> | <span data-ttu-id="b750f-180">双精度</span><span class="sxs-lookup"><span data-stu-id="b750f-180">Double</span></span> | <span data-ttu-id="b750f-181">曝光分数影响</span><span class="sxs-lookup"><span data-stu-id="b750f-181">Exposure score impact</span></span>
<span data-ttu-id="b750f-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="b750f-182">totalMachineCount</span></span> | <span data-ttu-id="b750f-183">长型</span><span class="sxs-lookup"><span data-stu-id="b750f-183">Long</span></span> | <span data-ttu-id="b750f-184">已安装设备的数量</span><span class="sxs-lookup"><span data-stu-id="b750f-184">Number of installed devices</span></span>
<span data-ttu-id="b750f-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="b750f-185">exposedMachinesCount</span></span> | <span data-ttu-id="b750f-186">长型</span><span class="sxs-lookup"><span data-stu-id="b750f-186">Long</span></span> | <span data-ttu-id="b750f-187">向漏洞公开的已安装设备的数量</span><span class="sxs-lookup"><span data-stu-id="b750f-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="b750f-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="b750f-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="b750f-189">长型</span><span class="sxs-lookup"><span data-stu-id="b750f-189">Long</span></span> | <span data-ttu-id="b750f-190">不受影响的设备数量</span><span class="sxs-lookup"><span data-stu-id="b750f-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="b750f-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="b750f-191">relatedComponent</span></span> | <span data-ttu-id="b750f-192">String</span><span class="sxs-lookup"><span data-stu-id="b750f-192">String</span></span> |  <span data-ttu-id="b750f-193">相关软件组件</span><span class="sxs-lookup"><span data-stu-id="b750f-193">Related software component</span></span>
