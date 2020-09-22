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
description: 管理员可以了解适用于 Exchange Online Protection (EOP) 中邮件的垃圾邮件可信度级别 (SCL) 。
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202229"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP 中的垃圾邮件可信度级别 (SCL) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，入站邮件通过 EOP 中的垃圾邮件筛选，并为其分配了一个垃圾邮件分数。 该分数映射到单个垃圾邮件可信度级别 (SCL) 添加到了 X 标头中的邮件。 SCL 较高表示邮件更有可能是垃圾邮件。 EOP 基于 SCL 对邮件采取操作。

下表描述了 SCL 的含义以及对邮件所执行的默认操作。 有关可以对基于垃圾邮件筛选判定的邮件执行的操作的详细信息，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

****

|SCL|定义|默认操作|
|:---:|---|---|
|-1|邮件跳过垃圾邮件筛选。 例如，邮件来自安全发件人，发送到安全收件人，或者来自 IP 允许列表中的电子邮件源服务器。 有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。|将邮件传递到收件人的收件箱。|
|0, 1|垃圾邮件筛选已确定邮件不是垃圾邮件。|将邮件传递到收件人的收件箱。|
|5, 6|垃圾邮件筛选功能已将邮件标记为**垃圾**邮件|将邮件传递到收件人的垃圾邮件文件夹。|
|9 |垃圾邮件筛选功能已将邮件标记为 **高可信度垃圾邮件**|将邮件传递到收件人的垃圾邮件文件夹。|
|

您会注意到，垃圾邮件筛选不会使用 SCL 2、3、4、7和8。

您可以使用邮件流规则 (也称为传输规则) 来标记邮件 SCL。 如果使用邮件流规则设置 SCL，则值5或6将触发垃圾邮件的垃圾邮件筛选操作，值7、8或9将触发垃圾邮件筛选 **操作，以**实现 **高可信度垃圾邮件**。 有关详细信息，请参阅 [使用邮件流规则设置邮件中 (SCL) 的垃圾邮件可信度级别](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

与 SCL 类似，批量投诉级别 (BCL) 标识错误的批量电子邮件 (也称为 _灰色邮件_) 。 BCL 越高，大量邮件产生投诉的可能性就越大（因此更有可能是垃圾邮件）。 在反垃圾邮件策略中配置 BCL 阈值。 有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)、 [批量投诉级别 (BCL) 在 EOP) ](bulk-complaint-level-values.md)中，以及 [垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

|<!-- -->|
|---|
|![LinkedIn 学习 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增版到 Microsoft 365**的简短图标？ 探索通过 LinkedIn 学习获取的适用于 **Microsoft 365 管理员和 IT 专业人员**的免费视频课程。|
