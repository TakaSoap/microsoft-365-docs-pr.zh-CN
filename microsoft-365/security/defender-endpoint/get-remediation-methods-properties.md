---
title: 修正活动方法和属性
description: API 响应包含威胁& 漏洞管理租户中创建的修正活动。 你可以为选定的修正任务请求所有修正活动、仅一个修正活动或有关公开的设备的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 修正方法， 修正属性，
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4c0ecd89c45ec2c91dc37f0c9cd0bfb868c0474e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245536"
---
# <a name="remediation-activity-methods-and-properties"></a><span data-ttu-id="f5fd3-105">修正活动方法和属性</span><span class="sxs-lookup"><span data-stu-id="f5fd3-105">Remediation activity methods and properties</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5fd3-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f5fd3-106">**Applies to:**</span></span>

- [<span data-ttu-id="f5fd3-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f5fd3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f5fd3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5fd3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f5fd3-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f5fd3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5fd3-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f5fd3-111">API 响应包含 [& 漏洞管理](next-gen-threat-and-vuln-mgt.md)   租户中创建的威胁和修正活动。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-111">The API response contains [Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md) remediation activities that have been created in your tenant.</span></span>  

## <a name="methods"></a><span data-ttu-id="f5fd3-112">方法</span><span class="sxs-lookup"><span data-stu-id="f5fd3-112">Methods</span></span>

<span data-ttu-id="f5fd3-113">方法</span><span class="sxs-lookup"><span data-stu-id="f5fd3-113">Method</span></span> | <span data-ttu-id="f5fd3-114">数据类型</span><span class="sxs-lookup"><span data-stu-id="f5fd3-114">Data type</span></span> | <span data-ttu-id="f5fd3-115">说明</span><span class="sxs-lookup"><span data-stu-id="f5fd3-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f5fd3-116">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="f5fd3-116">List all remediation activities</span></span>](get-remediation-all-activities.md) | <span data-ttu-id="f5fd3-117">调查集合</span><span class="sxs-lookup"><span data-stu-id="f5fd3-117">Investigation collection</span></span> | <span data-ttu-id="f5fd3-118">返回有关所有修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-118">Returns information about all remediation activities.</span></span>
[<span data-ttu-id="f5fd3-119">列出一个修正活动的公开设备</span><span class="sxs-lookup"><span data-stu-id="f5fd3-119">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md) | <span data-ttu-id="f5fd3-120">调查实体</span><span class="sxs-lookup"><span data-stu-id="f5fd3-120">Investigation entity</span></span> | <span data-ttu-id="f5fd3-121">返回有关指定修正活动的公开设备的信息。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-121">Returns information about exposed devices for the specified remediation activity.</span></span>
[<span data-ttu-id="f5fd3-122">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="f5fd3-122">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md) | <span data-ttu-id="f5fd3-123">调查实体</span><span class="sxs-lookup"><span data-stu-id="f5fd3-123">Investigation entity</span></span> | <span data-ttu-id="f5fd3-124">返回指定修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-124">Returns information for the specified remediation activity.</span></span>

