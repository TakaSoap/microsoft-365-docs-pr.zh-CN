---
title: 防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: 了解 Exchange Online Protection （EOP）中的基本反网络钓鱼策略和 Office 365 高级威胁防护中的高级 ATP 反网络钓鱼策略。
ms.openlocfilehash: f96b490d2c031fb509c39b2efdbc725cec2709a5
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537469"
---
# <a name="anti-phishing-policies-in-office-365"></a>Office 365 中的反网络钓鱼策略

在具有 Exchange Online 邮箱、独立 Exchange Online Protection （EOP）组织且无 Exchange Online 邮箱和 Office 365 高级威胁防护（ATP）组织的 Office 365 组织中，可以使用配置反网络钓鱼防护设置的策略。

ATP 反网络钓鱼策略仅在具有 Office 365 ATP 的组织中可用。 例如：

- Office 365 企业版 E5、Office 365 教育版 A5 等。
- [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)
- [作为附加项的 Office 365 ATP](https://products.office.com/exchange/advance-threat-protection)

ATP 反网络钓鱼策略包括内置默认反网络钓鱼策略，您可以创建其他自定义 ATP 反网络钓鱼策略。

其他 Office 365 组织（具有 Exchange Online 邮箱或独立 Exchange Online Protection （EOP）组织）没有 Exchange Online 邮箱的内置默认反网络钓鱼策略，但不能创建其他策略。 只有具有 Exchange Online 邮箱的组织才能修改其默认的反网络钓鱼策略。

反网络钓鱼策略和 ATP 反网络钓鱼策略之间的高级别差异如下表所述：

||||
|---|:---:|:---:|
|**功能**|**防钓鱼策略**|**ATP 反网络钓鱼策略**|
|自动创建的默认策略|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|创建自定义策略||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|策略设置<sup>\*</sup>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|模拟设置||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|欺骗设置|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|高级网络钓鱼阈值||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>在默认策略中，策略名称和说明为只读（说明为空），您不能指定策略应用于哪个用户（默认策略适用于所有收件人）。

若要配置反网络钓鱼策略，请参阅下列主题：

- [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)

- [在 Office 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)

本主题的其余部分介绍在 EOP 和 ATP 反网络钓鱼策略中可用的设置。

## <a name="spoof-settings"></a>欺骗设置

哄骗是指电子邮件中的发件人地址（电子邮件客户端中显示的发件人地址）与电子邮件源的域不匹配。 有关哄骗的详细信息，请参阅[Office 365 中的反欺骗保护](anti-spoofing-protection.md)。

以下欺骗设置在反网络钓鱼策略和 ATP 反网络钓鱼策略中可用：

- **反欺骗保护**：启用或禁用反欺骗保护。 建议您将其保留为启用状态。 您可以使用**欺骗智能策略**来允许或阻止特定的欺骗内部和外部发件人。 有关详细信息，请参阅[在 Office 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

  > [!NOTE]
  > 默认情况下，在 EOP 中默认的反网络钓鱼策略、默认 ATP 反网络钓鱼策略和创建的新自定义 ATP 反网络钓鱼策略中启用欺骗设置。 <br/><br/> 如果您的 MX 记录不指向 Office 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。 有关说明，请参阅[增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

  对于阻止欺骗发件人发送的邮件，您还可以指定对邮件执行的操作：

  - **将邮件移动到 "垃圾邮件" 文件夹**：这是默认值。 邮件传递到邮箱并移动到 "垃圾邮件" 文件夹。 在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则（默认情况下已启用），邮件将被移动到 "垃圾邮件" 文件夹中。 有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。 若要了解隔离，请参阅以下主题：

    - [Office 365 中的隔离](quarantine-email-messages.md)
    - [在 Office 365 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Office 365 中以用户身份查找和释放已隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

- **未经身份验证的发件人**：启用或禁用 Outlook 中未识别的发件人标识 具体来说：

  - 如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或[复合身份验证](email-validation-and-authentication.md#composite-authentication) **，** 则会将问号（？）添加到发件人的照片中。

  - 如果 "发件人" 地址（电子邮件客户端中显示的邮件发件人）中的域与 DKIM 签名中的域不同或**邮件 "发**件人" 地址中的域不同，则添加 via tag （chris@contoso.com <u>via</u> michelle@fabrikam.com）。 有关这些地址的详细信息，请参阅[电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  若要防止将这些标识符添加到特定发件人的邮件中，可以使用以下选项：

  - 允许发件人在欺骗智能策略中进行欺骗。 有关说明，请参阅[在 Office 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

  - 为发件人域[配置电子邮件身份验证](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。
  
    - 对于发件人照片中的问号，SPF 或 DKIM 是最重要的。
    - 对于 via 标记，确认域在 "DKIM" 签名中，或 "发件人地址中的**邮件**" 与 "发件人" 地址中的域（或为其子域）。

  有关详细信息，请参阅[识别可疑邮件在 Outlook.com 和 web 上的 Outlook](https://support.office.com/article/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的独占设置

本节介绍仅在 ATP 反网络钓鱼策略中可用的策略设置。

> [!NOTE]
> 默认情况下，未配置或打开 ATP 专用设置，即使在默认策略中也是如此。 若要利用这些功能，您需要在默认的 ATP 反网络钓鱼策略中启用和配置这些功能，或者创建和配置自定义 ATP 反网络钓鱼策略。

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的策略设置

以下策略设置仅适用于 ATP 反网络钓鱼策略：

- **名称**：无法重命名默认的反网络钓鱼策略，但可以命名和重命名所创建的自定义策略。

- **说明**您不能将说明添加到默认的反网络钓鱼策略中，但可以添加和更改所创建的自定义策略的说明。

- **应用**于：标识 ATP 反网络钓鱼策略应用于的内部收件人。 此值在自定义策略中是必需的，在默认策略中不可用（默认策略适用于所有收件人）。

    只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“且”逻辑（例如，_\<recipient1\>_ 且 _\<组成员 1\>_）。

  - **收件人为**：组织中的一个或多个邮箱、邮件用户或邮件联系人。
  - **收件人是**组织中的一个或多个组的成员：
  - **收件人域为**： Office 365 中的一个或多个已配置的接受域。

  - 例外情况**除外**：规则例外。 设置和行为与条件完全一样：

    - **收件人为**
    - **收件人是的成员**
    - **收件人域为**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的模拟设置

模拟是邮件中发件人或发件人的电子邮件域的外观与真实发件人或域非常相似：

- 域 contoso.com 的模拟示例是ćóntoso.com。

- 用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。

其他情况下，模拟域可能被视为合法的（注册域、配置的电子邮件身份验证记录等），但其目的是欺骗收件人。

以下模拟设置仅适用于 ATP 反网络钓鱼策略：

- **要保护的用户**：阻止模拟指定的内部或外部用户。 例如，高级管理人员（内部）和董事会成员（外部）。 您可以添加最高为60的内部和外部地址。 此受保护的用户列表与**应用**于设置的策略所适用的收件人列表不同。

  例如，在应用于名为 "主管" 的组的策略中，将 Felipe Apodaca （felipea@contoso.com）指定为受保护的用户。 向执行人员组的成员发送的入站邮件（其中 Felipe Apodaca 将被模拟）将由策略处理（为模拟用户配置的操作）。

- **要保护的域**：阻止模拟指定的域。 例如，您拥有的所有域（[接受域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)）或特定域（拥有或合作伙伴域的域）。 此受保护域的列表与**应用**于设置的策略所适用的域列表不同。

  例如，将 tailspintoys.com 指定为应用于名为 "主管" 的组成员的策略中的受保护域。 向执行人员组的成员发送的入站邮件将由策略对其中的 tailspintoys.com 进行处理（为模拟域配置的操作）。

- **针对受保护的用户或域的操作**：选择对入站邮件执行的操作，这些邮件包含对策略中的受保护用户和受保护域的模拟尝试。 您可以为受保护的用户和模拟的受保护域的模拟指定不同的操作：

  - **不应用任何操作**

  - 将**邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是发送给目标收件人。

  - **将邮件移动到 "垃圾邮件" 文件夹**：邮件将传递到邮箱并移动到 "垃圾邮件" 文件夹。 在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则（默认情况下已启用），邮件将被移动到 "垃圾邮件" 文件夹中。 有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

    - **隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。 若要了解隔离，请参阅以下主题：

    - [Office 365 中的隔离](quarantine-email-messages.md)
    - [在 Office 365 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Office 365 中以用户身份查找和释放已隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

  - **传递邮件并向 "密件抄送" 行添加其他地址**：将邮件传递给预期收件人，并以无提示方式将邮件传递给指定的收件人。

  - **邮件传递前将其删除**：悄悄删除整个邮件，包括所有附件。

- **安全提示**：启用或禁用以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：

  - **模拟用户**： "发件人" 地址包含受保护的用户。
  - **模拟域**： "发件人" 地址包含受保护的域。
  - **异常字符**： "发件人" 地址包含受保护的发件人或域中的异常字符集（例如，数学符号和文本或大写和小写字母的组合）。

- **邮箱智能**：启用或禁用用于确定用户的电子邮件模式与其常用联系人的人工智能（AI）。 此设置可帮助 AI 区分合法和欺骗的电子邮件与这些联系人。 邮箱智能仅适用于 Exchange Online 邮箱。

- **基于邮箱智能的模拟保护**：基于每个用户的个人发件人地图启用或禁用增强的模拟结果。 此智能允许 Office 365 自定义用户模拟检测，并更好地处理误报。 当检测到用户模拟时，您可以定义对邮件执行的特定操作：

  - **不应用任何操作**
  - **将邮件重定向到其他电子邮件地址**
  - **将邮件移动到 "垃圾邮件" 文件夹**
  - **隔离邮件**
  - **传递邮件并向 "密件抄送" 行添加其他地址**
  - **邮件传递前删除邮件**

- **受信任的发件人和域**：模拟保护设置的例外。 来自指定发件人和发件人域的邮件永远不会归为策略的基于模拟的攻击。 换句话说，受保护的发件人、受保护域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。 这些列表的最大限制约为1000个条目。

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的高级网络钓鱼阈值

以下高级网络钓鱼阈值仅在 ATP 反网络钓鱼策略中可用来指定如何处理检测到的网络钓鱼邮件：

- **1-Standard**：这是默认值。 对邮件执行的操作的严重性取决于邮件是网络钓鱼的置信度（低、中、高或非常高的可信度）。 例如，以非常高的可信度标识为网络钓鱼的邮件会应用最严重的操作，而标识为具有较低可信度的网络钓鱼的邮件则应用了较少的严重操作。

- **2-严格**：被标识为高度可信度的网络钓鱼的邮件被视为以非常高的可信度进行识别。

- **3-更主动**：被标识为中等或高可信度的网络钓鱼的邮件将被视为以非常高的可信度进行识别。

- **4-最严格**：被标识为低、中或高可信度的网络钓鱼的邮件被视为以非常高的置信度进行标识。

误报（正确的邮件被标记为坏）可能会随着此设置的增加而增加。 有关推荐设置的信息，请参阅[OFFICE ATP 反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。
