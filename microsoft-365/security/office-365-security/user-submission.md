---
title: 用户报告的邮件设置
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
ms.openlocfilehash: 4f14f87355181e9b7f6c0b52aa6b122b560c5f23
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338681"
---
# <a name="user-reported-message-settings"></a><span data-ttu-id="d861d-103">用户报告的邮件设置</span><span class="sxs-lookup"><span data-stu-id="d861d-103">User reported message settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d861d-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="d861d-104">**Applies to**</span></span>
- [<span data-ttu-id="d861d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d861d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d861d-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="d861d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d861d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d861d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d861d-108">在Microsoft 365邮箱Exchange Online，您可以指定一个邮箱来接收用户报告为恶意或不恶意的邮件。</span><span class="sxs-lookup"><span data-stu-id="d861d-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="d861d-109">当用户使用各种报告选项报告邮件时，您可以使用此邮箱截取仅 (发送到自定义邮箱的邮件) 或接收发送到自定义邮箱 (Microsoft) 的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="d861d-109">When users report messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="d861d-110">此功能适用于以下邮件报告选项：</span><span class="sxs-lookup"><span data-stu-id="d861d-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="d861d-111">报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="d861d-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)
- [<span data-ttu-id="d861d-112">报告网络钓鱼外接程序</span><span class="sxs-lookup"><span data-stu-id="d861d-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)
- [<span data-ttu-id="d861d-113">第三方报告工具</span><span class="sxs-lookup"><span data-stu-id="d861d-113">Third-party reporting tools</span></span>](#third-party-reporting-tools)

<span data-ttu-id="d861d-114">将用户报告的邮件发送到自定义邮箱，而不是直接发送给 Microsoft，使管理员能够使用管理员提交选择性地将邮件手动 [报告给](admin-submission.md)Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d861d-114">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span> <span data-ttu-id="d861d-115">这些设置以前称为用户提交策略。</span><span class="sxs-lookup"><span data-stu-id="d861d-115">These settings were formerly known as the User submissions policy.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d861d-116">如果在[邮件中禁用](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)了报告Outlook 网页版，则在此处启用用户报告的邮件将替代该设置，并使用户能够在邮件中Outlook 网页版邮件。</span><span class="sxs-lookup"><span data-stu-id="d861d-116">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user reported messages here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="d861d-117">自定义邮箱先决条件</span><span class="sxs-lookup"><span data-stu-id="d861d-117">Custom mailbox prerequisites</span></span>

<span data-ttu-id="d861d-118">使用以下文章配置必备组件，以便用户报告的邮件转到自定义邮箱：</span><span class="sxs-lookup"><span data-stu-id="d861d-118">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="d861d-119">通过创建 Exchange 邮件流规则来设置垃圾邮件可信度，跳过自定义邮箱上的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="d861d-119">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="d861d-120">请参阅使用 EAC 创建邮件流规则，[该规则将邮件的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)设置为"绕过 **垃圾邮件筛选"。**</span><span class="sxs-lookup"><span data-stu-id="d861d-120">See [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **Bypass spam filtering**.</span></span>

- <span data-ttu-id="d861d-121">[创建一保险箱附件](set-up-safe-attachments-policies.md)策略，其中包括自定义邮箱，其中保险箱附件扫描已关闭 **(保险箱未知** 恶意软件响应"部分关闭 \> ) 。</span><span class="sxs-lookup"><span data-stu-id="d861d-121">[Create a Safe Attachments policy](set-up-safe-attachments-policies.md) that includes the custom mailbox where Safe Attachments scanning is turned off (**Safe Attachments unknown malware response** section \> **Off**).</span></span>

- <span data-ttu-id="d861d-122">[Create a 保险箱 Links policy](set-up-safe-links-policies.md) that includes the custom mailbox where 保险箱 Links scanning is turned off (**Select the action for unknown potentially malicious URLs in messages section** \> **Off**) .</span><span class="sxs-lookup"><span data-stu-id="d861d-122">[Create a Safe Links policy](set-up-safe-links-policies.md) that includes the custom mailbox where Safe Links scanning is turned off (**Select the action for unknown potentially malicious URLs in messages** section \> **Off**).</span></span>

- <span data-ttu-id="d861d-123">[](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)创建一个反恶意软件策略，其中包括自定义邮箱，其中对恶意软件禁用了零时差自动清除 (ZAP)  (**保护设置** 部分未选中"为恶意软件启用零时差自动清除 \> ") 。</span><span class="sxs-lookup"><span data-stu-id="d861d-123">[Create an anti-malware policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where zero-hour auto purge (ZAP) for malware is turned off (**Protection settings** section \> **Enable zero-hour auto purge for malware** is not selected).</span></span>

- <span data-ttu-id="d861d-124">[](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)创建一个反垃圾邮件策略，其中包括自定义邮箱，其中未选择"启用零时差自动清除 (ZAP) "的自定义邮箱，其中"垃圾邮件的 ZAP"和"网络钓鱼的 \> **ZAP"** 被禁用 ("自动清除"部分) 。</span><span class="sxs-lookup"><span data-stu-id="d861d-124">[Create an anti-spam policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where ZAP for spam and ZAP for phishing are turned off (**Zero-hour auto purge** section \> **Enabled zero-hour auto purge (ZAP)** is not selected).</span></span>

- <span data-ttu-id="d861d-125">禁用自定义邮箱中的垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="d861d-125">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="d861d-126">使用[配置邮箱上的垃圾邮件Exchange Online禁用](configure-junk-email-settings-on-exo-mailboxes.md)垃圾邮件规则。</span><span class="sxs-lookup"><span data-stu-id="d861d-126">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="d861d-127">禁用后，EOP 无法根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱的安全列表集合，将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="d861d-127">After it's disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="d861d-128">验证邮箱满足所有适用的先决条件后，可以使用本文中的过程配置用户提交邮箱。</span><span class="sxs-lookup"><span data-stu-id="d861d-128">After you've verified that your mailbox meets all applicable prerequisites, you can use the procedures in this article to configure the user submissions mailbox.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d861d-129">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="d861d-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d861d-130">访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="d861d-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="d861d-131">若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="d861d-131">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="d861d-132">若要修改用户提交的配置，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="d861d-132">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="d861d-133">**组织管理\*\*\*\*或安全管理员**（在 Microsoft 365 Defender [门户中）。](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="d861d-133">**Organization Management** or **Security Administrator** in the [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
- <span data-ttu-id="d861d-134">您需要访问 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d861d-134">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="d861d-135">如果您尝试使用的帐户无法访问 Exchange Online PowerShell，则当您指定提交邮箱时，将收到如下所示的错误：</span><span class="sxs-lookup"><span data-stu-id="d861d-135">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="d861d-136">在域中指定电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="d861d-136">Specify an email address in your domain</span></span>

  <span data-ttu-id="d861d-137">有关启用或禁用对 PowerShell Exchange Online，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d861d-137">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="d861d-138">启用或禁用对 Exchange Online PowerShell 的访问</span><span class="sxs-lookup"><span data-stu-id="d861d-138">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="d861d-139">客户端访问规则Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d861d-139">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="d861d-140">使用Microsoft 365 Defender门户配置用户提交邮箱</span><span class="sxs-lookup"><span data-stu-id="d861d-140">Use the Microsoft 365 Defender portal to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="d861d-141">In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **policies** \> **Others** section User \> **reported message settings** User \> **submissions**.</span><span class="sxs-lookup"><span data-stu-id="d861d-141">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings** \> **User submissions**.</span></span>

2. <span data-ttu-id="d861d-142">在"**用户提交"** 页上，您看到的内容 **由"Microsoft Outlook报告消息**"按钮设置是"关闭"还是"**开"确定**：</span><span class="sxs-lookup"><span data-stu-id="d861d-142">On the **User submissions** page, what you see is determined by whether the **Microsoft Outlook Report Message button** setting is **Off** or **On**:</span></span>

   - <span data-ttu-id="d861d-143">**Microsoft Outlook"报告消息"按钮** \>**打开** ![切换：如果使用报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页版 中的内置报告，请选择此选项，然后配置 ](../../media/scc-toggle-on.png) 以下设置：</span><span class="sxs-lookup"><span data-stu-id="d861d-143">**Microsoft Outlook Report Message button** \> **On** ![Toggle on](../../media/scc-toggle-on.png): Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="d861d-144">**将报告的邮件发送到**：选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="d861d-144">**Send the reported messages to**: Select one of the following options:</span></span>
       - <span data-ttu-id="d861d-145">**Microsoft：** 所有报告的邮件都转到 Microsoft (时，不会使用用户提交) 。</span><span class="sxs-lookup"><span data-stu-id="d861d-145">**Microsoft**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>
       - <span data-ttu-id="d861d-146">**Microsoft 和我的组织的邮箱**：在出现的框中，输入现有邮箱Exchange Online电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d861d-146">**Microsoft and my organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d861d-147">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="d861d-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="d861d-148">用户提交将同时转到 Microsoft 进行分析，并转到自定义邮箱，供管理员或安全运营团队进行分析。</span><span class="sxs-lookup"><span data-stu-id="d861d-148">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>
       - <span data-ttu-id="d861d-149">**我的组织的邮箱**：在出现的框中，输入现有邮箱Exchange Online地址。</span><span class="sxs-lookup"><span data-stu-id="d861d-149">**My organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d861d-150">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="d861d-150">Distribution groups are not allowed.</span></span> <span data-ttu-id="d861d-151">如果希望邮件仅转到管理员或安全运营团队进行分析，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="d861d-151">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="d861d-152">除非管理员自行转发，否则邮件不会发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d861d-152">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!IMPORTANT]
          >
          > <span data-ttu-id="d861d-153">美国政府组织 (GCC、GCC High 和 DoD) 只能配置我的 **组织的邮箱**。</span><span class="sxs-lookup"><span data-stu-id="d861d-153">U.S. Government organizations (GCC, GCC High, and DoD) can only configure **My organization's mailbox**.</span></span> <span data-ttu-id="d861d-154">其他两个选项已禁用。</span><span class="sxs-lookup"><span data-stu-id="d861d-154">The other two options are disabled.</span></span>
          >
          > <span data-ttu-id="d861d-155">如果组织配置为仅发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且用户报告的邮件门户中的结果将始终为空。</span><span class="sxs-lookup"><span data-stu-id="d861d-155">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

       <span data-ttu-id="d861d-156">无论你为"将报告的邮件 **发送到"** 选择的值如何，以下设置都可用：</span><span class="sxs-lookup"><span data-stu-id="d861d-156">Regardless of the value you selected for **Send the reported messages to**, the following settings are available:</span></span>

       - <span data-ttu-id="d861d-157">**让用户选择是否要向 Microsoft 报告其邮件**</span><span class="sxs-lookup"><span data-stu-id="d861d-157">**Let users choose if they want to report their message to Microsoft**</span></span>
       - <span data-ttu-id="d861d-158">**"选择可供用户使用的报告选项"部分** ：至少选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="d861d-158">**Select reporting options that are available to users** section: Select at least one among the following options:</span></span>
         - <span data-ttu-id="d861d-159">**发送邮件前询问我**</span><span class="sxs-lookup"><span data-stu-id="d861d-159">**Ask me before sending the message**</span></span>
         - <span data-ttu-id="d861d-160">**始终报告邮件**</span><span class="sxs-lookup"><span data-stu-id="d861d-160">**Always report the message**</span></span>
         - <span data-ttu-id="d861d-161">**从不报告邮件**</span><span class="sxs-lookup"><span data-stu-id="d861d-161">**Never report the message**</span></span>

          > [!CAUTION]
          > <span data-ttu-id="d861d-162">如果已使用 Outlook 网页版 邮箱策略禁用[Outlook 网页版](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)中的垃圾邮件报告，但配置了之前的任何设置以向 Microsoft 报告邮件，则用户将能够使用报告邮件外接程序或报告网络钓鱼外接程序在 Outlook 网页版 中向 Microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="d861d-162">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configured any of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

     - <span data-ttu-id="d861d-163">**用户报告体验部分**</span><span class="sxs-lookup"><span data-stu-id="d861d-163">**User reporting experience section**</span></span>
       - <span data-ttu-id="d861d-164">**"报告** 前"选项卡：在"标题"和"邮件"正文框中，输入用户在使用报告邮件外接程序或报告网络钓鱼外接程序报告邮件之前看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="d861d-164">**Before reporting** tab: In the **Title** and **Message body** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="d861d-165">您可以使用变量 %type% 将提交类型 (垃圾邮件、网络钓鱼等) 。</span><span class="sxs-lookup"><span data-stu-id="d861d-165">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>
       - <span data-ttu-id="d861d-166">**"报告** 后"选项卡：在"标题"和"确认"消息框中，输入用户在使用"报告邮件"外接程序或"报告钓鱼邮件"外接程序报告邮件后看到的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="d861d-166">**After reporting** tab: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="d861d-167">可以使用变量 %type% 包含提交类型。</span><span class="sxs-lookup"><span data-stu-id="d861d-167">You can use the variable %type% to include the submission type.</span></span>

       <span data-ttu-id="d861d-168">如页面上所示，如果您选择将报告的邮件发送给 Microsoft 的选项，还会将以下文本添加到通知中：</span><span class="sxs-lookup"><span data-stu-id="d861d-168">As shown on the page, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="d861d-169">你的电子邮件将像现在一样提交到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="d861d-169">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="d861d-170">某些电子邮件可能包含个人或敏感信息。</span><span class="sxs-lookup"><span data-stu-id="d861d-170">Some emails might contain personal or sensitive information.</span></span>

   - <span data-ttu-id="d861d-171">**Microsoft Outlook"报告消息"按钮** \>**关闭** ![关闭：如果使用第三方报告工具而不是报告邮件外接程序、报告网络钓鱼外接程序或 Outlook 网页版 中的内置报告，请选择此选项，然后配置 ](../../media/scc-toggle-off.png) 以下设置：</span><span class="sxs-lookup"><span data-stu-id="d861d-171">**Microsoft Outlook Report Message button** \> **Off** ![Toggle off](../../media/scc-toggle-off.png): Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="d861d-172">选择 **"使用此自定义邮箱接收用户报告的提交"。**</span><span class="sxs-lookup"><span data-stu-id="d861d-172">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="d861d-173">在出现的框中，输入可以接收电子邮件Exchange Online邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d861d-173">In the box that appears, enter the email address of an existing Exchange Online mailbox that can receive email.</span></span>

   <span data-ttu-id="d861d-174">完成后，单击"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="d861d-174">When you're finished, click **Confirm**.</span></span> <span data-ttu-id="d861d-175">若要清除这些值，请单击"还原 **"**</span><span class="sxs-lookup"><span data-stu-id="d861d-175">To clear these values, click **Restore**</span></span>

## <a name="third-party-reporting-tools"></a><span data-ttu-id="d861d-176">第三方报告工具</span><span class="sxs-lookup"><span data-stu-id="d861d-176">Third-party reporting tools</span></span>

<span data-ttu-id="d861d-177">可以将第三方邮件报告工具配置为将报告的邮件发送到自定义邮箱。</span><span class="sxs-lookup"><span data-stu-id="d861d-177">You can configure third-party message reporting tools to send reported messages to the custom mailbox.</span></span> <span data-ttu-id="d861d-178">为此，将"Microsoft Outlook **报告邮件**"按钮设置设置为 **"** 关闭"，将"我的组织的邮箱"设置为Office 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="d861d-178">You would do this by setting the **Microsoft Outlook Report Message button** setting to **Off** and setting the **My organization's mailbox** to an Office 365 mailbox of your choice.</span></span>

<span data-ttu-id="d861d-179">唯一的要求是原始邮件作为 包含。EML 或 。MSG (未) 发送到自定义邮箱的邮件中的附件 (不要只将原始邮件转发到自定义邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="d861d-179">The only requirement is that the original message is included as a .EML or .MSG attachment (not compressed) in the message that's sent to the custom mailbox (don't just forward the original message to the custom mailbox).</span></span>

<span data-ttu-id="d861d-180">下一节将介绍邮件格式要求。</span><span class="sxs-lookup"><span data-stu-id="d861d-180">The message formatting requirements are described in the next section.</span></span> <span data-ttu-id="d861d-181">格式是可选的，但如果它不符合规定格式，报告将始终作为网络钓鱼提交。</span><span class="sxs-lookup"><span data-stu-id="d861d-181">The formatting is optional, but if it does not follow the prescribed format, the reports will always be submitted as phish.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="d861d-182">邮件提交格式</span><span class="sxs-lookup"><span data-stu-id="d861d-182">Message submission format</span></span>

<span data-ttu-id="d861d-183">若要正确标识原始附加的邮件，发送到自定义邮箱的邮件需要特定格式。</span><span class="sxs-lookup"><span data-stu-id="d861d-183">To correctly identify the original attached messages, messages that are sent to the custom mailbox require specific formatting.</span></span> <span data-ttu-id="d861d-184">如果邮件不使用此格式，则原始附加的邮件始终标识为网络钓鱼提交。</span><span class="sxs-lookup"><span data-stu-id="d861d-184">If the messages don't use this format, the original attached messages are always identified as phishing submissions.</span></span>

<span data-ttu-id="d861d-185">如果要指定原始附加邮件的报告原因，则发送到自定义邮箱 (的邮件不修改附件) 需要从主题 (信封标题) 中的下列前缀之一开始：</span><span class="sxs-lookup"><span data-stu-id="d861d-185">If you want to specify the reported reason for the original attached messages, messages that are sent to the custom mailbox (don't modify the attachment) need to start with one of the following prefixes in the Subject (Envelope Title):</span></span>

- <span data-ttu-id="d861d-186">1|或垃圾邮件：</span><span class="sxs-lookup"><span data-stu-id="d861d-186">1| or Junk:</span></span>
- <span data-ttu-id="d861d-187">2|或非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d861d-187">2| or Not junk</span></span>
- <span data-ttu-id="d861d-188">3|或网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="d861d-188">3| or Phishing</span></span>

<span data-ttu-id="d861d-189">例如：</span><span class="sxs-lookup"><span data-stu-id="d861d-189">For example:</span></span>

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

- <span data-ttu-id="d861d-190">根据主题，这两条消息都报告为"非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="d861d-190">Both of these messages are being reported as Not Junk based on Subject.</span></span>
- <span data-ttu-id="d861d-191">其余部分将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d861d-191">The rest is ignored.</span></span>


<span data-ttu-id="d861d-192">不遵循此格式的邮件将不会在提交门户中正确显示。</span><span class="sxs-lookup"><span data-stu-id="d861d-192">Messages that don't follow this format will not display properly in the Submissions portal.</span></span>
