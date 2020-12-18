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
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中提供的防钓鱼策略。
ms.openlocfilehash: 7660516e60c77a7f31f711f78b6fd28d3ad179fd
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709700"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 中的防钓鱼策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


配置防钓鱼保护设置的策略适用于具有 Exchange Online 邮箱的 Microsoft 365 组织、没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织和适用于 Office 365 的 Microsoft Defender 组织。

Microsoft Defender for Office 365 中的反网络钓鱼策略仅适用于具有 Defender for Office 365 的组织。 For example:

- Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等
- [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)
- [作为加载项的 Microsoft Defender for Office 365](https://products.office.com/exchange/advance-threat-protection)

下表介绍了 EOP 中的反网络钓鱼策略与 Microsoft Defender for Office 365 中的反网络钓鱼策略之间的高级差异：

****

|功能|EOP 中的防钓鱼策略|Microsoft Defender for Office 365 中的防钓鱼策略|
|---|:---:|:---:|
|自动创建的默认策略|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|创建自定义策略|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|策略设置<sup>\*</sup>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|模拟设置||![复选标记](../../media/checkmark.png)|
|欺骗设置|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|高级网络钓鱼阈值||![复选标记](../../media/checkmark.png)|
|

<sup>\*</sup> 在默认策略中，策略名称和说明是只读的 (说明为空) ，并且你无法指定策略应用于 (默认策略应用于所有收件人) 。

若要配置防钓鱼策略，请参阅以下文章：

- [在 EOP 中配置反垃圾邮件策略](configure-anti-phishing-policies-eop.md)

- [在 Microsoft Defender for Office 365 中配置防钓鱼策略](configure-atp-anti-phishing-policies.md)

本文的其余部分介绍了 EOP 和 Defender for Office 365 中的反钓鱼策略中可用的设置。

## <a name="policy-settings"></a>策略设置

以下策略设置在 EOP 和 Microsoft Defender for Office 365 中的防钓鱼策略中可用：

- **名称**：无法重命名默认的防钓鱼策略，但您可以命名和重命名您创建的自定义策略。

- **说明** 无法向默认防钓鱼策略添加说明，但可以添加和更改所创建的自定义策略的说明。

- **应用于**：标识应用防钓鱼策略的内部收件人。 此值在自定义策略中是必需的，在默认策略 (默认策略应用于所有收件人) 。

  只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

  - **收件人为**：您组织中一个或多个邮箱、邮件用户或邮件联系人。
  - **收件人是组织中** 一个或多个组的成员。
  - **收件人域为**：Microsoft 365 中配置的一个或多个接受域。

  - **例外：** 规则例外。 设置和行为与条件完全相同：

    - **收件人为**
    - **收件人是**
    - **收件人域为**

  > [!NOTE]
  > 自定义 **防** 钓鱼策略中需要"应用于"设置，以标识策略应用于 <u>的邮件收件人</u>。 Microsoft Defender for Office 365 中的反网络钓鱼[](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)策略还具有模拟设置，可在其中指定将接收模拟保护的单个<u></u>发件人电子邮件地址或发件人域，如本文稍后所述。

## <a name="spoof-settings"></a>欺骗设置

欺骗是电子邮件中的发件人地址 (电子邮件客户端中显示发件人地址) 与电子邮件源的域不匹配。 有关欺骗功能详细信息，请参阅 [Microsoft 365](anti-spoofing-protection.md)中的反欺骗保护。

EOP 和 Microsoft Defender for Office 365 中的反网络钓鱼策略中提供了以下欺骗设置：

- **反欺骗保护**：启用或禁用反欺骗保护。 建议保持启用状态。 使用欺骗 **智能策略允许** 或阻止特定的欺骗内部和外部发件人。 有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

  > [!NOTE]
  >
  > - 默认情况下，在默认防钓鱼策略和您创建的任何新的自定义防钓鱼策略中启用反欺骗保护。
  >
  > - 如果 MX 记录未指向 Microsoft 365，无需禁用反欺骗保护;改为启用连接器的增强筛选。 有关说明，请参阅 [Exchange Online 中连接器的增强筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。
  >
  > - 禁用反欺骗保护仅禁用来自复合身份验证检查的 [隐式欺骗](email-validation-and-authentication.md#composite-authentication) 保护。 如果发件人未通过将策略设置为隔离或拒绝的显式 [DMARC](use-dmarc-to-validate-email.md) 检查，邮件仍将被隔离或拒绝。

  对于来自被阻止的欺骗发件人的邮件，还可以指定对邮件要采取的操作：

  - **将邮件移动到"垃圾邮件"文件夹**：这是默认值。 邮件将传递到邮箱并移动到"垃圾邮件"文件夹。 在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移动到"垃圾邮件"文件夹 (该邮件默认) 。 有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。

  - **隔离邮件**：将邮件发送到隔离邮箱，而不是目标收件人。 有关隔离的信息，请参阅以下文章：

    - [Microsoft 365 中的隔离](quarantine-email-messages.md)
    - [在 Microsoft 365 中以管理员角色管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Microsoft 365 中以用户状态查找并释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

- **未经身份验证的发件人**：请参阅下一节中的信息。

### <a name="unauthenticated-sender"></a>未经身份验证的发件人

未经身份验证的发件人标识是 EOP 和[](#spoof-settings)Microsoft Defender for Office 365 中的反网络钓鱼策略中提供的欺骗设置的一部分，如上一部分所述。

" **未经身份验证的发件人"** 设置在 Outlook 中启用或禁用未经身份验证的发件人标识。 具体来说：

- 如果邮件未通过 SPF 或 DKIM 检查，并且邮件未通过 DMARC 或复合身份验证，则向发件人的照片添加问号[ (？) 。](email-validation-and-authentication.md#composite-authentication) 禁用未经身份验证的发件人标识可防止将问号添加到发件人的照片中。

- 如果"发件人"地址 <u> (电子邮件</u> 客户端中显示的邮件发件人) 中的域不同于 DKIM 签名或 **MAIL FROM** 地址中的域，则添加通过 michelle@fabrikam.com) 的通过标记。 (chris@contoso.com 有关这些地址详细信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

  如果发件人地址中的域不同于 DKIM 签名中的域或 MAIL FROM 地址中的域，则禁用未经身份验证的发件人标识不会阻止添加通过标记。

若要阻止向来自特定发件人的邮件添加问号或通过标记，有以下选项：

- 允许发件人在欺骗智能策略中欺骗。 当禁用未经身份验证的发件人标识时，此操作将阻止通过标记出现在发件人的邮件中。 有关说明，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

- [为发件人域](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 配置电子邮件身份验证。
  - 对于发件人照片中的问号，SPF 或 DKIM 是最重要的。
  - 对于通过标记，请确认 DKIM 签名中的域或 **MAIL FROM** 地址与 (匹配，或是) 地址中域的子域。

有关详细信息，请参阅"识别 Outlook.com [和 Outlook 网页中的可疑邮件](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的独占设置

本部分介绍仅在 Microsoft Defender for Office 365 中的反网络钓鱼策略中可用的策略设置。

> [!NOTE]
> Microsoft Defender for Office 365 中的默认防钓鱼 [策略为所有](set-up-anti-phishing-policies.md#spoof-settings) 收件人提供欺骗保护和邮箱智能。 但是，其他可用的 [模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。 若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的模拟设置

模拟是邮件中发件人或发件人的电子邮件域看起来与真实发件人或域类似的地方：

- 域 contoso.com 的模拟示例是 ćóntoso.com。
- 用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。

模拟的域可能被视为合法（注册的域、配置的电子邮件身份验证记录等），但其意图是欺骗收件人。

以下模拟设置仅适用于 Microsoft Defender for Office 365 中的防钓鱼策略：

- **要保护的用户**：防止指定的内部或外部电子邮件地址被模拟 **为邮件发件人**。 例如，您收到来自公司副总裁的电子邮件，要求您向她发送一些内部公司信息。 是否执行？ 许多人在未思考的情况下发送回复。

  您可以使用受保护的用户添加内部和外部发件人电子邮件地址，防止模拟。 受 **用户模拟** 保护的发件人列表不同于策略应用于默认策略的所有 (收件人的收件人列表; 特定收件人，如"策略设置"部分"应用于"设置 [) 。](#policy-settings)

  > [!NOTE]
  >
  > - 在每个防钓鱼策略中，最多可以指定 60 个受保护的 (发件人电子邮件地址) 。 不能在多个策略中指定同一受保护用户。
  >
  > - 如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。 如果发件人和收件人从未通过电子邮件进行通信，邮件将被标识为模拟尝试。

  默认情况下，不会将发件人电子邮件地址配置为在用户中用于保护模拟 **保护**。 因此，默认情况下，默认策略或自定义策略中的模拟保护不会覆盖发件人电子邮件地址。

  向用户添加内部或外部电子邮件地址以保护列表时，来自这些发件人的邮件将接受模拟保护检查。 如果邮件发送到应用于默认策略 **的所有** 收件人的收件人，则检查 (是否模拟;**应用于自定义** 策略策略中的) 。 如果在发件人的电子邮件地址中检测到模拟，则用户的模拟保护操作将应用于邮件 (对邮件执行哪些操作，是否显示模拟用户安全提示等) 。

- **要保护的** 域：防止在邮件发件人的域中模拟 **指定的域**。 例如，你拥有的所有域 ([接受](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或 (域或合作伙伴域) 。 此 **防止模拟** 的发件人域列表不同于策略应用于默认策略的所有 (收件人的收件人列表;特定收件人，如"策略设置"部分"应用于"设置 [) 。](#policy-settings)

  > [!NOTE]
  > 可以在所有反网络钓鱼策略中定义的受保护域的最大数量为 50 个。

  默认情况下，不会将发件人域配置为在域中进行模拟 **保护以保护**。 因此，默认情况下，在默认策略或自定义策略中，模拟保护不会覆盖任何发件人域。

  当您将域添加到 **"域"以保护** 列表时，来自这些域中发件人的邮件将接受模拟保护检查。 如果邮件发送到应用于默认策略 **的所有** 收件人的收件人，则检查 (是否模拟;**应用于自定义** 策略策略中的) 。 如果在发件人域中检测到模拟，域的模拟保护操作将应用于邮件 (对邮件执行什么操作，是否显示模拟用户安全提示等) 。

- **针对受保护用户或域的操作**：选择要对入站邮件采取的操作，这些入站邮件包含针对策略中受保护用户和受保护域的模拟尝试。 可以指定用于模拟受保护用户与模拟受保护域的不同操作：

  - **不应用任何操作**

  - **将邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是目标收件人。

  - **将邮件移动到"垃圾邮件"文件夹**：邮件将传递到邮箱并移动到"垃圾邮件"文件夹。 在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移动到"垃圾邮件"文件夹 (该邮件默认) 。 有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。

    - **隔离邮件**：将邮件发送到隔离邮箱，而不是目标收件人。 有关隔离的信息，请参阅以下文章：

    - [Microsoft 365 中的隔离](quarantine-email-messages.md)
    - [在 Microsoft 365 中以管理员角色管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Microsoft 365 中以用户状态查找并释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

  - **传递邮件，将其他地址添加到"Bcc"** 行：将邮件传递至目标收件人，以静默方式将邮件发送给指定的收件人。

  - **在邮件传递之前删除** 邮件：以无提示方式删除整个邮件，包括所有附件。

- **安全提示**：启用或禁用以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：

  - **模拟用户**："来自"地址包含受保护的用户。
  - **模拟域**："来自"地址包含受保护的域。
  - **异常字符**：发件人地址包含异常字符集 (例如，数学符号和文本，或大写和小写字母) 在受保护的发件人或域中。

  > [!IMPORTANT]
  >
  > 即使关闭模拟安全提示，我们也建议您使用邮件流规则 (也称为传输规则) 来添加名为 **X-MS-Exchange-EnableFirstContactSafetyTip** 的邮件头，并启用对邮件的值。  安全提示将在收件人第一次收到来自发件人的邮件时或他们经常不从发件人获取邮件时通知收件人。
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="用于使用多个收件人进行模拟保护的安全提示文本。":::

- **邮箱智能**：启用或禁用 (AI) ，该智能技术可确定具有常用联系人的用户电子邮件模式。 此设置可帮助 AI 区分合法电子邮件和欺骗性电子邮件与这些联系人。 邮箱智能仅适用于 Exchange Online 邮箱。

- **基于邮箱智能的模拟保护**：启用或禁用基于每个用户的单个发件人映射的增强模拟结果。 此智能允许 Microsoft 365 自定义用户模拟检测并更好地处理误报。 检测到用户模拟时，可以定义对邮件执行的特定操作：

  - **不应用任何操作**
  - **将邮件重定向到其他电子邮件地址**
  - **将邮件移动到"垃圾邮件"文件夹**
  - **隔离邮件**
  - **传递邮件，将其他地址添加到"Bcc"行**
  - **在邮件传递之前删除邮件**

- **受信任的发件人和域**：模拟保护设置的例外。 来自指定发件人和发件人域的邮件从不被策略分类为基于模拟的攻击。 换句话说，对受保护的发件人、受保护的域或邮箱智能保护的操作不适用于这些受信任的发件人或发件人域。 这些列表的最大限制为大约 1000 个条目。

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的高级网络钓鱼阈值

以下高级网络钓鱼阈值仅适用于 Microsoft Defender for Office 365 中的防钓鱼策略。 这些阈值控制将机器学习模型应用到邮件以确定网络钓鱼裁定的敏感度：

- **1 - 标准**：这是默认值。 对邮件采取的操作的严重性取决于邮件是网络钓鱼邮件的可信度 (低、中、高或非常高) 。 例如，被标识为可信度非常高的网络钓鱼的邮件应用了最严重的操作，而被标识为低可信度的网络钓鱼的邮件应用了不太严重的操作。

- **2 - 积极**：被标识为高可信度的网络钓鱼的邮件被视为可信度非常高的邮件。

- **3 -** 更积极：被标识为具有中等或高可信度的网络钓鱼的邮件被视为可信度非常高的邮件。

- **4 -** 最积极：被标识为低、中或高可信度的网络钓鱼的邮件被视为可信度非常高的邮件。

当增加此设置时， (标记为错误) 误报的可能性会增加。 有关建议设置的信息，请参阅 [Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)设置中的防钓鱼策略。
