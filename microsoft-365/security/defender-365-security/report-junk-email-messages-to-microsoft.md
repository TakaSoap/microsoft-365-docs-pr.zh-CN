---
title: 向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055679"
---
# <a name="report-messages-and-files-to-microsoft"></a>向 Microsoft 报告邮件和文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，用户和管理员都有几种向 Microsoft 报告电子邮件和文件的不同方法。

****

|方法|说明|
|---|---|
|[使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft](admin-submission.md)|对于拥有 Exchange Online 邮箱的组织的管理员， (报告方法在独立 EOP) 。|
|[启用报告消息加载项](enable-the-report-message-add-in.md)|使用 Outlook 和 Outlook 网页 (以前称为 Outlook Web App) 。 <p> 根据你的订阅，用户通过外接程序报告的邮件可在管理员提交门户、自动调查和响应[](admin-submission.md) ([AIR) 结果](air-view-investigation-results.md)、用户报告的邮件报告以及威胁资源管理器中[](view-email-security-reports.md#user-reported-messages-report)[提供。](threat-explorer-views.md#email--submissions) <p> 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。
|[启用“报告网络钓鱼”加载项](enable-the-report-phish-add-in.md)|使用 Outlook 和 Outlook 网页 (以前称为 Outlook Web App) 。 <p> 根据你的订阅，用户通过外接程序报告的邮件可在管理员提交门户、自动调查和响应[](admin-submission.md) ([AIR) 结果](air-view-investigation-results.md)、用户报告的邮件报告以及威胁资源管理器中[](view-email-security-reports.md#user-reported-messages-report)[提供。](threat-explorer-views.md#email--submissions) <p> 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。|
|[安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序](junk-email-reporting-add-in-for-microsoft-outlook.md)|仅适用于 Outlook。|
|[报告 Outlook 网页中的垃圾邮件和钓鱼电子邮件](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|为具有 Exchange Online 邮箱的组织使用 Outlook 网页版中的内置功能 (独立 EOP) 。 <p> 用户报告的邮件在管理员 [提交门户中提供](admin-submission.md)。 <p> 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。|
|[报告 Outlook for iOS 和 Outlook for Android 中的垃圾邮件和钓鱼电子邮件](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|为具有 Exchange Online 邮箱的组织使用 Outlook for iOS 和 Outlook for Android 中的内置 (在独立 EOP) 。 <p> 用户报告的邮件在管理员 [提交门户中提供](admin-submission.md)。 <p> 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。|
|[手动将邮件提交到 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|将附加邮件手动发送到特定 Microsoft 电子邮件地址，以发送垃圾邮件，而不是垃圾邮件和网络钓鱼。|
|[使用邮件流规则来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|了解如何创建邮件流规则 (也称为传输规则) 在用户向 Microsoft 报告邮件进行分析时通知您。|
|[将恶意软件和非恶意软件提交给 Microsoft 进行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全智能网站提交附件和其他文件。|

如果垃圾邮件或网络钓鱼邮件被隔离而不是传递，则用户可以从安全与合规中心中的隔离门户& Microsoft。 有关详细信息，请参阅 [在 Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)中以用户模式查找并释放隔离邮件。

> [!NOTE]
> 提交到 Microsoft 的数据位于北美数据中心的 Office 365 合规性边界中。 数据由工程团队的分析师审阅，以帮助提高筛选器的有效性。
