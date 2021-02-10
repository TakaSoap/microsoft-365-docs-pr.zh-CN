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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解应用于 Exchange Online Protection (EOP) 中的邮件的垃圾邮件可信度 (SCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167151"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP 中 SCL (垃圾邮件) 级别

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

在具有 Exchange Online 邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，入站邮件通过 EOP 中的垃圾邮件筛选，并分配有垃圾邮件得分。 该分数映射到添加到 X 标头 (SCL) 单个垃圾邮件可信度级别。 SCL 越高，表明邮件更有可能是垃圾邮件。 EOP 根据 SCL 对邮件采取操作。

下表介绍了 SCL 的含义以及对邮件执行的默认操作。 有关可以基于垃圾邮件筛选裁定对邮件采取的操作详细信息，请参阅"在 EOP 中配置[反垃圾邮件策略"。](configure-your-spam-filter-policies.md)

****

|SCL|定义|默认操作|
|:---:|---|---|
|-1|邮件跳过了垃圾邮件筛选。 例如，邮件来自安全发件人、发送给安全收件人或来自 IP 允许列表上的电子邮件源服务器。 有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。|将邮件传递到收件人的收件箱。|
|0, 1|垃圾邮件筛选确定邮件不是垃圾邮件。|将邮件传递到收件人的收件箱。|
|5, 6|将邮件标记为垃圾邮件的垃圾邮件 **筛选**|将邮件传递到收件人的垃圾邮件文件夹。|
|9 |将邮件标记为高可信度垃圾邮件 **的垃圾邮件筛选**|将邮件传递到收件人的垃圾邮件文件夹。|
|

你会注意到，垃圾邮件筛选不会使用 SCL 2、3、4、7 和 8。

您可以使用邮件流规则 (传输规则) 标记邮件上的 SCL。 如果使用邮件流规则设置 SCL，则值 5 或 6 会触发 **垃圾邮件** 的垃圾邮件筛选操作，值 7、8 或 9 会触发高可信度垃圾邮件的垃圾邮件筛选 **操作**。 有关详细信息，请参阅使用邮件流规则设置邮件中 [SCL (垃圾邮件) 可信度](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

与 SCL 类似，BCL (批量投诉级别) 识别错误批量 (也称为 _灰色_ 邮件) 。 BCL 越高，大量邮件产生投诉的可能性就越大（因此更有可能是垃圾邮件）。 您可以在反垃圾邮件策略中配置 BCL 阈值。 有关详细信息，请参阅在[EOP](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略、批量投诉级别[ (BCL) in EOP) ](bulk-complaint-level-values.md)以及垃圾邮件和批量电子邮件之间有什么[区别？。](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![Microsoft ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **365** LinkedIn Learning New 的简短图标？ 发现 LinkedIn Learning 为 **Microsoft 365** 管理员和 IT 专业人员提供的免费视频课程。
