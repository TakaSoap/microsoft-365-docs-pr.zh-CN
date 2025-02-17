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
ms.collection: M365-security-compliance
ms.openlocfilehash: e23d63a519bf69f94ce4990d8851d673826dcb5c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475072"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>安全与合规中心内转发电子邮件见解&域

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

将电子邮件转发给特定域中的外部收件人有有效的业务原因。 但是，当贵组织的用户突然开始将邮件转发到组织中没有人将邮件转发到新域的域中时， (可疑) 。

此条件可能指示用户帐户遭到入侵。 如果您怀疑帐户已被泄露，请参阅 [响应遭到入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)。

安全 **与合规** 中心内 [&](https://protection.office.com) 转发电子邮件的"新域"通知你，当组织的用户将邮件转发到新域时。

此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。

:::image type="content" source="../../media/mfi-new-domains-being-forwarded.png" alt-text="正在转发的电子邮件见解的新域" lightbox="../../media/mfi-new-domains-being-forwarded.png":::


单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括返回转发 [报告的链接](view-mail-flow-reports.md#forwarding-report)。

:::image type="content" source="../../media/mfi-new-domains-being-forwarded-details.png" alt-text="单击&quot;正在转发的新域&quot;电子邮件见解后出现的&quot;详细信息&quot;飞出" lightbox="../../media/mfi-new-domains-being-forwarded-details.png":::

单击"报告仪表板"或"仪表板"上的"最热门见解&建议"区域中的"查看所有见解"后， (**进入** \> **此详细信息** <https://protection.office.com/insightdashboard>) 。

若要阻止自动将邮件转发到外部域，请为部分或所有外部域配置远程域。 有关详细信息，请参阅管理[远程域中Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。