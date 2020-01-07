---
title: 在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件传递问题
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 了解如何在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件问题（阻止发送邮件的租户）。
ms.openlocfilehash: 69ee2b7d707ae88cca7aa5d4a5f39e8458f6925f
ms.sourcegitcommit: 82baed362528fed30e9e09c6a4a37c07be2f138d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40959650"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="d75fd-103">在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件传递问题</span><span class="sxs-lookup"><span data-stu-id="d75fd-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="d75fd-104">本主题介绍在未送达报告（也称为 "NDR"、"退回邮件"、"传递状态通知" 或 "DSN"）中看到状态代码 550 5.7.7 xx 时可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d75fd-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="d75fd-105">当你的租户受到限制以单向方式发送电子邮件时，你将看到此自动通知。</span><span class="sxs-lookup"><span data-stu-id="d75fd-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="d75fd-106">这些错误代码通常将为705或750。</span><span class="sxs-lookup"><span data-stu-id="d75fd-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="d75fd-107">5.7.705：租户已超出阈值限制：需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="d75fd-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="d75fd-108">一旦您的用户（统称为 "组织"），通过该服务发送一定数量的可疑电子邮件，则在解决问题之前，可以阻止所有用户发送任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-108">Once your users (collectively, as organization) send a certain amount of suspicious email through the service, all users can be prevented from sending any email until the problem is fixed.</span></span> <span data-ttu-id="d75fd-109">这通常是泄露（最常见的）或发送过多的批量邮件的结果。</span><span class="sxs-lookup"><span data-stu-id="d75fd-109">This is usually the result of a compromise (most common) or sending too much bulk mail.</span></span> <span data-ttu-id="d75fd-110">用户将收到一 NDR，其中指出：</span><span class="sxs-lookup"><span data-stu-id="d75fd-110">Users will receive an NDR that states:</span></span>

`550 5.7.705 Access denied, tenant has exceeded threshold`

<span data-ttu-id="d75fd-111">在极少数情况下，如果您的订阅已过期，也可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d75fd-111">In rare cases, this could also happen if you renew your subscription after it has already expired.</span></span> <span data-ttu-id="d75fd-112">服务同步新订阅信息所需的时间（通常不超过一天），但在这种情况下，可能会阻止您的组织同时发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-112">It takes time for the service to sync the new subscription information (typically, no more than one day), but your organization could be blocked from sending email in the meantime.</span></span> <span data-ttu-id="d75fd-113">避免这种情况的最佳方式是确保你的订阅不会过期。</span><span class="sxs-lookup"><span data-stu-id="d75fd-113">The best way to prevent this is to make sure your subscription does not expire.</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="d75fd-114">5.7.750：未注册的域电子邮件限制：您需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="d75fd-114">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="d75fd-115">Office 365 允许租户通过 Exchange Online Protection （EOP）中继某些邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-115">Office 365 allows tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d75fd-116">例如：</span><span class="sxs-lookup"><span data-stu-id="d75fd-116">For example:</span></span>

- <span data-ttu-id="d75fd-117">Office 365 邮箱接收来自外部发件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-117">An Office 365 mailbox receives email from an external sender.</span></span> <span data-ttu-id="d75fd-118">邮件转发是在 Office 365 邮箱上配置的，因此邮件将返回到用户的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d75fd-118">Mail forwarding is configured on the Office 365 mailbox, so the message goes back out to the user's external email address.</span></span> <span data-ttu-id="d75fd-119">此方案在教育环境中最常见，即学生希望使用其个人电子邮件帐户查看学校相关的邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-119">This scenario is most common in education environments where students want to use their personal email accounts to view school-related messages.</span></span>

- <span data-ttu-id="d75fd-120">具有通过 EOP 发送传出邮件的本地电子邮件服务器的混合 envrionments。</span><span class="sxs-lookup"><span data-stu-id="d75fd-120">Hybrid envrionments that have on-premises email servers that send outgoing mail through EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="d75fd-121">未注册域的问题</span><span class="sxs-lookup"><span data-stu-id="d75fd-121">Problems with unregistered domains</span></span>

<span data-ttu-id="d75fd-122">问题是，在本地电子邮件服务器受到威胁时，会通过 EOP 中继大量垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-122">The problem is when compromised on-premises email servers relay a large volume of spam through EOP.</span></span> <span data-ttu-id="d75fd-123">在几乎所有情况下，连接器都设置正确，但电子邮件是从未注册（也称为未设置）的域发送的。</span><span class="sxs-lookup"><span data-stu-id="d75fd-123">In almost all cases, the connectors are set up correctly, but email is being sent from unregistered (also known as unprovisioned) domains.</span></span> <span data-ttu-id="d75fd-124">Office 365 允许未注册的域中有合理的电子邮件量，但您应配置用于将电子邮件作为接受域发送的每个域。</span><span class="sxs-lookup"><span data-stu-id="d75fd-124">Office 365 allows a reasonable amount of email from unregistered domains, but you should configure every domain that you use to send email as an accepted domain.</span></span>

