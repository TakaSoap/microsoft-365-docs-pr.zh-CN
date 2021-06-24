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
description: 管理员可以了解如何在 Microsoft 365 Defender 门户中从“受限的用户”页面删除用户。 用户之所以被添加到“受限的用户”门户是因为发送出站垃圾邮件，这通常是由于帐户遭入侵所致。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082848"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="62b04-104">在 Microsoft 365 中从“受限的用户”门户中删除被阻止的用户</span><span class="sxs-lookup"><span data-stu-id="62b04-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="62b04-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="62b04-105">**Applies to**</span></span>
- [<span data-ttu-id="62b04-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="62b04-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="62b04-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="62b04-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="62b04-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62b04-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="62b04-109">如果某用户超过[服务限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)中指定的出站发送限制之一，此用户就会被限制发送电子邮件，但仍可以接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="62b04-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="62b04-110">用户被添加到 Microsoft 365 Defender 门户中的“**受限的用户**”页面。</span><span class="sxs-lookup"><span data-stu-id="62b04-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="62b04-111">如果此用户试图发送电子邮件，邮件就会以未送达报告（亦称为“NDR”或“退回邮件”）形式返回，并显示错误代码 [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和以下文本：</span><span class="sxs-lookup"><span data-stu-id="62b04-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="62b04-112">“你的邮件无法送达，因为系统认为你不是有效的发件人。</span><span class="sxs-lookup"><span data-stu-id="62b04-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="62b04-113">这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="62b04-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="62b04-114">请联系电子邮件管理员获取帮助。</span><span class="sxs-lookup"><span data-stu-id="62b04-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="62b04-115">远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。</span><span class="sxs-lookup"><span data-stu-id="62b04-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="62b04-116">管理员可以在 Microsoft 365 Defender 或 Exchange Online PowerShell 中从“受限的用户”页面删除用户。</span><span class="sxs-lookup"><span data-stu-id="62b04-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="62b04-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="62b04-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="62b04-118">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="62b04-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="62b04-119">若要直接转到“**受限的用户**”页面，请使用 <https://security.microsoft.com/restrictedusers>。</span><span class="sxs-lookup"><span data-stu-id="62b04-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="62b04-120">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="62b04-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="62b04-121">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="62b04-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="62b04-122">若要从“受限的用户”门户中删除用户，需要成为 **组织管理** 或 **安全管理员** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="62b04-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="62b04-123">若要获得对“受限的用户”门户的只读访问权限，需要成为 **全局读取者** 或 **安全信息读取者** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="62b04-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="62b04-124">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="62b04-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="62b04-125">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="62b04-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="62b04-126">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="62b04-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="62b04-127">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="62b04-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="62b04-128">发件人超过出站电子邮件限制是帐户遭到入侵的标志。</span><span class="sxs-lookup"><span data-stu-id="62b04-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="62b04-129">请务必先按照所需步骤操作以重新获得对用户帐户的控制，再从“受限的用户”门户中删除用户。</span><span class="sxs-lookup"><span data-stu-id="62b04-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="62b04-130">有关详细信息，请参阅[在 Office 365 中响应遭入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="62b04-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="62b04-131">使用 Microsoft 365 Defender 门户从“受限的用户”列表中删除用户</span><span class="sxs-lookup"><span data-stu-id="62b04-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="62b04-132">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**” > “**检查**” > “**受限的用户**”。</span><span class="sxs-lookup"><span data-stu-id="62b04-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="62b04-133">在“**受限的用户**”页面上，查找你希望取消阻止的用户并通过单击该用户进行选择。</span><span class="sxs-lookup"><span data-stu-id="62b04-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="62b04-134">单击显示的“**取消阻止**”操作。</span><span class="sxs-lookup"><span data-stu-id="62b04-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="62b04-135">在显示的“**取消阻止用户**”浮出控件中，阅读有关受限帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="62b04-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="62b04-136">应按照建议进行操作，以确保在帐户遭入侵时采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="62b04-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="62b04-137">完成后，请单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="62b04-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="62b04-138">下一个屏幕包含可帮助防止以后遭入侵的建议。</span><span class="sxs-lookup"><span data-stu-id="62b04-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="62b04-139">启用多重身份验证 (MFA) 和重置密码是一种很好的防御措施。</span><span class="sxs-lookup"><span data-stu-id="62b04-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="62b04-140">完成后，请单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="62b04-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="62b04-141">单击 **“是”** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="62b04-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="62b04-142">从用户中删除所有限制可能需要多达 24 小时。</span><span class="sxs-lookup"><span data-stu-id="62b04-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="62b04-143">验证用于受限的用户的警报设置</span><span class="sxs-lookup"><span data-stu-id="62b04-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="62b04-144">默认警报策略“被限制发送电子邮件的用户”会在用户被阻止发送出站邮件时自动通知管理员。</span><span class="sxs-lookup"><span data-stu-id="62b04-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="62b04-145">可以验证这些设置，并添加其他要通知的用户。</span><span class="sxs-lookup"><span data-stu-id="62b04-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="62b04-146">有关警报策略的详细信息，请参阅 [Microsoft 365 中的警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="62b04-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62b04-147">必须启用审核日志搜索，这样警报才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="62b04-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="62b04-148">有关详细信息，请参阅[启用或禁用审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="62b04-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="62b04-149">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**警报策略**”。</span><span class="sxs-lookup"><span data-stu-id="62b04-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="62b04-150">在“**警报策略**”页面上，查找并选择名为“**被限制发送电子邮件的用户**”的警报。</span><span class="sxs-lookup"><span data-stu-id="62b04-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="62b04-151">你可以按名称对策略进行排序，或使用“**搜索框**”查找策略。</span><span class="sxs-lookup"><span data-stu-id="62b04-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="62b04-152">在显示的“**被限制发送电子邮件的用户**”浮出控件中，验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="62b04-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="62b04-153">**状态**：验证此警报是否已启用 ![开关打开](../../media/scc-toggle-on.png)。</span><span class="sxs-lookup"><span data-stu-id="62b04-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="62b04-154">**电子邮件收件人**：单击“编辑”，然后在随即显示的“编辑收件人”浮出控件中验证或配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="62b04-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="62b04-155">**发送电子邮件通知**：验证此项是否已选中（“**开**”）。</span><span class="sxs-lookup"><span data-stu-id="62b04-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="62b04-156">**电子邮件收件人**：默认值为“TenantAdmins”（表示“全局管理员”成员）。</span><span class="sxs-lookup"><span data-stu-id="62b04-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="62b04-157">若要添加其他收件人，请单击此框的空白区域。</span><span class="sxs-lookup"><span data-stu-id="62b04-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="62b04-158">此时，收件人列表会显示，你可以键入名称来筛选并选择收件人。</span><span class="sxs-lookup"><span data-stu-id="62b04-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="62b04-159">若要从此框中删除现有收件人，请单击其名称旁边的 ![“删除”图标](../../media/m365-cc-sc-remove-selection-icon.png)可。</span><span class="sxs-lookup"><span data-stu-id="62b04-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="62b04-160">**每日通知限制**：默认值为“无限制”，但你可以选择每日通知数上限。</span><span class="sxs-lookup"><span data-stu-id="62b04-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="62b04-161">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="62b04-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="62b04-162">返回到“被限制发送电子邮件的用户”浮出控件，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="62b04-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="62b04-163">使用 Exchange Online PowerShell 查看和删除“受限的用户”列表中的用户</span><span class="sxs-lookup"><span data-stu-id="62b04-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="62b04-164">若要查看被限制发送电子邮件的用户列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="62b04-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="62b04-165">若要查看特定用户的详细信息，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="62b04-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="62b04-166">若要详细了解语法和参数，请参阅 [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="62b04-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="62b04-167">若要从“受限的用户”列表中删除用户，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="62b04-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="62b04-168">若要详细了解语法和参数，请参阅 [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)。</span><span class="sxs-lookup"><span data-stu-id="62b04-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
