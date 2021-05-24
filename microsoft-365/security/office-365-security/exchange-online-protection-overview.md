---
title: Exchange Online Protection (EOP) 概述
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 了解Exchange Online Protection (EOP) 如何在独立和混合环境中帮助保护本地电子邮件组织。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624715"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="b3946-103">Exchange Online Protection 概述</span><span class="sxs-lookup"><span data-stu-id="b3946-103">Exchange Online Protection overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b3946-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b3946-104">**Applies to**</span></span>
- [<span data-ttu-id="b3946-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b3946-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b3946-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b3946-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b3946-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3946-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b3946-108">Exchange Online Protection (EOP) 是基于云的筛选服务，可帮助保护组织免受垃圾邮件、恶意软件和其他电子邮件威胁的攻击。</span><span class="sxs-lookup"><span data-stu-id="b3946-108">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam, malware, and other email threats.</span></span> <span data-ttu-id="b3946-109">EOP 包含在具有邮箱Microsoft 365的所有Exchange Online中。</span><span class="sxs-lookup"><span data-stu-id="b3946-109">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span>

<span data-ttu-id="b3946-110">本文的其余部分介绍了 EOP 的工作原理。</span><span class="sxs-lookup"><span data-stu-id="b3946-110">The rest of this article explains how EOP works.</span></span>

> [!NOTE]
> <span data-ttu-id="b3946-111">EOP 本身还可用于保护内部部署邮箱和混合环境，以保护内部部署Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3946-111">EOP is also available by itself to protect on-premises mailboxes and in hybrid environments to protect on-premises Exchange mailboxes.</span></span> <span data-ttu-id="b3946-112">有关详细信息，[请参阅独立](/exchange/standalone-eop/standaonline-eop)Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="b3946-112">For more information, see [Standalone Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="b3946-113">EOP 如何工作</span><span class="sxs-lookup"><span data-stu-id="b3946-113">How EOP works</span></span>

<span data-ttu-id="b3946-114">了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="b3946-114">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="在垃圾邮件或隔离裁定之前，通过 Connection、Anti-malware、Mailflow Rules-slash-Policy Filtering 和 Content Filtering 从 Internet 或客户反馈传递到 EOP 的电子邮件的图形。":::

- <span data-ttu-id="b3946-116">传入邮件进入 EOP 时，最初会通过连接筛选，这将检查发件人的信誉。</span><span class="sxs-lookup"><span data-stu-id="b3946-116">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="b3946-117">大多数垃圾邮件此时停止，并遭 EOP 拒绝。</span><span class="sxs-lookup"><span data-stu-id="b3946-117">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="b3946-118">有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="b3946-118">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="b3946-119">然后检查邮件是否有恶意软件。</span><span class="sxs-lookup"><span data-stu-id="b3946-119">Then the message is inspected for malware.</span></span> <span data-ttu-id="b3946-120">如果在邮件或附件中发现恶意软件， (邮件) 仅路由到管理员隔离存储。</span><span class="sxs-lookup"><span data-stu-id="b3946-120">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="b3946-121">若要了解有关恶意软件保护的更多信息，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b3946-121">To learn more about malware protection, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

- <span data-ttu-id="b3946-122">邮件将继续通过策略筛选，其中根据自定义邮件流规则（也称为 (模板创建) 强制实施的传输规则）评估邮件。</span><span class="sxs-lookup"><span data-stu-id="b3946-122">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="b3946-123">例如，你可以将规则设置为当收到来自特定发件人的邮件时向管理器发送通知。</span><span class="sxs-lookup"><span data-stu-id="b3946-123">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="b3946-124">此时， (CAL with Services) 也会进行数据丢失防护 (Exchange Enterprise DLP) 。</span><span class="sxs-lookup"><span data-stu-id="b3946-124">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="b3946-125">接下来，邮件通过反垃圾邮件筛选，其中邮件会检查垃圾邮件、网络钓鱼或批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3946-125">Next, the message passes through anti-spam filtering where the message is check for spam, phishing, or bulk email.</span></span> <span data-ttu-id="b3946-126">检测到的邮件可以发送到隔离邮箱或用户的"垃圾邮件"文件夹以及其他选项。</span><span class="sxs-lookup"><span data-stu-id="b3946-126">Detected messages can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="b3946-127">有关详细信息，请参阅[配置反垃圾邮件策略和](configure-your-spam-filter-policies.md)[配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="b3946-127">For more information see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="b3946-128">任何成功通过所有这些保护层的邮件将传递给收件人。</span><span class="sxs-lookup"><span data-stu-id="b3946-128">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="b3946-129">有关详细信息，请参阅电子邮件 [保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="b3946-129">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="b3946-130">内部部署电子邮件组织的 EOP 计划和功能</span><span class="sxs-lookup"><span data-stu-id="b3946-130">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="b3946-131">可用的 EOP 订阅计划包括：</span><span class="sxs-lookup"><span data-stu-id="b3946-131">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="b3946-132">**独立 EOP：** 注册 EOP 以保护本地电子邮件组织。</span><span class="sxs-lookup"><span data-stu-id="b3946-132">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="b3946-133">**eOP features in Exchange Online**： Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span><span class="sxs-lookup"><span data-stu-id="b3946-133">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b3946-134">**Exchange Enterprise CAL with Services：** 如果你有一个本地 Exchange 组织，你已购买其他 Exchange Enterprise CAL with Services 许可证，则 EOP 是所包括服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="b3946-134">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="b3946-135">有关所有 EOP 订阅计划的要求、重要限制以及功能可用性的信息，请参阅Exchange Online Protection[说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="b3946-135">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="b3946-136">如果您拥有包含Microsoft 365或Office 365邮箱的 Exchange Online 订阅，则具有 EOP。</span><span class="sxs-lookup"><span data-stu-id="b3946-136">If you have a Microsoft 365 or Office 365 subscription that includes Exchange Online mailboxes, you have EOP.</span></span> <span data-ttu-id="b3946-137">有关在订阅中设置 EOP 安全功能的步骤，以及 Microsoft Defender for Office 365 订阅可为您提供的附加安全性的信息，请参阅[防止威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="b3946-137">For steps to set up EOP security features in your subscription, and information on the added security a Microsoft Defender for Office 365 subscription can give you, see [protect against threats](protect-against-threats.md).</span></span> <span data-ttu-id="b3946-138">有关用于设置的 EOP 功能的建议设置，可以在[EOP](recommended-settings-for-eop-and-office365.md)和 Microsoft Defender 的推荐设置中Office 365安全。</span><span class="sxs-lookup"><span data-stu-id="b3946-138">The recommended settings for EOP feature for setup can be found in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="b3946-139">为内部部署电子邮件组织设置 EOP</span><span class="sxs-lookup"><span data-stu-id="b3946-139">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="b3946-p108">设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。</span><span class="sxs-lookup"><span data-stu-id="b3946-p108">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="b3946-142">如果您已购买 EOP，请参阅 [设置 EOP 服务](/exchange/standalone-eop/set-up-your-eop-service)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。</span><span class="sxs-lookup"><span data-stu-id="b3946-142">If you've already purchased EOP, see [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="b3946-143">EOP 数据中心</span><span class="sxs-lookup"><span data-stu-id="b3946-143">EOP datacenters</span></span>

<span data-ttu-id="b3946-144">EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。</span><span class="sxs-lookup"><span data-stu-id="b3946-144">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="b3946-145">例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。</span><span class="sxs-lookup"><span data-stu-id="b3946-145">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="b3946-146">每个数据中心中的服务器代表您接受邮件，从而在您的组织和 Internet 之间提供一个分隔层，从而减少服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="b3946-146">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="b3946-147">通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。</span><span class="sxs-lookup"><span data-stu-id="b3946-147">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="b3946-p110">EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：</span><span class="sxs-lookup"><span data-stu-id="b3946-p110">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="b3946-151">在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="b3946-151">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
- <span data-ttu-id="b3946-152">在 Asia-Pacific (APAC) 中，Exchange Online邮箱都位于 APAC 数据中心，并且邮件当前通过 APAC 数据中心路由，用于 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="b3946-152">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>
- <span data-ttu-id="b3946-153">在美洲，服务分布在以下位置：</span><span class="sxs-lookup"><span data-stu-id="b3946-153">In the Americas, services are distributed in the following locations:</span></span>
  - <span data-ttu-id="b3946-154">南非：Exchange Online邮箱位于巴西和智利的数据中心。</span><span class="sxs-lookup"><span data-stu-id="b3946-154">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="b3946-155">所有邮件均通过本地数据中心进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="b3946-155">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="b3946-156">隔离邮件存储在租户所在的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="b3946-156">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
  - <span data-ttu-id="b3946-157">加拿大：Exchange Online位于加拿大的数据中心。</span><span class="sxs-lookup"><span data-stu-id="b3946-157">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="b3946-158">所有邮件均通过本地数据中心进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="b3946-158">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="b3946-159">隔离邮件存储在租户所在的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="b3946-159">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
  - <span data-ttu-id="b3946-160">美国：Exchange Online邮箱位于美国数据中心。</span><span class="sxs-lookup"><span data-stu-id="b3946-160">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="b3946-161">所有邮件均通过本地数据中心进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="b3946-161">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="b3946-162">隔离邮件存储在租户所在的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="b3946-162">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
- <span data-ttu-id="b3946-163">对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="b3946-163">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="b3946-164">EOP 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="b3946-164">EOP Help for admins</span></span>

<span data-ttu-id="b3946-165">针对 EOP 管理员的帮助内容包括以下顶级类别：</span><span class="sxs-lookup"><span data-stu-id="b3946-165">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="b3946-166">为 Microsoft Defender for Office 365 管理员配置[EOP，第 1](protect-against-threats.md)天：在 Microsoft Defender 的核心为 Office 365 配置 EOP 保护和Office 365。</span><span class="sxs-lookup"><span data-stu-id="b3946-166">[Configure EOP, Day 1, for Microsoft Defender for Office 365 admins](protect-against-threats.md): Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="b3946-167">[EOP 功能](eop-features.md)：提供 EOP 中提供的功能列表。</span><span class="sxs-lookup"><span data-stu-id="b3946-167">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="b3946-168">[设置 EOP 服务](/exchange/standalone-eop/set-up-your-eop-service)：提供设置 EOP 服务的步骤，以及指向其他信息的链接。</span><span class="sxs-lookup"><span data-stu-id="b3946-168">[Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="b3946-169">[从 Google Postini、Barracuda 垃圾邮件和](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)病毒防火墙或 Cisco IronPort 切换到 EOP：介绍从另一个电子邮件保护产品切换到 EOP 的过程。</span><span class="sxs-lookup"><span data-stu-id="b3946-169">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="b3946-170">[在独立 EOP 中管理](/exchange/standalone-eop/manage-recipients-in-eop)收件人：介绍如何在独立 EOP 中管理邮件用户和组。</span><span class="sxs-lookup"><span data-stu-id="b3946-170">[Manage recipients in standalone EOP](/exchange/standalone-eop/manage-recipients-in-eop): Describes how to manage mail users and groups in standalone EOP.</span></span>

- <span data-ttu-id="b3946-171">[EOP](mail-flow-in-eop.md)中的邮件流：介绍如何使用连接器配置自定义邮件流方案，如何管理与服务关联的域，以及如何启用基于目录的边缘阻止 (DBEB) 功能。</span><span class="sxs-lookup"><span data-stu-id="b3946-171">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="b3946-172">[EOP 和 Microsoft Defender Office 365](recommended-settings-for-eop-and-office365.md)安全建议设置：介绍设置和预配服务后的建议配置设置和注意事项。</span><span class="sxs-lookup"><span data-stu-id="b3946-172">[Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="b3946-173">[审核报告中Exchange Online：](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)介绍如何使用审核报告跟踪对服务的配置更改。</span><span class="sxs-lookup"><span data-stu-id="b3946-173">[Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="b3946-174">[EOP 中的](anti-spam-and-anti-malware-protection.md)反垃圾邮件和反恶意软件保护：介绍垃圾邮件筛选和恶意软件筛选，并演示如何自定义它们以最好地满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b3946-174">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="b3946-175">还介绍了管理员和最终用户可以对隔离邮件执行的任务。</span><span class="sxs-lookup"><span data-stu-id="b3946-175">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="b3946-176">[reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)： Describes the reports and troubleshooting tools that are available.</span><span class="sxs-lookup"><span data-stu-id="b3946-176">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="b3946-177">[Exchange](/exchange/exchange-admin-center)[独立 EOP](/exchange/standalone-eop/exchange-admin-center-eop)中的 Exchange Online 管理中心或 Exchange 管理中心 ：介绍如何访问和导航 Exchange 管理中心 (EAC) 管理界面，以便管理相关的 EOP 功能。</span><span class="sxs-lookup"><span data-stu-id="b3946-177">[Exchange admin center in Exchange Online](/exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](/exchange/standalone-eop/exchange-admin-center-eop): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage related EOP features.</span></span>

- <span data-ttu-id="b3946-178">[Exchange Online Protection PowerShell：](/powershell/exchange/exchange-online-protection-powershell)提供有关远程 PowerShell 的信息，通过远程 PowerShell，你可以从命令行管理 EOP 服务。</span><span class="sxs-lookup"><span data-stu-id="b3946-178">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="b3946-179">[EOP 帮助与支持](help-and-support-for-eop.md) 提供有关获取帮助和技术支持的信息。</span><span class="sxs-lookup"><span data-stu-id="b3946-179">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>