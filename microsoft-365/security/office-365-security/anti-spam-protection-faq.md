---
title: 反垃圾邮件保护常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以查看有关 Exchange Online Protection (EOP) 中的反垃圾邮件保护的常见问题和) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8620ad3f99c45dae3442ec89d879124053c1a005
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175975"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="bccc7-103">反垃圾邮件保护常见问题解答</span><span class="sxs-lookup"><span data-stu-id="bccc7-103">Anti-spam protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bccc7-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="bccc7-104">**Applies to**</span></span>
- [<span data-ttu-id="bccc7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bccc7-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="bccc7-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bccc7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="bccc7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bccc7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bccc7-108">本主题提供有关 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的反恶意软件保护的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="bccc7-108">This topic provides frequently asked questions and answers about anti-malware protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="bccc7-109">有关隔离的问题和解答，请参阅[隔离常见问题解答](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-109">For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>

<span data-ttu-id="bccc7-110">有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="bccc7-111">有关反欺骗保护的问题和解答，请参阅 [反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="by-default-what-happens-to-a-spam-detected-message"></a><span data-ttu-id="bccc7-112">默认情况下，检测到垃圾邮件的邮件会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bccc7-112">By default, what happens to a spam-detected message?</span></span>

<span data-ttu-id="bccc7-113">**对于入站邮件：** 大多数垃圾邮件都通过连接筛选（基于源电子邮件服务器的 IP 地址）删除。</span><span class="sxs-lookup"><span data-stu-id="bccc7-113">**For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the source email server.</span></span> <span data-ttu-id="bccc7-114">反垃圾邮件策略 (垃圾邮件筛选器策略或内容筛选器策略，) 垃圾邮件、批量邮件或网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-114">Anti-spam policies (also known as spam filter policies or content filter policies) inspect and classify messages as spam, bulk, or phishing.</span></span> <span data-ttu-id="bccc7-115">默认情况下，分类为垃圾邮件或批量邮件将传递到收件人的"垃圾邮件"文件夹，而分类为网络钓鱼的邮件将被隔离。</span><span class="sxs-lookup"><span data-stu-id="bccc7-115">By default, messages that are classified as spam or bulk are delivered to the recipient's Junk Email folder, while messages classified as phishing are quarantined.</span></span> <span data-ttu-id="bccc7-116">您可以修改适用于所有收件人 (的默认反垃圾邮件策略) ，也可以为特定用户组创建具有更严格设置的自定义反垃圾邮件策略 (例如，可以隔离发送给主管人员) 的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-116">You can modify the default anti-spam policy (applies to all recipients), or you can create custom anti-spam policies with stricter settings for specific groups of users (for example, you can quarantine spam that's sent to executives).</span></span> <span data-ttu-id="bccc7-117">有关详细信息，请参阅配置[反垃圾邮件策略和](configure-your-spam-filter-policies.md)[推荐的反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-117">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Recommended anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bccc7-118">在 EOP 保护内部部署邮箱的混合部署中，您需要在本地 Exchange 组织中配置两个 Exchange 邮件流规则 (也称为传输规则) ，以检测添加到邮件中的 EOP 垃圾邮件筛选头。</span><span class="sxs-lookup"><span data-stu-id="bccc7-118">In hybrid deployments where EOP protects on-premises mailboxes, you need to configure two Exchange mail flow rules (also known as transport rules) in your on-premises Exchange organization to detect the EOP spam filtering headers that are added to messages.</span></span> <span data-ttu-id="bccc7-119">有关详细信息，请参阅[在混合环境中将独立 EOP 配置为向“垃圾邮件”文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-119">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

 <span data-ttu-id="bccc7-120">**对于出站邮件：** 邮件通过高风险传递池路由，[](high-risk-delivery-pool-for-outbound-messages.md)或在未送达报告（也称为 NDR 或退回邮件）中 (退回) 。</span><span class="sxs-lookup"><span data-stu-id="bccc7-120">**For outbound messages:** The message is either routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) or is returned to the sender in a non-delivery report (also known as an NDR or bounce message).</span></span> <span data-ttu-id="bccc7-121">有关出站垃圾邮件保护详细信息，请参阅["出站垃圾邮件控制"。](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="bccc7-121">For more information about outbound spam protection, see [Outbound spam controls](outbound-spam-controls.md).</span></span>

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a><span data-ttu-id="bccc7-122">什么是零日垃圾邮件变体，该服务如何处理它？</span><span class="sxs-lookup"><span data-stu-id="bccc7-122">What's a zero-day spam variant and how is it handled by the service?</span></span>

<span data-ttu-id="bccc7-123">零日垃圾邮件变体是从未捕获或分析过的第一代以前未知的垃圾邮件变体，因此我们的反垃圾邮件筛选器尚不具有可用于检测它的任何信息。</span><span class="sxs-lookup"><span data-stu-id="bccc7-123">A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our anti-spam filters don't yet have any information available for detecting it.</span></span> <span data-ttu-id="bccc7-124">在我们的垃圾邮件分析员捕获并分析零日垃圾邮件示例后，如果它符合垃圾邮件分类条件，我们的反垃圾邮件筛选器将进行更新以检测它，并且不再被视为"零日"。</span><span class="sxs-lookup"><span data-stu-id="bccc7-124">After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our anti-spam filters are updated to detect it, and it's no longer considered "zero-day."</span></span>

<span data-ttu-id="bccc7-125">**注意：** 如果您收到可能是零日垃圾邮件变体的邮件，为了帮助我们改进服务，请使用向 Microsoft 报告邮件和文件中所述的方法之一将邮件提交给 [Microsoft。](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="bccc7-125">**Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a><span data-ttu-id="bccc7-126">是否需要配置服务以提供反垃圾邮件保护？</span><span class="sxs-lookup"><span data-stu-id="bccc7-126">Do I need to configure the service to provide anti-spam protection?</span></span>

<span data-ttu-id="bccc7-127">注册服务并添加域后，将自动启用垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bccc7-127">After you sign up for the service and add your domain, spam filtering is automatically enabled.</span></span> <span data-ttu-id="bccc7-128">默认情况下 (，除了前面提到的混合环境中独立 EOP 独立客户的例外情况外，垃圾邮件筛选功能将保护你，而无需任何其他) 。</span><span class="sxs-lookup"><span data-stu-id="bccc7-128">By default, spam filtering is tuned to protect you without needing any additional configuration (aside from the previously noted exception for standalone EOP standalone customers in hybrid environments).</span></span> <span data-ttu-id="bccc7-129">作为管理员，您可以编辑默认垃圾邮件筛选设置，以最好地满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="bccc7-129">As an admin, you can edit the default spam filtering settings to best meet the needs of your organization.</span></span> <span data-ttu-id="bccc7-130">更精细地来说，您还可以创建适用于组织中指定用户、组或域的反垃圾邮件策略和出站反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="bccc7-130">For greater granularity, you can also create anti-spam policies and outbound anti-spam policies that are applied to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="bccc7-131">虽然自定义策略的优先级始终高于默认策略，但可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="bccc7-131">Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>

<span data-ttu-id="bccc7-132">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="bccc7-132">For more information, see the following topics:</span></span>

[<span data-ttu-id="bccc7-133">用于配置 EOP 和 Defender for Office 365 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="bccc7-133">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

[<span data-ttu-id="bccc7-134">在 EOP 中配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="bccc7-134">Configure connection filtering in EOP</span></span>](configure-the-connection-filter-policy.md)

[<span data-ttu-id="bccc7-135">在 EOP 中配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="bccc7-135">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="bccc7-136">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="bccc7-136">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a><span data-ttu-id="bccc7-137">如果我对反垃圾邮件策略进行更改，那么保存更改后需要多久，它们生效？</span><span class="sxs-lookup"><span data-stu-id="bccc7-137">If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?</span></span>

<span data-ttu-id="bccc7-138">更改最多可能需要 1 小时才生效。</span><span class="sxs-lookup"><span data-stu-id="bccc7-138">It may take up to 1 hour for the changes to take effect.</span></span>

## <a name="is-bulk-email-filtering-automatically-enabled"></a><span data-ttu-id="bccc7-139">批量电子邮件筛选是否自动启用？</span><span class="sxs-lookup"><span data-stu-id="bccc7-139">Is bulk email filtering automatically enabled?</span></span>

<span data-ttu-id="bccc7-140">是。</span><span class="sxs-lookup"><span data-stu-id="bccc7-140">Yes.</span></span> <span data-ttu-id="bccc7-141">有关批量电子邮件详细信息，请参阅垃圾邮件和批量电子邮件之间[有什么区别？。](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="bccc7-141">For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

## <a name="does-the-service-provide-url-filtering"></a><span data-ttu-id="bccc7-142">服务是否提供 URL 筛选？</span><span class="sxs-lookup"><span data-stu-id="bccc7-142">Does the service provide URL filtering?</span></span>

<span data-ttu-id="bccc7-143">是，服务具有一个 URL 筛选器，用于检查邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="bccc7-143">Yes, the service has a URL filter that checks for URLs within messages.</span></span> <span data-ttu-id="bccc7-144">如果检测到与已知垃圾邮件或恶意内容关联的 URL，则邮件被标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-144">If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a><span data-ttu-id="bccc7-145">使用此服务的客户如何向 Microsoft 发送 (误报) 非 (垃圾邮件) 误报？</span><span class="sxs-lookup"><span data-stu-id="bccc7-145">How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?</span></span>

<span data-ttu-id="bccc7-146">垃圾邮件和非垃圾邮件可以通过多种方式提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="bccc7-146">Spam and non-spam messages can be submitted to Microsoft for analysis in several ways.</span></span> <span data-ttu-id="bccc7-147">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-147">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="can-i-get-spam-reports"></a><span data-ttu-id="bccc7-148">我能否收到垃圾邮件报告？</span><span class="sxs-lookup"><span data-stu-id="bccc7-148">Can I get spam reports?</span></span>

<span data-ttu-id="bccc7-149">可以，例如，可以在 Microsoft 365 管理中心获取垃圾邮件检测报告。</span><span class="sxs-lookup"><span data-stu-id="bccc7-149">Yes, for example you can get a spam detection report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bccc7-150">此报告以唯一邮件计数显示垃圾邮件数量。</span><span class="sxs-lookup"><span data-stu-id="bccc7-150">This report shows spam volume as a count of unique messages.</span></span> <span data-ttu-id="bccc7-151">有关报告功能详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="bccc7-151">For more information about reporting, see the following links:</span></span>

<span data-ttu-id="bccc7-152">Exchange Online 客户：在 Exchange Online 中监视 [、报告和邮件跟踪](https://docs.microsoft.com/exchange/monitoring/monitoring)</span><span class="sxs-lookup"><span data-stu-id="bccc7-152">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)</span></span>

<span data-ttu-id="bccc7-153">独立 EOP 客户 [：Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="bccc7-153">Standalone EOP customers: [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)</span></span>

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a><span data-ttu-id="bccc7-154">有人向我发送了一条消息，我找不到它。</span><span class="sxs-lookup"><span data-stu-id="bccc7-154">Someone sent me a message and I can't find it.</span></span> <span data-ttu-id="bccc7-155">我怀疑它可能被检测为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-155">I suspect that it may have been detected as spam.</span></span> <span data-ttu-id="bccc7-156">是否有可用于查找的工具？</span><span class="sxs-lookup"><span data-stu-id="bccc7-156">Is there a tool that I can use to find out?</span></span>

<span data-ttu-id="bccc7-157">可以，邮件跟踪工具使您能够在电子邮件通过服务时跟踪它们，以便了解它们发生了什么。</span><span class="sxs-lookup"><span data-stu-id="bccc7-157">Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them.</span></span> <span data-ttu-id="bccc7-158">有关如何使用邮件跟踪工具查找邮件被标记为垃圾邮件的原因详细信息，请参阅邮件 [被标记为垃圾邮件吗？](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span><span class="sxs-lookup"><span data-stu-id="bccc7-158">For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)</span></span>

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a><span data-ttu-id="bccc7-159">如果我的用户发送出站 (，服务) 限制我的邮件速率限制吗？</span><span class="sxs-lookup"><span data-stu-id="bccc7-159">Will the service throttle (rate limit) my mail if my users send outbound spam?</span></span>

<span data-ttu-id="bccc7-160">如果 EOP 确定用户在特定时间范围内通过服务发送的邮件超过一半 (例如每小时) ，则用户将被阻止发送邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-160">If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by EOP, the user will be blocked from sending messages.</span></span> <span data-ttu-id="bccc7-161">在大多数情况下，如果出站邮件被确定为垃圾邮件，它将通过高风险传递池进行路由，这会降低正常的出站 IP 池添加到阻止列表的可能性。</span><span class="sxs-lookup"><span data-stu-id="bccc7-161">In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>

<span data-ttu-id="bccc7-p113">当发件人被阻止发送出站垃圾邮件时，您可以发送通知到一个特定的电子邮件地址。 有关此设置的详细信息，请参阅[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-p113">You can send a notification to a specified email address when a sender is blocked sending outbound spam. For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a><span data-ttu-id="bccc7-164">能否将第三方反垃圾邮件和反恶意软件提供程序与 Exchange Online 结合使用？</span><span class="sxs-lookup"><span data-stu-id="bccc7-164">Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?</span></span>

<span data-ttu-id="bccc7-165">是。</span><span class="sxs-lookup"><span data-stu-id="bccc7-165">Yes.</span></span> <span data-ttu-id="bccc7-166">尽管我们建议你将 MX 记录指向 Microsoft，但我们会意识到，将你的电子邮件路由到 Microsoft 第一时间外的其他位置出于合法的业务原因。</span><span class="sxs-lookup"><span data-stu-id="bccc7-166">Although we recommend that you point your MX record to Microsoft, we realize that there are legitimate business reasons to route your email to somewhere other than Microsoft first.</span></span>

- <span data-ttu-id="bccc7-167">**入站**：将 MX 记录更改为指向第三方提供程序，然后将邮件重定向到 EOP 进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="bccc7-167">**Inbound**: Change your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing.</span></span> <span data-ttu-id="bccc7-168">有关详细信息，请参阅 [Exchange Online 中连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-168">For more information, see [Enhanced Filtering for connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="bccc7-169">**出站**：配置从 Microsoft 365 到目标第三方提供商的智能主机路由。</span><span class="sxs-lookup"><span data-stu-id="bccc7-169">**Outbound**: Configure smart host routing from Microsoft 365 to the destination third-party provider.</span></span>

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a><span data-ttu-id="bccc7-170">Microsoft 是否拥有任何有关如何保护自己免受网络钓鱼诈骗之害的文档？</span><span class="sxs-lookup"><span data-stu-id="bccc7-170">Does Microsoft have any documentation about how I can protect myself from phishing scams?</span></span>

<span data-ttu-id="bccc7-171">是。</span><span class="sxs-lookup"><span data-stu-id="bccc7-171">Yes.</span></span> <span data-ttu-id="bccc7-172">有关详细信息，请参阅 ["保护 Internet 上的隐私"](https://support.microsoft.com/help/4091455)</span><span class="sxs-lookup"><span data-stu-id="bccc7-172">For more information, see [Protect your privacy on the internet](https://support.microsoft.com/help/4091455)</span></span>

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a><span data-ttu-id="bccc7-173">是否正在调查垃圾邮件和恶意软件邮件的发送人，或将其转移到法律执行实体？</span><span class="sxs-lookup"><span data-stu-id="bccc7-173">Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?</span></span>

<span data-ttu-id="bccc7-174">该服务侧重于垃圾邮件和恶意软件检测和删除，但我们有时可能会调查特别危险或破坏性的垃圾邮件或攻击活动，并寻求漏洞。</span><span class="sxs-lookup"><span data-stu-id="bccc7-174">The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators.</span></span> <span data-ttu-id="bccc7-175">这可能涉及与法律和数字犯罪单位合作，以关闭垃圾邮件制造者聊天机器人网络、阻止垃圾邮件制造者使用服务 (（如果他们使用该服务发送出站电子邮件) ）以及将信息传递给法律执行人员。</span><span class="sxs-lookup"><span data-stu-id="bccc7-175">This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a><span data-ttu-id="bccc7-176">确保我的邮件已送达的一组最佳出站邮件做法是什么？</span><span class="sxs-lookup"><span data-stu-id="bccc7-176">What are a set of best outbound mailing practices that will ensure that my mail is delivered?</span></span>

<span data-ttu-id="bccc7-177">下面介绍的指南是发送出站电子邮件的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="bccc7-177">The guidelines presented below are best practices for sending outbound email messages.</span></span>

- <span data-ttu-id="bccc7-178">**源电子邮件域应在 DNS 中解析。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-178">**The source email domain should resolve in DNS.**</span></span>

  <span data-ttu-id="bccc7-179">例如，如果发件人是user@fabrikam，则域 fabrikam 解析为 IP 地址 192.0.43.10。</span><span class="sxs-lookup"><span data-stu-id="bccc7-179">For example, if the sender is user@fabrikam, the domain fabrikam resolves to the IP address 192.0.43.10.</span></span>

  <span data-ttu-id="bccc7-180">如果发送域在 DNS 中没有 A 记录和 MX 记录，则无论邮件内容是否为垃圾邮件，服务都将会通过高风险传送池路由邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-180">If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam.</span></span> <span data-ttu-id="bccc7-181">有关高风险传递池的信息，请参阅出站邮件的高风险 [传递池](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="bccc7-181">For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="bccc7-182">**出站邮件服务器应具有反向 DNS (PTR) 条目。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-182">**Outbound mail eserver should have a reverse DNS (PTR) entry.**</span></span>

  <span data-ttu-id="bccc7-183">例如，如果电子邮件源 IP 地址为 192.0.43.10，则反向 DNS 条目为 `43-10.any.icann.org` 。'</span><span class="sxs-lookup"><span data-stu-id="bccc7-183">For example, if the email source IP address is 192.0.43.10, the reverse DNS entry would be `43-10.any.icann.org`.\`</span></span>

- <span data-ttu-id="bccc7-184">**HELO/EHLO 和 MAIL FROM 命令需要保持一致，并且不是以 IP 地址形式呈现，而是以域名形式呈现。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-184">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>

  <span data-ttu-id="bccc7-185">HELO/EHLO 命令需要配置成与发送 IP 地址的反向 DNS 相匹配，使域在邮件头的各个部分保持相同。</span><span class="sxs-lookup"><span data-stu-id="bccc7-185">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>

- <span data-ttu-id="bccc7-186">**确保在 DNS 中设置了正确的 SPF。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-186">**Ensure that proper SPF records are set up in DNS.**</span></span>

  <span data-ttu-id="bccc7-p119">SPF 记录是一种机制，用于验证从域发出的邮件是否确实来自域并且不带有欺骗性质。 有关 SPF 记录的详细信息，请参阅下列链接：</span><span class="sxs-lookup"><span data-stu-id="bccc7-p119">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>

  [<span data-ttu-id="bccc7-189">设置 SPF 以防止欺骗</span><span class="sxs-lookup"><span data-stu-id="bccc7-189">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [<span data-ttu-id="bccc7-190">关于域的常见问题</span><span class="sxs-lookup"><span data-stu-id="bccc7-190">Domains FAQ</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- <span data-ttu-id="bccc7-191">**使用 DKIM 对电子邮件签名，用较宽松的规范签名。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-191">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>

  <span data-ttu-id="bccc7-p120">如果发件人希望使用域名密钥识别邮件标准 (DKIM) 对邮件签名，并想通过服务发送出站电子邮件，需要使用较宽松的标头规范化算法签名。 用严格的标头规范签名可能导致签名通过服务时变得无效。</span><span class="sxs-lookup"><span data-stu-id="bccc7-p120">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>

- <span data-ttu-id="bccc7-194">**域所有者在 WHOIS 数据库中需要有正确的信息。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-194">**Domain owners should have accurate information in the WHOIS database.**</span></span>

  <span data-ttu-id="bccc7-195">这标识了域所有者以及如何通过稳定的父公司、联系点和名称服务器联系他们。</span><span class="sxs-lookup"><span data-stu-id="bccc7-195">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>

- <span data-ttu-id="bccc7-196">**对于邮件群发程序，发件人： 名字需要反映发送邮件的人，而邮件的主题行应该是对邮件内容的简短摘要。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-196">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>

  <span data-ttu-id="bccc7-p121">邮件正文应该对提供内容、服务或产品有一个清楚的说明。 例如，如果发件人为 Contoso 公司发送一个群发邮件，电子邮件的"发件人"以及"主题"应与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="bccc7-p121">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>

  > <span data-ttu-id="bccc7-199">发件人： marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="bccc7-199">From: marketing@contoso.com</span></span> <br> <span data-ttu-id="bccc7-200">主题： 圣诞季的新更新目录！</span><span class="sxs-lookup"><span data-stu-id="bccc7-200">Subject: New updated catalog for the Christmas season!</span></span>

  <span data-ttu-id="bccc7-201">以下是不能执行的操作的一个示例，因为该示例是非描述性的：</span><span class="sxs-lookup"><span data-stu-id="bccc7-201">The following is an example of what not to do because it is not descriptive:</span></span>

  > <span data-ttu-id="bccc7-202">发件人： user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="bccc7-202">From: user@hotmail.com</span></span> <br> <span data-ttu-id="bccc7-203">主题： 目录</span><span class="sxs-lookup"><span data-stu-id="bccc7-203">Subject: Catalogs</span></span>

- <span data-ttu-id="bccc7-204">**如果将群发邮件发送给很多个收件人，并且邮件是新闻稿的格式，那么在邮件底部应该存在取消订阅的方法。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-204">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>

  <span data-ttu-id="bccc7-205">取消订阅的选项应该与以下内容相似：</span><span class="sxs-lookup"><span data-stu-id="bccc7-205">The unsubscribe option should resemble the following:</span></span>

  > <span data-ttu-id="bccc7-206">该邮件由 sender@fabrikam.com 发送给 example@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="bccc7-206">This message was sent to example@contoso.com by sender@fabrikam.com.</span></span> <span data-ttu-id="bccc7-207">更新配置文件/电子邮件地址|使用 **SafeUnsubscribe |** &trade;隐私策略</span><span class="sxs-lookup"><span data-stu-id="bccc7-207">Update Profile/Email Address | Instant removal with **SafeUnsubscribe**&trade; | Privacy Policy</span></span>

- <span data-ttu-id="bccc7-208">**如果发送群发邮件，需使用双重选择执行列表获取。如果您是一个邮件群发者，双重选择是行业的最佳做法。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-208">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>

  <span data-ttu-id="bccc7-209">双重加入是要求用户采取以下两种操作注册市场邮件的做法。</span><span class="sxs-lookup"><span data-stu-id="bccc7-209">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>

  1. <span data-ttu-id="bccc7-210">第一次在用户单击一个之前未选中的复选框（其中他们选择接收营销人员发送的其他促销或电子邮件）时选择。</span><span class="sxs-lookup"><span data-stu-id="bccc7-210">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>

  2. <span data-ttu-id="bccc7-211">第二次在营销人员向用户提供的电子邮件地址发送确认邮件，要求用户在时间敏感型链接上单击时选择。</span><span class="sxs-lookup"><span data-stu-id="bccc7-211">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>

  <span data-ttu-id="bccc7-212">使用双重选择为群发邮件发件人构建良好的信誉。</span><span class="sxs-lookup"><span data-stu-id="bccc7-212">Using double opt-in builds a good reputation for bulk email senders.</span></span>

- <span data-ttu-id="bccc7-213">**群发邮件发件人应创建透明内容，以便他们负起责任：**</span><span class="sxs-lookup"><span data-stu-id="bccc7-213">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>

  1. <span data-ttu-id="bccc7-214">收件人将发件人添加到通讯簿上的冗长请求应清楚地表明这些操作无法保证邮件传送的安全性。</span><span class="sxs-lookup"><span data-stu-id="bccc7-214">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>

  2. <span data-ttu-id="bccc7-215">当在邮件正文构建重定向时，使用一致的链接样式。</span><span class="sxs-lookup"><span data-stu-id="bccc7-215">When constructing redirects in the body of the message, use a consistent link style.</span></span>

  3. <span data-ttu-id="bccc7-216">请不要发送大容量图片或附件，或仅含一张图片的邮件。</span><span class="sxs-lookup"><span data-stu-id="bccc7-216">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>

  4. <span data-ttu-id="bccc7-217">当采用跟踪像素（网络臭虫或信号），清楚地说明公开隐私或 P3P 设置。</span><span class="sxs-lookup"><span data-stu-id="bccc7-217">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>

- <span data-ttu-id="bccc7-218">**设置出站退回邮件的格式。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-218">**Format outbound bounce messages.**</span></span>

  <span data-ttu-id="bccc7-219">当生成传递状态通知 (也称为未送达报告、未送达报告或退回邮件) 时，发件人应遵循 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)中指定的退回格式。</span><span class="sxs-lookup"><span data-stu-id="bccc7-219">When generating delivery status notification messages (also known as non-delivery reports, NDRs, or bounce messages), senders should follow the format of a bounce as specified in [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).</span></span>

- <span data-ttu-id="bccc7-220">**清除退回的不存在用户的电子邮件地址。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-220">**Remove bounced email addresses for non-existent users.**</span></span>

  <span data-ttu-id="bccc7-p123">如果您接收到一个指示不再使用某电子邮件地址的 NDR，请从列表中清除不存在的电子邮件别名。 电子邮件地址会随时间发生变化，大家有时会丢弃这些地址。</span><span class="sxs-lookup"><span data-stu-id="bccc7-p123">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>

- <span data-ttu-id="bccc7-223">**使用 Hotmail 的智能网络数据服务 (SNDS) 程序。**</span><span class="sxs-lookup"><span data-stu-id="bccc7-223">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>

  <span data-ttu-id="bccc7-p124">Hotmail 使用名为智能网络数据服务的程序，使发件人可以检查最终用户提交的抱怨。 SNDS 是疑难解答 Hotmail 传送问题的初始门户。</span><span class="sxs-lookup"><span data-stu-id="bccc7-p124">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
