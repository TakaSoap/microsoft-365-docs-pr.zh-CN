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
# <a name="recommendation-resource-type"></a><span data-ttu-id="9e55a-104">建议资源类型</span><span class="sxs-lookup"><span data-stu-id="9e55a-104">Recommendation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e55a-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9e55a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="9e55a-106">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="9e55a-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9e55a-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="9e55a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="9e55a-108">方法</span><span class="sxs-lookup"><span data-stu-id="9e55a-108">Methods</span></span>
<span data-ttu-id="9e55a-109">方法</span><span class="sxs-lookup"><span data-stu-id="9e55a-109">Method</span></span> |<span data-ttu-id="9e55a-110">返回类型</span><span class="sxs-lookup"><span data-stu-id="9e55a-110">Return Type</span></span> |<span data-ttu-id="9e55a-111">说明</span><span class="sxs-lookup"><span data-stu-id="9e55a-111">Description</span></span>
:---|:---|:---
[<span data-ttu-id="9e55a-112">列出所有建议</span><span class="sxs-lookup"><span data-stu-id="9e55a-112">List all recommendations</span></span>](get-all-recommendations.md) | <span data-ttu-id="9e55a-113">建议集合</span><span class="sxs-lookup"><span data-stu-id="9e55a-113">Recommendation collection</span></span> | <span data-ttu-id="9e55a-114">检索影响组织的所有安全建议的列表</span><span class="sxs-lookup"><span data-stu-id="9e55a-114">Retrieves a list of all security recommendations affecting the organization</span></span>
[<span data-ttu-id="9e55a-115">按 Id 获取建议</span><span class="sxs-lookup"><span data-stu-id="9e55a-115">Get recommendation by Id</span></span>](get-recommendation-by-id.md) | <span data-ttu-id="9e55a-116">建议</span><span class="sxs-lookup"><span data-stu-id="9e55a-116">Recommendation</span></span> | <span data-ttu-id="9e55a-117">按 ID 检索安全建议</span><span class="sxs-lookup"><span data-stu-id="9e55a-117">Retrieves a security recommendation by its ID</span></span>
[<span data-ttu-id="9e55a-118">获取建议软件</span><span class="sxs-lookup"><span data-stu-id="9e55a-118">Get recommendation software</span></span>](get-recommendation-software.md)| [<span data-ttu-id="9e55a-119">软件</span><span class="sxs-lookup"><span data-stu-id="9e55a-119">Software</span></span>](software.md) | <span data-ttu-id="9e55a-120">检索与特定软件相关的安全建议</span><span class="sxs-lookup"><span data-stu-id="9e55a-120">Retrieves a security recommendation related to a specific software</span></span>
[<span data-ttu-id="9e55a-121">获取建议设备</span><span class="sxs-lookup"><span data-stu-id="9e55a-121">Get recommendation devices</span></span>](get-recommendation-machines.md)|<span data-ttu-id="9e55a-122">MachineRef 集合</span><span class="sxs-lookup"><span data-stu-id="9e55a-122">MachineRef collection</span></span> | <span data-ttu-id="9e55a-123">检索与安全建议关联的设备列表</span><span class="sxs-lookup"><span data-stu-id="9e55a-123">Retrieves a list of devices associated with the security recommendation</span></span>
[<span data-ttu-id="9e55a-124">获取建议漏洞</span><span class="sxs-lookup"><span data-stu-id="9e55a-124">Get recommendation vulnerabilities</span></span>](get-recommendation-vulnerabilities.md) | <span data-ttu-id="9e55a-125">[漏洞](vulnerability.md) 集合</span><span class="sxs-lookup"><span data-stu-id="9e55a-125">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="9e55a-126">检索与安全建议关联的漏洞列表</span><span class="sxs-lookup"><span data-stu-id="9e55a-126">Retrieves a list of vulnerabilities associated with the security recommendation</span></span>


