---
title: ATP 中的 Campaign Views
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
description: 了解 Office 365 高级威胁防护中的 Campaigns Views。
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825793"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="b354a-103">ATP 中的 Campaign Views</span><span class="sxs-lookup"><span data-stu-id="b354a-103">Campaign Views in ATP</span></span>

<span data-ttu-id="b354a-104">Campaign Views 是安全 & 合规中心中的高级威胁防护 (ATP) 中的一项功能，可以对服务中的钓鱼攻击进行识别和分类。</span><span class="sxs-lookup"><span data-stu-id="b354a-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="b354a-105">Campaign Views 可以帮助你：</span><span class="sxs-lookup"><span data-stu-id="b354a-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="b354a-106">高效调查和应对钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="b354a-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="b354a-107">更好地了解攻击范围。</span><span class="sxs-lookup"><span data-stu-id="b354a-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="b354a-108">向决策者展示价值。</span><span class="sxs-lookup"><span data-stu-id="b354a-108">Show value to decision makers.</span></span>

<span data-ttu-id="b354a-109">借助 Campaign Views，可以让你比任何人都更快获得有关攻击的更全面概览。</span><span class="sxs-lookup"><span data-stu-id="b354a-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="b354a-110">什么是活动 (campaign)？</span><span class="sxs-lookup"><span data-stu-id="b354a-110">What is a campaign?</span></span>

<span data-ttu-id="b354a-111">活动是针对一个或多个组织的协同式电子邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="b354a-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="b354a-112">拉备用凭据和公司数据的电子邮件攻击是一个大且有趣的行业。</span><span class="sxs-lookup"><span data-stu-id="b354a-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="b354a-113">随着阻止攻击的技术不断增加，攻击者会尽努力确保继续存在成功。</span><span class="sxs-lookup"><span data-stu-id="b354a-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="b354a-114">Microsoft 利用跨整个服务中数量来说过多数量的防钓鱼、反垃圾邮件和反恶意软件数据来帮助确定活动。</span><span class="sxs-lookup"><span data-stu-id="b354a-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="b354a-115">我们将根据几个因素来分析和分类攻击信息。</span><span class="sxs-lookup"><span data-stu-id="b354a-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="b354a-116">例如：</span><span class="sxs-lookup"><span data-stu-id="b354a-116">For example:</span></span>

- <span data-ttu-id="b354a-117">**攻击来源：源**IP 地址和发件人电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="b354a-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="b354a-118">**攻击邮件属性：** 邮件的内容、样式和语调。</span><span class="sxs-lookup"><span data-stu-id="b354a-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="b354a-119">**攻击收件人**：收件人域名、收件人工作职能（管理员、高管等）、公司类型（大型、小型、公共、私有等）和行业。</span><span class="sxs-lookup"><span data-stu-id="b354a-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="b354a-120">**攻击有效负载：** 邮件中的恶意链接、附件或其他有效负载。</span><span class="sxs-lookup"><span data-stu-id="b354a-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="b354a-121">活动可能短期有效，也可以跨多个天、数周或包含活动和非活动时段的月数。</span><span class="sxs-lookup"><span data-stu-id="b354a-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="b354a-122">市场活动可以针对你的特定组织进行发布，或者你的组织可能是拥有多个公司的大型活动的一部分。</span><span class="sxs-lookup"><span data-stu-id="b354a-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="b354a-123">Campaign Views 安全与&中心</span><span class="sxs-lookup"><span data-stu-id="b354a-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="b354a-124">在安全与活动管理活动，或[直接在&安全](https://protection.office.com)报告报告中或**Threat management**直接在安全活动活动中心 \> 中推出**Campaign** <https://protection.office.com/campaigns> Views。</span><span class="sxs-lookup"><span data-stu-id="b354a-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![安全和合规中心中的活动概述](../../media/campaigns-overview.png)

