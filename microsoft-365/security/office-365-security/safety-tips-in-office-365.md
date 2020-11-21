---
title: 电子邮件中的安全提示
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
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: 了解 EOP 和 Office 365 如何通过将安全提示添加到电子邮件顶部来保护您的垃圾邮件、网络钓鱼和恶意软件阻止。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e36887e2bb0146c86a8a4f1526f1e712a38b46ba
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376615"
---
# <a name="safety-tips-in-email-messages"></a>电子邮件中的安全提示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) 和 Microsoft 365 保护你的垃圾邮件、网络钓鱼和恶意软件防护。 如今，其中一些攻击非常精心编制，使其看起来是合法的。 将邮件发送到 "垃圾邮件" 文件夹并不总是足够。 现在，当您在 Outlook 或 web 上的 Outlook 或任何电子邮件客户端中检查您的电子邮件时，EOP 会自动检查发件人，并将安全提示添加到电子邮件的顶部。

Outlook 中的安全提示不依赖于所使用的 Outlook 版本，因为安全提示被破译开放并直接插入到邮件正文中。 这意味着安全提示将显示在所使用的任何电子邮件客户端中。 它是在电子邮件筛选器级别完成的，不是在邮件客户端级别呈现的，因此，它不仅显示在任何版本的 Outlook 中，还会显示在任何电子邮件客户端中。

安全提示--有颜色编码的邮件--将警告您可能有害的邮件。 您的收件箱中的大多数邮件不会有安全提示。 只有在 EOP 和 Microsoft 365 包含可帮助阻止垃圾邮件、网络钓鱼和恶意软件攻击的信息时，才会看到它们。 如果安全提示确实显示在收件箱中，则可以使用以下示例来了解有关每种安全提示的详细信息。

- 可疑邮件 (红色安全提示) 。

    ![显示红色安全提示的屏幕截图。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    电子邮件中的红色安全提示意味着您收到的邮件包含可疑的内容，如仿冒骗局。 我们建议您从收件箱中删除此类电子邮件，而无需打开它。

- 安全邮件 (绿色安全提示) 。

    ![显示绿色安全提示的屏幕截图。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    除了不安全的邮件之外，我们还将通过绿色安全提示告诉你我们信任的发件人发来的有效邮件。 电子邮件中的绿色安全提示意味着我们检查邮件的发件人并验证其安全。 Microsoft 维护此受信任发件人列表，其中包括金融组织和经常被欺骗或模拟的人。

## <a name="working-with-safety-tips"></a>使用安全提示

始终为 web 上的 Outlook 启用安全提示，即使每封邮件都将收到一个。 管理员可以关闭其他电子邮件客户端（如 Outlook）的安全提示。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您不同意 EOP 如何对邮件进行分类 (也就是说，邮件不是垃圾邮件，也不会被标记为垃圾邮件) 。您可以将邮件提交给 Microsoft 进行分析以帮助更好地体验。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。 您还可以单击安全提示中的 "反馈" 链接以将评论直接提交给 Microsoft，以帮助我们改进。
