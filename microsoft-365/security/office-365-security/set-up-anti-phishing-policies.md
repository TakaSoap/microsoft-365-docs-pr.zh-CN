---
title: 防钓鱼策略
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
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护 (Office 365 ATP) 中提供的反网络钓鱼策略。
ms.openlocfilehash: 498b6e27b3fca66e388eaa27ba7895056ef7f0fc
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326933"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 中的反网络钓鱼策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


使用 Exchange Online 邮箱、独立 Exchange Online Protection (EOP) 组织（无 Exchange Online 邮箱）和 Office 365 高级威胁防护 (Office 365 ATP) 组织的 Microsoft 365 组织中提供了用于配置反钓鱼保护设置的策略。

ATP 反网络钓鱼策略仅在具有 Office 365 ATP 的组织中可用。 例如：

- Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等。
- [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)
- [作为附加项的 Office 365 ATP](https://products.office.com/exchange/advance-threat-protection)

所有其他组织都具有反网络钓鱼策略。

反网络钓鱼策略和 ATP 反网络钓鱼策略之间的高级别差异如下表所述：

****

|功能|防钓鱼策略|ATP 反网络钓鱼策略|
|---|:---:|:---:|
|自动创建的默认策略|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|创建自定义策略|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|策略设置<sup>\*</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|模拟设置||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|欺骗设置|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|高级网络钓鱼阈值||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> 在默认策略中，"策略名称" 和 "说明" 是只读的 (说明为空) ，您不能指定该策略应用于的用户 (默认策略将应用于) 的所有收件人。

若要配置反网络钓鱼策略，请参阅以下文章：

- [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)

- [在 Microsoft 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)

本文的其余部分介绍了反网络钓鱼策略和 ATP 反网络钓鱼策略中提供的设置。

## <a name="policy-settings"></a>策略设置

以下策略设置在反网络钓鱼策略和 ATP 反网络钓鱼策略中可用：

- **名称**：无法重命名默认的反网络钓鱼策略，但可以命名和重命名所创建的自定义策略。

- **说明** 您不能将说明添加到默认的反网络钓鱼策略中，但可以添加和更改所创建的自定义策略的说明。

- **应用**于：标识应用了反网络钓鱼策略的内部收件人。 此值在自定义策略中是必需的，在默认策略中不可用 (默认策略适用于) 的所有收件人。

  只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

  - **收件人为**：组织中的一个或多个邮箱、邮件用户或邮件联系人。
  - **收件人是**组织中的一个或多个组的成员：
  - **收件人域为**： Microsoft 365 中已配置的一个或多个接受的域。

  - 例外情况**除外**：规则例外。 设置和行为与条件完全一样：

    - **收件人为**
    - **收件人是的成员**
    - **收件人域为**

  > [!NOTE]
  > "**应用于**" 设置在自定义反网络钓鱼策略中是必需的，以标识这些<u>策略应用于的</u>邮件**收件人**。 ATP 反网络钓鱼策略还具有 [模拟设置](#impersonation-settings-in-atp-anti-phishing-policies) ，您可以在其中指定 <u>将接收模拟保护的</u> 单个发件人电子邮件地址或发件人域，如本主题后面所述。

## <a name="spoof-settings"></a>欺骗设置

哄骗是指电子邮件中的发件人地址 (在电子邮件客户端中显示的发件人地址) 与电子邮件源的域不匹配。 有关哄骗的详细信息，请参阅 [Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)。

以下欺骗设置在反网络钓鱼策略和 ATP 反网络钓鱼策略中可用：

- **反欺骗保护**：启用或禁用反欺骗保护。 建议您将其保留为启用状态。 您可以使用 **欺骗智能策略** 来允许或阻止特定的欺骗内部和外部发件人。 有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

  > [!NOTE]
  > 默认情况下，在 EOP 的默认反网络钓鱼策略中启用了欺骗设置、默认的 ATP 反网络钓鱼策略，以及您创建的新的自定义反网络钓鱼策略或 ATP 反网络钓鱼策略。 <br/><br/> 如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。 有关说明，请参阅 [增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

  对于阻止欺骗发件人发送的邮件，您还可以指定对邮件执行的操作：

  - **将邮件移动到 "垃圾邮件" 文件夹**：这是默认值。 邮件传递到邮箱并移动到 "垃圾邮件" 文件夹。 在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移至 "垃圾邮件" 文件夹 (默认情况下，将启用该规则) 。 有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。 有关隔离的信息，请参阅以下文章：

    - [Microsoft 365 中的隔离](quarantine-email-messages.md)
    - [在 Microsoft 365 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Microsoft 365 中查找并以用户的形式发布隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

- **未经身份验证的发件人**：请参阅下一节中的信息。

### <a name="unauthenticated-sender"></a>未经身份验证发件人

未经身份验证的发件人标识是反网络钓鱼策略和 ATP 反网络钓鱼策略中提供的 [欺骗设置](#spoof-settings) 的一部分，如上一节中所述。

**未经身份验证的发件人**设置启用或禁用 Outlook 中未经验证的发件人标识。 具体来说：

- 如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或[复合身份验证](email-validation-and-authentication.md#composite-authentication) **，** 则会将 ) 添加到发件人的照片中的 ( 问号。 禁用未经身份验证的发件人标识可防止将问号添加到发件人的照片中。

- 如果 "发件人" 地址中的域 (电子邮件客户) 端中显示的邮件发件人不同于 DKIM 签名中的域或**邮件的 "发**件人" 地址中的域，则会添加 via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) 。 有关这些地址的详细信息，请参阅 [电子邮件标准的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

  如果 "发件人" 地址中的域不同于 DKIM 签名中的域或邮件的 "发件人" 地址中的域，禁用未经身份验证的发件人标识将不会阻止添加 via 标记。

若要防止将问号或 via 标记添加到特定发件人的邮件中，可以使用以下选项：

- 允许发件人在欺骗智能策略中进行欺骗。 当禁用未经身份验证的发件人标识时，此操作将阻止来自发件人的邮件中显示的 via 标记。 有关说明，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

- 为发件人域[配置电子邮件身份验证](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。
  
  - 对于发件人照片中的问号，SPF 或 DKIM 是最重要的。
  - 对于 via 标记，确认 DKIM 签名中的域，或 "发 **件人地址匹配** (" 或 "发件人地址中) 域的子域"。

有关详细信息，请参阅 [识别可疑邮件在 Outlook.com 和 web 上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的独占设置

本节介绍仅在 ATP 反网络钓鱼策略中可用的策略设置。

> [!NOTE]
> 默认情况下，未配置或打开 ATP 专用设置，即使在默认策略中也是如此。 若要利用这些功能，您需要在默认的 ATP 反网络钓鱼策略中启用和配置这些功能，或者创建和配置自定义 ATP 反网络钓鱼策略。

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的模拟设置

模拟是邮件中发件人或发件人的电子邮件域类似于真实的发件人或域：

- 域 contoso.com 的模拟示例是 ćóntoso.com。
- 用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。

模拟的域可能被视为合法（注册的域、配置的电子邮件身份验证记录等），但其意图是欺骗收件人。

以下模拟设置仅适用于 ATP 反网络钓鱼策略：

- **要保护的用户**：阻止将指定的内部或外部电子邮件地址模拟 **为邮件发件人**。 例如，主管 (内部发件人) 和董事会成员 (外部发件人) 。 您可以添加最高为60的内部和外部发件人电子邮件地址，以防止模拟。 受模拟保护的 **发件人** 列表与该策略所应用于的 **收件人** 列表不同。

  默认策略适用于发送给所有收件人的邮件，而自定义策略仅适用于发送到您在 "[策略设置](#policy-settings)" 部分中所述的 "**应用于**" 设置中定义的收件人的邮件。

  默认情况下，不会为 **要保护的用户**中的模拟保护配置发件人电子邮件地址。 因此，在默认策略或自定义策略中，默认情况下，模拟保护不会覆盖任何发件人的电子邮件地址。

  将内部或外部电子邮件地址添加到 " **要保护的用户** " 列表中时，来自这些 **发件人** 的邮件将受到模拟保护检查。 **如果**将邮件发送给**收件人**，该邮件将被检查以模拟邮件，以确保该邮件应用于默认策略的所有收件人 (。**应用**于自定义策略) 中的收件人。 如果在发件人的电子邮件地址中检测到模拟，用户的模拟保护操作将应用于邮件， (邮件上的操作、模拟的用户安全提示等 ) 。

- **要保护的域**：阻止 **在邮件发件人的域中**模拟指定的域。 例如，您拥有的所有域都 ([接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或拥有您拥有的域或合作伙伴域) 的特定域 (域。 受模拟保护的 **发件人域** 的列表与该策略所应用于的 **收件人** 列表不同。

  默认策略适用于发送给所有收件人的邮件，而自定义策略仅适用于发送到您在 "[策略设置](#policy-settings)" 部分中所述的 "**应用于**" 设置中定义的收件人的邮件。

  默认情况下，不会为 **要保护的域**中的模拟保护配置任何发件人域。 因此，在默认策略或自定义策略中，默认情况下，模拟保护不会覆盖任何发件人域。

  将域添加到 " **要保护的域** " 列表中时，来自 **这些域中发件人** 的邮件将受到模拟保护检查。 **如果**将邮件发送给**收件人**，该邮件将被检查以模拟邮件，以确保该邮件应用于默认策略的所有收件人 (。**应用**于自定义策略) 中的收件人。 如果在发件人的域中检测到模拟，则域的模拟保护操作将应用于邮件 (邮件上的操作、模拟的域安全提示等 ) 。

- **针对受保护的用户或域的操作**：选择对入站邮件执行的操作，这些邮件包含对策略中的受保护用户和受保护域的模拟尝试。 您可以为受保护的用户和模拟的受保护域的模拟指定不同的操作：

  - **不应用任何操作**

  - 将**邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是发送给目标收件人。

  - **将邮件移动到 "垃圾邮件" 文件夹**：邮件将传递到邮箱并移动到 "垃圾邮件" 文件夹。 在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移至 "垃圾邮件" 文件夹 (默认情况下，将启用该规则) 。 有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

    - **隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。 有关隔离的信息，请参阅以下文章：

    - [Microsoft 365 中的隔离](quarantine-email-messages.md)
    - [在 Microsoft 365 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Microsoft 365 中查找并以用户的形式发布隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

  - **传递邮件并向 "密件抄送" 行添加其他地址**：将邮件传递给预期收件人，并以无提示方式将邮件传递给指定的收件人。

  - **邮件传递前将其删除**：悄悄删除整个邮件，包括所有附件。

- **安全提示**：启用或禁用以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：

  - **模拟用户**： "发件人" 地址包含受保护的用户。
  - **模拟域**： "发件人" 地址包含受保护的域。
  - **异常字符**： From 地址包含不寻常的字符集 (例如，数学符号和文本，或者在受保护的发件人或域中的大写和小写字母的组合) 。

  > [!NOTE]
  > 即使关闭了模拟安全提示，也可以使用邮件流规则 (也称为传输规则) 将名为 **X-MS-EnableFirstContactSafetyTip** 的邮件头添加到邮件中。 将显示特定安全提示，通知收件人通常不会从发件人收到电子邮件，或者当收件人首次从发件人获取电子邮件时，会收到通知。

- **邮箱智能**：启用或禁用用于确定用户的电子邮件模式与其常用联系人的智能 (AI) 。 此设置可帮助 AI 区分合法和欺骗的电子邮件与这些联系人。 邮箱智能仅适用于 Exchange Online 邮箱。

- **基于邮箱智能的模拟保护**：基于每个用户的个人发件人地图启用或禁用增强的模拟结果。 此智能允许 Microsoft 365 自定义用户模拟检测，并更好地处理误报。 当检测到用户模拟时，您可以定义对邮件执行的特定操作：

  - **不应用任何操作**
  - **将邮件重定向到其他电子邮件地址**
  - **将邮件移动到 "垃圾邮件" 文件夹**
  - **隔离邮件**
  - **传递邮件并向 "密件抄送" 行添加其他地址**
  - **邮件传递前删除邮件**

- **受信任的发件人和域**：模拟保护设置的例外。 来自指定发件人和发件人域的邮件永远不会归为策略的基于模拟的攻击。 换句话说，受保护的发件人、受保护域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。 这些列表的最大限制约为1000个条目。

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>ATP 反网络钓鱼策略中的高级网络钓鱼阈值

以下高级网络钓鱼阈值仅在 ATP 反网络钓鱼策略中可用，以控制将机器学习模型应用于邮件以确定仿冒判定的邮件的灵敏度：

- **1-Standard**：这是默认值。 对邮件执行的操作的严重性取决于邮件是网络钓鱼 (低、中、高或非常高的可信度) 的可信度程度。 例如，以非常高的可信度标识为网络钓鱼的邮件会应用最严重的操作，而标识为具有较低可信度的网络钓鱼的邮件则应用了较少的严重操作。

- **2-严格**：被标识为高度可信度的网络钓鱼的邮件被视为以非常高的可信度进行识别。

- **3-更主动**：被标识为中等或高可信度的网络钓鱼的邮件将被视为以非常高的可信度进行识别。

- **4-最严格**：被标识为低、中或高可信度的网络钓鱼的邮件被视为以非常高的置信度进行标识。

误报 (正常的可能性可能会随着此设置的增加而被标记为坏) 。 有关推荐设置的信息，请参阅 [ATP 反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings)。
