---
title: 响应遭到入侵的电子邮件帐户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用 Microsoft 365 中的工具来识别并响应遭到入侵的电子邮件帐户。
ms.openlocfilehash: 5d5e5360e9851aee8eab27fc7c39e266e0332411
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659881"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="cd430-103">响应遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="cd430-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cd430-104">**摘要** 了解如何识别并响应 Microsoft 365 中遭到入侵的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="cd430-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="cd430-105">什么是 Microsoft 365 中遭到入侵的电子邮件帐户？</span><span class="sxs-lookup"><span data-stu-id="cd430-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="cd430-106">通过使用凭据（例如用户名和密码或 PIN）来控制对 Microsoft 365 邮箱、数据和其他服务的访问。</span><span class="sxs-lookup"><span data-stu-id="cd430-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="cd430-107">如果除预期用户以外的其他人窃取了这些凭据，则被盗的凭据将视为遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="cd430-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="cd430-108">借助这些凭据，攻击者能够以原始用户的身份登录并执行非法操作。</span><span class="sxs-lookup"><span data-stu-id="cd430-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="cd430-109">通过使用窃取的凭据，攻击者可以访问用户的 Microsoft 365 邮箱、SharePoint 文件夹或用户 OneDrive 中的文件。</span><span class="sxs-lookup"><span data-stu-id="cd430-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="cd430-110">其中一种常见操作是攻击者以原始用户的身份将电子邮件发送给组织内外的收件人。</span><span class="sxs-lookup"><span data-stu-id="cd430-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="cd430-111">当攻击者通过电子邮件将数据发送给外部收件人时，这称为数据泄露。</span><span class="sxs-lookup"><span data-stu-id="cd430-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="cd430-112">遭到入侵的 Microsoft 电子邮件帐户的症状</span><span class="sxs-lookup"><span data-stu-id="cd430-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="cd430-113">用户可能会注意到并报告其 Microsoft 365 邮箱中的异常活动。</span><span class="sxs-lookup"><span data-stu-id="cd430-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="cd430-114">下面是一些常见症状：</span><span class="sxs-lookup"><span data-stu-id="cd430-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="cd430-115">可疑活动，例如丢失或删除的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cd430-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="cd430-116">其他用户可能会收到来自遭到入侵的帐户的电子邮件，而发件人的“**已发送邮件**”文件夹中没有相应的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cd430-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="cd430-117">存在并非由预期用户或管理员创建的收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="cd430-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="cd430-118">这些规则可以自动将电子邮件转发到未知地址，或将其移动到“**便笺**”、“**垃圾邮件**”或“**RSS 订阅**”文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd430-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="cd430-119">在全局地址列表中，用户的显示名称可能已发生更改。</span><span class="sxs-lookup"><span data-stu-id="cd430-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="cd430-120">用户的邮箱被阻止发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cd430-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="cd430-121">Microsoft Outlook 或 Outlook 网页版（以前称为 Outlook Web App）中的“已发送邮件”或“已删除邮件”文件夹包含常见的黑客帐户邮件，例如“我被困在伦敦，请给我汇款”。</span><span class="sxs-lookup"><span data-stu-id="cd430-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="cd430-122">异常的个人资料更改，例如更新了姓名、电话号码或邮政编码。</span><span class="sxs-lookup"><span data-stu-id="cd430-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="cd430-123">异常的凭据更改，例如多次要求进行密码更改。</span><span class="sxs-lookup"><span data-stu-id="cd430-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="cd430-124">最近添加了邮件转发功能。</span><span class="sxs-lookup"><span data-stu-id="cd430-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="cd430-125">最近添加了异常的签名，例如假银行签名或处方药签名。</span><span class="sxs-lookup"><span data-stu-id="cd430-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="cd430-126">如果用户报告了上述任何症状，你应该进一步展开调查。</span><span class="sxs-lookup"><span data-stu-id="cd430-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="cd430-127">Microsoft 365 安全与合规中心和 Azure 门户提供了各种工具，可帮助你对疑似遭到入侵的用户帐户的活动展开调查。</span><span class="sxs-lookup"><span data-stu-id="cd430-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="cd430-128">**安全与合规中心内的统一审核日志**：通过筛选从可疑活动发生前到当前日期的日期范围内的结果，审阅可疑帐户的所有活动。</span><span class="sxs-lookup"><span data-stu-id="cd430-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="cd430-129">不要在搜索过程中筛选活动。</span><span class="sxs-lookup"><span data-stu-id="cd430-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="cd430-130">**EAC 中的管理员审核日志**：在 Exchange Online 中，可以使用 Exchange 管理中心 (EAC) 搜索和查看管理员审核日志中的条目。</span><span class="sxs-lookup"><span data-stu-id="cd430-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="cd430-131">管理员审核日志根据管理员和分配有管理权限的用户执行的 Exchange Online PowerShell cmdlet 来记录特定操作。</span><span class="sxs-lookup"><span data-stu-id="cd430-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="cd430-132">管理员审核日志中的条目向您提供有关所运行的 cmdlet、所使用的参数、运行 cmdlet 的用户以及受影响的对象的相关信息。</span><span class="sxs-lookup"><span data-stu-id="cd430-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="cd430-133">**Azure AD 门户中的 Azure AD 登录日志和其他风险报告**：检查以下列中的值：</span><span class="sxs-lookup"><span data-stu-id="cd430-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="cd430-134">查看 IP 地址</span><span class="sxs-lookup"><span data-stu-id="cd430-134">Review IP address</span></span>
  - <span data-ttu-id="cd430-135">登录位置</span><span class="sxs-lookup"><span data-stu-id="cd430-135">sign-in locations</span></span>
  - <span data-ttu-id="cd430-136">登录时间</span><span class="sxs-lookup"><span data-stu-id="cd430-136">sign-in times</span></span>
  - <span data-ttu-id="cd430-137">登录成功或失败</span><span class="sxs-lookup"><span data-stu-id="cd430-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="cd430-138">如何保护和恢复疑似遭到入侵的 Microsoft 365 帐户和邮箱的电子邮件功能</span><span class="sxs-lookup"><span data-stu-id="cd430-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="cd430-139">即使你重新获得对帐户的访问权限，攻击者也可能添加了后门条目，这让攻击者能够恢复对该帐户的控制权。</span><span class="sxs-lookup"><span data-stu-id="cd430-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="cd430-140">你必须执行以下所有步骤才能重新获得对帐户的访问权限，以便更快地确保劫持者无法继续控制你的帐户。</span><span class="sxs-lookup"><span data-stu-id="cd430-140">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="cd430-141">这些步骤可帮助你删除劫持者可能已添加到你帐户的任何后门条目。</span><span class="sxs-lookup"><span data-stu-id="cd430-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="cd430-142">执行这些步骤后，我们建议你运行病毒扫描以确保你的计算机不会遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="cd430-142">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="cd430-143">步骤 1 重置用户密码</span><span class="sxs-lookup"><span data-stu-id="cd430-143">Step 1 Reset the user's password</span></span>

