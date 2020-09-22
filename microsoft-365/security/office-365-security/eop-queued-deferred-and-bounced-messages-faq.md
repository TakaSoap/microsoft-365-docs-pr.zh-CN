---
title: EOP 排队、延迟以及退回邮件的常见问题
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: 查找有关在 Exchange Online Protection (EOP) 筛选过程中已排队、延迟或退回邮件的常见问题的解答。
ms.openlocfilehash: 4ae38e871c0d6e4321bd7586c5cfd0bea3aeef81
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202935"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排队、延迟以及退回邮件的常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本主题提供有关在 Exchange Online Protection (EOP) 筛选过程中已排队、延迟或退回邮件的常见问题的解答。

## <a name="why-is-mail-queuing"></a>为什么是邮件队列？

如果服务无法连接到收件人服务器进行传递，则会对邮件进行排队或延迟。 如果从收件人网络返回500系列错误，它将不会延迟邮件。

## <a name="how-does-a-message-become-deferred"></a>邮件如何延迟？

当无法建立与收件人服务器的连接，并且收件人的服务器返回 "临时故障" （如连接超时、连接被拒绝或400系列错误）时，将保留邮件。 如果存在永久性故障（如 500-系列错误），则会将邮件返回给发件人。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>邮件保留延迟的时间和重试间隔是多少？

延迟中的邮件将保留在队列中一天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 前几个 deferrals 为15分钟或更短，随后的重试次数 (在接下来的6到6个或更大的时间) 将多次重试次数增加到最大的60分钟。 间隔持续时间扩展是动态的，其中考虑了多个变量（如队列大小和内部邮件优先级）。 在基本中，它是15分钟 (或更少的) 启动，然后在接下来的几小时内扩展到60分钟的最大值。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>您的电子邮件服务器还原后，队列中的邮件如何分发？

您的电子邮件服务器还原后，所有排队的邮件将按其接收时间顺序进行处理，并在服务器不可用时进行排队。
