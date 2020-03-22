---
title: 垃圾邮件可信度
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 管理员可以了解垃圾邮件可信度（SCL）如何确定邮件是垃圾邮件的可能性和可能性，以及垃圾邮件筛选对基于 SCL 的邮件所采取的默认操作。
ms.openlocfilehash: b8f194f9aecc31896fb816433e71d1b26de708f7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893690"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Office 365 中的垃圾邮件可信度（SCL）

当 Office 365 （Exchange Online 或独立 Exchange Online Protection （EOP），而不是 Exchange Online 邮箱）收到入站电子邮件时，邮件将通过垃圾邮件筛选，并为其分配一个垃圾邮件分数。 该分数映射到在 X 标头中添加到邮件的单个垃圾邮件可信度（SCL）。 SCL 较高表示邮件更有可能是垃圾邮件。 该服务将根据 SCL 对邮件采取操作。

下表描述了 SCL 的含义以及对邮件所执行的默认操作。 有关可以对基于垃圾邮件筛选判定的邮件执行的操作的详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

||||
|:---:|---|---|
|**SCL**|**定义**|**默认操作**|
|-1|邮件跳过垃圾邮件筛选。 例如，邮件来自安全发件人，发送到安全收件人，或者来自 IP 允许列表中的电子邮件源服务器。 有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。|将邮件传递到收件人的收件箱。|
|0, 1|垃圾邮件筛选已确定邮件不是垃圾邮件。|将邮件传递到收件人的收件箱。|
|5, 6|垃圾邮件筛选功能已将邮件标记为**垃圾**邮件|将邮件传递到收件人的垃圾邮件文件夹。|
|9 |垃圾邮件筛选功能已将邮件标记为**高可信度垃圾邮件**|将邮件传递到收件人的垃圾邮件文件夹。|
|

您会注意到，垃圾邮件筛选不会使用 SCL 2、3、4、7和8。

您可以使用邮件流规则（也称为传输规则）在邮件上标记 SCL。 如果使用邮件流规则设置 SCL，则值5或6将触发垃圾邮件的垃圾邮件筛选操作，值7、8或9将触发垃圾邮件筛选**操作，以**实现**高可信度垃圾邮件**。 有关详细信息，请参阅[使用邮件流规则在邮件中设置垃圾邮件可信度级别（SCL）](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

与 SCL 类似，批量投诉级别（BCL）标识错误的批量电子邮件（也称为_灰色邮件_）。 较高的 BCL 表明批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。 在反垃圾邮件策略中配置 BCL 阈值。 有关详细信息，请参阅[在 office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)、 [office 365 中的批量投诉级别（BCL）](bulk-complaint-level-values.md)，以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

||
|:-----|
|![LinkedIn Learning 短图标](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。|
