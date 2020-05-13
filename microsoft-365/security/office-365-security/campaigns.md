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
ms.openlocfilehash: 5441c877dac70330bf1e5653983494be5b1b3293
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209591"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="44a1e-103">ATP 中的市场活动视图</span><span class="sxs-lookup"><span data-stu-id="44a1e-103">Campaign Views in ATP</span></span>

<span data-ttu-id="44a1e-104">活动视图是安全 & 合规性中心中的高级威胁防护（ATP）中的一项功能，用于识别和分类服务中的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="44a1e-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="44a1e-105">Campaign Views 可以帮助你：</span><span class="sxs-lookup"><span data-stu-id="44a1e-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="44a1e-106">高效调查和应对钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="44a1e-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="44a1e-107">更好地了解攻击范围。</span><span class="sxs-lookup"><span data-stu-id="44a1e-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="44a1e-108">向决策者展示价值。</span><span class="sxs-lookup"><span data-stu-id="44a1e-108">Show value to decision makers.</span></span>

<span data-ttu-id="44a1e-109">借助 Campaign Views，可以让你比任何人都更快获得有关攻击的更全面概览。</span><span class="sxs-lookup"><span data-stu-id="44a1e-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="44a1e-110">什么是活动 (campaign)？</span><span class="sxs-lookup"><span data-stu-id="44a1e-110">What is a campaign?</span></span>

<span data-ttu-id="44a1e-111">活动是针对一个或多个组织的协同式电子邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="44a1e-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="44a1e-112">窃取凭据和公司数据的电子邮件攻击是一个大型且 lucrative 的行业。</span><span class="sxs-lookup"><span data-stu-id="44a1e-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="44a1e-113">随着技术的提高而停止攻击的努力，攻击者将修改其方法以确保持续的成功。</span><span class="sxs-lookup"><span data-stu-id="44a1e-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="44a1e-114">Microsoft 利用整个服务中大量的防网络钓鱼、反垃圾邮件和反恶意软件数据来帮助确定市场活动。</span><span class="sxs-lookup"><span data-stu-id="44a1e-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="44a1e-115">我们根据几个因素对攻击信息进行分析和分类。</span><span class="sxs-lookup"><span data-stu-id="44a1e-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="44a1e-116">例如：</span><span class="sxs-lookup"><span data-stu-id="44a1e-116">For example:</span></span>

- <span data-ttu-id="44a1e-117">**攻击来源**：源 IP 地址和发件人电子邮件域名。</span><span class="sxs-lookup"><span data-stu-id="44a1e-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="44a1e-118">**攻击邮件属性**：攻击邮件的内容、样式和语气。</span><span class="sxs-lookup"><span data-stu-id="44a1e-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="44a1e-119">**攻击收件人**：收件人域名、收件人工作职能（管理员、高管等）、公司类型（大型、小型、公共、私有等）和行业。</span><span class="sxs-lookup"><span data-stu-id="44a1e-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="44a1e-120">**攻击负载**：攻击邮件中的恶意链接、附件或其他负载。</span><span class="sxs-lookup"><span data-stu-id="44a1e-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="44a1e-121">市场活动可能较短，或者可能跨多天、几周或月，且具有有效和非活动时段。</span><span class="sxs-lookup"><span data-stu-id="44a1e-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="44a1e-122">可能会针对你的特定组织发起市场活动，或你的组织可能是跨多个公司的更大市场活动的一部分。</span><span class="sxs-lookup"><span data-stu-id="44a1e-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="44a1e-123">市场活动视图安全 & 合规性中心</span><span class="sxs-lookup"><span data-stu-id="44a1e-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="44a1e-124">"活动" 视图在**威胁管理**市场活动的[安全性 & 合规性中心](https://protection.office.com)中提供 \> **Campaigns**。</span><span class="sxs-lookup"><span data-stu-id="44a1e-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![安全和合规中心中的活动概述](../../media/campaigns-overview.png)

<span data-ttu-id="44a1e-126">您还可以从以下来源获取市场活动视图：</span><span class="sxs-lookup"><span data-stu-id="44a1e-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="44a1e-127">**威胁管理** \>**浏览器** \>**视图** \>**市场活动**</span><span class="sxs-lookup"><span data-stu-id="44a1e-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="44a1e-128">**威胁管理** \>**浏览器** \>**视图** \>**所有电子邮件** \>**活动**</span><span class="sxs-lookup"><span data-stu-id="44a1e-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="44a1e-129">如果看不到任何活动数据，请尝试更改日期范围。</span><span class="sxs-lookup"><span data-stu-id="44a1e-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="44a1e-130">“概述”页面显示有关该活动的以下信息：</span><span class="sxs-lookup"><span data-stu-id="44a1e-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="44a1e-131">**名称**</span><span class="sxs-lookup"><span data-stu-id="44a1e-131">**Name**</span></span>