<span data-ttu-id="f5fd3-125">详细了解修正 [活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-125">Learn more about [remediation activities](tvm-remediation.md).</span></span>

## <a name="properties"></a><span data-ttu-id="f5fd3-126">属性</span><span class="sxs-lookup"><span data-stu-id="f5fd3-126">Properties</span></span>

<span data-ttu-id="f5fd3-127">属性 ID</span><span class="sxs-lookup"><span data-stu-id="f5fd3-127">Property id</span></span> | <span data-ttu-id="f5fd3-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="f5fd3-128">Data type</span></span> | <span data-ttu-id="f5fd3-129">说明</span><span class="sxs-lookup"><span data-stu-id="f5fd3-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="f5fd3-130">“类别”</span><span class="sxs-lookup"><span data-stu-id="f5fd3-130">category</span></span> | <span data-ttu-id="f5fd3-131">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-131">String</span></span> | <span data-ttu-id="f5fd3-132">软件/安全配置 (修正活动的) </span><span class="sxs-lookup"><span data-stu-id="f5fd3-132">Category of the remediation activity (Software/Security configuration)</span></span>
<span data-ttu-id="f5fd3-133">completerEmail</span><span class="sxs-lookup"><span data-stu-id="f5fd3-133">completerEmail</span></span> | <span data-ttu-id="f5fd3-134">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-134">String</span></span> | <span data-ttu-id="f5fd3-135">如果修正活动是由某人手动完成的，此列将包含他们的电子邮件</span><span class="sxs-lookup"><span data-stu-id="f5fd3-135">If the remediation activity was manually completed by someone, this column contains their email</span></span>
<span data-ttu-id="f5fd3-136">completerId</span><span class="sxs-lookup"><span data-stu-id="f5fd3-136">completerId</span></span> | <span data-ttu-id="f5fd3-137">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-137">String</span></span> | <span data-ttu-id="f5fd3-138">如果修正活动是由某人手动完成的，则此列包含其对象 ID</span><span class="sxs-lookup"><span data-stu-id="f5fd3-138">If the remediation activity was manually completed by someone, this column contains their object id</span></span>
<span data-ttu-id="f5fd3-139">completionMethod</span><span class="sxs-lookup"><span data-stu-id="f5fd3-139">completionMethod</span></span> | <span data-ttu-id="f5fd3-140">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-140">String</span></span> | <span data-ttu-id="f5fd3-141">如果由 (选择"标记为已完成") 或"手动"修补所有设备，则修正活动可以"自动"完成。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-141">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed.”</span></span>
<span data-ttu-id="f5fd3-142">createdOn</span><span class="sxs-lookup"><span data-stu-id="f5fd3-142">createdOn</span></span> | <span data-ttu-id="f5fd3-143">日期时间</span><span class="sxs-lookup"><span data-stu-id="f5fd3-143">DateTime</span></span> | <span data-ttu-id="f5fd3-144">创建此修正活动的时间</span><span class="sxs-lookup"><span data-stu-id="f5fd3-144">Time this remediation activity was created</span></span>
<span data-ttu-id="f5fd3-145">说明</span><span class="sxs-lookup"><span data-stu-id="f5fd3-145">description</span></span> | <span data-ttu-id="f5fd3-146">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-146">String</span></span> | <span data-ttu-id="f5fd3-147">此修正活动的说明</span><span class="sxs-lookup"><span data-stu-id="f5fd3-147">Description of this remediation activity</span></span>
<span data-ttu-id="f5fd3-148">dueOn</span><span class="sxs-lookup"><span data-stu-id="f5fd3-148">dueOn</span></span> | <span data-ttu-id="f5fd3-149">日期时间</span><span class="sxs-lookup"><span data-stu-id="f5fd3-149">DateTime</span></span> | <span data-ttu-id="f5fd3-150">此修正活动的创建者设置的截止日期</span><span class="sxs-lookup"><span data-stu-id="f5fd3-150">Due date the creator set for this remediation activity</span></span>
<span data-ttu-id="f5fd3-151">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="f5fd3-151">fixedDevices</span></span> |  | <span data-ttu-id="f5fd3-152">已修复的设备数量</span><span class="sxs-lookup"><span data-stu-id="f5fd3-152">The number of devices that have been fixed</span></span>
<span data-ttu-id="f5fd3-153">id</span><span class="sxs-lookup"><span data-stu-id="f5fd3-153">id</span></span> | <span data-ttu-id="f5fd3-154">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-154">String</span></span> | <span data-ttu-id="f5fd3-155">此修正活动的 ID</span><span class="sxs-lookup"><span data-stu-id="f5fd3-155">ID of this remediation activity</span></span>
<span data-ttu-id="f5fd3-156">nameId</span><span class="sxs-lookup"><span data-stu-id="f5fd3-156">nameId</span></span> | <span data-ttu-id="f5fd3-157">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-157">String</span></span> | <span data-ttu-id="f5fd3-158">相关产品名称</span><span class="sxs-lookup"><span data-stu-id="f5fd3-158">Related product name</span></span>
<span data-ttu-id="f5fd3-159">priority</span><span class="sxs-lookup"><span data-stu-id="f5fd3-159">priority</span></span> | <span data-ttu-id="f5fd3-160">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-160">String</span></span> | <span data-ttu-id="f5fd3-161">为此修正活动设置的创建者设置的优先级 (高\中\低) </span><span class="sxs-lookup"><span data-stu-id="f5fd3-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span>
<span data-ttu-id="f5fd3-162">productId</span><span class="sxs-lookup"><span data-stu-id="f5fd3-162">productId</span></span> | <span data-ttu-id="f5fd3-163">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-163">String</span></span> | <span data-ttu-id="f5fd3-164">相关产品 ID</span><span class="sxs-lookup"><span data-stu-id="f5fd3-164">Related product ID</span></span>
<span data-ttu-id="f5fd3-165">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="f5fd3-165">productivityImpactRemediationType</span></span> | <span data-ttu-id="f5fd3-166">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-166">String</span></span> | <span data-ttu-id="f5fd3-167">只能请求对没有用户影响的设备进行一些配置更改。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-167">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="f5fd3-168">此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。</span><span class="sxs-lookup"><span data-stu-id="f5fd3-168">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span>
<span data-ttu-id="f5fd3-169">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="f5fd3-169">rbacGroupNames</span></span> | <span data-ttu-id="f5fd3-170">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-170">String</span></span> | <span data-ttu-id="f5fd3-171">相关设备组名称</span><span class="sxs-lookup"><span data-stu-id="f5fd3-171">Related device group names</span></span>
<span data-ttu-id="f5fd3-172">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="f5fd3-172">recommendedProgram</span></span> | <span data-ttu-id="f5fd3-173">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-173">String</span></span> | <span data-ttu-id="f5fd3-174">要升级到的推荐程序</span><span class="sxs-lookup"><span data-stu-id="f5fd3-174">Recommended program to upgrade to</span></span>
<span data-ttu-id="f5fd3-175">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="f5fd3-175">recommendedVendor</span></span> | <span data-ttu-id="f5fd3-176">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-176">String</span></span> | <span data-ttu-id="f5fd3-177">建议升级到的供应商</span><span class="sxs-lookup"><span data-stu-id="f5fd3-177">Recommended vendor to upgrade to</span></span>
<span data-ttu-id="f5fd3-178">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="f5fd3-178">recommendedVersion</span></span> | <span data-ttu-id="f5fd3-179">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-179">String</span></span> | <span data-ttu-id="f5fd3-180">要更新/升级到的建议版本</span><span class="sxs-lookup"><span data-stu-id="f5fd3-180">Recommended version to update/upgrade to</span></span>
<span data-ttu-id="f5fd3-181">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="f5fd3-181">relatedComponent</span></span> | <span data-ttu-id="f5fd3-182">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-182">String</span></span> | <span data-ttu-id="f5fd3-183">此修正活动的相关组件 (安全建议计划的相关组件) </span><span class="sxs-lookup"><span data-stu-id="f5fd3-183">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span>
<span data-ttu-id="f5fd3-184">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="f5fd3-184">requesterEmail</span></span> | <span data-ttu-id="f5fd3-185">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-185">String</span></span> | <span data-ttu-id="f5fd3-186">创建者电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f5fd3-186">Creator email address</span></span>
<span data-ttu-id="f5fd3-187">requesterId</span><span class="sxs-lookup"><span data-stu-id="f5fd3-187">requesterId</span></span> | <span data-ttu-id="f5fd3-188">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-188">String</span></span> | <span data-ttu-id="f5fd3-189">Creator 对象 ID</span><span class="sxs-lookup"><span data-stu-id="f5fd3-189">Creator object id</span></span>
<span data-ttu-id="f5fd3-190">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="f5fd3-190">requesterNotes</span></span> | <span data-ttu-id="f5fd3-191">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-191">String</span></span> | <span data-ttu-id="f5fd3-192">注释 (此) 活动的创建者添加的自定义文本</span><span class="sxs-lookup"><span data-stu-id="f5fd3-192">The notes (free text) the creator added for this remediation activity</span></span>
<span data-ttu-id="f5fd3-193">scid</span><span class="sxs-lookup"><span data-stu-id="f5fd3-193">scid</span></span> | <span data-ttu-id="f5fd3-194">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-194">String</span></span> | <span data-ttu-id="f5fd3-195">相关安全建议 SCID</span><span class="sxs-lookup"><span data-stu-id="f5fd3-195">SCID of the related security recommendation</span></span>
<span data-ttu-id="f5fd3-196">状态</span><span class="sxs-lookup"><span data-stu-id="f5fd3-196">status</span></span> | <span data-ttu-id="f5fd3-197">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-197">String</span></span> | <span data-ttu-id="f5fd3-198">修正活动状态 (/已完成) </span><span class="sxs-lookup"><span data-stu-id="f5fd3-198">Remediation activity status (Active/Completed)</span></span>
<span data-ttu-id="f5fd3-199">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="f5fd3-199">statusLastModifiedOn</span></span> | <span data-ttu-id="f5fd3-200">日期时间</span><span class="sxs-lookup"><span data-stu-id="f5fd3-200">DateTime</span></span> | <span data-ttu-id="f5fd3-201">更新状态字段的日期</span><span class="sxs-lookup"><span data-stu-id="f5fd3-201">Date when the status field was updated</span></span>
<span data-ttu-id="f5fd3-202">targetDevices</span><span class="sxs-lookup"><span data-stu-id="f5fd3-202">targetDevices</span></span> | <span data-ttu-id="f5fd3-203">长型</span><span class="sxs-lookup"><span data-stu-id="f5fd3-203">Long</span></span> | <span data-ttu-id="f5fd3-204">此修正适用于的公开设备数量</span><span class="sxs-lookup"><span data-stu-id="f5fd3-204">Number of exposed devices that this remediation is applicable to</span></span>
<span data-ttu-id="f5fd3-205">title</span><span class="sxs-lookup"><span data-stu-id="f5fd3-205">title</span></span> | <span data-ttu-id="f5fd3-206">String</span><span class="sxs-lookup"><span data-stu-id="f5fd3-206">String</span></span> | <span data-ttu-id="f5fd3-207">此修正活动的标题</span><span class="sxs-lookup"><span data-stu-id="f5fd3-207">Title of this remediation activity</span></span>
<span data-ttu-id="f5fd3-208">type</span><span class="sxs-lookup"><span data-stu-id="f5fd3-208">type</span></span> | <span data-ttu-id="f5fd3-209">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-209">String</span></span> | <span data-ttu-id="f5fd3-210">修正类型</span><span class="sxs-lookup"><span data-stu-id="f5fd3-210">Remediation type</span></span>
<span data-ttu-id="f5fd3-211">vendorId</span><span class="sxs-lookup"><span data-stu-id="f5fd3-211">vendorId</span></span> | <span data-ttu-id="f5fd3-212">字符串</span><span class="sxs-lookup"><span data-stu-id="f5fd3-212">String</span></span> | <span data-ttu-id="f5fd3-213">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="f5fd3-213">Related vendor name</span></span>

## <a name="see-also"></a><span data-ttu-id="f5fd3-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5fd3-214">See also</span></span>

- [<span data-ttu-id="f5fd3-215">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="f5fd3-215">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="f5fd3-216">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="f5fd3-216">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="f5fd3-217">列出一个修正活动的公开设备</span><span class="sxs-lookup"><span data-stu-id="f5fd3-217">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="f5fd3-218">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="f5fd3-218">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f5fd3-219">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="f5fd3-219">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
