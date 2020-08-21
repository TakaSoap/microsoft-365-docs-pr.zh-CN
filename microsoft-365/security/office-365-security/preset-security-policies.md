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
description: '管理员可以了解如何在 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护策略 ATP 策略的保护功能上应用 (条) '
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825253"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>EOP 和 Office 365 ATP 中的预设安全策略

预设安全策略提供了一个集中位置，用于一次性向用户应用所有推荐的垃圾邮件、恶意软件和网络钓鱼策略。 策略设置不可配置。 而是由我们设置这些功能，它们基于我们在数据中心中的观察和体验，在保持无害内容从用户中断而不会中断其工作之间的平衡。

本主题的其余部分介绍预设的安全策略以及如何配置它们。

## <a name="what-preset-security-policies-are-made-of"></a>制作哪些预设安全策略

预设安全策略由以下元素组成：

- 配置文件
- 策略
- 策略设置

此外，如果有多个预设安全策略和其他策略适用于同一个人，则优先级的顺序非常重要。

### <a name="profiles-in-preset-security-policies"></a>预设安全策略中的配置文件

配置文件确定保护级别。 提供了以下配置文件：

- **标准保护**： 适合大多数用户的基础保护配置文件。
- **严格的保护**：适用于选定用户的更级 (目标或优先级的用户的更严格的) 。

您使用具有条件和例外的规则，这些规则可确定配置文件是或不适用于哪些人。

只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

可用的条件和例外如下所示：

- **收件人是**：组织中的邮箱、邮件用户或邮件联系人。
- **收件人为以下组的成员**：您组织中的组。
- **收件人域是：** 在 Microsoft 365 中配置的接受域。

### <a name="policies-in-preset-security-policies"></a>预设安全策略中的策略

预设安全策略使用 EOP 和 Office 365 ATP 中各种保护功能的相应策略。 在向用户 _分配标准_ 保护 **或** 严格 **保护预设** 安全策略后，将创建这些策略。 您无法修改这些策略。

