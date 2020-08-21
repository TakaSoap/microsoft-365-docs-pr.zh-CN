---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理员和最终用户可了解如何通过电子邮件消息发送电子邮件， (邮件被标记为错误邮件或邮件，允许发送给) Microsoft 进行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f00f8399164a84d2cb9dae0c4c416b73dfb0dc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827805"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="7f95a-103">手动将邮件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="7f95a-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="7f95a-104">如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议您使用安全与合规中心中的&提交门户。</span><span class="sxs-lookup"><span data-stu-id="7f95a-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7f95a-105">有关详细信息，请参阅["使用管理员提交"将可取的垃圾邮件、网络钓鱼邮件、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="7f95a-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="7f95a-106">如果组织用户在其收件箱中 (收到垃圾邮件、) 垃圾邮件 (或网络钓鱼邮件，或者某个合法电子邮件被标记为垃圾邮件而使用户接收不到，将会感到不到的一种感到不到你的邮件会感到最为有趣。</span><span class="sxs-lookup"><span data-stu-id="7f95a-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="7f95a-107">我们正在不断对垃圾邮件筛选器进行调整，以进行更加准确。</span><span class="sxs-lookup"><span data-stu-id="7f95a-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="7f95a-108">你和你的用户可以通过以下方式来帮助此过程：将误报 (标记为错误) 、漏报邮件 (错误邮件至) Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="7f95a-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="7f95a-109">由于收到的大量提交，我们可能无法应答所有分析请求。</span><span class="sxs-lookup"><span data-stu-id="7f95a-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="7f95a-110">向 Microsoft 提交漏报</span><span class="sxs-lookup"><span data-stu-id="7f95a-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="7f95a-111">Outlook 和 Web 上的 Outlook 网页版中的用户（以前称为 Outlook Web App) ） (中的用户可以使用 Microsoft Outlook 的报告邮件加载项，而不是使用以下过程报告误报。</span><span class="sxs-lookup"><span data-stu-id="7f95a-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="7f95a-112">有关如何安装和使用此工具的信息，请参阅 ["启用报告消息"加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="7f95a-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="7f95a-113">如果收到一封通过垃圾邮件筛选并且应被标识为垃圾邮件或网络钓鱼的邮件，您可以将邮件提交至 Microsoft 垃圾邮件分析和 Microsoft 网络钓鱼分析团队（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="7f95a-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="7f95a-114">如果该信息符合分类条件，则该信息会检查该邮件，并将其添加到服务范围的筛选器。</span><span class="sxs-lookup"><span data-stu-id="7f95a-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="7f95a-115">创建下列收件人之一的新的空白电子邮件：</span><span class="sxs-lookup"><span data-stu-id="7f95a-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="7f95a-116">**垃圾邮件**： `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="7f95a-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="7f95a-117">**网络钓鱼**： `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="7f95a-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="7f95a-118">将垃圾邮件或网络钓鱼邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="7f95a-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="7f95a-119">这会将垃圾邮件或网络钓鱼邮件保存为新邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="7f95a-120">请勿复制并粘贴邮件内容或转发邮件 (我们需要原始邮件，以便我们可以在标头标头) 。</span><span class="sxs-lookup"><span data-stu-id="7f95a-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="7f95a-121">可在新邮件中附加多个邮件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="7f95a-122">确保所有邮件都是同一类型：网络钓鱼邮件或垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="7f95a-123">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="7f95a-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="7f95a-124">使用 .msg (默认 Outlook 格式) 或 .eml (已附加邮件的 Web) 格式。</span><span class="sxs-lookup"><span data-stu-id="7f95a-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="7f95a-125">完成后，请单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f95a-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="7f95a-126">管理员可通过几种不同的方法来阻止被错误识别为垃圾邮件的特定邮件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="7f95a-127">有关详细信息，请参阅 [在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7f95a-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="7f95a-128">向 Microsoft 提交误报</span><span class="sxs-lookup"><span data-stu-id="7f95a-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="7f95a-129">Outlook 和 Web 上的 Outlook 中的用户可以使用 Microsoft Outlook 的报告邮件加载项，而不是使用以下过程报告误报。</span><span class="sxs-lookup"><span data-stu-id="7f95a-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="7f95a-130">有关如何安装和使用此工具的信息，请参阅 ["启用报告消息"加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="7f95a-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="7f95a-131">如果某个邮件被错误地标识为垃圾邮件，您可以将该邮件提交到 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="7f95a-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="7f95a-132">分析者将对邮件进行评估，并将 (根据分析) 调整服务范围筛选器以允许发送邮件的身份验证结果而定。</span><span class="sxs-lookup"><span data-stu-id="7f95a-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="7f95a-133">创建一个新的空白电子邮件， `not_junk@office365.microsoft.com` 将为收件人：</span><span class="sxs-lookup"><span data-stu-id="7f95a-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="7f95a-134">将未识别的邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="7f95a-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="7f95a-135">这会将未识别的邮件另存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="7f95a-136">请勿复制并粘贴邮件内容或转发邮件 (我们需要原始邮件，以便我们可以检查邮件头) 。</span><span class="sxs-lookup"><span data-stu-id="7f95a-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="7f95a-137">可在新邮件中附加多个邮件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="7f95a-138">确保所有邮件都是同一类型：网络钓鱼邮件或垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="7f95a-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="7f95a-139">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="7f95a-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="7f95a-140">使用 .msg (默认 Outlook 格式) 或 .eml (已附加邮件的 Web) 格式。</span><span class="sxs-lookup"><span data-stu-id="7f95a-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="7f95a-141">完成后，请单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="7f95a-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="7f95a-142">管理员有几种不同的方法来允许特定邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="7f95a-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="7f95a-143">有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7f95a-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="7f95a-144">创建邮件流规则，以接收报告给 Microsoft 的邮件副本</span><span class="sxs-lookup"><span data-stu-id="7f95a-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="7f95a-145">有关说明，请参阅 ["邮件流规则"来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7f95a-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
