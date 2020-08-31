---
title: 在中国使用独立 EOP 保护本地邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用由世纪互联运营的 Office 365 的中国管理员可以了解如何使用独立 Exchange Online Protection (EOP) 来保护其本地邮箱。
ms.openlocfilehash: ca3f7f1ffc91b404ac59e92b40ae1f95709ec3ff
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307745"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a><span data-ttu-id="e1b5d-103">在中国使用独立 EOP 保护本地邮箱</span><span class="sxs-lookup"><span data-stu-id="e1b5d-103">Protect on-premises mailboxes in China with standalone EOP</span></span>

> [!NOTE]
> <span data-ttu-id="e1b5d-104">本文仅适用于由中国世纪互联运营的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-104">This article applies only to Office 365 operated by 21Vianet in China.</span></span>

<span data-ttu-id="e1b5d-105">即使您计划在本地承载部分或全部邮箱，仍可以使用 Exchange Online Protection (EOP) 保护邮箱。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-105">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e1b5d-106">若要配置连接器，你的帐户必须是全局管理员或 Exchange 公司管理员 (组织管理角色组) 。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-106">To configure connectors, your account must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span> <span data-ttu-id="e1b5d-107">有关 Office 365 权限与 Exchange 权限的关系的信息，请参阅 [在由世纪互联运营的 office 365 中分配管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-107">For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet).</span></span> <span data-ttu-id="e1b5d-108">如果所有 Exchange 邮箱都是本地的，请按照以下步骤设置您的 EOP 服务。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-108">If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="e1b5d-109">步骤1：使用 Microsoft 365 管理中心添加并验证你的域</span><span class="sxs-lookup"><span data-stu-id="e1b5d-109">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="e1b5d-110">在 Microsoft 365 管理中心，导航到 "安装程序" 以将您的域添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-110">In the Microsoft 365 admin center, navigate to Setup to add your domain to the service.</span></span>

2. <span data-ttu-id="e1b5d-111">按照门户中的步骤将适用的 DNS 记录添加到您的 DNS 托管提供商，以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-111">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="e1b5d-112">[将您的域和用户添加到由世纪互联运营的 office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) 中，并为 [office 365 创建 dns 记录。当您](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) 将您的域添加到服务并配置 dns 时，可以参考这些资源，从而为 office 创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-112">[Add your domain and users to Office 365 operated by 21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) and [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="e1b5d-113">步骤2：添加收件人并配置域类型</span><span class="sxs-lookup"><span data-stu-id="e1b5d-113">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="e1b5d-114">在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-114">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service.</span></span> <span data-ttu-id="e1b5d-115">执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-115">There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="e1b5d-116">此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-116">Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative.</span></span> <span data-ttu-id="e1b5d-117">有关 DBEB 的详细信息，请参阅 [使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-117">For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="e1b5d-118">步骤 3：使用 EAC 设置邮件流</span><span class="sxs-lookup"><span data-stu-id="e1b5d-118">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="e1b5d-119">在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 Set up connectors to route mail between Office 365 and your own email servers (EAC) 中创建连接器。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-119">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="e1b5d-120">有关详细说明，请参阅 [在 Office 365 中使用连接器配置邮件流](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-120">For detailed instructions, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

 <span data-ttu-id="e1b5d-121">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="e1b5d-121">How do you know this task worked?</span></span>

 <span data-ttu-id="e1b5d-122">请参阅 [Test mail flow by 验证 Office 365 连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-122">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="e1b5d-123">步骤 4：允许入站端口 25 SMTP 访问</span><span class="sxs-lookup"><span data-stu-id="e1b5d-123">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="e1b5d-124">配置连接器后，请等待 72 小时，允许准备 DNS 记录更新。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-124">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates.</span></span> <span data-ttu-id="e1b5d-125">遵循此限制，将防火墙或邮件服务器上的入站端口-25 SMTP 流量限制为仅接受来自 EOP 数据中心的邮件，特别是从 [Office 365 的 url 和 ip 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)列出的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-125">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints).</span></span> <span data-ttu-id="e1b5d-126">此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-126">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="e1b5d-127">此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-127">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="e1b5d-p105">将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-p105">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="e1b5d-130">第5步：确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="e1b5d-130">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="e1b5d-131">若要确保垃圾邮件 () 垃圾邮件被正确路由到每个用户的 "垃圾邮件" 文件夹，您必须执行以下几个配置步骤。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-131">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="e1b5d-132">[配置独立 EOP 将垃圾邮件传递到混合环境中的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)中提供了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-132">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="e1b5d-133">如果不想将邮件移动到每个用户的 "垃圾邮件" 文件夹，可以通过编辑反垃圾邮件策略 (也称为 "内容筛选器策略") 选择另一个操作。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-133">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="e1b5d-134">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="e1b5d-135">步骤6：使用 Microsoft 365 管理中心将 MX 记录指向 EOP</span><span class="sxs-lookup"><span data-stu-id="e1b5d-135">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="e1b5d-136">按照 Office 365 域配置步骤更新你的域的 MX 记录，以便于你的入站电子邮件能够通过 EOP。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-136">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="e1b5d-137">有关详细信息，请参阅 [管理 dns 记录时，可以再次引用为 Office 365 创建 dns 记录](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-137">For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="e1b5d-138">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="e1b5d-138">How do you know this task worked?</span></span>

 <span data-ttu-id="e1b5d-139">请参阅 [Test mail flow by 验证 Office 365 连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-139">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

<span data-ttu-id="e1b5d-p108">此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：</span><span class="sxs-lookup"><span data-stu-id="e1b5d-p108">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="e1b5d-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>

- <span data-ttu-id="e1b5d-p109">将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-p109">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="e1b5d-145">如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-145">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="e1b5d-146">不太常见：包含本地邮箱和云中的混合安装</span><span class="sxs-lookup"><span data-stu-id="e1b5d-146">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="e1b5d-147">如果 exchange Online 中有本地 Exchange 邮箱以及 Exchange Online 中的云中的一个或多个邮箱，则可以使用 *混合* 设置。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-147">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a *hybrid* setup.</span></span> <span data-ttu-id="e1b5d-148">在混合安装中，诸如忙/闲日历共享和邮件路由等功能在本地和云环境中协同工作。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-148">In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments.</span></span> <span data-ttu-id="e1b5d-149">您可能在将邮箱转换为 Exchange Online 时设置了混合设置。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-149">You might have a hybrid setup in place while you transition mailboxes to Exchange Online.</span></span> <span data-ttu-id="e1b5d-150">混合环境的设置与 EOP 独立保护的方式不同。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-150">A hybrid environment is set up differently than EOP standalone protection.</span></span>

<span data-ttu-id="e1b5d-151">您可以选择一种混合方案，以充分利用基于云的电子邮件为大多数员工。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-151">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees.</span></span> <span data-ttu-id="e1b5d-152">您可以执行此操作，同时在本地承载一些邮箱; 请参阅。例如，适用于法律部门。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-152">You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span>

<span data-ttu-id="e1b5d-153">混合设置可能非常复杂，但具有许多好处。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-153">A hybrid setup can be complex, but it has many benefits.</span></span> <span data-ttu-id="e1b5d-154">若要了解有关使用 Exchange 设置混合方案的详细信息，请参阅 [Exchange Server 混合部署](https://docs.microsoft.com/Exchange/exchange-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="e1b5d-154">To learn more about setting up hybrid scenarios with Exchange, see [Exchange Server hybrid deployments](https://docs.microsoft.com/Exchange/exchange-hybrid).</span></span>
