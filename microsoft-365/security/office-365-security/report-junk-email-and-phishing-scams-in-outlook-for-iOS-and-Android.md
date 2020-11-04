---
title: 在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼电子邮件
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Outlook for iOS 和 Outlook for Android 中内置的 "垃圾邮件"、"非垃圾邮件" 和 "仿冒电子邮件报告" 选项。
ms.openlocfilehash: 1c842ac5349f9c2804c637fa4c5598b06e8f489f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877287"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="aee54-103">在 Exchange Online 中的 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="aee54-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="aee54-104">在使用 [混合新式身份验证](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)的 Exchange Online 或本地邮箱中具有邮箱的 Microsoft 365 组织中，您可以使用 Outlook for IOS 和 Outlook for Android 中的内置报告选项来提交误报 (良好的电子邮件，并将其标记为垃圾邮件) 、漏报 (错误的电子邮件) 并将网络钓鱼邮件发送到 Exchange Online PROTECTION (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="aee54-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aee54-105">在开始之前，您需要知道什么</span><span class="sxs-lookup"><span data-stu-id="aee54-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="aee54-106">如果您是具有 Exchange Online 邮箱的组织中的管理员，我们建议您在安全 & 合规性中心中使用提交门户。</span><span class="sxs-lookup"><span data-stu-id="aee54-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="aee54-107">有关详细信息，请参阅 [使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="aee54-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="aee54-108">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aee54-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="aee54-109">有关详细信息，请参阅 [用户提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="aee54-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="aee54-110">有关向 Microsoft 报告邮件的详细信息，请参阅 [将邮件和文件报告给 microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="aee54-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="aee54-111">如果在用户提交策略中禁用了 Outlook 的垃圾邮件报告功能，则垃圾邮件或仿冒邮件将移至 "垃圾邮件" 文件夹，而不会报告给您的管理员或 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="aee54-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="aee54-112">在 Outlook for iOS 和 Outlook for Android 中报告垃圾邮件和网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="aee54-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="aee54-113">对于收件箱中的邮件，或除垃圾邮件以外的任何其他电子邮件文件夹，请使用以下步骤报告 iOS 和 Android 的垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="aee54-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="aee54-114">选择一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="aee54-114">Select one or more messages.</span></span>
2. <span data-ttu-id="aee54-115">在右上角点击三个垂直点。</span><span class="sxs-lookup"><span data-stu-id="aee54-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="aee54-116">将打开 "操作" 菜单。</span><span class="sxs-lookup"><span data-stu-id="aee54-116">The action menu opens.</span></span>

   ![从 "操作" 菜单报告垃圾邮件或仿冒电子邮件](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="aee54-118">点击 " **报告垃圾邮件** "，然后选择 " **垃圾邮件** 或 **网络钓鱼** "。</span><span class="sxs-lookup"><span data-stu-id="aee54-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![报告垃圾邮件或网络钓鱼电子邮件](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="aee54-120">在出现的对话框中，可以选择 " **报告** " 或 " **无感谢** "。</span><span class="sxs-lookup"><span data-stu-id="aee54-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="aee54-121">如果选择 " **否** "，则如果你攻出了 **垃圾** 邮件，如果你点击了 "垃圾 **邮件" 文件夹** ，则会将邮件移动到 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="aee54-121">On selecting **No Thanks** , if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="aee54-122">选择 " **报告** "，同时将邮件的副本发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="aee54-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![报告垃圾邮件或网络钓鱼电子邮件报告选项](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="aee54-124">如果你改变主意，请在出现的 toast 通知中选择 " **撤消** "。</span><span class="sxs-lookup"><span data-stu-id="aee54-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="aee54-125">邮件将保留在 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="aee54-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="aee54-126">从 Outlook for iOS 和 Outlook for Android 中的 "垃圾邮件" 文件夹报告非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="aee54-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="aee54-127">在 "垃圾邮件" 文件夹中，使用以下步骤报告垃圾邮件误报：</span><span class="sxs-lookup"><span data-stu-id="aee54-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="aee54-128">选择一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="aee54-128">Select one or more messages.</span></span>
2. <span data-ttu-id="aee54-129">在右上角点击三个垂直点。</span><span class="sxs-lookup"><span data-stu-id="aee54-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="aee54-130">将打开 "操作" 菜单。</span><span class="sxs-lookup"><span data-stu-id="aee54-130">The action menu opens.</span></span>

   ![从 "操作" 菜单报告非垃圾邮件](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="aee54-132">点击 " **非垃圾邮件** "。</span><span class="sxs-lookup"><span data-stu-id="aee54-132">Tap **Not junk**.</span></span>

<span data-ttu-id="aee54-133">出现 toast 通知，表明电子邮件已移动到您的收件箱。</span><span class="sxs-lookup"><span data-stu-id="aee54-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="aee54-134">如果你改变主意，请在 toast 通知上选择 " **撤消** "。</span><span class="sxs-lookup"><span data-stu-id="aee54-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="aee54-135">电子邮件仍保留在 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="aee54-135">The email remains in the Junk folder.</span></span>
