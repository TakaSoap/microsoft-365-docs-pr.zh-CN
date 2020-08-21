---
title: 零时差自动清除 O) AP (
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解零时差差自动清除 (ZAP) 如何通过试图将 Exchange Online 邮箱中的传递邮件移至垃圾邮件文件夹或被动被动发现为垃圾邮件或网络钓鱼的隔离邮箱。
ms.openlocfilehash: 9096486ed98657fede7927089592c92fffdad70e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826693"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>在 Exchange Online 中为 ZAP (零时) 清除

## <a name="basic-features-of-zap"></a>ZAP 的基本功能

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，零时差差自动清除 (ZAP) 是一种电子邮件保护功能，它会被撤销地检测并忽略已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。

ZAP 不适用于保护本地 Exchange (的 EOP) EOP 保护的独立 Exchange Online Protection。

## <a name="how-zap-works"></a>ZAP 的工作原理

每天更新服务中的垃圾邮件和恶意软件签名。 但是，用户仍会因各种原因收到恶意邮件，包括向用户交付之后内容被简化的情况。 ZAP 通过不等监控服务中垃圾邮件和恶意软件签名的更新来解决这一问题。 ZAP 可以查找并删除用户邮箱中已有的邮件。

ZAP 操作对于用户是无缝的;如果检测到并移动了消息，则不会通知这些消息。

[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则通常 (称为传输规则、) 件箱规则或其他筛选器的优先级高于 ZAP。 与邮件流中发生的情况类似，这意味着，即使服务确定已传递的邮件需要 ZAP，由于安全发件人配置如何操作邮件也不会对邮件执行操作。 这是为配置邮件而跳过筛选时要谨慎的另一个原因。

### <a name="malware-zap"></a>恶意软件 ZAP

为了 **查看或未读** 邮件，在传递后发现包含恶意软件的邮件，ZAP 会隔离包含恶意软件附件的邮件。 只有管理员可以从隔离查看和管理恶意软件邮件。

在反恶意软件策略中默认启用恶意软件 ZAP。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>网络钓鱼邮件 ZAP

对于**在传递后识别**为钓鱼的邮件，ZAP 结果取决于针对在适用的反垃圾邮件策略中为钓鱼电子邮件筛选结定而配置的操作。 **Phishing email** 以下列表描述了适用于网络钓鱼的可用筛选谓词操作及其可能的 ZAP 结果：

- **添加 X-Header** **、在主题行（带文本的前挂起**主题行）： ZAP 不对邮件执行任何操作。

- **将邮件移动到垃圾邮件**：ZAP 将邮件移动到垃圾邮件文件夹，只要在邮箱上启用了默认启用 (就会) 。 有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

- **重定向邮件到电子邮件地址****、删除****邮件、隔离邮件**：ZAP 隔离邮件。

默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，"网络钓鱼电子邮件筛选裁 **定** "的默认操作为" **隔离**邮件"，这意味着默认情况下，ZAP 将隔离邮件。

有关配置垃圾邮件筛选分析检查的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="spam-zap"></a>垃圾邮件 ZAP

对于 **在传递后** 被标识为垃圾邮件的未读邮件，ZAP 结果取决于针对适用的反 **垃圾邮件** 策略中为垃圾邮件筛选结点配置的操作。 以下列表介绍了垃圾邮件的可用筛选谓词操作及其可能的 ZAP 结果：

- **添加 X-Header**、 **预挂起带文本的主题行**： ZAP 不对邮件执行任何操作。

- **将邮件移动到垃圾邮件**：ZAP 将邮件移动到垃圾邮件文件夹，只要在邮箱上启用了默认启用 (就会) 。 有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。

- **重定向邮件到电子邮件地址****、删除****邮件、隔离邮件**：ZAP 隔离邮件。 最终用户可以查看和管理自己的垃圾邮件隔离邮件。

默认情况下，在反垃圾邮件策略中启用垃圾邮件 ZAP，垃圾邮件筛选结点的默认操作为**Spam**"将邮件移至**垃圾邮件文件夹"，** 这意味着默认情况下，垃圾邮件 ZAP 会将未读**邮件移动到"** 垃圾邮件"文件夹。

有关配置垃圾邮件筛选分析检查的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Office 365 ATP 中的 Office 365 高级威胁 (的 ZAP 注意事) 

ZAP 不会隔离所有正在 [进行动态](dynamic-delivery-and-previewing.md) 传递扫描的邮件，或恶意软件筛选已将附件替换为 **恶意软件警报扫描文件Text.txt** 附件。 如果收到这些邮件类型的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选裁定被设置为对邮件 (移动至垃圾邮件、重定向、删除、隔离) 执行某些操作 (则 ZAP 将默认执行"移动到垃圾邮件"操作。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否移动了邮件

为确定 ZAP 是否移动了您的邮件，可使用威胁防[护状态](view-email-security-reports.md#threat-protection-status-report)报告或[威胁资源管理器 (以及实时) 。 ](threat-explorer.md) 请注意，作为系统操作，ZAP 不会记录在 Exchange 邮箱审核日志中。

## <a name="zap-faq"></a>ZAP 常见问题解答

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>如果将合法邮件移动到"垃圾邮件"文件夹，会怎什么？

应按照正常报告过程 [实现误报](report-junk-email-messages-to-microsoft.md)。 邮件将移至垃圾邮件文件夹的唯一原因是服务已确定该邮件是垃圾邮件还是恶意邮件。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>如果我使用"隔离"文件夹而不是"垃圾邮件"文件夹，该怎办？

ZAP 将基于您在本主题前面描述的配置对邮件执行操作。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>如果使用安全发件人、邮件流规则或允许/阻止的发件人名列表，该怎怎办？

安全发件人、邮件流规则或阻止和允许组织设置优先。 这些消息将从 ZAP 中排除，因为服务按你配置的任务进行操作。 这是为配置邮件而跳过筛选时要谨慎的另一个原因。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>如果将邮件移到其他文件夹（例如收 (规则规则，该怎) ？

只要未删除消息，或者操作尚未应用，ZAP 仍可正常工作。 例如，如果网络钓鱼策略设置为隔离，且用户或管理员已对电子邮件隔离垃圾邮件，那么隔离邮箱将执行隔离操作来隔离该文件。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP 对邮箱的保留影响是什么？

ZAP 不会从置于保留状态的邮箱中隔离邮件。 ZAP 可以根据为反垃圾邮件策略中的垃圾邮件或网络钓鱼欺解配置的操作，将邮件移动到"垃圾邮件"文件夹。

有关 Exchange Online 中的保留的详细信息，请参阅 Exchange [Online 中的"就地保留"和"诉讼保留"。](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)
