---
title: 批量合成级别值
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理员可以了解在通过 EOP 管理 (Exchange Online Protection) 中所使用的值，以便 (合规性) 。
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827429"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>在 EOP 中为深 (使用 BCL) 批量校准

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 将批量兼容级别 (BCL) 分配给来自批量邮件群发程序的入站邮件。 BCL 在 X 标头中的邮件的添加位置，它类似于用来将邮件标识为垃圾邮件的垃圾邮件可 [) 信度 (SCL ](spam-confidence-levels.md) 文件。 BCL 更高，则批量邮件更有可能生成 (因此更有可能是垃圾邮件) 。 Microsoft 使用内部和第三方来源识别批量邮件，并确定适当的 BCL。

批量邮件处理器因其发送模式、内容创建以及收件人获取做法的不同而不同。 良好的批量邮件人员向其订阅者发送所需的包含相关内容的邮件。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 来自批量邮件程序的邮件为批量邮件或灰色邮件。

 垃圾邮件筛选根据 BCL**Bulk email**阈值 (将邮件标记为"批量邮件"。默认值或指定) 值，对邮件 (默认操作将邮件传递到收件人的垃圾邮件文件夹) 。 有关详细信息，请参阅["配置反垃圾邮件"策略](configure-your-spam-filter-policies.md)[和垃圾邮件和批量邮件之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)

下表描述了 BCL 阈值。

****

|BCL|说明|
|:---:|---|
|0|邮件不是由批量发件人发送。|
|1, 2, 3|邮件来自于产生少量抱怨的批量发件人。|
|4, 5, 6, 7|邮件来自于产生各种各样的抱怨的批量发件人。|
|8, 9|邮件来自于产生大量的诉率的批量发件人。|
|
