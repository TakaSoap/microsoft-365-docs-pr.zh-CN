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
description: 了解 EOP 和 Office 365 如何通过向最上面的电子邮件添加安全提示来为您提供垃圾邮件、网络钓鱼和恶意软件防护。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e13e9cce325dfd3f8312c1d68459ab3c423c1fbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827477"
---
# <a name="safety-tips-in-email-messages"></a>电子邮件中的安全提示

Exchange Online Protection (，) 、网络钓鱼和恶意软件防护功能保护您。 现在，其中的某些攻击非常合理，所以它非常合理。 向"垃圾邮件"文件夹发送邮件并非总是够的。 现在，在 Outlook 或 Outlook 网页版或任何电子邮件客户端中查看电子邮件时，EOP 会自动检查发件人，并在电子邮件顶部添加安全提示。

Outlook 中的安全提示不取决于您使用的 Outlook 版本，因为安全提示已被错误打开，并直接插入到邮件正文中。 这意味着无论您使用哪个电子邮件客户端，安全提示都将显示。 它是在电子邮件筛选级别执行的，不在邮件客户端级别呈现，所以不仅在任何版本的 Outlook 中显示，而且还会显示在任何电子邮件客户端中。

安全提示（彩色标记消息）将警告您潜在的有害消息。 收件箱中的大多数邮件都不具有安全提示。 仅当 EOP 和 Microsoft 365 拥有可防止垃圾邮件、网络钓鱼和恶意软件攻击所需的信息时，才能看到它们。 如果收件箱中显示安全提示，则可以使用以下示例了解有关每种安全提示的详细信息。

- 可疑邮件被 (安全提示) 。

    ![显示红色安全提示的屏幕截图。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    电子邮件中的红色安全提示意味着您收到的邮件包含可疑的邮件，如钓鱼邮件。 建议您从收件箱中删除此类电子邮件，而不用打开。

- 垃圾邮件配置内向 (安全提示) 。

    ![显示黄色安全提示的屏幕截图。](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    电子邮件中的黄色安全提示表示邮件已标记为垃圾邮件。 如果您不识别并信任邮件发件人，则不下载任何附件或图片，也不要单击邮件中的任何链接。 在 Outlook 网页版中，可以单击 **垃圾邮件** 项黄色栏中的垃圾邮件以将邮件移动到收件箱中的垃圾邮件。 如果传递给收件箱的邮件上出现黄色安全提示，则可能是因为您已禁用将垃圾邮件移动到"垃圾邮件"文件夹。

-  (安全邮件和绿色安全) 。

    ![显示绿色安全提示的屏幕截图。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    除了不安全的邮件外，我们还会告诉您对于来自发件人的有效邮件（受到绿色安全提示的信任）。 电子邮件中的绿色安全提示意味着我们检查了邮件的发件人并验证其安全。 Microsoft 维护此受信任的发件人列表，其中包括财经组织和其他通常被欺骗或模拟的发件人。

- 未筛选的邮件和 (安全提示) 。

    ![显示灰色安全提示的屏幕截图。](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    当我们发现邮件来自你信任安全发件人列表的发件人或是否存在邮件流规则以绕过筛选时，我们还会通知你。

    在阻止外部图像，即邮件位于收件箱中并且不显示为垃圾邮件，但包含你未选择下载的外部图像时，显示灰色安全提示。

## <a name="working-with-safety-tips"></a>使用安全提示

安全提示始终为 Outlook 网页版启用，即使并非每封邮件都收到一封邮件。 管理员可以关闭其他电子邮件客户端（如 Outlook）的安全提示。 有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

如果您同质地对邮件 (（也就是说，不是垃圾邮件或应标记为垃圾邮件) ）进行分类，您可以将邮件提交给 Microsoft 进行分析以帮助您更好地获取您的体验。 有关说明，请参阅"[报告邮件和文件"发送到 Microsoft。](report-junk-email-messages-to-microsoft.md) 也可单击安全提示中的反馈链接，直接向 Microsoft 提交评论，以帮助我们改进。