- **Exchange Online Protection (EOP) 策略**：包括具有 Exchange Online 邮箱的 Microsoft 365 组织和独立的 EOP 组织，无需 Exchange Online 邮箱：
  
  - [名为"标准预](configure-your-spam-filter-policies.md)**设安全策略"和"严****格预设安全策略"的反垃圾邮件策略**。
  - [名为"标准预](configure-anti-malware-policies.md)**设安全策略"和"严****格预设安全策略"的反恶意软件策略**。
  - [EOP 反网络钓鱼策略（名为](set-up-anti-phishing-policies.md#spoof-settings)**"标准预设安全策略"****和"严格预设安全** (策略）防欺骗) 。

- **Office 365 高级威胁防 (ATP) 策略**：其中包括订阅有 Microsoft 365 E5 或 Office 365 ATP 的组织：

  - 名为"标准预设安全策略"和"严格预 **设安全** 策略"的 ATP **防钓鱼策略**，包括：

    - EOP [反网络](set-up-anti-phishing-policies.md#spoof-settings) 钓鱼策略中提供的相同欺骗设置。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [名为标准预设](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)**安全策略和严格****预设安全策略的安全链接策略**。

  - [名为"标准预](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)**设安全策略"和"严****格预设安全策略"的安全附件策略**。

请注意，EOP 保护可以对不同于 ATP 保护的用户应用 EOP 保护。

### <a name="policy-settings-in-preset-security-policies"></a>预设安全策略中的策略设置

您无法修改保护配置文件中的策略设置。 **"EOP"****和"Office** 365 ATP 安全"推荐[设置中描述了标准和严格策略设置值](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>预设的安全策略和其他策略的优先级顺序

如果向用户应用多个策略，将按以下顺序应用到最低优先级：

1. **严格保护预** 设安全策略
2. **标准保护** 预设安全策略
3. 自定义安全策略
4. 默认安全策略

换言之，严格 **保护策略的** 设置会覆盖标准保护策略 **的** 设置，它会覆盖自定义策略的设置，该策略会覆盖默认策略中的设置。

## <a name="assign-preset-security-policies-to-users"></a>向用户分配预设安全策略

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到"预设 **安全策略"** 页，请使用 <https://protection.office.com/presetSecurityPolicies> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要配置预设安全策略，您必须是以下角色组之一的成员：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 若要对预设安全策略进行只读访问，您需要是以下角色组的成员之一：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>使用安全与&中心向用户分配预设安全策略

1. 在安全与合规&中心内，转到 **威胁** \> **管理** \> **策略预设安全策略**。

2. 在 **"标准保护**或**严格保护"下，单击**"编辑 **"。**

3. 此**时将启动****"应用标准保护"或"应用严**格保护"向导。 在 **EOP 保护应用于步骤** 时，确定将应用 EOP 保护 [的内部](#policies-in-preset-security-policies) 收件人：

   1. 单击 **"添加条件"。** 在出现的下拉列表中，选择"已应用"下面的条件 **（如果出现该条件：）**

      - **收件人为**
      - **收件人为以下项的成员**
      - **收件人域为**

      您只能使用一次条件，但可为该条件指定多个值。 同一条件的多个值使用 OR (例如 _\<recipient1\>_ _\<recipient2\>_ ，) 。

   2. 您选择的条件将显示在具有底纹的部分中。 在该部分，单击" **任意内容"** 框。 如果等待等待，将显示一个列表，以便您可以选择一个值。 或者，可以开始键入一个值来筛选列表并选择一个值。 根据需要重复执行此步骤（次数不限）。 若要删除单个值，请单击该值 **上的"** ![ ](../../media/scc-remove-icon.png) 删除"图标。 要删除整个条件，请单击条件 **上的** ![ " ](../../media/scc-remove-icon.png) 删除"图标。

   3. 要添加其他条件，请单击 **"添加一个条件** ，并从其余条件中进行选择"。 例如，不同的条件使用 AND (逻辑 _\<recipient1\>_ ， _\<member of group 1\>_ 以及) 。

      重复上一步向条件中添加值，并根据需要多次重复此步骤，直到您不在条件运行状态。

   4. 若要添加例外，请单击"**添加条件"。** 在出现的下拉列表中，选择"除非"时 **的条件**。 设置和行为与条件完全相同。

   完成后，单击“下一步”****。

4. 如果你的组织拥有 Office 365 ATP，则 **你将转到 ATP** 保护来识别要应用 [Office 365 ATP 保护](#policies-in-preset-security-policies) 的内部收件人。

   设置和行为与 EOP 保护完全 **一样，步骤要应用到** EOP 保护。

   完成后，单击“下一步”****。

5. 在 **"确认**步骤"上，验证您的选择，然后单击"确认 **"。**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>使用安全与&合规中心修改预设安全策略的分配

修改标准保护或严格 **保护** 安全策略分配 **的** 步骤与初始向用户分配 [预设的安全策略时的相同](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。

当仍**保留现有条件**和**例外的同时，若要**禁用标准保护或严格保护安全策略，请将切换滑动到 **"已禁用"。** 若要启用策略，请将切换滑动 **到启用**。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否向用户成功分配了标准保护**Standard protection**或严**格**保护安全策略，请使用保护设置，其中默认值与标准保护设置不同，此设置与**严格保护设置不同**。 **Standard protection**

例如，对于检测为垃圾邮件的电子邮件 (非高可信度垃圾邮件) 验证此邮件是否是标准保护用户的"垃圾邮件 **"文件夹**，并已隔离为 **"严格保护用户"。**

或者，对于 [批量电子邮件，](bulk-complaint-level-values.md)请验证 BCL 值 6 或更高版本是否将邮件传递到标准保护用户的 **垃圾邮件文件夹，** 而 BCL 值 4 或更高则隔离此邮件以 **供严格保护** 用户使用。