<span data-ttu-id="d75fd-125">一旦受到威胁，租户将被阻止为未注册的域发送出站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-125">Once compromised, tenants will be prevented from sending outbound email for unregistered domains.</span></span> <span data-ttu-id="d75fd-126">用户将收到一 NDR，其中指出：</span><span class="sxs-lookup"><span data-stu-id="d75fd-126">Users will receive an NDR that states:</span></span>

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="d75fd-127">如何取消阻止租户以便再次发送</span><span class="sxs-lookup"><span data-stu-id="d75fd-127">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="d75fd-128">如果您的租户被阻止发送电子邮件，则需要执行以下几项操作：</span><span class="sxs-lookup"><span data-stu-id="d75fd-128">There are several things you need to do if your tenant is blocked from sending email:</span></span>

1. <span data-ttu-id="d75fd-129">验证是否已注册所有电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="d75fd-129">Verify that all of your email domains are registered.</span></span> <span data-ttu-id="d75fd-130">有关详细信息，请参阅[将域添加到 Office 365](https://docs.microsoft.com/en-us/office365/admin/setup/add-domain)和[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d75fd-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/en-us/office365/admin/setup/add-domain) and [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="d75fd-131">查找异常[连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="d75fd-131">Look for unusual [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> <span data-ttu-id="d75fd-132">恶意参与者通常会在 Office 365 组织中创建新的入站连接器以发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-132">Malicious actors will often create new inbound connectors in your Office 365 organization to send spam.</span></span> <span data-ttu-id="d75fd-133">若要查看现有连接器，请参阅[验证 Office 365 中的连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)。</span><span class="sxs-lookup"><span data-stu-id="d75fd-133">To view your existing connectors, see [Validate connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).</span></span>

3. <span data-ttu-id="d75fd-134">按照对[Office 365 中的受损电子邮件帐户的响应](responding-to-a-compromised-email-account.md)中所述，检查是否存在已损坏的用户。</span><span class="sxs-lookup"><span data-stu-id="d75fd-134">Check for compromised users as described in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

4. <span data-ttu-id="d75fd-135">为 Office 365 组织中的所有管理员[启用 MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 。</span><span class="sxs-lookup"><span data-stu-id="d75fd-135">[Enable MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) for all admins in your Office 365 organization.</span></span>

5. <span data-ttu-id="d75fd-136">锁定你的本地电子邮件服务器并验证其是否未受到威胁。</span><span class="sxs-lookup"><span data-stu-id="d75fd-136">Lock down your on-premises email servers and verify that they are not compromised.</span></span>

   > [!TIP]
   > <span data-ttu-id="d75fd-137">这里有许多因素，尤其是在使用第三方服务器时。</span><span class="sxs-lookup"><span data-stu-id="d75fd-137">There are many factors here, especially if you're using third-party servers.</span></span> <span data-ttu-id="d75fd-138">无论如何，您都需要验证所有传出电子邮件现在是否合法。</span><span class="sxs-lookup"><span data-stu-id="d75fd-138">Regardless, you'll need to verify that all of your outgoing email is now legitimate.</span></span>

6. <span data-ttu-id="d75fd-139">致电 Microsoft 支持部门，让你的租户不再被阻止，以从未注册的域中再次发送。</span><span class="sxs-lookup"><span data-stu-id="d75fd-139">Call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span> <span data-ttu-id="d75fd-140">错误代码很有帮助，但您需要证明您的环境已受到保护，并且无法发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d75fd-140">The error code is helpful, but you'll need to prove that your environment has been secured and is incapable of sending spam.</span></span> <span data-ttu-id="d75fd-141">若要打开支持案例，请参阅[联系支持人员以获取商业产品-管理员帮助](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="d75fd-141">To open a support case, see [Contact support for business products - Admin Help](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d75fd-142">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="d75fd-142">For more information</span></span>

[<span data-ttu-id="d75fd-143">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="d75fd-143">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="d75fd-144">Exchange Online 服务说明的 "发送限制" 部分中的批量邮件指南</span><span class="sxs-lookup"><span data-stu-id="d75fd-144">Bulk Mail guidance in the sending limits section of the Exchange Online service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[<span data-ttu-id="d75fd-145">Office 365 中的电子邮件未送达报告</span><span class="sxs-lookup"><span data-stu-id="d75fd-145">Email non-delivery reports in Office 365</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[<span data-ttu-id="d75fd-146">配置邮箱的电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="d75fd-146">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="d75fd-147">如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="d75fd-147">How to set up a multifunction device or application to send email using Office 365</span></span>](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

<span data-ttu-id="d75fd-148">[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d75fd-148">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
