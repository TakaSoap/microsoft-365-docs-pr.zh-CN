---
title: Microsoft Defender for Office 365 计划中的活动视图
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解 Microsoft Defender for Office 365 中的市场活动视图。
ms.openlocfilehash: 20cb50a4b304e148df24e54fac3a05c484cfa4f0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794360"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="18e42-103">Microsoft Defender for Office 365 中的市场活动视图</span><span class="sxs-lookup"><span data-stu-id="18e42-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="18e42-104">市场活动视图是 Microsoft Defender for Office 365 计划 2 (例如 Microsoft 365 E5 或具有 Defender for Office 365 计划 2 加载项的组织中的一项) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-104">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="18e42-105">安全与合规&中的活动视图可标识和分类服务中的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="18e42-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="18e42-106">Campaign Views 可以帮助你：</span><span class="sxs-lookup"><span data-stu-id="18e42-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="18e42-107">高效调查和应对钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="18e42-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="18e42-108">更好地了解攻击范围。</span><span class="sxs-lookup"><span data-stu-id="18e42-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="18e42-109">向决策者展示价值。</span><span class="sxs-lookup"><span data-stu-id="18e42-109">Show value to decision makers.</span></span>

<span data-ttu-id="18e42-110">借助 Campaign Views，可以让你比任何人都更快获得有关攻击的更全面概览。</span><span class="sxs-lookup"><span data-stu-id="18e42-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="18e42-111">什么是活动 (campaign)？</span><span class="sxs-lookup"><span data-stu-id="18e42-111">What is a campaign?</span></span>

<span data-ttu-id="18e42-112">活动是针对一个或多个组织的协同式电子邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="18e42-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="18e42-113">窃取凭据和公司数据的电子邮件攻击是一个规模较大且规模很大的行业。</span><span class="sxs-lookup"><span data-stu-id="18e42-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="18e42-114">随着技术不断加强，攻击者会修改其方法以确保持续成功。</span><span class="sxs-lookup"><span data-stu-id="18e42-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="18e42-115">Microsoft 利用整个服务中大量的反网络钓鱼、反垃圾邮件和反恶意软件数据来帮助识别活动。</span><span class="sxs-lookup"><span data-stu-id="18e42-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="18e42-116">我们根据若干因素分析和分类攻击信息。</span><span class="sxs-lookup"><span data-stu-id="18e42-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="18e42-117">例如：</span><span class="sxs-lookup"><span data-stu-id="18e42-117">For example:</span></span>

