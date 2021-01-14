---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: 管理员和最终用户可以了解如何通过电子邮件将 (标记为错误或错误的邮件，) Microsoft 进行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94747b1d0a1aef746a63abada977aa47270ae4e2
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865076"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>手动将邮件提交给 Microsoft 进行分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议你使用安全与合规中心&门户。 有关详细信息，请参阅"使用管理员提交"将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)

如果组织中的用户收到垃圾邮件或 (垃圾邮件) 或钓鱼邮件，或者他们因被标记为垃圾邮件而未收到合法电子邮件，则可能会感到沮丧。 我们会不断微调垃圾邮件筛选器，以更加准确。

你和用户可以通过向 Microsoft 提交误报 (标记为错误) 、漏报 (允许的) 和钓鱼邮件来帮助此过程。

> [!NOTE]
> 由于我们收到的提交量很高，我们可能无法回答所有分析请求。

## <a name="submit-false-negatives-to-microsoft"></a>向 Microsoft 提交漏报

> [!TIP]
> Outlook 和 Web 上的 Outlook (（以前称为 Outlook Web App) ）中的用户可以使用报告邮件外接程序或报告网络钓鱼外接程序，而不是使用以下过程报告漏报。 若要了解如何安装和使用这些工具，请参阅"启用报告邮件" [加载项和](enable-the-report-message-add-in.md) "启用报告钓鱼 ["加载项](enable-the-report-phish-add-in.md)。

如果您收到通过垃圾邮件筛选传递的邮件，该邮件应被标识为垃圾邮件或网络钓鱼，您可以视情况将邮件提交给 Microsoft 垃圾邮件分析团队和 Microsoft 网络钓鱼分析团队。 如果邮件符合分类条件，分析员将审阅邮件并将其添加到服务范围的筛选器。

1. 创建包含以下收件人之一的新空白电子邮件：

   - **垃圾邮件**： `junk@office365.microsoft.com`

   - **网络钓鱼**： `phish@office365.microsoft.com`

2. 将垃圾邮件或网络钓鱼邮件拖放到新邮件中。 这会将垃圾邮件或网络钓鱼邮件另存为新邮件中的附件。 请勿复制并粘贴邮件内容，或将邮件转发 (需要原始邮件，以便检查邮件头) 。

   > [!NOTE]
   >
   > - 可以在新邮件中附加多个邮件。 确保所有邮件类型相同：钓鱼邮件或垃圾邮件。
   >
   > - 保留新的邮件正文空白。
   >
   > - 将 .msg (默认 Outlook) 或 .eml (Web 上的默认 Outlook 格式) 附加邮件使用。

3. 完成后，单击"发送 **"。**

> [!TIP]
> 管理员有几种不同的方法来阻止被错误识别为垃圾邮件的特定邮件。 有关详细信息，请参阅 [在 EOP 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>向 Microsoft 提交误报

> [!TIP]
> Outlook 和 Web 上的 Outlook (（以前称为 Outlook Web App) ）中的用户可以使用报告邮件外接程序或报告网络钓鱼外接程序，而不是使用以下过程报告误报。 若要了解如何安装和使用这些工具，请参阅"启用报告邮件" [加载项和](enable-the-report-message-add-in.md) "启用报告钓鱼 ["加载项](enable-the-report-phish-add-in.md)。


如果邮件被错误地标识为垃圾邮件，可以将邮件提交给 Microsoft 垃圾邮件分析团队。 分析员将评估邮件， (根据分析结果) 可以调整服务范围的筛选器以允许邮件通过。

1. 创建一封作为收件人的新空白 `not_junk@office365.microsoft.com` 电子邮件：

2. 将错误标识的邮件拖放到新邮件中。 这会将错误标识的邮件另存为新邮件中的附件。 请勿复制并粘贴邮件内容，或将邮件转发 (需要原始邮件，以便检查邮件头) 。

   > [!NOTE]
   >
   > - 可以在新邮件中附加多个邮件。 确保所有邮件类型相同：钓鱼邮件或垃圾邮件。
   >
   > - 保留新的邮件正文空白。
   >
   > - 将 .msg (默认 Outlook) 或 .eml (Web 上的默认 Outlook 格式) 附加邮件使用。

3. 完成后，单击"发送 **"。**

> [!TIP]
> 管理员有几种不同的方式允许特定邮件跳过垃圾邮件筛选。 有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>从提交到 Microsoft 的数据存储在什么位置？

数据位于北美数据中心的 Office 365 合规性边界内。 数据由工程团队的分析师审阅，以帮助提高筛选器的有效性。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>创建邮件流规则以接收报告给 Microsoft 的邮件的副本

有关说明， [请参阅"使用邮件流规则"查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
