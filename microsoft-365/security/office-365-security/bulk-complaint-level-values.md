---
title: 批量投诉级别值、批量邮件发件、BCL 级别、BCL 的工作方式、bcl 评级、反垃圾邮件、反垃圾邮件标头、批量邮件筛选、停止批量邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 了解 Office 365 中的 "批量合规性级别（BCL）" 值。
ms.openlocfilehash: e45b08756dd528e56b24635d670ddcd05e4396e4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630631"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Office 365 中的大宗投诉级别（BCL）

批量收件人因其发送模式、内容创建和收件人获取实践而异。 有些是极大批量邮件程序，可向订阅者发送带有相关内容的所需邮件。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 来自批量邮件散播邮件的邮件称为 "批量邮件" 或 "灰色邮件"。

若要区分来自不同类型的批量发件人的邮件，批量邮件（Exchange Online 或独立 Exchange Online 保护（EOP），不包含 Exchange Online 邮箱）的入站邮件被分配了一个以 X 标头形式添加到邮件的批量投诉级别（BCL）。 BCL 类似于用于将邮件标识为垃圾邮件的[垃圾邮件信任级别（SCL）](spam-confidence-levels.md) 。 较高的 BCL 指示批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。 Microsoft 使用内部和第三方源来标识批量邮件，并确定相应的 BCL。

 垃圾邮件筛选将邮件标记为基于 BCL 阈值（默认值或指定值）的**批量电子邮件**，并对邮件执行指定的操作（默认操作是将邮件传递到收件人的 "垃圾邮件" 文件夹）。 有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)

下表描述了 BCL 阈值。

|||
|:---:|---|
|**BCL**|**说明**|
|0|邮件不是由批量发件人发送。|
|1, 2, 3|邮件来自于产生少量抱怨的批量发件人。|
|4, 5, 6, 7|邮件来自于产生各种各样的抱怨的批量发件人。|
|8, 9|邮件来自批量发件人，生成大量投诉。|
|
