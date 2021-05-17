---
title: 电子邮件主题中的Advanced eDiscovery
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
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285558"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="c9848-103">电子邮件主题中的Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c9848-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="c9848-104">请考虑一个已进行一段时间的电子邮件对话。</span><span class="sxs-lookup"><span data-stu-id="c9848-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="c9848-105">在大多数情况下，线程上的最后一封电子邮件将包括上述所有电子邮件的内容;查看最后的电子邮件将提供线程中发生的对话的完整上下文。</span><span class="sxs-lookup"><span data-stu-id="c9848-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="c9848-106">电子邮件线程标识此类电子邮件，以便审阅者可以在不丢失任何上下文的情况下查看已收集文档的一小部分。</span><span class="sxs-lookup"><span data-stu-id="c9848-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="c9848-107">电子邮件线程处理有什么功能？</span><span class="sxs-lookup"><span data-stu-id="c9848-107">What does email threading do?</span></span>

<span data-ttu-id="c9848-108">电子邮件线程分析每个电子邮件，并解析为单个邮件;每封电子邮件都是单个邮件链。</span><span class="sxs-lookup"><span data-stu-id="c9848-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="c9848-109">然后，它分析审阅集内的所有电子邮件，以确定电子邮件是否具有独特的内容，或者该链是否完全包含在不同的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="c9848-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="c9848-110">最终的电子邮件分为四类：</span><span class="sxs-lookup"><span data-stu-id="c9848-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="c9848-111">**包含**：电子邮件中的最后一封邮件具有唯一内容，并且电子邮件包含其他电子邮件中包含的所有附件，这些附件中的内容完全包含在此电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="c9848-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="c9848-112">**包含(-)**：电子邮件中的最后一封邮件具有唯一内容，但电子邮件不包含其他电子邮件中包含的某些附件，这些附件中的内容完全包含在此电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="c9848-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="c9848-113">**包含副本**：包含/包含(-)电子邮件的精确副本</span><span class="sxs-lookup"><span data-stu-id="c9848-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="c9848-114">**无**：此电子邮件的内容完全包含在至少一封标记为包含/包含(-)的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="c9848-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="c9848-115">与电子邮件中的对话Outlook？</span><span class="sxs-lookup"><span data-stu-id="c9848-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="c9848-116">一目了然，这看起来与邮件中的对话分组Outlook。</span><span class="sxs-lookup"><span data-stu-id="c9848-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="c9848-117">但是，有一些重要的区别。</span><span class="sxs-lookup"><span data-stu-id="c9848-117">However, there are some important distinctions.</span></span> <span data-ttu-id="c9848-118">考虑一个分叉为两个对话的电子邮件对话;例如，有人回复了对话中不是最新的电子邮件，因此对话中的最后两封电子邮件都有独特的内容。</span><span class="sxs-lookup"><span data-stu-id="c9848-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="c9848-119">Outlook仍将电子邮件分组到单个对话中;仅阅读最后一封电子邮件意味着缺少第二个到最后一封电子邮件的上下文，该上下文还包含独特的内容。</span><span class="sxs-lookup"><span data-stu-id="c9848-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="c9848-120">由于电子邮件线程将每封电子邮件解析为各个组件并进行比较，因此电子邮件线程会将最后两封电子邮件标记为包含两个，从而确保只要阅读标记为包含邮件的所有电子邮件，就不会错过任何上下文。</span><span class="sxs-lookup"><span data-stu-id="c9848-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
