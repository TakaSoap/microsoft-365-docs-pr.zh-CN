---
title: 正在转发的新域的电子邮件见解
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: 管理员可以了解如何使用安全 & 合规中心中的"邮件流"仪表板中的"正在转发的新域"电子邮件见解来调查用户何时将邮件转发到从未转发到的外部域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25440898dfd29097985ddf1ffc0c17aa9c017793
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190253"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>安全与合规中心内转发电子邮件见解&域

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

将电子邮件转发给特定域中的外部收件人有有效的业务原因。 但是，当贵组织的用户突然开始将邮件转发到组织中没有人将邮件转发到新域的域中时， (可疑) 。

此条件可能指示用户帐户遭到入侵。 如果您怀疑帐户已被泄露，请参阅响应遭到入侵 [的电子邮件帐户](responding-to-a-compromised-email-account.md)。

安全 **与合规** 中心内 [&](https://protection.office.com) 转发的电子邮件见解的新域在组织用户将邮件转发到新域时通知你。

此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。

![正在转发电子邮件见解的新域。](../../media/mfi-new-domains-being-forwarded.png)

单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括返回 [转发报告的链接](view-mail-flow-reports.md#forwarding-report)。

![详细信息 在单击"正在转发的新域"电子邮件见解后出现的飞出图。](../../media/mfi-new-domains-being-forwarded-details.png)

单击报表仪表板或仪表板上"热门见解"&建议"区域中的"查看全部"后，选择见解后， (**访问** 此 \>  <https://protection.office.com/insightdashboard> 详细信息) 。

若要阻止自动将邮件转发到外部域，请为部分或所有外部域配置远程域。 有关详细信息，请参阅管理 Exchange Online 中的[远程域](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。