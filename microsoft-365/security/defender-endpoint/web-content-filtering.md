---
title: Web 内容筛选
description: 在 Microsoft Defender ATP 中，使用 Web 内容筛选根据网站的内容类别跟踪和监管对网站的访问。
keywords: Web 保护， Web 威胁防护， Web 浏览， 监视， 报告， 卡， 域列表， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a8ab1ba1f0dc1bb629e438380b7b77e1ed221f08
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186025"
---
# <a name="web-content-filtering"></a><span data-ttu-id="fe4ed-104">Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="fe4ed-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fe4ed-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="fe4ed-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe4ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fe4ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe4ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="fe4ed-108">**Web 内容筛选当前处于公共预览阶段**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="fe4ed-109">此预览版本在没有服务级别协议的情况下提供，不建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="fe4ed-110">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="fe4ed-111">有关详细信息，请参阅适用于终结点预览[功能的 Microsoft Defender。](preview.md)</span><span class="sxs-lookup"><span data-stu-id="fe4ed-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="fe4ed-112">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fe4ed-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe4ed-113">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="fe4ed-114">Web 内容筛选是 Microsoft Defender for Endpoint 中的 [Web](web-protection-overview.md) 保护功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fe4ed-115">它使组织能够根据网站的内容类别跟踪和监管对网站的访问。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="fe4ed-116">许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="fe4ed-117">配置跨设备组的策略以阻止某些类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="fe4ed-118">阻止类别会阻止指定设备组内的用户访问与该类别关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="fe4ed-119">对于未阻止的任何类别，将自动审核 URL。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="fe4ed-120">用户无需中断即可访问 URL，并且你将收集访问统计信息以帮助创建更自定义的策略决策。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="fe4ed-121">如果用户正在查看的页面上的元素正在调用阻止的资源，则会看到阻止通知。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="fe4ed-122">Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Blocks 和 Opera) 执行) 。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="fe4ed-123">有关浏览器支持的信息，请参阅先决条件部分。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="fe4ed-124">总结优点：</span><span class="sxs-lookup"><span data-stu-id="fe4ed-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="fe4ed-125">阻止用户访问被阻止类别的网站，无论他们是在内部浏览还是离开</span><span class="sxs-lookup"><span data-stu-id="fe4ed-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="fe4ed-126">使用 Microsoft Defender 中为基于终结点角色的访问控制设置定义的设备组，便捷地 [将策略部署到用户组](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="fe4ed-126">Conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="fe4ed-127">访问位于相同中心位置的 Web 报告，并查看实际块和 Web 使用情况</span><span class="sxs-lookup"><span data-stu-id="fe4ed-127">Access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="fe4ed-128">用户体验</span><span class="sxs-lookup"><span data-stu-id="fe4ed-128">User experience</span></span>

<span data-ttu-id="fe4ed-129">第三方支持的浏览器的阻止体验由网络保护提供，它提供系统级 Toast 以通知用户阻止的连接。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> 

<span data-ttu-id="fe4ed-130">有关更用户友好的浏览器内体验，请考虑使用 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-130">For a more user-friendly in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe4ed-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="fe4ed-131">Prerequisites</span></span>

<span data-ttu-id="fe4ed-132">在尝试此功能之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="fe4ed-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="fe4ed-133">Windows 10 企业版 E5 许可证或 Microsoft 365 E3 + Microsoft 365 E5 安全加载项。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-133">Windows 10 Enterprise E5 license OR Microsoft 365 E3 + Microsoft 365 E5 Security add-on.</span></span>
- <span data-ttu-id="fe4ed-134">访问 Microsoft Defender 安全中心门户</span><span class="sxs-lookup"><span data-stu-id="fe4ed-134">Access to Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="fe4ed-135">运行 Windows 10 周年更新 (版本 1607) 或更高版本使用最新的 MoCAMP 更新。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

