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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: 查找有关 Exchange Online Protection 或 EOP 筛选过程中已排队、延迟或退回的邮件 (常见问题) 解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203888"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排队、延迟以及退回邮件的常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本主题解答了在 Exchange Online Protection (EOP 筛选过程中排队、延迟或退回) 的常见问题。

## <a name="why-is-mail-queuing"></a>为什么是邮件队列？

如果服务无法连接到收件人服务器进行传递，邮件将排队或延迟。 如果从收件人网络返回 500 系列错误，将不会延迟邮件。

## <a name="how-does-a-message-become-deferred"></a>邮件如何延迟？

当无法建立与收件人服务器的连接，并且收件人服务器返回"临时故障"（例如，连接失败、连接被拒绝或 400 系列错误）时，邮件将被持有。 如果永久失败（如 500 系列错误）将邮件返回给发件人。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>邮件保持延迟状态的时间以及重试间隔是什么？

延期的邮件将在我们的队列中保留 1 天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 前几个延迟为 15 分钟或更短，接下来的六十 (次重试数大约) 将多次重试间隔增加至最长 60 分钟。 考虑到队列大小和内部邮件优先级等多个变量，间隔持续时间扩展是动态的。 基本来说，需要 15 分钟 (或更少) 开始，然后在这几个小时内从该开始扩展到最大值 60 分钟。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>恢复您的电子邮件服务器后，如何分配排队的邮件？

还原您的电子邮件服务器后，所有排队的邮件都会按照服务器不可用时接收和排队的顺序自动进行处理。
