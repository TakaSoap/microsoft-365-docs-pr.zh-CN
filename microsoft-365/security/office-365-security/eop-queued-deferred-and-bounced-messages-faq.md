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
description: 查找有关在 Exchange Online Protection (EOP 筛选过程中已排队、延迟或退回的邮件) 问题的答案。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 854e954e3ebb995ba23db2afc6f2ca9ab19de508
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165423"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排队、延迟以及退回邮件的常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

本主题解答了有关 Exchange Online Protection (EOP 筛选过程中已排队、延迟或退回) 的常见问题。

## <a name="why-is-mail-queuing"></a>为什么邮件排队？

如果服务无法连接到收件人服务器进行传递，则邮件将排队或延迟。 如果从收件人网络返回 500 系列错误，将不会延迟邮件。

## <a name="how-does-a-message-become-deferred"></a>邮件如何延迟？

当无法连接到收件人服务器，并且收件人的服务器返回"临时故障"（如连接失败、连接被拒绝或 400 系列错误）时，邮件将被持有。 如果存在永久性故障（如 500 系列错误），则邮件将返回给发件人。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>邮件在延迟中保留多久，重试间隔是多长？

延迟的邮件将在我们的队列中保留 1 天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 前几个延迟为 15 分钟或更短，后续重试时间 (大约六十) 将多次重试间隔增加至最长 60 分钟。 时间间隔持续时间扩展是动态的，考虑队列大小和内部邮件优先级等多个变量。 一个基本的开始时间 (15 分钟) ，然后在这之后几个小时内从该开始扩展至 60 分钟（ 最大值）。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>还原您的电子邮件服务器后，如何分配排队的邮件？

还原您的电子邮件服务器后，所有排队的邮件都会按照服务器不可用时接收和排队的顺序自动进行处理。
