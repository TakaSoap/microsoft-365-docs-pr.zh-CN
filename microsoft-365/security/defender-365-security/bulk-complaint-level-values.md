---
title: 批量投诉级别值
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online Protection (EOP) 中使用的批量合规性级别 (BCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055753"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP 中的批量 (BCL) 级别

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 向来自批量邮件发送的入站邮件分配批量兼容级别 (BCL) 。 BCL 添加到邮件的 X 标头中，类似于垃圾邮件可信度 ([SCL ](spam-confidence-levels.md)) 用于将邮件标识为垃圾邮件。 BCL 越高，表明批量邮件在邮件中 (产生投诉的可能性更大，因此更可能是垃圾邮件) 。 Microsoft 使用内部源和第三方源来标识批量邮件并确定相应的 BCL。

群发邮件程序在发送模式、内容创建和收件人获取做法方面有所不同。 良好的批量邮件发送器会向订阅者发送包含相关内容的所需邮件。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 来自批量邮件的邮件称为"批量邮件"或"灰色邮件"。

 垃圾邮件筛选根据 BCL 阈值将邮件标记为"批量电子邮件" (默认值或您指定的) 并针对邮件执行指定操作 (默认操作是将邮件发送到收件人的"垃圾邮件"文件夹) 。  有关详细信息，请参阅 [配置反垃圾邮件策略和](configure-your-spam-filter-policies.md) 垃圾邮件和批量电子邮件 [之间有什么区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)

下表介绍了 BCL 阈值。

****

|BCL|说明|
|:---:|---|
|0|邮件不是由批量发件人发送。|
|1, 2, 3|邮件来自于产生少量抱怨的批量发件人。|
|4, 5, 6, 7<sup>\*</sup>|邮件来自于产生各种各样的抱怨的批量发件人。|
|8, 9|邮件来自生成大量投诉的批量发件人。|
|

<sup>\*</sup> 这是反垃圾邮件策略中使用的默认阈值。
