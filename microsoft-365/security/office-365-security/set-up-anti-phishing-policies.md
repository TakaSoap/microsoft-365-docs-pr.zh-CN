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
ms.localizationpriority: medium
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP Exchange Online Protection (和 Microsoft Defender for) 中提供的防钓鱼Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d4e0cb56d6aad0b26bea145439b806080982dfe5
ms.sourcegitcommit: 7b83e2605895fee5c73cd1d01f4cd16e1457a69f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60907917"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

配置防钓鱼保护设置的策略适用于具有 Exchange Online 邮箱的 Microsoft 365 组织、没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织以及 Microsoft Defender forOffice 365组织。

适用于组织的 Microsoft Defender Office 365包括：

- Microsoft 365 企业版E5、Microsoft 365 教育版 A5 等。
- [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender Office 365加载项](https://products.office.com/exchange/advance-threat-protection)

下表介绍了 EOP 中的反网络钓鱼策略与 Defender for Office 365 中的反网络钓鱼策略之间的高级差异：

<br>

****

|功能|EOP 中的防钓鱼策略|Defender for Office 365 中的防钓鱼策略|
|---|:---:|:---:|
|自动创建的默认策略|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|创建自定义策略|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|常见策略设置<sup>\*</sup>|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|欺骗设置|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|第一个联系人安全提示|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|模拟设置||![复选标记](../../media/checkmark.png)|
|高级网络钓鱼阈值||![复选标记](../../media/checkmark.png)|
|

<sup>\*</sup> 在默认策略中，策略名称和说明是只读的 (说明为空) ，并且你无法指定策略应用于哪些人 (默认策略将应用于) 。

若要配置防钓鱼策略，请参阅以下文章：

- [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)
- [在 Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md)

本文的其余部分介绍了 EOP 和 Defender for Office 365 中的防钓鱼策略中可用的设置。

## <a name="common-policy-settings"></a>常见策略设置

以下策略设置在 EOP 和 Defender for Office 365 中的防钓鱼策略中Office 365：

- **名称**：无法重命名默认的防钓鱼策略。 创建自定义防钓鱼策略后，无法在此门户中重命名Microsoft 365 Defender策略。

- **说明** 无法向默认反网络钓鱼策略添加说明，但可以添加和更改所创建的自定义策略的说明。

- **用户、组和域**：标识应用防钓鱼策略的内部收件人。 此值在自定义策略中是必需的，在默认策略中 (默认策略应用于所有收件人) 。

  只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

  - **用户**：组织中一个或多个邮箱、邮件用户或邮件联系人。
  - **组**：您的组织中的一个或多个组。
  - **域**：域中配置的一个或多个 [接受](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)Microsoft 365。

  - **排除这些用户、组和域**：策略的例外。 设置和行为与条件完全相同：
    - **用户**
    - **组**
    - **域**

  > [!NOTE]
  > 自定义防钓鱼策略中至少需要选择"用户、组和域"设置中的一个选项，以标识策略应用于<u>的邮件收件人</u>。 Defender for Office 365 中的反网络钓鱼策略还具有模拟设置[](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)，可在其中指定将接收模拟保护的单个发件人电子邮件地址或发件人域<u></u>，如本文稍后所述。

## <a name="spoof-settings"></a>欺骗设置

欺骗是电子邮件中的发件人地址 (电子邮件客户端中显示的发件人地址) 与电子邮件源的域不匹配。 有关欺骗功能详细信息，请参阅 Microsoft 365[中的反欺骗Microsoft 365。](anti-spoofing-protection.md)

EOP 和 Defender for Office 365 中的反网络钓鱼策略中提供了以下欺骗Office 365：

- **启用欺骗智能**：打开或关闭欺骗智能。 建议将其保持打开。

  启用欺骗智能后， **欺骗** 智能见解会显示欺骗智能自动检测、允许或阻止的欺骗发件人。 你可以手动替代欺骗智能裁定，以允许或阻止在见解中检测到的欺骗性发件人。 但当你这样做时，欺骗的发件人将从欺骗智能见解中消失，并且现在仅在租户允许/阻止列表中的"欺骗"选项卡上可见。 还可以在租户允许/阻止列表中手动为欺骗性发件人创建允许或阻止条目。 有关更多信息，请参阅下面的文章：

  - [EOP 中的欺骗智能见解](learn-about-spoof-intelligence.md)
  - [在 EOP 中管理租户允许/阻止列表](tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - 默认情况下，在默认防钓鱼策略和您创建的任何新的自定义防钓鱼策略中启用反欺骗保护。
  > - 如果你的 MX 记录没有指向安全位置，你无需禁用反欺骗Microsoft 365;改为启用连接器的增强筛选。 有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  > - 禁用反欺骗保护只会禁用来自复合身份验证检查的隐式[欺骗](email-validation-and-authentication.md#composite-authentication)保护。 如果发件人未 _通过显式_ [DMARC](use-dmarc-to-validate-email.md) 检查，则策略被设置为隔离或拒绝，邮件仍将被隔离或拒绝。

- **未经身份验证的发件人通知**：这些通知仅在启用欺骗智能时可用。 请参阅下一节中的信息。
- **操作**：对于来自被阻止的欺骗 (发件人的邮件自动被欺骗智能阻止或在租户允许/阻止列表) 中手动阻止，还可以指定对邮件采取的操作：
  - **将邮件移动到收件人的"垃圾邮件"文件夹**：这是默认值。 邮件将传递到邮箱，并移动到"垃圾邮件"文件夹。 有关详细信息，请参阅 Configure [junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)。
  - **隔离邮件**：将邮件发送到隔离邮箱，而不是目标收件人。 若要了解隔离，请参阅以下文章：
    - [隔离Microsoft 365](quarantine-email-messages.md)
    - [以管理员角色管理隔离的邮件和Microsoft 365](manage-quarantined-messages-and-files.md)
    - [以用户模式查找并释放隔离Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

    如果选择" **隔离邮件"，** 还可以选择适用于被欺骗智能保护隔离的邮件的隔离策略。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

### <a name="unauthenticated-sender"></a>未经身份验证的发件人

未经身份验证的发件人通知是 EOP 和[](#spoof-settings)Defender for Office 365 反网络钓鱼策略中提供的欺骗设置的一部分，如上一部分所述。 以下设置仅在启用欺骗智能时可用：

- **显示 (？)** 欺骗的未经身份验证的发件人：如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或复合身份验证，此通知会将问号添加到发件人的照片的"发件人"框中 [。](email-validation-and-authentication.md#composite-authentication) 关闭此设置后，不会将问号添加到发件人的照片中。

- 显示 **"通过"标记？：** 如果"发件人"地址 (中显示的邮件发件人) 中的域不同于 DKIM 签名或 MAIL **FROM** 地址中的域，此通知将在"发件人"框中通过 <u>fabrikam.com)</u>添加通过标记 (chris@contoso.com。 有关这些地址详细信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

若要防止向来自特定发件人的邮件添加问号或通过标记，可以使用以下选项：

- 允许在欺骗智能见解 [中或手动](learn-about-spoof-intelligence.md) 在租户允许/阻止列表中允许 [欺骗发件人](tenant-allow-block-list.md)。 禁用未经身份验证的发件人标识后，允许欺骗发件人将阻止在发件人发送的邮件中显示 via 标记。
- [为发件人域](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 配置电子邮件身份验证。
  - 对于发件人照片中的问号，SPF 或 DKIM 是最重要的。
  - 对于 via 标记，确认 DKIM 签名中的域或 **MAIL FROM** 地址 (或是"收件人"地址) 域的子域。

有关详细信息，请参阅在[Outlook.com](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)和 Outlook 网页版

## <a name="first-contact-safety-tip"></a>第一个联系人安全提示

"**显示第一安全提示** 联系人"设置在 EOP 和 Defender 中对 Office 365 组织可用，并且不依赖于欺骗智能或模拟保护设置。 以下安全提示向收件人显示该邮件：

- 他们第一次从发件人收到邮件时
- 他们通常不会收到来自发件人的邮件。

![对于具有安全提示的邮件，请首先联系联系人。](../../media/safety-tip-first-contact-one-recipient.png)

![对于具有安全提示的邮件，请首先联系联系人。](../../media/safety-tip-first-contact-multiple-recipients.png)

此功能添加了一层额外的安全保护，防止潜在的模拟攻击，因此我们建议您将其打开。

第一个联系人 安全提示 也无需创建邮件流规则 (也称为传输规则) ，该规则添加名为 **X-MS-Exchange-EnableFirstContactSafetyTip** 的邮件头和值 **Enable** to messages (尽管此功能在) 中仍然可用。

> [!NOTE]
> 如果邮件具有多个收件人，则提示是否显示以及基于多数模型的收件人。 如果大多数收件人从未收到或经常收到来自发件人的邮件，则受影响的收件人将收到"某些收到此邮件 **的人..."** 提示。 如果您担心此行为会向另一个收件人公开一个收件人的通信习惯，则不应启用第一个联系人安全提示而是继续使用邮件流规则。

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的独占Office 365

本部分介绍仅在 Defender for Office 365 中的反网络钓鱼策略中可用的策略Office 365。

> [!NOTE]
> Defender for Office 365[中的默认](set-up-anti-phishing-policies.md#spoof-settings)防钓鱼策略可为所有收件人提供欺骗保护和邮箱智能。 但是，其他 [可用的模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。 若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的防钓鱼策略中的模拟Office 365

模拟是邮件中的发件人或发件人的电子邮件域看起来类似于真实发件人或域的情况：

- 域 contoso.com 的模拟示例是 ćóntoso.com。
- 用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。

> [!NOTE]
> 模拟保护查找类似域。 例如，如果你的域 contoso.com，我们会检查不同的顶级域（A0.com、.biz 等) 作为模拟尝试，但也检查一些类似的域。 例如，contosososo.com 或 contoabcdef.com 可能会被视为模拟尝试 contoso.com。

模拟的域可能被视为合法（注册的域、配置的电子邮件身份验证记录等），但其意图是欺骗收件人。

以下模拟设置仅在 Defender for Office 365 中的防钓鱼策略中Office 365：

- **允许用户保护**：防止指定的内部或外部电子邮件地址被模拟 **为邮件发件人**。 例如，您收到一封来自公司副总裁的电子邮件，要求您向她发送一些内部公司信息。 是否执行？ 许多人在未思考的情况下发送回复。

  您可以使用受保护的用户添加内部和外部发件人电子邮件地址，防止模拟。 此 **受用户** 模拟保护的发件人列表不同于策略应用于默认策略的所有 (收件人的收件人列表;特定收件人，如"通用策略设置"部分"用户、组和域"[](#common-policy-settings)设置) 。

  > [!NOTE]
  >
  > - 在每个防钓鱼策略中，最多可指定 350 个受保护 (发件人电子邮件地址) 。 不能在多个策略中指定同一受保护的用户。 因此，无论向收件人应用多少策略，每个收件人 (发件人电子邮件地址) 用户数量上限为 350。 有关策略优先级以及策略处理如何在应用第一个策略后停止的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。
  > - 如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。 如果发件人和收件人从未通过电子邮件进行通信，则邮件将被标识为模拟尝试。

  默认情况下，不会将发件人电子邮件地址配置为在"用户"中用于保护的 **模拟保护**。 因此，默认情况下，在默认策略或自定义策略中，模拟保护不会覆盖发件人电子邮件地址。

  当您将内部或外部电子邮件地址添加到"用户保护"列表时，来自这些发件人的邮件将接受模拟保护检查。 如果邮件发送到应用于默认策略的所有收件人的收件人，则检查 (是否模拟;**自定义策略中的** 用户、组和域) 。 如果在发件人的电子邮件地址中检测到模拟，则用户模拟保护操作将应用于邮件 (对邮件执行哪些操作，是否显示模拟用户安全提示等) 。

- **启用域进行保护**：阻止在邮件发件人的域中 **模拟指定的域**。 例如，你拥有的所有域 (接受) 或特定自定义[](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) (或合作伙伴域) 。 受模拟 **保护** 的发件人域列表不同于策略应用于默认策略的所有 (收件人的收件人列表;特定收件人，如"通用策略设置"部分"用户、组和域"[](#common-policy-settings)设置) 。

  > [!NOTE]
  > 可以在所有反网络钓鱼策略中定义的受保护域的最大数量为 50 个。

  默认情况下，在"启用域保护"中，不会为模拟保护 **配置任何发件人域**。 因此，默认情况下，在默认策略或自定义策略中，模拟保护不会覆盖任何发件人域。

  将域添加到"**启用域保护"列表** 时，来自这些域中发件人的邮件将接受模拟保护检查。 如果邮件发送到应用于默认策略的所有收件人的收件人，则检查 (是否模拟;**自定义策略中的** 用户、组和域) 。 如果在发件人域中检测到模拟，则域的模拟保护操作将应用于邮件 (以及对邮件执行哪些操作、是否显示模拟用户安全提示等) 。

- **操作**：选择要对入站邮件采取的操作，这些入站邮件包含针对策略中受保护的用户和受保护域的模拟尝试。 您可以指定用于模拟受保护用户与模拟受保护域的不同操作：
  - **不应用任何操作**
  - **将邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是目标收件人。
  - **将邮件移动到收件人的"垃圾邮件"文件夹**：邮件被传递到邮箱并移动到"垃圾邮件"文件夹。 有关详细信息，请参阅 Configure [junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)。
  - **隔离邮件**：将邮件发送到隔离邮箱，而不是目标收件人。 若要了解隔离，请参阅以下文章：
    - [隔离Microsoft 365](quarantine-email-messages.md)
    - [以管理员角色管理隔离的邮件和Microsoft 365](manage-quarantined-messages-and-files.md)
    - [以用户模式查找并释放隔离Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

    如果选择" **隔离邮件"，** 则还可以选择适用于由用户模拟或域模拟保护隔离的邮件的隔离策略。 隔离策略定义用户可以对隔离邮件执行哪些操作。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

  - **传递邮件，将其他地址添加到"Bcc"** 行：将邮件传递至目标收件人，以静默方式将邮件传递至指定的收件人。
  - **在邮件传递之前删除邮件**：以静默方式删除整个邮件，包括所有附件。

- **模拟安全提示**：打开或关闭以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：
  - **显示模拟用户的提示**："自"地址包含" **允许用户保护用户** "。 仅在启用 **和配置** "启用用户保护"时可用。
  - **显示模拟域的提示**："自"地址包含" **允许域保护域** "。 仅在启用 **要保护的域** 已打开并配置时可用。
  - 显示异常字符的提示：发件人地址包含异常字符集 (例如，在"允许用户保护发件人"或"使域能够保护发件人域"中混合使用大写和小写字母) 例如，数学符号和文本。   仅在启用 **用户保护或**_启用_ 要保护的域打开并配置时可用。

- **启用邮箱智能**：启用或禁用 (AI) ，该智能智能功能可确定具有常用联系人的用户电子邮件模式。 此设置可帮助 AI 区分来自合法发件人和模拟发件人的邮件。

  例如，一 (glaureano@contoso.com) 一位用户是公司的 CEO，因此在"允许用户保护策略设置"中将她添加为受保护的发件人。  但是，应用该策略的一些收件人会定期与一个名为"一名为一名的 Vendora Laureano (glaureano@fabrikam.com) "。 由于这些收件人具有与 glaureano@fabrikam.com 的通信历史记录，因此邮箱智能不会将来自 glaureano@fabrikam.com 的邮件识别为这些 glaureano@contoso.com 的模拟尝试。

  若要使用邮箱智能用户学习的常用联系人 (并且缺少其他) 以帮助保护用户免受模拟攻击，可以在启用邮箱智能后启用智能模拟 **保护**。 

- **启用智能模拟保护**：打开此设置可指定对邮件执行哪些操作以从邮箱智能结果进行模拟检测：
  - **不要应用任何操作**：请注意，此值与启用邮箱智能但关闭启用智能模拟保护具有相同的 **结果**。
  - **将邮件重定向到其他电子邮件地址**
  - **将邮件移动到收件人的"垃圾邮件"文件夹**
  - **隔离邮件**：如果选择此操作，还可以选择适用于由邮箱智能保护隔离的邮件的隔离策略。 隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。
  - **传递邮件，将其他地址添加到"Bcc"行**
  - **在邮件传递之前删除邮件**

- **添加受信任的发件人和域**：模拟保护设置例外。 策略不会将来自指定发件人和发件人域的邮件分类为基于模拟的攻击。 换句话说，对受保护的发件人、受保护的域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。 这些列表的最大限制为 1024 个条目。

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的反网络钓鱼策略中的高级网络钓鱼Office 365

以下高级网络钓鱼阈值仅适用于 Defender for Office 365 中的防钓鱼策略。 这些阈值控制将机器学习模型应用到邮件以确定网络钓鱼裁定的敏感度：

- **1 - 标准**：这是默认值。 对邮件采取的操作的严重性取决于邮件是网络钓鱼邮件的可信度 (低、中、高或非常高) 。 例如，可信度非常高的标识为网络钓鱼的邮件应用了最严重的操作，而被标识为低可信度的网络钓鱼邮件应用了不太严重的操作。
- **2 - 积极**：被标识为高可信度网络钓鱼的邮件被视为可信度非常高的邮件。
- **3 - 更积极**：被标识为具有中等或高可信度的网络钓鱼的邮件被视为具有非常高可信度的邮件。
- **4 - 最积极**：被标识为低、中或高可信度网络钓鱼的邮件被视为可信度非常高的邮件。

当你增加此设置时， (标记为错误) 误报的可能性会增加。 有关建议设置的信息，请参阅 Microsoft Defender 中的防钓鱼策略[，Office 365设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。
