---
title: EOP 排队、延迟以及退回邮件的常见问题
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: 查找有关 Exchange Online Protection （EOP）筛选过程中已排队、延迟或退回邮件的常见问题的解答。
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206588"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="5e576-103">EOP 排队、延迟以及退回邮件的常见问题</span><span class="sxs-lookup"><span data-stu-id="5e576-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="5e576-104">本主题提供有关在 Exchange Online Protection （EOP）筛选过程中已排队、延迟或退回邮件的常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="5e576-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="5e576-105">为什么是邮件队列？</span><span class="sxs-lookup"><span data-stu-id="5e576-105">Why is mail queuing?</span></span>

<span data-ttu-id="5e576-106">如果服务无法连接到收件人服务器进行传递，则会对邮件进行排队或延迟。</span><span class="sxs-lookup"><span data-stu-id="5e576-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="5e576-107">如果从收件人网络返回500系列错误，它将不会延迟邮件。</span><span class="sxs-lookup"><span data-stu-id="5e576-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="5e576-108">邮件如何延迟？</span><span class="sxs-lookup"><span data-stu-id="5e576-108">How does a message become deferred?</span></span>

<span data-ttu-id="5e576-109">当无法建立与收件人服务器的连接，并且收件人的服务器返回 "临时故障" （如连接超时、连接被拒绝或400系列错误）时，将保留邮件。</span><span class="sxs-lookup"><span data-stu-id="5e576-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="5e576-110">如果存在永久性故障（如 500-系列错误），则会将邮件返回给发件人。</span><span class="sxs-lookup"><span data-stu-id="5e576-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="5e576-111">邮件保留延迟的时间和重试间隔是多少？</span><span class="sxs-lookup"><span data-stu-id="5e576-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="5e576-112">延迟中的邮件将保留在队列中一天。</span><span class="sxs-lookup"><span data-stu-id="5e576-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="5e576-113">重试发送邮件的依据为从收件人的邮件系统返回的错误。</span><span class="sxs-lookup"><span data-stu-id="5e576-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="5e576-114">前几个 deferrals 为15分钟或更短，随后的重试次数（在接下来的6到6或更长时间）内，将多次重试次数增加到最大的60分钟。</span><span class="sxs-lookup"><span data-stu-id="5e576-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="5e576-115">间隔持续时间扩展是动态的，其中考虑了多个变量（如队列大小和内部邮件优先级）。</span><span class="sxs-lookup"><span data-stu-id="5e576-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="5e576-116">在基本版中，启动时间为15分钟（或更短），然后在接下来的几小时内扩展到60分钟的最大值。</span><span class="sxs-lookup"><span data-stu-id="5e576-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="5e576-117">您的电子邮件服务器还原后，队列中的邮件如何分发？</span><span class="sxs-lookup"><span data-stu-id="5e576-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="5e576-118">您的电子邮件服务器还原后，所有排队的邮件将按其接收时间顺序进行处理，并在服务器不可用时进行排队。</span><span class="sxs-lookup"><span data-stu-id="5e576-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
