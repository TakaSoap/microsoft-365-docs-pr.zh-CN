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
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: 了解 EOP 和 Office 365 如何在电子邮件顶部添加安全提示，保护您免受垃圾邮件、网络钓鱼和恶意软件的侵害。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2eae3f17d4ba9b72383bf1b8864a136cd9e7b2b8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288557"
---
# <a name="safety-tips-in-email-messages"></a>电子邮件中的安全提示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) 和 Microsoft 365 可保护您免受垃圾邮件、网络钓鱼和恶意软件防护的侵害。 如今，其中一些攻击精心制作，看起来是合法的。 将邮件发送到"垃圾邮件"文件夹并不总是足够。 现在，当您在 Outlook 或 Web 上的 Outlook 或任何电子邮件客户端中检查电子邮件时，EOP 会自动检查发件人，并将安全提示添加到电子邮件顶部。

Outlook 中的安全提示不取决于您使用的 Outlook 版本，因为安全提示被破解打开并直接插入到邮件正文中。 这意味着安全提示将在你使用的任何电子邮件客户端中显示。 它在电子邮件筛选器级别完成，不会在邮件客户端级别呈现，因此它不仅显示在任何版本的 Outlook 中，还显示在任何电子邮件客户端中。

安全提示（颜色编码的消息）将警告你潜在有害的邮件。 收件箱中的大多数邮件没有安全提示。 只有在 EOP 和 Microsoft 365 具有有助于防止垃圾邮件、网络钓鱼和恶意软件攻击的信息时，你才能看到它们。 如果收件箱中显示安全提示，可以使用以下示例了解有关每种类型的安全提示的信息。

- 可疑邮件 (红色安全提示) 。

    ![显示红色安全提示的屏幕截图。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    电子邮件中的红色安全提示意味着你收到的邮件包含可疑内容，例如欺诈邮件。 我们建议您从收件箱中删除此类电子邮件，而不打开它。

- 安全邮件 (绿色安全提示) 。

    ![显示绿色安全提示的屏幕截图。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    除了不安全的邮件之外，我们还将告知你来自我们信任的发件人的有效邮件以及绿色安全提示。 电子邮件中的绿色安全提示意味着我们检查了邮件的发件人，并验证了邮件是否安全。 Microsoft 维护此受信任发件人列表，其中包括金融组织和其他经常欺骗或模拟的发件人。

## <a name="working-with-safety-tips"></a>使用安全提示

始终为 Web 上的 Outlook 启用安全提示，即使不是每封邮件都会收到一条。 管理员可以关闭其他电子邮件客户端（如 Outlook）的安全提示。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您对 EOP 对邮件进行分类的方法有 (即，该邮件不是垃圾邮件，或者应该将其标记为垃圾邮件) ，可以将邮件提交给 Microsoft 进行分析，以帮助改善体验。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。 还可以单击安全提示中的"反馈"链接，直接向 Microsoft 提交评论以帮助我们改进。
