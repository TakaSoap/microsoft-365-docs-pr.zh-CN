---
title: 从“受限的用户”门户中删除被阻止的用户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Office 365 中从“受限的用户”门户中删除用户。 用户之所以被添加到“受限的用户”门户是因为发送出站垃圾邮件，这通常是由于帐户遭入侵所致。
ms.openlocfilehash: f1f869a81ef5b01733bf9060117cf3706094b961
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895199"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="111a8-104">在 Office 365 中从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="111a8-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="111a8-105">如果某用户超过[服务限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)中指定的出站发送限制之一，此用户就会被限制发送电子邮件，但仍可以接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="111a8-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="111a8-106">此用户会被添加到 Office 365 安全与合规中心内的“受限的用户”门户。</span><span class="sxs-lookup"><span data-stu-id="111a8-106">The user is added to the Restricted Users portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="111a8-107">如果此用户试图发送电子邮件，邮件就会以未送达报告（亦称为“NDR”或“退回邮件”）形式返回，并显示错误代码 [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和以下文本：</span><span class="sxs-lookup"><span data-stu-id="111a8-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="111a8-108">“你的邮件无法送达，因为系统认为你不是有效的发件人。</span><span class="sxs-lookup"><span data-stu-id="111a8-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="111a8-109">这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="111a8-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="111a8-110">请联系电子邮件管理员获取帮助。</span><span class="sxs-lookup"><span data-stu-id="111a8-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="111a8-111">远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。</span><span class="sxs-lookup"><span data-stu-id="111a8-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="111a8-112">管理员可以从安全与合规中心内的“受限的发件人”门户中或使用 Exchange Online PowerShell 删除用户。</span><span class="sxs-lookup"><span data-stu-id="111a8-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="111a8-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="111a8-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="111a8-114">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="111a8-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="111a8-115">若要直接转到“受限的用户”\*\*\*\* 页，请访问 <https://protection.office.com/restrictedusers>。</span><span class="sxs-lookup"><span data-stu-id="111a8-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="111a8-116">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="111a8-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="111a8-117">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="111a8-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="111a8-118">必须是“组织管理”\*\*\*\* 或“安全管理员”\*\*\*\* 角色组的成员，才能从“受限的用户”门户中删除用户。</span><span class="sxs-lookup"><span data-stu-id="111a8-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="111a8-119">必须是“安全信息读取者”\*\*\*\* 角色组的成员，才能获得对“受限的用户”门户的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="111a8-119">For read-only access to the Restricted Users portal, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="111a8-120">若要详细了解安全与合规中心内的角色组，请参阅 [Office 365 安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="111a8-120">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="111a8-121">发件人超过出站电子邮件限制是帐户遭入侵的标志。</span><span class="sxs-lookup"><span data-stu-id="111a8-121">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="111a8-122">请务必先按照必需步骤操作来重新获得对帐户的控制，再从“受限的用户”门户中删除用户。</span><span class="sxs-lookup"><span data-stu-id="111a8-122">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="111a8-123">有关详细信息，请参阅[在 Office 365 中响应遭入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="111a8-123">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="111a8-124">使用安全与合规中心从“受限的用户”列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="111a8-124">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="111a8-125">在安全与合规中心内，依次转到“威胁管理”\*\*\*\*\>“审阅”\*\*\*\*\>“受限的用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="111a8-125">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="111a8-126">查找并选择要取消阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="111a8-126">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="111a8-127">在“操作”\*\*\*\* 列中，单击“取消阻止”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="111a8-127">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="111a8-128">一个飞出窗口将转到有关其发送受限的帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="111a8-128">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="111a8-129">应按照建议进行操作，确保在帐户实际遭到破坏的情况下采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="111a8-129">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="111a8-130">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="111a8-130">Click **Next** when done.</span></span>

