---
title: 有关安全建议中的Microsoft 365、优先级帐户、Office 365中的优先级帐户、Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
ms.custom: ''
description: 管理员可以了解如何提升安全设置，并使用报告、警报和调查，以在组织中Microsoft 365帐户。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f27e146df680b36c117816f0a07e45e0345c647a
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63675407"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365 中优先帐户安全建议

并非所有用户帐户都有权访问相同的公司信息。 某些帐户有权访问敏感信息，如财务数据、产品开发信息、合作伙伴对关键生成系统的访问权限等。 如果泄露，有权访问高度机密信息的帐户将构成严重的威胁。 我们将这些类型的帐户称为 _优先帐户_。 优先级帐户 (但不限于使用) CEO、COS、CFO、基础结构管理员帐户、生成系统帐户等。

对于攻击者，为普通用户或未知用户转换随机网络的普通网络钓鱼攻击效率很低。 另一方面，_以_ 优先级帐户为目标的网络钓鱼或钓鱼攻击对攻击者来说非常具有攻击性。 因此，优先级帐户需要比普通保护更强大，以帮助防止帐户泄露。

Microsoft 365和 Microsoft Defender for Office 365包含多个关键功能，这些功能可为优先帐户提供额外的安全层。 本文介绍这些功能及其使用方法。

![图标表单中的安全建议摘要。](../../media/security-recommendations-for-priority-users.png)

