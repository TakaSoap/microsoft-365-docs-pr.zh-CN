---
title: 向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理员可以了解向 Microsoft 报告好坏消息和文件以进行分析的不同方法。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c87938a8716da36f027300d685f0caedcf69660
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291123"
---
# <a name="report-messages-and-files-to-microsoft"></a>向 Microsoft 报告邮件和文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，用户和管理员都有几种不同的方法向 Microsoft 报告电子邮件和文件。

****

|方法|说明|
|---|---|
|[使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft](admin-submission.md)|对于拥有邮箱的组织中管理员Exchange Online报告 (在独立 EOP) 。|
|[启用报告邮件或报告钓鱼外接程序](enable-the-report-message-add-in.md)|适用于Outlook web Outlook上 (以前称为"Outlook Web App) "的 Outlook Web App) 。 <p> 根据你的订阅，用户通过外接程序报告的邮件可在管理员提交门户、自动调查和响应[](admin-submission.md) (AIR) [结果](air-view-investigation-results.md)、用户报告的邮件报告以及威胁资源管理器中[提供。](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report) <p> 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。
|[向报告误报和漏报Outlook](report-false-positives-and-false-negatives.md)|提交误报 (阻止或发送到垃圾邮件文件夹) 的误报 (以及使用"报告邮件"功能传递到收件箱) Exchange Online Protection (EOP) 的误报或钓鱼邮件。|
|[手动将邮件提交到 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|将附加邮件手动发送到特定 Microsoft 电子邮件地址，以发送垃圾邮件，而不是垃圾邮件和网络钓鱼。|
|[使用邮件流规则来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|了解如何创建邮件流规则 (也称为传输规则) 在用户向 Microsoft 报告邮件进行分析时通知您。|
|[将恶意软件和非恶意软件提交给 Microsoft 进行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全智能 网站提交附件和其他文件。|

如果垃圾邮件或网络钓鱼邮件被隔离而不是传递，则用户可以从安全与合规中心中的隔离门户& Microsoft。 有关详细信息，请参阅[Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)。

> [!NOTE]
> 提交到 Microsoft 的数据位于北美数据中心Office 365合规性边界。 数据由工程团队的分析师审阅，以帮助提高筛选器的有效性。
