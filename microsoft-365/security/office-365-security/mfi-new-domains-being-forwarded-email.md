---
title: 正在转发的新域的电子邮件见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中转发的电子邮件见解的新域，以调查用户何时将邮件转发到从未转发到的外部域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150593"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>安全与合规中心内转发电子邮件见解&域

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

将电子邮件转发给特定域中的外部收件人有一些有效的业务原因。 但是，当贵组织的用户突然开始将邮件转发到组织中没有人将邮件转发到新域域的域时 (可疑) 。

此条件可能指示用户帐户受到威胁。 如果怀疑帐户已被泄露，请参阅"响应遭到入侵[的电子邮件帐户"。](responding-to-a-compromised-email-account.md)

当 **组织的用户** 将邮件转发到新域时，安全与合规中心 [&](https://protection.office.com) 转发电子邮件见解的新域会通知你。

此见解仅在检测到问题时显示，并且显示在"转发 [报告"页上](view-mail-flow-reports.md#forwarding-report) 。

![正在转发的新域的电子邮件见解](../../media/mfi-new-domains-being-forwarded.png)

单击小部件时，将出现一个飞出控件，您可以在其中找到有关转发邮件的更多详细信息，包括返回转发 [报告的链接](view-mail-flow-reports.md#forwarding-report)。

![单击"正在转发的新域"电子邮件见解后显示的详细信息飞出](../../media/mfi-new-domains-being-forwarded-details.png)

在报表仪表板或仪表板上单击"查看所有热门见解"&建议区域中选择见解 **后，也可以** 访问 ( \> 页面 <https://protection.office.com/insightdashboard>) 。

若要阻止自动将邮件转发到外部域，请为部分或所有外部域配置远程域。 有关详细信息，请参阅管理 [Exchange Online 中的远程域](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
