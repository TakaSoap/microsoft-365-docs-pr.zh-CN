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
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft 365 Defender 门户中从“受限的用户”页面删除用户。 用户之所以被添加到“受限的用户”门户是因为发送出站垃圾邮件，这通常是由于帐户遭入侵所致。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 66b810f7bb6381d405ee7ffc0d6b1cf7a10f2bf2
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941428"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>在 Microsoft 365 中从“受限的用户”门户中删除被阻止的用户

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果某用户超过[服务限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)中指定的出站发送限制之一，此用户就会被限制发送电子邮件，但仍可以接收电子邮件。

此用户添加到 Microsoft 365 Defender 门户中的“**受限用户**”页面。如果此用户试图发送电子邮件，邮件就会以未送达报告（亦称为“NDR”或“退回邮件”）形式返回，并显示错误代码 [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) 和以下文本：

> “你的邮件无法送达，因为系统认为你不是有效的发件人。 这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。  请联系电子邮件管理员获取帮助。 远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。

管理员可以在 Microsoft 365 Defender 或 Exchange Online PowerShell 中从“受限的用户”页面删除用户。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到 **受限用户** 页，请使用 <https://security.microsoft.com/restrictedusers>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要从“受限的用户”门户中删除用户，需要成为 **组织管理** 或 **安全管理员** 角色组的成员。
  - 若要获得对“受限的用户”门户的只读访问权限，需要成为 **全局读取者** 或 **安全信息读取者** 角色组的成员。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的权限。有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 发件人超过出站电子邮件限制是帐户遭到入侵的标志。 请务必先按照所需步骤操作以重新获得对用户帐户的控制，再从“受限的用户”门户中删除用户。 有关详细信息，请参阅[在 Office 365 中响应遭入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)。

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>使用 Microsoft 365 Defender 门户从“受限的用户”列表中删除用户

1. 在 Microsoft 365 Defender 门户 <https://security.microsoft.com> 中，转到 **电子邮件和协作** \> **查看** \> **受限用户**。 若要直接转到 **受限用户** 页，请使用 <https://security.microsoft.com/restrictedusers>。

2. 在“**受限的用户**”页面上，查找你希望取消阻止的用户并通过单击该用户进行选择。

3. 单击显示的“**取消阻止**”操作。

4. 在显示的“**取消阻止用户**”浮出控件中，阅读有关受限帐户的详细信息。 应按照建议进行操作，以确保在帐户遭入侵时采取适当的措施。

   完成后，请单击“**下一步**”。

5. 下一个屏幕包含可帮助防止以后遭入侵的建议。 启用多重身份验证 (MFA) 和重置密码是一种很好的防御措施。

   完成后，请单击“**提交**”。

6. 单击 **“是”** 确认更改。

   > [!NOTE]
   > 从用户中删除所有限制可能需要多达 1 小时。

## <a name="verify-the-alert-settings-for-restricted-users"></a>验证用于受限的用户的警报设置

默认警报策略“被限制发送电子邮件的用户”会在用户被阻止发送出站邮件时自动通知管理员。 可以验证这些设置，并添加其他要通知的用户。 有关警报策略的详细信息，请参阅 [Microsoft 365 中的警报策略](../../compliance/alert-policies.md)。

> [!IMPORTANT]
> 必须启用审核日志搜索，这样警报才能正常运行。 有关详细信息，请参阅[启用或禁用审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

1. 在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**策略和规则**”\>“**警报策略**”。

2. 在“**警报策略**”页面上，查找并选择名为“**被限制发送电子邮件的用户**”的警报。 你可以按名称对策略进行排序，或使用“**搜索框**”查找策略。

3. 在显示的“**被限制发送电子邮件的用户**”浮出控件中，验证或配置下列设置：
   - **状态**：验证此警报是否已启用![切换打开](../../media/scc-toggle-on.png)。
   - **电子邮件收件人**：单击“编辑”，然后在随即显示的“编辑收件人”浮出控件中验证或配置下列设置：
     - **发送电子邮件通知**：验证此项是否已选中（“**开**”）。
     - **电子邮件收件人**：默认值为“TenantAdmins”（表示“全局管理员”成员）。 若要添加其他收件人，请单击此框的空白区域。 此时，收件人列表会显示，你可以键入名称来筛选并选择收件人。 可以通过单击现有收件人姓名旁边的![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) 从框中删除现有收件人。
     - **每日通知限制**：默认值为“无限制”，但你可以选择每日通知数上限。

     完成时，请单击“保存”。

4. 返回到“被限制发送电子邮件的用户”浮出控件，单击“关闭”。

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>使用 Exchange Online PowerShell 查看和删除“受限的用户”列表中的用户

若要查看被限制发送电子邮件的用户列表，请运行以下命令：

```powershell
Get-BlockedSenderAddress
```

若要查看特定用户的详细信息，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

若要详细了解语法和参数，请参阅 [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress)。

若要从“受限的用户”列表中删除用户，请将 \<emailaddress\> 替换为相应用户的电子邮件地址，并运行以下命令：

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

若要详细了解语法和参数，请参阅 [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress)。