<span data-ttu-id="b354a-126">还可从以下位置转到 Campaign Views：</span><span class="sxs-lookup"><span data-stu-id="b354a-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="b354a-127">**威胁管理** \>**资源管理器** \>**视图** \>**活动**</span><span class="sxs-lookup"><span data-stu-id="b354a-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="b354a-128">**威胁管理** \>**资源管理器** \>**视图** \>**所有电子邮件** \>**"活动"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b354a-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="b354a-129">**威胁管理** \>**资源管理器** \>**视图** \>**网络钓鱼邮件** \>**"活动"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b354a-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="b354a-130">**威胁管理** \>**资源管理器** \>**视图** \>**恶意软件** \>**"活动"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b354a-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="b354a-131">要访问活动视图，需要是安全与合规中心**的组织**管理角色组、安全管理员 &**Security Administrator**安全读者角色**Security Reader**组的成员。</span><span class="sxs-lookup"><span data-stu-id="b354a-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="b354a-132">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b354a-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="b354a-133">活动概述</span><span class="sxs-lookup"><span data-stu-id="b354a-133">Campaigns overview</span></span>

<span data-ttu-id="b354a-134">"概述"页面上显示有关所有市场活动的信息。</span><span class="sxs-lookup"><span data-stu-id="b354a-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="b354a-135">在默认**的"活动"选项卡上\*\*\*\*，"活动类型**区域"中将显示每天接收者数的条形图。</span><span class="sxs-lookup"><span data-stu-id="b354a-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="b354a-136">默认情况下，该图同时显示**网络钓鱼和\*\*\*\*恶意软件**数据。</span><span class="sxs-lookup"><span data-stu-id="b354a-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="b354a-137">如果看不到任何活动数据，请尝试更改日期范围或 [筛选器](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="b354a-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="b354a-138">"概述"页面的其余部分在" **活动"选项卡上显示以下** 信息：</span><span class="sxs-lookup"><span data-stu-id="b354a-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="b354a-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="b354a-139">**Name**</span></span>