|任务|所有Office 365 企业版计划|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[提高优先级帐户的登录安全性](#increase-sign-in-security-for-priority-accounts)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[对优先级帐户使用严格预设安全策略](#use-strict-preset-security-policies-for-priority-accounts)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[将用户标记应用于优先级帐户](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[监视警报、报告和检测中的优先级帐户](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[培训用户](#train-users)|![包含。](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

> [!NOTE]
> 有关保护管理员帐户的 _特权 (_，) [本主题。](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="increase-sign-in-security-for-priority-accounts"></a>提高优先级帐户的登录安全性

优先级帐户需要更高的登录安全性。 通过要求使用 MFA 身份验证和禁用 (身份验证) ，可以增强其登录安全性。

有关说明，请参阅步骤 [1。使用 MFA 提高远程工作者的登录安全性](../../solutions/empower-people-to-work-remotely-secure-sign-in.md)。 尽管本文介绍的是远程工作者，但相同的概念也适用于优先用户。

**注意**：我们强烈建议针对所有优先级用户全局禁用旧版身份验证协议，如上一篇文章中所述。 如果您的业务需求阻止您这样做，Exchange Online以下控件来帮助限制旧身份验证协议的范围：

- 您可以使用 [Exchange Online 中的](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)身份验证策略和[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)客户端访问规则来阻止或允许特定用户的基本身份验证和旧版身份验证协议（如 POP3、IMAP4 和经过身份验证的 SMTP）。

- 可以在单个邮箱上禁用 POP3 和 IMAP4 访问。 您可以在组织一级禁用已验证的 SMTP，并启用它，以在仍然需要它的特定邮箱上启用它。 有关说明，请参阅以下文章：
  - [为用户启用或禁用 POP3 或 IMAP4 访问](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [启用或禁用 SMTP AUTH (身份验证的客户端 SMTP) ](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

还值得注意的是，Exchange Online 中正在对 Exchange Web 服务 (EWS) 、Exchange ActiveSync、POP3、IMAP4 和远程 PowerShell 弃用基本身份验证。 有关详细信息，请参阅此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>对优先级帐户使用严格预设安全策略

优先级用户需要针对 EOP Exchange Online Protection (和 Defender for Office 365 中提供的各种) 更严格的操作。

例如，不应将分类为垃圾邮件的邮件发送到"垃圾邮件"文件夹，而是应在这些邮件用于优先级帐户时隔离这些相同的邮件。

可以通过在预设安全策略中使用 Strict 配置文件，对优先级帐户实施此严格方法。

预设安全策略是一个方便且集中的位置，用于将我们建议的严格策略设置应用于 EOP 和 Defender for Office 365。 有关详细信息，请参阅 [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md)。

有关严格策略设置与默认策略设置和标准策略设置之间如何不同的详细信息，请参阅 [EOP 和 Microsoft Defender](recommended-settings-for-eop-and-office365.md) 的推荐设置Office 365安全性。

## <a name="apply-user-tags-to-priority-accounts"></a>将用户标记应用于优先级帐户

作为 Microsoft 365 E5 或加载项订阅) 的一部分，Microsoft Defender for Office 365 计划 2 (中的用户标记是一种在报告和事件调查中快速标识和分类特定用户或用户组的方法。

**优先级帐户** 是一种内置用户标记 (称为系统标记) ，可用于标识涉及优先帐户的事件和警报。 有关优先级帐户 **详细信息，** 请参阅管理和 [监视优先级帐户](../../admin/setup/priority-accounts.md)。

还可以创建自定义标记以进一步标识和分类优先级帐户。 有关详细信息，请参阅用户 [标记](user-tags.md)。 可以在与自定义 **用户 (** 相同的界面) 系统标记中的优先级帐户。

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>监视警报、报告和检测中的优先级帐户

保护并标记优先用户后，可以使用 EOP 和 Defender for Office 365 中的可用报告、警报和调查来快速识别涉及优先帐户的事件或检测。 下表介绍了支持用户标记的功能。

|功能|说明|
|---|---|
|警报|受影响用户的用户标记在门户的警报页面上可见并Microsoft 365 Defender筛选器。 有关详细信息，请参阅 [查看警报](../../compliance/alert-policies.md#viewing-alerts)。|
|资源管理器 <p> 实时检测|在 **资源管理器** (Defender for Office 365 计划 2) 或实时 **检测 (Defender** for Office 365 计划 1) 中，用户标记在"电子邮件"网格视图和"电子邮件详细信息"飞出控件中可见。 用户标记也可作为可筛选属性使用。 有关详细信息，请参阅资源管理器  [中的标记](threat-explorer.md#tags-in-threat-explorer)。|
|市场活动视图|用户标记是 Microsoft Defender for Office 365 计划 2 中的多个可筛选属性之一。 有关详细信息，请参阅 Campaign [Views](campaigns.md)。|
|威胁防护状态报告|在威胁防护状态报告中的几乎所有视图和详细信息表中，你可以按优先级帐户 **筛选结果**。 有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。|
|优先级帐户的电子邮件问题报告|EAC **Exchange** 管理中心中的"优先级帐户的电子邮件 (报告) 有关优先级帐户的未送达和延迟 **邮件的信息**。 有关详细信息，请参阅电子邮件 [优先帐户问题报告](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。|

## <a name="train-users"></a>培训用户

使用优先帐户培训用户可帮助节省这些用户和安全运营团队的时间和沮丧。 不为人知的用户不太可能打开可疑电子邮件中的附件或单击链接，并且他们更有可能避免可疑网站。

美国国家/ [地区学校网络安全](https://www.belfercenter.org/CyberPlaybook) 宣传活动手册为在组织内部建立强大的安全意识文化提供了出色的指导，包括培训用户识别网络钓鱼攻击。

Microsoft 365提供了以下资源来帮助通知组织的用户：

|概念|资源|说明|
|---|---|---|
|Microsoft 365|[可自定义的学习路径](/office365/customlearning/)|这些资源可帮助您将针对组织用户的培训整合在一起。|
|Microsoft 365 安全中心|[Learning模块：使用内置智能安全保护组织，Microsoft 365](/learn/modules/security-with-microsoft-365)|本模块使您能够描述Microsoft 365功能如何协同工作，并阐明这些安全功能的好处。|
|多重身份验证|[两步验证：什么是附加验证页面？](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|本文帮助最终用户了解什么是多重身份验证以及为什么在组织中使用的多重身份验证。|
|攻击模拟培训|[开始使用攻击模拟培训](attack-simulation-training-get-started.md)|Microsoft Defender for Office 365 计划 2 中的攻击模拟培训允许管理员配置、启动和跟踪针对特定用户组的模拟网络钓鱼攻击。|

此外，Microsoft 建议用户执行本文中所述的操作：保护帐户和设备免受黑客和 [恶意软件的攻击](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 这些操作包括：

- 使用强密码
- 保护设备
- 为非托管设备Windows Mac PC (启用安全功能) 

## <a name="see-also"></a>另请参阅

[宣布在 Microsoft Defender 中为用户Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
