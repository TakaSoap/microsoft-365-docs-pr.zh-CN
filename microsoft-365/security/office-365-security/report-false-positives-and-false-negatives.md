---
title: 在 Outlook 中报告误报和漏报
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 了解如何使用"报告邮件"功能在Outlook中报告误报和漏报。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e848595035501f5da7b6099efd2700ebac6f17e3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291159"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="ef93a-103">在 Outlook 中报告误报和漏报</span><span class="sxs-lookup"><span data-stu-id="ef93a-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ef93a-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="ef93a-104">**Applies to**</span></span>
- [<span data-ttu-id="ef93a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ef93a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ef93a-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="ef93a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ef93a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef93a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="ef93a-108">如果你是拥有 Microsoft 365 邮箱Exchange Online组织的管理员，建议使用安全与合规中心中的&门户。</span><span class="sxs-lookup"><span data-stu-id="ef93a-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ef93a-109">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ef93a-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="ef93a-110">在 Microsoft 365 组织中，邮箱位于 Exchange Online 或本地邮箱使用混合新式身份验证，你可以提交误报 (被阻止或发送到垃圾邮件文件夹) 的误报 (以及传递到) 至 Exchange Online Protection (EOP) 的不需要的电子邮件或网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="ef93a-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ef93a-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="ef93a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ef93a-112">为了获得最佳用户提交体验，请使用报告邮件外接程序或报告网络钓鱼外接程序。</span><span class="sxs-lookup"><span data-stu-id="ef93a-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="ef93a-113">请注意，此外接程序适用于Outlook平台（Web、iOS、Android 和桌面版）中的加载项。</span><span class="sxs-lookup"><span data-stu-id="ef93a-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="ef93a-114">如果你是拥有多个邮箱Exchange Online管理员，请使用安全与合规&门户。</span><span class="sxs-lookup"><span data-stu-id="ef93a-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ef93a-115">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ef93a-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="ef93a-116">您可以配置为直接向 Microsoft 和/或您指定的邮箱发送邮件。</span><span class="sxs-lookup"><span data-stu-id="ef93a-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="ef93a-117">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="ef93a-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="ef93a-118">若要详细了解如何获取和启用报告邮件或报告钓鱼加载项，请参阅启用报告邮件或报告钓鱼 [加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="ef93a-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="ef93a-119">有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="ef93a-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="ef93a-120">使用"报告邮件"功能</span><span class="sxs-lookup"><span data-stu-id="ef93a-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="ef93a-121">报告垃圾邮件和钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="ef93a-121">Report junk and phishing messages</span></span>

<span data-ttu-id="ef93a-122">对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下方法报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="ef93a-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="ef93a-123">单击 **选定邮件** 右上角的"更多操作"省略号，从下拉菜单中单击"报告邮件"，然后选择"**垃圾邮件**"或"网络钓鱼 **"。**</span><span class="sxs-lookup"><span data-stu-id="ef93a-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef93a-124">![报告邮件 - 更多操作](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="ef93a-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef93a-125">![报告邮件 - 垃圾邮件和网络钓鱼](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="ef93a-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="ef93a-126">选定的邮件将发送给 Microsoft 进行分析，并：</span><span class="sxs-lookup"><span data-stu-id="ef93a-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="ef93a-127">如果报告为垃圾邮件，则移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef93a-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="ef93a-128">如果报告为网络钓鱼，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="ef93a-128">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="ef93a-129">报告非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="ef93a-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="ef93a-130">单击 **选定邮件** 右上角的"更多操作"省略号，单击下拉菜单中的"报告邮件"，然后单击"非 **垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="ef93a-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef93a-131">![报告邮件 - 更多操作](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="ef93a-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef93a-132">![报告邮件 - 非垃圾邮件](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="ef93a-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="ef93a-133">选定的邮件将被发送到 Microsoft 进行分析，并移动到收件箱或其他任何指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ef93a-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="ef93a-134">查看和查看报告的邮件</span><span class="sxs-lookup"><span data-stu-id="ef93a-134">View and review reported messages</span></span>

<span data-ttu-id="ef93a-135">若要查看用户报告给 Microsoft 的邮件，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="ef93a-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="ef93a-136">使用管理员提交门户。</span><span class="sxs-lookup"><span data-stu-id="ef93a-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="ef93a-137">有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="ef93a-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="ef93a-138">创建邮件流规则 (也称为传输规则) 传输规则，以发送报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="ef93a-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="ef93a-139">有关说明，请参阅 [使用邮件流规则查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="ef93a-139">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>