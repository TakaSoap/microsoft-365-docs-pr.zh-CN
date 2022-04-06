---
title: Exchange Online Protection (EOP) 概述
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 了解Exchange Online Protection (EOP) 如何在独立和混合环境中帮助保护本地电子邮件组织。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3fb49a24ae378be990efd727450a06889cc50679
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473356"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) 是基于云的筛选服务，可保护组织免受垃圾邮件、恶意软件和其他电子邮件威胁的攻击。 EOP 包含在具有邮箱Microsoft 365组织Exchange Online EOP。

> [!NOTE]
> EOP 本身还可用于保护内部部署邮箱和混合环境，以保护内部部署Exchange邮箱。 有关详细信息，请参阅独立[Exchange Online Protection](/exchange/standalone-eop/standalone-eop)。

有关设置 EOP 安全功能的步骤以及与 Microsoft Defender for Office 365 的新增安全性的比较，请参阅[防止威胁](protect-against-threats.md)。 EOP 功能的建议设置在 [EOP 和 Microsoft Defender](recommended-settings-for-eop-and-office365.md) 的推荐设置中Office 365安全性。

本文的其余部分介绍了 EOP 的工作原理以及 EOP 中提供的功能。

## <a name="how-eop-works"></a>EOP 如何工作

了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="在垃圾邮件或隔离裁定之前，通过连接、反恶意软件、邮件流规则-斜杠-策略筛选和内容筛选从 Internet 或客户反馈传递到 EOP 的电子邮件的图形" lightbox="../../media/tp_emailprocessingineopt3.png":::

1. 传入邮件进入 EOP 时，最初会通过连接筛选，这将检查发件人的信誉。 大多数垃圾邮件此时停止，并遭 EOP 拒绝。 有关详细信息，请参阅[配置连接筛选](configure-the-connection-filter-policy.md)。

2. 然后检查邮件是否有恶意软件。 如果在邮件或附件中发现恶意软件 () 邮件将被传递到隔离区。 默认情况下，只有管理员可以查看恶意软件隔离邮件并与之交互。 但是，管理员可以创建并使用 [隔离策略](quarantine-policies.md) 来指定允许用户对隔离邮件执行哪些操作。 若要详细了解恶意软件保护，请参阅 [EOP 中的反恶意软件保护](anti-malware-protection.md)。

3. 邮件将继续通过策略筛选，其中根据任何邮件流规则（也称为 (创建的邮件流规则) 规则）进行评估。 例如，当邮件从特定发件人到达时，规则可以向经理发送通知。

   在具有 CAL with Services 许可证Exchange Enterprise内部部署组织中，此时也会 (在 EOP 中执行 [DLP) ](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)检查的数据丢失防护。

