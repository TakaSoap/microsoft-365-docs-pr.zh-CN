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
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理员可以了解 EOP 和 Office 365 ATP 部署) 功能 (Exchange Online Protection 中的防钓 (鱼保护功能) 。
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827441"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365 中的防钓鱼保护

*网络钓鱼是* 一种电子邮件攻击，它尝试从合法的发件人或受信任的发件人访问邮件中的敏感信息。 存在特定类别的网络钓鱼。 例如：

- **鱼站点钓鱼使用** 非常侧重和定制的专门为目标收件人定制的自定义内容 (通常在攻击者负责帮助者在对收件人) 。

- **为什么面向** 组织内的主管人员或其他高值目标，以实现最大影响。

- **商务电子邮件泄 (BEC) 使用 ** 外部受信任的发件人 (财务主管、客户、) 受信任合作伙伴等，以尝试批准批准的付款、转接商支付或泄露客户数据。

- **加密数据和要求** 付款来解密数据的勒索软件几乎总是从网络钓鱼邮件中开始。 反网络钓鱼防护不能帮助解密加密文件，但它可以帮助检测与勒索软件活动相关联的初始网络钓鱼邮件。 有关从勒索软件攻击中恢复的详细信息，请参阅 [Microsoft 365](recover-from-ransomware.md)中的勒索软件攻击恢复。

随着攻击的复杂性不断增长，训练用户就很难识别复杂的钓鱼邮件。 遗弃使用 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护默认 Office 365 ATP (邮箱中的) 功能) 帮助。

## <a name="anti-phishing-protection-in-eop"></a>EOP 中的防钓鱼保护

EOP (，也就是说，没有 ATP 的 Microsoft 365 组织) 包含可帮助保护组织防钓鱼威胁的功能：

- **欺骗智能**：审查来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。 有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

- **EOP 中的防钓鱼策略：** 打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，并指定被阻止的欺骗 (移到垃圾邮件文件夹或隔离) 的操作。 有关详细信息，请参阅 EOP [中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)。

- **隐式电子邮件身份验证**：EOP 通过发件人信誉、发件人历史记录、收件人历史记录、行为分析和其他高级技术增强了对入站电子邮件 ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [、DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)) 的标准电子邮件身份验证检查，以帮助识别预测发件人。 有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP 中的其他防钓鱼保护

Office 365 ATP 包含其他更多高级的防钓鱼功能：

- **ATP 防钓鱼策略**：创建新的自定义策略，配置反模拟设置 (保护用户和域不进行模拟) 、邮箱智能设置和可调整的高级网络钓鱼阈值。 有关详细信息，请参阅在 [Microsoft 365 中配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。 有关反网络钓鱼策略和 ATP 防钓鱼策略之间差异的详细信息，请参阅 [Microsoft 365 中的反网络钓鱼策略](set-up-anti-phishing-policies.md)。

- **Campaign Views：** 机器学习和其他启发式方法用于标识并分析与整个服务和组织相比的协调网络钓鱼攻击涉及的消息。 有关详细信息，请参阅[Office 365 ATP 中的 Campaign Views。](campaigns.md)

- **攻击模拟器：管理员可以创建**虚假的网络钓鱼邮件，并将这些消息作为教育工具发送给内部用户。 有关详细信息，请参阅 [Office 365 ATP 中的攻击模拟器](attack-simulator.md)。

## <a name="other-anti-phishing-resources"></a>其他防钓鱼资源

- 对于最终用户：请保护自己，[防止网络钓鱼方案和其他形式的在线草。](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Microsoft 365 如何通过验证发件人地址来防止钓鱼](how-office-365-validates-the-from-address.md)。