<span data-ttu-id="fe4ed-136">如果未Windows Defender SmartScreen，网络保护将接管阻止。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-136">If Windows Defender SmartScreen isn't turned on, Network Protection will take over the blocking.</span></span> <span data-ttu-id="fe4ed-137">它需要 [在设备上启用网络](enable-network-protection.md) 保护。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-137">It requires [enabling Network Protection](enable-network-protection.md) on the device.</span></span> <span data-ttu-id="fe4ed-138">Chrome、Firefox、则和 Opera 当前是启用了此功能的第三方浏览器。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-138">Chrome, Firefox, Brave, and Opera are currently 3rd party browsers in which this feature is enabled.</span></span>

## <a name="data-handling"></a><span data-ttu-id="fe4ed-139">数据处理</span><span class="sxs-lookup"><span data-stu-id="fe4ed-139">Data handling</span></span>

<span data-ttu-id="fe4ed-140">我们将遵循你选择用作 Microsoft Defender 终结点数据处理设置的 [一部分的任何区域](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-140">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy).</span></span> <span data-ttu-id="fe4ed-141">您的数据不会离开该区域中的数据中心。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-141">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="fe4ed-142">此外，你的数据不会与任何第三方共享，包括我们的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-142">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="fe4ed-143">打开 Web 内容筛选</span><span class="sxs-lookup"><span data-stu-id="fe4ed-143">Turn on web content filtering</span></span>

<span data-ttu-id="fe4ed-144">从左侧导航菜单中，选择"常规>**高级>设置"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-144">From the left-hand navigation menu, select **Settings > General > Advanced Features**.</span></span> <span data-ttu-id="fe4ed-145">向下滚动，直到您看到用于 Web 内容 **筛选的条目**。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-145">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="fe4ed-146">将开关切换到 **开** 和 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-146">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="fe4ed-147">配置 Web 内容筛选策略</span><span class="sxs-lookup"><span data-stu-id="fe4ed-147">Configure web content filtering policies</span></span>

<span data-ttu-id="fe4ed-148">Web 内容筛选策略指定在哪些设备组上阻止哪些网站类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-148">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="fe4ed-149">若要管理策略，请转到"设置 **">"> Web 内容筛选"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-149">To manage the policies, go to **Settings > Rules > Web content filtering**.</span></span>

<span data-ttu-id="fe4ed-150">使用筛选器查找包含特定阻止类别或应用于特定设备组的策略。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-150">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="fe4ed-151">创建策略</span><span class="sxs-lookup"><span data-stu-id="fe4ed-151">Create a policy</span></span>

<span data-ttu-id="fe4ed-152">添加新策略：</span><span class="sxs-lookup"><span data-stu-id="fe4ed-152">To add a new policy:</span></span>

1. <span data-ttu-id="fe4ed-153">在 **"设置"** 中的 **"Web 内容筛选"页上选择**"添加 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-153">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>
2. <span data-ttu-id="fe4ed-154">指定名称。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-154">Specify a name.</span></span>
3. <span data-ttu-id="fe4ed-155">选择要阻止的类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-155">Select the categories to block.</span></span> <span data-ttu-id="fe4ed-156">使用展开图标完全展开每个父类别并选择特定的 Web 内容类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-156">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>
4. <span data-ttu-id="fe4ed-157">指定策略作用域。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-157">Specify the policy scope.</span></span> <span data-ttu-id="fe4ed-158">选择设备组以指定在何处应用策略。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-158">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="fe4ed-159">将仅阻止所选设备组中设备访问所选类别中的网站。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-159">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>
5. <span data-ttu-id="fe4ed-160">查看摘要并保存策略。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-160">Review the summary and save the policy.</span></span> <span data-ttu-id="fe4ed-161">策略刷新可能需要 2 个小时才能应用到所选设备。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-161">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

<span data-ttu-id="fe4ed-162">提示：无需在设备组上选择任何类别即可部署策略。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-162">Tip: You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="fe4ed-163">此操作将创建仅审核策略，以帮助你在创建阻止策略之前了解用户行为。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-163">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="fe4ed-164">如果同时删除策略或更改设备组，这可能会导致策略部署延迟。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-164">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fe4ed-165">阻止"未分类"类别可能会导致意外和意外的结果。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-165">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="fe4ed-166">允许特定网站</span><span class="sxs-lookup"><span data-stu-id="fe4ed-166">Allow specific websites</span></span>

<span data-ttu-id="fe4ed-167">通过创建自定义指示器策略，可以覆盖 Web 内容筛选中阻止的类别以允许单个网站。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-167">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="fe4ed-168">当自定义指示器策略应用于有关设备组时，它将取代 Web 内容筛选策略。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-168">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="fe4ed-169">通过访问设置指示器 URL/域添加项，在Microsoft Defender 安全  >    >  **中心中**  >  **创建自定义指示器**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-169">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**</span></span>
2. <span data-ttu-id="fe4ed-170">输入网站的域</span><span class="sxs-lookup"><span data-stu-id="fe4ed-170">Enter the domain of the site</span></span>
3. <span data-ttu-id="fe4ed-171">将策略操作设置为 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-171">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="fe4ed-172">报告不准确之处</span><span class="sxs-lookup"><span data-stu-id="fe4ed-172">Reporting inaccuracies</span></span>

<span data-ttu-id="fe4ed-173">如果遇到未正确分类的域，可以直接从"Web 内容筛选报告"页向我们报告不准确之处。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-173">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="fe4ed-174">此功能仅适用于新的 Microsoft 365 安全中心 (security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-174">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="fe4ed-175">若要报告不准确的信息，请导航到"报告 web > Web >**筛选详细信息>域"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-175">To report an inaccuracy, navigate to **Reports > Web protection > Web Content Filtering Details > Domains**.</span></span> <span data-ttu-id="fe4ed-176">在我们的 Web 内容筛选报表的"域"选项卡上，你将在每个域旁边看到一个省略号。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-176">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="fe4ed-177">将鼠标悬停在此省略号上，然后选择 **"报告 Inaccuracy"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-177">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="fe4ed-178">将打开一个面板，您可以在其中选择优先级并添加其他详细信息，例如建议用于重新分类的类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-178">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="fe4ed-179">完成表单后，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="fe4ed-179">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="fe4ed-180">Our team will review the request within one business day.</span><span class="sxs-lookup"><span data-stu-id="fe4ed-180">Our team will review the request within one business day.</span></span> <span data-ttu-id="fe4ed-181">若要立即取消阻止，请创建自定义 [允许指示器](indicator-ip-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-181">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="fe4ed-182">Web 内容筛选卡和详细信息</span><span class="sxs-lookup"><span data-stu-id="fe4ed-182">Web content filtering cards and details</span></span>

<span data-ttu-id="fe4ed-183">选择 **"> Web 保护"** 以查看包含有关 Web 内容筛选和 Web 威胁防护信息的卡片。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-183">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="fe4ed-184">以下卡片提供有关 Web 内容筛选的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-184">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="fe4ed-185">按类别分类的 Web 活动</span><span class="sxs-lookup"><span data-stu-id="fe4ed-185">Web activity by category</span></span>

<span data-ttu-id="fe4ed-186">此卡片列出了访问尝试次数最大或减少的父 Web 内容类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-186">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="fe4ed-187">了解过去 30 天、3 个月或 6 个月内组织中 Web 活动模式的变化。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-187">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="fe4ed-188">选择类别名称以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-188">Select a category name to view more information.</span></span>

<span data-ttu-id="fe4ed-189">在使用此功能的前 30 天内，您的组织可能没有足够的数据来显示此信息。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-189">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![按类别卡片分类的 Web 活动的图像](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="fe4ed-191">Web 内容筛选摘要卡</span><span class="sxs-lookup"><span data-stu-id="fe4ed-191">Web content filtering  summary card</span></span>

<span data-ttu-id="fe4ed-192">此卡片显示阻止访问尝试跨不同父 Web 内容类别的分布。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-192">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="fe4ed-193">选择其中一个彩色栏以查看有关特定父 Web 类别的信息。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-193">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Web 内容筛选摘要卡的图像](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="fe4ed-195">Web 活动摘要卡片</span><span class="sxs-lookup"><span data-stu-id="fe4ed-195">Web activity summary card</span></span>

<span data-ttu-id="fe4ed-196">此卡片显示所有 URL 中 Web 内容的请求总数。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-196">This card displays the total number of requests for web content in all URLs.</span></span>

![Web 活动摘要卡片的图像](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="fe4ed-198">查看卡片详细信息</span><span class="sxs-lookup"><span data-stu-id="fe4ed-198">View card details</span></span>

<span data-ttu-id="fe4ed-199">通过从卡片 **的** 图表中选择表格行或彩色条，可以访问每张卡片的报告详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-199">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="fe4ed-200">每个卡片的报告详细信息页面包含有关 Web 内容类别、网站域和设备组的广泛统计数据。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-200">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Web 保护报告详细信息的图像](images/web-protection-report-details.png)

- <span data-ttu-id="fe4ed-202">**Web 类别**：列出组织中已尝试访问的 Web 内容类别。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-202">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="fe4ed-203">选择特定类别以打开摘要飞出。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-203">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="fe4ed-204">**域**：列出组织中已访问或阻止的 Web 域。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-204">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="fe4ed-205">选择特定域以查看有关该域的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-205">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="fe4ed-206">**设备组**：列出在组织中生成 Web 活动的所有设备组</span><span class="sxs-lookup"><span data-stu-id="fe4ed-206">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="fe4ed-207">使用页面左上方的时区筛选器选择时间段。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-207">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="fe4ed-208">还可以筛选信息或自定义列。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-208">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="fe4ed-209">选择一行以打开一个包含有关所选项目的详细信息的飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-209">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="fe4ed-210">错误和问题</span><span class="sxs-lookup"><span data-stu-id="fe4ed-210">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="fe4ed-211">此预览版中的限制和已知问题</span><span class="sxs-lookup"><span data-stu-id="fe4ed-211">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="fe4ed-212">如果你的设备的操作系统配置是 Server (cmd > Systeminfo > OS Configuration) 。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-212">Only Microsoft Edge is supported if your device's OS configuration is Server (cmd > Systeminfo > OS Configuration).</span></span> <span data-ttu-id="fe4ed-213">网络保护仅在服务器设备的检查模式下受支持，它负责保护跨受支持的第三方浏览器的流量。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-213">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="fe4ed-214">未分配的设备将在报告内显示不正确的数据。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-214">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="fe4ed-215">在"设备>透视表详细信息"中，你可能会看到一个包含空白设备组字段的行。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-215">In the Report details > Device groups pivot, you may see a row with a blank Device Group field.</span></span> <span data-ttu-id="fe4ed-216">此组包含未分配设备，然后再放入指定组。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-216">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="fe4ed-217">此行的报告可能不包含设备或访问计数的准确计数。</span><span class="sxs-lookup"><span data-stu-id="fe4ed-217">The report for this row may not contain an accurate count of devices or access counts.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe4ed-218">相关主题</span><span class="sxs-lookup"><span data-stu-id="fe4ed-218">Related topics</span></span>

- [<span data-ttu-id="fe4ed-219">Web 保护概述</span><span class="sxs-lookup"><span data-stu-id="fe4ed-219">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="fe4ed-220">Web 威胁防护</span><span class="sxs-lookup"><span data-stu-id="fe4ed-220">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="fe4ed-221">监视 Web 安全</span><span class="sxs-lookup"><span data-stu-id="fe4ed-221">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="fe4ed-222">响应 Web 威胁</span><span class="sxs-lookup"><span data-stu-id="fe4ed-222">Respond to web threats</span></span>](web-protection-response.md)
