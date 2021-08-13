---
title: 在 Outlook 中报告误报和漏报
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 了解如何使用"报告消息"功能在Outlook报告误报和漏报。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac0dbb205e6205a9c92cc56922b7399c6dd2c65cde276854b2901edf89b29503
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "56788288"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>在 Outlook 中报告误报和漏报

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 如果你是拥有邮箱的 Microsoft 365 组织的管理员Exchange Online，我们建议你使用 Microsoft 365 Defender 门户中的"提交"页面。  有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)

在 Microsoft 365 组织中，邮箱位于 Exchange Online 或本地邮箱使用混合新式身份验证，你可以提交误报 (被阻止或发送到垃圾邮件文件夹) 的误报 (以及传递到) 到 Exchange Online Protection (EOP) 的不需要的电子邮件或网络钓鱼。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 为了获得最佳用户提交体验，请使用报告邮件外接程序或报告网络钓鱼外接程序。

  > [!IMPORTANT]
  > 报告垃圾邮件或网络钓鱼的内置体验Outlook用户提交[策略](./user-submission.md)。 我们建议改为使用报告邮件外接程序或报告网络钓鱼外接程序。

- 报告邮件外接程序和 Report Phishing 外接程序适用于所有平台 Outlook、iOS、Android 和桌面 (Outlook 网页版) 。

- 如果你是具有邮箱的组织管理员，请使用 Exchange Online 门户中的提交Microsoft 365 Defender门户。 有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)

- 您可以配置为直接向 Microsoft 和/或您指定的邮箱发送邮件。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。

- 若要详细了解如何获取和启用报告邮件或报告钓鱼加载项，请参阅启用报告邮件或报告钓鱼 [加载项](enable-the-report-message-add-in.md)。

- 有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-report-message-feature"></a>使用"报告邮件"功能

### <a name="report-junk-and-phishing-messages"></a>报告垃圾邮件和钓鱼邮件

对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下方法报告垃圾邮件和网络钓鱼邮件：

1. 选择 **选定邮件** 右上角的"更多操作"省略号，从下拉菜单中选择"报告邮件"，然后选择"**垃圾邮件**"或"网络钓鱼 **"。**

   ![报告邮件 - 更多操作](../../media/report-message-more-actions.png)

   ![报告邮件 - 垃圾邮件和网络钓鱼](../../media/report-message-junk-phishing.png)

2. 选定的邮件将发送给 Microsoft 进行分析，并：
   - 如果报告为垃圾邮件，则移动到"垃圾邮件"文件夹。
   - 如果报告为网络钓鱼，则将其删除。

### <a name="report-messages-that-are-not-junk"></a>报告非垃圾邮件

1. 选择 **选定邮件** 右上角的"更多操作"省略号，从下拉菜单中选择"报告邮件"，然后选择"非 **垃圾邮件"。**

   ![报告邮件 - 更多操作](../../media/report-message-more-actions.png)

   ![报告邮件 - 非垃圾邮件](../../media/report-message-not-junk.png)

2. 选定的邮件将被发送到 Microsoft 进行分析，并移动到收件箱或其他任何指定的文件夹。

## <a name="view-and-review-reported-messages"></a>查看和查看报告的邮件

若要查看用户报告给 Microsoft 的邮件，可以使用以下选项：

- 使用 **应用门户** 中的Microsoft 365 Defender页面。 有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。
- 创建邮件流规则 (也称为传输规则) 传输规则，以发送报告的邮件的副本。 有关说明，请参阅 [使用邮件流规则查看向 Microsoft 报告的用户](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。
