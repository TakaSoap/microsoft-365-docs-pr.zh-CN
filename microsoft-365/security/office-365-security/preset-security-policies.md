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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何跨 Exchange Online Protection 和 EOP (和 Microsoft Defender for Office 365 的保护功能) 标准策略和严格策略设置
ms.openlocfilehash: a77201835652fb36822fbc603f5211c1f7a9521b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659226"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 和 Microsoft Defender for Office 365 中的预设安全策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


预设安全策略提供了一个集中位置，用于一次将建议的所有垃圾邮件、恶意软件和网络钓鱼策略应用于用户。 策略设置不可配置。 相反，它们由我们设置，基于我们在数据中心中的观察和体验，以平衡将有害的内容远离用户而不中断他们的工作。

本主题的其余部分介绍了预设安全策略以及如何配置它们。

## <a name="what-preset-security-policies-are-made-of"></a>什么是预设安全策略

预设安全策略包含以下元素：

- 配置文件
- 策略
- 策略设置

此外，如果多个预设安全策略和其他策略适用于同一个人，则优先顺序很重要。

### <a name="profiles-in-preset-security-policies"></a>预设安全策略中的配置文件

配置文件确定保护级别。 以下配置文件可用：

- **标准保护**：适用于大多数用户的基线保护配置文件。
- **严格保护**：针对所选用户的更积极保护配置文件 (高价值目标或优先级用户) 。

使用具有条件和例外的规则来确定配置文件是应用还是不适用于哪些人。

只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

可用的条件和例外包括：

- **收件人为**：组织中邮箱、邮件用户或邮件联系人。
- **收件人是组织中**： 组的成员。
- **收件人域是**：在 Microsoft 365 中配置的接受域。

### <a name="policies-in-preset-security-policies"></a>预设安全策略中的策略

预设安全策略使用来自 EOP 和 Microsoft Defender for Office 365 中各种保护功能的相应策略。 这些策略是在 _将标准保护_ 或严格保护预设安全策略分配给用户后创建的。 不能修改这些策略。

