---
title: 将垃圾邮件、非垃圾邮件和网络钓鱼邮件报告给 Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理员可以了解将正常和错误消息报告给 Microsoft 的不同方法。
ms.openlocfilehash: 4578e3d29a89e94d23c04e4d80e45c79c18cfb85
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216871"
---
# <a name="report-messages-and-files-to-microsoft"></a>向 Microsoft 报告邮件和文件

Office 365 中的用户和管理员拥有 Exchange Online 中邮箱的组织，或独立 Exchange Online Protection （EOP）组织（没有 Exchange Online 邮箱）具有多种不同的方法来向 Microsoft 报告邮件和文件。

|||
|---|---|
|**方法**|**说明**|
|[使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft](admin-submission.md)|针对具有 Exchange Online 邮箱的组织中的管理员的推荐报告方法（在独立 EOP 中不可用）。|
|[在 Office 365 中启用报告邮件加载项](enable-the-report-message-add-in.md)|适用于 Outlook、Outlook for Mac 和 web 上的 Outlook （以前称为 Outlook Web App），也是推荐的外接程序。 <br/><br/> 根据你的订阅，在[自动调查和响应（空中）结果](air-view-investigation-results.md)、[用户报告的邮件报告](view-email-security-reports.md#user-reported-messages-report)和[威胁浏览器](threat-explorer-views.md#email--submissions)中，用户使用加载项报告的邮件将可用。|
|[在 Office 365 中安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序](junk-email-reporting-add-in-for-microsoft-outlook.md)|仅在 Outlook 中有效。|
|[在 Office 365 中的 Outlook 网页上报告垃圾邮件和网络钓鱼电子邮件](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|对于具有 Exchange Online 邮箱的组织，请在 web 上的 Outlook 中使用内置功能（在独立 EOP 中不可用）。|
|[手动将邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|手动将附加的邮件发送到垃圾邮件、非垃圾邮件和网络钓鱼的特定 Microsoft 电子邮件地址。 <br/><br/> 此外，还了解如何创建邮件流规则（也称为传输规则），以便在用户向这些报告电子邮件地址发送邮件时通知您。|
|[将恶意软件和非恶意软件提交给 Microsoft 进行分析](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|使用 Microsoft 安全智能网站提交附件和其他文件。|
|

如果已隔离垃圾邮件或网络钓鱼邮件，而不是进行传递，则用户可以从 Office 365 Security & 合规性中心中的隔离门户向 Microsoft 报告邮件。 有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。