- <span data-ttu-id="18e42-118">**攻击源**：源 IP 地址和发件人电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="18e42-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="18e42-119">**邮件属性**：邮件的内容、样式和语气。</span><span class="sxs-lookup"><span data-stu-id="18e42-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="18e42-120">**邮件收件人**：收件人如何相关。</span><span class="sxs-lookup"><span data-stu-id="18e42-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="18e42-121">例如，收件人域、收件人工作职能 (管理员、主管人员等 ) 、公司类型 (大型、小型、公共、私有等 ) 和行业。</span><span class="sxs-lookup"><span data-stu-id="18e42-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="18e42-122">**攻击负载**：邮件中的恶意链接、附件或其他有效负载。</span><span class="sxs-lookup"><span data-stu-id="18e42-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="18e42-123">市场活动可能是短期的，或者可能跨越几天、几周或几个月（包括活动期和非活动期）。</span><span class="sxs-lookup"><span data-stu-id="18e42-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="18e42-124">可能会针对你的特定组织启动市场活动，或者你的组织可能是跨多个公司的更大活动的一部分。</span><span class="sxs-lookup"><span data-stu-id="18e42-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="18e42-125">安全与合规中心&视图</span><span class="sxs-lookup"><span data-stu-id="18e42-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="18e42-126">活动视图在安全与合规 [](https://protection.office.com)中心&**威胁管理** \> **活动，** 或直接位于 <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="18e42-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![安全和合规中心中的活动概述](../../media/campaigns-overview.png)

<span data-ttu-id="18e42-128">您还可以从：</span><span class="sxs-lookup"><span data-stu-id="18e42-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="18e42-129">**威胁管理** \>**资源管理器** \>**视图** \>**市场活动**</span><span class="sxs-lookup"><span data-stu-id="18e42-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="18e42-130">**威胁管理** \>**资源管理器** \>**视图** \>**所有电子邮件** \>**"市场活动"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="18e42-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="18e42-131">**威胁管理** \>**资源管理器** \>**视图** \>**网络钓鱼** \>**"市场活动"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="18e42-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="18e42-132">**威胁管理** \>**资源管理器** \>**视图** \>**恶意软件** \>**"市场活动"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="18e42-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="18e42-133">若要访问活动视图，你需要是安全与合规中心内组织管理、安全管理员或安全读者&组的成员。 </span><span class="sxs-lookup"><span data-stu-id="18e42-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="18e42-134">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="18e42-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="18e42-135">市场活动概述</span><span class="sxs-lookup"><span data-stu-id="18e42-135">Campaigns overview</span></span>

<span data-ttu-id="18e42-136">概述页面显示有关所有市场活动的信息。</span><span class="sxs-lookup"><span data-stu-id="18e42-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="18e42-137">在默认 **"市场活动"** 选项卡上，" **市场活动** 类型"区域显示一个条形图，显示每天的收件人数。</span><span class="sxs-lookup"><span data-stu-id="18e42-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="18e42-138">默认情况下，此图同时显示 **网络钓鱼和\*\*\*\*恶意软件** 数据。</span><span class="sxs-lookup"><span data-stu-id="18e42-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="18e42-139">如果看不到任何市场活动数据，请尝试更改日期范围或 [筛选器](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="18e42-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="18e42-140">概述页面的其余部分在"市场活动"选项卡 **上显示以下信息** ：</span><span class="sxs-lookup"><span data-stu-id="18e42-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="18e42-141">**名称**</span><span class="sxs-lookup"><span data-stu-id="18e42-141">**Name**</span></span>

- <span data-ttu-id="18e42-142">**示例主题**：活动中某封邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="18e42-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="18e42-143">请注意，活动的所有邮件不一定具有相同的主题。</span><span class="sxs-lookup"><span data-stu-id="18e42-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="18e42-144">目标 **：计算** 得出的百分比： (组织中) / (服务组织中所有组织的市场活动收件人总数) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="18e42-145">此值指示市场活动仅定向到你的组织的程度 (该值) 该值与针对服务中其他组织的 (值) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="18e42-146">**类型**： **此值为钓鱼** 邮件或 **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="18e42-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="18e42-147">**子类型**：此值包含有关市场活动的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="18e42-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="18e42-148">例如：</span><span class="sxs-lookup"><span data-stu-id="18e42-148">For example:</span></span>
  - <span data-ttu-id="18e42-149">**网络钓鱼**：如果可用，则此市场活动所钓鱼的品牌。</span><span class="sxs-lookup"><span data-stu-id="18e42-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="18e42-150">例如 `Microsoft` ，、 `365` `Unknown` `Outlook` 或 `DocuSign` 。</span><span class="sxs-lookup"><span data-stu-id="18e42-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="18e42-151">**恶意软件**：例如， `HTML/PHISH` 或 `HTML/<MalwareFamilyName>` 。</span><span class="sxs-lookup"><span data-stu-id="18e42-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="18e42-152">如果可用，则此市场活动所钓鱼的品牌。</span><span class="sxs-lookup"><span data-stu-id="18e42-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="18e42-153">当检测由 Defender for Office 365 技术驱动时，前缀 **ATP 将** 添加到子类型值。</span><span class="sxs-lookup"><span data-stu-id="18e42-153">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="18e42-154">**收件人**：此活动所面向的用户数。</span><span class="sxs-lookup"><span data-stu-id="18e42-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="18e42-155">**收件箱**：收件箱中收到来自此活动的邮件的用户数 ("垃圾邮件"文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="18e42-156">**单击**：单击 URL 或在网络钓鱼邮件中打开附件的用户数。</span><span class="sxs-lookup"><span data-stu-id="18e42-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="18e42-157">**单击率**：由"单击的收件箱 **"计算**  /  **得出的** 百分比。</span><span class="sxs-lookup"><span data-stu-id="18e42-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="18e42-158">此值是活动有效性的指示器。</span><span class="sxs-lookup"><span data-stu-id="18e42-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="18e42-159">换句话说，如果收件人能够将邮件标识为网络钓鱼邮件，并且他们未单击有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="18e42-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="18e42-160">请注意， **恶意软件** 市场活动中不会使用点击率。</span><span class="sxs-lookup"><span data-stu-id="18e42-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="18e42-161">**已访问**：实际通过有效负载网站的用户数。</span><span class="sxs-lookup"><span data-stu-id="18e42-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="18e42-162">如果存在 **Clicked 值** ，但安全链接阻止访问网站，则此值将为零。</span><span class="sxs-lookup"><span data-stu-id="18e42-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="18e42-163">" **宣传活动源** "选项卡显示世界地图中的邮件源。</span><span class="sxs-lookup"><span data-stu-id="18e42-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="18e42-164">筛选器和设置</span><span class="sxs-lookup"><span data-stu-id="18e42-164">Filters and settings</span></span>

<span data-ttu-id="18e42-165">在"市场活动视图"页面顶部，有几个筛选器和查询设置可帮助你查找和隔离特定市场活动。</span><span class="sxs-lookup"><span data-stu-id="18e42-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![市场活动筛选器](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="18e42-167">可以执行的最基本筛选是开始日期/时间和结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="18e42-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="18e42-168">若要进一步筛选视图，可以通过单击"市场活动类型"按钮，进行选择，然后单击"刷新"，对多个值进行单个属性 **筛选**。</span><span class="sxs-lookup"><span data-stu-id="18e42-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="18e42-169">以下列表介绍了"市场活动类型"按钮中可用的可筛选市场活动属性：</span><span class="sxs-lookup"><span data-stu-id="18e42-169">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="18e42-170">**基本**：</span><span class="sxs-lookup"><span data-stu-id="18e42-170">**Basic**:</span></span>
  - <span data-ttu-id="18e42-171">**市场活动类型**：选择 **恶意软件** 或 **网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="18e42-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="18e42-172">清除选定内容与同时选择两者的结果相同。</span><span class="sxs-lookup"><span data-stu-id="18e42-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="18e42-173">**市场活动名称**</span><span class="sxs-lookup"><span data-stu-id="18e42-173">**Campaign name**</span></span>
  - <span data-ttu-id="18e42-174">**市场活动子类型**</span><span class="sxs-lookup"><span data-stu-id="18e42-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="18e42-175">**发件人**</span><span class="sxs-lookup"><span data-stu-id="18e42-175">**Sender**</span></span>
  - <span data-ttu-id="18e42-176">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="18e42-176">**Recipients**</span></span>
  - <span data-ttu-id="18e42-177">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="18e42-177">**Sender domain**</span></span>
  - <span data-ttu-id="18e42-178">**主题**</span><span class="sxs-lookup"><span data-stu-id="18e42-178">**Subject**</span></span>
  - <span data-ttu-id="18e42-179">**附件的文件名**</span><span class="sxs-lookup"><span data-stu-id="18e42-179">**Attachment filename**</span></span>
  - <span data-ttu-id="18e42-180">**恶意软件系列**</span><span class="sxs-lookup"><span data-stu-id="18e42-180">**Malware family**</span></span>
  - <span data-ttu-id="18e42-181">**标记**：已应用指定用户标记的用户或 (包括优先级帐户) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-181">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="18e42-182">有关用户标记详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="18e42-182">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="18e42-183">**系统替代**</span><span class="sxs-lookup"><span data-stu-id="18e42-183">**System overrides**</span></span>
  - <span data-ttu-id="18e42-184">**传递操作**</span><span class="sxs-lookup"><span data-stu-id="18e42-184">**Delivery action**</span></span>
  - <span data-ttu-id="18e42-185">**其他操作**</span><span class="sxs-lookup"><span data-stu-id="18e42-185">**Additional action**</span></span>
  - <span data-ttu-id="18e42-186">**方向性**</span><span class="sxs-lookup"><span data-stu-id="18e42-186">**Directionality**</span></span>
  - <span data-ttu-id="18e42-187">**检测技术**</span><span class="sxs-lookup"><span data-stu-id="18e42-187">**Detection technology**</span></span>
  - <span data-ttu-id="18e42-188">**原始传递位置**</span><span class="sxs-lookup"><span data-stu-id="18e42-188">**Original delivery location**</span></span>
  - <span data-ttu-id="18e42-189">**最新送达位置**</span><span class="sxs-lookup"><span data-stu-id="18e42-189">**Latest delivery location**</span></span>
  - <span data-ttu-id="18e42-190">**系统替代**</span><span class="sxs-lookup"><span data-stu-id="18e42-190">**System overrides**</span></span>

- <span data-ttu-id="18e42-191">**高级**：</span><span class="sxs-lookup"><span data-stu-id="18e42-191">**Advanced**:</span></span>
  - <span data-ttu-id="18e42-192">**Internet 邮件 ID：** 在邮件头的 **Message-ID** 头字段中可用。</span><span class="sxs-lookup"><span data-stu-id="18e42-192">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="18e42-193">示例值是 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (括号) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-193">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="18e42-194">**网络邮件 ID：** 在邮件头的 **X-MS-Exchange-Organization-Network-Message-Id** 头字段中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="18e42-194">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="18e42-195">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="18e42-195">**Sender IP**</span></span>
  - <span data-ttu-id="18e42-196">**附件 SHA256：** 若要在 Windows 中查找文件的 SHA256 哈希值，在命令提示符中运行以下 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 命令：</span><span class="sxs-lookup"><span data-stu-id="18e42-196">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="18e42-197">**群集 ID**</span><span class="sxs-lookup"><span data-stu-id="18e42-197">**Cluster ID**</span></span>
  - <span data-ttu-id="18e42-198">**警报策略 ID**</span><span class="sxs-lookup"><span data-stu-id="18e42-198">**Alert Policy ID**</span></span>
  - <span data-ttu-id="18e42-199">**ZAP URL 信号**</span><span class="sxs-lookup"><span data-stu-id="18e42-199">**ZAP URL signal**</span></span>

- <span data-ttu-id="18e42-200">**URL：**</span><span class="sxs-lookup"><span data-stu-id="18e42-200">**URLs**:</span></span>
  - <span data-ttu-id="18e42-201">**URL 域**</span><span class="sxs-lookup"><span data-stu-id="18e42-201">**URL domain**</span></span>
  - <span data-ttu-id="18e42-202">**URL 域和路径**</span><span class="sxs-lookup"><span data-stu-id="18e42-202">**URL domain and path**</span></span>
  - <span data-ttu-id="18e42-203">**URL**</span><span class="sxs-lookup"><span data-stu-id="18e42-203">**URL**</span></span>
  - <span data-ttu-id="18e42-204">**URL 路径**</span><span class="sxs-lookup"><span data-stu-id="18e42-204">**URL path**</span></span>
  - <span data-ttu-id="18e42-205">**单击裁定**</span><span class="sxs-lookup"><span data-stu-id="18e42-205">**Click verdict**</span></span>

<span data-ttu-id="18e42-206">对于更高级筛选（包括按多个属性进行筛选），可以单击 **"高级** 筛选"按钮生成查询。</span><span class="sxs-lookup"><span data-stu-id="18e42-206">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="18e42-207">可以使用相同的市场活动属性，但具有以下增强功能：</span><span class="sxs-lookup"><span data-stu-id="18e42-207">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="18e42-208">可以单击 **"添加条件"** 选择多个条件。</span><span class="sxs-lookup"><span data-stu-id="18e42-208">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="18e42-209">您可以在条件之间 **选择"And"** 或 **"Or"** 运算符。</span><span class="sxs-lookup"><span data-stu-id="18e42-209">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="18e42-210">您可以选择条件 **列表底部的条件** 组项以形成复杂的复合条件。</span><span class="sxs-lookup"><span data-stu-id="18e42-210">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="18e42-211">完成后，单击"查询 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="18e42-211">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="18e42-212">创建基本或高级筛选器后，可以使用"保存查询"或"另存为 **"查询来保存它**。</span><span class="sxs-lookup"><span data-stu-id="18e42-212">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="18e42-213">稍后，返回到"市场活动视图"时，可以通过单击"保存的查询设置"加载 **保存的筛选器**。</span><span class="sxs-lookup"><span data-stu-id="18e42-213">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="18e42-214">若要导出图表或市场活动列表，请单击"导出"，然后选择"**导出图表数据**"或"**导出市场活动列表"。** </span><span class="sxs-lookup"><span data-stu-id="18e42-214">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="18e42-215">如果你有 Microsoft Defender for Endpoint 订阅，可以单击 **"MDE** 设置"来连接或断开与 Microsoft Defender for Endpoint 的市场活动信息。</span><span class="sxs-lookup"><span data-stu-id="18e42-215">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="18e42-216">有关详细信息，请参阅将 [Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成](integrate-office-365-ti-with-wdatp.md)。</span><span class="sxs-lookup"><span data-stu-id="18e42-216">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="18e42-217">活动详细信息</span><span class="sxs-lookup"><span data-stu-id="18e42-217">Campaign details</span></span>

<span data-ttu-id="18e42-218">单击某个市场活动的名称时，活动详细信息会显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="18e42-218">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="18e42-219">市场活动信息</span><span class="sxs-lookup"><span data-stu-id="18e42-219">Campaign information</span></span>

<span data-ttu-id="18e42-220">在市场活动详细信息视图的顶部，提供以下市场活动信息：</span><span class="sxs-lookup"><span data-stu-id="18e42-220">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="18e42-221">**ID**：唯一市场活动标识符。</span><span class="sxs-lookup"><span data-stu-id="18e42-221">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="18e42-222">**开始\*\*\*\*和结束**：市场活动的开始日期和结束日期。</span><span class="sxs-lookup"><span data-stu-id="18e42-222">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="18e42-223">请注意，这些日期可能超出在概述页上选择的筛选日期。</span><span class="sxs-lookup"><span data-stu-id="18e42-223">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="18e42-224">**影响**：此部分包含所选日期范围筛选器的以下 (或在日程表中选择的日期范围) ：</span><span class="sxs-lookup"><span data-stu-id="18e42-224">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  - <span data-ttu-id="18e42-225">收件人总数。</span><span class="sxs-lookup"><span data-stu-id="18e42-225">The total number of recipients.</span></span>
  - <span data-ttu-id="18e42-226">"收件箱"邮件数 (即传递到收件箱，而不是"垃圾邮件"文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-226">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="18e42-227">在网络钓鱼邮件中单击 URL 有效负载的用户数。</span><span class="sxs-lookup"><span data-stu-id="18e42-227">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="18e42-228">有多少用户访问了 URL。</span><span class="sxs-lookup"><span data-stu-id="18e42-228">Howe many users visited the URL.</span></span>

- <span data-ttu-id="18e42-229">目标 **：计算** 得出的百分比： (组织中) / (服务组织中所有组织的市场活动收件人总数) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-229">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="18e42-230">请注意，此值在活动的整个生命周期内计算，不会基于日期筛选器更改。</span><span class="sxs-lookup"><span data-stu-id="18e42-230">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="18e42-231">活动活动的交互式时间线：时间线显示活动在整个生命周期内的活动。</span><span class="sxs-lookup"><span data-stu-id="18e42-231">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="18e42-232">默认情况下，阴影区域包括你在概述中选择的日期范围筛选器。</span><span class="sxs-lookup"><span data-stu-id="18e42-232">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="18e42-233">可以单击并拖动以选择特定的起始点和终点，这将更改"影响"区域以及页面其余部分中显示的数据，如以下各节<u>中所述</u>。</span><span class="sxs-lookup"><span data-stu-id="18e42-233">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="18e42-234">在标题栏中，可以单击"下载市场活动写入"按钮"下载市场活动写入"图标，将市场活动详细信息下载到默认名为 (的 ![ Word ](../../media/download-campaign-write-up-button.png) 文档CampaignReport.docx) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-234">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="18e42-235">请注意，下载包含整个活动生命周期的详细信息 (您所选的筛选日期) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-235">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![市场活动信息](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="18e42-237">活动流</span><span class="sxs-lookup"><span data-stu-id="18e42-237">Campaign flow</span></span>

<span data-ttu-id="18e42-238">在活动详细信息视图的中间，有关市场活动的重要详细信息在水平流程图的"流"部分 (称为 _Sankey_ 图表) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-238">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="18e42-239">这些详细信息将帮助你了解活动的元素和组织中的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="18e42-239">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="18e42-240">流图中显示的信息由日程表中的着色日期范围控制，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="18e42-240">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![不包含用户 URL 单击次数的活动详细信息](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="18e42-242">如果将鼠标悬停在图表中的水平带区上，则将看到相关邮件的数目（例如来自特定来源 IP 的邮件，使用指定发件人域名的来自来源 IP 的邮件等）。</span><span class="sxs-lookup"><span data-stu-id="18e42-242">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="18e42-243">此图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="18e42-243">The diagram contains the following information:</span></span>

- <span data-ttu-id="18e42-244">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="18e42-244">**Sender IPs**</span></span>
- <span data-ttu-id="18e42-245">**发件人域名**</span><span class="sxs-lookup"><span data-stu-id="18e42-245">**Sender domains**</span></span>
- <span data-ttu-id="18e42-246">**筛选器裁定**： 裁定值与可用的网络钓鱼和垃圾邮件筛选裁定相关，如反垃圾邮件 [邮件头中所述](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="18e42-246">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="18e42-247">下表介绍了可用值：</span><span class="sxs-lookup"><span data-stu-id="18e42-247">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="18e42-248">值</span><span class="sxs-lookup"><span data-stu-id="18e42-248">Value</span></span>|<span data-ttu-id="18e42-249">垃圾邮件筛选器裁定</span><span class="sxs-lookup"><span data-stu-id="18e42-249">Spam filter verdict</span></span>|<span data-ttu-id="18e42-250">说明</span><span class="sxs-lookup"><span data-stu-id="18e42-250">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="18e42-251">**允许**</span><span class="sxs-lookup"><span data-stu-id="18e42-251">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="18e42-252">在垃圾邮件筛选评估之前，邮件被标记为非垃圾邮件和/或跳过筛选。</span><span class="sxs-lookup"><span data-stu-id="18e42-252">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="18e42-253">例如，邮件流规则将邮件标记为非垃圾邮件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="18e42-253">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="18e42-254">邮件由于其他原因跳过了垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="18e42-254">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="18e42-255">例如，发件人和收件人似乎在同一个组织中。</span><span class="sxs-lookup"><span data-stu-id="18e42-255">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="18e42-256">**已阻止**</span><span class="sxs-lookup"><span data-stu-id="18e42-256">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="18e42-257">在垃圾邮件筛选评估之前，邮件被标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="18e42-257">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="18e42-258">例如，通过邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="18e42-258">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="18e42-259">**已检测**</span><span class="sxs-lookup"><span data-stu-id="18e42-259">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="18e42-260">邮件被垃圾邮件筛选标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="18e42-260">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="18e42-261">**未检测到**</span><span class="sxs-lookup"><span data-stu-id="18e42-261">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="18e42-262">垃圾邮件筛选将邮件标记为非垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="18e42-262">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="18e42-263">**已发布**</span><span class="sxs-lookup"><span data-stu-id="18e42-263">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="18e42-264">邮件由于从隔离区中释放而跳过了垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="18e42-264">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="18e42-265">**租户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-265">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="18e42-266">邮件由于反垃圾邮件策略中的设置而跳过了垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="18e42-266">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="18e42-267">例如，发件人在允许的发件人列表或允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="18e42-267">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="18e42-268">**租户块**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-268">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="18e42-269">邮件被垃圾邮件筛选阻止，因为反垃圾邮件策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="18e42-269">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="18e42-270">例如，发件人在允许的发件人列表或允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="18e42-270">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="18e42-271">**用户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-271">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="18e42-272">邮件跳过了垃圾邮件筛选，因为发件人位于用户的安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="18e42-272">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="18e42-273">**用户阻止**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-273">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="18e42-274">邮件被垃圾邮件筛选阻止，因为发件人位于用户的"阻止的发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="18e42-274">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="18e42-275">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="18e42-275">**ZAP**</span></span>|<span data-ttu-id="18e42-276">不适用</span><span class="sxs-lookup"><span data-stu-id="18e42-276">n/a</span></span>|<span data-ttu-id="18e42-277">[零时差自动清除 (ZAP) ](zero-hour-auto-purge.md) 将传递的邮件移动到"垃圾邮件"文件夹或隔离邮箱。</span><span class="sxs-lookup"><span data-stu-id="18e42-277">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="18e42-278">在反垃圾邮件策略中配置操作。</span><span class="sxs-lookup"><span data-stu-id="18e42-278">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="18e42-279"><sup>\*</sup> 查看反垃圾邮件策略，因为允许的邮件可能已被服务阻止。</span><span class="sxs-lookup"><span data-stu-id="18e42-279"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="18e42-280"><sup>\*\*</sup> 查看反垃圾邮件策略，因为这些邮件应隔离，而不是传递。</span><span class="sxs-lookup"><span data-stu-id="18e42-280"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="18e42-281">传递位置：你可能需要调查传递到收件人的邮件 (收件箱或垃圾邮件文件夹) ，即使用户未单击邮件中的有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="18e42-281">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="18e42-282">您还可以从隔离区中删除隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="18e42-282">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="18e42-283">有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="18e42-283">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="18e42-284">**已删除文件夹**</span><span class="sxs-lookup"><span data-stu-id="18e42-284">**Deleted folder**</span></span>
  - <span data-ttu-id="18e42-285">**已丢弃**</span><span class="sxs-lookup"><span data-stu-id="18e42-285">**Dropped**</span></span>
  - <span data-ttu-id="18e42-286">**外部**：收件人位于混合环境中本地电子邮件组织中。</span><span class="sxs-lookup"><span data-stu-id="18e42-286">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="18e42-287">**失败**</span><span class="sxs-lookup"><span data-stu-id="18e42-287">**Failed**</span></span>
  - <span data-ttu-id="18e42-288">**转发**</span><span class="sxs-lookup"><span data-stu-id="18e42-288">**Forwarded**</span></span>
  - <span data-ttu-id="18e42-289">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="18e42-289">**Inbox**</span></span>
  - <span data-ttu-id="18e42-290">**垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="18e42-290">**Junk folder**</span></span>
  - <span data-ttu-id="18e42-291">**隔离**</span><span class="sxs-lookup"><span data-stu-id="18e42-291">**Quarantine**</span></span>
  - <span data-ttu-id="18e42-292">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="18e42-292">**Unknown**</span></span>

- <span data-ttu-id="18e42-293">**URL 单击**：这些值在下一节中介绍。</span><span class="sxs-lookup"><span data-stu-id="18e42-293">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="18e42-294">在包含 10 多个项目的所有层中，显示前 10 项，其余项目在"其他"中捆绑 **在一起**。</span><span class="sxs-lookup"><span data-stu-id="18e42-294">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="18e42-295">URL 单击次数</span><span class="sxs-lookup"><span data-stu-id="18e42-295">URL clicks</span></span>

<span data-ttu-id="18e42-296">当网络钓鱼邮件传递到收件人的"收件箱"或"垃圾邮件"文件夹时，用户始终会单击有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="18e42-296">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="18e42-297">不单击 URL 是成功指标，但您需要确定网络钓鱼邮件甚至传递到邮箱的原因。</span><span class="sxs-lookup"><span data-stu-id="18e42-297">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="18e42-298">如果用户单击网络钓鱼邮件中的有效负载 URL，操作将显示在活动详细信息视图中图表的 **URL** 单击区域中。</span><span class="sxs-lookup"><span data-stu-id="18e42-298">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="18e42-299">**允许**</span><span class="sxs-lookup"><span data-stu-id="18e42-299">**Allowed**</span></span>
- <span data-ttu-id="18e42-300">**BlockPage：** 收件人单击了有效负载 URL，但他们对恶意网站的访问被贵组织中安全 [链接](atp-safe-links.md) 策略阻止。</span><span class="sxs-lookup"><span data-stu-id="18e42-300">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="18e42-301">**BlockPageOverride：** 收件人单击了邮件中的有效负载 URL，安全链接尝试阻止它们，但允许他们覆盖此块。</span><span class="sxs-lookup"><span data-stu-id="18e42-301">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="18e42-302">检查 [安全链接策略](set-up-atp-safe-links-policies.md) ，了解为什么允许用户替代安全链接裁定并继续访问恶意网站。</span><span class="sxs-lookup"><span data-stu-id="18e42-302">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="18e42-303">**PendingDetonationPage：Microsoft** Defender for Office 365 中的安全附件正在打开和调查虚拟计算机环境中的有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="18e42-303">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="18e42-304">**PendingDetonationPageOverride：** 允许收件人替代有效负载触发过程并打开 URL，而无需等待结果。</span><span class="sxs-lookup"><span data-stu-id="18e42-304">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="18e42-305">选项卡</span><span class="sxs-lookup"><span data-stu-id="18e42-305">Tabs</span></span>

<span data-ttu-id="18e42-306">市场活动详细信息视图中的选项卡允许你进一步调查市场活动。</span><span class="sxs-lookup"><span data-stu-id="18e42-306">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="18e42-307">选项卡上显示的信息由日程表中的阴影日期范围控制，如"市场活动信息" [部分](#campaign-information) 中所述。</span><span class="sxs-lookup"><span data-stu-id="18e42-307">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="18e42-308">**URL 单击**：如果用户未在邮件中单击有效负载 URL，则此部分将为空。</span><span class="sxs-lookup"><span data-stu-id="18e42-308">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="18e42-309">如果用户能够单击 URL，将填充以下值：</span><span class="sxs-lookup"><span data-stu-id="18e42-309">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="18e42-310">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-310">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="18e42-311">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-311">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="18e42-312">**单击时间**</span><span class="sxs-lookup"><span data-stu-id="18e42-312">**Click time**</span></span>
  - <span data-ttu-id="18e42-313">**单击裁定**</span><span class="sxs-lookup"><span data-stu-id="18e42-313">**Click verdict**</span></span>

- <span data-ttu-id="18e42-314">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="18e42-314">**Sender IPs**</span></span>
  - <span data-ttu-id="18e42-315">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-315">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="18e42-316">**总计数**</span><span class="sxs-lookup"><span data-stu-id="18e42-316">**Total count**</span></span>
  - <span data-ttu-id="18e42-317">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="18e42-317">**Inboxed**</span></span>
  - <span data-ttu-id="18e42-318">**未收件箱**</span><span class="sxs-lookup"><span data-stu-id="18e42-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="18e42-319">**SPF 通过**： 发件人策略框架和 [SPF (验证) 。](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="18e42-319">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="18e42-320">未通过 SPF 验证的发件人指示未经身份验证的发件人，或者邮件正在欺骗合法发件人。</span><span class="sxs-lookup"><span data-stu-id="18e42-320">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="18e42-321">**发件人**</span><span class="sxs-lookup"><span data-stu-id="18e42-321">**Senders**</span></span>
  - <span data-ttu-id="18e42-322">**发件人**：这是 SMTP MAIL FROM 命令中的实际发件人地址，不一定是用户在电子邮件客户端中看到的发件人：电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="18e42-322">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="18e42-323">**总计数**</span><span class="sxs-lookup"><span data-stu-id="18e42-323">**Total count**</span></span>
  - <span data-ttu-id="18e42-324">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="18e42-324">**Inboxed**</span></span>
  - <span data-ttu-id="18e42-325">**未收件箱**</span><span class="sxs-lookup"><span data-stu-id="18e42-325">**Not Inboxed**</span></span>
  - <span data-ttu-id="18e42-326">**DKIM 通过**： 发件人已通过 DKIM 身份验证的域密钥标识 [ (DKIM) 。](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="18e42-326">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="18e42-327">未通过 DKIM 验证的发件人指示未经身份验证的发件人，或者邮件正在欺骗合法发件人。</span><span class="sxs-lookup"><span data-stu-id="18e42-327">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="18e42-328">**DMARC 通过**： 发件人已通过基于域的邮件身份验证、 报告和一致性 ([DMARC) 。](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="18e42-328">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="18e42-329">未通过 DMARC 验证的发件人指示未经身份验证的发件人，或者邮件正在欺骗合法发件人。</span><span class="sxs-lookup"><span data-stu-id="18e42-329">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="18e42-330">**附件**</span><span class="sxs-lookup"><span data-stu-id="18e42-330">**Attachments**</span></span>
  - <span data-ttu-id="18e42-331">**Filename**</span><span class="sxs-lookup"><span data-stu-id="18e42-331">**Filename**</span></span>
  - <span data-ttu-id="18e42-332">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="18e42-332">**SHA256**</span></span>
  - <span data-ttu-id="18e42-333">**恶意软件系列**</span><span class="sxs-lookup"><span data-stu-id="18e42-333">**Malware family**</span></span>
  - <span data-ttu-id="18e42-334">**总计数**</span><span class="sxs-lookup"><span data-stu-id="18e42-334">**Total count**</span></span>

- <span data-ttu-id="18e42-335">**URL**</span><span class="sxs-lookup"><span data-stu-id="18e42-335">**URL**</span></span>
  - <span data-ttu-id="18e42-336">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18e42-336">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="18e42-337">**总计数**</span><span class="sxs-lookup"><span data-stu-id="18e42-337">**Total Count**</span></span>

<span data-ttu-id="18e42-338"><sup>\*</sup> 单击此值将打开一个新浮出控件，其中包含有关“活动详细信息”视图顶部的指定项（用户、URL 等）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="18e42-338"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="18e42-339">若要返回到“活动详细信息”视图，请单击新浮出控件中的“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="18e42-339">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="18e42-340">按钮</span><span class="sxs-lookup"><span data-stu-id="18e42-340">Buttons</span></span>

<span data-ttu-id="18e42-341">通过“活动详细信息”视图中的按钮，可使用威胁资源管理器的强大功能进一步调查活动。</span><span class="sxs-lookup"><span data-stu-id="18e42-341">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="18e42-342">**探索活动**：打开新的威胁资源管理器搜索选项卡，将 **活动 ID** 值用作搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="18e42-342">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
- <span data-ttu-id="18e42-343">**浏览收件箱邮件**：打开一个新的威胁资源管理器搜索选项卡，使用 **活动 ID** 和传递 **位置：收件箱** 作为搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="18e42-343">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
