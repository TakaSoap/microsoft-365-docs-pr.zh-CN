---
title: 在"报告"仪表板中查看邮件流报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解安全与合规中心的"报告"仪表板中&报告。
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1fc133a8e05541f402e35cf8d62ee9662af661b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476216"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>在安全与合规中心的"报告"仪表板中&流报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> 本文中的大多数报告也可在 EAC Microsoft 365 Defender管理中心Exchange (查看) 。 有关详细信息，请参阅下列主题：
>
> - [新管理中心中的Exchange报告](/exchange/monitoring/mail-flow-reports/mail-flow-reports)
> - [在电子邮件门户中查看Microsoft 365 Defender报告](view-email-security-reports.md)

除了安全 & 合规中心的邮件流仪表板中提供的邮件流[](mail-flow-insights-v2.md)报告之外，报告仪表板中还提供了各种其他邮件流报告，以帮助您监视 Microsoft 365 组织。

如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在安全与合规中心内通过&"<https://protection.office.com>报告仪表板"查看 **这些报告**\>。 若要直接转到"报表"仪表板，请打开 <https://protection.office.com/insightdashboard>。

:::image type="content" source="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png" alt-text="安全与合规中心&报告仪表板" lightbox="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png":::

## <a name="connector-report"></a>连接器报告

> [!NOTE]
> 此报告已替换为 EAC 中的 **入站** 邮件报表和出 **站** 邮件报告。 有关详细信息，请参阅新 EAC 中的入站邮件 [和出站邮件报告](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports)。

## <a name="exchange-transport-rule-report"></a>Exchange传输规则报告

"**Exchange传输** 规则"报告显示邮件流规则对 (传入和传出邮件) 传输规则的影响。

若要查看报告，请在 打开<https://protection.office.com>安全与&合规中心，\>转到"报告仪表板"，然后选择"Exchange **规则"**。 若要直接转到报告，请打开 <https://security.microsoft.com/reports/ETRRuleReport>。

:::image type="content" source="../../media/scc-transport-rule-report-widget.png" alt-text="报表Exchange中的&quot;传输规则&quot;小组件" lightbox="../../media/scc-transport-rule-report-widget.png":::

> [!NOTE]
> 当前 **Exchange** EAC 中提供了传输规则报告。 有关详细信息，请参阅Exchange [EAC 中的传输规则报告](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report)。

## <a name="forwarding-report"></a>转发报告

> [!NOTE]
> 转发 **报告现已** 在 EAC 中提供。 有关详细信息，请参阅新 [EAC 中的自动转发邮件报告](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>邮件流状态报告

邮件 **流状态报告** 类似于"已发送和已接收 [电子邮件](#sent-and-received-email-report)"报告，包含有关边缘上允许或阻止的电子邮件的其他信息。 这是包含边缘保护信息的唯一报告，并且只显示 EOP 服务允许其进入服务进行评估之前阻止Exchange Online Protection (电子邮件) 。 必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。

若要查看报告，请打开安全与&中心，\>转到"报告 [仪表板](https://protection.office.com)**"并选择"****邮件流状态报告"**。 若要直接转到邮件 **流状态报告，** 请打开 <https://security.microsoft.com/reports/mailflowStatusReport>。

:::image type="content" source="../../media/scc-mail-flow-status-report-widget.png" alt-text="&quot;报告&quot;仪表板中的&quot;邮件流状态报告&quot;小部件" lightbox="../../media/scc-mail-flow-status-report-widget.png":::

> [!NOTE]
> 单击安全与合规中心&此报告的小部件 (protection.office.com) 现在将你查看 Microsoft 365 Defender 门户 (security.microsoft.com) 。 有关报告的详细信息，请参阅 [邮件流状态报告](view-email-security-reports.md#mailflow-status-report)。

## <a name="sent-and-received-email-report"></a>已发送和已接收电子邮件报告

> [!NOTE]
> 此报告已被 [Mailflow 状态报告取代](#mailflow-status-report)。

## <a name="top-senders-and-recipients-report"></a>首要发件人和收件人报告

The **Top senders and recipients** shows the top messages senders in your organization， and the top recipients for messages that were detected by EOP and Defender for Office 365 protection features.

若要查看报告，请在 打开安全与&中心，**转到"**\>报告仪表板<https://protection.office.com>"**，然后选择"****顶级发件人和收件人"**。 若要直接转到报告，请打开以下 URL 之一：

- Defender for Office 365：<https://protection.office.com/TopSenderRecipientsATP>
- EOP： <https://protection.office.com/TopSenderRecipients>

:::image type="content" source="../../media/scc-top-senders-and-recipients-widget.png" alt-text="&quot;报告&quot;仪表板中的&quot;热门发件人和收件人&quot;小组件" lightbox="../../media/scc-top-senders-and-recipients-widget.png":::

> [!NOTE]
> 尽管单击安全与合规中心中此报告的小部件&一个 protection.office.com 页面，但页面内容来自 Microsoft 365 Defender 门户。 有关报告的详细信息，请参阅 Top [senders and recipients report](view-email-security-reports.md#top-senders-and-recipients-report)。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报告需要哪些权限？

若要查看和使用本文中所述的报告，你需要是安全与合规中心内以下角色组&之一：

- **组织管理**
- **安全管理员**
- **安全读者**
- **全局读取者**

有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

> [!NOTE]
> 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="related-topics"></a>相关主题

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)

[安全与合规中心内的邮件流见解](mail-flow-insights-v2.md)

[查看安全与合规中心内的电子邮件安全报告](view-email-security-reports.md)

[查看 Microsoft Defender for Office 365](view-reports-for-mdo.md)
