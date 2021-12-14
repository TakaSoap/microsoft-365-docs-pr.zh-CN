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
- admindeeplinkMAC
- admindeeplinkDEFENDER
- admindeeplinkEXCHANGE
ms.localizationpriority: high
search.appverid:
- MET150
description: 了解如何使用 Microsoft 365 中的工具来识别并响应遭到入侵的电子邮件帐户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c848a62793e6397f4cfd489c68d156a194b7911d
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421110"
---
# <a name="responding-to-a-compromised-email-account"></a>响应遭到入侵的电子邮件帐户

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**摘要** 了解如何识别并响应 Microsoft 365 中遭到入侵的电子邮件帐户。

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>什么是 Microsoft 365 中遭到入侵的电子邮件帐户？

通过使用凭据（例如用户名和密码或 PIN）来控制对 Microsoft 365 邮箱、数据和其他服务的访问。 如果除预期用户以外的其他人窃取了这些凭据，则被盗的凭据将视为遭到入侵。 借助这些凭据，攻击者能够以原始用户的身份登录并执行非法操作。

通过使用窃取的凭据，攻击者可以访问用户的 Microsoft 365 邮箱、SharePoint 文件夹或用户 OneDrive 中的文件。 其中一种常见操作是攻击者以原始用户的身份将电子邮件发送给组织内外的收件人。 当攻击者通过电子邮件将数据发送给外部收件人时，这称为数据泄露。

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>遭到入侵的 Microsoft 电子邮件帐户的症状

用户可能会注意到并报告其 Microsoft 365 一邮箱中的异常活动。下面是一些常见症状：

- 可疑活动，例如丢失或删除的电子邮件。
- 其他用户可能会收到来自遭到入侵的帐户的电子邮件，而发件人的“**已发送邮件**”文件夹中没有相应的电子邮件。
- 存在并非由预期用户或管理员创建的收件箱规则。 这些规则可以自动将电子邮件转发到未知地址，或将其移动到“**便笺**”、“**垃圾邮件**”或“**RSS 订阅**”文件夹。
- 在全局地址列表中，用户的显示名称可能已发生更改。
- 用户的邮箱被阻止发送电子邮件。
- Microsoft Outlook 或 Outlook 网页版（以前称为 Outlook Web App）中的“已发送邮件”或“已删除邮件”文件夹包含常见的黑客帐户邮件，例如“我被困在伦敦，请给我汇款”。
- 异常的个人资料更改，例如更新了姓名、电话号码或邮政编码。
- 异常的凭据更改，例如多次要求进行密码更改。
- 最近添加了邮件转发功能。
- 最近添加了异常的签名，例如假银行签名或处方药签名。

如果用户报告了上述任何症状，你应该进一步展开调查。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender 门户</a>和 Azure 门户提供的工具可帮助你调查你怀疑可能遭到入侵的用户帐户的活动。

- **Microsoft 365 Defender 门户内的统一审核日志**：通过筛选从可疑活动发生前到当前日期的日期范围内的结果来审阅可疑帐户的所有活动。不要在搜索期间筛选活动。

- **EAC 中的管理员审核日志**：在 Exchange Online 中，可以使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心 (EAC)</a> 搜索和查看管理员审核日志中的条目。 管理员审核日志根据管理员和分配有管理员权限的用户执行的 Exchange Online PowerShell cmdlet 来记录特定操作。 管理员审核日志中的条目向您提供有关所运行的 cmdlet、所使用的参数、运行 cmdlet 的用户以及受影响的对象的相关信息。

- **Azure AD 门户中的 Azure AD 登录日志和其他风险报告**：检查以下列中的值：
  - 查看 IP 地址
  - 登录位置
  - 登录时间
  - 登录成功或失败

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>如何保护和恢复疑似遭到入侵的 Microsoft 365 帐户和邮箱的电子邮件功能

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使你重新获得对帐户的访问权限，攻击者也可能添加了后门条目，这让攻击者能够恢复对该帐户的控制权。

你必须执行以下所有步骤才能重新获得对帐户的访问权限，以便更快地确保劫持者无法继续控制你的帐户。 这些步骤可帮助你删除劫持者可能已添加到你帐户的任何后门条目。 执行这些步骤后，我们建议你运行病毒扫描以确保你的计算机不会遭到入侵。

### <a name="step-1-reset-the-users-password"></a>步骤 1 重置用户密码

