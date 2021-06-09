---
title: 列出所有修正活动
description: 返回有关所有修正活动的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 所有修正，
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845124"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="94b2f-104">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="94b2f-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94b2f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="94b2f-105">**Applies to:**</span></span>

- [<span data-ttu-id="94b2f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94b2f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94b2f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94b2f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="94b2f-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="94b2f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="94b2f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="94b2f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="94b2f-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="94b2f-110">API description</span></span>

<span data-ttu-id="94b2f-111">返回有关所有修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="94b2f-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="94b2f-112">[详细了解修正活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="94b2f-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="94b2f-113">**URL：** GET： /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="94b2f-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="94b2f-114">权限</span><span class="sxs-lookup"><span data-stu-id="94b2f-114">Permissions</span></span>

<span data-ttu-id="94b2f-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="94b2f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="94b2f-116">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="94b2f-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="94b2f-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="94b2f-117">Permission type</span></span> | <span data-ttu-id="94b2f-118">权限</span><span class="sxs-lookup"><span data-stu-id="94b2f-118">Permission</span></span> | <span data-ttu-id="94b2f-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="94b2f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="94b2f-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="94b2f-120">Application</span></span> | <span data-ttu-id="94b2f-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="94b2f-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="94b2f-122">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="94b2f-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="94b2f-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="94b2f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="94b2f-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="94b2f-124">RemediationTask.Read</span></span> | <span data-ttu-id="94b2f-125">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="94b2f-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="94b2f-126">属性</span><span class="sxs-lookup"><span data-stu-id="94b2f-126">Properties</span></span>

<span data-ttu-id="94b2f-127">属性 (id) </span><span class="sxs-lookup"><span data-stu-id="94b2f-127">Property (id)</span></span> | <span data-ttu-id="94b2f-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="94b2f-128">Data type</span></span> | <span data-ttu-id="94b2f-129">说明</span><span class="sxs-lookup"><span data-stu-id="94b2f-129">Description</span></span> | <span data-ttu-id="94b2f-130">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="94b2f-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="94b2f-131">“类别”</span><span class="sxs-lookup"><span data-stu-id="94b2f-131">category</span></span> | <span data-ttu-id="94b2f-132">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-132">String</span></span> | <span data-ttu-id="94b2f-133">软件/安全配置 (修正活动的) </span><span class="sxs-lookup"><span data-stu-id="94b2f-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="94b2f-134">软件</span><span class="sxs-lookup"><span data-stu-id="94b2f-134">Software</span></span>
<span data-ttu-id="94b2f-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="94b2f-135">completerEmail</span></span> | <span data-ttu-id="94b2f-136">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-136">String</span></span> | <span data-ttu-id="94b2f-137">如果修正活动是由某人手动完成的，此列将包含他们的电子邮件</span><span class="sxs-lookup"><span data-stu-id="94b2f-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="94b2f-138">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-138">null</span></span>
<span data-ttu-id="94b2f-139">completerId</span><span class="sxs-lookup"><span data-stu-id="94b2f-139">completerId</span></span> | <span data-ttu-id="94b2f-140">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-140">String</span></span> | <span data-ttu-id="94b2f-141">如果修正活动是由某人手动完成的，则此列包含其对象 ID</span><span class="sxs-lookup"><span data-stu-id="94b2f-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="94b2f-142">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-142">null</span></span>
<span data-ttu-id="94b2f-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="94b2f-143">completionMethod</span></span> | <span data-ttu-id="94b2f-144">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-144">String</span></span> | <span data-ttu-id="94b2f-145">如果所有设备 (都由选择"标记为已完成) 或"手动"进行修补，则修正活动可以"自动"完成。</span><span class="sxs-lookup"><span data-stu-id="94b2f-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="94b2f-146">自动</span><span class="sxs-lookup"><span data-stu-id="94b2f-146">Automatic</span></span>
<span data-ttu-id="94b2f-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="94b2f-147">createdOn</span></span> | <span data-ttu-id="94b2f-148">日期时间</span><span class="sxs-lookup"><span data-stu-id="94b2f-148">DateTime</span></span> | <span data-ttu-id="94b2f-149">创建此修正活动的时间</span><span class="sxs-lookup"><span data-stu-id="94b2f-149">Time this remediation activity was created</span></span> | <span data-ttu-id="94b2f-150">2021-01-12T18：54：11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="94b2f-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="94b2f-151">说明</span><span class="sxs-lookup"><span data-stu-id="94b2f-151">description</span></span> | <span data-ttu-id="94b2f-152">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-152">String</span></span> | <span data-ttu-id="94b2f-153">此修正活动的说明</span><span class="sxs-lookup"><span data-stu-id="94b2f-153">Description of this remediation activity</span></span> | <span data-ttu-id="94b2f-154">将 Microsoft Silverlight 更新到更高版本，以减少影响设备的已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="94b2f-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="94b2f-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="94b2f-155">dueOn</span></span> | <span data-ttu-id="94b2f-156">日期时间</span><span class="sxs-lookup"><span data-stu-id="94b2f-156">DateTime</span></span> | <span data-ttu-id="94b2f-157">此修正活动的创建者设置的截止日期</span><span class="sxs-lookup"><span data-stu-id="94b2f-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="94b2f-158">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="94b2f-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="94b2f-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="94b2f-159">fixedDevices</span></span> | <span data-ttu-id="94b2f-160">.</span><span class="sxs-lookup"><span data-stu-id="94b2f-160">.</span></span> | <span data-ttu-id="94b2f-161">已修复的设备数量</span><span class="sxs-lookup"><span data-stu-id="94b2f-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="94b2f-162">2</span><span class="sxs-lookup"><span data-stu-id="94b2f-162">2</span></span>
<span data-ttu-id="94b2f-163">id</span><span class="sxs-lookup"><span data-stu-id="94b2f-163">id</span></span> | <span data-ttu-id="94b2f-164">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-164">String</span></span> | <span data-ttu-id="94b2f-165">此修正活动的 ID</span><span class="sxs-lookup"><span data-stu-id="94b2f-165">ID of this remediation activity</span></span> | <span data-ttu-id="94b2f-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="94b2f-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="94b2f-167">nameId</span><span class="sxs-lookup"><span data-stu-id="94b2f-167">nameId</span></span> | <span data-ttu-id="94b2f-168">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-168">String</span></span> | <span data-ttu-id="94b2f-169">相关产品名称</span><span class="sxs-lookup"><span data-stu-id="94b2f-169">Related product name</span></span> | <span data-ttu-id="94b2f-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="94b2f-170">Microsoft Silverlight</span></span>
<span data-ttu-id="94b2f-171">priority</span><span class="sxs-lookup"><span data-stu-id="94b2f-171">priority</span></span> | <span data-ttu-id="94b2f-172">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-172">String</span></span> | <span data-ttu-id="94b2f-173">为此修正活动设置的创建者设置的优先级 (高\中\低) </span><span class="sxs-lookup"><span data-stu-id="94b2f-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="94b2f-174">高</span><span class="sxs-lookup"><span data-stu-id="94b2f-174">High</span></span>
<span data-ttu-id="94b2f-175">productId</span><span class="sxs-lookup"><span data-stu-id="94b2f-175">productId</span></span> | <span data-ttu-id="94b2f-176">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-176">String</span></span> | <span data-ttu-id="94b2f-177">相关产品 ID</span><span class="sxs-lookup"><span data-stu-id="94b2f-177">Related product ID</span></span> | <span data-ttu-id="94b2f-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="94b2f-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="94b2f-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="94b2f-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="94b2f-180">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-180">String</span></span> | <span data-ttu-id="94b2f-181">只能请求对没有用户影响的设备进行一些配置更改。</span><span class="sxs-lookup"><span data-stu-id="94b2f-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="94b2f-182">此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。</span><span class="sxs-lookup"><span data-stu-id="94b2f-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="94b2f-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="94b2f-183">AllExposedAssets</span></span>
<span data-ttu-id="94b2f-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="94b2f-184">rbacGroupNames</span></span> | <span data-ttu-id="94b2f-185">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-185">String</span></span> | <span data-ttu-id="94b2f-186">相关设备组名称</span><span class="sxs-lookup"><span data-stu-id="94b2f-186">Related device group names</span></span> | <span data-ttu-id="94b2f-187">[ "Windows Servers"， "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="94b2f-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="94b2f-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="94b2f-188">recommendedProgram</span></span> | <span data-ttu-id="94b2f-189">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-189">String</span></span> | <span data-ttu-id="94b2f-190">要升级到的推荐程序</span><span class="sxs-lookup"><span data-stu-id="94b2f-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="94b2f-191">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-191">null</span></span>
<span data-ttu-id="94b2f-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="94b2f-192">recommendedVendor</span></span> | <span data-ttu-id="94b2f-193">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-193">String</span></span> | <span data-ttu-id="94b2f-194">建议升级到的供应商</span><span class="sxs-lookup"><span data-stu-id="94b2f-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="94b2f-195">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-195">null</span></span>
<span data-ttu-id="94b2f-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="94b2f-196">recommendedVersion</span></span> | <span data-ttu-id="94b2f-197">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-197">String</span></span> | <span data-ttu-id="94b2f-198">要更新/升级到的建议版本</span><span class="sxs-lookup"><span data-stu-id="94b2f-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="94b2f-199">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-199">null</span></span>
<span data-ttu-id="94b2f-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="94b2f-200">relatedComponent</span></span> | <span data-ttu-id="94b2f-201">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-201">String</span></span> | <span data-ttu-id="94b2f-202">此修正活动的相关组件 (安全建议计划的相关组件) </span><span class="sxs-lookup"><span data-stu-id="94b2f-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="94b2f-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="94b2f-203">Microsoft Silverlight</span></span>
<span data-ttu-id="94b2f-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="94b2f-204">requesterEmail</span></span> | <span data-ttu-id="94b2f-205">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-205">String</span></span> | <span data-ttu-id="94b2f-206">创建者电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="94b2f-206">Creator email address</span></span> | <span data-ttu-id="94b2f-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94b2f-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="94b2f-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="94b2f-208">requesterId</span></span> | <span data-ttu-id="94b2f-209">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-209">String</span></span> | <span data-ttu-id="94b2f-210">Creator 对象 ID</span><span class="sxs-lookup"><span data-stu-id="94b2f-210">Creator object id</span></span> | <span data-ttu-id="94b2f-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="94b2f-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="94b2f-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="94b2f-212">requesterNotes</span></span> | <span data-ttu-id="94b2f-213">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-213">String</span></span> | <span data-ttu-id="94b2f-214">注释 (此) 活动的创建者添加的自定义文本</span><span class="sxs-lookup"><span data-stu-id="94b2f-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="94b2f-215">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-215">null</span></span>
<span data-ttu-id="94b2f-216">scid</span><span class="sxs-lookup"><span data-stu-id="94b2f-216">scid</span></span> | <span data-ttu-id="94b2f-217">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-217">String</span></span> | <span data-ttu-id="94b2f-218">相关安全建议 SCID</span><span class="sxs-lookup"><span data-stu-id="94b2f-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="94b2f-219">空</span><span class="sxs-lookup"><span data-stu-id="94b2f-219">null</span></span>
<span data-ttu-id="94b2f-220">状态</span><span class="sxs-lookup"><span data-stu-id="94b2f-220">status</span></span> | <span data-ttu-id="94b2f-221">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-221">String</span></span> | <span data-ttu-id="94b2f-222">修正活动状态 (/已完成) </span><span class="sxs-lookup"><span data-stu-id="94b2f-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="94b2f-223">活动</span><span class="sxs-lookup"><span data-stu-id="94b2f-223">Active</span></span>
<span data-ttu-id="94b2f-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="94b2f-224">statusLastModifiedOn</span></span> | <span data-ttu-id="94b2f-225">日期时间</span><span class="sxs-lookup"><span data-stu-id="94b2f-225">DateTime</span></span> | <span data-ttu-id="94b2f-226">更新状态字段的日期</span><span class="sxs-lookup"><span data-stu-id="94b2f-226">Date when the status field was updated</span></span> | <span data-ttu-id="94b2f-227">2021-01-12T18：54：11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="94b2f-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="94b2f-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="94b2f-228">targetDevices</span></span> | <span data-ttu-id="94b2f-229">长型</span><span class="sxs-lookup"><span data-stu-id="94b2f-229">Long</span></span> | <span data-ttu-id="94b2f-230">此修正适用于的公开设备数量</span><span class="sxs-lookup"><span data-stu-id="94b2f-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="94b2f-231">43</span><span class="sxs-lookup"><span data-stu-id="94b2f-231">43</span></span>
<span data-ttu-id="94b2f-232">title</span><span class="sxs-lookup"><span data-stu-id="94b2f-232">title</span></span> | <span data-ttu-id="94b2f-233">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-233">String</span></span> | <span data-ttu-id="94b2f-234">此修正活动的标题</span><span class="sxs-lookup"><span data-stu-id="94b2f-234">Title of this remediation activity</span></span> | <span data-ttu-id="94b2f-235">更新 Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="94b2f-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="94b2f-236">type</span><span class="sxs-lookup"><span data-stu-id="94b2f-236">type</span></span> | <span data-ttu-id="94b2f-237">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-237">String</span></span> | <span data-ttu-id="94b2f-238">修正类型</span><span class="sxs-lookup"><span data-stu-id="94b2f-238">Remediation type</span></span> | <span data-ttu-id="94b2f-239">更新</span><span class="sxs-lookup"><span data-stu-id="94b2f-239">Update</span></span>
<span data-ttu-id="94b2f-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="94b2f-240">vendorId</span></span> | <span data-ttu-id="94b2f-241">String</span><span class="sxs-lookup"><span data-stu-id="94b2f-241">String</span></span> | <span data-ttu-id="94b2f-242">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="94b2f-242">Related vendor name</span></span> | <span data-ttu-id="94b2f-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b2f-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="94b2f-244">示例</span><span class="sxs-lookup"><span data-stu-id="94b2f-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="94b2f-245">请求示例</span><span class="sxs-lookup"><span data-stu-id="94b2f-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="94b2f-246">响应示例</span><span class="sxs-lookup"><span data-stu-id="94b2f-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="94b2f-247">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94b2f-247">See also</span></span>

- [<span data-ttu-id="94b2f-248">修正方法和属性</span><span class="sxs-lookup"><span data-stu-id="94b2f-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="94b2f-249">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="94b2f-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="94b2f-250">列出修正活动的暴露设备</span><span class="sxs-lookup"><span data-stu-id="94b2f-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="94b2f-251">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="94b2f-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="94b2f-252">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="94b2f-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
