---
title: 手动将邮件提交给 Microsoft 进行分析
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
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理员和最终用户可以了解如何将电子邮件（正确的邮件标记为损坏或坏邮件允许）进行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6973330c4504bd6478265205f60798b3b7c1875
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811034"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="96860-103">手动将邮件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="96860-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="96860-104">如果您是具有 Exchange Online 邮箱的组织中的管理员，我们建议您在安全 & 合规性中心中使用提交门户。</span><span class="sxs-lookup"><span data-stu-id="96860-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="96860-105">有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="96860-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="96860-106">如果组织中的用户在其收件箱中收到垃圾邮件（垃圾邮件）或网络钓鱼邮件，或者如果邮件被标记为垃圾邮件，则可能会令人沮丧。</span><span class="sxs-lookup"><span data-stu-id="96860-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="96860-107">我们不断调整垃圾邮件筛选器，使其更加准确。</span><span class="sxs-lookup"><span data-stu-id="96860-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="96860-108">您和您的用户可以通过将误报（好的电子邮件标记为 "坏"）、"漏报（允许错误邮件）" 和 "网络钓鱼邮件" 提交给 Microsoft 进行分析来帮助此过程。</span><span class="sxs-lookup"><span data-stu-id="96860-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="96860-109">由于我们收到的提交量很大，我们可能无法应答所有分析请求。</span><span class="sxs-lookup"><span data-stu-id="96860-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="96860-110">将漏报提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="96860-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="96860-111">Outlook 和 web 上的 Outlook （以前称为 Outlook Web App）中的用户可以使用 Microsoft Outlook 的报告消息外接程序，而不是使用以下过程来报告漏报。</span><span class="sxs-lookup"><span data-stu-id="96860-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="96860-112">有关如何安装和使用此工具的信息，请参阅[Enable The Report Message 外接程序](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="96860-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="96860-113">如果您收到一封邮件，该邮件将通过应标识为垃圾邮件或网络钓鱼的垃圾邮件筛选传递，则可以根据需要将邮件提交到 Microsoft 垃圾邮件分析和 Microsoft 仿冒分析团队。</span><span class="sxs-lookup"><span data-stu-id="96860-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="96860-114">分析师将检查邮件并将其添加到服务范围的筛选器中（如果它满足分类条件）。</span><span class="sxs-lookup"><span data-stu-id="96860-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="96860-115">使用以下收件人之一创建一个新的空白电子邮件：</span><span class="sxs-lookup"><span data-stu-id="96860-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="96860-116">**垃圾邮件**：`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="96860-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="96860-117">**网络钓鱼**：`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="96860-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="96860-118">将垃圾邮件或仿冒邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="96860-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="96860-119">这会将垃圾邮件或仿冒邮件保存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="96860-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="96860-120">请勿复制和粘贴邮件的内容或转发邮件（我们需要原始邮件，以便我们可以检查邮件头）。</span><span class="sxs-lookup"><span data-stu-id="96860-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="96860-121">您可以在新邮件中附加多封邮件。</span><span class="sxs-lookup"><span data-stu-id="96860-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="96860-122">确保所有邮件都属于同一类型： "仿冒欺诈邮件" 或 "垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="96860-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="96860-123">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="96860-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="96860-124">对于附加的邮件，请使用 .msg （默认 Outlook 格式）或 .eml （默认 Outlook 网页格式）格式。</span><span class="sxs-lookup"><span data-stu-id="96860-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="96860-125">完成后，请单击 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="96860-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="96860-126">管理员有几种不同的方法来阻止被 misidentified 为垃圾邮件的特定邮件。</span><span class="sxs-lookup"><span data-stu-id="96860-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="96860-127">有关详细信息，请参阅[在 EOP 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="96860-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="96860-128">向 Microsoft 提交误报</span><span class="sxs-lookup"><span data-stu-id="96860-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="96860-129">Outlook 和 Outlook 网页版中的用户可以使用 Microsoft Outlook 的报告消息外接程序，而不是使用以下过程报告误报。</span><span class="sxs-lookup"><span data-stu-id="96860-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="96860-130">有关如何安装和使用此工具的信息，请参阅[Enable The Report Message 外接程序](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="96860-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="96860-131">如果邮件被错误地标识为垃圾邮件，您可以将邮件提交给 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="96860-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="96860-132">分析师将评估邮件，并且（取决于分析结果）可以调整服务范围的筛选器以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="96860-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="96860-133">创建一个新的空白电子邮件， `not_junk@office365.microsoft.com` 作为收件人：</span><span class="sxs-lookup"><span data-stu-id="96860-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="96860-134">将 misidentified 邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="96860-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="96860-135">这会将 misidentified 邮件另存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="96860-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="96860-136">请勿复制和粘贴邮件的内容或转发邮件（我们需要原始邮件，以便我们可以检查邮件头）。</span><span class="sxs-lookup"><span data-stu-id="96860-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="96860-137">您可以在新邮件中附加多封邮件。</span><span class="sxs-lookup"><span data-stu-id="96860-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="96860-138">请确保所有邮件的类型都相同：网络钓鱼邮件或垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="96860-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="96860-139">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="96860-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="96860-140">对于附加的邮件，请使用 .msg （默认 Outlook 格式）或 .eml （默认 Outlook 网页格式）格式。</span><span class="sxs-lookup"><span data-stu-id="96860-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="96860-141">完成后，请单击 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="96860-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="96860-142">管理员有几种不同的方法允许特定邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="96860-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="96860-143">有关详细信息，请参阅[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="96860-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="96860-144">创建邮件流规则以接收报告给 Microsoft 的邮件副本</span><span class="sxs-lookup"><span data-stu-id="96860-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="96860-145">有关说明，请参阅[使用邮件流规则查看用户报告给 Microsoft 的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="96860-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
