---
title: 电子邮件主题Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 执行电子邮件Advanced eDiscovery分析时，电子邮件线程分析电子邮件会话，将每封邮件分为不同的类别。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 788858d6acaccbe07f3190b5adaaa05fe95c33a5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159786"
---
# <a name="email-threading-in-advanced-ediscovery"></a>电子邮件主题Advanced eDiscovery

请考虑一个已进行一段时间的电子邮件对话。 在大多数情况下，电子邮件线程中的最后一封邮件将包含上述所有邮件的内容。 因此，查看最后一条消息将给出线程中发生的对话的完整上下文。 电子邮件线程可标识此类邮件，以便审阅者可以在不丢失任何上下文的情况下查看已收集文档的一小部分。

## <a name="what-does-email-threading-do"></a>电子邮件线程处理有什么功能？

电子邮件线程分析每个电子邮件线程，并解析为单个邮件。 每个电子邮件线程都是单个邮件链。 Advanced eDiscovery审阅集内的所有电子邮件信息，以确定电子邮件是否具有唯一内容，或者电子邮件线索中的 (父邮件) 是否完全包含在最终邮件中。 电子邮件分为四个包含值：

- **非** 独占 *：非* 独占电子邮件是电子邮件线程中的最终电子邮件，包含该电子邮件线程之前的所有内容。

- **非独占减**：电子邮件被指定为非独占邮件 *，* 如果有一个或多个附件与电子邮件线程中的特定邮件相关联。 审阅者可以使用非独占减号值来确定线程中的哪些特定电子邮件具有关联的附件。 

- **非独占副本**：如果电子邮件是非独占邮件或非独占邮件的确切副本，则视为包含邮件副本。 

- **None：None** 值表示邮件的内容完全包含在至少一封标记为非独占或非独占邮件的其他电子邮件中。 

## <a name="how-is-it-different-from-conversations-in-outlook"></a>与会议对话之间Outlook？

一目了然，这看起来与邮件中的对话分组Outlook。 但是，有一些重要的区别。 考虑一个分叉为两个对话的电子邮件对话;例如，有人回复了对话中不是最新的电子邮件，因此对话中的最后两封电子邮件都有独特的内容。

Outlook仍将电子邮件分组到单个对话中;仅阅读最后一封电子邮件意味着缺少第二个到最后一封电子邮件的上下文，该上下文还包含独特的内容。 由于电子邮件线程将每封电子邮件解析为各个组件并进行比较，因此电子邮件线程会将最后两封电子邮件标记为包含两个，从而确保只要阅读标记为包含邮件的所有电子邮件，就不会错过任何上下文。
