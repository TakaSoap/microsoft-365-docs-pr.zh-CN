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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解应用于 EOP (中的) 邮件的垃圾邮件可信度Exchange Online Protection (SCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5a7bfd34fdb23b0bef94119f53adaa9ecc0c4a1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169391"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP 中的垃圾邮件 (SCL) 级别

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

在Microsoft 365没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中，入站邮件通过 EOP 中的垃圾邮件筛选，并分配有垃圾邮件得分。 该分数映射到添加到 X 标头中的 (SCL) 单个垃圾邮件可信度。 SCL 越高，邮件就越有可能是垃圾邮件。 EOP 根据 SCL 对邮件采取操作。

下表介绍了 SCL 的含义以及对邮件执行的默认操作。 有关可以基于垃圾邮件筛选裁定对邮件采取的操作详细信息，请参阅在 [EOP](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。

****

|SCL|定义|默认操作|
|:---:|---|---|
|-1|邮件跳过了垃圾邮件筛选。 例如，邮件来自安全发件人、发送给安全收件人或来自 IP 允许列表上的电子邮件源服务器。 有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。|将邮件传递到收件人的收件箱。|
|0, 1|垃圾邮件筛选确定邮件不是垃圾邮件。|将邮件传递到收件人的收件箱。|
|5, 6|垃圾邮件筛选将邮件标记为 **"垃圾邮件"**|将邮件传递到收件人的垃圾邮件文件夹。|
|9 |垃圾邮件筛选将邮件标记为 **高可信度垃圾邮件**|将邮件传递到收件人的垃圾邮件文件夹。|
|

你会注意到，垃圾邮件筛选不会使用 SCL 2、3、4、7 和 8。

您可以使用邮件流规则 (传输规则) 标记邮件上的 SCL。 如果使用邮件流规则设置 SCL，则值 5 或 6 将触发 **垃圾邮件** 的垃圾邮件筛选操作，值 7、8 或 9 将触发高可信度垃圾邮件的垃圾邮件筛选 **操作**。 有关详细信息，请参阅使用 [邮件流规则设置](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)邮件中的 (SCL) 级别。

与 SCL 类似，批量投诉级别 BCL (BCL) 识别错误批量 (也称为灰色 _邮件) 。_ BCL 越高，大量邮件产生投诉的可能性就越大（因此更有可能是垃圾邮件）。 您可以在反垃圾邮件策略中配置 BCL 阈值。 有关详细信息，请参阅在[EOP](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略[、EOP ](bulk-complaint-level-values.md)) 中的批量投诉级别 (BCL) 和垃圾邮件和批量电子邮件之间有什么[区别？。](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![LinkedIn Learning 快捷图标。](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **是新Microsoft 365？** 发现 LinkedIn **Microsoft 365** 为管理员和 IT 专业人员提供的免费视频Learning。