- <span data-ttu-id="44a1e-132">**示例主题**：活动中某封邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="44a1e-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="44a1e-133">请注意，市场活动中的所有邮件都不一定具有相同的主题。</span><span class="sxs-lookup"><span data-stu-id="44a1e-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="44a1e-134">**类型**：当前，此值始终是**网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="44a1e-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="44a1e-135">**子类型**：此活动中作为钓鱼对象的品牌。</span><span class="sxs-lookup"><span data-stu-id="44a1e-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="44a1e-136">当通过 ATP 技术驱动检测时，会将前缀**ATP**添加到子类型值中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="44a1e-137">**收件人**：此活动所面向的用户数。</span><span class="sxs-lookup"><span data-stu-id="44a1e-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="44a1e-138">**Inboxed**：在其收件箱中接收来自此市场活动的邮件的用户数（未传递给垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="44a1e-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="44a1e-139">**单击**：在网络钓鱼邮件中单击 URL 的用户数。</span><span class="sxs-lookup"><span data-stu-id="44a1e-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="44a1e-140">**单击 "速率**：由 '**单击**  /  **Inboxed**' 计算的百分比。</span><span class="sxs-lookup"><span data-stu-id="44a1e-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="44a1e-141">此值是市场活动的有效性的指标，以及收件人是否能够将邮件标识为网络钓鱼并避免在有效负载 URL 上单击。</span><span class="sxs-lookup"><span data-stu-id="44a1e-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="44a1e-142">已**访问**：有多少用户实际将其通过到有效负载网站。</span><span class="sxs-lookup"><span data-stu-id="44a1e-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="44a1e-143">如果有**单击**的值，但安全链接阻止了对网站的访问，则此值将为零。</span><span class="sxs-lookup"><span data-stu-id="44a1e-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="44a1e-144">单击活动的名称时，活动详细信息将显示在浮出控件中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="44a1e-145">活动详细信息</span><span class="sxs-lookup"><span data-stu-id="44a1e-145">Campaign details</span></span>

<span data-ttu-id="44a1e-146">“活动详细信息”视图中提供了有关活动的大量信息：</span><span class="sxs-lookup"><span data-stu-id="44a1e-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="44a1e-147">活动信息：</span><span class="sxs-lookup"><span data-stu-id="44a1e-147">Campaign information:</span></span>

  - <span data-ttu-id="44a1e-148">**ID**：唯一的市场活动标识符。</span><span class="sxs-lookup"><span data-stu-id="44a1e-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="44a1e-149">**开始时间**和**结束时间**：你选择的日期范围筛选器。</span><span class="sxs-lookup"><span data-stu-id="44a1e-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="44a1e-150">**影响**：您选择的日期范围筛选器的以下数据：</span><span class="sxs-lookup"><span data-stu-id="44a1e-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="44a1e-151">总收件人数。</span><span class="sxs-lookup"><span data-stu-id="44a1e-151">The total number of recipients.</span></span>

    - <span data-ttu-id="44a1e-152">"Inboxed" （即传递到 "收件箱"，而不是 "垃圾邮件"）的邮件数。</span><span class="sxs-lookup"><span data-stu-id="44a1e-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="44a1e-153">在网络钓鱼邮件中单击 URL 有效负载的用户数。</span><span class="sxs-lookup"><span data-stu-id="44a1e-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="44a1e-154">Howe 许多用户访问了该 URL。</span><span class="sxs-lookup"><span data-stu-id="44a1e-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="44a1e-155">活动的时间线：活动的开始时间和结束时间以及随时间推移的邮件数量。</span><span class="sxs-lookup"><span data-stu-id="44a1e-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="44a1e-156">活动流</span><span class="sxs-lookup"><span data-stu-id="44a1e-156">Campaign flow</span></span>

<span data-ttu-id="44a1e-157">关于活动的重要详细信息显示在**流程**部分中的水平流程图表（称为 _Sankey_ 图表）中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="44a1e-158">这些详细信息将帮助你了解活动的元素和组织中的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="44a1e-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![不包含用户 URL 单击次数的活动详细信息](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="44a1e-160">如果将鼠标悬停在图表中的水平带区上，则将看到相关邮件的数目（例如来自特定来源 IP 的邮件，使用指定发件人域名的来自来源 IP 的邮件等）。</span><span class="sxs-lookup"><span data-stu-id="44a1e-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="44a1e-161">此图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="44a1e-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="44a1e-162">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="44a1e-162">**Sender IPs**</span></span>

