---
title: Web 内容筛选
description: 使用 Microsoft Defender for Endpoint 中的 Web 内容筛选，根据网站的内容类别跟踪和监管对网站的访问。
keywords: Web 保护， Web 威胁防护， Web 浏览， 监视， 报告， 卡， 域列表， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a16e3eb8f6f7eae9fbaa82c9fd978f4fef429818
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822318"
---
# <a name="web-content-filtering"></a><span data-ttu-id="bdb0e-104">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="bdb0e-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bdb0e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-105">**Applies to:**</span></span>
- [<span data-ttu-id="bdb0e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bdb0e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bdb0e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdb0e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="bdb0e-108">**Web 内容筛选当前处于公共预览阶段**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="bdb0e-109">此预览版本在没有服务级别协议的情况下提供，不建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="bdb0e-110">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="bdb0e-111">有关详细信息，请参阅适用于终结点预览[功能的 Microsoft Defender。](preview.md)</span><span class="sxs-lookup"><span data-stu-id="bdb0e-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="bdb0e-112">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bdb0e-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bdb0e-113">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="bdb0e-114">Web 内容筛选是 Microsoft Defender for Endpoint 中的 [Web](web-protection-overview.md) 保护功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bdb0e-115">它使组织能够根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="bdb0e-116">许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="bdb0e-117">配置跨设备组的策略以阻止某些类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="bdb0e-118">阻止类别会阻止指定设备组内的用户访问与该类别关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="bdb0e-119">对于未阻止的任何类别，将自动审核 URL。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="bdb0e-120">用户无需中断即可访问 URL，并且你将收集访问统计信息以帮助创建更自定义的策略决策。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="bdb0e-121">如果用户正在查看的页面上的元素正在调用阻止的资源，则会看到阻止通知。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="bdb0e-122">Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Blocks 和 Opera) 执行) 。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="bdb0e-123">有关浏览器支持的信息，请参阅先决条件部分。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="bdb0e-124">总结优点：</span><span class="sxs-lookup"><span data-stu-id="bdb0e-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="bdb0e-125">阻止用户访问被阻止类别的网站，无论他们是在内部浏览还是离开</span><span class="sxs-lookup"><span data-stu-id="bdb0e-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="bdb0e-126">安全团队可以使用 Microsoft Defender for Endpoint 基于角色的访问控制设置中定义的设备组，便捷地将策略 [部署到用户组](/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="bdb0e-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="bdb0e-127">安全团队可以访问位于相同中心位置的 Web 报告，并查看实际块和 Web 使用情况</span><span class="sxs-lookup"><span data-stu-id="bdb0e-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="bdb0e-128">用户体验</span><span class="sxs-lookup"><span data-stu-id="bdb0e-128">User experience</span></span>

<span data-ttu-id="bdb0e-129">第三方支持的浏览器的阻止体验由网络保护提供，它提供系统级 Toast 以通知用户阻止的连接。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="bdb0e-130">为获得更用户友好的浏览器内体验，请考虑使用Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bdb0e-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="bdb0e-131">Prerequisites</span></span>

<span data-ttu-id="bdb0e-132">在尝试此功能之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="bdb0e-132">Before trying out this feature, make sure you meet the following requirements:</span></span>

- <span data-ttu-id="bdb0e-133">Windows 10 企业版E5、Microsoft 365 E5、Microsoft 365 E5 安全性、Microsoft 365 E3 + Microsoft 365 E5 安全性 加载项或 Microsoft Defender for Endpoint 独立许可证。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="bdb0e-134">访问 Microsoft Defender 安全中心 门户 (https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="bdb0e-135">运行 Windows 10 周年更新 (版本 1607) 或更高版本，包含最新的 Microsoft Defender 反恶意软件引擎更新。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest Microsoft Defender antimalware engine update.</span></span>

## <a name="data-handling"></a><span data-ttu-id="bdb0e-136">数据处理</span><span class="sxs-lookup"><span data-stu-id="bdb0e-136">Data handling</span></span>

<span data-ttu-id="bdb0e-137">数据存储在已选择作为 Microsoft Defender 终结点数据处理设置的[一部分的区域。](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="bdb0e-137">Data is stored in the region that was selected as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="bdb0e-138">您的数据不会离开该区域中的数据中心。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-138">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="bdb0e-139">此外，你的数据不会与任何第三方共享，包括我们的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-139">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="bdb0e-140">打开 Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="bdb0e-140">Turn on web content filtering</span></span>

<span data-ttu-id="bdb0e-141">从左侧导航菜单中，选择"设置  >  **高级**  >  **功能"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-141">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="bdb0e-142">向下滚动，直到您看到用于 Web 内容 **筛选的条目**。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-142">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="bdb0e-143">将开关切换到 **开** 和 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-143">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="bdb0e-144">配置 Web 内容筛选策略</span><span class="sxs-lookup"><span data-stu-id="bdb0e-144">Configure web content filtering policies</span></span>

<span data-ttu-id="bdb0e-145">Web 内容筛选策略指定在哪些设备组上阻止哪些网站类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-145">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="bdb0e-146">若要管理策略，请转到"设置  >    >  **Web 内容筛选"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-146">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="bdb0e-147">使用筛选器查找包含特定阻止类别或应用于特定设备组的策略。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-147">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="bdb0e-148">创建策略</span><span class="sxs-lookup"><span data-stu-id="bdb0e-148">Create a policy</span></span>

<span data-ttu-id="bdb0e-149">添加新策略：</span><span class="sxs-lookup"><span data-stu-id="bdb0e-149">To add a new policy:</span></span>

1. <span data-ttu-id="bdb0e-150">选择 **"Web 内容** 筛选"**页上的"** 添加 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-150">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="bdb0e-151">指定名称。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-151">Specify a name.</span></span>

3. <span data-ttu-id="bdb0e-152">选择要阻止的类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-152">Select the categories to block.</span></span> <span data-ttu-id="bdb0e-153">使用展开图标完全展开每个父类别并选择特定的 Web 内容类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-153">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="bdb0e-154">指定策略作用域。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-154">Specify the policy scope.</span></span> <span data-ttu-id="bdb0e-155">选择设备组以指定在何处应用策略。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-155">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="bdb0e-156">将仅阻止所选设备组中设备访问所选类别中的网站。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-156">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="bdb0e-157">查看摘要并保存策略。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-157">Review the summary and save the policy.</span></span> <span data-ttu-id="bdb0e-158">策略刷新可能需要 2 个小时才能应用到所选设备。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-158">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!NOTE]
> - <span data-ttu-id="bdb0e-159">无需在设备组上选择任何类别即可部署策略。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-159">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="bdb0e-160">此操作将创建仅审核策略，以帮助你在创建阻止策略之前了解用户行为。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-160">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>
> - <span data-ttu-id="bdb0e-161">如果同时删除策略或更改设备组，这可能会导致策略部署延迟。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-161">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>
> - <span data-ttu-id="bdb0e-162">阻止"未分类"类别可能会导致意外和意外的结果。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-162">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="bdb0e-163">允许特定网站</span><span class="sxs-lookup"><span data-stu-id="bdb0e-163">Allow specific websites</span></span>

<span data-ttu-id="bdb0e-164">通过创建自定义指示器策略，可以覆盖 Web 内容筛选中阻止的类别以允许单个网站。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-164">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="bdb0e-165">当自定义指示器策略应用于有关设备组时，它将取代 Web 内容筛选策略。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-165">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="bdb0e-166">通过访问"Microsoft Defender 安全中心 URL/域设置项 **"，** 在加载项  >    >  **中**  >  **创建自定义指示器**。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-166">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="bdb0e-167">输入网站的域。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-167">Enter the domain of the site.</span></span>

3. <span data-ttu-id="bdb0e-168">将策略操作设置为 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-168">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="bdb0e-169">报告不准确之处</span><span class="sxs-lookup"><span data-stu-id="bdb0e-169">Reporting inaccuracies</span></span>

<span data-ttu-id="bdb0e-170">如果遇到未正确分类的域，可以直接从"Web 内容筛选报告"页向我们报告不准确之处。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-170">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="bdb0e-171">此功能仅在新安全中心Microsoft 365可用 (security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-171">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="bdb0e-172">若要报告不准确的信息，请导航到"报告  >  **Web 保护 Web** 内容  >  **筛选详细信息**  >  **域"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-172">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="bdb0e-173">在我们的 Web 内容筛选报表的"域"选项卡上，你将在每个域旁边看到一个省略号。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-173">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="bdb0e-174">将鼠标悬停在此省略号上，然后选择 **"报告 Inaccuracy"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-174">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="bdb0e-175">将打开一个面板，您可以在其中选择优先级并添加其他详细信息，例如建议用于重新分类的类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-175">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="bdb0e-176">完成表单后，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="bdb0e-176">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="bdb0e-177">Our team will review the request within one business day.</span><span class="sxs-lookup"><span data-stu-id="bdb0e-177">Our team will review the request within one business day.</span></span> <span data-ttu-id="bdb0e-178">若要立即取消阻止，请创建自定义 [允许指示器](indicator-ip-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-178">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="bdb0e-179">Web 内容筛选卡和详细信息</span><span class="sxs-lookup"><span data-stu-id="bdb0e-179">Web content filtering cards and details</span></span>

<span data-ttu-id="bdb0e-180">选择 **"**  >  **报告 Web 保护**"以查看包含有关 Web 内容筛选和 Web 威胁防护信息的卡片。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-180">Select **Reports** > **Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="bdb0e-181">以下卡片提供有关 Web 内容筛选的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-181">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="bdb0e-182">按类别分类的 Web 活动</span><span class="sxs-lookup"><span data-stu-id="bdb0e-182">Web activity by category</span></span>

<span data-ttu-id="bdb0e-183">此卡片列出了访问尝试次数最大或减少的父 Web 内容类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-183">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="bdb0e-184">了解过去 30 天、3 个月或 6 个月内组织中 Web 活动模式的变化。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-184">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="bdb0e-185">选择类别名称以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-185">Select a category name to view more information.</span></span>

<span data-ttu-id="bdb0e-186">在使用此功能的前 30 天内，您的组织可能没有足够的数据来显示此信息。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-186">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![按类别卡片分类的 Web 活动的图像](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="bdb0e-188">Web 内容筛选摘要卡</span><span class="sxs-lookup"><span data-stu-id="bdb0e-188">Web content filtering  summary card</span></span>

<span data-ttu-id="bdb0e-189">此卡片显示阻止访问尝试跨不同父 Web 内容类别的分布。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-189">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="bdb0e-190">选择其中一个彩色栏以查看有关特定父 Web 类别的信息。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-190">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Web 内容筛选摘要卡的图像](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="bdb0e-192">Web 活动摘要卡片</span><span class="sxs-lookup"><span data-stu-id="bdb0e-192">Web activity summary card</span></span>

<span data-ttu-id="bdb0e-193">此卡片显示所有 URL 中 Web 内容的请求总数。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-193">This card displays the total number of requests for web content in all URLs.</span></span>

![Web 活动摘要卡片的图像](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="bdb0e-195">查看卡片详细信息</span><span class="sxs-lookup"><span data-stu-id="bdb0e-195">View card details</span></span>

<span data-ttu-id="bdb0e-196">通过从卡片 **的** 图表中选择表格行或彩色条，可以访问每张卡片的报告详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-196">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="bdb0e-197">每个卡片的报告详细信息页面包含有关 Web 内容类别、网站域和设备组的广泛统计数据。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-197">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Web 保护报告详细信息的图像](images/web-protection-report-details.png)

- <span data-ttu-id="bdb0e-199">**Web 类别**：列出组织中已尝试访问的 Web 内容类别。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-199">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="bdb0e-200">选择特定类别以打开摘要飞出。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-200">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="bdb0e-201">**域**：列出组织中已访问或阻止的 Web 域。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-201">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="bdb0e-202">选择特定域以查看有关该域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-202">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="bdb0e-203">**设备组**：列出在组织中生成 Web 活动的所有设备组</span><span class="sxs-lookup"><span data-stu-id="bdb0e-203">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="bdb0e-204">使用页面左上方的时区筛选器选择时间段。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-204">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="bdb0e-205">还可以筛选信息或自定义列。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-205">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="bdb0e-206">选择一行以打开一个包含有关所选项目的详细信息的飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-206">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="bdb0e-207">错误和问题</span><span class="sxs-lookup"><span data-stu-id="bdb0e-207">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="bdb0e-208">此预览版中的限制和已知问题</span><span class="sxs-lookup"><span data-stu-id="bdb0e-208">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="bdb0e-209">如果你Microsoft Edge操作系统配置是 Server (  >  **systeminfo** OS Configuration) ，则仅支持此  >  ) 。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-209">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="bdb0e-210">网络保护仅在服务器设备的检查模式下受支持，它负责保护跨受支持的第三方浏览器的流量。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-210">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="bdb0e-211">未分配的设备将在报告内显示不正确的数据。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-211">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="bdb0e-212">在"**报告详细信息**  >  **""** 设备组透视表"中，你可能会看到一个包含空白"设备组"字段的行。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-212">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="bdb0e-213">此组包含未分配设备，然后再放入指定组。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-213">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="bdb0e-214">此行的报告可能不包含设备或访问计数的准确计数。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-214">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="bdb0e-215">Web 内容筛选报告当前限制为显示前 5000 条记录。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-215">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="bdb0e-216">例如，"域"报告最多只显示给定筛选器查询前 5000 个域（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="bdb0e-216">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 


