---
title: 防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的防钓鱼保护功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055784"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 中的防钓鱼保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*网络钓鱼* 是一种电子邮件攻击，它尝试窃取看似来自合法或受信任的发件人的邮件中的敏感信息。 存在网络钓鱼的特定类别。 例如：

- **Spear 网络钓鱼** 使用专门针对目标收件人定制的集中的自定义内容 (通常是在攻击者对收件人重新联机之后) 。

- **一个** 面向主管人员或组织内部的其他高价值目标，以最大化效果。

- **商业电子邮件泄露 (BEC)** 使用伪造的受信任发件人 (财务官、客户、受信任合作伙伴等 ) 来欺骗收件人批准付款、转移资金或泄露客户数据。

- **加密你的** 数据并要求付款以解密数据的勒索软件几乎总是从网络钓鱼邮件中开始。 防钓鱼保护无法帮助您解密加密文件，但它可以帮助检测与勒索软件活动关联的初始网络钓鱼邮件。 有关从勒索软件攻击中恢复的信息，请参阅 [在 Microsoft 365](recover-from-ransomware.md)中从勒索软件攻击中恢复。

随着攻击复杂性的不断增加，经过培训的用户甚至很难识别复杂的网络钓鱼邮件。 幸运的是，Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中的其他功能可以提供帮助。

## <a name="anti-phishing-protection-in-eop"></a>EOP 中的防钓鱼保护

EOP (，即没有 Microsoft Defender for Office 365 的 Microsoft 365) 包含可帮助保护组织免受网络钓鱼威胁的功能：

- **欺骗智能**：审查来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。 有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

- **EOP** 中的反网络钓鱼策略：打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，并指定针对被阻止的欺骗 (移动到垃圾邮件文件夹或隔离) 的操作。 有关详细信息，请参阅在 [EOP 中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)。

- 隐式 **电子邮件** 身份验证：EOP 通过发件人信誉、发件人历史记录、收件人历史记录、行为分析和其他高级技术增强入站电子邮件 ([SPF、DKIM](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和 [DMARC](use-dmarc-to-validate-email.md)) 的标准电子邮件身份验证检查，以帮助识别伪造的发件人。 [](use-dkim-to-validate-outbound-email.md) 有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的其他防钓鱼保护

Microsoft Defender for Office 365 包含更多更高级的防钓鱼功能：

- **Microsoft Defender for Office 365** 中的反网络钓鱼策略：创建新的自定义策略、配置反模拟设置 (保护用户和域免受模拟) 、邮箱智能设置和可调整的高级网络钓鱼阈值的影响。 有关详细信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。 有关 EOP 中的反网络钓鱼策略与 Defender for Office 365 中的反网络钓鱼策略之间的差异详细信息，请参阅 [Microsoft 365](set-up-anti-phishing-policies.md)中的反网络钓鱼策略。

- **市场活动视图**：机器学习和其他启发式技术可标识和分析针对整个服务和组织的协调网络钓鱼攻击所涉及的邮件。 有关详细信息，请参阅 [Microsoft Defender for Office 365 中的市场活动视图](campaigns.md)。

- **攻击模拟器**：管理员可以创建假的网络钓鱼邮件，并将其作为教育工具发送给内部用户。 有关详细信息，请参阅 [Microsoft Defender for Office 365 中的攻击模拟器](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>其他防钓鱼资源

- 对于最终用户： [保护自己免受网络钓鱼计划和其他形式的在线欺诈的攻击](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [Microsoft 365 如何验证"自"地址以防止钓鱼](how-office-365-validates-the-from-address.md)。
