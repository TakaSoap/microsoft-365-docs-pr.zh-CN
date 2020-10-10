---
title: 用户提交策略
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
- MET150
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: 8347463a4c3f41b6b6333d35c5b4207d1b94aabe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412558"
---
# <a name="user-submissions-policies"></a><span data-ttu-id="756f4-103">用户提交策略</span><span class="sxs-lookup"><span data-stu-id="756f4-103">User submissions policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="756f4-104">在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。</span><span class="sxs-lookup"><span data-stu-id="756f4-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="756f4-105">当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件， (仅将邮件发送给自定义邮箱) 或接收 (发送到自定义邮箱和 Microsoft) 的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="756f4-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="756f4-106">此功能适用于以下邮件报告选项：</span><span class="sxs-lookup"><span data-stu-id="756f4-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="756f4-107">报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="756f4-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="756f4-108">[Outlook 网页上的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (以前称为 Outlook web App) </span><span class="sxs-lookup"><span data-stu-id="756f4-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="756f4-109">Outlook for iOS 和 Outlook for Android 中的内置报告</span><span class="sxs-lookup"><span data-stu-id="756f4-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="756f4-110">如果 [在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。</span><span class="sxs-lookup"><span data-stu-id="756f4-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="756f4-111">您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="756f4-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="756f4-112">将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用 [管理员提交](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="756f4-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="756f4-113">自定义邮箱先决条件</span><span class="sxs-lookup"><span data-stu-id="756f4-113">Custom mailbox prerequisites</span></span>

