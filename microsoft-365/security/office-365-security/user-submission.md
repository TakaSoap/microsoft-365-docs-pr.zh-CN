---
title: 为用户提交的垃圾邮件和网络钓鱼邮件指定邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何配置邮箱以收集用户报告的垃圾邮件和网络钓鱼电子邮件。
ms.openlocfilehash: e9550ce6357ddf19041e752c17e8bd844cba1a11
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726491"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="7d984-103">为 Exchange Online 中的垃圾邮件和网络钓鱼邮件的用户提交指定邮箱</span><span class="sxs-lookup"><span data-stu-id="7d984-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="7d984-104">在使用 Exchange Online 邮箱的 Microsoft 365 组织中，您可以指定接收用户报告为恶意或非恶意邮件的邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d984-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="7d984-105">当用户使用各种报告选项提交邮件时，您可以使用此邮箱来拦截邮件（仅发送到自定义邮箱）或接收邮件副本（发送到自定义邮箱和 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="7d984-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="7d984-106">此功能适用于以下邮件报告选项：</span><span class="sxs-lookup"><span data-stu-id="7d984-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="7d984-107">报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="7d984-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="7d984-108">[Outlook 网页网站中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)（以前称为 "Outlook web App"）</span><span class="sxs-lookup"><span data-stu-id="7d984-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="7d984-109">如果[在 web 上的 Outlook 中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告功能，则在此处启用用户提交将覆盖该设置，并使用户能够在 web 上再次报告 Outlook 中的邮件。</span><span class="sxs-lookup"><span data-stu-id="7d984-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="7d984-110">您还可以配置第三方邮件报告工具，以便将邮件转发到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d984-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="7d984-111">将用户报告的邮件传递到自定义邮箱，而不是直接发送到 Microsoft，使管理员可以有选择性地将邮件报告给 Microsoft，并使用[管理员提交](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="7d984-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7d984-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="7d984-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7d984-113">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="7d984-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7d984-114">若要直接转到 "**用户提交**" 页，请使用 <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="7d984-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="7d984-115">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7d984-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7d984-116">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7d984-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7d984-117">您需要先分配权限，然后才能执行本主题中的过程：</span><span class="sxs-lookup"><span data-stu-id="7d984-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="7d984-118">若要修改用户提交的配置，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="7d984-118">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="7d984-119">[Security & 合规性中心](permissions-in-the-security-and-compliance-center.md)中的 "**组织管理**" 或 "**安全管理员**"。</span><span class="sxs-lookup"><span data-stu-id="7d984-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="7d984-120">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**组织管理**" 或 "**卫生管理**"。</span><span class="sxs-lookup"><span data-stu-id="7d984-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="7d984-121">若要对用户提交进行只读访问，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="7d984-121">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="7d984-122">Security [& 合规性中心](permissions-in-the-security-and-compliance-center.md)中的**安全阅读**。</span><span class="sxs-lookup"><span data-stu-id="7d984-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="7d984-123">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中**的仅查看组织管理**。</span><span class="sxs-lookup"><span data-stu-id="7d984-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="7d984-124">使用安全 & 合规性中心配置用户提交邮箱</span><span class="sxs-lookup"><span data-stu-id="7d984-124">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="7d984-125">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **用户提交**"。</span><span class="sxs-lookup"><span data-stu-id="7d984-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="7d984-126">在出现的 "**用户提交**" 页面中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="7d984-126">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="7d984-127">a.</span><span class="sxs-lookup"><span data-stu-id="7d984-127">a.</span></span> <span data-ttu-id="7d984-128">**为 Outlook 启用 "报告邮件" 功能（推荐）**：如果您在 outlook 网页版中使用报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7d984-128">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="7d984-129">**自定义最终用户确认消息**：单击此链接。</span><span class="sxs-lookup"><span data-stu-id="7d984-129">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="7d984-130">在出现的 "**自定义确认消息**" 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7d984-130">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="7d984-131">**提交前**：在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件之前看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="7d984-131">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="7d984-132">您可以使用变量% type% 来包含提交类型（垃圾邮件、非垃圾邮件、网络钓鱼等）。</span><span class="sxs-lookup"><span data-stu-id="7d984-132">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="7d984-133">如前所述，如果选择将报告的邮件发送给 Microsoft 的选项，则还会向通知中添加以下文本：</span><span class="sxs-lookup"><span data-stu-id="7d984-133">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="7d984-134">你的电子邮件将按与 Microsoft 的相同方式提交到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="7d984-134">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="7d984-135">有些电子邮件可能包含个人信息或敏感信息。</span><span class="sxs-lookup"><span data-stu-id="7d984-135">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="7d984-136">**提交后**：单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="7d984-136">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="7d984-137">在 "**标题**" 和 "**确认消息**" 框中，输入用户在使用报告邮件外接程序报告邮件后看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="7d984-137">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="7d984-138">您可以使用变量% type% 来包括提交类型。</span><span class="sxs-lookup"><span data-stu-id="7d984-138">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="7d984-139">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="7d984-139">When you're finished, click **Save**.</span></span> <span data-ttu-id="7d984-140">若要清除这些值，请单击 "**用户提交**" 页上的 "**还原**回"。</span><span class="sxs-lookup"><span data-stu-id="7d984-140">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="7d984-141">**将报告的邮件发送到**：执行下列任一选择：</span><span class="sxs-lookup"><span data-stu-id="7d984-141">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="7d984-142">**Microsoft （推荐）**：不使用用户提交邮箱（所有报告的邮件都转到 Microsoft）。</span><span class="sxs-lookup"><span data-stu-id="7d984-142">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="7d984-143">**Microsoft 和自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7d984-143">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="7d984-144">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="7d984-144">Distribution groups are not allowed.</span></span> <span data-ttu-id="7d984-145">用户提交将转到 Microsoft 进行分析和自定义邮箱，以供管理员或安全操作团队进行分析。</span><span class="sxs-lookup"><span data-stu-id="7d984-145">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="7d984-146">**自定义邮箱**：在显示的框中，输入现有 Exchange Online 邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7d984-146">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="7d984-147">不允许使用通讯组。</span><span class="sxs-lookup"><span data-stu-id="7d984-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="7d984-148">如果您希望邮件仅转到管理员或安全操作团队进行分析，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="7d984-148">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="7d984-149">除非管理员自行转发，否则邮件不会转到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7d984-149">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="7d984-150">美国政府组织（GCC、GCC-H 和 DoD）只能配置**自定义邮箱**。</span><span class="sxs-lookup"><span data-stu-id="7d984-150">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="7d984-151">其他两个选项将被禁用。</span><span class="sxs-lookup"><span data-stu-id="7d984-151">The other two options are disabled.</span></span> 

      <span data-ttu-id="7d984-152">完成后，请单击 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="7d984-152">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="7d984-153">如果您已在 Outlook 网页上使用 Outlook 网页邮箱策略禁用了 "[垃圾邮件报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)"，但您将上述任一设置配置为向 microsoft 报告邮件，则用户可以使用报告邮件加载项在 outlook 网页中向 microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="7d984-153">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="7d984-154">**禁用 outlook 的报告邮件功能**：如果您在 outlook 网页版中使用第三方报告工具而不是报告邮件外接程序或内置报告，请选择此选项，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7d984-154">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="7d984-155">选择 "**使用此自定义邮箱" 可接收用户报告的提交**。</span><span class="sxs-lookup"><span data-stu-id="7d984-155">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="7d984-156">在出现的框中，输入已在 Office 365 中的现有邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7d984-156">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="7d984-157">这必须是 Exchange Online 中可接收电子邮件的现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d984-157">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="7d984-158">完成后，请单击 "**确认**"。</span><span class="sxs-lookup"><span data-stu-id="7d984-158">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="7d984-159">邮件提交格式</span><span class="sxs-lookup"><span data-stu-id="7d984-159">Message submission format</span></span>

<span data-ttu-id="7d984-160">发送到自定义邮箱的邮件需要遵循特定的提交邮件格式。</span><span class="sxs-lookup"><span data-stu-id="7d984-160">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="7d984-161">提交的主题（信封标题）应采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="7d984-161">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="7d984-162">是 SafetyAPIAction 是以下整数值之一：</span><span class="sxs-lookup"><span data-stu-id="7d984-162">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="7d984-163">1：垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7d984-163">1: Junk</span></span>
- <span data-ttu-id="7d984-164">2： NotJunk</span><span class="sxs-lookup"><span data-stu-id="7d984-164">2: NotJunk</span></span>
- <span data-ttu-id="7d984-165">3：网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="7d984-165">3: Phish</span></span>

<span data-ttu-id="7d984-166">在下面的示例中：</span><span class="sxs-lookup"><span data-stu-id="7d984-166">In the following example:</span></span>

- <span data-ttu-id="7d984-167">将邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="7d984-167">The message is being reported as Phish.</span></span>
- <span data-ttu-id="7d984-168">网络邮件 ID 为49871234-6dc6-43e8-abcd-08d797f20abe。</span><span class="sxs-lookup"><span data-stu-id="7d984-168">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="7d984-169">发件人 IP 为167.220.232.101。</span><span class="sxs-lookup"><span data-stu-id="7d984-169">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="7d984-170">"发件人" 地址为 test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7d984-170">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="7d984-171">邮件的主题行是 "测试网络钓鱼提交"</span><span class="sxs-lookup"><span data-stu-id="7d984-171">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="7d984-172">不遵循此格式的邮件在提交门户中不会正确显示。</span><span class="sxs-lookup"><span data-stu-id="7d984-172">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
