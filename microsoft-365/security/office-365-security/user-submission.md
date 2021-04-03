---
title: 用户提交策略
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d86c79f0f0ab74d1dfbb88e7803f4ee4d691ea73
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501184"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="b654e-103">用户提交策略</span><span class="sxs-lookup"><span data-stu-id="b654e-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b654e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b654e-104">**Applies to**</span></span>
- [<span data-ttu-id="b654e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b654e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b654e-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b654e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b654e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b654e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b654e-108">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，可以指定一个邮箱来接收用户报告为恶意或不恶意的邮件。</span><span class="sxs-lookup"><span data-stu-id="b654e-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="b654e-109">当用户使用各种报告选项提交邮件时，您可以使用此邮箱拦截仅 (发送到自定义邮箱的邮件) 或接收 (发送到自定义邮箱和 Microsoft) 的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="b654e-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="b654e-110">此功能适用于以下邮件报告选项：</span><span class="sxs-lookup"><span data-stu-id="b654e-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="b654e-111">报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="b654e-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="b654e-112">报告网络钓鱼外接程序</span><span class="sxs-lookup"><span data-stu-id="b654e-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="b654e-113">[Outlook 网页网页中的](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 内置 (以前称为Outlook Web App) </span><span class="sxs-lookup"><span data-stu-id="b654e-113">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="b654e-114">Outlook for iOS 和 Outlook for Android 中的内置报告</span><span class="sxs-lookup"><span data-stu-id="b654e-114">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="b654e-115">如果在 [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)网页中禁用了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 Outlook 网页中重新报告邮件。</span><span class="sxs-lookup"><span data-stu-id="b654e-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="b654e-116">还可以配置第三方邮件报告工具，将邮件转发到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b654e-116">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="b654e-117">将用户报告的邮件发送到自定义邮箱，而不是直接发送给 Microsoft，使管理员能够使用管理员提交选择性地将邮件手动 [报告给](admin-submission.md)Microsoft。</span><span class="sxs-lookup"><span data-stu-id="b654e-117">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="b654e-118">自定义邮箱先决条件</span><span class="sxs-lookup"><span data-stu-id="b654e-118">Custom mailbox prerequisites</span></span>

<span data-ttu-id="b654e-119">使用以下文章配置必备组件，以便用户报告的邮件转到自定义邮箱：</span><span class="sxs-lookup"><span data-stu-id="b654e-119">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="b654e-120">通过创建 Exchange 邮件流规则来设置垃圾邮件可信度，跳过自定义邮箱上的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="b654e-120">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="b654e-121">请参阅 [使用 EAC 创建将邮件的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 设置为 **-1** 的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="b654e-121">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="b654e-122">关闭自定义邮箱中恶意软件的扫描附件。</span><span class="sxs-lookup"><span data-stu-id="b654e-122">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="b654e-123">使用 [Defender for Office 365](set-up-safe-attachments-policies.md)中的"设置安全附件策略"创建安全附件策略，同时将"安全附件未知恶意软件响应"设置为"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-123">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="b654e-124">关闭自定义邮箱中邮件的 URL 扫描。</span><span class="sxs-lookup"><span data-stu-id="b654e-124">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="b654e-125">使用 [Defender for Office 365](set-up-safe-links-policies.md)中的"设置安全链接策略"创建安全链接策略，并设置"关闭"以选择邮件中未知潜在恶意 **URL 的操作**。</span><span class="sxs-lookup"><span data-stu-id="b654e-125">Use [Set up Safe Links policies in Defender for Office 365](set-up-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="b654e-126">创建反恶意软件策略以关闭恶意软件零时差自动清除。</span><span class="sxs-lookup"><span data-stu-id="b654e-126">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="b654e-127">请参阅 [使用安全&合规中心创建反恶意软件](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)策略，将 **"恶意软件零时差自动清除**"设置为 **"关闭"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-127">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="b654e-128">创建垃圾邮件筛选器策略，以禁用对自定义邮箱中的 (和网络钓鱼) ZAP 邮件进行零时差自动清除。</span><span class="sxs-lookup"><span data-stu-id="b654e-128">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="b654e-129">请参阅 [使用安全&](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 中心创建反垃圾邮件策略并清除 **垃圾邮件** **ZAP** 和钓鱼邮件 **ZAP** 的打开复选框。</span><span class="sxs-lookup"><span data-stu-id="b654e-129">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="b654e-130">禁用自定义邮箱中的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="b654e-130">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="b654e-131">使用 [配置 Exchange Online 邮箱上的垃圾邮件设置禁用](configure-junk-email-settings-on-exo-mailboxes.md) 垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="b654e-131">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="b654e-132">禁用后，EOP 无法根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱的安全列表集合，将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b654e-132">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="b654e-133">在验证邮箱满足所有适用的先决条件后，请使用安全 [&](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) 合规性中心配置本文 (提交邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="b654e-133">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b654e-134">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b654e-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b654e-135">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="b654e-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b654e-136">若要直接转到用户 **提交页面，** 请使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="b654e-136">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="b654e-137">若要修改用户提交的配置，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="b654e-137">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="b654e-138">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="b654e-138">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="b654e-139">**Exchange** Online 中的 [组织管理](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="b654e-139">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b654e-140">您需要访问 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b654e-140">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="b654e-141">如果您尝试使用的帐户无法访问 Exchange Online PowerShell，则指定提交邮箱时将收到如下所示的错误：</span><span class="sxs-lookup"><span data-stu-id="b654e-141">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="b654e-142">在域中指定电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="b654e-142">Specify an email address in your domain</span></span>

  <span data-ttu-id="b654e-143">有关启用或禁用对 Exchange Online PowerShell 的访问权的信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b654e-143">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="b654e-144">启用或禁用对 Exchange Online PowerShell 的访问</span><span class="sxs-lookup"><span data-stu-id="b654e-144">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="b654e-145">Exchange Online 中的客户端访问规则</span><span class="sxs-lookup"><span data-stu-id="b654e-145">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="b654e-146">使用安全&合规中心配置用户提交邮箱</span><span class="sxs-lookup"><span data-stu-id="b654e-146">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="b654e-147">在安全与&中心，转到"**威胁管理** \> **策略**"" \> **用户提交"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="b654e-148">在出现的 **"用户** 提交"页面中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b654e-148">In the **User submissions** page that appears, select one of the following options:</span></span>

      1. <span data-ttu-id="b654e-149">**启用 Outlook (** 推荐) 的报告邮件功能：如果使用报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页中的内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b654e-149">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

    - <span data-ttu-id="b654e-150">**自定义最终用户确认消息：** 单击此链接。</span><span class="sxs-lookup"><span data-stu-id="b654e-150">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="b654e-151">在出现的 **"自定义确认消息** "飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b654e-151">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

        - <span data-ttu-id="b654e-152">**提交前**：在"标题"和"确认"消息框中，输入用户在使用报告邮件外接程序或报告网络钓鱼外接程序报告邮件之前看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="b654e-152">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="b654e-153">您可以使用变量 %type% 将提交类型 (垃圾邮件、网络钓鱼等) 。</span><span class="sxs-lookup"><span data-stu-id="b654e-153">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

            <span data-ttu-id="b654e-154">如前所述，如果您选择将报告的邮件发送给 Microsoft 的选项，则还会将以下文本添加到通知中：</span><span class="sxs-lookup"><span data-stu-id="b654e-154">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="b654e-155">你的电子邮件将像现在一样提交到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b654e-155">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="b654e-156">某些电子邮件可能包含个人或敏感信息。</span><span class="sxs-lookup"><span data-stu-id="b654e-156">Some emails might contain personal or sensitive information.</span></span>

        - <span data-ttu-id="b654e-157">**提交后**：单击展开 ![ 图标 ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="b654e-157">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="b654e-158">在 **"标题\*\*\*\*"** 和"确认"消息框中，输入用户在使用"报告邮件"外接程序或"报告钓鱼邮件"外接程序报告邮件后看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="b654e-158">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="b654e-159">可以使用变量 %type% 包含提交类型。</span><span class="sxs-lookup"><span data-stu-id="b654e-159">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="b654e-160">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="b654e-160">When you're finished, click **Save**.</span></span> <span data-ttu-id="b654e-161">若要清除这些值，请单击"**用户提交**"页面上的"**还原"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-161">To clear these values, click **Restore** back on the **User submissions** page.</span></span>
    
    - <span data-ttu-id="b654e-162">**自定义最终用户报告选项**：单击此链接。</span><span class="sxs-lookup"><span data-stu-id="b654e-162">**Customize the end-user reporting options**: Click this link.</span></span> <span data-ttu-id="b654e-163">在出现的 **"自定义最终用户报告** 选项"飞出中，输入垃圾邮件报告选项的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="b654e-163">In the **Customize end-user reporting options** flyout that appears, enter the descriptive text for Junk email reporting options.</span></span> 
<span data-ttu-id="b654e-164">在 **"要显示何时报告邮件的选项"下**，至少选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b654e-164">Under **Options to show when messages are reported**, select at least one among the following options:</span></span>
        - <span data-ttu-id="b654e-165">**在发送报告之前询问我**</span><span class="sxs-lookup"><span data-stu-id="b654e-165">**Ask me before sending a report**</span></span>
        - <span data-ttu-id="b654e-166">**自动发送报告**</span><span class="sxs-lookup"><span data-stu-id="b654e-166">**Automatically send reports**</span></span>
        -  <span data-ttu-id="b654e-167">**从不发送报告** </span><span class="sxs-lookup"><span data-stu-id="b654e-167">**Never send reports** </span></span>\
   <span data-ttu-id="b654e-168">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="b654e-168">When you're finished, click **Save**.</span></span>
              - <span data-ttu-id="b654e-169">**将报告的邮件发送到**：进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="b654e-169">**Send the reported messages to**: Make one of the following selections:</span></span>
              - <span data-ttu-id="b654e-170">**Microsoft (推荐) ：** 所有报告的邮件都转到 Microsoft (时，不会使用用户提交) 。</span><span class="sxs-lookup"><span data-stu-id="b654e-170">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>
              - <span data-ttu-id="b654e-171">**Microsoft 和自定义邮箱：** 在出现的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b654e-171">**Both Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="b654e-172">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="b654e-172">Distribution groups are not allowed.</span></span> <span data-ttu-id="b654e-173">用户提交将同时转到 Microsoft 进行分析，并转到自定义邮箱，供管理员或安全运营团队进行分析。</span><span class="sxs-lookup"><span data-stu-id="b654e-173">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>
              - <span data-ttu-id="b654e-174">**仅自定义邮箱**：在出现的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b654e-174">**Custom mailbox only**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="b654e-175">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="b654e-175">Distribution groups are not allowed.</span></span> <span data-ttu-id="b654e-176">如果希望邮件仅转到管理员或安全运营团队进行分析，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="b654e-176">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="b654e-177">除非管理员自行转发，否则邮件不会发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="b654e-177">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b654e-178">GCC、GCC-H 和 DoD (的美国政府组织只能) 自定义 **邮箱**。</span><span class="sxs-lookup"><span data-stu-id="b654e-178">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="b654e-179">其他两个选项已禁用。</span><span class="sxs-lookup"><span data-stu-id="b654e-179">The other two options are disabled.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b654e-180">如果组织配置为仅发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且用户报告的邮件门户中的结果将始终为空。</span><span class="sxs-lookup"><span data-stu-id="b654e-180">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

      <span data-ttu-id="b654e-181">完成后，单击"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-181">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="b654e-182">如果已使用 Web 上的 Outlook 邮箱策略禁用 [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 网页中的垃圾邮件报告，但配置了以上任一设置以向 Microsoft 报告邮件，则用户将能够使用"报告邮件"外接程序或"报告网络钓鱼"外接程序在 Outlook 网页中向 Microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="b654e-182">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>


    1. <span data-ttu-id="b654e-183">**禁用 Outlook** 的"报告邮件"功能：如果您使用第三方报告工具而不是报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页中的内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b654e-183">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

          <span data-ttu-id="b654e-184">选择 **"使用此自定义邮箱接收用户报告的提交"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-184">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="b654e-185">在出现的框中，输入 Office 365 中已有邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b654e-185">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="b654e-186">这应该是 Exchange Online 中可以接收电子邮件的现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="b654e-186">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

          <span data-ttu-id="b654e-187">完成后，单击"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="b654e-187">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="b654e-188">邮件提交格式</span><span class="sxs-lookup"><span data-stu-id="b654e-188">Message submission format</span></span>

<span data-ttu-id="b654e-189">发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。</span><span class="sxs-lookup"><span data-stu-id="b654e-189">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="b654e-190">提交 (信封标题) 应采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="b654e-190">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="b654e-191">其中 SafetyAPIAction 是以下整数值之一：</span><span class="sxs-lookup"><span data-stu-id="b654e-191">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="b654e-192">1：垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b654e-192">1: Junk</span></span>
- <span data-ttu-id="b654e-193">2：非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b654e-193">2: Not junk</span></span>
- <span data-ttu-id="b654e-194">3：网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="b654e-194">3: Phishing</span></span>

<span data-ttu-id="b654e-195">在下面的示例中：</span><span class="sxs-lookup"><span data-stu-id="b654e-195">In the following example:</span></span>

- <span data-ttu-id="b654e-196">邮件被报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="b654e-196">The message is being reported as phishing.</span></span>
- <span data-ttu-id="b654e-197">网络消息 ID 为 49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="b654e-197">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="b654e-198">发件人 IP 为 167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="b654e-198">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="b654e-199">The From address is test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b654e-199">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="b654e-200">邮件的主题行是"测试网络钓鱼提交"</span><span class="sxs-lookup"><span data-stu-id="b654e-200">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="b654e-201">不遵循此格式的邮件将不会在提交门户中正确显示。</span><span class="sxs-lookup"><span data-stu-id="b654e-201">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
