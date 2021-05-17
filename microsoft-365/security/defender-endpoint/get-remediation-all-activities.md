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
ms.technology: mde
ms.openlocfilehash: cf7c79cb6cc76af88ce0293a013ba6edbf435d8c
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245488"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="103b7-104">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="103b7-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="103b7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="103b7-105">**Applies to:**</span></span>

- [<span data-ttu-id="103b7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="103b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="103b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="103b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="103b7-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="103b7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="103b7-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="103b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="103b7-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="103b7-110">API description</span></span>

<span data-ttu-id="103b7-111">返回有关所有修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="103b7-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="103b7-112">[详细了解修正活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="103b7-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="103b7-113">**URL：** GET： /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="103b7-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="103b7-114">权限</span><span class="sxs-lookup"><span data-stu-id="103b7-114">Permissions</span></span>

<span data-ttu-id="103b7-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="103b7-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="103b7-116">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="103b7-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="103b7-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="103b7-117">Permission type</span></span> | <span data-ttu-id="103b7-118">权限</span><span class="sxs-lookup"><span data-stu-id="103b7-118">Permission</span></span> | <span data-ttu-id="103b7-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="103b7-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="103b7-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="103b7-120">Application</span></span> | <span data-ttu-id="103b7-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="103b7-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="103b7-122">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="103b7-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="103b7-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="103b7-123">Delegated (work or school account)</span></span> | <span data-ttu-id="103b7-124">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="103b7-124">RemediationTask.Read.Read</span></span> | <span data-ttu-id="103b7-125">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="103b7-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="103b7-126">属性</span><span class="sxs-lookup"><span data-stu-id="103b7-126">Properties</span></span>

<span data-ttu-id="103b7-127">属性 (id) </span><span class="sxs-lookup"><span data-stu-id="103b7-127">Property (id)</span></span> | <span data-ttu-id="103b7-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="103b7-128">Data type</span></span> | <span data-ttu-id="103b7-129">说明</span><span class="sxs-lookup"><span data-stu-id="103b7-129">Description</span></span> | <span data-ttu-id="103b7-130">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="103b7-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="103b7-131">“类别”</span><span class="sxs-lookup"><span data-stu-id="103b7-131">category</span></span> | <span data-ttu-id="103b7-132">String</span><span class="sxs-lookup"><span data-stu-id="103b7-132">String</span></span> | <span data-ttu-id="103b7-133">软件/安全配置 (修正活动的) </span><span class="sxs-lookup"><span data-stu-id="103b7-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="103b7-134">软件</span><span class="sxs-lookup"><span data-stu-id="103b7-134">Software</span></span>
<span data-ttu-id="103b7-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="103b7-135">completerEmail</span></span> | <span data-ttu-id="103b7-136">String</span><span class="sxs-lookup"><span data-stu-id="103b7-136">String</span></span> | <span data-ttu-id="103b7-137">如果修正活动是由某人手动完成的，此列将包含他们的电子邮件</span><span class="sxs-lookup"><span data-stu-id="103b7-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="103b7-138">空</span><span class="sxs-lookup"><span data-stu-id="103b7-138">null</span></span>
<span data-ttu-id="103b7-139">completerId</span><span class="sxs-lookup"><span data-stu-id="103b7-139">completerId</span></span> | <span data-ttu-id="103b7-140">String</span><span class="sxs-lookup"><span data-stu-id="103b7-140">String</span></span> | <span data-ttu-id="103b7-141">如果修正活动是由某人手动完成的，则此列包含其对象 ID</span><span class="sxs-lookup"><span data-stu-id="103b7-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="103b7-142">空</span><span class="sxs-lookup"><span data-stu-id="103b7-142">null</span></span>
<span data-ttu-id="103b7-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="103b7-143">completionMethod</span></span> | <span data-ttu-id="103b7-144">String</span><span class="sxs-lookup"><span data-stu-id="103b7-144">String</span></span> | <span data-ttu-id="103b7-145">如果所有设备 (都由选择"标记为已完成) 或"手动"进行修补，则修正活动可以"自动"完成。</span><span class="sxs-lookup"><span data-stu-id="103b7-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="103b7-146">自动</span><span class="sxs-lookup"><span data-stu-id="103b7-146">Automatic</span></span>
<span data-ttu-id="103b7-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="103b7-147">createdOn</span></span> | <span data-ttu-id="103b7-148">日期时间</span><span class="sxs-lookup"><span data-stu-id="103b7-148">DateTime</span></span> | <span data-ttu-id="103b7-149">创建此修正活动的时间</span><span class="sxs-lookup"><span data-stu-id="103b7-149">Time this remediation activity was created</span></span> | <span data-ttu-id="103b7-150">2021-01-12T18：54：11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="103b7-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="103b7-151">说明</span><span class="sxs-lookup"><span data-stu-id="103b7-151">description</span></span> | <span data-ttu-id="103b7-152">String</span><span class="sxs-lookup"><span data-stu-id="103b7-152">String</span></span> | <span data-ttu-id="103b7-153">此修正活动的说明</span><span class="sxs-lookup"><span data-stu-id="103b7-153">Description of this remediation activity</span></span> | <span data-ttu-id="103b7-154">将 Microsoft Silverlight 更新到更高版本，以减少影响设备的已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="103b7-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="103b7-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="103b7-155">dueOn</span></span> | <span data-ttu-id="103b7-156">日期时间</span><span class="sxs-lookup"><span data-stu-id="103b7-156">DateTime</span></span> | <span data-ttu-id="103b7-157">此修正活动的创建者设置的截止日期</span><span class="sxs-lookup"><span data-stu-id="103b7-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="103b7-158">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="103b7-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="103b7-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="103b7-159">fixedDevices</span></span> | <span data-ttu-id="103b7-160">.</span><span class="sxs-lookup"><span data-stu-id="103b7-160">.</span></span> | <span data-ttu-id="103b7-161">已修复的设备数量</span><span class="sxs-lookup"><span data-stu-id="103b7-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="103b7-162">2</span><span class="sxs-lookup"><span data-stu-id="103b7-162">2</span></span>
<span data-ttu-id="103b7-163">id</span><span class="sxs-lookup"><span data-stu-id="103b7-163">id</span></span> | <span data-ttu-id="103b7-164">String</span><span class="sxs-lookup"><span data-stu-id="103b7-164">String</span></span> | <span data-ttu-id="103b7-165">此修正活动的 ID</span><span class="sxs-lookup"><span data-stu-id="103b7-165">ID of this remediation activity</span></span> | <span data-ttu-id="103b7-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="103b7-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="103b7-167">nameId</span><span class="sxs-lookup"><span data-stu-id="103b7-167">nameId</span></span> | <span data-ttu-id="103b7-168">String</span><span class="sxs-lookup"><span data-stu-id="103b7-168">String</span></span> | <span data-ttu-id="103b7-169">相关产品名称</span><span class="sxs-lookup"><span data-stu-id="103b7-169">Related product name</span></span> | <span data-ttu-id="103b7-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="103b7-170">Microsoft Silverlight</span></span>
<span data-ttu-id="103b7-171">priority</span><span class="sxs-lookup"><span data-stu-id="103b7-171">priority</span></span> | <span data-ttu-id="103b7-172">String</span><span class="sxs-lookup"><span data-stu-id="103b7-172">String</span></span> | <span data-ttu-id="103b7-173">为此修正活动设置的创建者设置的优先级 (高\中\低) </span><span class="sxs-lookup"><span data-stu-id="103b7-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="103b7-174">高</span><span class="sxs-lookup"><span data-stu-id="103b7-174">High</span></span>
<span data-ttu-id="103b7-175">productId</span><span class="sxs-lookup"><span data-stu-id="103b7-175">productId</span></span> | <span data-ttu-id="103b7-176">String</span><span class="sxs-lookup"><span data-stu-id="103b7-176">String</span></span> | <span data-ttu-id="103b7-177">相关产品 ID</span><span class="sxs-lookup"><span data-stu-id="103b7-177">Related product ID</span></span> | <span data-ttu-id="103b7-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="103b7-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="103b7-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="103b7-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="103b7-180">String</span><span class="sxs-lookup"><span data-stu-id="103b7-180">String</span></span> | <span data-ttu-id="103b7-181">只能请求对没有用户影响的设备进行一些配置更改。</span><span class="sxs-lookup"><span data-stu-id="103b7-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="103b7-182">此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。</span><span class="sxs-lookup"><span data-stu-id="103b7-182">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="103b7-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="103b7-183">AllExposedAssets</span></span>
<span data-ttu-id="103b7-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="103b7-184">rbacGroupNames</span></span> | <span data-ttu-id="103b7-185">String</span><span class="sxs-lookup"><span data-stu-id="103b7-185">String</span></span> | <span data-ttu-id="103b7-186">相关设备组名称</span><span class="sxs-lookup"><span data-stu-id="103b7-186">Related device group names</span></span> | <span data-ttu-id="103b7-187">[ "Windows Servers"， "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="103b7-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="103b7-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="103b7-188">recommendedProgram</span></span> | <span data-ttu-id="103b7-189">String</span><span class="sxs-lookup"><span data-stu-id="103b7-189">String</span></span> | <span data-ttu-id="103b7-190">要升级到的推荐程序</span><span class="sxs-lookup"><span data-stu-id="103b7-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="103b7-191">空</span><span class="sxs-lookup"><span data-stu-id="103b7-191">null</span></span>
<span data-ttu-id="103b7-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="103b7-192">recommendedVendor</span></span> | <span data-ttu-id="103b7-193">String</span><span class="sxs-lookup"><span data-stu-id="103b7-193">String</span></span> | <span data-ttu-id="103b7-194">建议升级到的供应商</span><span class="sxs-lookup"><span data-stu-id="103b7-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="103b7-195">空</span><span class="sxs-lookup"><span data-stu-id="103b7-195">null</span></span>
<span data-ttu-id="103b7-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="103b7-196">recommendedVersion</span></span> | <span data-ttu-id="103b7-197">String</span><span class="sxs-lookup"><span data-stu-id="103b7-197">String</span></span> | <span data-ttu-id="103b7-198">要更新/升级到的建议版本</span><span class="sxs-lookup"><span data-stu-id="103b7-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="103b7-199">空</span><span class="sxs-lookup"><span data-stu-id="103b7-199">null</span></span>
<span data-ttu-id="103b7-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="103b7-200">relatedComponent</span></span> | <span data-ttu-id="103b7-201">String</span><span class="sxs-lookup"><span data-stu-id="103b7-201">String</span></span> | <span data-ttu-id="103b7-202">此修正活动的相关组件 (安全建议计划的相关组件) </span><span class="sxs-lookup"><span data-stu-id="103b7-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="103b7-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="103b7-203">Microsoft Silverlight</span></span>
<span data-ttu-id="103b7-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="103b7-204">requesterEmail</span></span> | <span data-ttu-id="103b7-205">String</span><span class="sxs-lookup"><span data-stu-id="103b7-205">String</span></span> | <span data-ttu-id="103b7-206">创建者电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="103b7-206">Creator email address</span></span> | <span data-ttu-id="103b7-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="103b7-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="103b7-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="103b7-208">requesterId</span></span> | <span data-ttu-id="103b7-209">String</span><span class="sxs-lookup"><span data-stu-id="103b7-209">String</span></span> | <span data-ttu-id="103b7-210">Creator 对象 ID</span><span class="sxs-lookup"><span data-stu-id="103b7-210">Creator object id</span></span> | <span data-ttu-id="103b7-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="103b7-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="103b7-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="103b7-212">requesterNotes</span></span> | <span data-ttu-id="103b7-213">String</span><span class="sxs-lookup"><span data-stu-id="103b7-213">String</span></span> | <span data-ttu-id="103b7-214">注释 (此) 活动的创建者添加的自定义文本</span><span class="sxs-lookup"><span data-stu-id="103b7-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="103b7-215">空</span><span class="sxs-lookup"><span data-stu-id="103b7-215">null</span></span>
<span data-ttu-id="103b7-216">scid</span><span class="sxs-lookup"><span data-stu-id="103b7-216">scid</span></span> | <span data-ttu-id="103b7-217">String</span><span class="sxs-lookup"><span data-stu-id="103b7-217">String</span></span> | <span data-ttu-id="103b7-218">相关安全建议 SCID</span><span class="sxs-lookup"><span data-stu-id="103b7-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="103b7-219">空</span><span class="sxs-lookup"><span data-stu-id="103b7-219">null</span></span>
<span data-ttu-id="103b7-220">状态</span><span class="sxs-lookup"><span data-stu-id="103b7-220">status</span></span> | <span data-ttu-id="103b7-221">String</span><span class="sxs-lookup"><span data-stu-id="103b7-221">String</span></span> | <span data-ttu-id="103b7-222">修正活动状态 (/已完成) </span><span class="sxs-lookup"><span data-stu-id="103b7-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="103b7-223">活动</span><span class="sxs-lookup"><span data-stu-id="103b7-223">Active</span></span>
<span data-ttu-id="103b7-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="103b7-224">statusLastModifiedOn</span></span> | <span data-ttu-id="103b7-225">日期时间</span><span class="sxs-lookup"><span data-stu-id="103b7-225">DateTime</span></span> | <span data-ttu-id="103b7-226">更新状态字段的日期</span><span class="sxs-lookup"><span data-stu-id="103b7-226">Date when the status field was updated</span></span> | <span data-ttu-id="103b7-227">2021-01-12T18：54：11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="103b7-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="103b7-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="103b7-228">targetDevices</span></span> | <span data-ttu-id="103b7-229">长型</span><span class="sxs-lookup"><span data-stu-id="103b7-229">Long</span></span> | <span data-ttu-id="103b7-230">此修正适用于的公开设备数量</span><span class="sxs-lookup"><span data-stu-id="103b7-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="103b7-231">43</span><span class="sxs-lookup"><span data-stu-id="103b7-231">43</span></span>
<span data-ttu-id="103b7-232">title</span><span class="sxs-lookup"><span data-stu-id="103b7-232">title</span></span> | <span data-ttu-id="103b7-233">String</span><span class="sxs-lookup"><span data-stu-id="103b7-233">String</span></span> | <span data-ttu-id="103b7-234">此修正活动的标题</span><span class="sxs-lookup"><span data-stu-id="103b7-234">Title of this remediation activity</span></span> | <span data-ttu-id="103b7-235">更新 Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="103b7-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="103b7-236">type</span><span class="sxs-lookup"><span data-stu-id="103b7-236">type</span></span> | <span data-ttu-id="103b7-237">String</span><span class="sxs-lookup"><span data-stu-id="103b7-237">String</span></span> | <span data-ttu-id="103b7-238">修正类型</span><span class="sxs-lookup"><span data-stu-id="103b7-238">Remediation type</span></span> | <span data-ttu-id="103b7-239">Update</span><span class="sxs-lookup"><span data-stu-id="103b7-239">Update</span></span>
<span data-ttu-id="103b7-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="103b7-240">vendorId</span></span> | <span data-ttu-id="103b7-241">String</span><span class="sxs-lookup"><span data-stu-id="103b7-241">String</span></span> | <span data-ttu-id="103b7-242">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="103b7-242">Related vendor name</span></span> | <span data-ttu-id="103b7-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="103b7-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="103b7-244">示例</span><span class="sxs-lookup"><span data-stu-id="103b7-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="103b7-245">请求示例</span><span class="sxs-lookup"><span data-stu-id="103b7-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="103b7-246">响应示例</span><span class="sxs-lookup"><span data-stu-id="103b7-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="103b7-247">另请参阅</span><span class="sxs-lookup"><span data-stu-id="103b7-247">See also</span></span>

- [<span data-ttu-id="103b7-248">修正方法和属性</span><span class="sxs-lookup"><span data-stu-id="103b7-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="103b7-249">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="103b7-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="103b7-250">列出修正活动的暴露设备</span><span class="sxs-lookup"><span data-stu-id="103b7-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="103b7-251">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="103b7-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="103b7-252">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="103b7-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
