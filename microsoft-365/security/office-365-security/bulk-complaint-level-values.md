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
description: 管理员可以了解 Exchange Online Protection (EOP) 中使用的 BCL (BCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165963"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP 中的批量 (BCL) 级别

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

在 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 将批量兼容级别 (BCL) 分配给来自批量邮件的入站邮件。 BCL 将添加到 X 标头中的邮件中，类似于垃圾邮件可信度 [ (SCL ](spam-confidence-levels.md)) 用于将邮件标识为垃圾邮件。 BCL 越高，表明批量邮件 (产生投诉，因此更有可能是垃圾邮件) 。 Microsoft 使用内部源和第三方源来标识批量邮件并确定相应的 BCL。

批量邮件发送程序在发送模式、内容创建和收件人获取做法方面有所不同。 良好的批量邮件发送器会向订阅者发送包含相关内容的所需邮件。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 来自批量邮件的邮件称为"批量邮件"或"灰色邮件"。

 垃圾邮件筛选根据 BCL 阈值 (默认值或指定) 的值将邮件标记为批量电子邮件，并针对邮件执行指定操作 (默认操作是将邮件发送到收件人的"垃圾邮件"文件夹) 。  有关详细信息，请参阅" [配置反垃圾邮件](configure-your-spam-filter-policies.md) 策略"以及垃圾邮件和批量电子邮件之间有什么 [区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)

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
