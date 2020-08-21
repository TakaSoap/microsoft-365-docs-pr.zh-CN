---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理员和最终用户可了解如何通过电子邮件消息发送电子邮件， (邮件被标记为错误邮件或邮件，允许发送给) Microsoft 进行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f00f8399164a84d2cb9dae0c4c416b73dfb0dc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827805"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>手动将邮件提交给 Microsoft 进行分析

> [!NOTE]
> 如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议您使用安全与合规中心中的&提交门户。 有关详细信息，请参阅["使用管理员提交"将可取的垃圾邮件、网络钓鱼邮件、URL 和文件提交到 Microsoft。](admin-submission.md)

如果组织用户在其收件箱中 (收到垃圾邮件、) 垃圾邮件 (或网络钓鱼邮件，或者某个合法电子邮件被标记为垃圾邮件而使用户接收不到，将会感到不到的一种感到不到你的邮件会感到最为有趣。 我们正在不断对垃圾邮件筛选器进行调整，以进行更加准确。

你和你的用户可以通过以下方式来帮助此过程：将误报 (标记为错误) 、漏报邮件 (错误邮件至) Microsoft 进行分析。

> [!NOTE]
> 由于收到的大量提交，我们可能无法应答所有分析请求。

## <a name="submit-false-negatives-to-microsoft"></a>向 Microsoft 提交漏报

> [!TIP]
> Outlook 和 Web 上的 Outlook 网页版中的用户（以前称为 Outlook Web App) ） (中的用户可以使用 Microsoft Outlook 的报告邮件加载项，而不是使用以下过程报告误报。 有关如何安装和使用此工具的信息，请参阅 ["启用报告消息"加载项](enable-the-report-message-add-in.md)。

如果收到一封通过垃圾邮件筛选并且应被标识为垃圾邮件或网络钓鱼的邮件，您可以将邮件提交至 Microsoft 垃圾邮件分析和 Microsoft 网络钓鱼分析团队（如果适用）。 如果该信息符合分类条件，则该信息会检查该邮件，并将其添加到服务范围的筛选器。

1. 创建下列收件人之一的新的空白电子邮件：

   - **垃圾邮件**： `junk@office365.microsoft.com`

   - **网络钓鱼**： `phish@office365.microsoft.com`

2. 将垃圾邮件或网络钓鱼邮件拖放到新邮件中。 这会将垃圾邮件或网络钓鱼邮件保存为新邮件的附件。 请勿复制并粘贴邮件内容或转发邮件 (我们需要原始邮件，以便我们可以在标头标头) 。

   > [!NOTE]
   >
   > - 可在新邮件中附加多个邮件。 确保所有邮件都是同一类型：网络钓鱼邮件或垃圾邮件。
   >
   > - 保留新的邮件正文空白。
   >
   > - 使用 .msg (默认 Outlook 格式) 或 .eml (已附加邮件的 Web) 格式。

3. 完成后，请单击"发送 **"。**

> [!TIP]
> 管理员可通过几种不同的方法来阻止被错误识别为垃圾邮件的特定邮件。 有关详细信息，请参阅 [在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>向 Microsoft 提交误报

> [!TIP]
> Outlook 和 Web 上的 Outlook 中的用户可以使用 Microsoft Outlook 的报告邮件加载项，而不是使用以下过程报告误报。 有关如何安装和使用此工具的信息，请参阅 ["启用报告消息"加载项](enable-the-report-message-add-in.md)。

如果某个邮件被错误地标识为垃圾邮件，您可以将该邮件提交到 Microsoft 垃圾邮件分析团队。 分析者将对邮件进行评估，并将 (根据分析) 调整服务范围筛选器以允许发送邮件的身份验证结果而定。

1. 创建一个新的空白电子邮件， `not_junk@office365.microsoft.com` 将为收件人：

2. 将未识别的邮件拖放到新邮件中。 这会将未识别的邮件另存为新邮件中的附件。 请勿复制并粘贴邮件内容或转发邮件 (我们需要原始邮件，以便我们可以检查邮件头) 。

   > [!NOTE]
   >
   > - 可在新邮件中附加多个邮件。 确保所有邮件都是同一类型：网络钓鱼邮件或垃圾邮件。
   >
   > - 保留新的邮件正文空白。
   >
   > - 使用 .msg (默认 Outlook 格式) 或 .eml (已附加邮件的 Web) 格式。

3. 完成后，请单击"发送 **"。**

> [!TIP]
> 管理员有几种不同的方法来允许特定邮件跳过垃圾邮件筛选。 有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>创建邮件流规则，以接收报告给 Microsoft 的邮件副本

有关说明，请参阅 ["邮件流规则"来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