4. <span data-ttu-id="111a8-131">下一个屏幕包含可帮助防止以后遭到破坏的建议。</span><span class="sxs-lookup"><span data-stu-id="111a8-131">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="111a8-132">启用多重身份验证 (MFA) 和更改密码是一种很好的防御措施。</span><span class="sxs-lookup"><span data-stu-id="111a8-132">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="111a8-133">完成后，单击 **“解锁用户”**。</span><span class="sxs-lookup"><span data-stu-id="111a8-133">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="111a8-134">单击 **“是”** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="111a8-134">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="111a8-135">移除限制可能需要 30 分钟或更长时间。</span><span class="sxs-lookup"><span data-stu-id="111a8-135">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="111a8-136">验证用于受限的用户的警报设置</span><span class="sxs-lookup"><span data-stu-id="111a8-136">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="111a8-137">默认警报策略“被限制发送电子邮件的用户”\*\*\*\* 会在用户被阻止发送出站邮件时自动通知管理员。</span><span class="sxs-lookup"><span data-stu-id="111a8-137">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="111a8-138">可以验证这些设置，并添加其他要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="111a8-138">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="111a8-139">若要详细了解警报策略，请参阅[安全与合规中心内的警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="111a8-139">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="111a8-140">必须启用审核日志搜索，这样警报才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="111a8-140">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="111a8-141">有关详细信息，请参阅[启用或禁用 Office 365 审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="111a8-141">For more information, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="111a8-142">在安全与合规中心内，依次转到“警报”\*\*\*\*\>“警报策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="111a8-142">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="111a8-143">查找并选择“被限制发送电子邮件的用户”\*\*\*\* 警报。</span><span class="sxs-lookup"><span data-stu-id="111a8-143">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="111a8-144">在随即显示的浮出控件中，验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="111a8-144">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="111a8-145">**状态**：验证此警报是否已启用 ![开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)。</span><span class="sxs-lookup"><span data-stu-id="111a8-145">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="111a8-146">**电子邮件收件人**：单击“编辑”\*\*\*\*，然后在随即显示的“编辑收件人”\*\*\*\* 浮出控件中验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="111a8-146">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="111a8-147">**发送电子邮件通知**：验证此复选框是否已选中（“开”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="111a8-147">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="111a8-148">**电子邮件收件人**：默认值为“TenantAdmins”\*\*\*\*（表示“全局管理员”\*\*\*\* 成员）。</span><span class="sxs-lookup"><span data-stu-id="111a8-148">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="111a8-149">若要添加其他收件人，请单击此框的空白区域。</span><span class="sxs-lookup"><span data-stu-id="111a8-149">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="111a8-150">此时，收件人列表会显示，你可以键入名称来筛选并选择收件人。</span><span class="sxs-lookup"><span data-stu-id="111a8-150">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="111a8-151">若要从此框中删除现有收件人，请单击其名称旁边的 ![“删除”图标](../../media/scc-remove-icon.png)可。</span><span class="sxs-lookup"><span data-stu-id="111a8-151">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="111a8-152">**每日通知限制**：默认值为“无限制”\*\*\*\*，但你可以选择每日通知数上限。</span><span class="sxs-lookup"><span data-stu-id="111a8-152">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="111a8-153">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="111a8-153">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="111a8-154">返回到“被限制发送电子邮件的用户”\*\*\*\* 浮出控件，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="111a8-154">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="111a8-155">使用 Exchange Online PowerShell 查看和删除“受限的用户”列表中的用户</span><span class="sxs-lookup"><span data-stu-id="111a8-155">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="111a8-156">若要查看被限制发送电子邮件的用户列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="111a8-156">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="111a8-157">若要查看特定用户的详细信息，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="111a8-157">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="111a8-158">若要详细了解语法和参数，请参阅 [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="111a8-158">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-blockedsenderaddress).</span></span>

<span data-ttu-id="111a8-159">若要从“受限的用户”列表中删除用户，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="111a8-159">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="111a8-160">若要详细了解语法和参数，请参阅 [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="111a8-160">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-blockedsenderaddress).</span></span>
