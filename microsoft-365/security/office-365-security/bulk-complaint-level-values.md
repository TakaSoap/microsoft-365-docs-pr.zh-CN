---
title: 批量投诉级别值、批量邮件发件、BCL 级别、BCL 的工作方式、bcl 评级、反垃圾邮件、反垃圾邮件标头、批量邮件筛选、停止批量邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: 了解 Office 365 中的批量投诉级别（BCL）值。
ms.openlocfilehash: 6f9314a5b96dbd641e461dfb564ed8605372a949
ms.sourcegitcommit: b0396171d24c6298b809b43bb109d3afed4de5b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "37451094"
---
# <a name="bulk-complaint-level-values"></a>批量投诉级别值

批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。 一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。

为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。 BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。 BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。 Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。 有关此邮件头的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

由于分级为9的批量邮件可能会生成投诉，因此默认 BCL 为7。 这意味着将接受批量邮件，直到达到7和邮件的投诉级别之后才接受。 分级越低，接受的垃圾邮件越少。 如果你的用户是，并且他们的工作是对批量邮件敏感，并且你的 BCL 设置为4，则将不接受具有高于4的 BCL 的批量邮件。

通过按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的步骤操作，您可以使用 BCL 值设置您组织所需的批量筛选级别。

下表介绍当前正在使用的 BCL 值。

|||
|:-----|:-----|
|**BCL 值**|**说明**|
|0|邮件不是由批量发件人发送。|
|1, 2, 3|邮件来自于产生少量抱怨的批量发件人。|
|4, 5, 6, 7|邮件来自于产生各种各样的抱怨的批量发件人。|
|8, 9|邮件来自于产生大量抱怨的批量发件人。|
