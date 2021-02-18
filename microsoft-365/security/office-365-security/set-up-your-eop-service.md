---
title: 设置独立 EOP 服务
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 管理员可以了解如何设置独立的 Exchange Online Protection (EOP) 来保护本地电子邮件环境。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: de3c40a15a69eb2430c9c9b0473a983ef7c5354f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290461"
---
# <a name="set-up-your-standalone-eop-service"></a><span data-ttu-id="f9147-103">设置独立 EOP 服务</span><span class="sxs-lookup"><span data-stu-id="f9147-103">Set up your standalone EOP service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9147-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="f9147-104">**Applies to**</span></span>
-  [<span data-ttu-id="f9147-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9147-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f9147-106">本主题介绍如何设置独立的 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="f9147-106">This topic explains how to set up standalone Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f9147-107">如果您已从 Office 365 域向导登录到这里，则假如您不想使用 Exchange Online Protection，请返回到 Office 365 域向导。</span><span class="sxs-lookup"><span data-stu-id="f9147-107">If you landed here from the Office 365 domains wizard, go back to the Office 365 domains wizard if you don't want to use Exchange Online Protection.</span></span> <span data-ttu-id="f9147-108">若要详细了解如何配置连接器，请参阅[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="f9147-108">If you're looking for more information on how to configure connectors, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

> [!NOTE]
> <span data-ttu-id="f9147-109">此主题假设你拥有内部部署邮箱，并且想使用 EOP 对其进行保护，这称为独立方案。</span><span class="sxs-lookup"><span data-stu-id="f9147-109">This topic assumes you have on-premises mailboxes and you want to protect them with EOP, which is known as a standalone scenario.</span></span> <span data-ttu-id="f9147-110">如果要使用 Exchange Online 在云中托管所有邮箱，则不必完成本文的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="f9147-110">If you want to host all of your mailboxes in the cloud with Exchange Online, you don't have to complete all of the steps in this article.</span></span> <span data-ttu-id="f9147-111">转到 ["比较 Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) 计划"以注册和购买云邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9147-111">Go to [Compare Exchange Online plans](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) to sign up and purchase cloud mailboxes.</span></span>
>
> <span data-ttu-id="f9147-112">如果你想在内部部署和云中分别托管一部分邮箱，这称为混合方案。</span><span class="sxs-lookup"><span data-stu-id="f9147-112">If you want to host some of your mailboxes on premises and some in the cloud, this is known as a hybrid scenario.</span></span> <span data-ttu-id="f9147-113">这需要更高级的邮件流设置。</span><span class="sxs-lookup"><span data-stu-id="f9147-113">It requires more advanced mail-flow settings.</span></span> <span data-ttu-id="f9147-114">[Exchange Server混合部署](https://docs.microsoft.com/exchange/exchange-hybrid) 介绍了混合邮件流，并提供了指向显示如何设置它的资源的链接。</span><span class="sxs-lookup"><span data-stu-id="f9147-114">[Exchange Server hybrid deployments](https://docs.microsoft.com/exchange/exchange-hybrid) explains hybrid mail flow and has links to resources that show how to set it up.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f9147-115">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="f9147-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f9147-116">估计完成该任务的时间：1 小时</span><span class="sxs-lookup"><span data-stu-id="f9147-116">Estimated time to complete this task: 1 hour</span></span>

- <span data-ttu-id="f9147-117">您需要在 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="f9147-117">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f9147-118">具体来说，您需要"远程域"和"接受域"角色，默认情况下，该角色 (全局管理员) **和邮件** 流管理员角色组。</span><span class="sxs-lookup"><span data-stu-id="f9147-118">Specifically, you need the **Remote and Accepted Domains** role, which is assigned to the **Organization Management** (global admins) and **Mail Flow Administrator** role groups by default.</span></span> <span data-ttu-id="f9147-119">有关详细信息，请参阅独立 [EOP 中](feature-permissions-in-eop.md) 的权限和使用 [EAC 修改角色组的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="f9147-119">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f9147-120">如果你还未注册 EOP，请访问 [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) 并选择购买或者试用服务。</span><span class="sxs-lookup"><span data-stu-id="f9147-120">If you haven't signed up for EOP, visit [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) and choose to buy or try the service.</span></span>

- <span data-ttu-id="f9147-121">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅 Exchange Online 中 [Exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f9147-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f9147-122">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="f9147-122">Having problems?</span></span> <span data-ttu-id="f9147-123">请在 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="f9147-123">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="f9147-124">步骤 1：使用 Microsoft 365 管理中心添加和验证域</span><span class="sxs-lookup"><span data-stu-id="f9147-124">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="f9147-125">在[Microsoft 365 管理中心](../../admin/admin-overview/about-the-admin-center.md)，转到"设置"将域添加到服务。</span><span class="sxs-lookup"><span data-stu-id="f9147-125">In the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md), go to **Setup** to add your domain to the service.</span></span>

2. <span data-ttu-id="f9147-126">按照该步骤将适用的 DNS 记录添加到您的 DNS 托管提供程序以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="f9147-126">Follow the steps to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="f9147-127">在将域添加到服务并配置 DNS 时，向[Office 365](../../admin/setup/add-domain.md)添加域和在任何 DNS 托管提供商处为[Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)创建 DNS 记录是参考的有用资源。</span><span class="sxs-lookup"><span data-stu-id="f9147-127">[Add a domain to Office 365](../../admin/setup/add-domain.md) and [Create DNS records at any DNS hosting provider for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a><span data-ttu-id="f9147-128">步骤 2：添加收件人，并选择性启用 DBEB</span><span class="sxs-lookup"><span data-stu-id="f9147-128">Step 2: Add recipients and optionally enable DBEB</span></span>

<span data-ttu-id="f9147-p106">在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="f9147-p106">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="f9147-133">步骤 3：使用 EAC 设置邮件流</span><span class="sxs-lookup"><span data-stu-id="f9147-133">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="f9147-134">在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 Set up connectors to route mail between Office 365 and your own email servers (EAC) 中创建连接器。</span><span class="sxs-lookup"><span data-stu-id="f9147-134">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="f9147-135">有关详细说明，请参阅 ["设置连接器"以在 Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)和您自己的电子邮件服务器之间路由邮件。</span><span class="sxs-lookup"><span data-stu-id="f9147-135">For detailed instructions, see [Set up connectors to route mail between Microsoft 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).</span></span>

### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="f9147-136">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="f9147-136">How do you know this task worked?</span></span>

<span data-ttu-id="f9147-137">检查服务和环境之间的邮件流。</span><span class="sxs-lookup"><span data-stu-id="f9147-137">Check mail flow between the service and your environment.</span></span> <span data-ttu-id="f9147-138">有关详细信息，请参阅通过验证 [Microsoft 365 连接器来测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="f9147-138">For more information, see [Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="f9147-139">步骤 4：允许入站端口 25 SMTP 访问</span><span class="sxs-lookup"><span data-stu-id="f9147-139">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="f9147-140">配置连接器后，请等待 72 小时以允许 DNS 记录更新传播。</span><span class="sxs-lookup"><span data-stu-id="f9147-140">After you configured connectors, wait 72 hours to allow propagation of your DNS record updates.</span></span> <span data-ttu-id="f9147-141">在此之后，限制防火墙或邮件服务器上的入站端口-25 SMTP 通信，以仅接受来自 EOP 数据中心的邮件，特别是来自 [Exchange Online Protection IP 地址](../../enterprise/urls-and-ip-address-ranges.md)中列出的 IP 地址的邮件。</span><span class="sxs-lookup"><span data-stu-id="f9147-141">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="f9147-142">此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。</span><span class="sxs-lookup"><span data-stu-id="f9147-142">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="f9147-143">此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。</span><span class="sxs-lookup"><span data-stu-id="f9147-143">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="f9147-144">将 SMTP 服务器上的设置配置 60 秒的连接时间。</span><span class="sxs-lookup"><span data-stu-id="f9147-144">Configure settings on the SMTP server with a connection time out of 60 seconds.</span></span> <span data-ttu-id="f9147-145">此设置在大多数情况下都是可接受的，例如，如果邮件发送了较大的附件，则允许出现一些延迟。</span><span class="sxs-lookup"><span data-stu-id="f9147-145">This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for example.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="f9147-146">步骤 5：确保垃圾邮件路由到每个用户的"垃圾邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="f9147-146">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="f9147-147">若要确保垃圾邮件 (垃圾邮件) 正确路由到每个用户的"垃圾邮件"文件夹，必须执行几个配置步骤。</span><span class="sxs-lookup"><span data-stu-id="f9147-147">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="f9147-148">步骤在配置独立 [EOP 中提供，以将垃圾邮件发送到混合环境中垃圾邮件文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="f9147-148">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

<span data-ttu-id="f9147-149">如果您不想将邮件移动到每个用户的"垃圾邮件"文件夹，则通过编辑反垃圾邮件策略可以选择其他操作。</span><span class="sxs-lookup"><span data-stu-id="f9147-149">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies.</span></span> <span data-ttu-id="f9147-150">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f9147-150">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="f9147-151">步骤 6：使用 Microsoft 365 管理中心将 MX 记录指向 EOP</span><span class="sxs-lookup"><span data-stu-id="f9147-151">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="f9147-152">按照域配置步骤更新域的 MX 记录，以便入站电子邮件通过 EOP 流动。</span><span class="sxs-lookup"><span data-stu-id="f9147-152">Follow the domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="f9147-153">请务必将你的 MX 记录直接指向 EOP 而不是让第三方筛选服务将电子邮件中继到 EOP。</span><span class="sxs-lookup"><span data-stu-id="f9147-153">Be sure to point your MX record directly to EOP as opposed to having a third-party filtering service relay email to EOP.</span></span> <span data-ttu-id="f9147-154">有关详细信息，请再次参阅[为 Office 365 创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="f9147-154">For more information, you can again reference [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f9147-155">如果必须将 MX 记录指向位于 EOP 前面的另一台服务器或服务，请参阅 [Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)中连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="f9147-155">If you must point your MX record to another server or service that sits in front of EOP, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="f9147-156">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="f9147-156">How do you know this task worked?</span></span>

<span data-ttu-id="f9147-p114">此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：</span><span class="sxs-lookup"><span data-stu-id="f9147-p114">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="f9147-159">检查服务和环境之间的邮件流。</span><span class="sxs-lookup"><span data-stu-id="f9147-159">Check mail flow between the service and your environment.</span></span> <span data-ttu-id="f9147-160">有关详细信息，请参阅通过验证 [Microsoft 365 连接器来测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="f9147-160">For more information, see [Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

- <span data-ttu-id="f9147-p116">将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9147-p116">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="f9147-163">如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。</span><span class="sxs-lookup"><span data-stu-id="f9147-163">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

> [!TIP]
> <span data-ttu-id="f9147-164">完成安装后，您无需进行其他操作，EOP 即可删除垃圾邮件和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="f9147-164">When you've completed your setup, you don't have to perform extra steps to make EOP remove spam and malware.</span></span> <span data-ttu-id="f9147-165">EOP 会自动删除垃圾邮件和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="f9147-165">EOP removes spam and malware automatically.</span></span> <span data-ttu-id="f9147-166">但是，您可以根据业务需求微调设置。</span><span class="sxs-lookup"><span data-stu-id="f9147-166">However, you can fine tune your settings based on your business requirements.</span></span> <span data-ttu-id="f9147-167">有关详细信息，请参阅 [Office 365](anti-spam-and-anti-malware-protection.md) 中的反垃圾邮件和反恶意软件保护 [以及配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="f9147-167">For more information, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md) and [Configure spoof intelligence](learn-about-spoof-intelligence.md).</span></span>
>
> <span data-ttu-id="f9147-168">现在服务正在运行，我们建议阅读有关配置 EOP 的最佳实践，其中介绍了设置 [EOP](best-practices-for-configuring-eop.md)后的建议设置和注意事项。</span><span class="sxs-lookup"><span data-stu-id="f9147-168">Now that your service is running, we recommend reading [Best practices for configuring EOP](best-practices-for-configuring-eop.md), which describes recommended settings and considerations for after you set up EOP.</span></span>
