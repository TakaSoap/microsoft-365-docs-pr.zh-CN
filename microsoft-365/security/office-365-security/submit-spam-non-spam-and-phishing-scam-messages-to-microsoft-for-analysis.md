---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理员和最终用户可以了解如何通过电子邮件将 (标记为错误或错误的邮件，以便) Microsoft 进行分析。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 42c384966b5ba5b1f7e52e26212f60c446d9bc58
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180659"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>手动将邮件提交给 Microsoft 进行分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 如果你是拥有多个邮箱Exchange Online管理员，我们建议你使用"提交"页面，Microsoft 365 Defender门户。  有关详细信息，请参阅使用提交门户将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)

如果组织的用户在收件箱中收到垃圾邮件 (垃圾邮件) 或钓鱼邮件，或者他们因被标记为垃圾邮件而未收到合法电子邮件，可能很令人沮丧。 我们会不断微调垃圾邮件筛选器，以更加准确。

你和用户可以通过向 Microsoft 提交误报 (标记为错误) 、漏报 (允许的) 错误邮件和网络钓鱼邮件，来帮助此过程。

> [!NOTE]
> 由于我们收到的提交量很高，我们可能无法回答所有分析请求。

## <a name="submit-false-negatives-to-microsoft"></a>向 Microsoft 提交漏报

> [!TIP]
> Outlook 和 Outlook 网页版 (中以前称为 Outlook Web App) 的用户可以使用报告邮件外接程序或报告网络钓鱼外接程序，而不是使用以下过程报告漏报。 若要了解如何安装和使用这些工具，请参阅启用报告邮件加载项和[](enable-the-report-message-add-in.md)启用报告钓鱼[加载项](enable-the-report-phish-add-in.md)。

如果您收到通过垃圾邮件筛选且应被标识为垃圾邮件或网络钓鱼的邮件，您可以在适当时将邮件提交给 Microsoft 垃圾邮件分析团队和 Microsoft 网络钓鱼分析团队。 如果邮件符合分类条件，分析员将查看邮件并将其添加到服务范围的筛选器。

1. 创建具有以下收件人之一的新空白电子邮件：

   - **垃圾邮件**： `junk@office365.microsoft.com`
   - **网络钓鱼**： `phish@office365.microsoft.com`

2. 将垃圾邮件或网络钓鱼邮件拖放到新邮件中。 这会将垃圾邮件或网络钓鱼邮件另存为新邮件中的附件。 不要复制和粘贴邮件内容或转发邮件 (我们需要原始邮件，以便检查邮件头) 。

   > [!NOTE]
   >
   > - 可以在新邮件中附加多个邮件。 确保所有邮件类型相同：网络钓鱼邮件或垃圾邮件。
   > - 保留新的邮件正文空白。
   > - 使用 .msg (默认 Outlook 格式) 或 .eml (Outlook附加邮件的 Web) 格式的默认格式。

3. 完成后，单击"发送 **"。**

> [!TIP]
> 管理员有几种不同的方法来阻止被错误识别为垃圾邮件的特定邮件。 有关详细信息，请参阅 [在 EOP 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>向 Microsoft 提交误报

> [!TIP]
> Outlook 和 Outlook 网页版 中的用户可以使用报告邮件外接程序或报告网络钓鱼外接程序，而不是使用以下过程报告误报。 若要了解如何安装和使用这些工具，请参阅启用报告邮件加载项和[](enable-the-report-message-add-in.md)启用报告钓鱼[加载项](enable-the-report-phish-add-in.md)。

如果邮件被错误地标识为垃圾邮件，你可以将邮件提交给 Microsoft 垃圾邮件分析团队。 分析员将评估邮件， (根据分析结果) 可以调整服务范围的筛选器以允许邮件通过。

1. 创建一封作为收件人的新 `not_junk@office365.microsoft.com` 空白电子邮件。

2. 将错误标识的邮件拖放到新邮件中。 这会将错误标识的邮件另存为新邮件中的附件。 不要复制和粘贴邮件内容或转发邮件 (我们需要原始邮件，以便检查邮件头) 。

   > [!NOTE]
   >
   > - 可以在新邮件中附加多个邮件。 确保所有邮件类型相同：网络钓鱼邮件或垃圾邮件。
   > - 保留新的邮件正文空白。
   > - 使用 .msg (默认 Outlook 格式) 或 .eml (Outlook附加邮件的 Web) 格式的默认格式。

3. 完成后，单击"发送 **"。**

> [!TIP]
> 管理员通过几种不同的方式允许特定邮件跳过垃圾邮件筛选。 有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>从提交到 Microsoft 的数据存储在何处？

数据位于北美数据中心Office 365合规性边界。 工程团队的分析人员会审查这些数据，以帮助提高筛选器的有效性。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>创建邮件流规则以接收报告给 Microsoft 的邮件的副本

有关说明，请参阅 [使用邮件流规则查看向 Microsoft 报告的用户](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。
