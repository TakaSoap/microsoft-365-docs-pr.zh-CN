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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43312ee6eff9b56ac4faf8173666a1ba79b9e067
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726727"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="9617d-104">在 Office 365 中从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="9617d-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="9617d-105">如果某用户超过[服务限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)中指定的出站发送限制之一，此用户就会被限制发送电子邮件，但仍可以接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9617d-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="9617d-106">此用户会被添加到安全与合规中心内的“受限用户”门户。</span><span class="sxs-lookup"><span data-stu-id="9617d-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="9617d-107">如果此用户试图发送电子邮件，邮件就会以未送达报告（亦称为“NDR”或“退回邮件”）形式返回，并显示错误代码 [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和以下文本：</span><span class="sxs-lookup"><span data-stu-id="9617d-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="9617d-108">“你的邮件无法送达，因为系统认为你不是有效的发件人。</span><span class="sxs-lookup"><span data-stu-id="9617d-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="9617d-109">这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9617d-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="9617d-110">请联系电子邮件管理员获取帮助。</span><span class="sxs-lookup"><span data-stu-id="9617d-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="9617d-111">远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。</span><span class="sxs-lookup"><span data-stu-id="9617d-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="9617d-112">管理员可以从安全与合规中心内的“受限的发件人”门户中或使用 Exchange Online PowerShell 删除用户。</span><span class="sxs-lookup"><span data-stu-id="9617d-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9617d-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9617d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9617d-114">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="9617d-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9617d-115">若要直接转到“受限的用户”\*\*\*\* 页，请访问 <https://protection.office.com/restrictedusers>。</span><span class="sxs-lookup"><span data-stu-id="9617d-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="9617d-116">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9617d-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9617d-117">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="9617d-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="9617d-118">若要从“受限的用户”门户中删除用户，你必须是以下任一角色组的成员：</span><span class="sxs-lookup"><span data-stu-id="9617d-118">To remove users from the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="9617d-119">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="9617d-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="9617d-120">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="9617d-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="9617d-121">若要以只读方式访问“受限的用户”门户，你必须是以下任一角色组的成员：</span><span class="sxs-lookup"><span data-stu-id="9617d-121">For read-only access to the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="9617d-122">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="9617d-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="9617d-123">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="9617d-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="9617d-124">发件人超过出站电子邮件限制是帐户遭入侵的标志。</span><span class="sxs-lookup"><span data-stu-id="9617d-124">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="9617d-125">请务必先按照必需步骤操作来重新获得对帐户的控制，再从“受限的用户”门户中删除用户。</span><span class="sxs-lookup"><span data-stu-id="9617d-125">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="9617d-126">有关详细信息，请参阅[在 Office 365 中响应遭入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="9617d-126">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="9617d-127">使用安全与合规中心从“受限的用户”列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="9617d-127">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="9617d-128">在安全与合规中心内，依次转到“威胁管理”\*\*\*\*\>“审阅”\*\*\*\*\>“受限的用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9617d-128">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="9617d-129">查找并选择要取消阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="9617d-129">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="9617d-130">在“操作”\*\*\*\* 列中，单击“取消阻止”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9617d-130">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="9617d-131">一个飞出窗口将转到有关其发送受限的帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9617d-131">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="9617d-132">应按照建议进行操作，确保在帐户实际遭到破坏的情况下采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="9617d-132">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="9617d-133">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="9617d-133">Click **Next** when done.</span></span>

4. <span data-ttu-id="9617d-134">下一个屏幕包含可帮助防止以后遭到破坏的建议。</span><span class="sxs-lookup"><span data-stu-id="9617d-134">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="9617d-135">启用多重身份验证 (MFA) 和更改密码是一种很好的防御措施。</span><span class="sxs-lookup"><span data-stu-id="9617d-135">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="9617d-136">完成后，单击 **“解锁用户”**。</span><span class="sxs-lookup"><span data-stu-id="9617d-136">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="9617d-137">单击 **“是”** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="9617d-137">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9617d-138">移除限制可能需要 30 分钟或更长时间。</span><span class="sxs-lookup"><span data-stu-id="9617d-138">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="9617d-139">验证用于受限的用户的警报设置</span><span class="sxs-lookup"><span data-stu-id="9617d-139">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="9617d-140">默认警报策略“被限制发送电子邮件的用户”\*\*\*\* 会在用户被阻止发送出站邮件时自动通知管理员。</span><span class="sxs-lookup"><span data-stu-id="9617d-140">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="9617d-141">可以验证这些设置，并添加其他要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="9617d-141">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="9617d-142">若要详细了解警报策略，请参阅[安全与合规中心内的警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9617d-142">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9617d-143">必须启用审核日志搜索，这样警报才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="9617d-143">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="9617d-144">有关详细信息，请参阅[启用或禁用审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="9617d-144">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="9617d-145">在安全与合规中心内，依次转到“警报”\*\*\*\*\>“警报策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9617d-145">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="9617d-146">查找并选择“被限制发送电子邮件的用户”\*\*\*\* 警报。</span><span class="sxs-lookup"><span data-stu-id="9617d-146">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="9617d-147">在随即显示的浮出控件中，验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="9617d-147">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="9617d-148">**状态**：验证此警报是否已启用 ![开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)。</span><span class="sxs-lookup"><span data-stu-id="9617d-148">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="9617d-149">**电子邮件收件人**：单击“编辑”\*\*\*\*，然后在随即显示的“编辑收件人”\*\*\*\* 浮出控件中验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="9617d-149">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="9617d-150">**发送电子邮件通知**：验证此复选框是否已选中（“开”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="9617d-150">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="9617d-151">**电子邮件收件人**：默认值为“TenantAdmins”\*\*\*\*（表示“全局管理员”\*\*\*\* 成员）。</span><span class="sxs-lookup"><span data-stu-id="9617d-151">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="9617d-152">若要添加其他收件人，请单击此框的空白区域。</span><span class="sxs-lookup"><span data-stu-id="9617d-152">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="9617d-153">此时，收件人列表会显示，你可以键入名称来筛选并选择收件人。</span><span class="sxs-lookup"><span data-stu-id="9617d-153">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="9617d-154">若要从此框中删除现有收件人，请单击其名称旁边的 ![“删除”图标](../../media/scc-remove-icon.png)可。</span><span class="sxs-lookup"><span data-stu-id="9617d-154">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="9617d-155">**每日通知限制**：默认值为“无限制”\*\*\*\*，但你可以选择每日通知数上限。</span><span class="sxs-lookup"><span data-stu-id="9617d-155">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="9617d-156">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9617d-156">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="9617d-157">返回到“被限制发送电子邮件的用户”\*\*\*\* 浮出控件，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9617d-157">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="9617d-158">使用 Exchange Online PowerShell 查看和删除“受限的用户”列表中的用户</span><span class="sxs-lookup"><span data-stu-id="9617d-158">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="9617d-159">若要查看被限制发送电子邮件的用户列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9617d-159">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="9617d-160">若要查看特定用户的详细信息，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9617d-160">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="9617d-161">若要详细了解语法和参数，请参阅 [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="9617d-161">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="9617d-162">若要从“受限的用户”列表中删除用户，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9617d-162">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="9617d-163">若要详细了解语法和参数，请参阅 [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="9617d-163">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
