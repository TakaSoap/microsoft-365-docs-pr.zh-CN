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
description: 了解 Exchange Online Protection (EOP) 如何在独立和混合环境中帮助保护本地电子邮件组织。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3df7b376d559535e168bfa21d2a8770b19569c4f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203886"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="47b6f-103">Exchange Online Protection 概述</span><span class="sxs-lookup"><span data-stu-id="47b6f-103">Exchange Online Protection overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="47b6f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="47b6f-104">**Applies to**</span></span>
- [<span data-ttu-id="47b6f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="47b6f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="47b6f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="47b6f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="47b6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47b6f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="47b6f-108">Exchange Online Protection (EOP) 是基于云的筛选服务，可帮助保护组织免受垃圾邮件和恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="47b6f-108">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="47b6f-109">EOP 包含在所有具有 Exchange Online 邮箱的 Microsoft 365 组织中。</span><span class="sxs-lookup"><span data-stu-id="47b6f-109">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="47b6f-110">但是，EOP 也可在下列本地方案中使用：</span><span class="sxs-lookup"><span data-stu-id="47b6f-110">However, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="47b6f-111">**在独立方案中**：EOP 为本地 Exchange 组织或任何其他本地 SMTP 电子邮件解决方案提供基于云的电子邮件保护。</span><span class="sxs-lookup"><span data-stu-id="47b6f-111">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="47b6f-112">**在混合部署** 中：当您混合使用本地邮箱和云邮箱时，EOP 可以配置为保护您的电子邮件环境并控制邮件路由。</span><span class="sxs-lookup"><span data-stu-id="47b6f-112">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="47b6f-113">在这些情况下，EOP 可以简化电子邮件环境的管理，并减轻维护本地硬件和软件带来的许多负担。</span><span class="sxs-lookup"><span data-stu-id="47b6f-113">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="47b6f-114">本主题的其余部分介绍了 EOP 在独立和混合环境中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="47b6f-114">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="47b6f-115">EOP 如何工作</span><span class="sxs-lookup"><span data-stu-id="47b6f-115">How EOP works</span></span>

<span data-ttu-id="47b6f-116">了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="47b6f-116">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="在垃圾邮件或隔离裁定之前，通过 Connection、Anti-malware、Mailflow Rules-slash-Policy Filtering 和 Content Filtering 从 Internet 或客户反馈传递到 EOP 的电子邮件的图形。":::

- <span data-ttu-id="47b6f-118">传入邮件进入 EOP 时，最初会通过连接筛选，这将检查发件人的信誉。</span><span class="sxs-lookup"><span data-stu-id="47b6f-118">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="47b6f-119">大多数垃圾邮件此时停止，并遭 EOP 拒绝。</span><span class="sxs-lookup"><span data-stu-id="47b6f-119">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="47b6f-120">有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="47b6f-120">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="47b6f-121">然后检查邮件是否有恶意软件的迹象。</span><span class="sxs-lookup"><span data-stu-id="47b6f-121">Then the message is inspected for signs of malware.</span></span> <span data-ttu-id="47b6f-122">如果在邮件或附件中发现恶意软件， (邮件) 仅路由到管理员隔离存储。</span><span class="sxs-lookup"><span data-stu-id="47b6f-122">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="47b6f-123">你可以在此处了解有关配置反恶意软件 [的更多信息](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="47b6f-123">You can learn more about configuring anti-malware [here](configure-anti-malware-policies.md).</span></span>

- <span data-ttu-id="47b6f-124">邮件将继续通过策略筛选，其中根据自定义邮件流规则（也称为 (模板创建) 强制实施的传输规则）评估邮件。</span><span class="sxs-lookup"><span data-stu-id="47b6f-124">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="47b6f-125">例如，你可以将规则设置为当收到来自特定发件人的邮件时向管理器发送通知。</span><span class="sxs-lookup"><span data-stu-id="47b6f-125">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="47b6f-126">此时， (EXCHANGE Enterprise CAL with Services) 也会进行数据丢失防护 (DLP) 。</span><span class="sxs-lookup"><span data-stu-id="47b6f-126">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="47b6f-127">接下来，邮件将经过内容筛选 (也称为反垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="47b6f-127">Next, the message passes through content filtering (also known as Anti-spam).</span></span> <span data-ttu-id="47b6f-128">此筛选器确定为垃圾邮件或网络钓鱼的邮件可以发送到隔离区，或者用户的"垃圾邮件"文件夹以及其他选项。</span><span class="sxs-lookup"><span data-stu-id="47b6f-128">A message that this filter determines to be spam *or phish* can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="47b6f-129">有关详细信息，请参阅[配置反垃圾邮件策略和](configure-your-spam-filter-policies.md)[配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="47b6f-129">For more information see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="47b6f-130">任何成功通过所有这些保护层的邮件将传递给收件人。</span><span class="sxs-lookup"><span data-stu-id="47b6f-130">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="47b6f-131">有关详细信息，请参阅电子邮件 [保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="47b6f-131">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="47b6f-132">内部部署电子邮件组织的 EOP 计划和功能</span><span class="sxs-lookup"><span data-stu-id="47b6f-132">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="47b6f-133">可用的 EOP 订阅计划包括：</span><span class="sxs-lookup"><span data-stu-id="47b6f-133">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="47b6f-134">**独立 EOP：** 注册 EOP 以保护本地电子邮件组织。</span><span class="sxs-lookup"><span data-stu-id="47b6f-134">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="47b6f-135">**Exchange Online 中的 EOP** 功能：任何包含 Exchange Online (或作为 Microsoft 365) 的一部分的订阅都使用 EOP 来保护 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="47b6f-135">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="47b6f-136">**Exchange Enterprise CAL with Services：** 如果你有一个本地 Exchange 组织，你已购买其他 Exchange Enterprise CAL with Services 许可证，则 EOP 是所包括服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="47b6f-136">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="47b6f-137">有关所有 EOP 订阅计划的要求、重要限制以及功能可用性的信息，请参阅 [Exchange Online Protection 服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="47b6f-137">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="47b6f-138">为内部部署电子邮件组织设置 EOP</span><span class="sxs-lookup"><span data-stu-id="47b6f-138">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="47b6f-p106">设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。</span><span class="sxs-lookup"><span data-stu-id="47b6f-p106">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="47b6f-141">如果您已购买 EOP，请参阅 [设置 EOP 服务](set-up-your-eop-service.md)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。</span><span class="sxs-lookup"><span data-stu-id="47b6f-141">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="47b6f-142">EOP 数据中心</span><span class="sxs-lookup"><span data-stu-id="47b6f-142">EOP datacenters</span></span>

<span data-ttu-id="47b6f-143">EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。</span><span class="sxs-lookup"><span data-stu-id="47b6f-143">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="47b6f-144">例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。</span><span class="sxs-lookup"><span data-stu-id="47b6f-144">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="47b6f-145">每个数据中心中的服务器代表您接受邮件，从而在您的组织和 Internet 之间提供一个分隔层，从而减少服务器的负载。</span><span class="sxs-lookup"><span data-stu-id="47b6f-145">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="47b6f-146">通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。</span><span class="sxs-lookup"><span data-stu-id="47b6f-146">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="47b6f-p108">EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：</span><span class="sxs-lookup"><span data-stu-id="47b6f-p108">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="47b6f-150">在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="47b6f-150">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="47b6f-151">在 Asia-Pacific (APAC) 中，所有 Exchange Online 邮箱都位于 APAC 数据中心，并且邮件当前通过 APAC 数据中心进行路由，以用于 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="47b6f-151">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="47b6f-152">在美洲，服务分布在以下位置：</span><span class="sxs-lookup"><span data-stu-id="47b6f-152">In the Americas, services are distributed in the following locations:</span></span>

  - <span data-ttu-id="47b6f-153">南非：Exchange Online 邮箱位于巴西和智利的数据中心。</span><span class="sxs-lookup"><span data-stu-id="47b6f-153">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="47b6f-154">所有邮件均通过本地数据中心进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="47b6f-154">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="47b6f-155">隔离邮件存储在租户所在的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="47b6f-155">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="47b6f-156">加拿大：Exchange Online 邮箱位于加拿大的数据中心。</span><span class="sxs-lookup"><span data-stu-id="47b6f-156">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="47b6f-157">所有邮件均通过本地数据中心进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="47b6f-157">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="47b6f-158">隔离邮件存储在租户所在的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="47b6f-158">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="47b6f-159">美国：Exchange Online 邮箱位于美国数据中心。</span><span class="sxs-lookup"><span data-stu-id="47b6f-159">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="47b6f-160">所有邮件均通过本地数据中心进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="47b6f-160">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="47b6f-161">隔离邮件存储在租户所在的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="47b6f-161">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="47b6f-162">对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="47b6f-162">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="47b6f-163">EOP 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="47b6f-163">EOP Help for admins</span></span>

<span data-ttu-id="47b6f-164">针对 EOP 管理员的帮助内容包括以下顶级类别：</span><span class="sxs-lookup"><span data-stu-id="47b6f-164">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="47b6f-165">[Configure EOP， Day 1， for Microsoft Defender for Office 365 admins：](protect-against-threats.md)Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="47b6f-165">[Configure EOP, Day 1, for Microsoft Defender for Office 365 admins](protect-against-threats.md): Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="47b6f-166">[EOP 功能](eop-features.md)：提供 EOP 中提供的功能列表。</span><span class="sxs-lookup"><span data-stu-id="47b6f-166">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="47b6f-167">[设置 EOP 服务](set-up-your-eop-service.md)：提供设置 EOP 服务的步骤，以及指向其他信息的链接。</span><span class="sxs-lookup"><span data-stu-id="47b6f-167">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="47b6f-168">[从 Google Postini、Barracuda 垃圾邮件和](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)病毒防火墙或 Cisco IronPort 切换到 EOP：介绍从另一个电子邮件保护产品切换到 EOP 的过程。</span><span class="sxs-lookup"><span data-stu-id="47b6f-168">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="47b6f-169">[在独立 EOP 中管理](manage-recipients-in-eop.md)收件人：介绍如何在 EOP 中管理邮件用户和组。</span><span class="sxs-lookup"><span data-stu-id="47b6f-169">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="47b6f-170">[EOP](mail-flow-in-eop.md)中的邮件流：介绍如何使用连接器配置自定义邮件流方案，如何管理与服务关联的域，以及如何启用基于目录的边缘阻止 (DBEB) 功能。</span><span class="sxs-lookup"><span data-stu-id="47b6f-170">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="47b6f-171">[配置 EOP 的](best-practices-for-configuring-eop.md)最佳实践：介绍设置和设置服务后的建议配置设置和注意事项。</span><span class="sxs-lookup"><span data-stu-id="47b6f-171">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="47b6f-172">[独立 EOP 中的](auditing-reports-in-eop.md)审核报告 ：介绍如何使用审核报告跟踪对服务的配置更改。</span><span class="sxs-lookup"><span data-stu-id="47b6f-172">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="47b6f-173">[EOP 中的](anti-spam-and-anti-malware-protection.md)反垃圾邮件和反恶意软件保护：介绍垃圾邮件筛选和恶意软件筛选，并演示如何自定义它们以最好地满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="47b6f-173">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="47b6f-174">还介绍了管理员和最终用户可以对隔离邮件执行的任务。</span><span class="sxs-lookup"><span data-stu-id="47b6f-174">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="47b6f-175">[Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)：介绍了可用的报告和疑难解答工具。</span><span class="sxs-lookup"><span data-stu-id="47b6f-175">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="47b6f-176">[独立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)中的 Exchange 管理中心 ：介绍如何通过 Exchange 管理中心 (EAC) 管理界面访问和导航，以便管理 EOP 服务。</span><span class="sxs-lookup"><span data-stu-id="47b6f-176">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="47b6f-177">[Exchange Online Protection PowerShell：](/powershell/exchange/exchange-online-protection-powershell)提供有关远程 PowerShell 的信息，使您可以从命令行管理 EOP 服务。</span><span class="sxs-lookup"><span data-stu-id="47b6f-177">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="47b6f-178">[EOP 帮助与支持](help-and-support-for-eop.md) 提供有关获取帮助和技术支持的信息。</span><span class="sxs-lookup"><span data-stu-id="47b6f-178">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>