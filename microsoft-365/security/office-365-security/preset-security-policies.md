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
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 的保护功能中应用标准和严格的策略设置
ms.openlocfilehash: 38a03727f91878f356d8bc0dc618c711bfc500bb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845728"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 和 Microsoft Defender for Office 365 中的预设安全策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


预设安全策略提供了一个集中位置，用于一次性将所有建议的垃圾邮件、恶意软件和网络钓鱼策略应用于用户。 策略设置是不可配置的。 相反，它们由美国进行设置，并基于我们在数据中心中的观察和体验，以实现在不中断用户的情况下保持有害内容的平衡。

本主题的其余部分介绍了预设的安全策略以及如何对其进行配置。

## <a name="what-preset-security-policies-are-made-of"></a>组成的预设安全策略

预设安全策略包含以下元素：

- 配置文件
- 策略
- 策略设置

此外，如果多个预设安全策略和其他策略适用于同一个人，则优先级顺序非常重要。

### <a name="profiles-in-preset-security-policies"></a>预设安全策略中的配置文件

配置文件确定保护级别。 以下配置文件可用：

- **标准保护** ：适用于大多数用户的基准保护配置文件。
- **严格保护** ：针对所选用户的更为严格的保护配置文件 (高价值目标或优先级用户) 。

您将规则与条件和例外一起使用，以确定哪些配置文件是哪些或哪些不适用。

只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如， _\<recipient1\>_ 或 _\<recipient2\>_ ）。 不同的条件或例外使用“和”逻辑（例如， _\<recipient1\>_ 和 _\<member of group 1\>_ ）。

可用的条件和例外情况如下：

- **收件人为** ：组织中的邮箱、邮件用户或邮件联系人。
- **收件人是组织中的组的成员** 。
- **收件人域为** ：在 Microsoft 365 中配置的接受域。

### <a name="policies-in-preset-security-policies"></a>预设安全策略中的策略

预设安全策略使用 EOP 和 Microsoft Defender for Office 365 中的各种保护功能中对应的策略。 将 **标准保护** 或 **严格保护** 预设安全策略分配给用户 _后_ ，将创建这些策略。 您不能修改这些策略。

