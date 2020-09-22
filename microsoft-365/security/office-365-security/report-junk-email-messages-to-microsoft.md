---
title: 将垃圾邮件、非垃圾邮件和网络钓鱼邮件报告给 Microsoft
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
description: 管理员可以了解将正常和错误邮件和文件报告给 Microsoft 进行分析的不同方法。
ms.openlocfilehash: 040f998b09f280fc2b6bdfdac327313f9cc65c3c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203638"
---
# <a name="report-messages-and-files-to-microsoft"></a>向 Microsoft 报告邮件和文件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online 保护的邮箱的 Microsoft 365 组织中，用户和管理员都有几种不同的方法来向 Microsoft 报告电子邮件和文件 (EOP) 组织。

****

|方法|说明|
|---|---|
|[使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft](admin-submission.md)|使用 Exchange Online 邮箱的组织中的管理员的建议报告方法 (在独立 EOP) 中不可用。|
|[启用报告消息加载项](enable-the-report-message-add-in.md)|适用于 Outlook、Outlook for Mac 和 web 上的 Outlook (以前称为 Outlook Web App) ，并且是推荐的加载项。 <br/><br/> 根据你的订阅，在 [管理员提交门户](admin-submission.md)中可以使用加载项报告的用户的邮件、 [自动调查和响应 (空中) 结果](air-view-investigation-results.md)、 [用户报告的邮件报告](view-email-security-reports.md#user-reported-messages-report)和 [威胁浏览器](threat-explorer-views.md#email--submissions)。 <br/><br/> 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [在 EOP 中为用户提交垃圾邮件和网络钓鱼邮件指定邮箱](user-submission.md)。|
|[安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序](junk-email-reporting-add-in-for-microsoft-outlook.md)|仅在 Outlook 中有效。|
|[在 web 上的 Outlook 中报告垃圾邮件和网络钓鱼电子邮件](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|使用 Outlook 网页版中的内置功能，以便具有 Exchange Online 邮箱的组织 (在独立 EOP) 中不可用。 <br/><br/> 用户报告的邮件在 [管理提交门户](admin-submission.md)中可用。 <br/><br/> 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [在 Exchange online 中指定用户提交垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。|
|[在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼电子邮件](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|使用 Outlook for iOS 中的内置功能适用于具有 Exchange Online 邮箱的组织的 Android (在独立 EOP) 中不可用。 <br/><br/> 用户报告的邮件在 [管理提交门户](admin-submission.md)中可用。 <br/><br/> 您可以将报告的邮件配置为复制或重定向到您指定的邮箱。 有关详细信息，请参阅 [在 Exchange online 中指定用户提交垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。|
|[手动将邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|手动将附加的邮件发送到垃圾邮件、非垃圾邮件和网络钓鱼的特定 Microsoft 电子邮件地址。|
|[使用邮件流规则来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|了解如何创建邮件流规则 (也称为传输规则) ，当用户将邮件报告给 Microsoft 进行分析时，该规则会通知你。
|||
|[将恶意软件和非恶意软件提交给 Microsoft 进行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全智能网站提交附件和其他文件。|
|

如果已隔离垃圾邮件或网络钓鱼邮件，而不是进行传递，则用户可以在安全 & 合规性中心的隔离门户中将邮件报告给 Microsoft。 有关详细信息，请参阅 [在 Microsoft 365 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。
