---
title: 在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 如果管理员为用户启用通知，则会收到一条通知消息，其中列出了发送到邮箱的邮件，并被标识为垃圾邮件、批量邮件或网络钓鱼邮件。 您可以在收到通知后释放或报告邮件。
ms.openlocfilehash: 4cf592f0aec948c3c8f6383cf288fb32ac644cd6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971360"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="d3515-104">在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="d3515-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="d3515-105">如果您的管理员为用户启用了垃圾邮件通知，您将收到一条通知消息，其中列出发往您的邮箱的邮件，而不是被标识为垃圾邮件和隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="d3515-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="d3515-106">如果你是管理员，并且想要启用此功能，则可以在[修改默认反垃圾邮件策略](configure-your-spam-filter-policies.md)时选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d3515-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d3515-107">您收到的邮件包括您拥有的垃圾邮件隔离邮件的数量，以及列表中最后一条消息的日期和时间（以通用协调时间或 UTC 为单位）。</span><span class="sxs-lookup"><span data-stu-id="d3515-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="d3515-108">此列表包含每个邮件的以下内容：</span><span class="sxs-lookup"><span data-stu-id="d3515-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="d3515-109">**发件人**隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d3515-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="d3515-110">**主题** 隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="d3515-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="d3515-111">**日期** 邮件隔离的日期和时间 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="d3515-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="d3515-112">以下是您可以使用隔离邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="d3515-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="d3515-113">如果希望 Office 365 将发件人添加到阻止发件人列表，请**阻止发件人**。</span><span class="sxs-lookup"><span data-stu-id="d3515-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="d3515-114">如果要执行其他操作，如预览或发布，请**查看**以导航到安全与合规中心内的隔离门户。</span><span class="sxs-lookup"><span data-stu-id="d3515-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="d3515-115">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="d3515-115">Be aware of the following:</span></span>

- <span data-ttu-id="d3515-116">由于与邮件流规则匹配而被隔离的邮件不会包括在用户隔离的邮件中。</span><span class="sxs-lookup"><span data-stu-id="d3515-116">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="d3515-117">只有垃圾邮件隔离邮件才会列出。</span><span class="sxs-lookup"><span data-stu-id="d3515-117">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="d3515-118">您可以释放邮件并将其报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="d3515-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