- <span data-ttu-id="b354a-140">**示例主题**：活动中某封邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="b354a-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="b354a-141">请注意，活动中的所有邮件的主题不一定都相同。</span><span class="sxs-lookup"><span data-stu-id="b354a-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="b354a-142">**目标**：计算所占的百分比： (组织) / (服务) 中所有组织中的市场活动收件人的总数。</span><span class="sxs-lookup"><span data-stu-id="b354a-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="b354a-143">此值指示市场活动在你的组织 (专门针对你的组织 (的一个较高值) 与其他组织定向到 (值) 的度。</span><span class="sxs-lookup"><span data-stu-id="b354a-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="b354a-144">**类型**：该值为钓**鱼或\*\*\*\*恶意软件。**</span><span class="sxs-lookup"><span data-stu-id="b354a-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="b354a-145">**子**类型：此值包含有关市场活动的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="b354a-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="b354a-146">例如：</span><span class="sxs-lookup"><span data-stu-id="b354a-146">For example:</span></span>

  - <span data-ttu-id="b354a-147">**网络钓鱼**：在可用时，是应用中被此活动取钓鱼的品牌。</span><span class="sxs-lookup"><span data-stu-id="b354a-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="b354a-148">例如， `Microsoft` 、 `365` `Unknown` 、 `Outlook` 或 `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="b354a-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="b354a-149">**恶意软件**：例如， `HTML/PHISH` 或 `HTML/<MalwareFamilyName>` 。</span><span class="sxs-lookup"><span data-stu-id="b354a-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="b354a-150">如果提供，则此活动正在网络钓鱼品牌。</span><span class="sxs-lookup"><span data-stu-id="b354a-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="b354a-151">如果检测由 ATP 技术驱动，则前缀 **ATP 将** 添加到子类型值中。</span><span class="sxs-lookup"><span data-stu-id="b354a-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="b354a-152">**收件人**：此活动所面向的用户数。</span><span class="sxs-lookup"><span data-stu-id="b354a-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="b354a-153">**收件箱**：在收件箱内收到此活动的邮件 (未传递到其"垃圾邮件"文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="b354a-154">**Clicked：** 单击 URL 或在网络钓鱼邮件中打开附件的用户数量。</span><span class="sxs-lookup"><span data-stu-id="b354a-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="b354a-155">**单击率**：由"单击的收件箱"计算**的**  /  **百**分比。</span><span class="sxs-lookup"><span data-stu-id="b354a-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="b354a-156">此值是活动有效性的指示器，以及收件人是否能够将邮件标识为网络钓鱼并避免单击有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="b354a-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="b354a-157">请注意，此值不在恶意软件活动中使用。</span><span class="sxs-lookup"><span data-stu-id="b354a-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="b354a-158">**已访问**：实际上有多少用户访问有效负载网站。</span><span class="sxs-lookup"><span data-stu-id="b354a-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="b354a-159">如果存在 **单击值** ，但安全链接阻止访问网站，此值将为零。</span><span class="sxs-lookup"><span data-stu-id="b354a-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="b354a-160">" **活动源"选项卡在** 世界地图上显示消息源。</span><span class="sxs-lookup"><span data-stu-id="b354a-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="b354a-161">筛选器和设置</span><span class="sxs-lookup"><span data-stu-id="b354a-161">Filters and settings</span></span>

<span data-ttu-id="b354a-162">在"活动视图"页面的顶部，有几种筛选器和查询设置，可帮助查找和隔离特定的活动。</span><span class="sxs-lookup"><span data-stu-id="b354a-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![活动筛选器](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="b354a-164">可以执行的最基本的筛选是开始日期/时间和结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="b354a-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="b354a-165">若要进一步筛选视图，可以通过单击 **"活动** 类型"按钮，进行选择，然后单击"刷新"，通过多个值 **筛选来进行筛选**。</span><span class="sxs-lookup"><span data-stu-id="b354a-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="b354a-166">以下列表介绍了可用的市场活动属性：</span><span class="sxs-lookup"><span data-stu-id="b354a-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="b354a-167">基本</span><span class="sxs-lookup"><span data-stu-id="b354a-167">Basic</span></span>

  - <span data-ttu-id="b354a-168">**市场活动类型：选择**"**恶意软件"** 或 **"钓鱼邮件"。**</span><span class="sxs-lookup"><span data-stu-id="b354a-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="b354a-169">清除选择的内容与选择两个选项的结果相同。</span><span class="sxs-lookup"><span data-stu-id="b354a-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="b354a-170">**活动名称**</span><span class="sxs-lookup"><span data-stu-id="b354a-170">**Campaign name**</span></span>
  - <span data-ttu-id="b354a-171">**市场活动子类型**</span><span class="sxs-lookup"><span data-stu-id="b354a-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="b354a-172">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b354a-172">**Sender**</span></span>
  - <span data-ttu-id="b354a-173">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="b354a-173">**Recipients**</span></span>
  - <span data-ttu-id="b354a-174">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="b354a-174">**Sender domain**</span></span>
  - <span data-ttu-id="b354a-175">**主题**</span><span class="sxs-lookup"><span data-stu-id="b354a-175">**Subject**</span></span>
  - <span data-ttu-id="b354a-176">**附件的文件名**</span><span class="sxs-lookup"><span data-stu-id="b354a-176">**Attachment filename**</span></span>
  - <span data-ttu-id="b354a-177">**恶意软件系列**</span><span class="sxs-lookup"><span data-stu-id="b354a-177">**Malware family**</span></span>
  - <span data-ttu-id="b354a-178">**传递操作**</span><span class="sxs-lookup"><span data-stu-id="b354a-178">**Delivery action**</span></span>
  - <span data-ttu-id="b354a-179">**检测技术**</span><span class="sxs-lookup"><span data-stu-id="b354a-179">**Detection technology**</span></span>
  - <span data-ttu-id="b354a-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b354a-180">**Tags**</span></span>
  - <span data-ttu-id="b354a-181">**系统替代**</span><span class="sxs-lookup"><span data-stu-id="b354a-181">**System overrides**</span></span>

- <span data-ttu-id="b354a-182">高级</span><span class="sxs-lookup"><span data-stu-id="b354a-182">Advanced</span></span>

  - <span data-ttu-id="b354a-183">**Internet 邮件 ID：** 在邮件 **头中的"** 邮件 ID 头"字段中可用。</span><span class="sxs-lookup"><span data-stu-id="b354a-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="b354a-184">示例值之前 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (括号) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="b354a-185">**网络邮件 ID：** 邮件头的 **X-MS-Exchange-Organization-Network-Message-Id** 头字段中提供的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="b354a-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="b354a-186">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="b354a-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="b354a-187">**附件 SHA256：** 若要在 Windows 中查找文件的 SHA256 哈希值，请在命令提示符中运行以下命令 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` ：</span><span class="sxs-lookup"><span data-stu-id="b354a-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="b354a-188">**群集 ID**</span><span class="sxs-lookup"><span data-stu-id="b354a-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="b354a-189">**提醒策略 ID**</span><span class="sxs-lookup"><span data-stu-id="b354a-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="b354a-190">URL</span><span class="sxs-lookup"><span data-stu-id="b354a-190">URLs</span></span>

  - <span data-ttu-id="b354a-191">**URL 域**</span><span class="sxs-lookup"><span data-stu-id="b354a-191">**URL domain**</span></span>
  - <span data-ttu-id="b354a-192">**URL 域和路径**</span><span class="sxs-lookup"><span data-stu-id="b354a-192">**URL domain and path**</span></span>
  - <span data-ttu-id="b354a-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="b354a-193">**URL**</span></span>
  - <span data-ttu-id="b354a-194">**URL 路径**</span><span class="sxs-lookup"><span data-stu-id="b354a-194">**URL path**</span></span>
  - <span data-ttu-id="b354a-195">**单击顶点**</span><span class="sxs-lookup"><span data-stu-id="b354a-195">**Click verdict**</span></span>

<span data-ttu-id="b354a-196">若要执行更高级的筛选（包括按多个属性进行筛选），可以单击" **高级筛选器"按钮** 来生成查询。</span><span class="sxs-lookup"><span data-stu-id="b354a-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="b354a-197">我们提供了相同的市场活动属性，但它们具有以下增强功能：</span><span class="sxs-lookup"><span data-stu-id="b354a-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="b354a-198">可单击" **添加条件"** 来选择多个条件。</span><span class="sxs-lookup"><span data-stu-id="b354a-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="b354a-199">您可在条件 **之间选择 And** **或 Or** 运算符。</span><span class="sxs-lookup"><span data-stu-id="b354a-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="b354a-200">您可以在条件列表 **底部** 选择条件组项目以形成复杂复合条件。</span><span class="sxs-lookup"><span data-stu-id="b354a-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="b354a-201">完成后，单击"查询 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b354a-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="b354a-202">基本或高级筛选器创建后，可以通过使用"保存查询"或"将**查询另存为"\*\*\*\*来保存它**。</span><span class="sxs-lookup"><span data-stu-id="b354a-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="b354a-203">稍后返回到活动视图时，可通过单击保存的查询设置来加载保存 **的筛选器**。</span><span class="sxs-lookup"><span data-stu-id="b354a-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="b354a-204">要导出图形或活动列表，请单击"导出并选择**导出图表数据\*\*\*\*"或"导出活动列表"。** **Export**</span><span class="sxs-lookup"><span data-stu-id="b354a-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="b354a-205">如果你有 Microsoft Defender ATP 订阅，可以单击 **WDATP** 以与 Microsoft Defender ATP 连接或断开市场活动信息。</span><span class="sxs-lookup"><span data-stu-id="b354a-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="b354a-206">有关详细信息，请参阅" [将 Office 365 ATP 与 Microsoft Defender ATP 集成](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)"。</span><span class="sxs-lookup"><span data-stu-id="b354a-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="b354a-207">活动详细信息</span><span class="sxs-lookup"><span data-stu-id="b354a-207">Campaign details</span></span>

<span data-ttu-id="b354a-208">单击活动的名称时，活动详细信息将显示在浮出控件中。</span><span class="sxs-lookup"><span data-stu-id="b354a-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="b354a-209">活动信息</span><span class="sxs-lookup"><span data-stu-id="b354a-209">Campaign information</span></span>

<span data-ttu-id="b354a-210">"活动详细信息"视图的顶部，可查看以下市场活动信息：</span><span class="sxs-lookup"><span data-stu-id="b354a-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="b354a-211">**ID：** 唯一市场活动标识符。</span><span class="sxs-lookup"><span data-stu-id="b354a-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="b354a-212">**已\*\*\*\*开始和**已结束：活动的开始日期和结束日期。</span><span class="sxs-lookup"><span data-stu-id="b354a-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="b354a-213">请注意，这些日期可能比你在概述页面上选择的过多的过滤日期更长。</span><span class="sxs-lookup"><span data-stu-id="b354a-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="b354a-214">**影响**：此部分包含您选择的日期范围筛选器 (以下数据 (您在时间线表项目中选择) ：</span><span class="sxs-lookup"><span data-stu-id="b354a-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="b354a-215">收件人总数。</span><span class="sxs-lookup"><span data-stu-id="b354a-215">The total number of recipients.</span></span>
  - <span data-ttu-id="b354a-216">"收件箱"发送 ("收件箱而不是传递到垃圾邮件文件夹文件夹的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="b354a-217">单击网络钓鱼邮件中的 URL 有效负载的用户数量。</span><span class="sxs-lookup"><span data-stu-id="b354a-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="b354a-218">多少用户访问了 URL。</span><span class="sxs-lookup"><span data-stu-id="b354a-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="b354a-219">**目标**：计算所占的百分比： (组织) / (服务) 中所有组织中的市场活动收件人的总数。</span><span class="sxs-lookup"><span data-stu-id="b354a-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="b354a-220">请注意，该值是在活动的整个生命周期内计算的，不会更改筛选日期。</span><span class="sxs-lookup"><span data-stu-id="b354a-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="b354a-221">活动活动的交互式日程表：时间线显示活动整个生命周期内的活动。</span><span class="sxs-lookup"><span data-stu-id="b354a-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="b354a-222">默认情况下，底纹区域包含你在概述中选择的日期范围筛选器。</span><span class="sxs-lookup"><span data-stu-id="b354a-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="b354a-223">你可以单击并拖动选择特定的起始点和终点， <u>这会更改在 **"影响"区域** 和页面的其余部分上显示的数据</u>。</span><span class="sxs-lookup"><span data-stu-id="b354a-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="b354a-224">在标题栏中，你可以单击"下载市场活动 **写入"** 按钮"下载市场 ![ 活动写入"图标，将活动详细信息下载到默认名为 ](../../media/download-campaign-write-up-button.png) CampaignReport.docx) 的 Word 文档 (。</span><span class="sxs-lookup"><span data-stu-id="b354a-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="b354a-225">请注意，此文档包含活动的整个生命周期的详细信息，不仅 (还包括你选择的筛选日期) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![活动信息](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="b354a-227">活动流</span><span class="sxs-lookup"><span data-stu-id="b354a-227">Campaign flow</span></span>

<span data-ttu-id="b354a-228">在活动详细信息视图的中间，有关活动的重要详细信息在水平流程图中的 **"流程** "部分 (称为 _"Sankey"_ 图，将) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="b354a-229">这些详细信息将帮助你了解活动的元素和组织中的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="b354a-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="b354a-230">流程图中显示的信息 **由** 日程表中的底纹日期范围控制，如上一节所述。</span><span class="sxs-lookup"><span data-stu-id="b354a-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![不包含用户 URL 单击次数的活动详细信息](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="b354a-232">如果将鼠标悬停在图表中的水平带区上，则将看到相关邮件的数目（例如来自特定来源 IP 的邮件，使用指定发件人域名的来自来源 IP 的邮件等）。</span><span class="sxs-lookup"><span data-stu-id="b354a-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="b354a-233">此图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="b354a-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="b354a-234">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="b354a-234">**Sender IPs**</span></span>

- <span data-ttu-id="b354a-235">**发件人域名**</span><span class="sxs-lookup"><span data-stu-id="b354a-235">**Sender domains**</span></span>

- <span data-ttu-id="b354a-236">**筛选器谓词**：这些值与反垃圾邮件标头中所述的可用网络钓鱼和 [垃圾邮件筛选反义相关](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="b354a-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="b354a-237">下表介绍了可用的值：</span><span class="sxs-lookup"><span data-stu-id="b354a-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="b354a-238">值</span><span class="sxs-lookup"><span data-stu-id="b354a-238">Value</span></span>|<span data-ttu-id="b354a-239">垃圾邮件筛选器谓词</span><span class="sxs-lookup"><span data-stu-id="b354a-239">Spam filter verdict</span></span>|<span data-ttu-id="b354a-240">说明</span><span class="sxs-lookup"><span data-stu-id="b354a-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="b354a-241">**允许**</span><span class="sxs-lookup"><span data-stu-id="b354a-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="b354a-242">在根据垃圾邮件筛选 (（也称为传输规则类型）评估前，邮件标记为"非垃圾邮件"和/或"过滤) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="b354a-243">出于其他原因，邮件 (例如，发件人和收件人可能在同一组织中已) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="b354a-244">**阻止**</span><span class="sxs-lookup"><span data-stu-id="b354a-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="b354a-245">例如，通过邮件流规则筛选出邮件在评估 (，该邮件被标记为垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="b354a-246">**已检测**</span><span class="sxs-lookup"><span data-stu-id="b354a-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="b354a-247">邮件被垃圾邮件筛选标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b354a-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="b354a-248">**未检测**</span><span class="sxs-lookup"><span data-stu-id="b354a-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="b354a-249">邮件被垃圾邮件筛选标记为"非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="b354a-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="b354a-250">**已发布**</span><span class="sxs-lookup"><span data-stu-id="b354a-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="b354a-251">邮件跳过了垃圾邮件筛选，因为从隔离中释放垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b354a-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="b354a-252">**租户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="b354a-253">由于反垃圾邮件策略设置类型忽略 (例如，发件人列在允许发件人列表或允许的域列表中，而导致邮件会跳过垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="b354a-254">**租户阻止**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="b354a-255">由于反垃圾邮件策略设置 (例如，发件人在允许发件人列表或允许的域列表中，邮件被垃圾邮件筛选阻止) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="b354a-256">**用户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="b354a-257">邮件跳过了垃圾邮件筛选，因为发件人位于 Outlook 中用户的安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="b354a-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="b354a-258">**用户阻止**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="b354a-259">邮件被垃圾邮件筛选阻止，因为发件人列在 Outlook 中用户的"阻止的发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="b354a-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="b354a-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="b354a-260">**ZAP**</span></span>|<span data-ttu-id="b354a-261">不适用</span><span class="sxs-lookup"><span data-stu-id="b354a-261">n/a</span></span>|<span data-ttu-id="b354a-262">[零时差自动 (ZAP ](zero-hour-auto-purge.md) 自动清除根据您的反垃圾邮件) 策略设置 (移至垃圾邮件文件夹或隔离邮件对传递的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b354a-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="b354a-263"><sup>\*</sup> 请查看你的反垃圾邮件策略，因为允许的邮件可能已被服务阻止。</span><span class="sxs-lookup"><span data-stu-id="b354a-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="b354a-264"><sup>\*\*</sup> 检查反垃圾邮件策略，因为应隔离这些邮件，未传递。</span><span class="sxs-lookup"><span data-stu-id="b354a-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="b354a-265">**送达位置**：你希望调查发送到收件人的邮件（发送到收件箱或垃圾邮件文件夹），即使用户未单击邮件中的有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="b354a-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="b354a-266">你还可以将隔离的邮件从隔离区中删除。</span><span class="sxs-lookup"><span data-stu-id="b354a-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="b354a-267">有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b354a-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="b354a-268">**已删除文件夹**</span><span class="sxs-lookup"><span data-stu-id="b354a-268">**Deleted folder**</span></span>
  - <span data-ttu-id="b354a-269">**Dropped**</span><span class="sxs-lookup"><span data-stu-id="b354a-269">**Dropped**</span></span>
  - <span data-ttu-id="b354a-270">**外部**：收件人位于混合环境中的本地电子邮件组织中。</span><span class="sxs-lookup"><span data-stu-id="b354a-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="b354a-271">**失败**</span><span class="sxs-lookup"><span data-stu-id="b354a-271">**Failed**</span></span>
  - <span data-ttu-id="b354a-272">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="b354a-272">**Forwarded**</span></span>
  - <span data-ttu-id="b354a-273">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="b354a-273">**Inbox**</span></span>
  - <span data-ttu-id="b354a-274">**垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="b354a-274">**Junk folder**</span></span>
  - <span data-ttu-id="b354a-275">**隔离**</span><span class="sxs-lookup"><span data-stu-id="b354a-275">**Quarantine**</span></span>
  - <span data-ttu-id="b354a-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="b354a-276">**Unknown**</span></span>

- <span data-ttu-id="b354a-277">**URL 单击：** 将在下一节中介绍这些内容。</span><span class="sxs-lookup"><span data-stu-id="b354a-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="b354a-278">在包含 10 个以上的项目的所有层中，会显示前 10 个项目，而其余层则被捆绑在其他 **项目中**。</span><span class="sxs-lookup"><span data-stu-id="b354a-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="b354a-279">URL 单击次数</span><span class="sxs-lookup"><span data-stu-id="b354a-279">URL clicks</span></span>

<span data-ttu-id="b354a-280">如果网络钓鱼邮件被传递到收件人 (至收件箱或垃圾邮件文件夹) ，用户总有可能会单击有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="b354a-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="b354a-281">如果未单击已传递邮件中的 URL，则只能准确地度量成功，但您需要首先确定将网络钓鱼邮件传递到其邮箱的原因。</span><span class="sxs-lookup"><span data-stu-id="b354a-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="b354a-282">如果用户单击了网络钓鱼邮件中的有效负载 URL，则操作将显示在活动详细信息视图中图表的 **URL** 单击区域。</span><span class="sxs-lookup"><span data-stu-id="b354a-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="b354a-283">**允许**</span><span class="sxs-lookup"><span data-stu-id="b354a-283">**Allowed**</span></span>

- <span data-ttu-id="b354a-284">**BlockPage：** 收件人单击有效负载 URL，但是他们对恶意网站的访问权限被组织中的 [ATP 安全链接](atp-safe-links.md) 策略阻止。</span><span class="sxs-lookup"><span data-stu-id="b354a-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="b354a-285">**BlockPageOverride：** 收件人单击邮件中的有效负载 URL，ATP 安全链接尝试阻止，但被允许替代阻止。</span><span class="sxs-lookup"><span data-stu-id="b354a-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="b354a-286">您需要调查安全链接策略，了解为什么用户[Safe Links policies](set-up-atp-safe-links-policies.md)被允许替代安全链接结合，并继续转接恶意网站。</span><span class="sxs-lookup"><span data-stu-id="b354a-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="b354a-287">**PendingDetonationPage**：ATP 安全附件正在在虚拟计算机环境中打开有效负载 URL 并查看发生了什么。</span><span class="sxs-lookup"><span data-stu-id="b354a-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="b354a-288">**PendingDetonationPageOverride：** 允许收件人覆盖有效负载表示法并打开该 URL，而不等待结果。</span><span class="sxs-lookup"><span data-stu-id="b354a-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="b354a-289">选项卡</span><span class="sxs-lookup"><span data-stu-id="b354a-289">Tabs</span></span>

<span data-ttu-id="b354a-290">"活动详细信息"视图中的选项卡让你可以进一步调查活动。</span><span class="sxs-lookup"><span data-stu-id="b354a-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="b354a-291">选项卡上显示的信息由时间线中的底纹日期范围控制，如 ["活动信息"部分](#campaign-information) 所述。</span><span class="sxs-lookup"><span data-stu-id="b354a-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="b354a-292">**URL 单击**：如果用户未单击网络钓鱼邮件中的有效负载 URL，则此部分将为空。</span><span class="sxs-lookup"><span data-stu-id="b354a-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="b354a-293">如果用户可以单击 URL，将填充以下值：</span><span class="sxs-lookup"><span data-stu-id="b354a-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="b354a-294">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="b354a-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="b354a-296">**单击时间**</span><span class="sxs-lookup"><span data-stu-id="b354a-296">**Click time**</span></span>
  - <span data-ttu-id="b354a-297">**单击顶点**</span><span class="sxs-lookup"><span data-stu-id="b354a-297">**Click verdict**</span></span>

- <span data-ttu-id="b354a-298">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="b354a-298">**Sender IPs**</span></span>

  - <span data-ttu-id="b354a-299">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="b354a-300">**总计数**</span><span class="sxs-lookup"><span data-stu-id="b354a-300">**Total count**</span></span>
  - <span data-ttu-id="b354a-301">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="b354a-301">**Inboxed**</span></span>
  - <span data-ttu-id="b354a-302">**未收件箱**</span><span class="sxs-lookup"><span data-stu-id="b354a-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="b354a-303">**SPF 已**通过：发件人由发件人[策略框架进行身份验证， (SPF) 。 ](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="b354a-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="b354a-304">未通过 SPF 验证的发件人未经过身份验证，或邮件是合法发件人。</span><span class="sxs-lookup"><span data-stu-id="b354a-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="b354a-305">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b354a-305">**Senders**</span></span>

  - <span data-ttu-id="b354a-306">**发件人**：此地址是 SMTP MAIL FROM 命令中的实际发件人地址，该地址不一定是用户在其电子邮件客户端中看到的"发件人："电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b354a-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="b354a-307">**总计数**</span><span class="sxs-lookup"><span data-stu-id="b354a-307">**Total count**</span></span>
  - <span data-ttu-id="b354a-308">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="b354a-308">**Inboxed**</span></span>
  - <span data-ttu-id="b354a-309">**未收件箱**</span><span class="sxs-lookup"><span data-stu-id="b354a-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="b354a-310">**已通过 DKIM：** 发件人由域[密钥在 DKIM 邮件 (验证) 。 ](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b354a-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="b354a-311">未通过 DKIM 验证的发件人表明该发件人未经过身份验证，或邮件是合法发件人。</span><span class="sxs-lookup"><span data-stu-id="b354a-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="b354a-312">**DMARC 通过**：发件人由基于域的邮件[身份验证、报告和一致性 (DMARC 身份验证) 。 ](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="b354a-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="b354a-313">未通过 DMARC 验证的发件人表明该发件人未经过身份验证，或邮件是合法发件人。</span><span class="sxs-lookup"><span data-stu-id="b354a-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="b354a-314">**附件**</span><span class="sxs-lookup"><span data-stu-id="b354a-314">**Attachments**</span></span>

  - <span data-ttu-id="b354a-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="b354a-315">**Filename**</span></span>
  - <span data-ttu-id="b354a-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="b354a-316">**SHA256**</span></span>
  - <span data-ttu-id="b354a-317">**恶意软件系列**</span><span class="sxs-lookup"><span data-stu-id="b354a-317">**Malware family**</span></span>
  - <span data-ttu-id="b354a-318">**总计数**</span><span class="sxs-lookup"><span data-stu-id="b354a-318">**Total count**</span></span>

- <span data-ttu-id="b354a-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="b354a-319">**URL**</span></span>

  - <span data-ttu-id="b354a-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b354a-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="b354a-321">**总计数**</span><span class="sxs-lookup"><span data-stu-id="b354a-321">**Total Count**</span></span>

<span data-ttu-id="b354a-322"><sup>\*</sup> 单击此值将打开一个新浮出控件，其中包含有关“活动详细信息”视图顶部的指定项（用户、URL 等）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b354a-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="b354a-323">若要返回到“活动详细信息”视图，请单击新浮出控件中的“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="b354a-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="b354a-324">按钮</span><span class="sxs-lookup"><span data-stu-id="b354a-324">Buttons</span></span>

<span data-ttu-id="b354a-325">通过“活动详细信息”视图中的按钮，可使用威胁资源管理器的强大功能进一步调查活动。</span><span class="sxs-lookup"><span data-stu-id="b354a-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="b354a-326">**探索活动**：打开新的威胁资源管理器搜索选项卡，将**活动 ID** 值用作搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="b354a-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="b354a-327">**浏览收件箱的邮件：** 使用"活动 ID 和传递"位置打开新的 **威** 胁 **资源管理器搜索选项卡：收件箱** 作为搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="b354a-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
