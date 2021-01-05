---
title: 手动将邮件提交给 Microsoft 进行分析
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: 管理员和最终用户可以了解如何通过电子邮件将 (标记为错误或错误的邮件，) Microsoft 进行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe8e3c5ed44c7578764ed0bf19408f4db16e3740
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751555"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="392c8-103">手动将邮件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="392c8-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="392c8-104">如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议你使用安全与合规中心&门户。</span><span class="sxs-lookup"><span data-stu-id="392c8-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="392c8-105">有关详细信息，请参阅使用管理员提交将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交给 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="392c8-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="392c8-106">如果组织中的用户收到垃圾邮件或 (垃圾邮件) 或钓鱼邮件，或者他们因被标记为垃圾邮件而未收到合法电子邮件，则可能会感到沮丧。</span><span class="sxs-lookup"><span data-stu-id="392c8-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="392c8-107">我们会不断微调垃圾邮件筛选器，以更加准确。</span><span class="sxs-lookup"><span data-stu-id="392c8-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="392c8-108">你和用户可以通过向 Microsoft 提交误报 (标记为错误) 、漏报 () 错误邮件和钓鱼邮件来帮助此过程。</span><span class="sxs-lookup"><span data-stu-id="392c8-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="392c8-109">由于我们收到的提交量很高，我们可能无法回答所有分析请求。</span><span class="sxs-lookup"><span data-stu-id="392c8-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="392c8-110">向 Microsoft 提交漏报</span><span class="sxs-lookup"><span data-stu-id="392c8-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="392c8-111">Outlook 和 Outlook 网页 (以前称为 Outlook Web App) 的用户可以使用 Microsoft Outlook 报告邮件外接程序，而不是使用以下过程报告漏报。</span><span class="sxs-lookup"><span data-stu-id="392c8-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="392c8-112">若要了解如何安装和使用此工具，请参阅" [启用报告消息"加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="392c8-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="392c8-113">如果您收到通过垃圾邮件筛选传递的邮件，该邮件应被标识为垃圾邮件或网络钓鱼，您可以视情况将邮件提交给 Microsoft 垃圾邮件分析团队和 Microsoft 网络钓鱼分析团队。</span><span class="sxs-lookup"><span data-stu-id="392c8-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="392c8-114">如果邮件符合分类条件，分析员将审阅邮件并将其添加到服务范围的筛选器。</span><span class="sxs-lookup"><span data-stu-id="392c8-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="392c8-115">创建包含以下收件人之一的新空白电子邮件：</span><span class="sxs-lookup"><span data-stu-id="392c8-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="392c8-116">**垃圾邮件**： `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="392c8-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="392c8-117">**网络钓鱼**： `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="392c8-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="392c8-118">将垃圾邮件或网络钓鱼邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="392c8-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="392c8-119">这会将垃圾邮件或网络钓鱼邮件另存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="392c8-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="392c8-120">请勿复制并粘贴邮件内容，或将邮件转发 (需要原始邮件，以便检查邮件头) 。</span><span class="sxs-lookup"><span data-stu-id="392c8-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="392c8-121">可以在新邮件中附加多个邮件。</span><span class="sxs-lookup"><span data-stu-id="392c8-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="392c8-122">确保所有邮件类型相同：钓鱼邮件或垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="392c8-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="392c8-123">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="392c8-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="392c8-124">使用 .msg (outlook 格式) 或 .eml (附加邮件的默认 Outlook 网页) 格式。</span><span class="sxs-lookup"><span data-stu-id="392c8-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="392c8-125">完成后，单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="392c8-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="392c8-126">管理员有几种不同的方法来阻止被错误识别为垃圾邮件的特定邮件。</span><span class="sxs-lookup"><span data-stu-id="392c8-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="392c8-127">有关详细信息，请参阅 [在 EOP 中创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="392c8-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="392c8-128">向 Microsoft 提交误报</span><span class="sxs-lookup"><span data-stu-id="392c8-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="392c8-129">Outlook 和 Outlook 网页中的用户可以使用适用于 Microsoft Outlook 的报告邮件外接程序，而不是使用以下过程报告误报。</span><span class="sxs-lookup"><span data-stu-id="392c8-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="392c8-130">若要了解如何安装和使用此工具，请参阅" [启用报告消息"加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="392c8-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="392c8-131">如果邮件被错误地标识为垃圾邮件，可以将邮件提交给 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="392c8-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="392c8-132">分析员将评估邮件， (根据分析结果) 可以调整服务范围的筛选器以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="392c8-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="392c8-133">创建一封作为收件人的新空白 `not_junk@office365.microsoft.com` 电子邮件：</span><span class="sxs-lookup"><span data-stu-id="392c8-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="392c8-134">将错误标识的邮件拖放到新邮件中。</span><span class="sxs-lookup"><span data-stu-id="392c8-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="392c8-135">这会将错误标识的邮件另存为新邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="392c8-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="392c8-136">请勿复制并粘贴邮件内容，或将邮件转发 (需要原始邮件，以便检查邮件头) 。</span><span class="sxs-lookup"><span data-stu-id="392c8-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="392c8-137">可以在新邮件中附加多个邮件。</span><span class="sxs-lookup"><span data-stu-id="392c8-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="392c8-138">确保所有邮件类型相同：钓鱼邮件或垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="392c8-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="392c8-139">保留新的邮件正文空白。</span><span class="sxs-lookup"><span data-stu-id="392c8-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="392c8-140">使用 .msg (outlook 格式) 或 .eml (附加邮件的默认 Outlook 网页) 格式。</span><span class="sxs-lookup"><span data-stu-id="392c8-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="392c8-141">完成后，单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="392c8-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="392c8-142">管理员有几种不同的方式允许特定邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="392c8-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="392c8-143">有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="392c8-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="392c8-144">从提交到 Microsoft 的数据存储在何处？</span><span class="sxs-lookup"><span data-stu-id="392c8-144">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="392c8-145">数据位于北美数据中心的 Office 365 合规性边界内。</span><span class="sxs-lookup"><span data-stu-id="392c8-145">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="392c8-146">数据由工程团队的分析师审阅，以帮助提高筛选器的有效性。</span><span class="sxs-lookup"><span data-stu-id="392c8-146">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="392c8-147">创建邮件流规则以接收报告给 Microsoft 的邮件的副本</span><span class="sxs-lookup"><span data-stu-id="392c8-147">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="392c8-148">有关说明， [请参阅"使用邮件流规则"查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="392c8-148">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
