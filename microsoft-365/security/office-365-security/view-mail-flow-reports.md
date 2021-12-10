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
ms.openlocfilehash: f742fc9f19d7b360e9402c9bc6331a84d2622979
ms.sourcegitcommit: e246725b0935067aad886530d5178972c0f895d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401291"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>在安全与合规中心的"报告"仪表板中查看&报告

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

除了安全与合规中心内"邮件流"仪表板中[](mail-flow-insights-v2.md)提供的邮件流报告之外，"报告"仪表板中还提供了各种其他邮件流报告，以帮助您监视 Microsoft 365 组织。 &

如果您具有 [必要的权限](#what-permissions-are-needed-to-view-these-reports)，可以在安全与合规&查看这些报告，访问报告 <https://protection.office.com>  \> **仪表板**。 若要直接转到"报表"仪表板，请打开 <https://protection.office.com/insightdashboard> 。

![安全与合规中心&仪表板。](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>连接器报告

> [!NOTE]
> 此报告已替换为 EAC 中的 **入站** 邮件报表和出 **站** 邮件报告。 有关详细信息，请参阅新 EAC 中的入站邮件和 [出站邮件报告](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports)。

## <a name="exchange-transport-rule-report"></a>Exchange传输规则报告

**"Exchange传输** 规则"报告显示邮件流规则对 (传入和传出邮件) 传输规则的影响。

若要查看报告，请在 打开安全与合规 <https://protection.office.com> &，转到报告仪表板 \> ，然后选择"Exchange **规则"。** 若要直接转到报告，请打开 <https://security.microsoft.com/reports/ETRRuleReport> 。

![Exchange仪表板中的"传输规则"小部件。](../../media/scc-transport-rule-report-widget.png)

> [!NOTE]
> 单击安全与合规中心&此报告的小部件 (protection.office.com) 现在将你查看 Microsoft 365 Defender 门户 (security.microsoft.com) 。 有关报告的详细信息，请参阅Exchange[传输规则报告](view-email-security-reports.md#exchange-transport-rule-report)。

## <a name="forwarding-report"></a>转发报告

> [!NOTE]
> 转发 **报告现已** 在 EAC 中提供。 有关详细信息，请参阅新 [EAC 中的自动转发邮件报告](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>邮件流状态报告

邮件 **流状态报告** 类似于"已发送和已接收 [电子邮件](#sent-and-received-email-report)"报告，包含有关边缘上允许或阻止的电子邮件的其他信息。 这是包含边缘保护信息的唯一报告，它只显示 EOP 服务允许其进入服务进行评估之前阻止Exchange Online Protection (电子邮件) 。 必须了解，如果将一封邮件发送给五个收件人，我们会将邮件计为五个不同的邮件，而不是一封邮件。

若要查看报告，请打开安全与&中心，**转到"**[报告仪表板](https://protection.office.com)" \> 并选择"**邮件流状态报告"。** 若要直接转到邮件 **流状态报告，** 请打开 <https://security.microsoft.com/reports/mailflowStatusReport> 。

!["报告"仪表板中的"邮件流状态报告"小部件。](../../media/scc-mail-flow-status-report-widget.png)

> [!NOTE]
> 单击安全与合规中心&此报告的小部件 (protection.office.com) 现在将你查看 Microsoft 365 Defender 门户 (security.microsoft.com) 。 有关报告的详细信息，请参阅 [邮件流状态报告](view-email-security-reports.md#mailflow-status-report)。

## <a name="sent-and-received-email-report"></a>已发送和已接收电子邮件报告

> [!NOTE]
> 此报告已替换为邮件 [流状态报告](#mailflow-status-report)。

## <a name="top-senders-and-recipients-report"></a>首要发件人和收件人报告

"**主要** 发件人和收件人"显示组织中排名居前的邮件发件人，以及 EOP 和 Defender 检测到的邮件的顶级Office 365保护功能。

若要查看报告，请在 打开安全与合规& <https://protection.office.com> 中心，转到报告仪表板 \> ，然后选择 **"顶级发件人和收件人"。** 若要直接转到报告，请打开以下 URL 之一：

- Defender for Office 365：<https://protection.office.com/TopSenderRecipientsATP>
- EOP： <https://protection.office.com/TopSenderRecipients>

!["报告"仪表板中的"顶部发件人和收件人"小组件。](../../media/scc-top-senders-and-recipients-widget.png)

> [!NOTE]
> 尽管单击安全与合规中心中此&小组件将你 protection.office.com 页面，但页面内容来自 Microsoft 365 Defender 门户。 有关报告的详细信息，请参阅 Top [senders and recipients report](view-email-security-reports.md#top-senders-and-recipients-report)。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报告需要哪些权限？

若要查看和使用本文中所述的报告，你需要是安全与合规中心内以下角色&之一：

- **组织管理**
- **安全管理员**
- **安全信息读取者**
- **全局读取者**

有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

> [!NOTE]
> 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="related-topics"></a>相关主题

[安全与合规中心内的智能报告和见解](reports-and-insights-in-security-and-compliance.md)

[安全与合规中心内的邮件流见解](mail-flow-insights-v2.md)

[查看安全与合规中心内的电子邮件安全报告](view-email-security-reports.md)

[查看 Microsoft Defender for Office 365](view-reports-for-mdo.md)
