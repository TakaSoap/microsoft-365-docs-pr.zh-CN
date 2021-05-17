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
description: 了解 EOP 和 Office 365如何在电子邮件顶部添加电子邮件安全提示垃圾邮件、网络钓鱼和恶意软件防护。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994981"
---
# <a name="safety-tips-in-email-messages"></a>电子邮件中的安全提示

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) Microsoft 365垃圾邮件、网络钓鱼和恶意软件防护保护您。 如今，其中一些攻击精心制作，看起来是合法的。 将邮件发送到"垃圾邮件"文件夹并不总是足够。 现在，当您在 Outlook 或 Outlook 或任何电子邮件客户端中检查电子邮件时，EOP 会自动检查发件人，并将 安全提示 添加到电子邮件顶部。

安全提示Outlook你使用的 Outlook，因为 安全提示 被破解打开并直接插入到邮件正文中。 这意味着，安全提示显示在你使用的任何电子邮件客户端中。 它在电子邮件筛选器级别完成，不会在邮件客户端级别呈现，因此它不仅显示在 Outlook 的任何版本中，它还显示在任何电子邮件客户端中。

此安全提示一条颜色编码的邮件，将警告你有关可能有害的邮件。 收件箱中的大多数邮件不会显示安全提示。 只有在 EOP 和 Microsoft 365这些信息来帮助阻止垃圾邮件、网络钓鱼和恶意软件攻击时，你才能看到这些信息。 如果收件箱中显示安全提示，可以使用以下示例了解有关每种类型的安全安全提示。

- 可疑邮件 (红色安全提示) 。

    ![显示红色图标的安全提示。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    电子邮件安全提示红色邮件表示您收到的邮件包含可疑邮件，如欺诈邮件。 我们建议您从收件箱中删除此类电子邮件，而不将其打开。

- 保险箱绿色 (邮件安全提示) 。

    ![显示绿色图标的安全提示。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    除了不安全的邮件之外，我们还将告知您来自我们信任的绿色发件人的有效安全提示。 电子邮件安全提示绿色标识意味着我们检查了邮件的发件人，并验证了邮件是否安全。 Microsoft 维护此受信任发件人列表，其中包括金融组织和其他经常欺骗或模拟的发件人。

## <a name="working-with-safety-tips"></a>使用安全提示

管理员可以在反垃圾邮件策略中打开或关闭安全提示。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您对 EOP 如何对邮件进行分类（即 (该邮件不是垃圾邮件或应该将其标记为垃圾邮件) ）的不一致，您可以将邮件提交给 Microsoft 进行分析，以帮助改善您的体验。 有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。 还可以单击"反馈"链接安全提示直接向 Microsoft 提交评论，以帮助我们改进。
