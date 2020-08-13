---
title: ATP 中的市场活动视图
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 了解 Office 365 高级威胁防护中的 Campaigns Views。
ms.openlocfilehash: b7078188d8e01f27e6941c3f61f4ef20a004606c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653229"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="f6e9f-103">ATP 中的市场活动视图</span><span class="sxs-lookup"><span data-stu-id="f6e9f-103">Campaign Views in ATP</span></span>

<span data-ttu-id="f6e9f-104">"市场活动视图" 是高级威胁防护 (ATP) 在安全 & 合规性中心中的一项功能，用于识别和分类服务中的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="f6e9f-105">Campaign Views 可以帮助你：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="f6e9f-106">高效调查和应对钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="f6e9f-107">更好地了解攻击范围。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="f6e9f-108">向决策者展示价值。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-108">Show value to decision makers.</span></span>

<span data-ttu-id="f6e9f-109">借助 Campaign Views，可以让你比任何人都更快获得有关攻击的更全面概览。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="f6e9f-110">什么是活动 (campaign)？</span><span class="sxs-lookup"><span data-stu-id="f6e9f-110">What is a campaign?</span></span>

<span data-ttu-id="f6e9f-111">活动是针对一个或多个组织的协同式电子邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="f6e9f-112">窃取凭据和公司数据的电子邮件攻击是一个大型且 lucrative 的行业。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="f6e9f-113">随着技术的提高而停止攻击的努力，攻击者将修改其方法以确保持续的成功。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="f6e9f-114">Microsoft 利用整个服务中大量的防网络钓鱼、反垃圾邮件和反恶意软件数据来帮助确定市场活动。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="f6e9f-115">我们根据几个因素对攻击信息进行分析和分类。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="f6e9f-116">例如：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-116">For example:</span></span>

- <span data-ttu-id="f6e9f-117">**攻击源**：源 IP 地址和发件人电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="f6e9f-118">**攻击邮件属性**：邮件的内容、样式和音调。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="f6e9f-119">**攻击收件人**：收件人域名、收件人工作职能（管理员、高管等）、公司类型（大型、小型、公共、私有等）和行业。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="f6e9f-120">**攻击负载**：邮件中的恶意链接、附件或其他有效负载。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="f6e9f-121">市场活动可能较短，或者可能跨多天、几周或月，且具有有效和非活动时段。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="f6e9f-122">可能会针对你的特定组织发起市场活动，或你的组织可能是跨多个公司的更大市场活动的一部分。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="f6e9f-123">市场活动视图安全 & 合规性中心</span><span class="sxs-lookup"><span data-stu-id="f6e9f-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="f6e9f-124">"活动" 视图在**威胁管理**市场活动的[安全性 & 合规性中心](https://protection.office.com)中 \> **Campaigns**，或直接在中提供 <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![安全和合规中心中的活动概述](../../media/campaigns-overview.png)

<span data-ttu-id="f6e9f-126">您还可以从以下来源获取市场活动视图：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="f6e9f-127">**威胁管理** \>**浏览器** \>**视图** \>**市场活动**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="f6e9f-128">**威胁管理** \>**浏览器** \>**视图** \>**所有电子邮件** \>"**市场活动**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f6e9f-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="f6e9f-129">**威胁管理** \>**浏览器** \>**视图** \>**网络钓鱼** \>"**市场活动**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f6e9f-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="f6e9f-130">**威胁管理** \>**浏览器** \>**视图** \>**恶意软件** \>"**市场活动**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f6e9f-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="f6e9f-131">若要访问市场活动视图，您需要是 Security & 合规性中心中的 "**组织管理**"、"**安全管理员**" 或 "**安全读者**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="f6e9f-132">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="f6e9f-133">市场活动概述</span><span class="sxs-lookup"><span data-stu-id="f6e9f-133">Campaigns overview</span></span>

