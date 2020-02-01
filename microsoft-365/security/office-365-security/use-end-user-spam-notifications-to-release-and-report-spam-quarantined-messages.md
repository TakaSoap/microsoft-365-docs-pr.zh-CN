---
title: 使用最终用户垃圾邮件通知释放和报告垃圾邮件隔离邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: '查看有关隔离电子邮件的管理员的最终用户垃圾邮件通知消息的用户可以对邮件执行以下操作。 '
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598079"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="161fc-103">使用最终用户垃圾邮件通知释放和报告垃圾邮件隔离邮件</span><span class="sxs-lookup"><span data-stu-id="161fc-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="161fc-p101">如果管理员启用最终用户垃圾邮件通知，您将收到一封通知邮件，其中将列出原本计划发送到您的邮箱但已被标识为垃圾邮件且被隔离的邮件。此邮件包括列出的垃圾邮件隔离邮件的数量，以及列表中最后一封邮件的日期和时间（用协调世界时 (UTC) 表示）。您可从此列表中查看有关每封邮件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="161fc-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="161fc-107">**发件人**：隔离邮件的发件人姓名和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="161fc-107">**Sender**: The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="161fc-108">**Subject**：隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="161fc-108">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="161fc-109">**日期**：邮件被隔离的日期和时间（以 UTC 为单位）。</span><span class="sxs-lookup"><span data-stu-id="161fc-109">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="161fc-110">**大小**：隔离邮件的大小，以千字节（kb）为单位。</span><span class="sxs-lookup"><span data-stu-id="161fc-110">**Size**: The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="161fc-111">您可以对每封邮件执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="161fc-111">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="161fc-112">**释放到收件箱**：单击此链接可将邮件发送到您的收件箱，您可以在其中查看邮件。</span><span class="sxs-lookup"><span data-stu-id="161fc-112">**Release to Inbox**: Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="161fc-113">**报告为非垃圾**邮件：单击此链接会将一份邮件副本发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="161fc-113">**Report as Not Junk**: Clicking this link sends a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="161fc-114">垃圾邮件团队将评估和分析邮件，同时依照分析结果，调整反垃圾邮件筛选器规则以允许传输邮件。</span><span class="sxs-lookup"><span data-stu-id="161fc-114">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="161fc-115">由于邮件流规则（也称为 a）匹配而被隔离的邮件不包含在最终用户垃圾邮件隔离邮件中。</span><span class="sxs-lookup"><span data-stu-id="161fc-115">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="161fc-116">只有垃圾邮件隔离邮件才会列出。</span><span class="sxs-lookup"><span data-stu-id="161fc-116">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="161fc-117">您可以释放邮件并将其报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="161fc-117">You can only release a message and report it as a false positive (not junk) once.</span></span>
