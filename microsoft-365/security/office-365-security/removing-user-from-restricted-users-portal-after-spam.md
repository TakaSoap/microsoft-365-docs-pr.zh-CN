---
title: 从“受限的用户”门户中删除被阻止的用户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Office 365 中从“受限的用户”门户中删除用户。 用户之所以被添加到“受限的用户”门户是因为发送出站垃圾邮件，这通常是由于帐户遭入侵所致。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2171e2465aa40e187f8104c7c0d2675562f115ce
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537867"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="77630-104">在 Office 365 中从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="77630-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="77630-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="77630-105">**Applies to**</span></span>
- [<span data-ttu-id="77630-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="77630-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="77630-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="77630-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="77630-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77630-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="77630-109">如果某用户超过[服务限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)中指定的出站发送限制之一，此用户就会被限制发送电子邮件，但仍可以接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77630-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="77630-110">此用户会被添加到安全与合规中心内的“受限用户”门户。</span><span class="sxs-lookup"><span data-stu-id="77630-110">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="77630-111">如果此用户试图发送电子邮件，邮件就会以未送达报告（亦称为“NDR”或“退回邮件”）形式返回，并显示错误代码 [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和以下文本：</span><span class="sxs-lookup"><span data-stu-id="77630-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="77630-112">“你的邮件无法送达，因为系统认为你不是有效的发件人。</span><span class="sxs-lookup"><span data-stu-id="77630-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="77630-113">这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77630-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="77630-114">请联系电子邮件管理员获取帮助。</span><span class="sxs-lookup"><span data-stu-id="77630-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="77630-115">远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。</span><span class="sxs-lookup"><span data-stu-id="77630-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="77630-116">管理员可以从安全与合规中心内的“受限的发件人”门户中或使用 Exchange Online PowerShell 删除用户。</span><span class="sxs-lookup"><span data-stu-id="77630-116">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="77630-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="77630-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="77630-118">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="77630-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="77630-119">若要直接转到“受限的用户”页，请访问 <https://protection.office.com/restrictedusers>。</span><span class="sxs-lookup"><span data-stu-id="77630-119">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="77630-120">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="77630-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="77630-121">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="77630-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="77630-122">若要从受限用户门户中删除用户，需要成为 **组织管理人员** 或 **安全管理员** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="77630-122">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="77630-123">若要获得对受限用户门户的只读访问权限，必须成为 **全球读者** 或 **安全读者** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="77630-123">For read-only access to the Restricted Users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="77630-124">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="77630-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="77630-125">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="77630-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="77630-126">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="77630-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="77630-127">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="77630-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="77630-128">发件人超过出站电子邮件限制是帐户遭到入侵的标志。</span><span class="sxs-lookup"><span data-stu-id="77630-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="77630-129">请务必先按照必需步骤操作来重新获得对帐户的控制，再从“受限的用户”门户中删除用户。</span><span class="sxs-lookup"><span data-stu-id="77630-129">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="77630-130">有关详细信息，请参阅[在 Office 365 中响应遭入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="77630-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="77630-131">使用安全与合规中心从“受限的用户”列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="77630-131">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="77630-132">在安全与合规中心内，依次转到“威胁管理”\>“审阅”\>“受限的用户”。</span><span class="sxs-lookup"><span data-stu-id="77630-132">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="77630-133">查找并选择要取消阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="77630-133">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="77630-134">在“操作”列中，单击“取消阻止”。</span><span class="sxs-lookup"><span data-stu-id="77630-134">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="77630-135">一个飞出窗口将转到有关其发送受限的帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="77630-135">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="77630-136">应按照建议进行操作，确保在帐户实际遭到破坏的情况下采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="77630-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="77630-137">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="77630-137">Click **Next** when done.</span></span>

4. <span data-ttu-id="77630-138">下一个屏幕包含可帮助防止以后遭到破坏的建议。</span><span class="sxs-lookup"><span data-stu-id="77630-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="77630-139">启用多重身份验证 (MFA) 和更改密码是一种很好的防御措施。</span><span class="sxs-lookup"><span data-stu-id="77630-139">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="77630-140">完成后，单击 **“解锁用户”**。</span><span class="sxs-lookup"><span data-stu-id="77630-140">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="77630-141">单击 **“是”** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="77630-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="77630-142">从用户中删除所有限制可能需要多达 24 小时。</span><span class="sxs-lookup"><span data-stu-id="77630-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="77630-143">验证用于受限的用户的警报设置</span><span class="sxs-lookup"><span data-stu-id="77630-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="77630-144">默认警报策略“被限制发送电子邮件的用户”会在用户被阻止发送出站邮件时自动通知管理员。</span><span class="sxs-lookup"><span data-stu-id="77630-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="77630-145">可以验证这些设置，并添加其他要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="77630-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="77630-146">有关警报策略的详细信息，请参阅 [Microsoft 365 中的警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77630-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77630-147">必须启用审核日志搜索，这样警报才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="77630-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="77630-148">有关详细信息，请参阅[启用或禁用审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="77630-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="77630-149">在安全与合规中心内，依次转到“警报”\>“警报策略”。</span><span class="sxs-lookup"><span data-stu-id="77630-149">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="77630-150">查找并选择 **发送电子邮件受限用户** 警报。</span><span class="sxs-lookup"><span data-stu-id="77630-150">Find and select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="77630-151">在随即显示的浮出控件中，验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="77630-151">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="77630-152">**状态**：验证此警报是否已启用 ![开关打开](../../media/scc-toggle-on.png)。</span><span class="sxs-lookup"><span data-stu-id="77630-152">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="77630-153">**电子邮件收件人**：单击“编辑”，然后在随即显示的“编辑收件人”浮出控件中验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="77630-153">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="77630-154">**发送电子邮件通知**：验证此复选框是否已选中（“开”）。</span><span class="sxs-lookup"><span data-stu-id="77630-154">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="77630-155">**电子邮件收件人**：默认值为“TenantAdmins”（表示“全局管理员”成员）。</span><span class="sxs-lookup"><span data-stu-id="77630-155">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="77630-156">若要添加其他收件人，请单击此框的空白区域。</span><span class="sxs-lookup"><span data-stu-id="77630-156">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="77630-157">此时，收件人列表会显示，你可以键入名称来筛选并选择收件人。</span><span class="sxs-lookup"><span data-stu-id="77630-157">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="77630-158">若要从此框中删除现有收件人，请单击其名称旁边的 ![“删除”图标](../../media/scc-remove-icon.png)可。</span><span class="sxs-lookup"><span data-stu-id="77630-158">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="77630-159">**每日通知限制**：默认值为“无限制”，但你可以选择每日通知数上限。</span><span class="sxs-lookup"><span data-stu-id="77630-159">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="77630-160">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="77630-160">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="77630-161">返回到“被限制发送电子邮件的用户”浮出控件，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="77630-161">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="77630-162">使用 Exchange Online PowerShell 查看和删除“受限的用户”列表中的用户</span><span class="sxs-lookup"><span data-stu-id="77630-162">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="77630-163">若要查看被限制发送电子邮件的用户列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="77630-163">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="77630-164">若要查看特定用户的详细信息，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="77630-164">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="77630-165">若要详细了解语法和参数，请参阅 [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="77630-165">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="77630-166">若要从“受限的用户”列表中删除用户，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="77630-166">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="77630-167">若要详细了解语法和参数，请参阅 [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="77630-167">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>