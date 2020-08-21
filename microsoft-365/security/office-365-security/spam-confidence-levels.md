---
title: 垃圾邮件可信度
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解应用到 EOP (Exchange Online Protection) 的 SCL 证书中的垃圾邮件可 (信度) 。
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827393"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP 中适用的 (SCL) 可信度

在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，入站邮件通过 EOP 中的垃圾邮件筛选并分配有垃圾邮件得分。 该分数将被映射到添加到 X 标头 (邮件的单个垃圾邮件可) 信度 (SCL。 SCL 更高，表示邮件是垃圾邮件的可能性较大。 EOP 根据 SCL 对邮件执行操作。

下表描述了 SCL 意味及对邮件采取的默认操作。 有关可以基于垃圾邮件筛选谓词对邮件采取的操作的详细信息，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

****

|SCL|定义|默认操作|
|:---:|---|---|
|-1|邮件跳过了垃圾邮件筛选。 例如，该邮件来自安全发件人，或从 IP 允许列表上的电子邮件源服务器发送。 有关详细信息，请参阅"[在 EOP 中创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)|将邮件传递到收件人的收件箱。|
|0, 1|垃圾邮件筛选确定邮件不是垃圾邮件。|将邮件传递到收件人的收件箱。|
|5, 6|邮件被筛选标记为 **"垃圾邮件"**|将邮件传递到收件人的垃圾邮件文件夹。|
|9 |邮件被标记为" **高可信度垃圾邮件"的垃圾邮件筛选**|将邮件传递到收件人的垃圾邮件文件夹。|
|

您会注意到垃圾邮件筛选不会使用 SCL 2、3、4、7 和 8。

可以使用邮件流规则 (也称为用于标记邮件上) SCL 的传输规则。 如果你使用邮件流规则设置 SCL，则值 5 或 6 会触发垃圾邮件筛选 **操作对垃圾邮件**，值为 7、8 或 9 会触发"高可信度垃圾邮件" **的垃圾邮件筛选操作**。 有关详细信息，请参阅" [使用邮件流规则"在邮件中设置关于 SCL (的) 可信度](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

与 SCL 类似，批量公合级别 (BCL) 它标识了变成灰 (色邮件的邮件 _项目和格式_) 。 BCL 更高，则大量邮件更有可能生成电子邮件 (因此更可能是垃圾邮件) 。 配置反垃圾邮件策略中的 BCL 阈值。 有关详细信息，请参阅"[在 EOP 中配置反垃圾邮件策略"、批量](configure-your-spam-filter-policies.md)与会级[ (BCL) （EOP) ） 以及](bulk-complaint-level-values.md)垃圾邮件和批量邮件之间[有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)

|<!-- -->|
|---|
|![LinkedIn Learning New 到 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 简短图标？** 发现 LinkedIn Learning 向 **Microsoft 365 管理员**和 IT 专业人人提供的免费视频课程。|
