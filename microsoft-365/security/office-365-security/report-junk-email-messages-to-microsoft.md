---
title: 向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理员可以了解向 Microsoft 报告好坏消息和文件以进行分析的不同方法。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 28c8aceff04adbb6b733b31262686a31825e1a8f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211845"
---
# <a name="report-messages-and-files-to-microsoft"></a>向 Microsoft 报告邮件和文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，用户和管理员都有几种不同的方法向 Microsoft 报告电子邮件和文件。

<br>

****

|方法|说明|
|---|---|
|[使用提交门户将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft](admin-submission.md)|对于拥有邮箱的组织的管理员，Exchange Online报告 (在独立 EOP) 。|
|[启用报告邮件或举报网络钓鱼加载项](enable-the-report-message-add-in.md)|适用于Outlook Outlook 网页版 (以前称为"Outlook Web App) "的Outlook Web App) 。 <p> 根据你的订阅，用户通过外接程序报告的邮件可在管理员提交门户、自动调查和响应[](admin-submission.md) (AIR) [结果](air-view-investigation-results.md)、用户报告的邮件报告以及[资源管理器](threat-explorer-views.md#email--submissions)中提供。 [](view-email-security-reports.md#user-reported-messages-report) <p> 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。
|[在 Outlook 中报告误报和漏报](report-false-positives-and-false-negatives.md)|使用“报告邮件”功能向 Exchange Online Protection (EOP) 提交误报 (已阻止或发送到垃圾邮件文件夹的优质电子邮件) 和误报 (发送到收件箱的不需要的电子邮件或网络钓鱼)。|
|[手动将邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|手动将附加邮件发送到特定的 Microsoft 电子邮件地址，用于垃圾邮件，而不是垃圾邮件和网络钓鱼。|
|[使用邮件流规则查看用户向 Microsoft 报告的内容](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|了解如何创建邮件流规则 (也称为传输规则) 在用户向 Microsoft 报告邮件进行分析时通知您。|
|[将恶意软件和非恶意软件提交给 Microsoft 进行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全智能站点提交附件和其他文件。|
|

> [!NOTE]
> 提交到 Microsoft 的数据位于北美数据中心的 Office 365 合规性边界中。 工程团队的分析人员会审查这些数据，以帮助提高筛选器的有效性。 提交被视为有助于改进筛选器的反馈，并保留 30 天。 之后，它将被删除。
