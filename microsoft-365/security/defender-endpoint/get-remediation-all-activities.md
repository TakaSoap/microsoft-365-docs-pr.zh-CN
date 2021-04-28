---
title: 列出所有修正活动
description: 返回有关所有修正活动的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务，
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
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061099"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="56192-104">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="56192-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56192-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="56192-105">**Applies to:**</span></span>

- [<span data-ttu-id="56192-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="56192-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="56192-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56192-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="56192-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="56192-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="56192-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="56192-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="56192-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="56192-110">API description</span></span>

<span data-ttu-id="56192-111">返回有关所有修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="56192-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="56192-112">[详细了解修正活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="56192-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="56192-113">**URL：** GET： /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="56192-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="56192-114">**属性** 详细信息</span><span class="sxs-lookup"><span data-stu-id="56192-114">**Properties** details</span></span>

<span data-ttu-id="56192-115">属性 (id) </span><span class="sxs-lookup"><span data-stu-id="56192-115">Property (id)</span></span> | <span data-ttu-id="56192-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="56192-116">Data type</span></span> | <span data-ttu-id="56192-117">说明</span><span class="sxs-lookup"><span data-stu-id="56192-117">Description</span></span> | <span data-ttu-id="56192-118">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="56192-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="56192-119">“类别”</span><span class="sxs-lookup"><span data-stu-id="56192-119">category</span></span> | <span data-ttu-id="56192-120">String</span><span class="sxs-lookup"><span data-stu-id="56192-120">String</span></span> | <span data-ttu-id="56192-121">软件/安全配置 (修正活动的) </span><span class="sxs-lookup"><span data-stu-id="56192-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="56192-122">软件</span><span class="sxs-lookup"><span data-stu-id="56192-122">Software</span></span>
<span data-ttu-id="56192-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="56192-123">completerEmail</span></span> | <span data-ttu-id="56192-124">String</span><span class="sxs-lookup"><span data-stu-id="56192-124">String</span></span> | <span data-ttu-id="56192-125">如果修正活动是由某人手动完成的，此列将包含他们的电子邮件</span><span class="sxs-lookup"><span data-stu-id="56192-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="56192-126">空</span><span class="sxs-lookup"><span data-stu-id="56192-126">null</span></span>
<span data-ttu-id="56192-127">completerId</span><span class="sxs-lookup"><span data-stu-id="56192-127">completerId</span></span> | <span data-ttu-id="56192-128">String</span><span class="sxs-lookup"><span data-stu-id="56192-128">String</span></span> | <span data-ttu-id="56192-129">如果修正活动是由某人手动完成的，则此列包含其对象 ID</span><span class="sxs-lookup"><span data-stu-id="56192-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="56192-130">空</span><span class="sxs-lookup"><span data-stu-id="56192-130">null</span></span>
<span data-ttu-id="56192-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="56192-131">completionMethod</span></span> | <span data-ttu-id="56192-132">String</span><span class="sxs-lookup"><span data-stu-id="56192-132">String</span></span> | <span data-ttu-id="56192-133">如果所有设备 (都由选择"标记为已完成) 或"手动"进行修补，则修正活动可以"自动"完成。</span><span class="sxs-lookup"><span data-stu-id="56192-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="56192-134">自动</span><span class="sxs-lookup"><span data-stu-id="56192-134">Automatic</span></span>
<span data-ttu-id="56192-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="56192-135">createdOn</span></span> | <span data-ttu-id="56192-136">日期时间</span><span class="sxs-lookup"><span data-stu-id="56192-136">DateTime</span></span> | <span data-ttu-id="56192-137">创建此修正活动的时间</span><span class="sxs-lookup"><span data-stu-id="56192-137">Time this remediation activity was created</span></span> | <span data-ttu-id="56192-138">2021-01-12T18：54：11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="56192-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="56192-139">说明</span><span class="sxs-lookup"><span data-stu-id="56192-139">description</span></span> | <span data-ttu-id="56192-140">String</span><span class="sxs-lookup"><span data-stu-id="56192-140">String</span></span> | <span data-ttu-id="56192-141">此修正活动的说明</span><span class="sxs-lookup"><span data-stu-id="56192-141">Description of this remediation activity</span></span> | <span data-ttu-id="56192-142">将 Chrome 更新到更高版本，以缓解影响你的设备的 1248 个已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="56192-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="56192-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="56192-143">dueOn</span></span> | <span data-ttu-id="56192-144">日期时间</span><span class="sxs-lookup"><span data-stu-id="56192-144">DateTime</span></span> | <span data-ttu-id="56192-145">此修正活动的创建者设置的截止日期</span><span class="sxs-lookup"><span data-stu-id="56192-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="56192-146">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="56192-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="56192-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="56192-147">fixedDevices</span></span> | <span data-ttu-id="56192-148">.</span><span class="sxs-lookup"><span data-stu-id="56192-148">.</span></span> | <span data-ttu-id="56192-149">已修复的设备数量</span><span class="sxs-lookup"><span data-stu-id="56192-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="56192-150">2</span><span class="sxs-lookup"><span data-stu-id="56192-150">2</span></span>
<span data-ttu-id="56192-151">id</span><span class="sxs-lookup"><span data-stu-id="56192-151">id</span></span> | <span data-ttu-id="56192-152">String</span><span class="sxs-lookup"><span data-stu-id="56192-152">String</span></span> | <span data-ttu-id="56192-153">此修正活动的 ID</span><span class="sxs-lookup"><span data-stu-id="56192-153">ID of this remediation activity</span></span> | <span data-ttu-id="56192-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="56192-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="56192-155">nameId</span><span class="sxs-lookup"><span data-stu-id="56192-155">nameId</span></span> | <span data-ttu-id="56192-156">String</span><span class="sxs-lookup"><span data-stu-id="56192-156">String</span></span> | <span data-ttu-id="56192-157">相关产品名称</span><span class="sxs-lookup"><span data-stu-id="56192-157">Related product name</span></span> | <span data-ttu-id="56192-158">chrome</span><span class="sxs-lookup"><span data-stu-id="56192-158">chrome</span></span>
<span data-ttu-id="56192-159">priority</span><span class="sxs-lookup"><span data-stu-id="56192-159">priority</span></span> | <span data-ttu-id="56192-160">String</span><span class="sxs-lookup"><span data-stu-id="56192-160">String</span></span> | <span data-ttu-id="56192-161">为此修正活动设置的创建者设置的优先级 (高\中\低) </span><span class="sxs-lookup"><span data-stu-id="56192-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="56192-162">高</span><span class="sxs-lookup"><span data-stu-id="56192-162">High</span></span>
<span data-ttu-id="56192-163">productId</span><span class="sxs-lookup"><span data-stu-id="56192-163">productId</span></span> | <span data-ttu-id="56192-164">String</span><span class="sxs-lookup"><span data-stu-id="56192-164">String</span></span> | <span data-ttu-id="56192-165">相关产品 ID</span><span class="sxs-lookup"><span data-stu-id="56192-165">Related product ID</span></span> | <span data-ttu-id="56192-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="56192-166">google-_-chrome</span></span>
<span data-ttu-id="56192-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="56192-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="56192-168">String</span><span class="sxs-lookup"><span data-stu-id="56192-168">String</span></span> | <span data-ttu-id="56192-169">只能请求对没有用户影响的设备进行一些配置更改。</span><span class="sxs-lookup"><span data-stu-id="56192-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="56192-170">此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。</span><span class="sxs-lookup"><span data-stu-id="56192-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="56192-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="56192-171">AllExposedAssets</span></span>
<span data-ttu-id="56192-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="56192-172">rbacGroupNames</span></span> | <span data-ttu-id="56192-173">String</span><span class="sxs-lookup"><span data-stu-id="56192-173">String</span></span> | <span data-ttu-id="56192-174">相关设备组名称</span><span class="sxs-lookup"><span data-stu-id="56192-174">Related device group names</span></span> | <span data-ttu-id="56192-175">[ "Windows Servers"， "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="56192-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="56192-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="56192-176">recommendedProgram</span></span> | <span data-ttu-id="56192-177">String</span><span class="sxs-lookup"><span data-stu-id="56192-177">String</span></span> | <span data-ttu-id="56192-178">要升级到的推荐程序</span><span class="sxs-lookup"><span data-stu-id="56192-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="56192-179">空</span><span class="sxs-lookup"><span data-stu-id="56192-179">null</span></span>
<span data-ttu-id="56192-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="56192-180">recommendedVendor</span></span> | <span data-ttu-id="56192-181">String</span><span class="sxs-lookup"><span data-stu-id="56192-181">String</span></span> | <span data-ttu-id="56192-182">建议升级到的供应商</span><span class="sxs-lookup"><span data-stu-id="56192-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="56192-183">空</span><span class="sxs-lookup"><span data-stu-id="56192-183">null</span></span>
<span data-ttu-id="56192-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="56192-184">recommendedVersion</span></span> | <span data-ttu-id="56192-185">String</span><span class="sxs-lookup"><span data-stu-id="56192-185">String</span></span> | <span data-ttu-id="56192-186">要更新/升级到的建议版本</span><span class="sxs-lookup"><span data-stu-id="56192-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="56192-187">空</span><span class="sxs-lookup"><span data-stu-id="56192-187">null</span></span>
<span data-ttu-id="56192-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="56192-188">relatedComponent</span></span> | <span data-ttu-id="56192-189">String</span><span class="sxs-lookup"><span data-stu-id="56192-189">String</span></span> | <span data-ttu-id="56192-190">此修正活动的相关组件 (安全建议计划的相关组件) </span><span class="sxs-lookup"><span data-stu-id="56192-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="56192-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="56192-191">Google Chrome</span></span>
<span data-ttu-id="56192-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="56192-192">requesterEmail</span></span> | <span data-ttu-id="56192-193">String</span><span class="sxs-lookup"><span data-stu-id="56192-193">String</span></span> | <span data-ttu-id="56192-194">创建者电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="56192-194">Creator email address</span></span> | <span data-ttu-id="56192-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="56192-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="56192-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="56192-196">requesterId</span></span> | <span data-ttu-id="56192-197">String</span><span class="sxs-lookup"><span data-stu-id="56192-197">String</span></span> | <span data-ttu-id="56192-198">Creator 对象 ID</span><span class="sxs-lookup"><span data-stu-id="56192-198">Creator object id</span></span> | <span data-ttu-id="56192-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="56192-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="56192-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="56192-200">requesterNotes</span></span> | <span data-ttu-id="56192-201">String</span><span class="sxs-lookup"><span data-stu-id="56192-201">String</span></span> | <span data-ttu-id="56192-202">注释 (此) 活动的创建者添加的自定义文本</span><span class="sxs-lookup"><span data-stu-id="56192-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="56192-203">空</span><span class="sxs-lookup"><span data-stu-id="56192-203">null</span></span>
<span data-ttu-id="56192-204">scid</span><span class="sxs-lookup"><span data-stu-id="56192-204">scid</span></span> | <span data-ttu-id="56192-205">String</span><span class="sxs-lookup"><span data-stu-id="56192-205">String</span></span> | <span data-ttu-id="56192-206">相关安全建议 SCID</span><span class="sxs-lookup"><span data-stu-id="56192-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="56192-207">空</span><span class="sxs-lookup"><span data-stu-id="56192-207">null</span></span>
<span data-ttu-id="56192-208">状态</span><span class="sxs-lookup"><span data-stu-id="56192-208">status</span></span> | <span data-ttu-id="56192-209">String</span><span class="sxs-lookup"><span data-stu-id="56192-209">String</span></span> | <span data-ttu-id="56192-210">修正活动状态 (/已完成) </span><span class="sxs-lookup"><span data-stu-id="56192-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="56192-211">活动</span><span class="sxs-lookup"><span data-stu-id="56192-211">Active</span></span>
<span data-ttu-id="56192-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="56192-212">statusLastModifiedOn</span></span> | <span data-ttu-id="56192-213">日期时间</span><span class="sxs-lookup"><span data-stu-id="56192-213">DateTime</span></span> | <span data-ttu-id="56192-214">更新状态字段的日期</span><span class="sxs-lookup"><span data-stu-id="56192-214">Date when the status field was updated</span></span> | <span data-ttu-id="56192-215">2021-01-12T18：54：11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="56192-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="56192-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="56192-216">targetDevices</span></span> | <span data-ttu-id="56192-217">长型</span><span class="sxs-lookup"><span data-stu-id="56192-217">Long</span></span> | <span data-ttu-id="56192-218">此修正适用于的公开设备数量</span><span class="sxs-lookup"><span data-stu-id="56192-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="56192-219">43</span><span class="sxs-lookup"><span data-stu-id="56192-219">43</span></span>
<span data-ttu-id="56192-220">title</span><span class="sxs-lookup"><span data-stu-id="56192-220">title</span></span> | <span data-ttu-id="56192-221">String</span><span class="sxs-lookup"><span data-stu-id="56192-221">String</span></span> | <span data-ttu-id="56192-222">此修正活动的标题</span><span class="sxs-lookup"><span data-stu-id="56192-222">Title of this remediation activity</span></span> | <span data-ttu-id="56192-223">更新 Google Chrome</span><span class="sxs-lookup"><span data-stu-id="56192-223">Update Google Chrome</span></span>
<span data-ttu-id="56192-224">type</span><span class="sxs-lookup"><span data-stu-id="56192-224">type</span></span> | <span data-ttu-id="56192-225">String</span><span class="sxs-lookup"><span data-stu-id="56192-225">String</span></span> | <span data-ttu-id="56192-226">修正类型</span><span class="sxs-lookup"><span data-stu-id="56192-226">Remediation type</span></span> | <span data-ttu-id="56192-227">更新</span><span class="sxs-lookup"><span data-stu-id="56192-227">Update</span></span>
<span data-ttu-id="56192-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="56192-228">vendorId</span></span> | <span data-ttu-id="56192-229">String</span><span class="sxs-lookup"><span data-stu-id="56192-229">String</span></span> | <span data-ttu-id="56192-230">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="56192-230">Related vendor name</span></span> | <span data-ttu-id="56192-231">google</span><span class="sxs-lookup"><span data-stu-id="56192-231">google</span></span>

## <a name="example"></a><span data-ttu-id="56192-232">示例</span><span class="sxs-lookup"><span data-stu-id="56192-232">Example</span></span>

<span data-ttu-id="56192-233">**请求** 示例</span><span class="sxs-lookup"><span data-stu-id="56192-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="56192-234">**响应** 示例</span><span class="sxs-lookup"><span data-stu-id="56192-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
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
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="56192-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56192-235">See also</span></span>

- [<span data-ttu-id="56192-236">修正方法和属性</span><span class="sxs-lookup"><span data-stu-id="56192-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="56192-237">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="56192-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="56192-238">列出一个修正活动的公开设备</span><span class="sxs-lookup"><span data-stu-id="56192-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="56192-239">基于风险的威胁&漏洞管理</span><span class="sxs-lookup"><span data-stu-id="56192-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="56192-240">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="56192-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
