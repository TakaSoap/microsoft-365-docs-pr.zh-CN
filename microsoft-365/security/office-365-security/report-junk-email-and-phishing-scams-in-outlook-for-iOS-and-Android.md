---
title: 报告 iOS 和 Android Outlook垃圾邮件和钓鱼电子邮件
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
description: 管理员可以了解适用于 iOS 和 Android 的 Outlook 中的内置垃圾邮件（非垃圾邮件）和网络钓鱼电子邮件报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2c95f7b32d0d395e164d218c994b1608d36018d5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203852"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>在 Exchange Online 中报告 Outlook for iOS 和 Android 中的垃圾邮件Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，如果邮箱位于 Exchange Online 或本地邮箱使用混合新式身份验证，可以将[](../../enterprise/hybrid-modern-auth-overview.md)误报 (标记为垃圾邮件) 、漏报 (允许的) 错误电子邮件以及网络钓鱼邮件提交到 Exchange Online Protection (EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始之前，您需要了解哪些信息

- 为了获得最佳用户提交体验，我们建议使用报告邮件和报告网络钓鱼外接程序。有关详细信息 [，请参阅启用报告邮件](./enable-the-report-message-add-in.md) 外接程序 [和启用报告](./enable-the-report-phish-add-in.md) 网络钓鱼外接程序。

- 如果你是拥有多个邮箱Exchange Online管理员，我们建议你使用安全与合规中心&提交门户。 有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。

- 有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

  > [!NOTE]
  > 如果在用户提交策略中Outlook垃圾邮件报告，垃圾邮件或网络钓鱼邮件将移动到"垃圾邮件"文件夹，并且不会报告给管理员或 Microsoft。