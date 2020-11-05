---
title: 正在转发的新域的电子邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全 & 合规中心中的 "邮件流" 仪表板中的新域转发电子邮件，以调查其用户何时将邮件转发到从未转发到的外部域。
ms.openlocfilehash: f2d8c9229062cbef0ad90b3d0fd843d6588a08dc
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920558"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>在安全 & 合规中心中转发的新域的电子邮件洞察力

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


将电子邮件转发给特定域中的外部收件人的商业原因有很多。 但是，当组织中的用户突然开始将邮件转发到域时，您的组织中没有任何人将邮件转发给 (新域) 的域是可疑的。

这种情况可能表示用户帐户受到威胁。 如果您怀疑帐户已损坏，请参阅 [响应已泄露的电子邮件帐户](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。

当您组织中的用户将邮件转发到新域时，将在 [安全 & 合规中心](https://protection.office.com)中 **转发的新域** 将向您发出通知。

此洞察力仅在检测到问题时显示，并显示在 " [转发报告](view-mail-flow-reports.md#forwarding-report) " 页上。

![正在转发的新域的电子邮件见解](../../media/mfi-new-domains-being-forwarded.png)

当您单击该小组件时，将显示一个弹出对话框，您可在其中找到有关转发邮件的更多详细信息，包括返回到 [转发报告](view-mail-flow-reports.md#forwarding-report)的链接。

![单击正在转发的新域的电子邮件洞察力之后显示的详细信息浮出控件](../../media/mfi-new-domains-being-forwarded-details.png)

当您在 ( **报告** 仪表板 "或") 上的 " **热门见解 & 建议** " 区域中单击 " **查看全部** " 后，您还可以转到此详细信息页面 \> **Dashboard** <https://protection.office.com/insightdashboard> 。

若要阻止自动将邮件转发到外部域，请为部分或全部外部域配置远程域。 有关详细信息，请参阅 [在 Exchange Online 中管理远程域](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
