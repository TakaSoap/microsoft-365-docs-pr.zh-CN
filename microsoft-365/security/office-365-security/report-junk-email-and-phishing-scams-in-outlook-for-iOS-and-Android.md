---
title: 在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和钓鱼电子邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Outlook for iOS 和 Outlook for Android 中的内置垃圾邮件（非垃圾邮件）和网络钓鱼电子邮件报告选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166815"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="4de32-103">在 Exchange Online 中报告 Outlook for iOS 和 Outlook for Android 中的垃圾邮件和网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="4de32-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4de32-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="4de32-104">**Applies to**</span></span>
- [<span data-ttu-id="4de32-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4de32-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4de32-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4de32-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4de32-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4de32-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4de32-108">在使用混合新式身份验证的 Exchange Online 或本地邮箱的 Microsoft 365 组织中，可以使用 Outlook for iOS 和 Outlook for Android 中的内置报告选项向 Exchange Online Protection (EOP) 提交误报 (标记为垃圾邮件) 、漏报 (允许的) 错误电子邮件以及网络钓鱼邮件。 [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="4de32-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4de32-109">开始之前，您需要了解哪些信息</span><span class="sxs-lookup"><span data-stu-id="4de32-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="4de32-110">如果你是具有 Exchange Online 邮箱的组织的管理员，我们建议你使用安全与合规中心&门户。</span><span class="sxs-lookup"><span data-stu-id="4de32-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="4de32-111">有关详细信息，请参阅"使用管理员提交"将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="4de32-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="4de32-112">可以将报告的邮件配置为复制或重定向到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4de32-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="4de32-113">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="4de32-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="4de32-114">有关向 Microsoft 报告邮件详细信息，请参阅向 [Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="4de32-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="4de32-115">如果在用户提交策略中禁用了 Outlook 的垃圾邮件报告，垃圾邮件或网络钓鱼邮件将移动到"垃圾邮件"文件夹，并且不会报告给管理员或 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4de32-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="4de32-116">在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="4de32-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="4de32-117">对于收件箱中的邮件或其他任何电子邮件文件夹（垃圾邮件除外），请使用以下步骤报告 iOS 和 Android 的垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="4de32-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="4de32-118">选择一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="4de32-118">Select one or more messages.</span></span>
2. <span data-ttu-id="4de32-119">在右上角点击三个垂直点。</span><span class="sxs-lookup"><span data-stu-id="4de32-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="4de32-120">操作菜单将打开。</span><span class="sxs-lookup"><span data-stu-id="4de32-120">The action menu opens.</span></span>

   ![从操作菜单报告垃圾邮件或钓鱼电子邮件](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="4de32-122">点击 **"报告垃圾邮件**"，然后选择"**垃圾邮件**"或"**网络钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="4de32-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![报告垃圾邮件或钓鱼电子邮件](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="4de32-124">在出现的对话框中， **可以选择"报告** "或" **否"。谢谢**。</span><span class="sxs-lookup"><span data-stu-id="4de32-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="4de32-125">选择"**否"时**，如果点击"垃圾邮件"，邮件将移动到"垃圾邮件"文件夹，如果点击了网络钓鱼，邮件将移动到"已删除邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="4de32-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="4de32-126">Select **Report** to also send a copy of the message to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4de32-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![报告垃圾邮件或网络钓鱼电子邮件报告选项](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="4de32-128">如果改变主意，请在出现的 Toast 通知上选择"撤消"。 </span><span class="sxs-lookup"><span data-stu-id="4de32-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="4de32-129">邮件仍保留在收件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4de32-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="4de32-130">从 Outlook for iOS 和 Outlook for Android 中的"垃圾邮件"文件夹报告非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4de32-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="4de32-131">在"垃圾邮件"文件夹中，使用以下步骤报告垃圾邮件误报：</span><span class="sxs-lookup"><span data-stu-id="4de32-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="4de32-132">选择一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="4de32-132">Select one or more messages.</span></span>
2. <span data-ttu-id="4de32-133">在右上角点击三个垂直点。</span><span class="sxs-lookup"><span data-stu-id="4de32-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="4de32-134">操作菜单将打开。</span><span class="sxs-lookup"><span data-stu-id="4de32-134">The action menu opens.</span></span>

   ![从操作菜单中报告非垃圾邮件](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="4de32-136">点击 **"非垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="4de32-136">Tap **Not junk**.</span></span>

<span data-ttu-id="4de32-137">将显示一个 Toast 通知，表明电子邮件已移动到收件箱。</span><span class="sxs-lookup"><span data-stu-id="4de32-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="4de32-138">如果改变主意，请选择 **Toast** 通知上的"撤消"。</span><span class="sxs-lookup"><span data-stu-id="4de32-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="4de32-139">电子邮件仍保留在"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4de32-139">The email remains in the Junk folder.</span></span>
