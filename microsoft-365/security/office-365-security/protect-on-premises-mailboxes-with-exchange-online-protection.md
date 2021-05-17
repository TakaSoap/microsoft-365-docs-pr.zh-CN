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
description: 中国使用由世纪Office 365的管理员可了解如何使用独立 Exchange Online Protection (EOP) 保护其本地邮箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203865"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a><span data-ttu-id="b6461-103">在中国使用独立 EOP 保护本地邮箱</span><span class="sxs-lookup"><span data-stu-id="b6461-103">Protect on-premises mailboxes in China with standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="b6461-104">本文仅适用于由世纪Office 365中国运营的系列文章。</span><span class="sxs-lookup"><span data-stu-id="b6461-104">This article applies only to Office 365 operated by 21Vianet in China.</span></span>

<span data-ttu-id="b6461-105">即使您计划在本地托管部分或所有邮箱，您仍可以使用 EOP Exchange Online Protection (邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="b6461-105">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b6461-106">若要配置连接器，你的帐户必须是全局管理员Exchange组织管理角色组 (公司管理员) 。</span><span class="sxs-lookup"><span data-stu-id="b6461-106">To configure connectors, your account must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span> <span data-ttu-id="b6461-107">有关这些权限Office 365权限Exchange，请参阅在由世纪Office 365[中分配管理员角色](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="b6461-107">For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet).</span></span> <span data-ttu-id="b6461-108">如果所有 Exchange邮箱都位于本地，请按照以下步骤设置 EOP 服务。</span><span class="sxs-lookup"><span data-stu-id="b6461-108">If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="b6461-109">步骤 1：使用Microsoft 365中心添加和验证域</span><span class="sxs-lookup"><span data-stu-id="b6461-109">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="b6461-110">在Microsoft 365管理中心中，导航到"设置"以将域添加到服务。</span><span class="sxs-lookup"><span data-stu-id="b6461-110">In the Microsoft 365 admin center, navigate to Setup to add your domain to the service.</span></span>

2. <span data-ttu-id="b6461-111">按照门户中的步骤将适用的 DNS 记录添加到 DNS 托管提供商，以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="b6461-111">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="b6461-112">将域和用户添加到由[世纪](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet)Office 365运营的域和在管理 DNS 记录时为 Office 365 创建 DNS 记录是向服务添加域和配置[DNS](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet)时参考的有用资源。</span><span class="sxs-lookup"><span data-stu-id="b6461-112">[Add your domain and users to Office 365 operated by 21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) and [Create DNS records for Office 365 when you manage your DNS records](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="b6461-113">步骤 2：添加收件人并配置域类型</span><span class="sxs-lookup"><span data-stu-id="b6461-113">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="b6461-114">在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。</span><span class="sxs-lookup"><span data-stu-id="b6461-114">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service.</span></span> <span data-ttu-id="b6461-115">执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="b6461-115">There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="b6461-116">此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。</span><span class="sxs-lookup"><span data-stu-id="b6461-116">Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative.</span></span> <span data-ttu-id="b6461-117">有关 DBEB 详细信息，请参阅使用 [基于目录的边缘阻止拒绝发送给无效收件人的邮件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="b6461-117">For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="b6461-118">步骤 3：使用 EAC 设置邮件流</span><span class="sxs-lookup"><span data-stu-id="b6461-118">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="b6461-119">在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 Set up connectors to route mail between Office 365 and your own email servers (EAC) 中创建连接器。</span><span class="sxs-lookup"><span data-stu-id="b6461-119">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="b6461-120">有关详细说明，请参阅 Configure [mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="b6461-120">For detailed instructions, see [Configure mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

 <span data-ttu-id="b6461-121">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="b6461-121">How do you know this task worked?</span></span>

 <span data-ttu-id="b6461-122">请参阅[通过验证您的邮件连接器测试Office 365流](/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="b6461-122">See [Test mail flow by validating your Office 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="b6461-123">步骤 4：允许入站端口 25 SMTP 访问</span><span class="sxs-lookup"><span data-stu-id="b6461-123">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="b6461-124">配置连接器后，请等待 72 小时，允许准备 DNS 记录更新。</span><span class="sxs-lookup"><span data-stu-id="b6461-124">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates.</span></span> <span data-ttu-id="b6461-125">然后，将防火墙或邮件服务器的入站端口-25 SMTP 流量限制为仅接受来自 EOP 数据中心的邮件，特别是来自 URL 中列出的 IP 地址和[Office 365。](../../enterprise/managing-office-365-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="b6461-125">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365](../../enterprise/managing-office-365-endpoints.md).</span></span> <span data-ttu-id="b6461-126">此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。</span><span class="sxs-lookup"><span data-stu-id="b6461-126">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="b6461-127">此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。</span><span class="sxs-lookup"><span data-stu-id="b6461-127">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="b6461-p105">将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。</span><span class="sxs-lookup"><span data-stu-id="b6461-p105">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="b6461-130">步骤 5：确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="b6461-130">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="b6461-131">为确保垃圾邮件 (垃圾邮件) 正确路由到每个用户的"垃圾邮件"文件夹，必须执行几个配置步骤。</span><span class="sxs-lookup"><span data-stu-id="b6461-131">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="b6461-132">配置独立 EOP 以将垃圾邮件发送到混合环境中垃圾邮件文件夹中 [提供了这些步骤](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="b6461-132">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="b6461-133">如果您不想将邮件移动到每个用户的"垃圾邮件"文件夹，您可以选择其他操作，通过编辑反垃圾邮件策略 (也称为内容筛选器策略) 。</span><span class="sxs-lookup"><span data-stu-id="b6461-133">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="b6461-134">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b6461-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="b6461-135">步骤 6：使用Microsoft 365中心将 MX 记录指向 EOP</span><span class="sxs-lookup"><span data-stu-id="b6461-135">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="b6461-136">按照 Office 365 域配置步骤更新你的域的 MX 记录，以便于你的入站电子邮件能够通过 EOP。</span><span class="sxs-lookup"><span data-stu-id="b6461-136">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="b6461-137">有关详细信息，可以在管理 DNS 记录时再次引用为Office 365[创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="b6461-137">For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet).</span></span>

<span data-ttu-id="b6461-138">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="b6461-138">How do you know this task worked?</span></span>

 <span data-ttu-id="b6461-139">请参阅[通过验证您的邮件连接器测试Office 365流](/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="b6461-139">See [Test mail flow by validating your Office 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

<span data-ttu-id="b6461-p108">此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：</span><span class="sxs-lookup"><span data-stu-id="b6461-p108">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="b6461-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span><span class="sxs-lookup"><span data-stu-id="b6461-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>

- <span data-ttu-id="b6461-p109">将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="b6461-p109">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="b6461-145">如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。</span><span class="sxs-lookup"><span data-stu-id="b6461-145">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="b6461-146">不太常见：具有本地邮箱和云中的邮箱的混合设置</span><span class="sxs-lookup"><span data-stu-id="b6461-146">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="b6461-147">如果Exchange本地邮箱和云中的一个或多个Exchange Online，则具有 *混合* 设置。</span><span class="sxs-lookup"><span data-stu-id="b6461-147">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a *hybrid* setup.</span></span> <span data-ttu-id="b6461-148">在混合设置中，忙/闲日历共享和邮件路由等功能在本地和云环境中协同工作。</span><span class="sxs-lookup"><span data-stu-id="b6461-148">In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments.</span></span> <span data-ttu-id="b6461-149">在将邮箱转换到邮箱时，您可能具有混合Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b6461-149">You might have a hybrid setup in place while you transition mailboxes to Exchange Online.</span></span> <span data-ttu-id="b6461-150">混合环境的设置方式与 EOP 独立保护不同。</span><span class="sxs-lookup"><span data-stu-id="b6461-150">A hybrid environment is set up differently than EOP standalone protection.</span></span>

<span data-ttu-id="b6461-151">你可以选择混合方案来利用大多数员工的基于云的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b6461-151">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees.</span></span> <span data-ttu-id="b6461-152">您可以在本地托管一些邮箱时进行此操作;例如，对于法律部门。</span><span class="sxs-lookup"><span data-stu-id="b6461-152">You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span>

<span data-ttu-id="b6461-153">混合设置可能很复杂，但有很多好处。</span><span class="sxs-lookup"><span data-stu-id="b6461-153">A hybrid setup can be complex, but it has many benefits.</span></span> <span data-ttu-id="b6461-154">若要了解有关使用混合部署设置混合方案Exchange，请参阅Exchange Server[部署](/Exchange/exchange-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="b6461-154">To learn more about setting up hybrid scenarios with Exchange, see [Exchange Server hybrid deployments](/Exchange/exchange-hybrid).</span></span>