<span data-ttu-id="756f4-114">使用以下文章配置需要的必备组件，以使用户报告的邮件转到您的自定义邮箱：</span><span class="sxs-lookup"><span data-stu-id="756f4-114">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="756f4-115">通过创建 exchange 邮件流规则以设置垃圾邮件可信度来跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="756f4-115">Skip spam filtering by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="756f4-116">请参阅 [使用 EAC 创建邮件流规则，将邮件的 scl](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) 设置为将 scl 设置为 **-1**。</span><span class="sxs-lookup"><span data-stu-id="756f4-116">See [Use the EAC to create a mail flow rule that sets the SCL of a message](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages?view=o365-worldwide#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="756f4-117">为恶意软件关闭扫描附件。</span><span class="sxs-lookup"><span data-stu-id="756f4-117">Turn off scanning attachments for malware.</span></span> <span data-ttu-id="756f4-118">使用 [Set up (或 edit) ATP Safe 附件策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) 来创建安全附件策略，该策略 **将不会扫描设置为** "已启用恶意软件"。</span><span class="sxs-lookup"><span data-stu-id="756f4-118">Use [Set up (or edit) an ATP Safe Attachments policy](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide#step-2-set-up-or-edit-an-atp-safe-attachments-policy) to create a Safe Attachments policy with the setting **Off - Attachment will not be scanned for malware** enabled.</span></span>

- <span data-ttu-id="756f4-119">对邮件禁用 URL 扫描。</span><span class="sxs-lookup"><span data-stu-id="756f4-119">Turn off URL scanning on messages.</span></span> <span data-ttu-id="756f4-120">使用 [Add (或 edit) ATP Safe Links 策略应用于所有或特定的电子邮件收件人](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients) 。若要创建安全链接策略， **请选择将邮件中可能存在的未知恶意 url 的操作** 设置为 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="756f4-120">Use [Add (or edit) ATP Safe Links policies that apply to all or specific email recipients](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-links-policies?view=o365-worldwide#step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients) to create a Safe Links policy with **Select the action for unknown potentially malicious URLs in messages** set to **Off**.</span></span>

- <span data-ttu-id="756f4-121">创建反恶意软件策略以关闭恶意软件零小时自动清除。</span><span class="sxs-lookup"><span data-stu-id="756f4-121">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="756f4-122">请参阅[使用安全 & 合规性中心创建反恶意软件策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies)，将**恶意软件设置为零小时自动清除** **。**</span><span class="sxs-lookup"><span data-stu-id="756f4-122">See [Use the Security & Compliance Center to create anti-malware policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="756f4-123">创建垃圾邮件筛选器策略，以禁用垃圾邮件 ZAP 和网络钓鱼 ZAP (ZAP) 的零小时自动清除。</span><span class="sxs-lookup"><span data-stu-id="756f4-123">Create a spam filter policy to disable Zero-hour Auto Purge (ZAP) for Spam ZAP and Phish ZAP.</span></span> <span data-ttu-id="756f4-124">请参阅 [使用安全 & 合规性中心创建反垃圾邮件策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) ，并清除用于垃圾邮件 Zap 和网络钓鱼 ZAP 的 " **打开** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="756f4-124">See [Use the Security & Compliance Center to create anti-spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for Spam ZAP and Phish ZAP.</span></span>

- <span data-ttu-id="756f4-125">禁用垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="756f4-125">Disable the junk email rule.</span></span> <span data-ttu-id="756f4-126">使用 [Exchange Online 邮箱上的 "配置垃圾邮件设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) " 禁用垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="756f4-126">Use [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes?view=o365-worldwide) to disable the junk email rule.</span></span> <span data-ttu-id="756f4-127">禁用后，EOP 无法将邮件移动到 "垃圾邮件" 文件夹，具体取决于垃圾邮件筛选判定操作 **将邮件移动到 "垃圾邮件" 文件夹** 或邮箱中的 "安全列表" 集合。</span><span class="sxs-lookup"><span data-stu-id="756f4-127">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="756f4-128">确认您的邮箱符合所有适用的先决条件后，请 [使用安全 & 合规性中心在本文中配置用户提交邮箱](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) () 。</span><span class="sxs-lookup"><span data-stu-id="756f4-128">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="756f4-129">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="756f4-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="756f4-130">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="756f4-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="756f4-131">若要直接转到 " **用户提交** " 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="756f4-131">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="756f4-132">若要修改用户提交的配置，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="756f4-132">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="756f4-133">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="756f4-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="756f4-134">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**组织管理**。</span><span class="sxs-lookup"><span data-stu-id="756f4-134">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="756f4-135">使用安全 & 合规性中心配置用户提交邮箱</span><span class="sxs-lookup"><span data-stu-id="756f4-135">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="756f4-136">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **用户提交**"。</span><span class="sxs-lookup"><span data-stu-id="756f4-136">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="756f4-137">在出现的 " **用户提交** " 页面中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="756f4-137">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="756f4-138">a.</span><span class="sxs-lookup"><span data-stu-id="756f4-138">a.</span></span> <span data-ttu-id="756f4-139">\*\*启用 (建议的 outlook) 的 "报告邮件" 功能 \*\*：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="756f4-139">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="756f4-140">**自定义最终用户确认消息**：单击此链接。</span><span class="sxs-lookup"><span data-stu-id="756f4-140">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="756f4-141">在出现的 " **自定义确认消息** " 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="756f4-141">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="756f4-142">**提交前**：在 " **标题** " 和 " **确认消息** " 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="756f4-142">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="756f4-143">您可以使用变量% type% 来包括提交类型 (垃圾邮件、非垃圾邮件、网络钓鱼等 ) 。</span><span class="sxs-lookup"><span data-stu-id="756f4-143">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="756f4-144">如前所述，如果选择将报告的邮件发送给 Microsoft 的选项，则还会向通知中添加以下文本：</span><span class="sxs-lookup"><span data-stu-id="756f4-144">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="756f4-145">你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="756f4-145">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="756f4-146">有些电子邮件可能包含个人信息或敏感信息。</span><span class="sxs-lookup"><span data-stu-id="756f4-146">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="756f4-147">**提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="756f4-147">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="756f4-148">在 " **标题** " 和 " **确认消息** " 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="756f4-148">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="756f4-149">您可以使用变量% type% 来包括提交类型。</span><span class="sxs-lookup"><span data-stu-id="756f4-149">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="756f4-150">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="756f4-150">When you're finished, click **Save**.</span></span> <span data-ttu-id="756f4-151">若要清除这些值，请单击 "**用户提交**" 页上的 "**还原**回"。</span><span class="sxs-lookup"><span data-stu-id="756f4-151">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="756f4-152">**将报告的邮件发送到**：执行下列任一选择：</span><span class="sxs-lookup"><span data-stu-id="756f4-152">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="756f4-153">\*\*Microsoft (建议) \*\*：不使用用户提交邮箱 (所有报告的邮件都转到 Microsoft) 。</span><span class="sxs-lookup"><span data-stu-id="756f4-153">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="756f4-154">**Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="756f4-154">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="756f4-155">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="756f4-155">Distribution groups are not allowed.</span></span> <span data-ttu-id="756f4-156">用户提交将转到 Microsoft 进行分析和自定义邮箱，以供管理员或安全操作团队进行分析。</span><span class="sxs-lookup"><span data-stu-id="756f4-156">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="756f4-157">**自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="756f4-157">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="756f4-158">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="756f4-158">Distribution groups are not allowed.</span></span> <span data-ttu-id="756f4-159">如果您希望邮件仅转到管理员或安全操作团队进行分析，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="756f4-159">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="756f4-160">除非管理员自行转发，否则邮件不会转到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="756f4-160">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="756f4-161">美国政府组织 (GCC、GCC-H 和 DoD) 只能配置 **自定义邮箱**。</span><span class="sxs-lookup"><span data-stu-id="756f4-161">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="756f4-162">其他两个选项将被禁用。</span><span class="sxs-lookup"><span data-stu-id="756f4-162">The other two options are disabled.</span></span> 

      <span data-ttu-id="756f4-163">完成后，请单击 " **确认**"。</span><span class="sxs-lookup"><span data-stu-id="756f4-163">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="756f4-164">如果您已在 Outlook 网页上使用 Outlook 网页邮箱策略禁用了 " [垃圾邮件报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) "，但您将上述任一设置配置为向 microsoft 报告邮件，则用户可以使用报告邮件加载项在 outlook 网页中向 microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="756f4-164">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="756f4-165">**禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="756f4-165">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="756f4-166">选择 " **使用此自定义邮箱" 可接收用户报告的提交**。</span><span class="sxs-lookup"><span data-stu-id="756f4-166">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="756f4-167">在出现的框中，输入已在 Office 365 中的现有邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="756f4-167">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="756f4-168">这必须是 Exchange Online 中可接收电子邮件的现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="756f4-168">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="756f4-169">完成后，请单击 " **确认**"。</span><span class="sxs-lookup"><span data-stu-id="756f4-169">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="756f4-170">邮件提交格式</span><span class="sxs-lookup"><span data-stu-id="756f4-170">Message submission format</span></span>

<span data-ttu-id="756f4-171">发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。</span><span class="sxs-lookup"><span data-stu-id="756f4-171">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="756f4-172">提交 (信封标题) 的主题应采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="756f4-172">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="756f4-173">是 SafetyAPIAction 是以下整数值之一：</span><span class="sxs-lookup"><span data-stu-id="756f4-173">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="756f4-174">1：垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="756f4-174">1: Junk</span></span>
- <span data-ttu-id="756f4-175">2： NotJunk</span><span class="sxs-lookup"><span data-stu-id="756f4-175">2: NotJunk</span></span>
- <span data-ttu-id="756f4-176">3：网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="756f4-176">3: Phish</span></span>

<span data-ttu-id="756f4-177">在下面的示例中：</span><span class="sxs-lookup"><span data-stu-id="756f4-177">In the following example:</span></span>

- <span data-ttu-id="756f4-178">将邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="756f4-178">The message is being reported as Phish.</span></span>
- <span data-ttu-id="756f4-179">网络邮件 ID 为49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="756f4-179">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="756f4-180">发件人 IP 为167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="756f4-180">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="756f4-181">"发件人" 地址为 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="756f4-181">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="756f4-182">邮件的主题行是 "测试网络钓鱼提交"</span><span class="sxs-lookup"><span data-stu-id="756f4-182">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="756f4-183">不遵循此格式的邮件在提交门户中不会正确显示。</span><span class="sxs-lookup"><span data-stu-id="756f4-183">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