- **Exchange Online Protection (EOP)** 策略：这包括具有 Exchange Online 邮箱的 Microsoft 365 组织和没有 Exchange Online 邮箱的独立 EOP 组织：

  - [名为"](configure-your-spam-filter-policies.md)**标准** 预设安全策略"和"**严格预设安全策略"的反垃圾邮件策略**。
  - [名为"](configure-anti-malware-policies.md)**标准** 预设安全策略"和"**严格预设安全策略"的反恶意软件策略**。
  - [名为"标准预设安全策略"](set-up-anti-phishing-policies.md#spoof-settings)和"严格预设安全策略"的EOP 防钓鱼策略 (欺骗) 。

- **Microsoft Defender for Office 365 策略**：这包括具有 Microsoft 365 E5 或适用于 Office 365 的 Defender 附加订阅的组织：

  - Microsoft Defender for Office 365 中名为 **"标准** 预设安全策略" **和"严格** 预设安全策略"的防钓鱼策略，其中包括：

    - EOP [防钓鱼](set-up-anti-phishing-policies.md#spoof-settings) 策略中可用的相同欺骗设置。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [名为"](set-up-atp-safe-links-policies.md)**标准** 预设安全策略"和"**严格预设安全策略"的安全链接策略**。

  - [名为"](set-up-atp-safe-attachments-policies.md) 标准预设安全策略 **"和** " **严格预设安全策略"的安全附件策略**。

请注意，你可以将 EOP 保护应用于不同于 Microsoft Defender 的 Office 365 保护的用户。

### <a name="policy-settings-in-preset-security-policies"></a>预设安全策略中的策略设置

不能修改保护配置文件中的策略设置。 标准 **策略** 和 **严格** 策略设置值在 EOP 和 [Microsoft Defender for Office 365 安全的建议设置中介绍](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>预设安全策略和其他策略的优先顺序

向用户应用多个策略时，将按从最高优先级到最低优先级的顺序应用以下顺序：

1. **严格保护** 预设安全策略
2. **标准保护** 预设安全策略
3. 自定义安全策略
4. 默认安全策略

换句话说，严格保护策略的设置会覆盖 **标准** 保护策略的设置，这将覆盖自定义策略中的设置，这将覆盖默认策略中的设置。

## <a name="assign-preset-security-policies-to-users"></a>向用户分配预设安全策略

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **"预设安全策略"页** ，请使用 <https://protection.office.com/presetSecurityPolicies> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要配置预设安全策略，你需要是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对预设安全策略进行只读访问，你需要是全局读者 **角色组的成员** 。

  有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

  注意：将用户添加到 Microsoft 36 & 5 管理中心的相应 Azure Active Directory 角色会为用户提供安全与合规中心所需的权限和 Microsoft 365 中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>使用安全&合规中心向用户分配预设安全策略

1. 在安全&，转到 **"威胁管理** \> **策略** \> **预设"安全策略**。

2. 在 **"标准保护**"或 **"严格保护"下**，单击 **"编辑"。**

3. " **应用标准保护"** 或 **"应用严格保护"** 向导将启动。 在 **适用于步骤的 EOP** 保护上，标识 [EOP 保护应用于](#policies-in-preset-security-policies) 的内部收件人：

   1. 单击 **"添加条件"。** In the dropdown that appears， select a condition under **Applied if**：

      - **收件人是**
      - **收件人是以下组的成员：**
      - **收件人域为**

      一个条件只能使用一次，但你可以为条件指定多个值。 同一条件的多个值使用 OR 逻辑 (或 _\<recipient1\>_ _\<recipient2\>_) 。

   2. 所选条件将显示在带阴影的节中。 在这一部分中，单击 **其中任何一个** 框。 如果您稍等片刻，将显示一个列表，以便您可以选择一个值。 或者，您可以开始键入值以筛选列表并选择值。 根据需要重复执行此步骤（次数不限）。 若要删除单个值 **，请单击值** ![ 上的" ](../../media/scc-remove-icon.png) 删除"图标。 若要删除整个条件 **，请单击** ![ 条件上的" ](../../media/scc-remove-icon.png) 删除"图标。

   3. 若要添加其他条件，请单击 **"添加条件** "，然后从其余条件中选择。 不同的条件使用 AND 逻辑 (，例如 _\<recipient1\>_ _\<member of group 1\>_ ，) 。

      重复上一步以向条件添加值，并根据需要多次重复此步骤，或直到条件用完。

   4. 若要添加例外，请单击 **"添加条件"。** In the dropdown that appears， select a condition under **Except when**. 设置和行为与条件完全相同。

   完成后，单击“下一步”。

4. 如果你的组织具有适用于 Office 365 的 Microsoft Defender，你将采用 **ATP** 保护，以执行步骤来标识 Microsoft [Defender for Office 365](#policies-in-preset-security-policies) 保护适用于的内部收件人。

   设置和行为与 **EOP 保护应用于步骤完全相同** 。

   完成后，单击“下一步”。

5. 在 **"确认**"步骤中，验证您的选择，然后单击"确认 **"。**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>使用安全&合规中心修改预设安全策略的分配

修改标准保护或严格保护安全策略分配的步骤与最初向用户分配预设安全策略[时的步骤相同](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。

若要禁用 **标准保护** 或 **严格** 保护安全策略，同时仍保留现有条件和例外，将切换切换为 **"已禁用"。** 若要启用策略，将切换开关滑动到 **"已启用"。**

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功将标准保护或严格保护安全策略分配给用户，请使用默认值不同于"标准"保护设置（与"严格保护"设置不同）的保护设置。 

例如，对于被检测为垃圾邮件 (高可信度垃圾邮件) 验证邮件是否传递到 **标准** 保护用户的"垃圾邮件"文件夹，并隔离"严格保护"用户。 

或者，对于 [](bulk-complaint-level-values.md)批量电子邮件，验证 BCL 值 6 或更高版本是否将邮件发送到 **标准** 保护用户的垃圾邮件文件夹，并且 BCL 值 4 或更高值会隔离严格保护 **用户** 的邮件。
