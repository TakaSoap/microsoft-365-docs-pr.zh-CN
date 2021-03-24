---
title: 创建和查看安全建议例外 - 威胁和漏洞管理
description: 创建并监视威胁和漏洞管理中的安全建议异常。
keywords: microsoft defender atp tvm remediation， mdatp tvm， threat and vulnerability management， threat & vulnerability management， threat & vulnerability management remediation， tvm remediation intune， tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c8ad69930ce4faecbffbc6d2fab59bbe2cac06fa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055334"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="dc757-104">创建和查看安全建议例外 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="dc757-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc757-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dc757-105">**Applies to:**</span></span>

- [<span data-ttu-id="dc757-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc757-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="dc757-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="dc757-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="dc757-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc757-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="dc757-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="dc757-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dc757-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="dc757-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="dc757-111">当建议此时不相关时，作为修正请求的替代方法，你可以为建议创建例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="dc757-112">如果你的组织具有设备组，你将能够将异常范围范围缩小到特定设备组。</span><span class="sxs-lookup"><span data-stu-id="dc757-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="dc757-113">可以针对所选设备组或过去和现在的所有设备组创建例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="dc757-114">为建议创建例外时，建议在例外持续时间结束之前不会处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="dc757-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="dc757-115">建议状态将更改为"完全 **异常**"或"部分异常 (按设备组) 。</span><span class="sxs-lookup"><span data-stu-id="dc757-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="dc757-116">权限</span><span class="sxs-lookup"><span data-stu-id="dc757-116">Permissions</span></span>

<span data-ttu-id="dc757-117">只有具有"异常处理"权限的用户才能管理异常 (包括创建或取消) 。</span><span class="sxs-lookup"><span data-stu-id="dc757-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="dc757-118">[详细了解 RBAC 角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="dc757-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![异常处理权限的视图。](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="dc757-120">创建异常</span><span class="sxs-lookup"><span data-stu-id="dc757-120">Create an exception</span></span>

<span data-ttu-id="dc757-121">选择要创建例外的安全建议，然后选择" **例外"选项** 并填写表单。</span><span class="sxs-lookup"><span data-stu-id="dc757-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![显示"异常选项"按钮在安全建议飞出控件中的位置。](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="dc757-123">按设备组分组的异常</span><span class="sxs-lookup"><span data-stu-id="dc757-123">Exception by device group</span></span>

<span data-ttu-id="dc757-124">将异常应用于所有当前设备组或选择特定设备组。</span><span class="sxs-lookup"><span data-stu-id="dc757-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="dc757-125">将来设备组不会包含在异常中。</span><span class="sxs-lookup"><span data-stu-id="dc757-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="dc757-126">列表中不会显示已具有异常的设备组。</span><span class="sxs-lookup"><span data-stu-id="dc757-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="dc757-127">如果你仅选择某些设备组，建议状态将从"活动"更改为"部分异常"。</span><span class="sxs-lookup"><span data-stu-id="dc757-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="dc757-128">如果选择所有设备组，状态将更改为"完全异常"。</span><span class="sxs-lookup"><span data-stu-id="dc757-128">The state will change to “full exception” if you select all the device groups.</span></span>

![显示设备组下拉列表。](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="dc757-130">筛选的视图</span><span class="sxs-lookup"><span data-stu-id="dc757-130">Filtered views</span></span>

<span data-ttu-id="dc757-131">如果你已在任何威胁和漏洞管理页面上按设备组进行筛选，则只有经过筛选的设备组将显示为选项。</span><span class="sxs-lookup"><span data-stu-id="dc757-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="dc757-132">这是在任何威胁和漏洞管理页面上按设备组筛选的按钮：</span><span class="sxs-lookup"><span data-stu-id="dc757-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![显示所选设备组筛选器。](images/tvm-selected-device-groups.png)

<span data-ttu-id="dc757-134">具有已筛选设备组的异常视图：</span><span class="sxs-lookup"><span data-stu-id="dc757-134">Exception view with filtered device groups:</span></span>

![显示筛选的设备组下拉列表。](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="dc757-136">大量设备组</span><span class="sxs-lookup"><span data-stu-id="dc757-136">Large number of device groups</span></span>

<span data-ttu-id="dc757-137">如果你的组织拥有 20 多个设备组，请选择 **已筛选** 设备组选项旁边的"编辑"。</span><span class="sxs-lookup"><span data-stu-id="dc757-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![显示如何编辑大量组。](images/tvm-exception-edit-groups.png)

<span data-ttu-id="dc757-139">将出现一个飞出框，可在其中搜索和选择想要包含的设备组。</span><span class="sxs-lookup"><span data-stu-id="dc757-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="dc757-140">Select the check mark icon below Search to check/uncheck all.</span><span class="sxs-lookup"><span data-stu-id="dc757-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![显示大型设备组飞出。](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="dc757-142">全局例外</span><span class="sxs-lookup"><span data-stu-id="dc757-142">Global exceptions</span></span>

<span data-ttu-id="dc757-143">如果你拥有全局管理员权限 (Microsoft Defender ATP 管理员) ，你将能够创建和取消全局例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-143">If you have global administrator permissions (called Microsoft Defender ATP administrator), you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="dc757-144">它会影响 **组织** 的所有当前和未来设备组，只有具有相似权限的用户才能更改它。</span><span class="sxs-lookup"><span data-stu-id="dc757-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="dc757-145">建议状态将从"活动"更改为"完全例外"。</span><span class="sxs-lookup"><span data-stu-id="dc757-145">The recommendation state will change from “active” to “full exception.”</span></span>

![显示全局例外选项。](images/tvm-exception-global.png)

<span data-ttu-id="dc757-147">需要记住的一些内容：</span><span class="sxs-lookup"><span data-stu-id="dc757-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="dc757-148">如果建议在全局例外下，则设备组的新创建异常将暂停，直到全局异常过期或取消。</span><span class="sxs-lookup"><span data-stu-id="dc757-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="dc757-149">此后，新的设备组例外将生效，直到它们过期。</span><span class="sxs-lookup"><span data-stu-id="dc757-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="dc757-150">如果建议已具有特定设备组的例外，并且创建了全局例外，则设备组异常将暂停，直到它过期，或者全局异常在过期之前被取消。</span><span class="sxs-lookup"><span data-stu-id="dc757-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="dc757-151">Justification</span><span class="sxs-lookup"><span data-stu-id="dc757-151">Justification</span></span>

<span data-ttu-id="dc757-152">选择需要提交异常的理由，而不是修正相关安全建议。</span><span class="sxs-lookup"><span data-stu-id="dc757-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="dc757-153">填写理由上下文，然后设置例外持续时间。</span><span class="sxs-lookup"><span data-stu-id="dc757-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="dc757-154">以下列表详细介绍了例外选项背后的理由：</span><span class="sxs-lookup"><span data-stu-id="dc757-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="dc757-155">**第三** 方控制 - 第三方产品或软件已解决此建议 - 选择此理由类型将降低曝光分数并增加安全分数，因为风险已降低</span><span class="sxs-lookup"><span data-stu-id="dc757-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="dc757-156">**备用缓解** - 内部工具已解决此建议 - 选择此理由类型将降低曝光分数并增加安全分数，因为风险已降低</span><span class="sxs-lookup"><span data-stu-id="dc757-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="dc757-157">**接受风险** - 风险较低且/或实施建议成本过高</span><span class="sxs-lookup"><span data-stu-id="dc757-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="dc757-158">**计划的修正 (宽限期)** - 已计划，但正在等待执行或授权</span><span class="sxs-lookup"><span data-stu-id="dc757-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="dc757-159">查看所有异常</span><span class="sxs-lookup"><span data-stu-id="dc757-159">View all exceptions</span></span>

<span data-ttu-id="dc757-160">导航到 **"修正"** 页中的"例外 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="dc757-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="dc757-161">可以按理由、类型和状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="dc757-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="dc757-162">选择例外以打开包含更多详细信息的飞出区。</span><span class="sxs-lookup"><span data-stu-id="dc757-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="dc757-163">每个设备组的例外将包含例外范围中每个设备组的列表，你可以导出该列表。</span><span class="sxs-lookup"><span data-stu-id="dc757-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="dc757-164">您还可以查看相关建议或取消例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-164">You can also view the related recommendation or cancel the exception.</span></span>

![在"修正"页中显示"异常"选项卡。](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="dc757-166">如何取消异常</span><span class="sxs-lookup"><span data-stu-id="dc757-166">How to cancel an exception</span></span>

<span data-ttu-id="dc757-167">若要取消异常，请导航到" **修正"页** 中的"例外 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="dc757-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="dc757-168">选择例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-168">Select the exception.</span></span>

<span data-ttu-id="dc757-169">若要取消所有设备组或全局例外的异常，请选择"取消 **所有设备组例外"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="dc757-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="dc757-170">你只能取消你有权使用的设备组的例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![取消按钮。](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="dc757-172">取消特定设备组的例外</span><span class="sxs-lookup"><span data-stu-id="dc757-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="dc757-173">选择特定设备组以取消它的例外。</span><span class="sxs-lookup"><span data-stu-id="dc757-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="dc757-174">设备组将显示一个飞出，并且可以选择取消 **异常**。</span><span class="sxs-lookup"><span data-stu-id="dc757-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![显示如何选择特定设备组。](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="dc757-176">应用例外后查看影响</span><span class="sxs-lookup"><span data-stu-id="dc757-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="dc757-177">在"安全建议"页中，选择"自定义列 **"，** 并选中"在异常发生后公开 ("和"在) 后影响 ("复选框 **) 。**</span><span class="sxs-lookup"><span data-stu-id="dc757-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![显示自定义列选项。](images/tvm-after-exceptions.png)

<span data-ttu-id="dc757-179">在应用 (后) 公开的设备会显示在应用异常后仍易受漏洞攻击的其余设备。</span><span class="sxs-lookup"><span data-stu-id="dc757-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="dc757-180">影响曝光的异常理由包括"第三方控制"和"备用缓解"。</span><span class="sxs-lookup"><span data-stu-id="dc757-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="dc757-181">其他理由不会减少设备的曝光，并且它们仍被视为公开。</span><span class="sxs-lookup"><span data-stu-id="dc757-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="dc757-182">异常 (后的影响) 在应用异常后对曝光分数或安全分数的剩余影响。</span><span class="sxs-lookup"><span data-stu-id="dc757-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="dc757-183">影响分数的异常理由包括"第三方控制"和"备用缓解"。</span><span class="sxs-lookup"><span data-stu-id="dc757-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="dc757-184">其他理由不会减少设备的曝光，因此曝光分数和安全分数不会更改。</span><span class="sxs-lookup"><span data-stu-id="dc757-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![显示表格中的列。](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="dc757-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc757-186">Related topics</span></span>

- [<span data-ttu-id="dc757-187">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="dc757-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="dc757-188">修正漏洞</span><span class="sxs-lookup"><span data-stu-id="dc757-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="dc757-189">安全性建议</span><span class="sxs-lookup"><span data-stu-id="dc757-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="dc757-190">曝光分数</span><span class="sxs-lookup"><span data-stu-id="dc757-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="dc757-191">Microsoft 设备安全分数</span><span class="sxs-lookup"><span data-stu-id="dc757-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
