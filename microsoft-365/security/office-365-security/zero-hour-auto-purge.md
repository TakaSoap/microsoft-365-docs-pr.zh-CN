---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
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
description: 零时差自动清除 (ZAP) 以反作用方式将 Exchange Online 邮箱中的已送达邮件移动到垃圾邮件文件夹或隔离邮箱，这些邮件在传递后被识别为垃圾邮件、网络钓鱼或包含恶意软件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ebfe8bd2eec176b57cfa55400525c8379f9ef4c8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197853"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>零时差自动清除 (ZAP) 中Exchange Online

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>零时差自动清除 (ZAP) 基础知识

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，零时差自动清除 (ZAP) 是一种电子邮件保护功能，可主动检测并消除已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。

ZAP 在保护内部部署邮箱Exchange Online Protection (EOP) 环境中Exchange工作。

## <a name="how-zap-works"></a>ZAP 的工作原理

垃圾邮件和恶意软件签名每天在服务中实时更新。 但是，用户仍可能会因各种原因收到恶意消息，包括内容在传送给用户后是否遭到武器化。 ZAP 通过持续监视服务中垃圾邮件和恶意软件签名的更新来解决此问题。 ZAP 可以查找和删除用户邮箱中已有的邮件。

ZAP 操作对于用户是无缝的;如果检测到并移动了邮件，系统不会通知他们。

[保险箱列表、](create-safe-sender-lists-in-office-365.md)邮件流规则 (传输规则) 收件箱规则或其他筛选器优先于 ZAP。 与邮件流中发生的情况类似，这意味着即使服务确定已传递的邮件需要 ZAP，由于安全发件人配置，邮件不会运行。 这是在配置邮件以绕过筛选时要谨慎的另一个原因。

### <a name="zero-hour-auto-purge-zap-for-malware"></a>零时差自动清除 (ZAP) 恶意软件

对于 **在传递后** 发现包含恶意软件的已读邮件或未读邮件，ZAP 隔离包含恶意软件附件的邮件。 默认情况下，只有管理员可以查看和管理隔离的恶意软件邮件。 但是，管理员可以创建并使用 _隔离_ 策略来定义允许用户对被隔离为恶意软件的邮件执行哪些操作。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

恶意软件的 ZAP 在反恶意软件策略中默认启用。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>针对网络钓鱼的零时差 (ZAP) 清除

对于 **在** 传递后标识为网络钓鱼的已读邮件或未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为网络钓鱼电子邮件筛选裁定配置的操作。 以下列表介绍了针对网络钓鱼的可用筛选裁定操作及其可能的 ZAP 结果：

- **添加 X-Header** **、Prepend subject line with text** **、Redirect message to email address、Delete** **message**：ZAP 对邮件不执行任何操作。

- **将邮件** 移动到垃圾邮件 ：ZAP 将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (该规则默认) 。 有关详细信息，请参阅 Configure [junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)。

- **隔离邮件**：ZAP 隔离邮件。

默认情况下，在反垃圾邮件策略中启用网络钓鱼的 ZAP，而网络钓鱼电子邮件筛选裁定的默认操作是隔离邮件，这意味着默认情况下，网络钓鱼的 ZAP 隔离邮件。