<span data-ttu-id="cd430-144">按照[为他人重置商业版密码](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password)中的程序操作。</span><span class="sxs-lookup"><span data-stu-id="cd430-144">Follow the procedures in [Reset a business password for someone](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="cd430-145">不要通过电子邮件将新密码发送给预期用户，因为此时攻击者仍可以访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd430-145">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="cd430-146">确保密码为强密码，并且包含大写和小写字母、至少一个数字和至少一个特殊字符。</span><span class="sxs-lookup"><span data-stu-id="cd430-146">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="cd430-147">不要重复使用过去五个密码中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="cd430-147">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="cd430-148">即使密码历史记录要求允许你重复使用最近使用过的密码，你也应该选择攻击者无法猜到的密码。</span><span class="sxs-lookup"><span data-stu-id="cd430-148">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="cd430-149">如果你的本地标识已与 Microsoft 365 联合，则必须在本地更改密码，然后通知管理员帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="cd430-149">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="cd430-150">务必更新应用密码。</span><span class="sxs-lookup"><span data-stu-id="cd430-150">Be sure to update app passwords.</span></span> <span data-ttu-id="cd430-151">重置用户帐户密码后，不会自动撤消应用密码。</span><span class="sxs-lookup"><span data-stu-id="cd430-151">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="cd430-152">用户应删除现有应用程序密码并创建新密码。</span><span class="sxs-lookup"><span data-stu-id="cd430-152">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="cd430-153">有关说明，请参阅[从其他安全验证页面创建和删除应用密码](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)。</span><span class="sxs-lookup"><span data-stu-id="cd430-153">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="cd430-154">强烈建议启用多重身份验证 (MFA)，以防发生泄漏，特别是对于拥有管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="cd430-154">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="cd430-155">若要了解有关 MFA 的详细信息，请转到[设置多重身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="cd430-155">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="cd430-156">步骤 2 删除可疑的电子邮件转发地址</span><span class="sxs-lookup"><span data-stu-id="cd430-156">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="cd430-157">在 <https://admin.microsoft.com> 打开 Microsoft 365 管理中心，</span><span class="sxs-lookup"><span data-stu-id="cd430-157">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="cd430-158">转到“**用户**”\>“**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-158">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="cd430-159">查找有问题的用户帐户，然后选择用户（行），无需选中复选框。</span><span class="sxs-lookup"><span data-stu-id="cd430-159">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="cd430-160">在出现的详细信息浮出控件中，选择“**邮件**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="cd430-160">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="cd430-161">如果“**电子邮件转发**”部分中的值为“**已应用**”，请单击“**管理电子邮件转发**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-161">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="cd430-162">在出现的“**管理电子邮件转发**”浮出控件中，清除“**转发发送至此邮箱的所有电子邮件**”，然后单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-162">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="cd430-163">步骤 3 禁用任何可疑的收件箱规则</span><span class="sxs-lookup"><span data-stu-id="cd430-163">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="cd430-164">使用 Outlook 网页版登录用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd430-164">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="cd430-165">单击齿轮图标，然后单击“**邮件**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-165">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="cd430-166">单击“**收件箱和整理规则**”并查看规则。</span><span class="sxs-lookup"><span data-stu-id="cd430-166">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="cd430-167">禁用或删除可疑的规则。</span><span class="sxs-lookup"><span data-stu-id="cd430-167">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="cd430-168">步骤 4 取消阻止用户发送邮件</span><span class="sxs-lookup"><span data-stu-id="cd430-168">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="cd430-169">如果疑似遭到入侵的邮箱被非法用于发送垃圾电子邮件，则可能是该邮箱已被阻止发送邮件。</span><span class="sxs-lookup"><span data-stu-id="cd430-169">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="cd430-170">若要取消阻止邮箱发送邮件，请按照[发送垃圾电子邮件后，从受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)中的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="cd430-170">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="cd430-171">步骤 5（可选）阻止用户帐户登录</span><span class="sxs-lookup"><span data-stu-id="cd430-171">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd430-172">你可以阻止疑似遭到入侵的帐户登录，直到你认为重新启用访问权限是安全的。</span><span class="sxs-lookup"><span data-stu-id="cd430-172">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="cd430-173">打开 Microsoft 365 管理中心，然后转到“**用户**”\>“**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-173">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="cd430-174">查找并选择用户帐户，单击“![更多图标](../../media/ITPro-EAC-MoreOptionsIcon.png)”，然后选择“**编辑登录状态**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-174">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="cd430-175">出现“**阻止登录**”的窗格上，选择“**阻止此用户登录**”，然后单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-175">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="cd430-176">在 <admin.protection.outlook.com/ecp/> 中打开 Exchange 管理中心 (EAC)，然后转到 **“收件人”>“邮​​箱”**。</span><span class="sxs-lookup"><span data-stu-id="cd430-176">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="cd430-177">查找并选择用户。</span><span class="sxs-lookup"><span data-stu-id="cd430-177">Find and select the select the user.</span></span> <span data-ttu-id="cd430-178">在“详细信息”窗格，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-178">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="cd430-179">在“**电话和语音功能**”部分，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-179">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="cd430-180">选择“**禁用 Exchange ActiveSync**”，然后在出现的警告中单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-180">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="cd430-181">选择“**禁用适用于设备的 OWA**”，然后在出现的警告中单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-181">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="cd430-182">在 Outlook 网页版的“**电子邮件连接**”部分中，单击“**禁用**”，然后在出现的警告中单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-182">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="cd430-183">步骤 6（可选）从所有管理角色组中删除疑似遭到入侵的帐户</span><span class="sxs-lookup"><span data-stu-id="cd430-183">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="cd430-184">在帐户受到保护后，可以恢复管理角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="cd430-184">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="cd430-185">使用全局管理员帐户登录：</span><span class="sxs-lookup"><span data-stu-id="cd430-185">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="cd430-186">在 Microsoft 365 管理中心，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-186">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="cd430-187">转到“**用户**”\>“**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-187">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="cd430-188">查找并选择用户帐户，单击“![更多图标](../../media/ITPro-EAC-MoreOptionsIcon.png)”，然后选择“**管理角色**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-188">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="cd430-189">删除分配给该帐户的任何管理角色。</span><span class="sxs-lookup"><span data-stu-id="cd430-189">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="cd430-190">完成后，单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-190">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="cd430-191">在 <https://protection.office.com> 中的安全与合规中心，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-191">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="cd430-192">选择“**权限**”，在列表中选择每个角色组，然后在出现的详细信息弹出窗口的“**成员**”部分查找用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cd430-192">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="cd430-193">如果角色组包含用户帐户，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-193">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="cd430-194">a.</span><span class="sxs-lookup"><span data-stu-id="cd430-194">a.</span></span> <span data-ttu-id="cd430-195">单击“**成员**”旁的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-195">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="cd430-196">b.</span><span class="sxs-lookup"><span data-stu-id="cd430-196">b.</span></span> <span data-ttu-id="cd430-197">在出现的“**编辑选择成员**”浮出控件中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-197">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="cd430-198">c.</span><span class="sxs-lookup"><span data-stu-id="cd430-198">c.</span></span> <span data-ttu-id="cd430-199">在出现的“**选择成员**”浮出控件中，选择用户帐户，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-199">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="cd430-200">完成后，单击“**完成**”、“**保存**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-200">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="cd430-201">在 <admin.protection.outlook.com/ecp/> 的 EAC 中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-201">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="cd430-202">选择“**权限**”，手动选择每个角色组，然后在详细信息窗格的“**成员**”部分验证用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cd430-202">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="cd430-203">如果角色组包含用户帐户，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cd430-203">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="cd430-204">a.</span><span class="sxs-lookup"><span data-stu-id="cd430-204">a.</span></span> <span data-ttu-id="cd430-205">选择角色组，单击“**编辑**”![编辑图标](../../media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="cd430-205">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="cd430-206">b.</span><span class="sxs-lookup"><span data-stu-id="cd430-206">b.</span></span> <span data-ttu-id="cd430-207">在“**成员**”部分，选择用户帐户，然后单击“**删除**”![删除图标](../../media/ITPro-EAC-RemoveIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="cd430-207">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="cd430-208">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cd430-208">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="cd430-209">步骤 7（可选）其他预防措施</span><span class="sxs-lookup"><span data-stu-id="cd430-209">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="cd430-210">确保验证已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="cd430-210">Make sure that you verify your sent items.</span></span> <span data-ttu-id="cd430-211">你可能需要通知联系人列表中的人员你的帐户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="cd430-211">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="cd430-212">例如，攻击者可能会向他们要钱，谎称他们被困在另一个国家/地区并且需要钱，也可能会向他们发送病毒以便劫持其计算机。</span><span class="sxs-lookup"><span data-stu-id="cd430-212">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="cd430-213">将此 Exchange 帐户用作其备用电子邮件帐户的任何其他服务可能已遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="cd430-213">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="cd430-214">首先，为 Microsoft 365 订阅执行这些步骤，然后为其他帐户执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="cd430-214">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="cd430-215">确保你的联系信息（如电话号码和地址）正确无误。</span><span class="sxs-lookup"><span data-stu-id="cd430-215">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="cd430-216">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd430-216">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="cd430-217">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="cd430-217">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="cd430-218">使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="cd430-218">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="cd430-219">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="cd430-219">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="cd430-220">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="cd430-220">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="cd430-221">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="cd430-221">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="cd430-222">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="cd430-222">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="cd430-223">90 天后。</span><span class="sxs-lookup"><span data-stu-id="cd430-223">Beyond 90 days.</span></span> <span data-ttu-id="cd430-224">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="cd430-224">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd430-225">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd430-225">See also</span></span>

- [<span data-ttu-id="cd430-226">在 Microsoft 365 中检测并修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="cd430-226">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="cd430-227">Internet 犯罪投诉中心</span><span class="sxs-lookup"><span data-stu-id="cd430-227">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="cd430-228">证券交易委员会 -“网络钓鱼”诈骗</span><span class="sxs-lookup"><span data-stu-id="cd430-228">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="cd430-229">[使用报告消息加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)直接向 Microsoft 和你的管理员报告垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="cd430-229">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
