---
title: 在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和钓鱼电子邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Outlook for iOS 和 Outlook for Android 中的内置垃圾邮件（非垃圾邮件）和网络钓鱼电子邮件报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509322"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>在 Exchange Online 中的 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在使用混合新式身份验证的 Exchange Online 或本地邮箱的 Microsoft 365 组织中，可以将标记为垃圾邮件) 的误报 (良好电子邮件、 (错误电子邮件允许的) 和网络钓鱼邮件提交到 Exchange Online Protection (EOP) 。 [](../../enterprise/hybrid-modern-auth-overview.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始之前，你需要了解哪些信息

- 为了获得最佳用户提交体验，我们建议使用报告邮件和报告网络钓鱼外接程序。[有关详细信息，请参阅"启用报告邮件外接程序"和](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)["](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in)启用报告网络钓鱼外接程序"。

- 如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议您使用安全与合规中心&门户。 有关详细信息，请参阅使用管理员提交将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅 [用户提交策略](user-submission.md)。

- 有关向 Microsoft 报告邮件详细信息，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > 如果在用户提交策略中禁用 Outlook 的垃圾邮件报告，垃圾邮件或网络钓鱼邮件将移动到"垃圾邮件"文件夹，并且不会报告给管理员或 Microsoft。
