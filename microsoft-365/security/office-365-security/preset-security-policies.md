---
title: 预设安全策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何跨 EOP Exchange Online Protection (和 Microsoft Defender for) 保护功能应用标准策略和严格Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ff58fb8ebb64c36ab157484fd0dbace9e9c0dfa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196473"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>在 EOP 和 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

预设安全策略提供了一个集中位置，用于一次将建议的所有垃圾邮件、恶意软件和网络钓鱼策略应用于用户。 策略设置不可配置。 相反，它们是由我们设置的，它们基于我们在数据中心中的观察和体验，以平衡将有害的内容远离用户和避免不必要的中断。

本文的其余部分介绍了预设安全策略以及如何配置它们。

## <a name="what-preset-security-policies-are-made-of"></a>预设安全策略由什么决定

预设安全策略包含以下元素：

- 配置文件
- 策略
- 策略设置

此外，如果多个预设安全策略和其他策略适用于同一个人，则优先顺序非常重要。

### <a name="profiles-in-preset-security-policies"></a>预设安全策略中的配置文件

配置文件确定保护级别。 以下配置文件可用：

- **标准保护**: 适用于大多数用户的基线保护配置文件。
- **严格保护**：针对所选用户的更积极保护配置文件 (高价值目标或优先) 。

使用具有条件和例外的规则，这些规则可确定配置文件的适用或不应用于哪些用户。

可用的条件和例外包括：

- **用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。
- **组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。
- **域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。

只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

### <a name="policies-in-preset-security-policies"></a>预设安全策略中的策略

预设安全策略使用来自 EOP 和 Microsoft Defender for Office 365 中各种保护功能的相应策略。 这些策略是在 _将"标准保护"_ 或"严格 **保护**"预设安全策略分配给用户后创建的。  不能修改这些策略。

- **Exchange Online Protection (EOP)** 策略：这包括Microsoft 365邮箱的 Exchange Online 组织，以及没有邮箱Exchange Online EOP 组织：

  - [名为"标准预设安全策略](configure-your-spam-filter-policies.md)"**和"****严格预设安全策略"的反垃圾邮件策略**。
  - [名为"标准预设安全策略](configure-anti-malware-policies.md)"**和"****严格预设安全策略"的反恶意软件策略**。
  - [名为"标准预设安全策略"](set-up-anti-phishing-policies.md#spoof-settings)和"严格预设安全策略"的EOP 防钓鱼策略 (欺骗) 。

- **Microsoft Defender for Office 365** 策略：这包括具有 Microsoft 365 E5 或 Defender for Office 365 加载项订阅的组织：

  - Microsoft Defender 中名为"标准预设安全策略Office 365 **严格** 预设安全策略"的反网络钓鱼策略，其中包括：

    - EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [保险箱"标准预设](set-up-safe-links-policies.md)安全策略"和"**严格预设安全策略"的链接策略**。

  - [保险箱"](set-up-safe-attachments-policies.md)**标准** 预设安全策略"和"**严格预设安全策略"的附件策略**。

请注意，你可以将 EOP 保护应用于与 Microsoft Defender 不同的用户，Office 365保护。

### <a name="policy-settings-in-preset-security-policies"></a>预设安全策略中的策略设置

你无法修改保护配置文件中的策略设置。 "**标准**"**和**"严格"策略设置值在 EOP 和 Microsoft Defender 的推荐设置中 [进行了Office 365安全。](recommended-settings-for-eop-and-office365.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>预设安全策略和其他策略的优先级顺序

向用户应用多个策略时，将按从最高优先级到最低优先级的顺序应用以下顺序：

1. **严格保护** 预设安全策略
2. **标准保护** 预设安全策略
3. 自定义安全策略
4. 默认安全策略

换句话说，严格保护策略的设置会覆盖 **标准** 保护策略的设置，这将覆盖自定义策略中的设置，这将覆盖默认策略中的设置。

例如，如果标准保护中存在一个安全性设置，并且管理员为用户启用了标准保护，那么将应用标准保护设置，而不是在自定义策略或默认策略 (中为同一用户) 配置的标准保护设置。  请注意，在将自定义策略应用于组织中其他用户以满足特定需求时，你可能希望仅对部分组织应用标准或严格保护策略。

## <a name="assign-preset-security-policies-to-users"></a>向用户分配预设安全策略

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到 **预设安全策略页面** ，请使用 <https://security.microsoft.com/presetSecurityPolicies> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要配置预设安全策略，你需要是组织管理或 **安全管理员角色****组** 的成员。
  - 若要对预设安全策略进行只读访问，你需要是全局读者角色 **组** 的成员。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：将用户添加到 Azure Active Directory 角色Microsoft 365 管理中心为用户提供了对 Microsoft 365 中其他功能所需的权限。  有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>使用 Microsoft 365 Defender门户向用户分配预设安全策略

1. 在 Microsoft 365 Defender 门户中，转到"模板策略"&中的"电子邮件&协作策略"&"预设安全策略 \>  \>  \> **"** 部分。

2. 在 **"标准保护"** 或 **"严格保护"下，** 单击"**编辑"。**

3. 将 **启动"应用标准保护** " **或"应用严格保护** "向导。 在 **"适用于 EOP** 保护"页上，标识 [EOP](#policies-in-preset-security-policies) 保护应用于以下收件人条件 (内部) ：
   - **用户**
   - **组**
   - **域**

   单击相应的框，开始键入值，然后从结果中选择所需的值。 根据需要多次重复此过程。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。 对于用户，请自行输入星号 (\*) 以查看所有可用值。

   - **排除这些用户、组和域**: 若要为策略应用于的内部收件人添加例外 (收件人例外)，请选择此选项并配置例外。 设置和行为与条件完全相同。

   完成后，单击“**下一步**”。

4. 在适用于 Office 365 组织的 Microsoft Defender 中，你将访问适用于 Office 365 保护的 **Defender** 页面，以标识 [Microsoft Defender](#policies-in-preset-security-policies)针对 Office 365 保护应用于 (收件人条件) 。

   设置和行为与适用于页面 **的 EOP 保护完全相同** 。

   完成后，单击“**下一步**”。

5. 在"**查看并确认更改"** 页上，验证您的选择，然后单击"确认 **"。**

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>使用Microsoft 365 Defender门户修改预设安全策略的分配

修改标准保护或严格保护安全策略分配的步骤与最初向用户分配预设安全策略[时的步骤相同](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)。

若要禁用 **标准保护****或严格** 保护安全策略，同时仍保留现有条件和例外，将开关滑动到 **禁用切换** ![ 关闭 ](../../media/scc-toggle-off.png) 。 若要启用策略，将切换开关滑动到 **启用切换** ![ 打开 ](../../media/scc-toggle-on.png) 。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否成功向用户分配了标准保护或严格保护安全策略，请使用默认值不同于"标准"保护设置（与"严格保护"设置不同）的保护设置。 

例如，对于被检测为垃圾邮件 (高可信度垃圾邮件) 验证该邮件是否传递到 **标准** 保护用户的"垃圾邮件"文件夹，并隔离"严格保护" **用户** 。

或者，对于 [](bulk-complaint-level-values.md)批量邮件，验证 BCL 值 6 或更高值是否将邮件发送到 **标准** 保护用户的垃圾邮件文件夹，BCL 值 4 或更高值会隔离严格保护 **用户的邮件。**