- **Exchange Online Protection (EOP) 策略** ：这包括具有 exchange online 邮箱和独立 EOP 组织的 Microsoft 365 组织，而无需使用 exchange online 邮箱：
  
  - 名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。
  - 名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [反恶意软件策略](configure-anti-malware-policies.md)。
  - EOP 欺骗设置 (的名为 **标准预设安全策略** 和 **严格预设安全策略**[的反网络钓鱼策略](set-up-anti-phishing-policies.md#spoof-settings)) 。

- **Microsoft Defender For office 365 策略** ：这包括具有 Microsoft 365 E5 或 Defender for office 365 附加订阅的组织：

  - Microsoft Defender for Office 365 中名为 **标准预设安全策略** 和 **严格预设安全策略** 的反网络钓鱼策略，其中包括：

    - EOP 反网络钓鱼策略中提供的相同 [欺骗设置](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [模拟设置](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高级网络钓鱼阈值](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - 名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [安全链接策略](set-up-atp-safe-links-policies.md)。

  - 名为 **标准预设安全策略** 和 **严格预设安全策略** 的 [安全附件策略](set-up-atp-safe-attachments-policies.md)。

请注意，您可以将 EOP 保护应用于与 Microsoft Defender for Office 365 保护不同的用户。

### <a name="policy-settings-in-preset-security-policies"></a>预设安全策略中的策略设置

不能在保护配置文件中修改策略设置。 [EOP 和 Microsoft Defender For Office 365 security 中的建议设置](recommended-settings-for-eop-and-office365-atp.md)中介绍了 **标准** 和 **严格** 的策略设置值。

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>预设安全策略和其他策略的优先级顺序

向用户应用多个策略时，将从最高优先级到最低优先级应用以下顺序：

1. **严格保护** 预设安全策略
2. **标准保护** 预设安全策略
3. 自定义安全策略
4. 默认安全策略

换言之， **严格保护** 策略的设置会覆盖 **标准保护** 策略的设置，这将覆盖自定义策略中的设置，这将覆盖默认策略中的设置。

## <a name="assign-preset-security-policies-to-users"></a>为用户分配预设的安全策略

### <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **预设安全策略** " 页，请使用 <https://protection.office.com/presetSecurityPolicies> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要配置预设安全策略，您必须是下列角色组之一的成员：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“ **组织管理** ”或“ **清洁管理** ”。

  - 若要对预设安全策略进行只读访问，您必须是下列角色组之一的成员：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“ **安全读取者** ”。
    - [安全 & 合规中心](permissions-in-the-security-and-compliance-center.md)中的 **全局读取器** 。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“ **仅查看组织管理** ”。

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>使用安全 & 合规性中心向用户分配预设的安全策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **预设安全策略** "。

2. 在 " **标准保护** 或 **严格保护** " 下，单击 " **编辑** "。

3. 将启动 " **应用标准保护** " 或 " **应用严格保护** " 向导。 在 **EOP 保护应用** 于步骤中，确定 [EOP 防护](#policies-in-preset-security-policies) 适用于的内部收件人：

   1. 单击 " **添加条件** "。 在出现的下拉列表中，选择 " **应用** 条件：

      - **收件人是**
      - **收件人是的成员**
      - **收件人域**

      仅可以使用一次条件，但可以为条件指定多个值。 同一条件的多个值使用或逻辑 (例如 _\<recipient1\>_ 或 _\<recipient2\>_ ) 。

   2. 选定的条件将显示在着色部分中。 在该部分中，单击 **任一** 框中的 ""。 如果你等待一段时间，将显示一个列表，以便你可以选择一个值。 或者，可以开始键入值来筛选列表并选择一个值。 根据需要重复执行此步骤（次数不限）。 若要删除单个值，请单击值上的 " **删除** ![ 删除 ](../../media/scc-remove-icon.png) " 图标。 若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。

   3. 若要添加其他条件，请单击 " **添加条件** "，然后从其余条件中进行选择。 不同的条件使用和逻辑 (例如， _\<recipient1\>_ 和 _\<member of group 1\>_ ) 。

      重复上一步以向条件中添加值，并根据需要多次重复此步骤，或在条件不足之前重复此步骤。

   4. 若要添加例外，请单击 " **添加条件** "。 在出现的下拉列表中，选择 " **如果条件除外** " 下的条件。 设置和行为与条件完全相同。

   完成后，单击“下一步”。

4. 如果你的组织具有 Microsoft Defender for Office 365，则将转到 **ATP 防护适用** 于步骤，以确定 [Microsoft defender for Office 365 防护](#policies-in-preset-security-policies) 适用的内部收件人。

   设置和行为与 **EOP 保护应用** 于步骤完全一样。

   完成后，单击“下一步”。

5. 在 " **确认** 步骤" 中，验证您的选择，然后单击 " **确认** "。

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>使用安全 & 合规性中心修改预设安全策略的分配

修改 **标准保护** 或 **严格保护** 安全策略分配的步骤与最初 [向用户分配预设安全策略](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)的步骤相同。

若要禁用 **标准保护** 或 **严格保护** 安全策略，同时仍保留现有条件和例外，请将开关滑动到 " **已禁用** "。 若要启用这些策略，请将开关滑动到 " **已启用** "。

### <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功将 **标准保护** 或 **严格保护** 安全策略分配给用户，请使用默认值不同于 **标准保护** 设置的保护设置，该设置不同于 **严格的保护** 设置。

例如，对于检测为垃圾邮件的电子邮件 (不高可信度垃圾邮件) 验证是否将邮件传递到 **标准保护** 用户的 "垃圾邮件" 文件夹，并为 **严格的保护** 用户隔离。

或者，对于 [批量电子邮件](bulk-complaint-level-values.md)，请验证 BCL 值6或更高将邮件传递到 **标准保护** 用户的 "垃圾邮件" 文件夹，bcl 值4或更高版本将隔离邮件的 **严格保护** 用户。