- <span data-ttu-id="44a1e-163">**发件人域名**</span><span class="sxs-lookup"><span data-stu-id="44a1e-163">**Sender domains**</span></span>

- <span data-ttu-id="44a1e-164">**筛选 verdicts**：此处的值与 "可用的网络钓鱼" 和 "垃圾邮件" 筛选 verdicts （如[反垃圾邮件邮件头](anti-spam-message-headers.md)中所述）相关。</span><span class="sxs-lookup"><span data-stu-id="44a1e-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="44a1e-165">下表描述了可用的值：</span><span class="sxs-lookup"><span data-stu-id="44a1e-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="44a1e-166">值</span><span class="sxs-lookup"><span data-stu-id="44a1e-166">Value</span></span>|<span data-ttu-id="44a1e-167">垃圾邮件筛选器判定</span><span class="sxs-lookup"><span data-stu-id="44a1e-167">Spam filter verdict</span></span>|<span data-ttu-id="44a1e-168">说明</span><span class="sxs-lookup"><span data-stu-id="44a1e-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="44a1e-169">**Allowed**</span><span class="sxs-lookup"><span data-stu-id="44a1e-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="44a1e-170">垃圾邮件筛选（例如，通过邮件流规则（也称为传输规则）进行评估之前，邮件被标记为非垃圾邮件和/或跳过的筛选器。</span><span class="sxs-lookup"><span data-stu-id="44a1e-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="44a1e-171">邮件因其他原因而跳过垃圾邮件筛选（例如，发件人和收件人似乎位于同一组织中）。</span><span class="sxs-lookup"><span data-stu-id="44a1e-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="44a1e-172">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="44a1e-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="44a1e-173">垃圾邮件筛选（例如，通过邮件流规则）评估邮件之前，邮件被标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="44a1e-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="44a1e-174">**已检测**</span><span class="sxs-lookup"><span data-stu-id="44a1e-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="44a1e-175">邮件被垃圾邮件筛选标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="44a1e-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="44a1e-176">**未检测到**</span><span class="sxs-lookup"><span data-stu-id="44a1e-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="44a1e-177">垃圾邮件筛选器将邮件标记为 "非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="44a1e-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="44a1e-178">**以后**</span><span class="sxs-lookup"><span data-stu-id="44a1e-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="44a1e-179">邮件跳过垃圾邮件筛选，因为它已从隔离区中释放。</span><span class="sxs-lookup"><span data-stu-id="44a1e-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="44a1e-180">**租户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="44a1e-181">邮件由于反垃圾邮件策略设置而跳过垃圾邮件筛选（例如，发件人位于 "允许的发件人" 列表或 "允许的域" 列表中）。</span><span class="sxs-lookup"><span data-stu-id="44a1e-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="44a1e-182">**租户块**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="44a1e-183">由于反垃圾邮件策略设置（例如，发件人位于 "允许的发件人列表" 或 "允许的域" 列表中），垃圾邮件筛选阻止了邮件。</span><span class="sxs-lookup"><span data-stu-id="44a1e-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="44a1e-184">**用户允许**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="44a1e-185">邮件跳过垃圾邮件筛选，因为发件人位于 Outlook 的用户安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="44a1e-186">**用户块**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="44a1e-187">邮件被垃圾邮件筛选阻止，因为发件人位于 Outlook 中的用户阻止的发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="44a1e-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="44a1e-188">**ZAP**</span></span>|<span data-ttu-id="44a1e-189">不适用</span><span class="sxs-lookup"><span data-stu-id="44a1e-189">n/a</span></span>|<span data-ttu-id="44a1e-190">[零小时自动清除（ZAP）](zero-hour-auto-purge.md)根据您的反垃圾邮件策略设置（移动到 "垃圾邮件" 文件夹或隔离的）对已发送邮件采取操作。</span><span class="sxs-lookup"><span data-stu-id="44a1e-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="44a1e-191"><sup>\*</sup>检查您的反垃圾邮件策略，因为服务可能阻止了允许的邮件。</span><span class="sxs-lookup"><span data-stu-id="44a1e-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="44a1e-192"><sup>\*\*</sup>检查反垃圾邮件策略，因为应隔离但不传递这些邮件。</span><span class="sxs-lookup"><span data-stu-id="44a1e-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="44a1e-193">**送达位置**：你希望调查发送到收件人的邮件（发送到收件箱或垃圾邮件文件夹），即使用户未单击邮件中的有效负载 URL。</span><span class="sxs-lookup"><span data-stu-id="44a1e-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="44a1e-194">您还可以从隔离区中删除隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="44a1e-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="44a1e-195">有关详细信息，请参阅[EOP 中隔离的电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="44a1e-195">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="44a1e-196">**已删除文件夹**</span><span class="sxs-lookup"><span data-stu-id="44a1e-196">**Deleted folder**</span></span>

  - <span data-ttu-id="44a1e-197">**已**</span><span class="sxs-lookup"><span data-stu-id="44a1e-197">**Dropped**</span></span>

  - <span data-ttu-id="44a1e-198">**外部**：收件人位于你的内部部署电子邮件组织中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="44a1e-199">**失败**</span><span class="sxs-lookup"><span data-stu-id="44a1e-199">**Failed**</span></span>

  - <span data-ttu-id="44a1e-200">**哪个**</span><span class="sxs-lookup"><span data-stu-id="44a1e-200">**Forwarded**</span></span>

  - <span data-ttu-id="44a1e-201">**收件箱**</span><span class="sxs-lookup"><span data-stu-id="44a1e-201">**Inbox**</span></span>

  - <span data-ttu-id="44a1e-202">**垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="44a1e-202">**Junk folder**</span></span>

  - <span data-ttu-id="44a1e-203">**隔离**</span><span class="sxs-lookup"><span data-stu-id="44a1e-203">**Quarantine**</span></span>

  - <span data-ttu-id="44a1e-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="44a1e-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="44a1e-205">在包含10个以上项目的所有层中，将显示前10个项目，而其余的项目捆绑在**一起。**</span><span class="sxs-lookup"><span data-stu-id="44a1e-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="44a1e-206">URL 单击次数</span><span class="sxs-lookup"><span data-stu-id="44a1e-206">URL clicks</span></span>

