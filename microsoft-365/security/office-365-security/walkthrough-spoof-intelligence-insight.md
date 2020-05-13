---
title: 演练-欺骗性的智能洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理员可以了解欺骗性智能洞察力的工作原理，包括如何快速确定哪些发件人合法地向您发送未经身份验证的电子邮件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a71b885926d742f86a5a0c86443a5f5ba23b8a6
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208460"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>演练-在 Microsoft 365 中 ATP 欺骗智能洞察力

在具有高级威胁防护（ATP）的 Microsoft 365 组织中，您可以使用欺骗智能洞察力快速确定哪些发件人合法地向您发送未经身份验证的电子邮件。 通过允许他们发送欺骗邮件，可以降低任何误报给用户带来的风险。 您还可以使用欺骗智能洞察力来监视和管理允许的域对，以提供额外的安全措施，并防止不安全的邮件到达您的组织中。

如果您不熟悉[安全 & 合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)，它可能会帮助您了解如何轻松地从仪表板导航到真知灼见和推荐的操作。

本演练是安全 & 合规中心的几个演练之一。 若要导航报告和见解，请参阅相关主题部分中的演练。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到**安全仪表板**页面，请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

  您可以从安全 & 合规中心的多个仪表板中查看欺骗性智能洞察力。 无论您正在查看哪个仪表板，真知灼见都会提供相同的详细信息，并允许您快速执行相同的任务。

- 必须先分配有权限，然后才能执行这些过程。 若要使用欺骗性智能洞察力，您必须是 "**组织管理**"、"**安全管理员**" 或 "**安全读者**" 角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

- 在 ATP 反网络钓鱼策略中启用和禁用欺骗智能。 有关详细信息，请参阅[在 Microsoft 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

- 在使用 Exchange Online 邮箱的 Microsoft 365 组织中，在没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）中，可以使用欺骗智能来监视和管理您向其发送未经身份验证的邮件的发件人。 有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全 & 合规中心中打开欺骗性智能洞察力

1. 在安全 & 合规性中心中，转到 "**威胁管理** \> **仪表板"。**

2. 在 "**见解**" 行中，查找以下项目之一：

   - **启用欺骗智能**：该洞察力被命名为**欺骗性域，在过去30天的身份验证失败**。 这是默认选项。

   - **已禁用欺骗情报**：已命名**启用欺骗保护**的洞察力，单击它可启用欺骗智能。

3. 仪表板上的洞察力显示如下所示的信息：

   ![欺骗性智能洞察力的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   此洞察力有两种模式：

   - **真知灼见模式**。 如果你启用了任何欺骗策略，则真知灼见将显示在过去30天内受到欺骗智能功能影响的邮件数。

   - **If 模式**。 如果未启用任何欺骗策略，则真知灼见将显示在过去30天内，我们的欺骗智能功能*会*影响的邮件数。

   无论哪种方式，真知灼见中显示的欺骗性域都分为两类：**可疑域对**和**非可疑域对**。 这些类别进一步细分为三个不同的存储桶供您查看。

   **域对**是 "发件人" 地址和发送基础结构的组合：

   - 发件人地址是在电子邮件客户端中显示的发件人的电子邮件地址。 此地址标识电子邮件的作者。 即，负责撰写邮件的个人或系统的邮箱。 此地址也称为 `5322.From` 地址。

   - 发送方结构或发件人是发送 IP 地址的反向 DNS 查找（PTR 记录）的组织域。 如果发送 IP 地址没有 PTR 记录，则发件人由使用 CIDR 表示法（/24）中的255.255.255.0 子网掩码的发送 IP 进行标识。 例如，如果 IP 地址为192.168.100.100，则发件人的完整 IP 地址为 192.168.100.100/24。

   **可疑域对**包括：

   - **高可信度欺骗**： Microsoft 365 收到了基于历史发送模式和域信誉分数的强信号，这些域是可疑的。 Microsoft 365 非常确信域是哄骗的，并且从这些域发送的邮件不太可能是合法的。

   - **中等可信度欺骗**： Microsoft 365 收到了中等信号，这些域根据历史发送模式和域的信誉得分而受到怀疑。 Office 365 适度确信域是欺骗的，并且从这些域发送的邮件是合法的。 此存储桶具有包含误报（FPs）的更多可能性，而不是高可信度欺骗存储桶。

   - **非可疑域对**（包括**rescued 欺骗**）： rescued 欺骗是未通过显式身份验证检查[SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)）的域，但通过了隐式电子邮件身份验证检查（[复合身份验证](email-validation-and-authentication.md#composite-authentication)）。 因此，Microsoft 365 会代表您 rescued 邮件，并且不会对邮件执行任何反欺骗操作。

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>查看有关欺骗性智能洞察力的可疑域对的详细信息

1. 在 "哄骗智能洞察力" 中，单击任一域对（high、适中或 rescued）。

   此时将显示 "**哄骗智能真知灼见**" 页面，其中显示了向您的组织发送未经身份验证的邮件的发件人列表。 此页上的信息可帮助您确定是否授权欺骗邮件，或者是否需要执行进一步的操作。 您可以按邮件数、欺骗的上次检测日期等对信息进行排序。 （例如，单击 "**邮件数**" 或 "**最后见到**的列标题"。）

2. 在表中选择一个项目以打开详细信息窗格，其中包含有关域对的丰富信息，其中包括我们捕获此内容的原因、您需要执行的操作、域摘要、域摘要、WhoIs 有关发件人的数据以及我们在你的租户中从相同的发件人处看到的类似电子邮件。 在这里，您还可以选择在**AllowedToSpoof**安全发件人列表中添加或删除域对。

   ![欺骗智能洞察力详细信息窗格中的域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>在 AllowedToSpoof 安全发件人列表中添加或删除域

在欺骗性智能洞察力的详细信息窗格中查看域对时，可以在 AllowedToSpoof 安全发件人列表中添加或删除域。 只需设置相应的开关即可。

这将修改欺骗性域和发送基础结构的唯一域对组合，并且不会对整个欺骗域或独立的发送基础结构提供覆盖范围。

例如，如果将以下域对添加到 "AllowedToSpoof" 发件人允许列表：*欺骗域*"gmail.com" 和*发送基础结构*"tm *. mx.com"，* 则仅允许来自该域对的邮件欺骗。 其他试图欺骗 "gmail.com" 的发件人以及 "tms.mx.com" 尝试欺骗的其他域将继续受到欺骗性智能的保护。

## <a name="related-topics"></a>相关主题

[Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)

[演练 - 从仪表板到见解](from-a-dashboard-to-an-insight.md)

[演练 - 从详细报告到见解](from-a-detailed-report-to-an-insight.md)

[演练 - 从见解到详细报告](from-an-insight-to-a-detailed-report.md)