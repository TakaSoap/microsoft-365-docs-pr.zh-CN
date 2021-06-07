---
title: 按 ID 获取一个修正活动
description: 返回指定修正活动的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 按 ID 修正，
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
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772145"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="c0ef1-104">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="c0ef1-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0ef1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c0ef1-105">**Applies to:**</span></span>

- [<span data-ttu-id="c0ef1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0ef1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c0ef1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0ef1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c0ef1-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c0ef1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0ef1-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c0ef1-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="c0ef1-110">API description</span></span>

<span data-ttu-id="c0ef1-111">返回指定修正活动的信息。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="c0ef1-112">显示与获取 [所有修正活动](get-remediation-all-activities.md)相同的列，但仅返回一 _个指定的修正活动的结果_。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="c0ef1-113">[详细了解修正活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="c0ef1-114">列出 id 指定的 (修正) </span><span class="sxs-lookup"><span data-stu-id="c0ef1-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="c0ef1-115">**URL：** GET： /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="c0ef1-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="c0ef1-116">权限</span><span class="sxs-lookup"><span data-stu-id="c0ef1-116">Permissions</span></span>

<span data-ttu-id="c0ef1-117">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c0ef1-118">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c0ef1-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c0ef1-119">权限类型</span><span class="sxs-lookup"><span data-stu-id="c0ef1-119">Permission type</span></span> | <span data-ttu-id="c0ef1-120">权限</span><span class="sxs-lookup"><span data-stu-id="c0ef1-120">Permission</span></span> | <span data-ttu-id="c0ef1-121">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="c0ef1-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c0ef1-122">应用程序</span><span class="sxs-lookup"><span data-stu-id="c0ef1-122">Application</span></span> | <span data-ttu-id="c0ef1-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="c0ef1-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="c0ef1-124">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="c0ef1-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c0ef1-125">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="c0ef1-125">Delegated (work or school account)</span></span> | <span data-ttu-id="c0ef1-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="c0ef1-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="c0ef1-127">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="c0ef1-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="c0ef1-128">属性</span><span class="sxs-lookup"><span data-stu-id="c0ef1-128">Properties</span></span>

<span data-ttu-id="c0ef1-129">属性 (id) </span><span class="sxs-lookup"><span data-stu-id="c0ef1-129">Property (id)</span></span> | <span data-ttu-id="c0ef1-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="c0ef1-130">Data type</span></span> | <span data-ttu-id="c0ef1-131">说明</span><span class="sxs-lookup"><span data-stu-id="c0ef1-131">Description</span></span> | <span data-ttu-id="c0ef1-132">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="c0ef1-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c0ef1-133">“类别”</span><span class="sxs-lookup"><span data-stu-id="c0ef1-133">category</span></span> | <span data-ttu-id="c0ef1-134">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-134">String</span></span> | <span data-ttu-id="c0ef1-135">软件/安全配置 (修正活动的) </span><span class="sxs-lookup"><span data-stu-id="c0ef1-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="c0ef1-136">软件</span><span class="sxs-lookup"><span data-stu-id="c0ef1-136">Software</span></span>
<span data-ttu-id="c0ef1-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="c0ef1-137">completerEmail</span></span> | <span data-ttu-id="c0ef1-138">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-138">String</span></span> | <span data-ttu-id="c0ef1-139">如果修正活动是由某人手动完成的，此列将包含他们的电子邮件</span><span class="sxs-lookup"><span data-stu-id="c0ef1-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="c0ef1-140">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-140">null</span></span>
<span data-ttu-id="c0ef1-141">completerId</span><span class="sxs-lookup"><span data-stu-id="c0ef1-141">completerId</span></span> | <span data-ttu-id="c0ef1-142">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-142">String</span></span> | <span data-ttu-id="c0ef1-143">如果修正活动是由某人手动完成的，则此列包含其对象 ID</span><span class="sxs-lookup"><span data-stu-id="c0ef1-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="c0ef1-144">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-144">null</span></span>
<span data-ttu-id="c0ef1-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="c0ef1-145">completionMethod</span></span> | <span data-ttu-id="c0ef1-146">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-146">String</span></span> | <span data-ttu-id="c0ef1-147">如果所有设备 (都由选择"标记为已完成) 或"手动"进行修补，则修正活动可以"自动"完成。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="c0ef1-148">自动</span><span class="sxs-lookup"><span data-stu-id="c0ef1-148">Automatic</span></span>
<span data-ttu-id="c0ef1-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="c0ef1-149">createdOn</span></span> | <span data-ttu-id="c0ef1-150">日期时间</span><span class="sxs-lookup"><span data-stu-id="c0ef1-150">DateTime</span></span> | <span data-ttu-id="c0ef1-151">创建此修正活动的时间</span><span class="sxs-lookup"><span data-stu-id="c0ef1-151">Time this remediation activity was created</span></span> | <span data-ttu-id="c0ef1-152">2021-01-12T18：54：11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="c0ef1-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="c0ef1-153">description</span><span class="sxs-lookup"><span data-stu-id="c0ef1-153">description</span></span> | <span data-ttu-id="c0ef1-154">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-154">String</span></span> | <span data-ttu-id="c0ef1-155">此修正活动的说明</span><span class="sxs-lookup"><span data-stu-id="c0ef1-155">Description of this remediation activity</span></span> | <span data-ttu-id="c0ef1-156">将 Microsoft Silverlight 更新到更高版本，以减少影响设备的已知漏洞。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="c0ef1-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="c0ef1-157">dueOn</span></span> | <span data-ttu-id="c0ef1-158">日期时间</span><span class="sxs-lookup"><span data-stu-id="c0ef1-158">DateTime</span></span> | <span data-ttu-id="c0ef1-159">此修正活动的创建者设置的截止日期</span><span class="sxs-lookup"><span data-stu-id="c0ef1-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="c0ef1-160">2021-01-13T00：00：00Z</span><span class="sxs-lookup"><span data-stu-id="c0ef1-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="c0ef1-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="c0ef1-161">fixedDevices</span></span> |  | <span data-ttu-id="c0ef1-162">已修复的设备数量</span><span class="sxs-lookup"><span data-stu-id="c0ef1-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="c0ef1-163">2</span><span class="sxs-lookup"><span data-stu-id="c0ef1-163">2</span></span>
<span data-ttu-id="c0ef1-164">id</span><span class="sxs-lookup"><span data-stu-id="c0ef1-164">id</span></span> | <span data-ttu-id="c0ef1-165">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-165">String</span></span> | <span data-ttu-id="c0ef1-166">此修正活动的 ID</span><span class="sxs-lookup"><span data-stu-id="c0ef1-166">ID of this remediation activity</span></span> | <span data-ttu-id="c0ef1-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="c0ef1-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="c0ef1-168">nameId</span><span class="sxs-lookup"><span data-stu-id="c0ef1-168">nameId</span></span> | <span data-ttu-id="c0ef1-169">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-169">String</span></span> | <span data-ttu-id="c0ef1-170">相关产品名称</span><span class="sxs-lookup"><span data-stu-id="c0ef1-170">Related product name</span></span> | <span data-ttu-id="c0ef1-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="c0ef1-171">Microsoft Silverlight</span></span>
<span data-ttu-id="c0ef1-172">priority</span><span class="sxs-lookup"><span data-stu-id="c0ef1-172">priority</span></span> | <span data-ttu-id="c0ef1-173">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-173">String</span></span> | <span data-ttu-id="c0ef1-174">为此修正活动设置的创建者设置的优先级 (高\中\低) </span><span class="sxs-lookup"><span data-stu-id="c0ef1-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="c0ef1-175">高</span><span class="sxs-lookup"><span data-stu-id="c0ef1-175">High</span></span>
<span data-ttu-id="c0ef1-176">productId</span><span class="sxs-lookup"><span data-stu-id="c0ef1-176">productId</span></span> | <span data-ttu-id="c0ef1-177">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-177">String</span></span> | <span data-ttu-id="c0ef1-178">相关产品 ID</span><span class="sxs-lookup"><span data-stu-id="c0ef1-178">Related product ID</span></span> | <span data-ttu-id="c0ef1-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="c0ef1-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="c0ef1-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="c0ef1-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="c0ef1-181">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-181">String</span></span> | <span data-ttu-id="c0ef1-182">只能请求对没有用户影响的设备进行一些配置更改。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="c0ef1-183">此值指示"所有公开的设备"或"仅不会影响用户的设备"之间的选择。</span><span class="sxs-lookup"><span data-stu-id="c0ef1-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="c0ef1-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="c0ef1-184">AllExposedAssets</span></span>
<span data-ttu-id="c0ef1-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="c0ef1-185">rbacGroupNames</span></span> | <span data-ttu-id="c0ef1-186">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-186">String</span></span> | <span data-ttu-id="c0ef1-187">相关设备组名称</span><span class="sxs-lookup"><span data-stu-id="c0ef1-187">Related device group names</span></span> | <span data-ttu-id="c0ef1-188">[ "Windows Servers"， "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="c0ef1-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="c0ef1-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="c0ef1-189">recommendedProgram</span></span> | <span data-ttu-id="c0ef1-190">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-190">String</span></span> | <span data-ttu-id="c0ef1-191">要升级到的推荐程序</span><span class="sxs-lookup"><span data-stu-id="c0ef1-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="c0ef1-192">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-192">null</span></span>
<span data-ttu-id="c0ef1-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="c0ef1-193">recommendedVendor</span></span> | <span data-ttu-id="c0ef1-194">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-194">String</span></span> | <span data-ttu-id="c0ef1-195">建议升级到的供应商</span><span class="sxs-lookup"><span data-stu-id="c0ef1-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="c0ef1-196">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-196">null</span></span>
<span data-ttu-id="c0ef1-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="c0ef1-197">recommendedVersion</span></span> | <span data-ttu-id="c0ef1-198">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-198">String</span></span> | <span data-ttu-id="c0ef1-199">要更新/升级到的建议版本</span><span class="sxs-lookup"><span data-stu-id="c0ef1-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="c0ef1-200">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-200">null</span></span>
<span data-ttu-id="c0ef1-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="c0ef1-201">relatedComponent</span></span> | <span data-ttu-id="c0ef1-202">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-202">String</span></span> | <span data-ttu-id="c0ef1-203">此修正活动的相关组件 (安全建议计划的相关组件) </span><span class="sxs-lookup"><span data-stu-id="c0ef1-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="c0ef1-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="c0ef1-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="c0ef1-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="c0ef1-205">requesterEmail</span></span> | <span data-ttu-id="c0ef1-206">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-206">String</span></span> | <span data-ttu-id="c0ef1-207">创建者电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="c0ef1-207">Creator email address</span></span> | <span data-ttu-id="c0ef1-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0ef1-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="c0ef1-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="c0ef1-209">requesterId</span></span> | <span data-ttu-id="c0ef1-210">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-210">String</span></span> | <span data-ttu-id="c0ef1-211">Creator 对象 ID</span><span class="sxs-lookup"><span data-stu-id="c0ef1-211">Creator object id</span></span> | <span data-ttu-id="c0ef1-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="c0ef1-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="c0ef1-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="c0ef1-213">requesterNotes</span></span> | <span data-ttu-id="c0ef1-214">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-214">String</span></span> | <span data-ttu-id="c0ef1-215">注释 (此) 活动的创建者添加的自定义文本</span><span class="sxs-lookup"><span data-stu-id="c0ef1-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="c0ef1-216">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-216">null</span></span>
<span data-ttu-id="c0ef1-217">scid</span><span class="sxs-lookup"><span data-stu-id="c0ef1-217">scid</span></span> | <span data-ttu-id="c0ef1-218">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-218">String</span></span> | <span data-ttu-id="c0ef1-219">相关安全建议 SCID</span><span class="sxs-lookup"><span data-stu-id="c0ef1-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="c0ef1-220">空</span><span class="sxs-lookup"><span data-stu-id="c0ef1-220">null</span></span>
<span data-ttu-id="c0ef1-221">状态</span><span class="sxs-lookup"><span data-stu-id="c0ef1-221">status</span></span> | <span data-ttu-id="c0ef1-222">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-222">String</span></span> | <span data-ttu-id="c0ef1-223">修正活动状态 (/已完成) </span><span class="sxs-lookup"><span data-stu-id="c0ef1-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="c0ef1-224">活动</span><span class="sxs-lookup"><span data-stu-id="c0ef1-224">Active</span></span>
<span data-ttu-id="c0ef1-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="c0ef1-225">statusLastModifiedOn</span></span> | <span data-ttu-id="c0ef1-226">日期时间</span><span class="sxs-lookup"><span data-stu-id="c0ef1-226">DateTime</span></span> | <span data-ttu-id="c0ef1-227">更新状态字段的日期</span><span class="sxs-lookup"><span data-stu-id="c0ef1-227">Date when the status field was updated</span></span> | <span data-ttu-id="c0ef1-228">2021-01-12T18：54：11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="c0ef1-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="c0ef1-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="c0ef1-229">targetDevices</span></span> | <span data-ttu-id="c0ef1-230">长型</span><span class="sxs-lookup"><span data-stu-id="c0ef1-230">Long</span></span> | <span data-ttu-id="c0ef1-231">此修正适用于的公开设备数量</span><span class="sxs-lookup"><span data-stu-id="c0ef1-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="c0ef1-232">43</span><span class="sxs-lookup"><span data-stu-id="c0ef1-232">43</span></span>
<span data-ttu-id="c0ef1-233">title</span><span class="sxs-lookup"><span data-stu-id="c0ef1-233">title</span></span> | <span data-ttu-id="c0ef1-234">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-234">String</span></span> | <span data-ttu-id="c0ef1-235">此修正活动的标题</span><span class="sxs-lookup"><span data-stu-id="c0ef1-235">Title of this remediation activity</span></span> | <span data-ttu-id="c0ef1-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="c0ef1-236">Microsoft Silverlight</span></span>
<span data-ttu-id="c0ef1-237">type</span><span class="sxs-lookup"><span data-stu-id="c0ef1-237">type</span></span> | <span data-ttu-id="c0ef1-238">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-238">String</span></span> | <span data-ttu-id="c0ef1-239">修正类型</span><span class="sxs-lookup"><span data-stu-id="c0ef1-239">Remediation type</span></span> | <span data-ttu-id="c0ef1-240">更新</span><span class="sxs-lookup"><span data-stu-id="c0ef1-240">Update</span></span>
<span data-ttu-id="c0ef1-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="c0ef1-241">vendorId</span></span> | <span data-ttu-id="c0ef1-242">String</span><span class="sxs-lookup"><span data-stu-id="c0ef1-242">String</span></span> | <span data-ttu-id="c0ef1-243">相关供应商名称</span><span class="sxs-lookup"><span data-stu-id="c0ef1-243">Related vendor name</span></span> | <span data-ttu-id="c0ef1-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="c0ef1-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="c0ef1-245">示例</span><span class="sxs-lookup"><span data-stu-id="c0ef1-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="c0ef1-246">请求示例</span><span class="sxs-lookup"><span data-stu-id="c0ef1-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="c0ef1-247">响应示例</span><span class="sxs-lookup"><span data-stu-id="c0ef1-247">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c0ef1-248">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0ef1-248">See also</span></span>

- [<span data-ttu-id="c0ef1-249">修正方法和属性</span><span class="sxs-lookup"><span data-stu-id="c0ef1-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="c0ef1-250">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="c0ef1-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="c0ef1-251">列出修正活动的暴露设备</span><span class="sxs-lookup"><span data-stu-id="c0ef1-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="c0ef1-252">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="c0ef1-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="c0ef1-253">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="c0ef1-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
