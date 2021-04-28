---
title: 按 ID 获取一个修正活动
description: 返回指定修正活动的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 列表
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
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061100"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="15a85-104">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="15a85-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="15a85-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="15a85-105">**Applies to:**</span></span>

- [<span data-ttu-id="15a85-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="15a85-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15a85-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15a85-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="15a85-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="15a85-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15a85-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="15a85-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="15a85-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="15a85-110">API description</span></span>

<span data-ttu-id="15a85-111">返回指定修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="15a85-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="15a85-112">显示与获取 [所有修正活动](get-remediation-all-activities.md)相同的列，但仅返回一 _个指定的修正活动的结果_。</span><span class="sxs-lookup"><span data-stu-id="15a85-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="15a85-113">[详细了解修正活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="15a85-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="15a85-114">列出 id 指定的 (修正) </span><span class="sxs-lookup"><span data-stu-id="15a85-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="15a85-115">**URL：** GET： /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="15a85-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="15a85-116">**属性** 详细信息</span><span class="sxs-lookup"><span data-stu-id="15a85-116">**Properties** details</span></span>

<span data-ttu-id="15a85-117">属性 (id) </span><span class="sxs-lookup"><span data-stu-id="15a85-117">Property (id)</span></span> | <span data-ttu-id="15a85-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="15a85-118">Data type</span></span> | <span data-ttu-id="15a85-119">说明</span><span class="sxs-lookup"><span data-stu-id="15a85-119">Description</span></span> | <span data-ttu-id="15a85-120">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="15a85-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="15a85-121">“类别”</span><span class="sxs-lookup"><span data-stu-id="15a85-121">category</span></span> | <span data-ttu-id="15a85-122">String</span><span class="sxs-lookup"><span data-stu-id="15a85-122">String</span></span> | <span data-ttu-id="15a85-123">软件/安全配置 (修正活动的) </span><span class="sxs-lookup"><span data-stu-id="15a85-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="15a85-124">软件</span><span class="sxs-lookup"><span data-stu-id="15a85-124">Software</span></span>
<span data-ttu-id="15a85-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="15a85-125">completerEmail</span></span> | <span data-ttu-id="15a85-126">String</span><span class="sxs-lookup"><span data-stu-id="15a85-126">String</span></span> | <span data-ttu-id="15a85-127">如果修正活动是由某人手动完成的，此列将包含他们的电子邮件</span><span class="sxs-lookup"><span data-stu-id="15a85-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="15a85-128">空</span><span class="sxs-lookup"><span data-stu-id="15a85-128">null</span></span>
<span data-ttu-id="15a85-129">completerId</span><span class="sxs-lookup"><span data-stu-id="15a85-129">completerId</span></span> | <span data-ttu-id="15a85-130">String</span><span class="sxs-lookup"><span data-stu-id="15a85-130">String</span></span> | <span data-ttu-id="15a85-131">如果修正活动是由某人手动完成的，则此列包含其对象 ID</span><span class="sxs-lookup"><span data-stu-id="15a85-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="15a85-132">空</span><span class="sxs-lookup"><span data-stu-id="15a85-132">null</span></span>
<span data-ttu-id="15a85-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="15a85-133">completionMethod</span></span> | <span data-ttu-id="15a85-134">String</span><span class="sxs-lookup"><span data-stu-id="15a85-134">String</span></span> | <span data-ttu-id="15a85-135">如果所有设备 (都由选择"标记为已完成) 或"手动"进行修补，则修正活动可以"自动"完成。</span><span class="sxs-lookup"><span data-stu-id="15a85-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="15a85-136">自动</span><span class="sxs-lookup"><span data-stu-id="15a85-136">Automatic</span></span>
<span data-ttu-id="15a85-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="15a85-137">createdOn</span></span> | <span data-ttu-id="15a85-138">日期时间</span><span class="sxs-lookup"><span data-stu-id="15a85-138">DateTime</span></span> | <span data-ttu-id="15a85-139">创建此修正活动的时间</span><span class="sxs-lookup"><span data-stu-id="15a85-139">Time this remediation activity was created</span></span> | <span data-ttu-id="15a85-140">2021-01-12T18：54：11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="15a85-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="15a85-141">说明</span><span class="sxs-lookup"><span data-stu-id="15a85-141">description</span></span> | <span data-ttu-id="15a85-142">String</span><span class="sxs-lookup"><span data-stu-id="15a85-142">String</span></span> | <span data-ttu-id="15a85-143">此修正活动的说明</span><span class="sxs-lookup"><span data-stu-id="15a85-143">Description of this remediation activity</span></span> | <span data-ttu-id="15a85-144">将 Chrome 更新到更高版本，以缓解影响你的设备的 1248 个已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="15a85-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="15a85-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="15a85-145">dueOn</span></span> | <span data-ttu-id="15a85-146">日期时间</span><span class="sxs-lookup"><span data-stu-id="15a85-146">DateTime</span></span> | <span data-ttu-id="15a85-147">此修正活动的创建者设置的截止日期</span><span class="sxs-lookup"><span data-stu-id="15a85-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="15a85-148">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="15a85-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="15a85-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="15a85-149">fixedDevices</span></span> |  | <span data-ttu-id="15a85-150">已修复的设备数量</span><span class="sxs-lookup"><span data-stu-id="15a85-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="15a85-151">2</span><span class="sxs-lookup"><span data-stu-id="15a85-151">2</span></span>
<span data-ttu-id="15a85-152">id</span><span class="sxs-lookup"><span data-stu-id="15a85-152">id</span></span> | <span data-ttu-id="15a85-153">String</span><span class="sxs-lookup"><span data-stu-id="15a85-153">String</span></span> | <span data-ttu-id="15a85-154">此修正活动的 ID</span><span class="sxs-lookup"><span data-stu-id="15a85-154">ID of this remediation activity</span></span> | <span data-ttu-id="15a85-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="15a85-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="15a85-156">nameId</span><span class="sxs-lookup"><span data-stu-id="15a85-156">nameId</span></span> | <span data-ttu-id="15a85-157">String</span><span class="sxs-lookup"><span data-stu-id="15a85-157">String</span></span> | <span data-ttu-id="15a85-158">相关产品名称</span><span class="sxs-lookup"><span data-stu-id="15a85-158">Related product name</span></span> | <span data-ttu-id="15a85-159">chrome</span><span class="sxs-lookup"><span data-stu-id="15a85-159">chrome</span></span>
<span data-ttu-id="15a85-160">priority</span><span class="sxs-lookup"><span data-stu-id="15a85-160">priority</span></span> | <span data-ttu-id="15a85-161">String</span><span class="sxs-lookup"><span data-stu-id="15a85-161">String</span></span> | <span data-ttu-id="15a85-162">为此修正活动设置的创建者设置的优先级 (高\中\低) </span><span class="sxs-lookup"><span data-stu-id="15a85-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="15a85-163">高</span><span class="sxs-lookup"><span data-stu-id="15a85-163">High</span></span>
<span data-ttu-id="15a85-164">productId</span><span class="sxs-lookup"><span data-stu-id="15a85-164">productId</span></span> | <span data-ttu-id="15a85-165">String</span><span class="sxs-lookup"><span data-stu-id="15a85-165">String</span></span> | <span data-ttu-id="15a85-166">相关产品 ID</span><span class="sxs-lookup"><span data-stu-id="15a85-166">Related product ID</span></span> | <span data-ttu-id="15a85-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="15a85-167">google-_-chrome</span></span>
<span data-ttu-id="15a85-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="15a85-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="15a85-169">String</span><span class="sxs-lookup"><span data-stu-id="15a85-169">String</span></span> | <span data-ttu-id="15a85-170">只能请求对没有用户影响的设备进行一些配置更改。</span><span class="sxs-lookup"><span data-stu-id="15a85-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="15a85-171">此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。</span><span class="sxs-lookup"><span data-stu-id="15a85-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="15a85-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="15a85-172">AllExposedAssets</span></span>
<span data-ttu-id="15a85-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="15a85-173">rbacGroupNames</span></span> | <span data-ttu-id="15a85-174">String</span><span class="sxs-lookup"><span data-stu-id="15a85-174">String</span></span> | <span data-ttu-id="15a85-175">相关设备组名称</span><span class="sxs-lookup"><span data-stu-id="15a85-175">Related device group names</span></span> | <span data-ttu-id="15a85-176">[ "Windows Servers"， "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="15a85-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="15a85-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="15a85-177">recommendedProgram</span></span> | <span data-ttu-id="15a85-178">String</span><span class="sxs-lookup"><span data-stu-id="15a85-178">String</span></span> | <span data-ttu-id="15a85-179">要升级到的推荐程序</span><span class="sxs-lookup"><span data-stu-id="15a85-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="15a85-180">空</span><span class="sxs-lookup"><span data-stu-id="15a85-180">null</span></span>
<span data-ttu-id="15a85-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="15a85-181">recommendedVendor</span></span> | <span data-ttu-id="15a85-182">String</span><span class="sxs-lookup"><span data-stu-id="15a85-182">String</span></span> | <span data-ttu-id="15a85-183">建议升级到的供应商</span><span class="sxs-lookup"><span data-stu-id="15a85-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="15a85-184">空</span><span class="sxs-lookup"><span data-stu-id="15a85-184">null</span></span>
<span data-ttu-id="15a85-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="15a85-185">recommendedVersion</span></span> | <span data-ttu-id="15a85-186">String</span><span class="sxs-lookup"><span data-stu-id="15a85-186">String</span></span> | <span data-ttu-id="15a85-187">要更新/升级到的建议版本</span><span class="sxs-lookup"><span data-stu-id="15a85-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="15a85-188">空</span><span class="sxs-lookup"><span data-stu-id="15a85-188">null</span></span>
<span data-ttu-id="15a85-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="15a85-189">relatedComponent</span></span> | <span data-ttu-id="15a85-190">String</span><span class="sxs-lookup"><span data-stu-id="15a85-190">String</span></span> | <span data-ttu-id="15a85-191">此修正活动的相关组件 (安全建议计划的相关组件) </span><span class="sxs-lookup"><span data-stu-id="15a85-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="15a85-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="15a85-192">Google Chrome</span></span>
<span data-ttu-id="15a85-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="15a85-193">requesterEmail</span></span> | <span data-ttu-id="15a85-194">String</span><span class="sxs-lookup"><span data-stu-id="15a85-194">String</span></span> | <span data-ttu-id="15a85-195">创建者电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="15a85-195">Creator email address</span></span> | <span data-ttu-id="15a85-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15a85-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="15a85-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="15a85-197">requesterId</span></span> | <span data-ttu-id="15a85-198">String</span><span class="sxs-lookup"><span data-stu-id="15a85-198">String</span></span> | <span data-ttu-id="15a85-199">Creator 对象 ID</span><span class="sxs-lookup"><span data-stu-id="15a85-199">Creator object id</span></span> | <span data-ttu-id="15a85-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="15a85-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="15a85-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="15a85-201">requesterNotes</span></span> | <span data-ttu-id="15a85-202">String</span><span class="sxs-lookup"><span data-stu-id="15a85-202">String</span></span> | <span data-ttu-id="15a85-203">注释 (此) 活动的创建者添加的自定义文本</span><span class="sxs-lookup"><span data-stu-id="15a85-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="15a85-204">空</span><span class="sxs-lookup"><span data-stu-id="15a85-204">null</span></span>
<span data-ttu-id="15a85-205">scid</span><span class="sxs-lookup"><span data-stu-id="15a85-205">scid</span></span> | <span data-ttu-id="15a85-206">String</span><span class="sxs-lookup"><span data-stu-id="15a85-206">String</span></span> | <span data-ttu-id="15a85-207">相关安全建议 SCID</span><span class="sxs-lookup"><span data-stu-id="15a85-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="15a85-208">空</span><span class="sxs-lookup"><span data-stu-id="15a85-208">null</span></span>
<span data-ttu-id="15a85-209">状态</span><span class="sxs-lookup"><span data-stu-id="15a85-209">status</span></span> | <span data-ttu-id="15a85-210">String</span><span class="sxs-lookup"><span data-stu-id="15a85-210">String</span></span> | <span data-ttu-id="15a85-211">修正活动状态 (/已完成) </span><span class="sxs-lookup"><span data-stu-id="15a85-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="15a85-212">活动</span><span class="sxs-lookup"><span data-stu-id="15a85-212">Active</span></span>
<span data-ttu-id="15a85-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="15a85-213">statusLastModifiedOn</span></span> | <span data-ttu-id="15a85-214">日期时间</span><span class="sxs-lookup"><span data-stu-id="15a85-214">DateTime</span></span> | <span data-ttu-id="15a85-215">更新状态字段的日期</span><span class="sxs-lookup"><span data-stu-id="15a85-215">Date when the status field was updated</span></span> | <span data-ttu-id="15a85-216">2021-01-12T18：54：11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="15a85-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="15a85-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="15a85-217">targetDevices</span></span> | <span data-ttu-id="15a85-218">长型</span><span class="sxs-lookup"><span data-stu-id="15a85-218">Long</span></span> | <span data-ttu-id="15a85-219">此修正适用于的公开设备数量</span><span class="sxs-lookup"><span data-stu-id="15a85-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="15a85-220">43</span><span class="sxs-lookup"><span data-stu-id="15a85-220">43</span></span>
<span data-ttu-id="15a85-221">title</span><span class="sxs-lookup"><span data-stu-id="15a85-221">title</span></span> | <span data-ttu-id="15a85-222">String</span><span class="sxs-lookup"><span data-stu-id="15a85-222">String</span></span> | <span data-ttu-id="15a85-223">此修正活动的标题</span><span class="sxs-lookup"><span data-stu-id="15a85-223">Title of this remediation activity</span></span> | <span data-ttu-id="15a85-224">更新 Google Chrome</span><span class="sxs-lookup"><span data-stu-id="15a85-224">Update Google Chrome</span></span>
<span data-ttu-id="15a85-225">type</span><span class="sxs-lookup"><span data-stu-id="15a85-225">type</span></span> | <span data-ttu-id="15a85-226">String</span><span class="sxs-lookup"><span data-stu-id="15a85-226">String</span></span> | <span data-ttu-id="15a85-227">修正类型</span><span class="sxs-lookup"><span data-stu-id="15a85-227">Remediation type</span></span> | <span data-ttu-id="15a85-228">更新</span><span class="sxs-lookup"><span data-stu-id="15a85-228">Update</span></span>
<span data-ttu-id="15a85-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="15a85-229">vendorId</span></span> | <span data-ttu-id="15a85-230">String</span><span class="sxs-lookup"><span data-stu-id="15a85-230">String</span></span> | <span data-ttu-id="15a85-231">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="15a85-231">Related vendor name</span></span> | <span data-ttu-id="15a85-232">google</span><span class="sxs-lookup"><span data-stu-id="15a85-232">google</span></span>

## <a name="example"></a><span data-ttu-id="15a85-233">示例</span><span class="sxs-lookup"><span data-stu-id="15a85-233">Example</span></span>

<span data-ttu-id="15a85-234">**请求** 示例</span><span class="sxs-lookup"><span data-stu-id="15a85-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="15a85-235">**响应** 示例</span><span class="sxs-lookup"><span data-stu-id="15a85-235">**Response** example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a><span data-ttu-id="15a85-236">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15a85-236">See also</span></span>

- [<span data-ttu-id="15a85-237">修正方法和属性</span><span class="sxs-lookup"><span data-stu-id="15a85-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="15a85-238">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="15a85-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="15a85-239">列出一个修正活动的公开设备</span><span class="sxs-lookup"><span data-stu-id="15a85-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="15a85-240">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="15a85-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="15a85-241">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="15a85-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