有关配置垃圾邮件筛选裁定的信息，请参阅在 Microsoft 365[中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>零时差自动清除 (ZAP) 高可信度网络钓鱼

对于 **在传递后** 被标识为高可信度网络钓鱼的已读邮件或未读邮件，ZAP 将隔离邮件。 默认情况下，只有管理员可以查看和管理隔离的高可信度钓鱼邮件。 但是，管理员可以创建并使用隔离策略来定义允许用户对被隔离为高可信度网络钓鱼的邮件执行哪些操作。 有关详细信息，请参阅隔离 [策略](quarantine-policies.md)

默认情况下启用高可信度钓鱼邮件的 ZAP。 有关详细信息，请参阅安全[默认值Office 365。](secure-by-default.md)

### <a name="zero-hour-auto-purge-zap-for-spam"></a>垃圾邮件的零时差自动 (ZAP) 清除

对于 **在** 传递后被标识为垃圾邮件的未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为垃圾邮件筛选裁定配置的操作。 垃圾邮件的可用筛选裁定操作及其可能的 ZAP 结果如下列表所述：

- **添加 X-Header** **、Prepend subject line with text** **、Redirect message to email address、Delete** **message**：ZAP 对邮件不执行任何操作。

- **将邮件** 移动到垃圾邮件 ：ZAP 将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (该规则默认) 。 有关详细信息，请参阅 Configure [junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)。

- **隔离邮件**：ZAP 隔离邮件。 默认情况下，最终用户可以查看和管理作为收件人的垃圾邮件隔离邮件。 但是，管理员可以创建并使用 _隔离_ 策略来定义允许用户对被隔离为垃圾邮件的邮件执行哪些操作。 有关详细信息，请参阅隔离 [策略](quarantine-policies.md)

默认情况下，反垃圾邮件策略中已启用垃圾邮件 ZAP，垃圾邮件筛选裁定的默认操作是"将邮件移动到垃圾邮件文件夹"，这意味着默认情况下，垃圾邮件 ZAP 会将未读邮件移动到"垃圾邮件"文件夹。 

有关配置垃圾邮件筛选裁定的信息，请参阅在 Microsoft 365[中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>零时差自动清除 (ZAP) Microsoft Defender for Office 365

ZAP 不会隔离正在 保险箱 附件策略扫描中动态 [](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)传递，或者 EOP 恶意软件筛选已使用恶意软件警报 Text.txt文件替换附件 **的任何邮件。** 如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选裁定设置为对邮件 (移动到垃圾邮件、重定向、删除或隔离) 则 ZAP 将默认为"移动到垃圾邮件"操作。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否移动了邮件

若要确定 ZAP 是否移动了邮件，可以使用威胁防护[](view-email-security-reports.md#threat-protection-status-report)状态报告或威胁资源管理器 (和实时[) 。 ](threat-explorer.md) 请注意，作为系统操作，ZAP 不会记录在Exchange审核日志中。

## <a name="zero-hour-auto-purge-zap-faq"></a>ZAP (常见问题解答) 零时差自动清除

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>如果将合法邮件移动到"垃圾邮件"文件夹，会发生什么情况？

应按照误报的正常 [报告过程操作](report-junk-email-messages-to-microsoft.md)。 邮件从"收件箱"移动到"垃圾邮件"文件夹的唯一原因是服务已确定该邮件是垃圾邮件或恶意邮件。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>如果我使用隔离文件夹而不是垃圾邮件文件夹，应该怎么做？

ZAP 将基于反垃圾邮件策略的配置对邮件采取措施，如本文前面所述。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>如果我使用安全发件人、邮件流规则或允许/阻止的发件人列表，该做什么？

保险箱发件人、邮件流规则或阻止和允许组织设置优先。 这些消息从 ZAP 中排除，因为服务正在执行你配置它所执行的工作。 这是在配置邮件以绕过筛选时要谨慎的另一个原因。

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>ZAP (零时差自动清除) 要求是什么？

对许可证没有限制。 ZAP 适用于联机托管的所有Exchange邮箱。 ZAP 在保护内部部署邮箱Exchange Online Protection (EOP) 环境中Exchange工作。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>如果将邮件移动到其他文件夹（例如收件箱规则 (，) ？

只要邮件尚未删除，或者只要尚未应用相同或更强的操作，零时差自动清除仍有效。 例如，如果反网络钓鱼策略设置为隔离，并且邮件已位于垃圾邮件中，则 ZAP 将采取措施隔离邮件。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP 对保留的邮箱有何影响？

零时差自动清除将隔离来自保留邮箱的邮件。 ZAP 可以基于为反垃圾邮件策略中的垃圾邮件或网络钓鱼裁定配置的操作，将邮件移动到"垃圾邮件"文件夹。

有关 Exchange Online 中保留Exchange Online，请参阅[In-Place Hold and Litigation Hold in Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds)。
