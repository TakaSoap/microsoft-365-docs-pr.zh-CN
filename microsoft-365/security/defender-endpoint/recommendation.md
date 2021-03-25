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
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198229"
---
# <a name="recommendation-resource-type"></a><span data-ttu-id="7d1f8-104">建议资源类型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7d1f8-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7d1f8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="7d1f8-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="7d1f8-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d1f8-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7d1f8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="7d1f8-108">方法</span><span class="sxs-lookup"><span data-stu-id="7d1f8-108">Methods</span></span>
<span data-ttu-id="7d1f8-109">方法</span><span class="sxs-lookup"><span data-stu-id="7d1f8-109">Method</span></span> |<span data-ttu-id="7d1f8-110">返回类型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-110">Return Type</span></span> |<span data-ttu-id="7d1f8-111">说明</span><span class="sxs-lookup"><span data-stu-id="7d1f8-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="7d1f8-112">列出所有建议</span><span class="sxs-lookup"><span data-stu-id="7d1f8-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="7d1f8-113">建议集合</span><span class="sxs-lookup"><span data-stu-id="7d1f8-113">Recommendation collection</span></span> | <span data-ttu-id="7d1f8-114">检索影响组织的所有安全建议的列表</span><span class="sxs-lookup"><span data-stu-id="7d1f8-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="7d1f8-115">按 Id 获取建议</span><span class="sxs-lookup"><span data-stu-id="7d1f8-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="7d1f8-116">建议</span><span class="sxs-lookup"><span data-stu-id="7d1f8-116">Recommendation</span></span> | <span data-ttu-id="7d1f8-117">按 ID 检索安全建议</span><span class="sxs-lookup"><span data-stu-id="7d1f8-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="7d1f8-118">获取建议软件</span><span class="sxs-lookup"><span data-stu-id="7d1f8-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="7d1f8-119">软件</span><span class="sxs-lookup"><span data-stu-id="7d1f8-119">Software</span></span>](software.md) | <span data-ttu-id="7d1f8-120">检索与特定软件相关的安全建议</span><span class="sxs-lookup"><span data-stu-id="7d1f8-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="7d1f8-121">获取建议设备</span><span class="sxs-lookup"><span data-stu-id="7d1f8-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="7d1f8-122">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="7d1f8-122">MachineRef collection</span></span> | <span data-ttu-id="7d1f8-123">检索与安全建议关联的设备列表</span><span class="sxs-lookup"><span data-stu-id="7d1f8-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="7d1f8-124">获取建议漏洞</span><span class="sxs-lookup"><span data-stu-id="7d1f8-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="7d1f8-125">[漏洞](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="7d1f8-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="7d1f8-126">检索与安全建议关联的漏洞列表</span><span class="sxs-lookup"><span data-stu-id="7d1f8-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="7d1f8-127">属性</span><span class="sxs-lookup"><span data-stu-id="7d1f8-127">Properties</span></span>
<span data-ttu-id="7d1f8-128">属性</span><span class="sxs-lookup"><span data-stu-id="7d1f8-128">Property</span></span> |   <span data-ttu-id="7d1f8-129">类型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-129">Type</span></span>   |   <span data-ttu-id="7d1f8-130">说明</span><span class="sxs-lookup"><span data-stu-id="7d1f8-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="7d1f8-131">id</span><span class="sxs-lookup"><span data-stu-id="7d1f8-131">id</span></span> | <span data-ttu-id="7d1f8-132">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-132">String</span></span> | <span data-ttu-id="7d1f8-133">建议 ID</span><span class="sxs-lookup"><span data-stu-id="7d1f8-133">Recommendation ID</span></span>
<span data-ttu-id="7d1f8-134">productName</span><span class="sxs-lookup"><span data-stu-id="7d1f8-134">productName</span></span> | <span data-ttu-id="7d1f8-135">String</span><span class="sxs-lookup"><span data-stu-id="7d1f8-135">String</span></span> | <span data-ttu-id="7d1f8-136">相关软件名称</span><span class="sxs-lookup"><span data-stu-id="7d1f8-136">Related software name</span></span>  
<span data-ttu-id="7d1f8-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="7d1f8-137">recommendationName</span></span> | <span data-ttu-id="7d1f8-138">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-138">String</span></span> | <span data-ttu-id="7d1f8-139">建议名称</span><span class="sxs-lookup"><span data-stu-id="7d1f8-139">Recommendation name</span></span>
<span data-ttu-id="7d1f8-140">漏洞</span><span class="sxs-lookup"><span data-stu-id="7d1f8-140">Weaknesses</span></span> | <span data-ttu-id="7d1f8-141">长型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-141">Long</span></span> | <span data-ttu-id="7d1f8-142">发现的漏洞数量</span><span class="sxs-lookup"><span data-stu-id="7d1f8-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="7d1f8-143">供应商</span><span class="sxs-lookup"><span data-stu-id="7d1f8-143">Vendor</span></span> | <span data-ttu-id="7d1f8-144">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-144">String</span></span> | <span data-ttu-id="7d1f8-145">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="7d1f8-145">Related vendor name</span></span>
<span data-ttu-id="7d1f8-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="7d1f8-146">recommendedVersion</span></span> | <span data-ttu-id="7d1f8-147">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-147">String</span></span> | <span data-ttu-id="7d1f8-148">建议版本</span><span class="sxs-lookup"><span data-stu-id="7d1f8-148">Recommended version</span></span>
<span data-ttu-id="7d1f8-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="7d1f8-149">recommendationCategory</span></span> | <span data-ttu-id="7d1f8-150">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-150">String</span></span> | <span data-ttu-id="7d1f8-151">建议类别。</span><span class="sxs-lookup"><span data-stu-id="7d1f8-151">Recommendation category.</span></span> <span data-ttu-id="7d1f8-152">可能的值包括："Accounts"、"Application"、"Network"、"OS"、"SecurityStack"</span><span class="sxs-lookup"><span data-stu-id="7d1f8-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="7d1f8-153">subCategory</span><span class="sxs-lookup"><span data-stu-id="7d1f8-153">subCategory</span></span> | <span data-ttu-id="7d1f8-154">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-154">String</span></span> | <span data-ttu-id="7d1f8-155">建议子类别</span><span class="sxs-lookup"><span data-stu-id="7d1f8-155">Recommendation sub-category</span></span>
<span data-ttu-id="7d1f8-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="7d1f8-156">severityScore</span></span> | <span data-ttu-id="7d1f8-157">双精度</span><span class="sxs-lookup"><span data-stu-id="7d1f8-157">Double</span></span> | <span data-ttu-id="7d1f8-158">配置对组织的 Microsoft 设备安全分数的潜在影响 (1-10) </span><span class="sxs-lookup"><span data-stu-id="7d1f8-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="7d1f8-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="7d1f8-159">publicExploit</span></span> | <span data-ttu-id="7d1f8-160">布尔值</span><span class="sxs-lookup"><span data-stu-id="7d1f8-160">Boolean</span></span> | <span data-ttu-id="7d1f8-161">公共攻击可用</span><span class="sxs-lookup"><span data-stu-id="7d1f8-161">Public exploit is available</span></span> 
<span data-ttu-id="7d1f8-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="7d1f8-162">activeAlert</span></span> | <span data-ttu-id="7d1f8-163">布尔值</span><span class="sxs-lookup"><span data-stu-id="7d1f8-163">Boolean</span></span> | <span data-ttu-id="7d1f8-164">活动警报与此建议关联</span><span class="sxs-lookup"><span data-stu-id="7d1f8-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="7d1f8-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="7d1f8-165">associatedThreats</span></span> | <span data-ttu-id="7d1f8-166">String collection</span><span class="sxs-lookup"><span data-stu-id="7d1f8-166">String collection</span></span> | <span data-ttu-id="7d1f8-167">威胁分析报告与此建议关联</span><span class="sxs-lookup"><span data-stu-id="7d1f8-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="7d1f8-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="7d1f8-168">remediationType</span></span> | <span data-ttu-id="7d1f8-169">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-169">String</span></span> | <span data-ttu-id="7d1f8-170">修正类型。</span><span class="sxs-lookup"><span data-stu-id="7d1f8-170">Remediation type.</span></span> <span data-ttu-id="7d1f8-171">可能的值是："ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"</span><span class="sxs-lookup"><span data-stu-id="7d1f8-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="7d1f8-172">状态</span><span class="sxs-lookup"><span data-stu-id="7d1f8-172">Status</span></span> | <span data-ttu-id="7d1f8-173">枚举</span><span class="sxs-lookup"><span data-stu-id="7d1f8-173">Enum</span></span> | <span data-ttu-id="7d1f8-174">建议例外状态。</span><span class="sxs-lookup"><span data-stu-id="7d1f8-174">Recommendation exception status.</span></span> <span data-ttu-id="7d1f8-175">可能的值是："Active"和"Exception"</span><span class="sxs-lookup"><span data-stu-id="7d1f8-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="7d1f8-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="7d1f8-176">configScoreImpact</span></span> | <span data-ttu-id="7d1f8-177">双精度</span><span class="sxs-lookup"><span data-stu-id="7d1f8-177">Double</span></span> | <span data-ttu-id="7d1f8-178">Microsoft 设备影响安全分数</span><span class="sxs-lookup"><span data-stu-id="7d1f8-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="7d1f8-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="7d1f8-179">exposureImpacte</span></span> | <span data-ttu-id="7d1f8-180">双精度</span><span class="sxs-lookup"><span data-stu-id="7d1f8-180">Double</span></span> | <span data-ttu-id="7d1f8-181">曝光分数影响</span><span class="sxs-lookup"><span data-stu-id="7d1f8-181">Exposure score impact</span></span>
<span data-ttu-id="7d1f8-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="7d1f8-182">totalMachineCount</span></span> | <span data-ttu-id="7d1f8-183">长型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-183">Long</span></span> | <span data-ttu-id="7d1f8-184">已安装设备的数量</span><span class="sxs-lookup"><span data-stu-id="7d1f8-184">Number of installed devices</span></span>
<span data-ttu-id="7d1f8-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="7d1f8-185">exposedMachinesCount</span></span> | <span data-ttu-id="7d1f8-186">长型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-186">Long</span></span> | <span data-ttu-id="7d1f8-187">向漏洞公开的已安装设备的数量</span><span class="sxs-lookup"><span data-stu-id="7d1f8-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="7d1f8-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="7d1f8-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="7d1f8-189">长型</span><span class="sxs-lookup"><span data-stu-id="7d1f8-189">Long</span></span> | <span data-ttu-id="7d1f8-190">不受影响的设备数量</span><span class="sxs-lookup"><span data-stu-id="7d1f8-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="7d1f8-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="7d1f8-191">relatedComponent</span></span> | <span data-ttu-id="7d1f8-192">字符串</span><span class="sxs-lookup"><span data-stu-id="7d1f8-192">String</span></span> |  <span data-ttu-id="7d1f8-193">相关软件组件</span><span class="sxs-lookup"><span data-stu-id="7d1f8-193">Related software component</span></span>
