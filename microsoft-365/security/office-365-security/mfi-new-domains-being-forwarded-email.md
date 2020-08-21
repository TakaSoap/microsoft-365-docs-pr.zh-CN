---
title: 正在转发的新域的电子邮件见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解在新式 Exchange 管理中心如何使用新域转发电子邮件见解，以了解其组织的用户何时将邮件转发到从未转发到的外部域。
ms.openlocfilehash: 0b4cd0490feebc8e05deb889b3cf54e1ea9f5928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826925"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>安全与合规中心转发&的新域

尽管可能有将电子邮件转发给特定域中的外部收件人的正当业务原因，但如果组织中的用户已成功将邮件转发到外部域，而组织中的任何人从未将邮件转发到这些域，然后 (新域) 之前，这也很可疑。 这种情况可能指示用户帐户被了了可能被到即被影响。 如果您所在帐户已被入入入攻击，请参阅"[响应被到解的电子邮件帐户"。](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)

转 **发电子邮件的新域** 见解会在您组织的用户正在向新域转发邮件时通知您。

仅当检测到问题时，该见解是出现的，并且显示在"转 [发报告"页面上](view-mail-flow-reports.md#forwarding-report) 。

![正在转发的新域的电子邮件见解](../../media/mfi-new-domains-being-forwarded.png)

单击小部件时，将出现一个浮出控件，您会在其中找到有关转发邮件的更多详细信息（包括返回到 [转发报告的链接](view-mail-flow-reports.md#forwarding-report)）。

![单击新域转发的电子邮件见解后显示的细化控件](../../media/mfi-new-domains-being-forwarded-details.png)

在**单击"查看** (报表仪表板"或"报表仪表板"的"查看**上级见解"（如果在 (报表仪表板&中**选择所有的见解）后，还可以了解此详细信息**View all** \> **Dashboard** <https://protection.office.com/insightdashboard>) 。

若要防止将邮件自动转发到外部域，请为部分或全部外部域配置远程域。 有关详细信息，请参阅"[在 Exchange Online 中管理远程域"。](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