<span data-ttu-id="f6e9f-134">"概述" 页显示有关所有市场活动的信息。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="f6e9f-135">在 "默认**市场活动**" 选项卡上，"**市场活动类型**" 区域显示一个条形图，显示每日的收件人数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="f6e9f-136">默认情况下，该图显示**网络钓鱼**和**恶意软件**数据。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="f6e9f-137">如果看不到任何市场活动数据，请尝试更改日期范围或[筛选器](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="f6e9f-138">"概述" 页的其余部分将在 "**市场活动**" 选项卡上显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="f6e9f-139">**名称**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-139">**Name**</span></span>

- <span data-ttu-id="f6e9f-140">**示例主题**：活动中某封邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="f6e9f-141">请注意，市场活动中的所有邮件都不一定具有相同的主题。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="f6e9f-142">**目标**：计算的百分比： (组织中的市场活动收件人数) / (服务) 中所有组织的活动收件人总数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="f6e9f-143">此值指示市场活动在组织中的具体目标程度 (较高值) 与在服务中的其他组织联系 () 较低值的值。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="f6e9f-144">**类型**：此值可以是**网络钓鱼**或**恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="f6e9f-145">**子类型**：此值包含有关市场活动的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="f6e9f-146">例如：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-146">For example:</span></span>

  - <span data-ttu-id="f6e9f-147">**网络钓鱼**：其中提供了此市场活动 phished 的品牌。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="f6e9f-148">例如、、、、 `Microsoft` `365` `Unknown` `Outlook` 或 `DocuSign` 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="f6e9f-149">**恶意软件**：例如 `HTML/PHISH` 或 `HTML/<MalwareFamilyName>` 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="f6e9f-150">如果可用，为此市场活动 phished 的品牌。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="f6e9f-151">当通过 ATP 技术驱动检测时，会将前缀**ATP**添加到子类型值中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="f6e9f-152">**收件人**：此活动所面向的用户数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="f6e9f-153">**Inboxed**：从其收件箱中的此市场活动中接收邮件的用户数 (不会传递到其 "垃圾邮件" 文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="f6e9f-154">**单击**：在此 URL 上单击或在网络钓鱼邮件中打开附件的用户数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="f6e9f-155">**单击 "速率**：由 '**单击**  /  **Inboxed**' 计算的百分比。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="f6e9f-156">此值是市场活动的有效性的指标，以及收件人是否能够将邮件标识为网络钓鱼并避免在有效负载 URL 上单击。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="f6e9f-157">请注意，此值不在恶意软件的市场活动中使用。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="f6e9f-158">已**访问**：有多少用户实际将其通过到有效负载网站。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="f6e9f-159">如果有**单击**的值，但安全链接阻止了对网站的访问，则此值将为零。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="f6e9f-160">"**市场活动来源**" 选项卡显示世界地图上的邮件源。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="f6e9f-161">筛选器和设置</span><span class="sxs-lookup"><span data-stu-id="f6e9f-161">Filters and settings</span></span>

<span data-ttu-id="f6e9f-162">在 "市场活动视图" 页的顶部，有几个筛选器和查询设置可帮助您查找和隔离特定的市场活动。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![市场活动筛选器](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="f6e9f-164">您可以执行的最基本筛选是开始日期/时间和结束日期/时间。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="f6e9f-165">若要进一步筛选视图，可以通过单击 "**市场活动类型**" 按钮，进行选择，然后单击 "**刷新**" 来执行 "多值筛选" 的 "单个" 属性。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="f6e9f-166">以下列表介绍了可用的市场活动属性：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="f6e9f-167">基本</span><span class="sxs-lookup"><span data-stu-id="f6e9f-167">Basic</span></span>

  - <span data-ttu-id="f6e9f-168">**市场活动类型**：选择**恶意软件**或**网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="f6e9f-169">清除所选内容与同时选择这两个选项的结果相同。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="f6e9f-170">**市场活动名称**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-170">**Campaign name**</span></span>
  - <span data-ttu-id="f6e9f-171">**市场活动子类型**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="f6e9f-172">**发件人**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-172">**Sender**</span></span>
  - <span data-ttu-id="f6e9f-173">**Recipients**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-173">**Recipients**</span></span>
  - <span data-ttu-id="f6e9f-174">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-174">**Sender domain**</span></span>
  - <span data-ttu-id="f6e9f-175">**主题**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-175">**Subject**</span></span>
  - <span data-ttu-id="f6e9f-176">**附件的文件名**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-176">**Attachment filename**</span></span>
  - <span data-ttu-id="f6e9f-177">**恶意软件系列**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-177">**Malware family**</span></span>
  - <span data-ttu-id="f6e9f-178">**传递操作**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-178">**Delivery action**</span></span>
  - <span data-ttu-id="f6e9f-179">**检测技术**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-179">**Detection technology**</span></span>
  - <span data-ttu-id="f6e9f-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-180">**Tags**</span></span>
  - <span data-ttu-id="f6e9f-181">**系统覆盖**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-181">**System overrides**</span></span>

- <span data-ttu-id="f6e9f-182">高级</span><span class="sxs-lookup"><span data-stu-id="f6e9f-182">Advanced</span></span>

  - <span data-ttu-id="f6e9f-183">**Internet 邮件 id**：邮件标头中的**邮件 id**标头字段中可用。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="f6e9f-184"> (的示例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 记下尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="f6e9f-185">**网络邮件 ID**：邮件头中的 X------------**邮件 id**标头字段中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="f6e9f-186">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="f6e9f-187">**附件 SHA256**：若要在 Windows 中查找文件的 SHA256 哈希值，请在命令提示符下运行以下命令： `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="f6e9f-188">**群集 ID**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="f6e9f-189">**通知策略 ID**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="f6e9f-190">URL</span><span class="sxs-lookup"><span data-stu-id="f6e9f-190">URLs</span></span>

  - <span data-ttu-id="f6e9f-191">**URL 域**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-191">**URL domain**</span></span>
  - <span data-ttu-id="f6e9f-192">**URL 域和路径**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-192">**URL domain and path**</span></span>
  - <span data-ttu-id="f6e9f-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-193">**URL**</span></span>
  - <span data-ttu-id="f6e9f-194">**URL 路径**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-194">**URL path**</span></span>
  - <span data-ttu-id="f6e9f-195">**单击 "判定"**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-195">**Click verdict**</span></span>

<span data-ttu-id="f6e9f-196">若要进行更高级的筛选（包括按多个属性筛选），可以单击 "**高级筛选**" 按钮生成查询。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="f6e9f-197">可以使用相同的市场活动属性，但具有以下增强功能：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="f6e9f-198">您可以单击 "**添加条件**" 来选择多个条件。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="f6e9f-199">可以在条件之间选择**and**或**or**运算符。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="f6e9f-200">您可以在 "条件" 列表底部选择 "**条件组**" 项目以形成复杂的复合条件。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="f6e9f-201">完成后，请单击 "**查询**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="f6e9f-202">在创建基本或高级筛选器之后，可以使用 "**保存查询**" 或 "**将查询另存为**" 来保存它。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="f6e9f-203">稍后，当您返回到市场活动视图时，您可以通过单击 "**已保存的查询设置**" 加载已保存的筛选器。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="f6e9f-204">若要导出关系图或市场活动列表，请单击 "**导出**"，然后选择 "**导出图表数据**" 或 "**导出市场活动列表**"。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="f6e9f-205">如果你拥有 Microsoft Defender ATP 订阅，可以单击 " **WDATP** " 以使用 MICROSOFT Defender atp 连接或断开市场活动信息。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="f6e9f-206">有关详细信息，请参阅将[Office 365 ATP 与 Microsoft DEFENDER ATP 集成](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="f6e9f-207">活动详细信息</span><span class="sxs-lookup"><span data-stu-id="f6e9f-207">Campaign details</span></span>

<span data-ttu-id="f6e9f-208">当您单击市场活动的名称时，市场活动详细信息将显示在浮出控件中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="f6e9f-209">市场活动信息</span><span class="sxs-lookup"><span data-stu-id="f6e9f-209">Campaign information</span></span>

<span data-ttu-id="f6e9f-210">在 "市场活动详细信息" 视图的顶部，可获取以下市场活动信息：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="f6e9f-211">**ID**：唯一的市场活动标识符。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="f6e9f-212">**已开始**和**结束**：市场活动的开始日期和结束日期。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="f6e9f-213">请注意，这些日期可能会比您在 "概述" 页上选择的筛选器日期进一步扩展。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="f6e9f-214">**影响**：此部分包含 (您在时间轴) 选择的日期范围筛选器的以下数据：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="f6e9f-215">总收件人数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-215">The total number of recipients.</span></span>
  - <span data-ttu-id="f6e9f-216">传递到收件箱，而不是传递到 "垃圾邮件" 文件夹) 的 "Inboxed" (的邮件数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="f6e9f-217">在网络钓鱼邮件中单击 URL 有效负载的用户数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="f6e9f-218">Howe 许多用户访问了该 URL。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="f6e9f-219">**目标**：计算的百分比： (组织中的市场活动收件人数) / (服务) 中所有组织的活动收件人总数。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="f6e9f-220">请注意，此值是在市场活动的整个生命周期中计算的，不会更改筛选器日期。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="f6e9f-221">市场活动活动的交互式日程表：时间线显示活动在整个市场活动生命周期中的活动。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="f6e9f-222">默认情况下，阴影区域包括您在概述中选择的日期范围筛选器。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="f6e9f-223">您可以单击并拖动以选择特定的起点和终点，<u>这将更改 "**影响**" 区域中显示的数据，以及下一节中所述的页面的其余</u>部分。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="f6e9f-224">在标题栏中，可以单击 "**下载市场活动上移**" 按钮 ![ 下载市场活动写图标 ](../../media/download-campaign-write-up-button.png) ，以将市场活动详细信息下载到 Word 文档中 (默认情况下，名为 CampaignReport.docx) 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="f6e9f-225">请注意，此文档包含有关市场活动的整个生命周期的详细信息 (并不仅仅是所选的筛选日期) 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![市场活动信息](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="f6e9f-227">活动流</span><span class="sxs-lookup"><span data-stu-id="f6e9f-227">Campaign flow</span></span>

<span data-ttu-id="f6e9f-228">在 "市场活动详细信息" 视图的中间，有关市场活动的重要详细信息显示在水平流图中的 "**流**" 部分中， (称为 " _Sankey_图) "。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="f6e9f-229">这些详细信息将帮助你了解活动的元素和组织中的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="f6e9f-230">**流程图**中显示的信息由时间轴中的阴影日期范围控制，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![不包含用户 URL 单击次数的活动详细信息](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="f6e9f-232">如果将鼠标悬停在图表中的水平带区上，则将看到相关邮件的数目（例如来自特定来源 IP 的邮件，使用指定发件人域名的来自来源 IP 的邮件等）。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="f6e9f-233">此图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="f6e9f-234">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-234">**Sender IPs**</span></span>

- <span data-ttu-id="f6e9f-235">**发件人域名**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-235">**Sender domains**</span></span>

- <span data-ttu-id="f6e9f-236">**筛选 verdicts**：这些值与 "可用的网络钓鱼" 和 "垃圾邮件" 筛选 verdicts （如[反垃圾邮件邮件头](anti-spam-message-headers.md)中所述）相关。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="f6e9f-237">下表描述了可用的值：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="f6e9f-238">值</span><span class="sxs-lookup"><span data-stu-id="f6e9f-238">Value</span></span>|<span data-ttu-id="f6e9f-239">垃圾邮件筛选器判定</span><span class="sxs-lookup"><span data-stu-id="f6e9f-239">Spam filter verdict</span></span>|<span data-ttu-id="f6e9f-240">说明</span><span class="sxs-lookup"><span data-stu-id="f6e9f-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="f6e9f-241">**允许**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="f6e9f-242">邮件在通过垃圾邮件筛选进行评估之前，邮件被标记为非垃圾邮件和/或跳过的筛选 (例如，通过邮件流规则（也称为传输规则) ）。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="f6e9f-243">邮件因其他原因而跳过垃圾邮件筛选 (例如，发件人和收件人似乎位于同一个组织) 中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="f6e9f-244">**阻止**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="f6e9f-245">邮件在通过垃圾邮件筛选进行评估之前将邮件标记为垃圾邮件 (例如，通过邮件流规则) 。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="f6e9f-246">**已检测**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="f6e9f-247">邮件被垃圾邮件筛选标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="f6e9f-248">**未检测到**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="f6e9f-249">垃圾邮件筛选器将邮件标记为 "非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="f6e9f-250">**以后**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="f6e9f-251">邮件跳过垃圾邮件筛选，因为它已从隔离区中释放。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="f6e9f-252">**租户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="f6e9f-253">邮件因反垃圾邮件策略设置而跳过垃圾邮件筛选 (例如，发件人位于 "允许的发件人" 列表或 "允许的域" 列表) 中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="f6e9f-254">**租户块**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="f6e9f-255">由于反垃圾邮件策略设置 (的垃圾邮件筛选阻止了邮件，例如，发件人位于 "允许的发件人" 列表或 "允许的域" 列表) 中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="f6e9f-256">**用户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="f6e9f-257">邮件跳过垃圾邮件筛选，因为发件人位于 Outlook 的用户安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="f6e9f-258">**用户块**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="f6e9f-259">邮件被垃圾邮件筛选阻止，因为发件人位于 Outlook 中的用户阻止的发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="f6e9f-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-260">**ZAP**</span></span>|<span data-ttu-id="f6e9f-261">不适用</span><span class="sxs-lookup"><span data-stu-id="f6e9f-261">n/a</span></span>|<span data-ttu-id="f6e9f-262">[零小时自动清除 (ZAP) ](zero-hour-auto-purge.md)根据您的反垃圾邮件策略设置（ (移动到 "垃圾邮件" 文件夹或隔离的) ）对所发送的邮件采取操作。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="f6e9f-263"><sup>\*</sup>检查您的反垃圾邮件策略，因为服务可能阻止了允许的邮件。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="f6e9f-264"><sup>\*\*</sup>检查反垃圾邮件策略，因为应隔离但不传递这些邮件。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="f6e9f-265">**送达位置**：你希望调查发送到收件人的邮件（发送到收件箱或垃圾邮件文件夹），即使用户未单击邮件中的有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="f6e9f-266">您还可以从隔离区中删除隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="f6e9f-267">有关详细信息，请参阅[EOP 中隔离的电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="f6e9f-268">**已删除文件夹**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-268">**Deleted folder**</span></span>
  - <span data-ttu-id="f6e9f-269">**已**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-269">**Dropped**</span></span>
  - <span data-ttu-id="f6e9f-270">**外部**：收件人位于混合环境的本地电子邮件组织中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="f6e9f-271">**失败**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-271">**Failed**</span></span>
  - <span data-ttu-id="f6e9f-272">**哪个**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-272">**Forwarded**</span></span>
  - <span data-ttu-id="f6e9f-273">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-273">**Inbox**</span></span>
  - <span data-ttu-id="f6e9f-274">**垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-274">**Junk folder**</span></span>
  - <span data-ttu-id="f6e9f-275">**隔离**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-275">**Quarantine**</span></span>
  - <span data-ttu-id="f6e9f-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-276">**Unknown**</span></span>

- <span data-ttu-id="f6e9f-277">**URL 单击**：在下一节中对这些内容进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="f6e9f-278">在包含10个以上项目的所有层中，将显示前10个项目，而其余的项目捆绑在**一起。**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="f6e9f-279">URL 单击次数</span><span class="sxs-lookup"><span data-stu-id="f6e9f-279">URL clicks</span></span>

<span data-ttu-id="f6e9f-280">将仿冒邮件传递到收件箱或垃圾邮件) 文件夹中的收件人 (时，总会有用户单击有效负载 URL 的机会。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="f6e9f-281">如果不单击已传递邮件中的 URL，则会使其成功，但您需要确定在第一个位置将仿冒邮件传递到其邮箱的原因。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="f6e9f-282">如果用户单击了仿冒邮件中的有效负载 URL，则操作将显示在 "市场活动详细信息" 视图中关系图的 " **URL 单击**" 区域中。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="f6e9f-283">**允许**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-283">**Allowed**</span></span>

- <span data-ttu-id="f6e9f-284">**BlockPage**：收件人单击了有效负载 URL，但组织中的[ATP 安全链接](atp-safe-links.md)策略阻止了其对恶意网站的访问。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="f6e9f-285">**BlockPageOverride**：收件人单击了邮件中的有效负载 URL 后，ATP 安全链接尝试停止它们，但允许它们替代该块。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="f6e9f-286">您需要调查[安全链接策略](set-up-atp-safe-links-policies.md)，以了解为什么允许用户覆盖安全链接判定并继续进入恶意网站。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="f6e9f-287">**PendingDetonationPage**： ATP 安全附件在虚拟计算机环境中打开有效负载 URL 的过程，并查看发生的情况。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="f6e9f-288">**PendingDetonationPageOverride**：允许收件人重写有效负载沙箱进程并打开 URL，而不等待结果。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="f6e9f-289">选项卡</span><span class="sxs-lookup"><span data-stu-id="f6e9f-289">Tabs</span></span>

<span data-ttu-id="f6e9f-290">利用 "市场活动详细信息" 视图中的选项卡，可以进一步调查市场活动。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="f6e9f-291">选项卡上显示的信息由时间轴中的着色日期范围控制，如 "[市场活动信息](#campaign-information)" 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="f6e9f-292">**URL 单击**：如果用户未单击仿冒邮件中的有效负载 URL，则此部分将为空。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="f6e9f-293">如果用户能够单击该 URL，则将填充以下值：</span><span class="sxs-lookup"><span data-stu-id="f6e9f-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="f6e9f-294">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="f6e9f-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="f6e9f-296">**单击 "时间"**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-296">**Click time**</span></span>
  - <span data-ttu-id="f6e9f-297">**单击 "判定"**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-297">**Click verdict**</span></span>

- <span data-ttu-id="f6e9f-298">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-298">**Sender IPs**</span></span>

  - <span data-ttu-id="f6e9f-299">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="f6e9f-300">**总计数**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-300">**Total count**</span></span>
  - <span data-ttu-id="f6e9f-301">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-301">**Inboxed**</span></span>
  - <span data-ttu-id="f6e9f-302">**不 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="f6e9f-303">已**通过 spf**：发件人已由[发件人策略框架 (SPF) ](how-office-365-uses-spf-to-prevent-spoofing.md)进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="f6e9f-304">未通过 SPF 验证的发件人表示发件人未经过身份验证，或者邮件正在哄骗合法发件人。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="f6e9f-305">**发件人**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-305">**Senders**</span></span>

  - <span data-ttu-id="f6e9f-306">**发件人**：这是 SMTP MAIL from 命令中的实际发件人地址，而不一定是用户在其电子邮件客户端中看到的 "发件人：" 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="f6e9f-307">**总计数**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-307">**Total count**</span></span>
  - <span data-ttu-id="f6e9f-308">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-308">**Inboxed**</span></span>
  - <span data-ttu-id="f6e9f-309">**不 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="f6e9f-310">已**通过 DKIM**：发件人由[识别为邮件 (DKIM) 的域密钥](support-for-validation-of-dkim-signed-messages.md)进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="f6e9f-311">未通过 DKIM 验证的发件人表示发件人未经过身份验证，或者邮件正在哄骗合法的发件人。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="f6e9f-312">已**通过 DMARC**：发件人通过[基于域的邮件身份验证、报告和一致性 (DMARC) ](use-dmarc-to-validate-email.md)进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="f6e9f-313">未通过 DMARC 验证的发件人表示发件人未经过身份验证，或者邮件正在哄骗合法的发件人。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="f6e9f-314">**附件**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-314">**Attachments**</span></span>

  - <span data-ttu-id="f6e9f-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-315">**Filename**</span></span>
  - <span data-ttu-id="f6e9f-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-316">**SHA256**</span></span>
  - <span data-ttu-id="f6e9f-317">**恶意软件系列**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-317">**Malware family**</span></span>
  - <span data-ttu-id="f6e9f-318">**总计数**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-318">**Total count**</span></span>

- <span data-ttu-id="f6e9f-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-319">**URL**</span></span>

  - <span data-ttu-id="f6e9f-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f6e9f-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="f6e9f-321">**总计数**</span><span class="sxs-lookup"><span data-stu-id="f6e9f-321">**Total Count**</span></span>

<span data-ttu-id="f6e9f-322"><sup>\*</sup> 单击此值将打开一个新浮出控件，其中包含有关“活动详细信息”视图顶部的指定项（用户、URL 等）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="f6e9f-323">若要返回到“活动详细信息”视图，请单击新浮出控件中的“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="f6e9f-324">按钮</span><span class="sxs-lookup"><span data-stu-id="f6e9f-324">Buttons</span></span>

<span data-ttu-id="f6e9f-325">通过“活动详细信息”视图中的按钮，可使用威胁资源管理器的强大功能进一步调查活动。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="f6e9f-326">**探索活动**：打开新的威胁资源管理器搜索选项卡，将**活动 ID** 值用作搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="f6e9f-327">**浏览 Inboxed 消息**：使用**市场活动 ID**和送达位置打开新的威胁资源管理器搜索选项卡 **： "收件箱**" 作为搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="f6e9f-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
