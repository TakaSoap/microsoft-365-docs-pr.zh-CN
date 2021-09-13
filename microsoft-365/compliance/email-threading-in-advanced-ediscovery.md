---
title: 电子邮件线程处理Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 执行电子邮件Advanced eDiscovery分析时，电子邮件线程分析电子邮件会话，将每封邮件分为不同的类别。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59200569"
---
# <a name="email-threading-in-advanced-ediscovery"></a>电子邮件线程处理Advanced eDiscovery

请考虑一个已进行一段时间的电子邮件对话。 在大多数情况下，线程上的最后一封电子邮件将包括上述所有电子邮件的内容;查看最后的电子邮件将提供线程中发生的对话的完整上下文。 电子邮件线程标识此类电子邮件，以便审阅者可以在不丢失任何上下文的情况下查看已收集文档的一小部分。

## <a name="what-does-email-threading-do"></a>电子邮件线程处理有什么功能？

电子邮件线程分析每个电子邮件，并解析为单个邮件;每封电子邮件都是单个邮件链。 然后，它分析审阅集内的所有电子邮件，以确定电子邮件是否具有独特的内容，或者该链是否完全包含在不同的电子邮件中。 最终的电子邮件分为四类：

- **包含**：电子邮件中的最后一封邮件具有唯一内容，并且电子邮件包含其他电子邮件中包含的所有附件，这些附件中的内容完全包含在此电子邮件中。

- **包含(-)**：电子邮件中的最后一封邮件具有唯一内容，但电子邮件不包含其他电子邮件中包含的某些附件，这些附件中的内容完全包含在此电子邮件中。

- **包含副本**：包含/包含(-)电子邮件的精确副本

- **无**：此电子邮件的内容完全包含在至少一封标记为包含/包含(-)的电子邮件中。

## <a name="how-is-it-different-from-conversations-in-outlook"></a>与会议对话之间Outlook？

一目了然，这看起来与邮件中的对话分组Outlook。 但是，有一些重要的区别。 考虑一个分叉为两个对话的电子邮件对话;例如，有人回复了对话中不是最新的电子邮件，因此对话中的最后两封电子邮件都有独特的内容。

Outlook仍将电子邮件分组到单个对话中;仅阅读最后一封电子邮件意味着缺少第二个到最后一封电子邮件的上下文，该上下文还包含独特的内容。 由于电子邮件线程将每封电子邮件解析为各个组件并进行比较，因此电子邮件线程会将最后两封电子邮件标记为包含两个，从而确保只要阅读标记为包含邮件的所有电子邮件，就不会错过任何上下文。