4. 邮件通过内容筛选 (反垃圾邮件和反欺骗) 其中有害的邮件被标识为垃圾邮件、高可信度垃圾邮件、网络钓鱼、高可信度网络钓鱼或反垃圾邮件策略) 或反网络钓鱼策略) 中的批量 (反垃圾邮件策略或欺骗 (欺骗设置。 您可以根据筛选裁定（隔离、移动到"垃圾邮件"文件夹等 (配置对邮件要执行的操作) 以及用户可以使用隔离策略对隔离邮件执行哪些 [操作](quarantine-policies.md)。 有关详细信息，请参阅在 EOP 中配置反 [垃圾邮件策略](configure-your-spam-filter-policies.md) 和配置 [反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

成功通过所有这些保护层的邮件将传递给收件人。

有关详细信息，请参阅电子邮件 [保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="eop-datacenters"></a>EOP 数据中心

EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。 例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。 每个数据中心中的服务器代表您接受邮件，从而在您的组织和 Internet 之间提供一个分隔层，从而减少服务器的负载。 通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。

EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。 如果您在一个区域进行设置，则所有邮件都将使用该区域的邮件路由进行处理。

### <a name="eop-features"></a>EOP 功能

本节简要概述了 EOP 中提供的主要功能。

有关所有 EOP 订阅计划的要求、重要限制以及功能可用性的信息，请参阅 Exchange Online Protection [服务说明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

**注意**：

- EOP 使用多个 URL 阻止列表，帮助检测邮件中的已知恶意链接。
- EOP 使用已知的大量域列表来发送垃圾邮件。
- EOP 使用多个反恶意软件引擎有助于时刻自动保护我们的客户。
- EOP 检查邮件正文中的活动有效负载以及所有邮件附件中是否有恶意软件。
- 有关保护策略的建议值，请参阅 [EOP 和 Microsoft Defender](recommended-settings-for-eop-and-office365.md) 的推荐设置Office 365安全性。
- 有关配置保护策略的快速说明，请参阅 [防止威胁](protect-against-threats.md)。

|功能|Comments|
|---|---|
|**Protection**||
|反恶意软件|[EOP 中的反恶意软件保护](anti-malware-protection.md) <p> [反恶意软件保护常见问题](anti-malware-protection-faq-eop.yml) <p> [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)|
|入站反垃圾邮件|[EOP 中的反垃圾邮件保护](anti-spam-protection.md) <p> [反垃圾邮件保护常见问题](anti-spam-protection-faq.yml) <p> [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
|出站反垃圾邮件|[EOP 中的出站垃圾邮件保护](outbound-spam-controls.md) <p> [在 EOP 中配置出站垃圾邮件筛选](configure-the-outbound-spam-policy.md) <p> [控制邮件中的自动外部电子邮件Microsoft 365](external-email-forwarding.md)|
|连接筛选|[配置连接筛选](configure-the-connection-filter-policy.md)|
|防网络钓鱼|[Microsoft 365](set-up-anti-phishing-policies.md) <p> [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)|
|防欺骗保护|[EOP 中的欺骗智能见解](learn-about-spoof-intelligence.md) <p> [管理租户允许/阻止列表](tenant-allow-block-list.md)|
|零时差自动清除 (恶意软件) 垃圾邮件和网络钓鱼邮件的 ZAP 策略|[ZAP in Exchange Online](zero-hour-auto-purge.md)|
|预设安全策略|[在 EOP 和 Microsoft Defender for Office 365 中预设安全策略](preset-security-policies.md) <p> [EOP 和 Microsoft Defender for Office 365 中的保护策略的配置分析器](configuration-analyzer-for-security-policies.md)|
|租户允许/阻止列表|[管理租户允许/阻止列表](tenant-allow-block-list.md)|
|阻止邮件发件人列表|[在 EOP 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)|
|允许邮件发件人列表|[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)|
|Directory Based Edge Blocking (DBEB)|[使用基于目录的边缘阻止以拒绝发送邮件给无效收件人](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|
|**隔离和提交**||
|管理员提交|[使用管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft](admin-submission.md)|
|自定义邮箱 (提交) |[用户提交策略](user-submission.md)|
|隔离 - 管理员|[在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md) <p> [隔离邮件常见问题解答](quarantine-faq.yml) <p> [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md) <p> [Microsoft 365 中的反垃圾邮件标题](anti-spam-message-headers.md) <p> 可以使用 邮件头分析器 （位于 ）分析隔离 [邮件的邮件头](https://mha.azurewebsites.net/)。|
|隔离 - 最终用户|[在 EOP 中以用户身份查找和释放已隔离邮件](find-and-release-quarantined-messages-as-a-user.md) <p> [使用隔离通知释放并报告隔离邮件](use-spam-notifications-to-release-and-report-quarantined-messages.md) <p> [隔离策略](quarantine-policies.md)|
|**邮件流**||
|邮件流规则|[Exchange Online 中的邮件流规则（传输规则）](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) <p> [Exchange Online 中的邮件流规则条件和例外（谓词）](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions) <p> [Exchange Online 中的邮件流规则操作](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) <p> [在 Exchange Online 中管理邮件流规则](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) <p> [邮件流规则过程Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)|
|接受的域|[在 Exchange Online 中管理接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)|
|连接器|[使用邮箱中的连接器配置Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)|
|增强了连接器的筛选功能|[增强的连接器筛选功能Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)|
|**监视**||
|邮件跟踪|[Message trace](message-trace-scc.md) <p> [邮件管理中心Exchange跟踪](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)|
|电子邮件&协作报告|[查看电子邮件安全报告](view-email-security-reports.md)|
|邮件流报告|[查看邮件流报告](view-mail-flow-reports.md) <p> [邮件管理中心Exchange流报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|邮件流见解|[邮件流见解](mail-flow-insights-v2.md) <p> [管理中心内的邮件Exchange见解](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|审核报告|[管理中心Exchange审核报告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|警报策略|[警报策略](../../compliance/alert-policies.md)|
|**服务级别协议 (SLA) 及支持**||
|垃圾邮件有效性 SLA|\> 99%|
|误报率 SLA|\< 1:250,000|
|病毒检测和阻止 SLA|100% 的已知病毒|
|每月运行时间 SLA|99.999%|
|24 小时全天候电话和网络技术支持|[EOP 的帮助和支持](help-and-support-for-eop.md)。|
|**其他功能**||
|服务器的地理位置冗余全局网络|EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。 有关详细信息，请参阅本文前面 [介绍的 EOP](#eop-datacenters) 数据中心部分。|
|内部部署服务器无法接受邮件时的邮件队列|延期的邮件将在我们的队列中保留一天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 邮件一般每 5 分钟重试发送一次。 有关详细信息，请参阅 [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.yml)。|
|Office 365 邮件加密加载项提供|有关详细信息，请参阅 [Office 365 中的加密](../../compliance/encryption.md)。|
|||
