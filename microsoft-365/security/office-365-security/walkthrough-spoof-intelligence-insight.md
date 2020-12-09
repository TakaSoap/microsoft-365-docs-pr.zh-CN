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
description: 管理员可以了解欺骗性智能洞察力的工作原理。 他们可以快速确定哪些发件人将电子邮件直接发送到其组织，而不是将电子邮件身份验证检查 (SPF、DKIM 或 DMARC) 的域。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602091"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>演练-Microsoft Defender for Office 365 中的欺骗智能洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Defender for Office 365 的 Microsoft 365 组织中，您可以使用欺骗智能洞察力快速确定哪些外部发件人可以合法地向您发送未经身份验证的电子邮件 (来自不通过 SPF、DKIM 或 DMARC 检查的域的邮件) 。

通过允许已知外部发件人从已知位置发送欺骗邮件，可以减少误报 (被标记为坏) 的良好电子邮件。 通过监视允许的欺骗性发件人，您可以提供额外的安全层来防止不安全的邮件到达您的组织中。

有关报告和见解的详细信息，请参阅 [Security & 合规性中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)。

本演练是安全 & 合规中心的几个演练之一。 若要导航报告和见解，请参阅 [相关主题](#related-topics) 部分中的演练。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **安全仪表板** 页面，请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

  您可以从安全 & 合规中心的多个仪表板中查看欺骗性智能洞察力。 无论您正在查看哪个仪表板，真知灼见都会提供相同的详细信息，并允许您快速执行相同的任务。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - **组织管理**
  - **安全管理员**
  - **安全读者**
  - **全局读者**

  **注意**：将用户添加到 microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心中的必需权限 _以及_ Microsoft 365 中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。

- 在 Microsoft Defender for Office 365 中启用和禁用欺骗智能在反网络钓鱼策略中。 默认情况下启用欺骗智能。 有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

- 若要使用欺骗智能来监视和管理向您发送未经身份验证的邮件的发件人，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全 & 合规中心中打开欺骗性智能洞察力

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **仪表板"。**

2. 在 " **见解** " 行中，查找以下项目之一：

   - **可能在过去七天内的欺骗域**：此洞察力表明启用了欺骗智能， (默认情况下启用了该功能) 。
   - **启用欺骗保护**：此洞察力表明已禁用欺骗性智能，单击真知灼见使你能够启用欺骗智能。

3. 仪表板上的洞察力显示如下所示的信息：

   ![欺骗性智能洞察力的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   此洞察力有两种模式：

   - **真知灼见模式**：如果启用欺骗智能，则真知灼见将显示在过去七天内受到欺骗智能功能影响的邮件数。
   - **如果模式** 为：如果禁用欺骗情报，则真知灼见将显示在过去七天中，我们的欺骗智能功能 *可能会* 影响多少封邮件。

   无论哪种方式，真知灼见中显示的欺骗性域都分为两类： **可疑域** 和 **非可疑域**。

   - **可疑域** 包括：

     - 高可信度欺骗：基于域的历史发送模式和信誉得分，我们非常确信域是哄骗的，并且来自这些域的邮件更有可能是恶意的。

     - 中等可信度欺骗：根据历史发送模式和域的信誉得分，我们确保了域是欺骗的，并且从这些域发送的邮件是合法的。 在此类别中，误报的可能性更大，而不是高度信心欺骗。

   **非可疑域**：域未通过显式电子邮件身份验证检查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。 但是，域通过隐式电子邮件身份验证检查 ([复合身份验证](email-validation-and-authentication.md#composite-authentication)) 。 因此，不会对邮件执行任何反欺骗操作。

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>查看有关欺骗性智能洞察力的可疑域的详细信息

1. 在 "哄骗智能洞察力" 中，单击 " **可疑域** " 或 " **非可疑域** " 以转到 " **哄骗智能洞察力** " 页面。 " **哄骗智能洞察力** " 页面包含以下信息：

   - **欺骗域**：在电子邮件客户端的 " **发件人** " 框中显示的欺骗用户的域。 此地址也称为 `5322.From` 地址。
   - **基础结构**：也称为 " _发送" 基础结构_。 在反向 DNS 查找中找到的域 (PTR 记录服务器的 IP 地址的 PTR 记录) 。 如果源 IP 地址没有 PTR 记录，则发送的基础结构被标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。
   - **邮件计数**：在最近7天内包含指定的欺骗性域的组织发送到组织的邮件数。
   - **上次查看** 时间：从包含欺骗域的发送基础结构收到邮件的最后日期。
   - **哄骗类型**：此值是 **外部** 的。
   - 是否 **允许欺骗？**：您在此处看到的值是：
     - **是**：允许欺骗用户的域和发送基础结构组合的邮件不会被视为欺骗电子邮件。
     - **否**：来自欺骗用户的域和发送基础结构的组合的邮件被标记为欺骗。 该操作由默认的反网络钓鱼策略或自定义反网络钓鱼策略控制 (默认值为 " **将邮件移动到垃圾邮件" 文件夹**) 。

     有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

2. 选择列表中的某一项，以查看浮出控件中的域/发送基础结构对的详细信息。 这些信息包括：
   - 为什么我们会发现这一点。
   - 您需要执行的操作。
   - 域摘要。
   - WhoIs 有关发件人的数据。
   - 从同一个发件人在你的租户中看到的类似消息。

   在这里，您还可以选择在 " **允许欺骗** 发件人允许" 列表中添加或删除域/发送基础结构对。 只需设置相应的开关即可。

   ![欺骗智能洞察力详细信息窗格中的域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>将域添加到允许的欺骗列表中

通过哄骗智能洞察力将域添加到允许的欺骗列表中，仅允许将欺骗性域 *和* 发送基础结构结合在一起。 它不允许来自任何来源的来自欺骗域的电子邮件，也不允许来自任何域的发送基础结构的电子邮件。

例如，您允许以下域成为允许欺骗的列表：

- **域**： gmail.com
- **基础结构**： tms.mx.com

仅允许来自该域/发送基础结构对的电子邮件进行欺骗。 不允许其他试图欺骗 gmail.com 的发件人。 来自 tms.mx.com 的其他域中的邮件由欺骗情报检查。

## <a name="related-topics"></a>相关主题

[Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)
