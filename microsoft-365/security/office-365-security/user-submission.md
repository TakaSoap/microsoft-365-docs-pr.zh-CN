---
title: 用户提交策略
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: 7064e2d26722c433d33fe2f983484a40fa33c1e6
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615620"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="79a99-103">用户提交策略</span><span class="sxs-lookup"><span data-stu-id="79a99-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="79a99-104">在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。</span><span class="sxs-lookup"><span data-stu-id="79a99-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="79a99-105">当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件， (仅将邮件发送给自定义邮箱) 或接收 (发送到自定义邮箱和 Microsoft) 的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="79a99-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="79a99-106">此功能适用于以下邮件报告选项：</span><span class="sxs-lookup"><span data-stu-id="79a99-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="79a99-107">报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="79a99-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="79a99-108">[Outlook 网页上的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (以前称为 Outlook web App) </span><span class="sxs-lookup"><span data-stu-id="79a99-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="79a99-109">Outlook for iOS 和 Outlook for Android 中的内置报告</span><span class="sxs-lookup"><span data-stu-id="79a99-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="79a99-110">如果 [在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。</span><span class="sxs-lookup"><span data-stu-id="79a99-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="79a99-111">您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="79a99-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="79a99-112">将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用 [管理员提交](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="79a99-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="79a99-113">自定义邮箱先决条件</span><span class="sxs-lookup"><span data-stu-id="79a99-113">Custom mailbox prerequisites</span></span>

<span data-ttu-id="79a99-114">使用以下文章配置需要的必备组件，以使用户报告的邮件转到您的自定义邮箱：</span><span class="sxs-lookup"><span data-stu-id="79a99-114">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="79a99-115">通过创建用于设置垃圾邮件可信度级别的 exchange 邮件流规则，跳过自定义邮箱上的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="79a99-115">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="79a99-116">请参阅 [使用 EAC 创建邮件流规则，将邮件的 scl](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 设置为将 scl 设置为 **-1**。</span><span class="sxs-lookup"><span data-stu-id="79a99-116">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="79a99-117">为自定义邮箱中的恶意软件关闭扫描附件。</span><span class="sxs-lookup"><span data-stu-id="79a99-117">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="79a99-118">使用 " [在适用于 Office 365 的 Defender 中设置安全附件策略](set-up-atp-safe-attachments-policies.md) " 创建安全附件策略，将安全附件设置为 " **关闭** " " **未知恶意软件响应**"。</span><span class="sxs-lookup"><span data-stu-id="79a99-118">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="79a99-119">对自定义邮箱中的邮件禁用 URL 扫描。</span><span class="sxs-lookup"><span data-stu-id="79a99-119">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="79a99-120">使用 [在 Defender For Office 365 中设置安全链接策略](set-up-atp-safe-links-policies.md) ，以创建一个安全链接策略，其中设置为 " **关闭** "，以便 **为邮件中的未知潜在恶意 url 选择操作**。</span><span class="sxs-lookup"><span data-stu-id="79a99-120">Use [Set up Safe Links policies in Defender for Office 365](set-up-atp-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="79a99-121">创建反恶意软件策略以关闭恶意软件零小时自动清除。</span><span class="sxs-lookup"><span data-stu-id="79a99-121">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="79a99-122">请参阅 [使用安全 & 合规性中心创建反恶意软件策略](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，将 **恶意软件设置为零小时自动清除** **。**</span><span class="sxs-lookup"><span data-stu-id="79a99-122">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="79a99-123">创建垃圾邮件筛选器策略以禁用自定义邮箱中的垃圾邮件和网络钓鱼的零小时自动清除 (ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="79a99-123">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="79a99-124">请参阅 [使用安全 & 合规性中心创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)，并清除用于垃圾邮件 **Zap** 和 **网络钓鱼 ZAP** 的 "**打开**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="79a99-124">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="79a99-125">禁用自定义邮箱中的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="79a99-125">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="79a99-126">使用 [Exchange Online 邮箱上的 "配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md) " 禁用垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="79a99-126">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="79a99-127">禁用后，EOP 无法将邮件移动到 "垃圾邮件" 文件夹，具体取决于垃圾邮件筛选判定操作 **将邮件移动到 "垃圾邮件" 文件夹** 或邮箱中的 "安全列表" 集合。</span><span class="sxs-lookup"><span data-stu-id="79a99-127">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="79a99-128">确认您的邮箱符合所有适用的先决条件后，请 [使用安全 & 合规性中心在本文中配置用户提交邮箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。</span><span class="sxs-lookup"><span data-stu-id="79a99-128">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="79a99-129">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="79a99-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="79a99-130">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="79a99-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="79a99-131">若要直接转到 " **用户提交** " 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="79a99-131">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="79a99-132">若要修改用户提交的配置，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="79a99-132">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="79a99-133">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="79a99-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="79a99-134">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **组织管理**。</span><span class="sxs-lookup"><span data-stu-id="79a99-134">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="79a99-135">使用安全 & 合规性中心配置用户提交邮箱</span><span class="sxs-lookup"><span data-stu-id="79a99-135">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="79a99-136">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **用户提交**"。</span><span class="sxs-lookup"><span data-stu-id="79a99-136">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="79a99-137">在出现的 " **用户提交** " 页面中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="79a99-137">In the **User submissions** page that appears, select one of the following options:</span></span>

   1. <span data-ttu-id="79a99-138">**启用 (建议的 outlook) 的 "报告邮件" 功能**：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="79a99-138">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="79a99-139">**自定义最终用户确认消息**：单击此链接。</span><span class="sxs-lookup"><span data-stu-id="79a99-139">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="79a99-140">在出现的 " **自定义确认消息** " 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="79a99-140">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="79a99-141">**提交前**：在 " **标题** " 和 " **确认消息** " 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="79a99-141">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="79a99-142">您可以使用变量% type% 来包括提交类型 (垃圾邮件、非垃圾邮件、网络钓鱼等 ) 。</span><span class="sxs-lookup"><span data-stu-id="79a99-142">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="79a99-143">如前所述，如果选择将报告的邮件发送给 Microsoft 的选项，则还会向通知中添加以下文本：</span><span class="sxs-lookup"><span data-stu-id="79a99-143">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="79a99-144">你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="79a99-144">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="79a99-145">有些电子邮件可能包含个人信息或敏感信息。</span><span class="sxs-lookup"><span data-stu-id="79a99-145">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="79a99-146">**提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="79a99-146">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="79a99-147">在 " **标题** " 和 " **确认消息** " 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="79a99-147">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="79a99-148">您可以使用变量% type% 来包括提交类型。</span><span class="sxs-lookup"><span data-stu-id="79a99-148">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="79a99-149">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="79a99-149">When you're finished, click **Save**.</span></span> <span data-ttu-id="79a99-150">若要清除这些值，请单击 "**用户提交**" 页上的 "**还原** 回"。</span><span class="sxs-lookup"><span data-stu-id="79a99-150">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="79a99-151">**将报告的邮件发送到**：执行下列任一选择：</span><span class="sxs-lookup"><span data-stu-id="79a99-151">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="79a99-152">**Microsoft (建议)**：不使用用户提交邮箱 (所有报告的邮件都转到 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="79a99-152">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="79a99-153">**Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="79a99-153">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="79a99-154">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="79a99-154">Distribution groups are not allowed.</span></span> <span data-ttu-id="79a99-155">用户提交将转到 Microsoft 进行分析和自定义邮箱，以供管理员或安全操作团队进行分析。</span><span class="sxs-lookup"><span data-stu-id="79a99-155">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="79a99-156">**自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="79a99-156">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="79a99-157">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="79a99-157">Distribution groups are not allowed.</span></span> <span data-ttu-id="79a99-158">如果您希望邮件仅转到管理员或安全操作团队进行分析，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="79a99-158">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="79a99-159">除非管理员自行转发，否则邮件不会转到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="79a99-159">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="79a99-160">美国政府组织 (GCC、GCC-H 和 DoD) 只能配置 **自定义邮箱**。</span><span class="sxs-lookup"><span data-stu-id="79a99-160">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="79a99-161">其他两个选项将被禁用。</span><span class="sxs-lookup"><span data-stu-id="79a99-161">The other two options are disabled.</span></span>

      <span data-ttu-id="79a99-162">完成后，请单击 " **确认**"。</span><span class="sxs-lookup"><span data-stu-id="79a99-162">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="79a99-163">如果您已在 Outlook 网页上使用 Outlook 网页邮箱策略禁用了 " [垃圾邮件报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) "，但您将上述任一设置配置为向 microsoft 报告邮件，则用户可以使用报告邮件加载项在 outlook 网页中向 microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="79a99-163">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="79a99-164">**禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="79a99-164">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="79a99-165">选择 " **使用此自定义邮箱" 可接收用户报告的提交**。</span><span class="sxs-lookup"><span data-stu-id="79a99-165">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="79a99-166">在出现的框中，输入已在 Office 365 中的现有邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="79a99-166">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="79a99-167">这必须是 Exchange Online 中可接收电子邮件的现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="79a99-167">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="79a99-168">完成后，请单击 " **确认**"。</span><span class="sxs-lookup"><span data-stu-id="79a99-168">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="79a99-169">邮件提交格式</span><span class="sxs-lookup"><span data-stu-id="79a99-169">Message submission format</span></span>

<span data-ttu-id="79a99-170">发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。</span><span class="sxs-lookup"><span data-stu-id="79a99-170">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="79a99-171">提交 (信封标题) 的主题应采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="79a99-171">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="79a99-172">其中，SafetyAPIAction 是以下整数值之一：</span><span class="sxs-lookup"><span data-stu-id="79a99-172">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="79a99-173">1：垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="79a99-173">1: Junk</span></span>
- <span data-ttu-id="79a99-174">2：不是垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="79a99-174">2: Not junk</span></span>
- <span data-ttu-id="79a99-175">3：网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="79a99-175">3: Phishing</span></span>

<span data-ttu-id="79a99-176">在下面的示例中：</span><span class="sxs-lookup"><span data-stu-id="79a99-176">In the following example:</span></span>

- <span data-ttu-id="79a99-177">将邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="79a99-177">The message is being reported as phishing.</span></span>
- <span data-ttu-id="79a99-178">网络邮件 ID 为49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="79a99-178">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="79a99-179">发件人 IP 为167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="79a99-179">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="79a99-180">"发件人" 地址为 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="79a99-180">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="79a99-181">邮件的主题行是 "测试网络钓鱼提交"</span><span class="sxs-lookup"><span data-stu-id="79a99-181">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="79a99-182">不遵循此格式的邮件在提交门户中不会正确显示。</span><span class="sxs-lookup"><span data-stu-id="79a99-182">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
