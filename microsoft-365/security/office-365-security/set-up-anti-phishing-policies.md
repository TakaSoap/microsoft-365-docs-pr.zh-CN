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
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护的 Office 365 ATP 策略 (网络钓鱼) 。
ms.openlocfilehash: f671588ff4232c6ca1c1342475f48802bf1a0076
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825097"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 中的反网络钓鱼策略

用于配置反网络钓鱼保护设置的策略在具有 Exchange Online 邮箱的 Microsoft 365 组织中可用，具有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织，以及 Office 365 高级威胁防护 (Office 365 ATP) 组织。

ATP 防钓鱼策略仅适用于已安装 Office 365 ATP 的组织。 例如：

- Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等
- [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP 作为加载项](https://products.office.com/exchange/advance-threat-protection)

所有其他组织都有防钓鱼策略。

下表介绍了防钓鱼策略与 ATP 防钓鱼策略之间的高级别差异：

****

|功能|防钓鱼策略|ATP 防钓鱼策略|
|---|:---:|:---:|
|自动创建的默认策略|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|创建自定义策略|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|策略设置<sup>\*</sup>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|模拟设置||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|欺骗设置|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|高级网络钓鱼阈值||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> 在默认策略中，策略名称和说明是只读的 (说明为空) ，并且不能指定谁应用到策略 (则默认策略应用于所有收件人) 。

若要配置防钓鱼策略，请参阅下列文章：

- [在 EOP 中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)

- [在 Microsoft 365 中配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)

本文的其余部分介绍了反网络钓鱼策略和 ATP 防钓鱼策略中可用的设置。

## <a name="policy-settings"></a>策略设置

防钓鱼策略和 ATP 防钓鱼策略中提供以下策略设置：

- **名称**：您不能重命名默认的反网络钓鱼策略，但可以命名和重命名您创建的自定义策略。

- **描述** 您无法向默认的反网络钓鱼策略添加描述，但可以添加和更改您创建的自定义策略的说明。

- **应用于**：标识将要应用反网络钓鱼策略的内部收件人。 在自定义策略中需要使用此值，并且在默认策略中不可用， (默认策略应用于所有) 。

  只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

  - **收件人是**：组织中一个或多个邮箱、邮件用户或邮件联系人。
  - **收件人为以下组的成员**：您所在组织的一个或多个组。
  - **收件人域是**：Microsoft 365 中配置的一个或多个接受的域。

  - **除外**：该规则的例外情况。 设置和行为与条件完全一样：

    - **收件人为**
    - **收件人为以下组的成员**
    - **收件人域为**

## <a name="spoof-settings"></a>欺骗设置

欺骗是电子邮件中的发件人地址 (电子邮件客户端地址与电子邮件源的域不匹配) 的发件人地址。 有关欺骗的详细信息，请参阅 Microsoft [365 中的防欺骗保护](anti-spoofing-protection.md)。

防钓鱼策略和 ATP 防钓鱼策略中提供以下欺骗性设置：

- **防欺骗保护**：启用或禁用反欺骗保护。 建议将其保持启用状态。 使用欺 **骗智能策略来** 允许或阻止特定欺骗性的内部和外部发件人。 有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

  > [!NOTE]
  > 在 EOP 的默认反网络钓鱼策略、默认 ATP 防钓鱼策略和你创建的自定义反网络钓鱼策略或 ATP 防钓鱼策略中，默认情况下会启用欺骗设置。 <br/><br/> 如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;改为启用连接器的增强筛选功能。 有关说明，请参阅["增强的 Exchange Online 中的连接器筛选"。](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

  对于来自受阻止的欺骗性发件人的邮件，你还可以指定要对邮件执行的操作：

  - **将邮件移动到垃圾邮件文件夹**：这是默认值。 邮件递送到邮箱，并移动到"垃圾邮件"文件夹。 如果对邮箱邮箱启用了默认的垃圾邮件规则，则邮件) 移动到"垃圾邮件" (。 有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

  - **隔离邮件：将**邮件发送到隔离，而不是目标收件人。 有关隔离的信息，请参阅以下文章：

    - [在 Microsoft 365 隔离](quarantine-email-messages.md)
    - [在 Microsoft 365 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Microsoft 365 中以用户身份查找和释放已隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

- **Unauthenticated Sender：** 请参阅下一节中的说明。

### <a name="unauthenticated-sender"></a>未经身份验证的发件人

未经身份验证的发件人标识是防钓鱼策略和 ATP 反网络钓鱼策略中提供的欺骗设置的一部分，如上一节所述。 [Spoof settings](#spoof-settings)

" **未经身份验证的** 发件人"设置启用或禁用 Outlook 中未经识别的发件人标识。 具体来说：

- 如果邮件未通过 SPF ) 或 DKIM 检查并且邮件未通过 DMARC**and**或复合身份验证，则将一个问号 (？"复选框中的标识添加到发件人[的照片](email-validation-and-authentication.md#composite-authentication)中。

- 如果 <u>"发件人</u> (chris@contoso.com"中的域不同 (电子邮件客户端) 中显示的邮件发件人不同于 DKIM 签名或 **MAIL FROM** 地址中的域，通过 michelle@fabrikam.com) 添加的邮件发件人。 有关这些地址的详细信息，请参阅 [电子邮件标准的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

为防止将这些标识符添加到来自特定发件人的邮件，您可以选择以下选项：

- 允许发件人在欺骗智能策略中进行欺骗。 有关说明，请参阅在 [Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

- [为发件人域](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 配置电子邮件身份验证。
  
  - 对于发件人照片中的问号，SPF 或 DKIM 最重要。
  - 对于通过标记，确认 DKIM 签名中的域或者 **MAIL FROM** 地址与 (匹配，或者是发件人地址中该域) 子域的子域。

有关详细信息，请参阅 ["在 Outlook 和 Web 上的 Outlook Outlook.com中识别可疑邮件](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>ATP 防钓鱼策略中的独占设置

本部分介绍仅在 ATP 防钓鱼策略中可用的策略设置。

> [!NOTE]
> 默认情况下，ATP 独占设置未配置或打开，即使在默认策略中也是个设置。 要利用这些功能，需要在默认 ATP 防钓鱼策略中启用和配置这些功能，或创建和配置自定义 ATP 防钓鱼策略。

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 防钓鱼策略中的模拟设置

模拟是邮件中的发件人或发件人电子邮件域与实际发件人或域的相似位置：

- 例如，将域记录contoso.com源ćóntoso.com。
- 有关对用户进行设置的michelle@contoso.com示例michele@contoso.com。

仿模拟域可能被视为合法的 (注册域、配置的电子邮件身份验证记录 ) 等，但其目的是拒绝收件人。

以下模拟设置仅在 ATP 防钓鱼策略中提供：

- **保护的用户**：防止模拟指定的内部或外部用户。 例如，主管人员 (外的) 板 (板) 。 最多可以添加 60 个内部和外部地址。 此受保护的用户列表与该策略应用于设置中的收件人 **列表** 不同。

  例如，在应用于名为"管理人员"的 (felipea@contoso.com) 的策略中，将 Felipe Apodaca 指定为受保护用户。 将按策略输入为模拟的用户配置的操作，将对向执行人员组成员 (发送 Felipe Apodaca 的入站邮件执行) 。

- **要保护**的域：阻止模拟指定域。 例如，您拥有的域 ([接受的域，) ](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 或特定 (您拥有或合作伙伴域) 。 此受保护域列表不同于该策略应用于设置中的 **域** 列表。

  例如，您可tailspintoys.com为策略中应用于名为 Executives 的成员的受保护域。 向管理人员组成员发送 tailspintoys.com的入站邮件将由策略类型 (为模拟域管理员配置的操作对) 。

- **受保护的用户或域的操作**：选择要对包含在策略中的受保护用户和受保护的域进行模拟尝试的入站邮件时执行的操作。 您可以指定其他操作以模拟受保护的用户和模拟受保护的域：

  - **不应用任何操作**

  - **重定向至其他电子邮件地址**：将邮件发送给指定收件人，而不是目标收件人。

  - **"将邮件移动到垃圾邮件**文件夹：邮件递送到邮箱"并移动到"垃圾邮件"文件夹。 如果对邮箱邮箱启用了默认的垃圾邮件规则，则邮件) 移动到"垃圾邮件" (。 有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

    - **隔离邮件：将**邮件发送到隔离，而不是目标收件人。 有关隔离的信息，请参阅以下文章：

    - [在 Microsoft 365 隔离](quarantine-email-messages.md)
    - [在 Microsoft 365 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)
    - [在 Microsoft 365 中以用户身份查找和释放已隔离邮件](find-and-release-quarantined-messages-as-a-user.md)

  - **传递邮件并向密件抄送行添加其他地址：** 将邮件传递给目标收件人并以静默方式将邮件传递给指定的收件人。

  - **在邮件传递前将其删除：** 自动删除整个邮件，包括所有附件。

- **安全提示：** 启用或禁用以下会显示将会检查失败的消息的模拟安全提示：

  - **模拟用户："** 发件人"地址包含受保护用户。
  - **模拟域："** 发件人"地址包含受保护域。
  - **不常见的**字符："发件人"地址包含异常字符集 (例如，数字符号和文本，或者是受保护的发件人或域中大写和小写字母) 的混合。

- **邮箱智能**：根据用户的经常 (联系人，启用或禁用项目智能 (AI) ，该服务将决定用户电子邮件模式。 此设置可帮助 AI 区分合法电子邮件和欺骗性电子邮件和这些联系人。 邮箱智能仅适用于 Exchange Online 邮箱。

- **基于邮箱智能的模拟保护**：基于每个用户的个人发件人地图，启用或禁用增强的模拟结果。 通过此智能，Microsoft 365 可以自定义用户模拟检测，并更好地处理误报。 检测到用户模拟时，你可以定义要对邮件执行的特定操作：

  - **不应用任何操作**
  - **将邮件重定向到其他电子邮件地址**
  - **将邮件移动到垃圾邮件文件夹**
  - **隔离邮件**
  - **传递邮件并向"送达"行添加其他地址**
  - **在邮件传递前将其删除**

- **受信任的发件人和域**：模拟保护设置的例外。 来自指定发件人和发件人域的邮件永远不会被按策略分类为基于模拟的攻击。 换句话说，对受保护的发件人、受保护的域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。 这些列表的最大限制是大约 1000 个条目。

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>ATP 防钓鱼策略中的高级网络钓鱼阈值

以下高级网络钓鱼阈值仅在 ATP 防钓鱼策略中提供，用于控制将机器学习模型应用于消息以确定网络钓鱼是否断开的敏感性：

- **1 - Standard：** 此值为默认值。 对邮件执行的操作的严重性取决于邮件是网络钓鱼邮件、中、高 (高或非常高可信度) 。 例如，对于优先级高的网络钓鱼邮件，系统将应用严重操作，而标识为网络钓鱼邮件的重度较低，但可信度较低。

- **2 - 高可行：** 被识别为高可信度的网络钓鱼的邮件被视为是以非常高可信度进行标识的。

- **3 - 更高效：** 识别为具有中等或高可信度的网络钓鱼的邮件被视为是以高可信度确定的。

- **4 - 最高级别：** 标识为低、中或高可信度的网络钓鱼的邮件被视为具有高可信度的网络钓鱼。

误报可能做 (标记为不好的消息) 增加此设置后不良消息。 有关推荐设置的信息，请参阅 [Office ATP 防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。
