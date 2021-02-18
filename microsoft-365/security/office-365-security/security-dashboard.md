---
title: 安全仪表板概述
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 使用新的安全仪表板查看 Office 365 威胁防护状态，并查看安全警报并采取行动。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 72743f1b052d39ac4762dffc0b3e3e694befa8bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "50288319"
---
# <a name="security-dashboard"></a>安全仪表板

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>基本函数以及如何打开安全仪表板

安全 [&合规](../../compliance/go-to-the-securitycompliance-center.md) 中心使组织能够管理数据保护和合规性。 假设您具有必要的权限，则安全仪表板使您能够查看威胁防护状态，以及查看安全警报并采取行动。

观看视频获取概述，然后阅读本文以了解更多信息。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

根据组织的订阅包括的内容，安全仪表板包括几个小组件，如威胁管理摘要、威胁防护状态、全球每周威胁检测、恶意软件等，如以下部分所述。

若要查看安全仪表板，在 [安全](../../compliance/go-to-the-securitycompliance-center.md)与合规&，请转到 **威胁管理** \> **仪表板**。

> [!NOTE]
> 您必须是全局管理员、安全管理员或安全读者才能查看安全仪表板。 某些小组件需要查看其他权限。 若要了解详细信息，请参阅 [安全与合规中心的访问权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="threat-management-summary"></a>威胁管理摘要

"威胁管理摘要"小组件可一目了然地告知你，在过去 7 到 7 天内， (如何) 威胁。

![安全仪表板 - 威胁管理摘要小组件](../../media/SecDash-ThreatMgmtSummary.png)

你将在威胁管理摘要中看到的信息取决于您的订阅包括哪些内容。 下表介绍了 Office 365 E3 和 Office 365 E5 包含的信息。

|Office 365 E3|Office 365 E5|
|---|---|
|恶意软件邮件被阻止<br>阻止的网络钓鱼邮件<br>用户报告的邮件<br><br><br><br>|恶意软件邮件被阻止<br>阻止的网络钓鱼邮件<br>用户报告的邮件<br>零日恶意软件被阻止<br>检测到高级网络钓鱼邮件<br>阻止的恶意 URL|

若要查看或访问"威胁管理摘要"小组件，您必须有权查看 Defender for Office 365 报告。 若要了解更多信息，请参阅[查看 Defender for Office 365 报告需要哪些权限？。](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="threat-protection-status"></a>威胁防护状态

"威胁防护状态"小部件显示威胁防护的有效性以及网络钓鱼和恶意软件的趋势和详细视图。

![威胁防护状态小组件](../../media/tpswidget.png)

详细信息取决于你的 Microsoft 365 订阅是否包含[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 或不带 Microsoft Defender for Office [365。](office-365-atp.md)

|如果你的订阅包括...|你将看到这些详细信息|
|---|---|
|EOP，而非 Microsoft Defender for Office 365|EOP 检测到并阻止的恶意电子邮件。<p> 请参阅[EOP (威胁防护状态) 。 ](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender for Office 365|EOP 和 Defender for Office 365 检测到并阻止的恶意内容和恶意电子邮件 <p> 包含反恶意软件引擎阻止的恶意内容、零时差自动清除和 Defender [](zero-hour-auto-purge.md)for Office 365 功能 (（包括安全[链接](atp-safe-links.md)、安全附件和 Defender [](atp-safe-attachments.md) [for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) 中的防钓鱼）的唯一电子邮件的聚合计数。 <p> 请参阅 [威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。|

若要查看或访问"威胁防护状态"小组件，必须有权查看 Defender for Office 365 报告。 若要了解更多信息，请参阅查看[Defender for Office 365](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)报告需要哪些权限？

## <a name="global-weekly-threat-detections"></a>全局每周威胁检测

"全球每周威胁检测"小组件显示过去 7 天内电子邮件中检测到 (7) 数。

!["全局每周威胁检测"小组件](../../media/globalweeklythreatdetections.png)

按下表中所述计算指标：

|跃点数|计算方式|
|---|---|
|扫描的邮件|扫描的电子邮件数乘以收件人数|
|威胁已停止|标识为包含恶意软件的电子邮件数乘以收件人数|
|被 [Defender for Office 365 阻止 ](office-365-atp.md)|Defender for Office 365 阻止的电子邮件数乘以收件人数|
|传递后删除|删除的邮件数乘以 [零时差自动](zero-hour-auto-purge.md) 清除数乘以收件人数|

## <a name="malware"></a>恶意软件

恶意软件小组件显示过去 7 个月 7 天内恶意软件趋势和 () 类型。

![恶意软件趋势和系列类型](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>见解

见解不仅涉及应查看的关键问题，还包括要考虑的建议和操作。

![智能见解](../../media/smartinsights.png)

例如，您可能看到正在传递网络钓鱼电子邮件，因为某些用户已禁用其垃圾邮件选项。 若要详细了解见解如何工作，请参阅安全与合规中心中的& [见解](reports-and-insights-in-security-and-compliance.md)。

## <a name="threat-investigation-and-response"></a>威胁调查和响应

如果组织的订阅包含 Microsoft  [Defender for Office 365 计划 2，](office-365-ti.md)则安全仪表板有一个包含高级威胁调查和响应工具的部分。 这些工具包括 [自动调查和响应功能](automated-investigation-response-office.md)。 自动调查和响应在诸如快速解决受损用户帐户 [等方案中很有用](address-compromised-users-quickly.md)。

若要了解更多信息，请参阅 [Office 365](office-365-air.md)中的 AIR (自动) 和响应入门。

## <a name="trends"></a>趋势

安全仪表板底部附近是"趋势"部分，概述了组织的电子邮件流趋势。 报告提供有关分类为垃圾邮件、恶意软件、网络钓鱼尝试和良好电子邮件的电子邮件的信息。 单击磁贴可查看报告中的更多详细信息。

!["趋势"部分总结了组织的电子邮件流趋势](../../media/trends.png)

此外，如果组织的订阅包含 Defender [for Office 365 计划 2，](office-365-ti.md)则本部分中还将提供"最近威胁管理警报"报告，使安全团队可以查看高优先级安全警报并采取措施。

若要查看或访问"已发送和已接收电子邮件"小部件，您必须具有查看 Defender for Office 365 报告的权限。 若要了解更多信息，请参阅[查看 Defender for Office 365 报告需要哪些权限？。](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

若要查看或访问"最近威胁管理警报"小部件，您必须具有查看警报的权限。 若要了解更多信息，请参阅查看警报所需的 [RBAC 权限](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。

## <a name="related-topics"></a>相关主题

[查看安全与合规中心内的电子邮件安全报告](view-email-security-reports.md)

[查看 Microsoft Defender for Office 365 报告](view-reports-for-atp.md)

[Defender for Office 365](office-365-atp.md)

[Office 365 威胁调查和响应](office-365-ti.md)
