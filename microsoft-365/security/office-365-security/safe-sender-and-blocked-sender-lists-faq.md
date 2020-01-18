---
title: Exchange Online 中的安全发件人和阻止发件人列表
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: 作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238389"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online 中的安全发件人和阻止发件人列表

作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。

若要了解如何在 Office 365 中将电子邮件标记为垃圾邮件，*请参阅更新版本的提示和过程。有关如何在* [Office 中阻止将电子邮件标记为垃圾邮件](prevent-email-from-being-marked-as-spam.md)的管理员。

如果你不是管理员，并且只想使用安全发件人列表在 Outlook 中管理自己的垃圾邮件，请查看[垃圾邮件筛选器概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)中的步骤。

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Exchange Online 中的安全发件人限制和阻止发件人限制是什么？

Exchange Online 中的安全发件人限制和阻止发件人限制与 Active Directory 和 Outlook 限制不同。区别在于：

- 安全发件人限制：1024

- 阻止的发件人限制：500

注意：

您可能会遇到[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述的错误。 若要解决此问题，请清除 "信任来自我的联系人的电子邮件" 复选框。 或者，减少默认 "联系人" 文件夹中的电子邮件地址量，使其在 Exchange Online 中为 "MaxSafeSenders" 属性设置的最大允许限制为1024。 有关此属性和 Set 邮箱 cmdlet 的详细信息，请 seethe 以下主题：

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>另请参阅

[Exchange Server 中的发件人筛选](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