<span data-ttu-id="44a1e-207">将仿冒邮件传递给收件人（"收件箱" 或 "垃圾邮件" 文件夹）时，总是有用户单击有效负载 URL 的机会。</span><span class="sxs-lookup"><span data-stu-id="44a1e-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="44a1e-208">如果不单击已传递邮件中的 URL，则会使其成功，但您需要确定在第一个位置将仿冒邮件传递到其邮箱的原因。</span><span class="sxs-lookup"><span data-stu-id="44a1e-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="44a1e-209">如果用户单击了仿冒邮件中的有效负载 URL，则操作将显示在 "市场活动详细信息" 视图中关系图的 " **URL 单击**" 区域中。</span><span class="sxs-lookup"><span data-stu-id="44a1e-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="44a1e-210">**Allowed**</span><span class="sxs-lookup"><span data-stu-id="44a1e-210">**Allowed**</span></span>

- <span data-ttu-id="44a1e-211">**BlockPage**：收件人单击了有效负载 URL，但组织中的[ATP 安全链接](atp-safe-links.md)策略阻止了其对恶意网站的访问。</span><span class="sxs-lookup"><span data-stu-id="44a1e-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="44a1e-212">**BlockPageOverride**：收件人单击了邮件中的有效负载 URL 后，ATP 安全链接尝试停止它们，但允许它们替代该块。</span><span class="sxs-lookup"><span data-stu-id="44a1e-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="44a1e-213">您需要调查[安全链接策略](set-up-atp-safe-links-policies.md)，以了解为什么允许用户覆盖安全链接判定并继续进入恶意网站。</span><span class="sxs-lookup"><span data-stu-id="44a1e-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="44a1e-214">**PendingDetonationPage**： ATP 安全附件在虚拟计算机环境中打开有效负载 URL 的过程，并查看发生的情况。</span><span class="sxs-lookup"><span data-stu-id="44a1e-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="44a1e-215">**PendingDetonationPageOverride**：允许收件人重写有效负载沙箱进程并打开 URL，而不等待结果。</span><span class="sxs-lookup"><span data-stu-id="44a1e-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="44a1e-216">选项卡</span><span class="sxs-lookup"><span data-stu-id="44a1e-216">Tabs</span></span>

