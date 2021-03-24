---
title: 我的组织中存在漏洞 - 威胁和漏洞管理
description: 列出 CVE 的常见 () 在组织中运行的软件中发现漏洞的 ID。 由 Microsoft Defender ATP 威胁和漏洞管理功能发现。
keywords: mdatp &漏洞管理， 威胁和漏洞管理， mdatp tvm 漏洞页面， 通过电视查找漏洞， tvm 漏洞列表， tvm 中的漏洞详细信息
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
ms.openlocfilehash: b42e25c409ba19639e77e95fafc3d939514511ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056504"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="2699f-105">我的组织中存在漏洞 - 威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="2699f-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2699f-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2699f-106">**Applies to:**</span></span>
- [<span data-ttu-id="2699f-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2699f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2699f-108">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="2699f-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2699f-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2699f-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2699f-110">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2699f-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2699f-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="2699f-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="2699f-112">威胁和漏洞管理使用 Defender 终结点保护中的相同信号扫描和检测漏洞。</span><span class="sxs-lookup"><span data-stu-id="2699f-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="2699f-113">" **漏洞** "页通过列出 CVE 中"常见漏洞和曝光" (CVE) 漏洞。</span><span class="sxs-lookup"><span data-stu-id="2699f-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="2699f-114">还可以查看严重性、常见漏洞评分系统 (CVSS) 分级、组织中的普遍程度、相应的漏洞、威胁见解等。</span><span class="sxs-lookup"><span data-stu-id="2699f-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="2699f-115">如果没有为漏洞分配正式的 CVE-ID，则由威胁和漏洞管理分配漏洞名称。</span><span class="sxs-lookup"><span data-stu-id="2699f-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="2699f-116">若要获取有关新漏洞事件的电子邮件，请参阅在 Microsoft [Defender for Endpoint](configure-vulnerability-email-notifications.md)中配置漏洞电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="2699f-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="2699f-117">导航到"漏洞"页面</span><span class="sxs-lookup"><span data-stu-id="2699f-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="2699f-118">以几种不同方式访问"漏洞"页面：</span><span class="sxs-lookup"><span data-stu-id="2699f-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="2699f-119">从 Microsoft Defender 安全中心的威胁和漏洞管理导航菜单中选择["漏洞"](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2699f-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="2699f-120">全局搜索</span><span class="sxs-lookup"><span data-stu-id="2699f-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="2699f-121">导航菜单</span><span class="sxs-lookup"><span data-stu-id="2699f-121">Navigation menu</span></span>

<span data-ttu-id="2699f-122">转到威胁和漏洞管理导航菜单，然后选择 **"漏洞** "以打开 CVEs 列表。</span><span class="sxs-lookup"><span data-stu-id="2699f-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="2699f-123">全局搜索中的漏洞</span><span class="sxs-lookup"><span data-stu-id="2699f-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="2699f-124">转到全局搜索下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="2699f-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="2699f-125">选择 **要查找** 的常见漏洞和 (CVE) ID 中的漏洞和密钥，然后选择搜索图标。</span><span class="sxs-lookup"><span data-stu-id="2699f-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="2699f-126">" **漏洞"** 页面将打开，并包含要查找的 CVE 信息。</span><span class="sxs-lookup"><span data-stu-id="2699f-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="2699f-127">![已选择下拉列表选项"漏洞"的全局搜索框和示例 CVE。](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="2699f-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="2699f-128">选择 CVE 打开包含详细信息的飞出面板，包括漏洞描述、详细信息、威胁见解和公开的设备。</span><span class="sxs-lookup"><span data-stu-id="2699f-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="2699f-129">若要在"漏洞"页中查看其余的漏洞，请键入 CVE，然后选择"搜索"。</span><span class="sxs-lookup"><span data-stu-id="2699f-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="2699f-130">漏洞概述</span><span class="sxs-lookup"><span data-stu-id="2699f-130">Weaknesses overview</span></span>

<span data-ttu-id="2699f-131">修正公开的设备中的漏洞，以降低对资产和组织的风险。</span><span class="sxs-lookup"><span data-stu-id="2699f-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="2699f-132">如果 **"公开的设备"** 列显示"0"，则意味着你没有风险。</span><span class="sxs-lookup"><span data-stu-id="2699f-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![登录页面存在缺陷。](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="2699f-134">泄露和威胁见解</span><span class="sxs-lookup"><span data-stu-id="2699f-134">Breach and threat insights</span></span>

<span data-ttu-id="2699f-135">当图标为红色时，在"威胁"列中查看任何相关的泄露和威胁见解。</span><span class="sxs-lookup"><span data-stu-id="2699f-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="2699f-136">始终对与持续威胁相关的建议设置优先级。</span><span class="sxs-lookup"><span data-stu-id="2699f-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="2699f-137">这些建议使用威胁见解图标"简单 ![ 绘制红色 Bug"进行标记。](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="2699f-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="2699f-138">和泄露见解图标 ![ 简单绘制一个指向目标的箭头 ](images/tvm_alert_icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2699f-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="2699f-139">如果在组织中发现漏洞，则突出显示"泄露见解"图标。</span><span class="sxs-lookup"><span data-stu-id="2699f-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="2699f-140">![将鼠标悬停在图标上时可能会显示泄露见解文本的示例。</span><span class="sxs-lookup"><span data-stu-id="2699f-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="2699f-141">其中显示"可能的活动警报与此建议关联。"](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="2699f-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="2699f-142">如果在组织中发现漏洞存在关联攻击，则突出显示威胁见解图标。</span><span class="sxs-lookup"><span data-stu-id="2699f-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="2699f-143">将鼠标悬停在图标上可显示威胁是攻击工具包的一部分，还是连接到特定高级永久市场活动或活动组。</span><span class="sxs-lookup"><span data-stu-id="2699f-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="2699f-144">如果可用，有一个指向威胁分析报告的链接，该报告包含零日攻击新闻、披露或相关安全公告。</span><span class="sxs-lookup"><span data-stu-id="2699f-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![将鼠标悬停在图标上时可能显示的威胁见解文本。](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="2699f-147">获取漏洞见解</span><span class="sxs-lookup"><span data-stu-id="2699f-147">Gain vulnerability insights</span></span>

<span data-ttu-id="2699f-148">如果选择 CVE，将打开一个飞出面板，该面板将包含详细信息，例如漏洞描述、详细信息、威胁见解和公开的设备。</span><span class="sxs-lookup"><span data-stu-id="2699f-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="2699f-149">相关方案中显示了"OS 功能"类别</span><span class="sxs-lookup"><span data-stu-id="2699f-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="2699f-150">你可以转到针对每个已公开设备的 CVE 的相关安全建议</span><span class="sxs-lookup"><span data-stu-id="2699f-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![漏洞飞出示例。](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="2699f-152">不支持的软件</span><span class="sxs-lookup"><span data-stu-id="2699f-152">Software that isn't supported</span></span>

<span data-ttu-id="2699f-153">当前不受威胁和漏洞管理&的 CVES 仍位于"漏洞"页面中。</span><span class="sxs-lookup"><span data-stu-id="2699f-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="2699f-154">由于软件不受支持，因此只有有限的数据可用。</span><span class="sxs-lookup"><span data-stu-id="2699f-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="2699f-155">使用不受支持的软件的 CES 不会提供公开的设备信息。</span><span class="sxs-lookup"><span data-stu-id="2699f-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="2699f-156">通过选择"公开设备"部分中的"不可用"选项，按不受支持的软件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="2699f-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![公开的设备筛选器。](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="2699f-158">查看其他位置的 CVE (项) 漏洞和曝光</span><span class="sxs-lookup"><span data-stu-id="2699f-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="2699f-159">仪表板中最易受攻击的软件</span><span class="sxs-lookup"><span data-stu-id="2699f-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="2699f-160">转到威胁 [和漏洞管理仪表板](tvm-dashboard-insights.md) ，然后向下滚动到" **最易受攻击的软件"小组件** 。</span><span class="sxs-lookup"><span data-stu-id="2699f-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="2699f-161">你将看到每个软件中发现漏洞的数量，以及威胁信息和设备曝光的一段时间的高级别视图。</span><span class="sxs-lookup"><span data-stu-id="2699f-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![具有四列的主要易受攻击的软件卡：软件、漏洞、威胁、公开的设备。](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="2699f-163">选择要调查的软件以转到向下钻取页面。</span><span class="sxs-lookup"><span data-stu-id="2699f-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="2699f-164">选择" **发现的漏洞"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2699f-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="2699f-165">选择要调查的漏洞，了解有关漏洞详细信息的详细信息</span><span class="sxs-lookup"><span data-stu-id="2699f-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Windows Server 2019 向下钻取概述。](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="2699f-167">发现设备页面中的漏洞</span><span class="sxs-lookup"><span data-stu-id="2699f-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="2699f-168">在设备页面中查看相关漏洞信息。</span><span class="sxs-lookup"><span data-stu-id="2699f-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="2699f-169">转到 Microsoft Defender 安全中心导航菜单栏，然后选择设备图标。</span><span class="sxs-lookup"><span data-stu-id="2699f-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="2699f-170">将 **打开"设备"** 列表页。</span><span class="sxs-lookup"><span data-stu-id="2699f-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="2699f-171">在 **"设备"列表** 页中，选择要调查的设备名称。</span><span class="sxs-lookup"><span data-stu-id="2699f-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![包含要调查的选定设备的设备列表。](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="2699f-173">设备页面将打开，并包含要调查的设备的详细信息和响应选项。</span><span class="sxs-lookup"><span data-stu-id="2699f-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="2699f-174">选择 **"发现的漏洞"。**</span><span class="sxs-lookup"><span data-stu-id="2699f-174">Select **Discovered vulnerabilities**.</span></span>

    ![包含详细信息和响应选项的设备页面。](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="2699f-176">选择要调查的漏洞，以打开包含 CVE 详细信息的飞出面板，例如：漏洞描述、威胁见解和检测逻辑。</span><span class="sxs-lookup"><span data-stu-id="2699f-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="2699f-177">CVE 检测逻辑</span><span class="sxs-lookup"><span data-stu-id="2699f-177">CVE Detection logic</span></span>

<span data-ttu-id="2699f-178">与软件证据类似，我们现在显示了在设备上应用的检测逻辑，以表明该设备易受攻击。</span><span class="sxs-lookup"><span data-stu-id="2699f-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="2699f-179">新部分称为"检测逻辑" (发现的设备页中发现的任何漏洞) 显示检测逻辑和来源。</span><span class="sxs-lookup"><span data-stu-id="2699f-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="2699f-180">相关方案中也显示了"OS 功能"类别。</span><span class="sxs-lookup"><span data-stu-id="2699f-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="2699f-181">只有在启用了特定操作系统组件时，CVE 才会影响运行易受攻击的操作系统的设备。</span><span class="sxs-lookup"><span data-stu-id="2699f-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="2699f-182">假设 Windows Server 2019 的 DNS 组件存在漏洞。</span><span class="sxs-lookup"><span data-stu-id="2699f-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="2699f-183">借助此新功能，我们将仅将此 CVE 附加到操作系统中启用了 DNS 功能的 Windows Server 2019 设备。</span><span class="sxs-lookup"><span data-stu-id="2699f-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![检测逻辑示例，列出在设备和 KB 上检测到的软件。](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="2699f-185">报告 inaccuracy</span><span class="sxs-lookup"><span data-stu-id="2699f-185">Report inaccuracy</span></span>

<span data-ttu-id="2699f-186">当你看到任何模糊、不准确或不完整的信息时报告误报。</span><span class="sxs-lookup"><span data-stu-id="2699f-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="2699f-187">还可以报告已修正的安全建议。</span><span class="sxs-lookup"><span data-stu-id="2699f-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="2699f-188">打开"漏洞"页上的 CVE。</span><span class="sxs-lookup"><span data-stu-id="2699f-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="2699f-189">选择 **"报告不准确"，** 将打开一个飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="2699f-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="2699f-190">从下拉菜单中选择不准确类别，并填写您的电子邮件地址和不准确的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2699f-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="2699f-191">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2699f-191">Select **Submit**.</span></span> <span data-ttu-id="2699f-192">将立即将反馈发送给威胁和漏洞管理专家。</span><span class="sxs-lookup"><span data-stu-id="2699f-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2699f-193">相关文章</span><span class="sxs-lookup"><span data-stu-id="2699f-193">Related articles</span></span>

- [<span data-ttu-id="2699f-194">威胁和漏洞管理概述</span><span class="sxs-lookup"><span data-stu-id="2699f-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2699f-195">安全性建议</span><span class="sxs-lookup"><span data-stu-id="2699f-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="2699f-196">软件清单</span><span class="sxs-lookup"><span data-stu-id="2699f-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="2699f-197">仪表板见解</span><span class="sxs-lookup"><span data-stu-id="2699f-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="2699f-198">查看和组织适用于终结点设备的 Microsoft Defender 列表</span><span class="sxs-lookup"><span data-stu-id="2699f-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
