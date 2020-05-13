---
title: 批量投诉级别值
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online Protection （EOP）中使用的批量合规性级别（BCL）值。
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209603"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP 中的大宗投诉级别（BCL）

在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中具有邮箱的 Microsoft 365 组织中，EOP 会从批量邮件发件人向入站邮件分配一个批量合规性级别（BCL）。 将 BCL 添加到邮件的 X 标头中，类似于用于将邮件标识为垃圾邮件的[垃圾邮件可信度（SCL）](spam-confidence-levels.md) 。 较高的 BCL 指示批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。 Microsoft 使用内部和第三方源来标识批量邮件，并确定相应的 BCL。

批量收件人因其发送模式、内容创建和收件人获取实践而异。 正常批量邮件发送将包含相关内容的邮件发送到订阅者。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 来自批量邮件散播邮件的邮件称为 "批量邮件" 或 "灰色邮件"。

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