<span data-ttu-id="44a1e-217">“活动详细信息”视图中有多个选项卡，可用于进一步调查活动。</span><span class="sxs-lookup"><span data-stu-id="44a1e-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="44a1e-218">**URL 单击**：如果用户未单击仿冒邮件中的有效负载 URL，则此部分将为空。</span><span class="sxs-lookup"><span data-stu-id="44a1e-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="44a1e-219">如果用户能够单击该 URL，则将填充以下值：</span><span class="sxs-lookup"><span data-stu-id="44a1e-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="44a1e-220">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="44a1e-221">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="44a1e-222">**单击时间**</span><span class="sxs-lookup"><span data-stu-id="44a1e-222">**Click Time**</span></span>

  - <span data-ttu-id="44a1e-223">**单击操作**</span><span class="sxs-lookup"><span data-stu-id="44a1e-223">**Click Action**</span></span>

- <span data-ttu-id="44a1e-224">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="44a1e-224">**Sender IPs**</span></span>

  - <span data-ttu-id="44a1e-225">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="44a1e-226">**总计数**</span><span class="sxs-lookup"><span data-stu-id="44a1e-226">**Total Count**</span></span>

  - <span data-ttu-id="44a1e-227">**收件箱邮件计数**</span><span class="sxs-lookup"><span data-stu-id="44a1e-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="44a1e-228">**阻止的计数**</span><span class="sxs-lookup"><span data-stu-id="44a1e-228">**Blocked Count**</span></span>

  - <span data-ttu-id="44a1e-229">已**通过的 SPF**：发件人[策略框架（SPF）](how-office-365-uses-spf-to-prevent-spoofing.md)对发件人进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="44a1e-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="44a1e-230">未通过 SPF 验证的发件人表示发件人未经过身份验证，或者邮件正在哄骗合法发件人。</span><span class="sxs-lookup"><span data-stu-id="44a1e-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="44a1e-231">**发件人**</span><span class="sxs-lookup"><span data-stu-id="44a1e-231">**Senders**</span></span>

  - <span data-ttu-id="44a1e-232">**发件人**：这是 SMTP MAIL from 命令中的实际发件人地址，而不一定是用户在其电子邮件客户端中看到的 "发件人：" 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="44a1e-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="44a1e-233">**总计数**</span><span class="sxs-lookup"><span data-stu-id="44a1e-233">**Total Count**</span></span>

  - <span data-ttu-id="44a1e-234">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="44a1e-234">**Inboxed**</span></span>

  - <span data-ttu-id="44a1e-235">**不 Inboxed**</span><span class="sxs-lookup"><span data-stu-id="44a1e-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="44a1e-236">已**通过 DKIM**：发件人由[识别为邮件的域密钥（DKIM）](support-for-validation-of-dkim-signed-messages.md)进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="44a1e-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="44a1e-237">未通过 DKIM 验证的发件人表示发件人未经过身份验证，或者邮件正在哄骗合法的发件人。</span><span class="sxs-lookup"><span data-stu-id="44a1e-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="44a1e-238">已**通过 DMARC**：发件人通过[基于域的邮件身份验证、报告和合规性（DMARC）](use-dmarc-to-validate-email.md)进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="44a1e-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="44a1e-239">未通过 DMARC 验证的发件人表示发件人未经过身份验证，或者邮件正在哄骗合法的发件人。</span><span class="sxs-lookup"><span data-stu-id="44a1e-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="44a1e-240">**有效负载**</span><span class="sxs-lookup"><span data-stu-id="44a1e-240">**Payloads**</span></span>

  - <span data-ttu-id="44a1e-241">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="44a1e-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="44a1e-242">**总计数**</span><span class="sxs-lookup"><span data-stu-id="44a1e-242">**Total Count**</span></span>

<span data-ttu-id="44a1e-243"><sup>\*</sup> 单击此值将打开一个新浮出控件，其中包含有关“活动详细信息”视图顶部的指定项（用户、URL 等）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="44a1e-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="44a1e-244">若要返回到“活动详细信息”视图，请单击新浮出控件中的“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="44a1e-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="44a1e-245">按钮</span><span class="sxs-lookup"><span data-stu-id="44a1e-245">Buttons</span></span>

<span data-ttu-id="44a1e-246">通过“活动详细信息”视图中的按钮，可使用威胁资源管理器的强大功能进一步调查活动。</span><span class="sxs-lookup"><span data-stu-id="44a1e-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="44a1e-247">**探索活动**：打开新的威胁资源管理器搜索选项卡，将**活动 ID** 值用作搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="44a1e-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="44a1e-248">**浏览 Inboxed 消息**：使用**市场活动 ID**和送达位置打开新的威胁资源管理器搜索选项卡 **： "收件箱**" 作为搜索筛选器。</span><span class="sxs-lookup"><span data-stu-id="44a1e-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
