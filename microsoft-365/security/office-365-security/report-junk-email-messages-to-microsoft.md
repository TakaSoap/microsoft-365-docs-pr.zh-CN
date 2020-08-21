---
title: 向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理员可以了解向 Microsoft 报告良好和不良消息与文件进行分析的不同方法。
ms.openlocfilehash: fabe28d084361041ae9e6a8d118dd8c43c2225f7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827637"
---
# <a name="report-messages-and-files-to-microsoft"></a>向 Microsoft 报告邮件和文件

在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，用户和管理员都有多种不同的方法向 Microsoft 报告电子邮件和文件。

****

|方法|说明|
|---|---|
|[使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft](admin-submission.md)|对于具有 Exchange Online 邮箱的组织中管理员，建议 (在独立 EOP 邮箱中不可用) 。|
|[启用报告消息加载项](enable-the-report-message-add-in.md)|适用于 Outlook、Outlook for Mac 和 Outlook 网页版 (（以前称为 Outlook Web App) 版本 Outlook Web App) ，这是推荐的外接程序。 <br/><br/> 根据您的订阅，用户报告的外接程序邮件位于[Admin Submissions 门户](admin-submission.md)、自动调查和[响应 (AIR) 结果、](air-view-investigation-results.md)[用户报告的消息报告](view-email-security-reports.md#user-reported-messages-report)和[威胁资源管理器中](threat-explorer-views.md#email--submissions)。 <br/><br/> 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [在 EOP 中指定提交用户收集垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。|
|[安装和使用 Microsoft Outlook 的垃圾邮件报告加载项](junk-email-reporting-add-in-for-microsoft-outlook.md)|仅适用于 Outlook。|
|[在 Outlook 网页版中报告垃圾和钓鱼电子邮件](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|对具有 Exchange Online 邮箱的组织使用 Outlook 网页版中的内置 (在独立 EOP) 。 <br/><br/> 用户可在管理提交门户 [中显示用户报告的邮件](admin-submission.md)。 <br/><br/> 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [指定一个邮箱以提交 Exchange Online 中垃圾邮件和网络钓鱼邮件](user-submission.md)。|
|[手动将邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|将附加的邮件手动发送到特定的 Microsoft 垃圾邮件地址，而不是垃圾邮件和网络钓鱼。|
|[使用邮件流规则来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|了解如何创建邮件流规则 (也称为传输规则，) 传输规则类型在用户向 Microsoft 报告邮件进行分析时会通知你。
|||
|[将恶意软件和非恶意软件提交给 Microsoft 分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全智能网站提交附件和其他文件。|
|

如果垃圾邮件或网络钓鱼邮件被隔离而不是传递，则用户可以从安全 & 合规中心的"隔离"门户将邮件报告给 Microsoft。 有关详细信息，请参阅 [在 Microsoft 365 中以用户身份查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。