按照[为他人重置商业版密码](../../admin/add-users/reset-passwords.md#reset-my-admin-password)中的程序操作。

> [!IMPORTANT]
>
> - 不要通过电子邮件将新密码发送给预期用户，因为此时攻击者仍可以访问邮箱。
>
> - 确保密码为强密码，并且包含大写和小写字母、至少一个数字和至少一个特殊字符。
>
> - 不要重复使用最近使用的五个密码。即使密码历史记录要求允许你重用最近使用过的密码，你也应该选择攻击者无法猜到的密码。
>
> - 如果你的本地标识已与 Microsoft 365 联合，则必须在本地更改密码，然后通知管理员帐户遭到入侵。
>
> - 务必更新应用密码。 重置用户帐户密码后，不会自动撤消应用密码。 用户应删除现有应用程序密码并创建新密码。 有关说明，请参阅[从其他安全验证页面创建和删除应用密码](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)。
>
> - 强烈建议启用多重身份验证 (MFA)，以防发生泄漏，特别是对于拥有管理权限的帐户。 若要了解有关 MFA 的详细信息，请转到[设置多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步骤 2 删除可疑的电子邮件转发地址

1. 转到 Microsoft 365 管理中心：<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>。

2. 转到“**用户**”\>“**活动用户**”。找到有问题的用户帐户，然后选择该用户（行），而不选中复选框。

3. 在出现的详细信息浮出控件中，选择“**邮件**”选项卡。

4. 如果“**电子邮件转发**”部分中的值为“**已应用**”，请单击“**管理电子邮件转发**”。 在出现的“**管理电子邮件转发**”浮出控件中，清除“**转发发送至此邮箱的所有电子邮件**”，然后单击“**保存更改**”。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步骤 3 禁用任何可疑的收件箱规则

1. 使用 Outlook 网页版登录用户的邮箱。

2. 单击齿轮图标，然后单击“**邮件**”。

3. 单击“**收件箱和整理规则**”并查看规则。

4. 禁用或删除可疑的规则。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步骤 4 取消阻止用户发送邮件

如果疑似遭到入侵的邮箱被非法用于发送垃圾电子邮件，则可能是该邮箱已被阻止发送邮件。

若要取消阻止邮箱发送邮件，请按照[发送垃圾电子邮件后，从受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)中的步骤执行操作。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步骤 5（可选）阻止用户帐户登录

> [!IMPORTANT]
> 你可以阻止疑似遭到入侵的帐户登录，直到你认为重新启用访问权限是安全的。

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的 Microsoft 365 管理中心，然后转到“**用户**”\>“**活动用户**”。

2. 查找并选择用户帐户，单击“![更多图标](../../media/ITPro-EAC-MoreOptionsIcon.png)”，然后选择“**编辑登录状态**”。

3. 出现“**阻止登录**”的窗格上，选择“**阻止此用户登录**”，然后单击“**保存更改**”。

4. 打开 Exchange 管理中心 （EAC），然后转到“**收件人**”\><a href="https://go.microsoft.com/fwlink/?linkid=2183135" target="_blank">“**邮箱**”</a>。

5. 查找并选择用户。在打开的邮箱详细信息浮出控件中，执行以下步骤：
   - 在 **电子邮件应用** 部分中，通过将切换开关移到右侧“![禁用](../../media/scc-toggle-on.png)”来阻止所有可用设置：
     - **Outlook 网页版**
     - **Outlook 桌面应用 (MAPI)**
     - **Exchange Web 服务**
     - **移动应用 (Exchange ActiveSync)**
     - **IMAP**
     - **POP3**

   完成后，单击“**保存**”，然后单击“**关闭**”。

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步骤 6（可选）从所有管理角色组中删除疑似遭到入侵的帐户

> [!NOTE]
> 在帐户受到保护后，可以恢复管理角色组成员身份。

1. 使用全局管理员帐户转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的 Microsoft 365 管理中心，然后执行以下步骤：
   1. 转到“**用户**”\>“**活动用户**”。
   2. 查找并选择用户帐户，单击“![更多图标](../../media/ITPro-EAC-MoreOptionsIcon.png)”，然后选择“**管理角色**”。
   3. 删除分配给该帐户的任何管理角色。 完成后，单击“**保存更改**”。

2. 打开 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender 门户</a>，然后执行以下步骤：
   1. 转到“**权限和角色**”\>“**电子邮件和协作角色**”\>“**角色**”。
   2. 在 **权限** 页面上，在列表中选择每个角色组，然后在出现的详细信息浮出控件的“**成员**”部分查找用户帐户。如果角色组包含用户账户，请执行以下步骤：
      1. 在“**成员**”部分中，单击“**编辑**”。
      2. 在出现的“**编辑选择成员**”浮出控件中，单击“**编辑**”。
      3. 在出现的 **选择成员** 浮出控件上，单击“**删除**”。
      4. 在出现的浮出控件中，选择用户账户，然后单击“**删除**”。

         完成后，单击“**完成**”、“**保存**”，然后单击“**关闭**”。

3. 打开 EAC，然后执行以下步骤：
   1. 选择“**角色**”\><a href="https://go.microsoft.com/fwlink/?linkid=2183234" target="_blank">“**管理员角色**”</a>。
   2. 在 **管理员角色** 页面上，手动选择每个角色组，然后在详细信息窗格中，选择“**已分配**”选项卡以验证用户帐户。 如果角色组包含该用户帐户，请执行以下步骤：
      1. 选择用户帐户。
      2. 单击 ![删除图标。](../../media/m365-cc-sc-delete-icon.png).

         完成后，单击“**保存**”。

### <a name="step-7-optional-additional-precautionary-steps"></a>步骤 7（可选）其他预防措施

1. 确保验证已发送的邮件。 你可能需要通知联系人列表中的人员你的帐户遭到入侵。 例如，攻击者可能会向他们要钱，谎称他们被困在另一个国家/地区并且需要钱，也可能会向他们发送病毒以便劫持其计算机。

2. 将此 Exchange 帐户用作其备用电子邮件帐户的任何其他服务可能已遭到入侵。 首先，为 Microsoft 365 订阅执行这些步骤，然后为其他帐户执行这些步骤。

3. 确保你的联系信息（如电话号码和地址）正确无误。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像网络安全专家那样保护 Microsoft 365

你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。  使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。

- 需要在前 30 天完成的任务。 这些任务会对你的用户产生直接影响并且影响很小。
- 要在 90 天内完成的任务。这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。
- 90 天后。这些增强功能基于前 90 天的工作构建。

## <a name="see-also"></a>另请参阅

- [在 Microsoft 365 中检测并修正 Outlook 规则和自定义窗体注入攻击](detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet 犯罪投诉中心](https://www.ic3.gov/Home/Ransomware)
- [证券交易委员会 -“网络钓鱼”诈骗](https://www.sec.gov/investor/pubs/phishing.htm)
- [使用报告消息加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)直接向 Microsoft 和你的管理员报告垃圾邮件
