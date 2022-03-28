---
title: 提高威胁防护Microsoft 365 商业高级版
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- admindeeplinkMAC
- admindeeplinkEXCHANGE
- admindeeplinkSPO
search.appverid:
- BCS160
- MET150
description: 获取有关提高企业防护级别的Microsoft 365 商业高级版
ms.openlocfilehash: c6533b966587235b8f29c1ce53bd9d5579b23b9c
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403800"
---
# <a name="increase-threat-protection-for-microsoft-365-business-premium"></a>提高威胁防护Microsoft 365 商业高级版

在此目标中，使用安全机制增强Microsoft 365 商业高级版。 保护组织免受网络钓鱼、恶意软件和其他威胁至关重要。 这些建议尤其适用于政治宣传活动、法律办公室和医疗保健机构，它们增加了安全性需求。

## <a name="start-with-secure-score"></a>从安全分数开始

Microsoft 安全分数根据常规活动和安全设置分析组织的安全性，并分配分数。 记下当前分数，然后执行本文中建议的操作以提高分数。 目标是始终注意并尝试提高分数。

有关详细信息，请参阅 [Microsoft 安全分数](../security/defender/microsoft-secure-score.md)。

## <a name="review-and-apply-preset-security-policies"></a>查看和应用预设安全策略

你的订阅 [包括预设安全策略](../security/office-365-security/preset-security-policies.md) ，这些策略使用建议的反垃圾邮件、反恶意软件和防钓鱼保护设置。 默认情况下，内置保护已启用;请考虑应用标准或严格保护来增强安全性。 

预设安全策略包括：

- 配置文件，用于确定保护级别
- 策略 (如反垃圾邮件、反恶意软件、防钓鱼、保险箱附件保险箱链接) 
- 策略 (组、用户或域等，用于接收策略和任何) 

下表总结了保护级别和预设策略类型。

| 保护级别 | 说明 |
|:---|:---|
| **标准保护** <br/> (*大多数企业推荐)* | 标准保护使用适合大多数用户的基线配置文件 <br/><br/>它包括反垃圾邮件、反恶意软件、反网络钓鱼、欺骗设置、模拟设置、保险箱链接保险箱附件策略。  |
| **严格保护**  | 严格保护包含与标准保护相同类型的策略，但具有更严格的设置。 如果你的企业必须满足其他安全要求或法规，请考虑对优先用户或高价值目标应用严格保护。 |
| **内置保护** | 防范电子邮件中的恶意链接和附件。 默认情况下启用并应用于所有用户。  |

可以指定用户、组和域以接收预设策略，也可以定义某些例外，但无法自行更改预设策略。

还可以为自定义设置创建自己的安全策略，以满足公司的需求。




<!--https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide


## Raise the level of protection against malware in mail

Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware. To bump up malware protection in email:

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a> and sign in with your admin account credentials.

2. In the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.

3. Double-click the default policy to edit this company-wide policy.

4. Click **Settings**.

5. Under **Common Attachment Types Filter**, select **On**. The file types that are blocked are listed in the window directly below this control. Make sure you add these filetypes:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   You can add or delete file types later, if needed.

6. Click **Save.**

For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).

## Protect against ransomware

Ransomware restricts access to data by encrypting files or locking computer screens. It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.

You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.

In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros. Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.

To create a mail transport rule:

1. Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.

2. In the **mail flow** category, click **rules**.

3. Click **+**, and then click **Create a new rule**.

4. Click **More options** at the bottom of the dialog box to see the full set of options.

5. Apply the settings in the following table for the rule. Leave the rest of the settings at the default, unless you want to change them.

6. Click **Save**.

|Setting|Warn users before opening attachments of Office files|
|---|---|
|Name|Anti-ransomware rule: warn users|
|Apply this rule if . . .|Any attachment . . . file extension matches . . .|
|Specify words or phrases|Add these file types: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Do the following . . .|Notify the recipient with a message|
|Provide message text|Do not open these types of files from people you do not know because they might contain macros with malicious code.|

For more information, see:

