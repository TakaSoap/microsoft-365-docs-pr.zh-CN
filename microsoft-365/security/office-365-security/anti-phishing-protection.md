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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护 (Office 365 ATP) 中的反钓鱼保护功能。
ms.openlocfilehash: 9297b241122a3aa316da1594c6b30111bfead308
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411772"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 中的反网络钓鱼保护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*网络钓鱼* 是一种电子邮件攻击，试图窃取来自合法或受信任发件人的邮件中的敏感信息。 存在特定类别的网络钓鱼。 例如：

- **Spear 仿冒** 使用专门为目标收件人量身定制的自定义自定义内容 (通常是攻击者) 的收件人的侦测之后。

- **Whaling** 在组织内的主管或其他高价值目标中定向，以实现最大效果。

- **业务电子邮件危害 (BEC) ** 使用伪造的受信任发件人 (财务总监、客户、受信任的合作伙伴等。向欺骗收件人批准付款、转移资金或暴露客户数据 ) 。

- 加密您的数据和要求付款以对其进行解密的**勒索软件**几乎总是会开始在网络钓鱼邮件中。 反网络钓鱼防护无法帮助您解密加密文件，但可以帮助检测与勒索软件活动相关联的初始网络钓鱼邮件。 有关从勒索软件攻击中恢复的详细信息，请参阅 [Microsoft 365 中的从勒索软件攻击恢复](recover-from-ransomware.md)。

随着攻击的复杂程度的增加，训练有素的用户更难识别复杂的网络钓鱼邮件。 幸运的是，Exchange Online Protection (EOP) 以及 Office 365 高级威胁防护 (Office 365 ATP) 中的其他功能。

## <a name="anti-phishing-protection-in-eop"></a>EOP 中的反网络钓鱼保护

EOP (即，没有 ATP 的 Microsoft 365 组织) 包含的功能可以帮助您的组织防御网络钓鱼威胁：

- **欺骗智能**：审查来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。 有关详细信息，请参阅 [在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

- **EOP 中的反网络钓鱼策略**：启用或禁用欺骗智能，在 Outlook 中打开或关闭未经身份验证的发件人标识，以及指定阻止的欺骗性发件人的操作 (移至垃圾邮件文件夹或隔离) 。 有关详细信息，请参阅 [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

- **隐式电子邮件身份验证**： EOP 增强了入站电子邮件的标准电子邮件身份验证检查 ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)) 与发件人信誉、发件人历史记录、收件人历史记录、行为分析以及其他可帮助您识别伪造发件人的高级技术 有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP 中的其他反网络钓鱼保护

Office 365 ATP 包含更高级和更高级的反网络钓鱼功能：

- **ATP 反网络钓鱼策略**：创建新的自定义策略、配置反模拟设置 (保护用户和域的模拟) 、邮箱智能设置和可调整的高级网络钓鱼阈值。 有关详细信息，请参阅 [在 Microsoft 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。 有关反网络钓鱼策略和 ATP 反网络钓鱼策略之间的差异的详细信息，请参阅 [Microsoft 365 中的反网络钓鱼策略](set-up-anti-phishing-policies.md)。

- "**活动" 视图**：机器学习和其他试探法可识别和分析针对整个服务和组织的协调的网络钓鱼攻击所涉及的邮件。 有关详细信息，请参阅 [Office 365 ATP 中的市场活动视图](campaigns.md)。

- **攻击模拟器**：管理员可以创建假冒的网络钓鱼邮件，并将其作为教育工具发送给内部用户。 有关详细信息，请参阅 [Office 365 ATP 中的攻击模拟器](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>其他反网络钓鱼资源

- 对于最终用户： [保护自己免受网络仿冒骗术和其他形式的在线欺诈](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。

- [Microsoft 365 如何验证发件人地址以防止仿冒](how-office-365-validates-the-from-address.md)。
