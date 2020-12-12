---
title: '零时差自动清除 (ZAP) '
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
description: 管理员可以了解零时差自动清除 (ZAP) 如何以反向方式将 Exchange Online 邮箱中的已传递邮件移动到垃圾邮件文件夹或被反向发现为垃圾邮件或网络钓鱼的隔离邮箱。
ms.openlocfilehash: 7b43fb46adacfe1e9f1e7e622122df90e747ff44
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659425"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online 中的零时 (ZAP) 清除

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>ZAP 的基本功能

在 Exchange Online 中具有邮箱的 Microsoft 365 组织中，零时差自动清除 (ZAP) 是一种电子邮件保护功能，可反作用地检测和消除已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。

ZAP 在保护本地 Exchange 邮箱的独立 Exchange Online Protection (EOP) 环境中不起作用。

## <a name="how-zap-works"></a>ZAP 的工作原理

垃圾邮件和恶意软件签名每天在服务中实时更新。 但是，用户仍可以出于各种原因接收恶意消息，包括内容在传送给用户后是否被武器化。 ZAP 通过持续监视服务中垃圾邮件和恶意软件签名的更新来解决此问题。 ZAP 可以查找和删除用户邮箱中已有的邮件。

ZAP 操作对于用户是无缝的;如果检测到并移动了邮件，则系统不会通知他们。

[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则 (传输规则) 收件箱规则或其他筛选器优先于 ZAP。 与邮件流中发生的情况类似，这意味着即使服务确定已传递的邮件需要 ZAP，由于安全发件人配置，邮件不会运行。 这是在配置邮件以绕过筛选时要谨慎的另一个原因。

### <a name="malware-zap"></a>恶意软件 ZAP

对于 **在传递** 后发现包含恶意软件的已读邮件或未读邮件，ZAP 隔离包含恶意软件附件的邮件。 只有管理员可以查看和管理隔离的恶意软件邮件。

反恶意软件策略中默认启用恶意软件 ZAP。 有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>网络钓鱼 ZAP

对于 **在** 传递后被标识为网络钓鱼的已读邮件或未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为网络钓鱼电子邮件筛选裁定配置的操作。 以下列表介绍了可用于网络钓鱼的筛选裁定操作及其可能的 ZAP 结果：

- **添加 X-Header，****在主题行前附加文本**：ZAP 不对邮件执行任何操作。

- **将邮件** 移动到"垃圾邮件"：ZAP 会将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (它默认启用) 。 有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。

- **将邮件重定向到电子邮件地址**， **删除邮件**， **隔离邮件**：ZAP 隔离邮件。

默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，而网络钓鱼电子邮件筛选裁定的默认操作是隔离邮件，这意味着默认情况下，网络钓鱼 ZAP 会隔离邮件。

有关配置垃圾邮件筛选裁定的信息，请参阅在 Microsoft [365](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。

### <a name="spam-zap"></a>垃圾邮件 ZAP

对于 **在** 传递后被标识为垃圾邮件的未读邮件，ZAP 结果取决于为适用的反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作。 以下列表描述了垃圾邮件的可用筛选裁定操作及其可能的 ZAP 结果：

- **添加 X-Header，****在主题行前附加文本**：ZAP 不对邮件执行任何操作。

- **将邮件** 移动到"垃圾邮件"：ZAP 会将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (它默认启用) 。 有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。

- **将邮件重定向到电子邮件地址**， **删除邮件**， **隔离邮件**：ZAP 隔离邮件。 最终用户可以查看和管理自己的垃圾邮件隔离邮件。

默认情况下，反垃圾邮件策略中启用垃圾邮件 ZAP，垃圾邮件筛选裁定的默认操作是"将邮件移动到垃圾邮件"文件夹，这意味着垃圾邮件 ZAP 默认情况下会将未读邮件移动到"垃圾邮件"文件夹。 

有关配置垃圾邮件筛选裁定的信息，请参阅在 Microsoft [365](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>适用于 Office 365 的 Microsoft Defender 的 ZAP 注意事项

ZAP 不会隔离安全附件扫描中的动态传递过程中的任何邮件 [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)，或者 EOP 恶意软件筛选已用恶意软件警报文件替换附件 **Text.txt邮件。** 如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选裁定设置为对邮件 (移动到垃圾邮件、重定向、删除或隔离) 则 ZAP 将默认为"移动到垃圾邮件"操作。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否移动了邮件

若要确定 ZAP 是否移动了邮件，可以使用威胁防护[](view-email-security-reports.md#threat-protection-status-report)状态报告或威胁资源管理器 (实时检测[) 。 ](threat-explorer.md) 请注意，作为系统操作，ZAP 不会记录在 Exchange 邮箱审核日志中。

## <a name="zap-faq"></a>ZAP 常见问题解答

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>如果合法邮件移动到"垃圾邮件"文件夹，会发生什么情况？

你应该遵循误报的正常 [报告过程](report-junk-email-messages-to-microsoft.md)。 邮件从收件箱移动到垃圾邮件文件夹的唯一原因是服务已确定邮件是垃圾邮件或恶意邮件。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>如果我使用隔离文件夹而不是"垃圾邮件"文件夹，该做什么？

ZAP 将基于反垃圾邮件策略的配置对邮件采取措施，如本文前面所述。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>如果我使用安全发件人、邮件流规则或允许/阻止的发件人列表，该做什么？

安全发件人、邮件流规则或阻止和允许组织设置优先。 这些消息从 ZAP 中排除，因为服务正在执行你配置它要执行的工作。 这是在配置邮件以绕过筛选时要谨慎的另一个原因。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>如果将邮件移动到其他文件夹（例如收件箱规则 (，) ？

只要邮件尚未删除，或者只要尚未应用相同或更强的操作，ZAP 仍然有效。 例如，如果防钓鱼策略设置为隔离，并且邮件已位于垃圾邮件中，则 ZAP 将采取措施来隔离邮件。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP 对保留的邮箱有何影响？

ZAP 不会隔离来自保留邮箱的邮件。 ZAP 可以基于为反垃圾邮件策略中的垃圾邮件或网络钓鱼裁定配置的操作，将邮件移动到"垃圾邮件"文件夹。

有关 Exchange Online 中的保留功能，请参阅 Exchange Online 中的就地 [保留和诉讼保留](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。
