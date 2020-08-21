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
description: 查找有关在 Exchange Online Protection 迁移过程中已排队、延迟或退回的邮件的常见问题 () 答。
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827745"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="0948d-103">EOP 排队、延迟以及退回邮件的常见问题</span><span class="sxs-lookup"><span data-stu-id="0948d-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="0948d-104">本主题回答了有关在 Exchange Online Protection 迁移过程中已排队、延迟或退回邮件 () 答。</span><span class="sxs-lookup"><span data-stu-id="0948d-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="0948d-105">为什么邮件队列？</span><span class="sxs-lookup"><span data-stu-id="0948d-105">Why is mail queuing?</span></span>

<span data-ttu-id="0948d-106">如果服务无法连接到用于传递的收件人服务器，则邮件将排入队列或延迟。</span><span class="sxs-lookup"><span data-stu-id="0948d-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="0948d-107">如果从收件人网络返回 500 系列错误，则不会延迟消息。</span><span class="sxs-lookup"><span data-stu-id="0948d-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="0948d-108">如何延迟邮件？</span><span class="sxs-lookup"><span data-stu-id="0948d-108">How does a message become deferred?</span></span>

<span data-ttu-id="0948d-109">当无法连接到收件人服务器且收件人的服务器返回"临时性故障"（如连接超时、拒绝连接或 400 系列错误）时，邮件将被保留。</span><span class="sxs-lookup"><span data-stu-id="0948d-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="0948d-110">如果存在永久性故障，如 500 系列错误，则消息将返回到发送方。</span><span class="sxs-lookup"><span data-stu-id="0948d-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="0948d-111">邮件保持延迟状态多长时间，什么是重试间隔？</span><span class="sxs-lookup"><span data-stu-id="0948d-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="0948d-112">延期的邮件将在我们的队列中保留 1 天。</span><span class="sxs-lookup"><span data-stu-id="0948d-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="0948d-113">重试发送邮件的依据为从收件人的邮件系统返回的错误。</span><span class="sxs-lookup"><span data-stu-id="0948d-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="0948d-114">前几个延迟要少于 15 分钟或更短，后续重试将 (在下一半部分中，或者) 在多次重试时缩小间隔的有效期为 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="0948d-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="0948d-115">时间间隔期扩展是动态的，将考虑多个变量，如队列大小和内部邮件优先级。</span><span class="sxs-lookup"><span data-stu-id="0948d-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="0948d-116">基本应用时，需要设置 15 分钟 (不好) 开始，然后在接下来的几个小时之间扩大到 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="0948d-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="0948d-117">还原电子邮件服务器后，如何分配排队邮件？</span><span class="sxs-lookup"><span data-stu-id="0948d-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="0948d-118">恢复电子邮件服务器后，所有排队的邮件将自动按服务器中断时接收和排队顺序进行处理。</span><span class="sxs-lookup"><span data-stu-id="0948d-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
