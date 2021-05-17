---
title: 安全建议危险和漏洞管理
description: 获取可操作的安全建议（按威胁、泄露可能性和价值危险和漏洞管理。
keywords: 危险和漏洞管理， 适用于终结点的 Microsoft Defender 电视安全建议， 网络安全建议， 可操作的安全建议
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933729"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="74699-104">安全建议 - 危险和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="74699-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74699-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74699-105">**Applies to:**</span></span>

- [<span data-ttu-id="74699-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="74699-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="74699-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="74699-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="74699-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74699-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="74699-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="74699-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74699-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="74699-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="74699-111">组织中标识的网络安全漏洞将映射到可操作的安全建议，并按其影响确定优先级。</span><span class="sxs-lookup"><span data-stu-id="74699-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="74699-112">优先建议有助于缩短缓解或修正漏洞和推动合规性的时间。</span><span class="sxs-lookup"><span data-stu-id="74699-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="74699-113">每个安全建议都包括可操作修正步骤。</span><span class="sxs-lookup"><span data-stu-id="74699-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="74699-114">为了帮助进行任务管理，也可使用 Microsoft Intune 和 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="74699-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="74699-115">当威胁形势发生变化时，建议也会发生变化，因为它会持续从你的环境收集信息。</span><span class="sxs-lookup"><span data-stu-id="74699-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="74699-116">若要获取有关新漏洞事件的电子邮件，请参阅在 Microsoft [Defender for Endpoint](configure-vulnerability-email-notifications.md)中配置漏洞电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="74699-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="74699-117">运作方式</span><span class="sxs-lookup"><span data-stu-id="74699-117">How it works</span></span>

<span data-ttu-id="74699-118">组织的每台设备都基于三个重要因素进行评分，以帮助客户在正确的时间专注于正确的内容。</span><span class="sxs-lookup"><span data-stu-id="74699-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="74699-119">**威胁** - 组织设备中的漏洞和攻击的特征和泄露历史记录。</span><span class="sxs-lookup"><span data-stu-id="74699-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="74699-120">根据这些因素，安全建议显示活动警报的相应链接、正在进行的威胁活动及其相应的威胁分析报告。</span><span class="sxs-lookup"><span data-stu-id="74699-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="74699-121">**泄露可能性** - 组织的安全状态和抵御威胁的复原能力</span><span class="sxs-lookup"><span data-stu-id="74699-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="74699-122">**业务价值** - 组织的资产、关键流程和知识产权</span><span class="sxs-lookup"><span data-stu-id="74699-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="74699-123">导航到"安全建议"页</span><span class="sxs-lookup"><span data-stu-id="74699-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="74699-124">以几种不同方式访问"安全建议"页：</span><span class="sxs-lookup"><span data-stu-id="74699-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="74699-125">威胁漏洞管理导航菜单中[的Microsoft Defender 安全中心](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="74699-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="74699-126">仪表板中危险和漏洞管理[建议](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="74699-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="74699-127">查看以下位置的相关安全建议：</span><span class="sxs-lookup"><span data-stu-id="74699-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="74699-128">"软件"页</span><span class="sxs-lookup"><span data-stu-id="74699-128">Software page</span></span>
- <span data-ttu-id="74699-129">设备页面</span><span class="sxs-lookup"><span data-stu-id="74699-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="74699-130">导航菜单</span><span class="sxs-lookup"><span data-stu-id="74699-130">Navigation menu</span></span>

<span data-ttu-id="74699-131">转到导航危险和漏洞管理，然后选择 **安全建议**。</span><span class="sxs-lookup"><span data-stu-id="74699-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="74699-132">此页面包含针对组织中发现的威胁和漏洞的安全建议列表。</span><span class="sxs-lookup"><span data-stu-id="74699-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="74699-133">危险和漏洞管理仪表板中危险和漏洞管理建议</span><span class="sxs-lookup"><span data-stu-id="74699-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="74699-134">在给定一天中，作为安全管理员，你可以查看 危险和漏洞管理 仪表板[](tvm-dashboard-insights.md)，以查看你的曝光分数与设备的[](tvm-exposure-score.md)Microsoft 安全[分数并排](tvm-microsoft-secure-score-devices.md)显示。</span><span class="sxs-lookup"><span data-stu-id="74699-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="74699-135">目标是 **降低组织对** 漏洞的暴露程度，提高组织的设备安全性，以更稳定地抵御网络安全威胁攻击。</span><span class="sxs-lookup"><span data-stu-id="74699-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="74699-136">顶级安全建议列表可帮助你实现该目标。</span><span class="sxs-lookup"><span data-stu-id="74699-136">The top security recommendations list can help you achieve that goal.</span></span>

![顶级安全建议卡片示例，具有四个安全建议。](images/top-security-recommendations350.png)

<span data-ttu-id="74699-138">顶级安全建议列出了根据上一节中提到的重要因素（威胁、被泄露的可能性和价值）确定优先级的改进机会。</span><span class="sxs-lookup"><span data-stu-id="74699-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="74699-139">选择一个建议将你访问包含更多详细信息的安全建议页面。</span><span class="sxs-lookup"><span data-stu-id="74699-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="74699-140">安全建议概述</span><span class="sxs-lookup"><span data-stu-id="74699-140">Security recommendations overview</span></span>

<span data-ttu-id="74699-141">查看建议、发现漏洞的数量、相关组件、威胁见解、公开设备的数量、状态、修正类型、修正活动、对曝光分数和 Microsoft 设备安全分数的影响以及关联的标记。</span><span class="sxs-lookup"><span data-stu-id="74699-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="74699-142">"公开设备 **"图的颜色** 随着趋势的变化而更改。</span><span class="sxs-lookup"><span data-stu-id="74699-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="74699-143">如果公开的设备数量上升，则颜色将变为红色。</span><span class="sxs-lookup"><span data-stu-id="74699-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="74699-144">如果公开设备的数量减少，图形的颜色将变为绿色。</span><span class="sxs-lookup"><span data-stu-id="74699-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="74699-145">威胁漏洞管理显示最多 **30** 天之前使用的设备。</span><span class="sxs-lookup"><span data-stu-id="74699-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="74699-146">这不同于适用于终结点的 Microsoft Defender 的其余部分，如果设备已使用超过 7 天，则设备处于"非活动"状态。</span><span class="sxs-lookup"><span data-stu-id="74699-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![安全建议登录页面示例。](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="74699-148">图标</span><span class="sxs-lookup"><span data-stu-id="74699-148">Icons</span></span>

<span data-ttu-id="74699-149">有用的图标也会快速吸引你注意：</span><span class="sxs-lookup"><span data-stu-id="74699-149">Useful icons also quickly call your attention to:</span></span>
- ![箭头命中目标](images/tvm_alert_icon.png) <span data-ttu-id="74699-151">可能的活动警报</span><span class="sxs-lookup"><span data-stu-id="74699-151">possible active alerts</span></span>
- ![红色 bug](images/tvm_bug_icon.png) <span data-ttu-id="74699-153">关联的公共攻击</span><span class="sxs-lookup"><span data-stu-id="74699-153">associated public exploits</span></span>
- ![光灯](images/tvm_insight_icon.png) <span data-ttu-id="74699-155">建议见解</span><span class="sxs-lookup"><span data-stu-id="74699-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="74699-156">探索安全建议选项</span><span class="sxs-lookup"><span data-stu-id="74699-156">Explore security recommendation options</span></span>

<span data-ttu-id="74699-157">选择要调查或处理的安全建议。</span><span class="sxs-lookup"><span data-stu-id="74699-157">Select the security recommendation that you want to investigate or process.</span></span>

![安全建议飞出页的示例。](images/secrec-flyouteolsw.png)

<span data-ttu-id="74699-159">从飞出菜单，可以选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="74699-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="74699-160">**打开软件页** - 打开软件页，获取有关软件及其分发方式的更多上下文。</span><span class="sxs-lookup"><span data-stu-id="74699-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="74699-161">这些信息可能包括威胁上下文、相关建议、发现的漏洞、公开的设备数量、发现的漏洞、已安装软件的设备的名称和详细信息以及版本分发。</span><span class="sxs-lookup"><span data-stu-id="74699-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="74699-162">[**修正选项**](tvm-remediation.md)- 提交修正请求以在 Microsoft Intune中打开票证，让 IT 管理员进行选取和解决。</span><span class="sxs-lookup"><span data-stu-id="74699-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="74699-163">在"修正"页中跟踪修正活动。</span><span class="sxs-lookup"><span data-stu-id="74699-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="74699-164">[**例外选项**](tvm-exception.md) - 提交异常、提供理由以及设置异常持续时间（如果尚无法修正问题）。</span><span class="sxs-lookup"><span data-stu-id="74699-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="74699-165">在设备上进行软件更改时，通常需要 2 个小时才能将数据反映在安全门户中。</span><span class="sxs-lookup"><span data-stu-id="74699-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="74699-166">但是，有时可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="74699-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="74699-167">配置更改可能需要 4 到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="74699-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="74699-168">调查设备曝光或影响的更改</span><span class="sxs-lookup"><span data-stu-id="74699-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="74699-169">如果公开设备的数量明显增长，或者对组织曝光分数和 Microsoft 设备安全分数的影响明显增加，则值得调查该安全建议。</span><span class="sxs-lookup"><span data-stu-id="74699-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="74699-170">选择建议和 **"打开软件"页**</span><span class="sxs-lookup"><span data-stu-id="74699-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="74699-171">选择 **"事件时间线** "选项卡以查看与该软件相关的所有影响事件，例如新漏洞或新的公共攻击。</span><span class="sxs-lookup"><span data-stu-id="74699-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="74699-172">详细了解事件时间线</span><span class="sxs-lookup"><span data-stu-id="74699-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="74699-173">确定如何处理增加或组织的曝光，例如提交修正请求</span><span class="sxs-lookup"><span data-stu-id="74699-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="74699-174">请求修正</span><span class="sxs-lookup"><span data-stu-id="74699-174">Request remediation</span></span>

<span data-ttu-id="74699-175">此危险和漏洞管理修复功能通过修正请求工作流填补了安全和 IT 管理员之间的空白。</span><span class="sxs-lookup"><span data-stu-id="74699-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="74699-176">安全管理员（如你可以请求 IT 管理员将漏洞从安全建议页面修正到Intune）</span><span class="sxs-lookup"><span data-stu-id="74699-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="74699-177">了解有关修正选项的详细信息</span><span class="sxs-lookup"><span data-stu-id="74699-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="74699-178">如何请求修正</span><span class="sxs-lookup"><span data-stu-id="74699-178">How to request remediation</span></span>

<span data-ttu-id="74699-179">选择要请求修正的安全建议，然后选择"修正 **选项"。**</span><span class="sxs-lookup"><span data-stu-id="74699-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="74699-180">填写表单，然后选择"提交 **请求"。**</span><span class="sxs-lookup"><span data-stu-id="74699-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="74699-181">转到" [**修正"**](tvm-remediation.md) 页以查看修正请求的状态。</span><span class="sxs-lookup"><span data-stu-id="74699-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="74699-182">了解有关如何请求修正的信息</span><span class="sxs-lookup"><span data-stu-id="74699-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="74699-183">异常文件</span><span class="sxs-lookup"><span data-stu-id="74699-183">File for exception</span></span>

<span data-ttu-id="74699-184">当建议此时不相关时，作为修正请求的替代方法，你可以为建议创建例外。</span><span class="sxs-lookup"><span data-stu-id="74699-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="74699-185">详细了解异常</span><span class="sxs-lookup"><span data-stu-id="74699-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="74699-186">只有具有"异常处理"权限的用户才能添加异常。</span><span class="sxs-lookup"><span data-stu-id="74699-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="74699-187">[详细了解 RBAC 角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="74699-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="74699-188">为建议创建例外时，建议不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="74699-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="74699-189">建议状态将更改为"完全 **异常**"或"部分异常 (按设备组) 。</span><span class="sxs-lookup"><span data-stu-id="74699-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="74699-190">如何创建异常</span><span class="sxs-lookup"><span data-stu-id="74699-190">How to create an exception</span></span>

<span data-ttu-id="74699-191">选择要为 创建例外的安全建议，然后选择例外 **选项**。</span><span class="sxs-lookup"><span data-stu-id="74699-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![显示"异常选项"按钮在安全建议飞出控件中的位置。](images/tvm-exception-options.png)

<span data-ttu-id="74699-193">填写表单并提交。</span><span class="sxs-lookup"><span data-stu-id="74699-193">Fill out the form and submit.</span></span> <span data-ttu-id="74699-194">若要查看当前 (和过去) 的所有异常，请导航到"威胁 & 漏洞管理 [](tvm-remediation.md)"菜单下的"修正 **"** 页并选择"异常 **"选项卡。** 详细了解如何创建 [异常](tvm-exception.md#create-an-exception)</span><span class="sxs-lookup"><span data-stu-id="74699-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="74699-195">报告 inaccuracy</span><span class="sxs-lookup"><span data-stu-id="74699-195">Report inaccuracy</span></span>

<span data-ttu-id="74699-196">当你看到任何模糊、不准确、不完整或已修正的安全建议信息时，你可以报告误报。</span><span class="sxs-lookup"><span data-stu-id="74699-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="74699-197">打开安全建议。</span><span class="sxs-lookup"><span data-stu-id="74699-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="74699-198">选择要报告的安全建议旁边的三个点，然后选择"报告 **不准确"。**</span><span class="sxs-lookup"><span data-stu-id="74699-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![显示"报告不准确"按钮在安全建议飞出控件中。](images/report-inaccuracy500.png)

3. <span data-ttu-id="74699-200">从弹出窗格中，从下拉菜单中选择不准确类别，填写您的电子邮件地址和有关不准确的详细信息。</span><span class="sxs-lookup"><span data-stu-id="74699-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="74699-201">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="74699-201">Select **Submit**.</span></span> <span data-ttu-id="74699-202">你的反馈将立即发送给危险和漏洞管理专家。</span><span class="sxs-lookup"><span data-stu-id="74699-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="74699-203">相关文章</span><span class="sxs-lookup"><span data-stu-id="74699-203">Related articles</span></span>

- [<span data-ttu-id="74699-204">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="74699-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="74699-205">仪表板</span><span class="sxs-lookup"><span data-stu-id="74699-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="74699-206">风险评分</span><span class="sxs-lookup"><span data-stu-id="74699-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="74699-207">设备的 Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="74699-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="74699-208">修正漏洞</span><span class="sxs-lookup"><span data-stu-id="74699-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="74699-209">创建和查看安全建议例外</span><span class="sxs-lookup"><span data-stu-id="74699-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="74699-210">活动日程表</span><span class="sxs-lookup"><span data-stu-id="74699-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