- [Ransomware: how to reduce risk](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restore your OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## Stop auto-forwarding for email

Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email. This can happen even without the user's awareness. You can prevent this from happening by configuring a mail flow rule.

To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, click **Admin centers** \> **Exchange**.

2. In the **mail flow** category, click **rules**.

3. Click **+**, and then click **Create a new rule**.

4. Click **More options** at the bottom of the dialog box to see the full set of options.

5. Apply the settings in the following table. Leave the rest of the settings at the default, unless you want to change them.

6. Click **Save**.

|Setting|Warn users before opening attachments of Office files|
|---|---|
|Name|Prevent auto forwarding of email to external domains|
|Apply this rule if ...|The sender . . . is external/internal . . . Inside the organization|
|Add condition|The message properties . . . include the message type . . . Auto-forward|
|Do the following ...|Block the message . . . reject the message and include an explanation.|
|Provide message text|Auto-forwarding email outside this organization is prevented for security reasons.|

## Protect your email from phishing attacks

If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection. Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks. If you haven't configured a custom domain, you don't need to do this.

We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.

To create an anti-phishing policy in Defender for Office 365, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:

1. Go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a>.

2. In the left navigation pane, under **Threat management**, choose **Policy**.

3. On the **Policy** page, choose **Anti-phishing**.

4. On the **Anti-phishing** page, select **+ Create**. A wizard launches that steps you through defining your anti-phishing policy.

5. Specify the name, description, and settings for your policy as recommended in the chart below. For more information, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.

|Setting or option|Recommended setting|
|---|---|
|Name|Domain and most valuable staff|
|Description|Ensure most important staff and our domain are not being impersonated.|
|Add users to protect|Select **+ Add a condition, The recipient is**. Type user names or enter the email address of the business owners, partners, or candidate, managers, and other important staff members. You can add up to 20 internal and external addresses that you want to protect from impersonation.|
|Add domains to protect|Select **+ Add a condition, The recipient domain is**. Enter the custom domain associated with your Microsoft 365 subscription, if you defined one. You can enter more than one domain.|
|Choose actions|If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*. <br/> If email is sent by an impersonated domain: Choose **Quarantine message**.|
|Mailbox intelligence|By default, mailbox intelligence is selected when you create a new anti-phishing policy. Leave this setting **On** for best results.|
|Add trusted senders and domains|Here you can add your own domain, or any other trusted domains.|
|Applied to|Select **The recipient domain is**. Under **Any of these**, select **Choose**. Select **+ Add**. Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**. Select **Done**.|

For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## Protect against malicious attachments, files, and links with Defender for Office 365

![Banner that point to https://aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)

First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on. Turn on the toggle next to the text **The new admin center**.

   ![The new admin center preview on.](../media/previewon.png)

If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center. See [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and [Set up Safe Links in the Security & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).

1. In the left nav, choose **Setup**.
2. On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.

   ![Choose View on the Increase protection from advanced threats.](../media/startatp.png)

3. On the **Increase protection from advanced threats** page, choose **Get started**.
4. On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.
    
   Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.

   ![Select all check boxes in Increase protection from advanced threats.](../media/setatp.png)

5. Choose **Create policies** to turn on Safe Attachments and Safe Links.

### Set up Safe Attachments in the Security & Compliance Center

People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more. It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message. Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default. We recommend that you create a new rule to begin using this protection. This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.

To create a Safe Attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:

1. Go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a> and sign in with your admin account.

2. In the left navigation pane, under **Threat management**, choose **Policy**.

3. On the Policy page, choose **Safe Attachments**.

4. On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.

5. Select **+** to create a new policy.

6. Apply the settings in the following table.

7. After you review your settings, choose **Create this policy** or **Save**, as appropriate.

|Setting or option|Recommended setting|
|---|---|
|Name|Block current and future emails with detected malware.|
|Description|Block current and future emails and attachments with detected malware.|
|Save attachments unknown malware response|Select **Block - Block the current and future emails and attachments with detected malware**.|
|Redirect attachment on detection|Enable redirection (select this box) <br/> Enter the admin account or a mailbox setup for quarantine. <br/> Apply the above selection if malware scanning for attachments times out or error occurs (select this box).|
|Applied to|The recipient domain is . . . select your domain.|

For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

### Set up Safe Links in the Security & Compliance Center

Hackers sometimes hide malicious websites in links in email or other files. Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents. Protection is defined through Safe Links policies.

We recommend that you do the following:

- Modify the default policy to increase protection.

- Add a new policy targeted to all recipients in your domain.

To set up Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:

1. Go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 Security & Compliance Center</a> and sign in with your admin account.

2. In the left navigation pane, under **Threat management**, choose **Policy**.

3. On the Policy page, choose **Safe Links**.

To modify the default policy:

1. On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.

2. Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.

3. Click **Save**.

To create a new policy targeted to all recipients in your domain:

1. On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.

2. Apply the settings listed in the following table.

3. Click **Save**.

|Setting or option|Recommended setting|
|---|---|
|Name|Safe links policy for all recipients in the domain|
|Select the action for unknown potentially malicious URLs in messages|Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Use Safe Attachments to scan downloadable content|Select this box.|
|Applied to|The recipient domain is . . . select your domain.|

For more information, see [Safe Links in Defender for Office 365](../security/office-365-security/safe-links.md).

-->

## <a name="turn-on-the-unified-audit-log"></a>打开统一审核日志

在安全与审核日志中心启用 & 搜索后，可以在日志中保留管理员和其他用户活动并搜索。

必须分配有"审核日志"角色Exchange Online，审核日志订阅中打开或关闭Microsoft 365搜索。 默认情况下，此角色分配给管理中心中"权限"页上的"合规性管理"<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange组</a>。 默认情况下，Microsoft 365中的全局管理员是此组的成员。

1. 若要打开"审核日志"，请转到 管理中心 ，<https://admin.microsoft.com>然后选择左侧导航中"管理中心"下的"安全"。
2. On the **Microsoft 365 Security** page， choose **More resources**， and then **Open** on the **Office 365 Security & Compliance Center** card.

    ![在安全与合规&选择"打开"。](../media/gotosecandcomp.png)
3. 在"安全性和合规性"页上，选择" **搜索"** ，然后选择" **审核日志搜索"**。
4. 在"审核日志搜索"页 **的顶部** ，选择 **"启用审核"**。

启用此功能后，你可以搜索文件、文件夹和许多活动。 有关详细信息，请参阅 [搜索审核日志](../compliance/search-the-audit-log-in-security-and-compliance.md)。

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>为文件和文件夹调整SharePoint OneDrive匿名共享设置

 (默认匿名链接过期时间更改为 14 天，将默认共享类型更改为"特定人员") 若要更改用户和用户OneDrive SharePoint：

1. 转到 管理中心 ，<https://admin.microsoft.com>然后选择左侧导航 **SharePoint管理****中心** 下选择" 管理中心"。
2. 在管理SharePoint，转到"策略 **"**<a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**"共享**</a>\>"。
3. 在"共享"页面上的"文件和文件夹链接"下，选择"特定人员"，在"任何人"链接的高级设置下，选择"这些链接必须在此天数内过期"，然后键入 14 (或您希望将链接生存期限制为) 的另一天数。

   ![选择"特定人员"，将链接过期时间设置为 14 天。](../media/anyonelinks.png)


## <a name="activity-alerts"></a>活动警报

可以使用活动警报跟踪管理员和用户活动，并检测组织中恶意软件和数据丢失防护事件。 你的订阅包括一组默认策略，但你也可以创建自定义策略。 有关详细信息，请参阅 [警报策略](../compliance/alert-policies.md)。 例如，如果您将一个重要文件存储在SharePoint您不希望任何人在外部共享，您可以创建一个通知，提醒您是否有人共享它。

下图显示了此策略中包含的默认Microsoft 365。

![默认警报策略包含在Microsoft 365。](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>禁用或管理日历共享

您可以阻止组织成员共享其日历，也可以管理他们可以共享的信息。 例如，您可以将共享限制为仅忙/闲时间。

1. 转到 管理中心 ，<https://admin.microsoft.com>**然后选择 设置** \> **Org 设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Services**</a>。

1. 选择 **"** 日历"，然后选择组织成员是否可以与外部拥有日历Office 365或Exchange共享日历。

   如果选择"与任何人共享"选项，还可以决定仅共享忙/闲信息。

3. 选择 **页面** 底部的"保存更改"。

   下图显示了不允许的日历共享。

   ![显示不允许的外部日历共享的屏幕截图。](../media/nocalendarsharing.png)

   下图显示了通过仅包含忙/闲信息的电子邮件链接允许日历共享时的设置。

   ![与任何人共享日历忙/闲的屏幕截图。](../media/sharefreebusy.png)

如果允许用户共享其日历，请参阅以下说明[，了解如何从](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) Outlook 网页版。