## <a name="properties"></a><span data-ttu-id="9e55a-127">属性</span><span class="sxs-lookup"><span data-stu-id="9e55a-127">Properties</span></span>
<span data-ttu-id="9e55a-128">属性</span><span class="sxs-lookup"><span data-stu-id="9e55a-128">Property</span></span> |   <span data-ttu-id="9e55a-129">类型</span><span class="sxs-lookup"><span data-stu-id="9e55a-129">Type</span></span>   |   <span data-ttu-id="9e55a-130">说明</span><span class="sxs-lookup"><span data-stu-id="9e55a-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="9e55a-131">id</span><span class="sxs-lookup"><span data-stu-id="9e55a-131">id</span></span> | <span data-ttu-id="9e55a-132">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-132">String</span></span> | <span data-ttu-id="9e55a-133">建议 ID</span><span class="sxs-lookup"><span data-stu-id="9e55a-133">Recommendation ID</span></span>
<span data-ttu-id="9e55a-134">productName</span><span class="sxs-lookup"><span data-stu-id="9e55a-134">productName</span></span> | <span data-ttu-id="9e55a-135">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-135">String</span></span> | <span data-ttu-id="9e55a-136">相关软件名称</span><span class="sxs-lookup"><span data-stu-id="9e55a-136">Related software name</span></span>  
<span data-ttu-id="9e55a-137">recommendationName</span><span class="sxs-lookup"><span data-stu-id="9e55a-137">recommendationName</span></span> | <span data-ttu-id="9e55a-138">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-138">String</span></span> | <span data-ttu-id="9e55a-139">建议名称</span><span class="sxs-lookup"><span data-stu-id="9e55a-139">Recommendation name</span></span>
<span data-ttu-id="9e55a-140">漏洞</span><span class="sxs-lookup"><span data-stu-id="9e55a-140">Weaknesses</span></span> | <span data-ttu-id="9e55a-141">长型</span><span class="sxs-lookup"><span data-stu-id="9e55a-141">Long</span></span> | <span data-ttu-id="9e55a-142">发现的漏洞数量</span><span class="sxs-lookup"><span data-stu-id="9e55a-142">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="9e55a-143">供应商</span><span class="sxs-lookup"><span data-stu-id="9e55a-143">Vendor</span></span> | <span data-ttu-id="9e55a-144">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-144">String</span></span> | <span data-ttu-id="9e55a-145">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="9e55a-145">Related vendor name</span></span>
<span data-ttu-id="9e55a-146">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="9e55a-146">recommendedVersion</span></span> | <span data-ttu-id="9e55a-147">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-147">String</span></span> | <span data-ttu-id="9e55a-148">建议版本</span><span class="sxs-lookup"><span data-stu-id="9e55a-148">Recommended version</span></span>
<span data-ttu-id="9e55a-149">recommendationCategory</span><span class="sxs-lookup"><span data-stu-id="9e55a-149">recommendationCategory</span></span> | <span data-ttu-id="9e55a-150">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-150">String</span></span> | <span data-ttu-id="9e55a-151">建议类别。</span><span class="sxs-lookup"><span data-stu-id="9e55a-151">Recommendation category.</span></span> <span data-ttu-id="9e55a-152">可能的值包括："Accounts"、"Application"、"Network"、"OS"、"SecurityStack"</span><span class="sxs-lookup"><span data-stu-id="9e55a-152">Possible values are: "Accounts", "Application", "Network", "OS", "SecurityStack</span></span>
<span data-ttu-id="9e55a-153">subCategory</span><span class="sxs-lookup"><span data-stu-id="9e55a-153">subCategory</span></span> | <span data-ttu-id="9e55a-154">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-154">String</span></span> | <span data-ttu-id="9e55a-155">建议子类别</span><span class="sxs-lookup"><span data-stu-id="9e55a-155">Recommendation sub-category</span></span>
<span data-ttu-id="9e55a-156">severityScore</span><span class="sxs-lookup"><span data-stu-id="9e55a-156">severityScore</span></span> | <span data-ttu-id="9e55a-157">双精度</span><span class="sxs-lookup"><span data-stu-id="9e55a-157">Double</span></span> | <span data-ttu-id="9e55a-158">配置对组织的 Microsoft 设备安全分数的潜在影响 (1-10) </span><span class="sxs-lookup"><span data-stu-id="9e55a-158">Potential impact of the configuration to the organization's Microsoft Secure Score for Devices (1-10)</span></span>
<span data-ttu-id="9e55a-159">publicExploit</span><span class="sxs-lookup"><span data-stu-id="9e55a-159">publicExploit</span></span> | <span data-ttu-id="9e55a-160">Boolean</span><span class="sxs-lookup"><span data-stu-id="9e55a-160">Boolean</span></span> | <span data-ttu-id="9e55a-161">公共攻击可用</span><span class="sxs-lookup"><span data-stu-id="9e55a-161">Public exploit is available</span></span> 
<span data-ttu-id="9e55a-162">activeAlert</span><span class="sxs-lookup"><span data-stu-id="9e55a-162">activeAlert</span></span> | <span data-ttu-id="9e55a-163">Boolean</span><span class="sxs-lookup"><span data-stu-id="9e55a-163">Boolean</span></span> | <span data-ttu-id="9e55a-164">活动警报与此建议关联</span><span class="sxs-lookup"><span data-stu-id="9e55a-164">Active alert is associated with this recommendation</span></span>
<span data-ttu-id="9e55a-165">associatedThreats</span><span class="sxs-lookup"><span data-stu-id="9e55a-165">associatedThreats</span></span> | <span data-ttu-id="9e55a-166">String collection</span><span class="sxs-lookup"><span data-stu-id="9e55a-166">String collection</span></span> | <span data-ttu-id="9e55a-167">威胁分析报告与此建议关联</span><span class="sxs-lookup"><span data-stu-id="9e55a-167">Threat analytics report is associated with this recommendation</span></span>
<span data-ttu-id="9e55a-168">remediationType</span><span class="sxs-lookup"><span data-stu-id="9e55a-168">remediationType</span></span> | <span data-ttu-id="9e55a-169">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-169">String</span></span> | <span data-ttu-id="9e55a-170">修正类型。</span><span class="sxs-lookup"><span data-stu-id="9e55a-170">Remediation type.</span></span> <span data-ttu-id="9e55a-171">可能的值是："ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"</span><span class="sxs-lookup"><span data-stu-id="9e55a-171">Possible values are: "ConfigurationChange","Update","Upgrade","Uninstall"</span></span>
<span data-ttu-id="9e55a-172">状态</span><span class="sxs-lookup"><span data-stu-id="9e55a-172">Status</span></span> | <span data-ttu-id="9e55a-173">枚举</span><span class="sxs-lookup"><span data-stu-id="9e55a-173">Enum</span></span> | <span data-ttu-id="9e55a-174">建议例外状态。</span><span class="sxs-lookup"><span data-stu-id="9e55a-174">Recommendation exception status.</span></span> <span data-ttu-id="9e55a-175">可能的值是："Active"和"Exception"</span><span class="sxs-lookup"><span data-stu-id="9e55a-175">Possible values are: "Active" and "Exception"</span></span>
<span data-ttu-id="9e55a-176">configScoreImpact</span><span class="sxs-lookup"><span data-stu-id="9e55a-176">configScoreImpact</span></span> | <span data-ttu-id="9e55a-177">双精度</span><span class="sxs-lookup"><span data-stu-id="9e55a-177">Double</span></span> | <span data-ttu-id="9e55a-178">Microsoft 设备影响安全分数</span><span class="sxs-lookup"><span data-stu-id="9e55a-178">Microsoft Secure Score for Devices impact</span></span>
<span data-ttu-id="9e55a-179">exposureImpacte</span><span class="sxs-lookup"><span data-stu-id="9e55a-179">exposureImpacte</span></span> | <span data-ttu-id="9e55a-180">双精度</span><span class="sxs-lookup"><span data-stu-id="9e55a-180">Double</span></span> | <span data-ttu-id="9e55a-181">曝光分数影响</span><span class="sxs-lookup"><span data-stu-id="9e55a-181">Exposure score impact</span></span>
<span data-ttu-id="9e55a-182">totalMachineCount</span><span class="sxs-lookup"><span data-stu-id="9e55a-182">totalMachineCount</span></span> | <span data-ttu-id="9e55a-183">长型</span><span class="sxs-lookup"><span data-stu-id="9e55a-183">Long</span></span> | <span data-ttu-id="9e55a-184">已安装设备的数量</span><span class="sxs-lookup"><span data-stu-id="9e55a-184">Number of installed devices</span></span>
<span data-ttu-id="9e55a-185">exposedMachinesCount</span><span class="sxs-lookup"><span data-stu-id="9e55a-185">exposedMachinesCount</span></span> | <span data-ttu-id="9e55a-186">长型</span><span class="sxs-lookup"><span data-stu-id="9e55a-186">Long</span></span> | <span data-ttu-id="9e55a-187">向漏洞公开的已安装设备的数量</span><span class="sxs-lookup"><span data-stu-id="9e55a-187">Number of installed devices that are exposed to vulnerabilities</span></span>
<span data-ttu-id="9e55a-188">nonProductivityImpactedAssets</span><span class="sxs-lookup"><span data-stu-id="9e55a-188">nonProductivityImpactedAssets</span></span> | <span data-ttu-id="9e55a-189">长型</span><span class="sxs-lookup"><span data-stu-id="9e55a-189">Long</span></span> | <span data-ttu-id="9e55a-190">不受影响的设备数量</span><span class="sxs-lookup"><span data-stu-id="9e55a-190">Number of devices which are not affected</span></span>  
<span data-ttu-id="9e55a-191">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="9e55a-191">relatedComponent</span></span> | <span data-ttu-id="9e55a-192">String</span><span class="sxs-lookup"><span data-stu-id="9e55a-192">String</span></span> |  <span data-ttu-id="9e55a-193">相关软件组件</span><span class="sxs-lookup"><span data-stu-id="9e55a-193">Related software component</span></span>
