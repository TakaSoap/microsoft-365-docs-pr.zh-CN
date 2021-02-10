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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="34d5c-103">EOP 排队、延迟以及退回邮件的常见问题</span><span class="sxs-lookup"><span data-stu-id="34d5c-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34d5c-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="34d5c-104">**Applies to**</span></span>
- [<span data-ttu-id="34d5c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34d5c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="34d5c-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="34d5c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="34d5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34d5c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="34d5c-108">本主题解答了有关 Exchange Online Protection (EOP 筛选过程中已排队、延迟或退回) 的常见问题。</span><span class="sxs-lookup"><span data-stu-id="34d5c-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="34d5c-109">为什么邮件排队？</span><span class="sxs-lookup"><span data-stu-id="34d5c-109">Why is mail queuing?</span></span>

<span data-ttu-id="34d5c-110">如果服务无法连接到收件人服务器进行传递，则邮件将排队或延迟。</span><span class="sxs-lookup"><span data-stu-id="34d5c-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="34d5c-111">如果从收件人网络返回 500 系列错误，将不会延迟邮件。</span><span class="sxs-lookup"><span data-stu-id="34d5c-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="34d5c-112">邮件如何延迟？</span><span class="sxs-lookup"><span data-stu-id="34d5c-112">How does a message become deferred?</span></span>

<span data-ttu-id="34d5c-113">当无法连接到收件人服务器，并且收件人的服务器返回"临时故障"（如连接失败、连接被拒绝或 400 系列错误）时，邮件将被持有。</span><span class="sxs-lookup"><span data-stu-id="34d5c-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="34d5c-114">如果存在永久性故障（如 500 系列错误），则邮件将返回给发件人。</span><span class="sxs-lookup"><span data-stu-id="34d5c-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="34d5c-115">邮件在延迟中保留多久，重试间隔是多长？</span><span class="sxs-lookup"><span data-stu-id="34d5c-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="34d5c-116">延迟的邮件将在我们的队列中保留 1 天。</span><span class="sxs-lookup"><span data-stu-id="34d5c-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="34d5c-117">重试发送邮件的依据为从收件人的邮件系统返回的错误。</span><span class="sxs-lookup"><span data-stu-id="34d5c-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="34d5c-118">前几个延迟为 15 分钟或更短，后续重试时间 (大约六十) 将多次重试间隔增加至最长 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="34d5c-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="34d5c-119">时间间隔持续时间扩展是动态的，考虑队列大小和内部邮件优先级等多个变量。</span><span class="sxs-lookup"><span data-stu-id="34d5c-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="34d5c-120">一个基本的开始时间 (15 分钟) ，然后在这之后几个小时内从该开始扩展至 60 分钟（ 最大值）。</span><span class="sxs-lookup"><span data-stu-id="34d5c-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="34d5c-121">还原您的电子邮件服务器后，如何分配排队的邮件？</span><span class="sxs-lookup"><span data-stu-id="34d5c-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="34d5c-122">还原您的电子邮件服务器后，所有排队的邮件都会按照服务器不可用时接收和排队的顺序自动进行处理。</span><span class="sxs-lookup"><span data-stu-id="34d5c-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
