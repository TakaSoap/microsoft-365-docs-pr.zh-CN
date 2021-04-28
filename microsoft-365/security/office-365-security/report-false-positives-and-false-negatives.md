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
description: 了解如何在 Outlook 中报告误报和漏报，以及如何启用"报告邮件"和"报告钓鱼邮件"加载项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065135"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="757ca-103">在 Outlook 中报告误报和漏报</span><span class="sxs-lookup"><span data-stu-id="757ca-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="757ca-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="757ca-104">**Applies to**</span></span>
- [<span data-ttu-id="757ca-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="757ca-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="757ca-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="757ca-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="757ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="757ca-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="757ca-108">如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议你使用安全与合规中心中的&门户。</span><span class="sxs-lookup"><span data-stu-id="757ca-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="757ca-109">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="757ca-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="757ca-110">在具有 Exchange Online 邮箱的 Microsoft 365 组织中或使用混合新式身份验证本地邮箱中，你可以向 Exchange Online Protection (EOP) 提交误报 (标记为垃圾邮件) 和误报 (错误电子邮件和网络钓鱼) 。</span><span class="sxs-lookup"><span data-stu-id="757ca-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="757ca-111">使用"报告邮件"功能之前要记住的一些内容</span><span class="sxs-lookup"><span data-stu-id="757ca-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="757ca-112">为了获得最佳用户提交体验，请使用报告邮件外接程序或报告网络钓鱼外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="757ca-113">请注意，此外接程序适用于所有平台（Web、iOS、Android 和桌面版）中的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="757ca-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="757ca-114">如果你是具有 Exchange Online 邮箱的组织管理员，请使用安全与合规中心中的&门户。</span><span class="sxs-lookup"><span data-stu-id="757ca-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="757ca-115">有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="757ca-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="757ca-116">您可以配置为直接向 Microsoft 和/或您指定的邮箱发送邮件。</span><span class="sxs-lookup"><span data-stu-id="757ca-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="757ca-117">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="757ca-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="757ca-118">有关向 Microsoft 报告邮件的信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="757ca-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="757ca-119">使用"报告邮件"功能</span><span class="sxs-lookup"><span data-stu-id="757ca-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="757ca-120">报告垃圾邮件和钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="757ca-120">Report junk and phishing messages</span></span>

<span data-ttu-id="757ca-121">对于收件箱或其他任何电子邮件文件夹中的邮件（垃圾邮件除外），请使用以下方法报告垃圾邮件和网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="757ca-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="757ca-122">单击 **选定邮件** 右上角的"更多操作"省略号，从下拉菜单中单击"报告邮件"，然后选择"**垃圾邮件**"或"网络钓鱼 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="757ca-123">![报告邮件 - 更多操作](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="757ca-124">![报告邮件 - 垃圾邮件和网络钓鱼](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="757ca-125">选定的邮件将发送给 Microsoft 进行分析，并：</span><span class="sxs-lookup"><span data-stu-id="757ca-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="757ca-126">如果报告为垃圾邮件，则移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="757ca-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="757ca-127">如果报告为网络钓鱼，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="757ca-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="757ca-128">报告非垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="757ca-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="757ca-129">单击 **选定邮件** 右上角的"更多操作"省略号，单击下拉菜单中的"报告邮件"，然后单击"非 **垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="757ca-130">![报告邮件 - 更多操作](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="757ca-131">![报告邮件 - 非垃圾邮件](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="757ca-132">选定的邮件将被发送到 Microsoft 进行分析，并移动到收件箱或其他任何指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="757ca-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="757ca-133">启用"报告邮件"和"报告网络钓鱼"外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="757ca-134">Outlook 和 Web 上的 Outlook 的"报告邮件"和"报告网络钓鱼"外接程序 (以前称为 Outlook Web App) ，使用户能够轻松地将误报 (良好电子邮件报告为错误) 或漏报 (允许) 向 Microsoft 及其关联公司报告错误电子邮件进行分析。</span><span class="sxs-lookup"><span data-stu-id="757ca-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="757ca-135">Microsoft 使用这些提交来提高电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="757ca-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="757ca-136">例如，假设用户正在使用报告网络钓鱼外接程序报告许多邮件。</span><span class="sxs-lookup"><span data-stu-id="757ca-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="757ca-137">此信息在安全仪表板和其他报告中显示。</span><span class="sxs-lookup"><span data-stu-id="757ca-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="757ca-138">组织的安全团队可以使用此信息指示可能需要更新反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="757ca-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="757ca-139">可以安装"报告邮件"或"报告钓鱼邮件"加载项。</span><span class="sxs-lookup"><span data-stu-id="757ca-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="757ca-140">如果希望用户同时报告垃圾邮件和网络钓鱼邮件，请在你的组织中部署报告邮件外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="757ca-141">有关详细信息，请参阅启用报告邮件外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="757ca-142">报告邮件外接程序提供报告垃圾邮件和网络钓鱼邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="757ca-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="757ca-143">管理员可以为组织启用"报告邮件"外接程序，并且各个用户可以自行安装它。</span><span class="sxs-lookup"><span data-stu-id="757ca-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="757ca-144">报告网络钓鱼外接程序提供仅报告网络钓鱼邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="757ca-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="757ca-145">管理员可以为组织启用报告网络钓鱼外接程序，并且单个用户可以自行安装它。</span><span class="sxs-lookup"><span data-stu-id="757ca-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="757ca-146">如果您是单个用户，您可以为自己启用这两个外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="757ca-147">f 你是全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，你可以为组织启用报告邮件外接程序和报告网络钓鱼外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="757ca-148">这两个加载项现在都可以通过集中 [部署获得](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="757ca-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="757ca-149">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="757ca-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="757ca-150">报告邮件外接程序和报告网络钓鱼外接程序适用于大多数 Microsoft 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="757ca-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="757ca-151">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="757ca-151">Outlook on the web</span></span>
  - <span data-ttu-id="757ca-152">Outlook 2013 SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="757ca-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="757ca-153">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="757ca-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="757ca-154">Microsoft 365 企业应用版中包含的 Outlook</span><span class="sxs-lookup"><span data-stu-id="757ca-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="757ca-155">适用于 iOS 和 Android 的 Outlook 应用</span><span class="sxs-lookup"><span data-stu-id="757ca-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="757ca-156">这两个加载项均不适用于本地 Exchange 组织的共享邮箱或邮箱。</span><span class="sxs-lookup"><span data-stu-id="757ca-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="757ca-157">现有的 Web 浏览器应同时使用报告邮件和报告钓鱼外接程序。但是，如果您注意到外接程序不可用或未正常工作，请尝试其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="757ca-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="757ca-158">对于组织安装，组织需要配置为使用 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="757ca-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="757ca-159">有关详细信息，请参阅确定加载项的集中部署 [是否适用于你的组织](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="757ca-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="757ca-160">管理员需为全局管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="757ca-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="757ca-161">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="757ca-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="757ca-162">获取报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="757ca-163">自己获取外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="757ca-164">转到 Microsoft AppSource ， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告消息"加载项。</span><span class="sxs-lookup"><span data-stu-id="757ca-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="757ca-165">若要直接转到"报告邮件"加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="757ca-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="757ca-166">单击 **"立即获取"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-166">Click **GET IT NOW**.</span></span>

   ![报告邮件 - 现在获取](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="757ca-168">在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="757ca-169">使用工作或学校帐户登录 (商业用途) Microsoft 帐户 (供个人) 。</span><span class="sxs-lookup"><span data-stu-id="757ca-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="757ca-170">安装并启用加载项后，你将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="757ca-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="757ca-171">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="757ca-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="757ca-172">![Outlook 的"报告邮件"加载项图标](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="757ca-173">在 Outlook 网页 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="757ca-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="757ca-174">![Outlook 网页报表邮件外接程序图标](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="757ca-175">获取组织的外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="757ca-176">外接程序可能需要 12 个小时才能显示在组织中。</span><span class="sxs-lookup"><span data-stu-id="757ca-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="757ca-177">在 Microsoft 365 管理中心中，转到 "设置" \> **"加载项"** 页面，位于 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="757ca-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="757ca-178">如果看不到"加载项 **"页面，** 请转到"集成应用"页面顶部的"设置 \>  \> ""集成应用""加载项 **"** 链接。</span><span class="sxs-lookup"><span data-stu-id="757ca-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="757ca-179">选择 **页面顶部的"** 部署外接程序"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理中心中的"服务和外接程序"页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="757ca-181">在出现的 **"部署新的外接程序"** 飞出中，查看信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="757ca-182">下一页上，单击 **从应用商店中选择**。</span><span class="sxs-lookup"><span data-stu-id="757ca-182">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的外接程序页面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="757ca-184">在出现的 **"选择外接程序"** 页中，单击"搜索"框中，输入"**报告** 邮件"，然后单击"**搜索搜索"** ![ 图标 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="757ca-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="757ca-185">在结果列表中，找到"**报告邮件**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![选择外接程序搜索结果](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="757ca-187">在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="757ca-188">在 **出现的"配置外接程序"** 页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="757ca-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="757ca-189">**已分配用户**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="757ca-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="757ca-190">**每个人都** (默认) </span><span class="sxs-lookup"><span data-stu-id="757ca-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="757ca-191">**特定用户/组**</span><span class="sxs-lookup"><span data-stu-id="757ca-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="757ca-192">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="757ca-192">**Just me**</span></span>

   - <span data-ttu-id="757ca-193">**部署方法**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="757ca-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="757ca-194">**修复 (默认) ：** 加载项会自动部署到指定用户，且无法删除。</span><span class="sxs-lookup"><span data-stu-id="757ca-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="757ca-195">**可用**：用户可以在"主页""获取加载项 \> **""管理员管理**" \> **中安装加载项**。</span><span class="sxs-lookup"><span data-stu-id="757ca-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="757ca-196">**可选**：外接程序将自动部署到指定用户，但他们可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="757ca-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![配置外接程序页面](../../media/configure-add-in.png)

   <span data-ttu-id="757ca-198">完成后，单击"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="757ca-199">在 **出现的"** 部署报告消息"页中，你将看到一个进度报告，然后确认外接程序已部署。</span><span class="sxs-lookup"><span data-stu-id="757ca-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="757ca-200">阅读信息后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-200">After you read the information, click **Next**.</span></span>

   !["部署报告消息"页](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="757ca-202">在出现的 **"宣布外接程序"** 页上，查看信息，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   !["宣布外接程序"页](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="757ca-204">查看或编辑报告邮件外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="757ca-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="757ca-205">在 Microsoft 365 管理中心中，转到 "设置" \> **"加载项"** 页面，位于 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="757ca-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="757ca-206">如果看不到"加载项 **"页面，** 请转到"集成应用"页面顶部的"设置 \>  \> ""集成应用""加载项 **"** 链接。</span><span class="sxs-lookup"><span data-stu-id="757ca-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![新的 Microsoft 365 Add-Ins中心中的"服务和服务"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="757ca-208">查找并选择 **"报告邮件** "外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="757ca-209">在出现的 **"编辑报告** 消息"飞出控件中，根据组织情况查看和编辑设置。</span><span class="sxs-lookup"><span data-stu-id="757ca-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="757ca-210">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="757ca-210">When you're finished, click **Save**.</span></span>

   ![报告邮件外接程序的设置](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="757ca-212">获取报告网络钓鱼外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="757ca-213">自己获取外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="757ca-214">转到 Microsoft AppSource， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告钓鱼"加载项。</span><span class="sxs-lookup"><span data-stu-id="757ca-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="757ca-215">单击 **"立即获取"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="757ca-216">在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="757ca-217">使用工作或学校帐户登录 (商业用途) Microsoft 帐户 (供个人) 。</span><span class="sxs-lookup"><span data-stu-id="757ca-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="757ca-218">安装并启用加载项后，你将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="757ca-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="757ca-219">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="757ca-219">In Outlook, the icon looks like this:</span></span>

  ![报告 Outlook 的网络钓鱼外接程序图标](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="757ca-221">在 Outlook 网页 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="757ca-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="757ca-222">![Outlook 网页报表 钓鱼加载项图标](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="757ca-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="757ca-223">获取组织的外接程序</span><span class="sxs-lookup"><span data-stu-id="757ca-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="757ca-224">外接程序可能需要 12 个小时才能显示在组织中。</span><span class="sxs-lookup"><span data-stu-id="757ca-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="757ca-225">在 Microsoft 365 管理中心中，转到 "设置" \> **"加载项"** 页面，位于 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="757ca-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="757ca-226">如果看不到"加载项 **"页面，** 请转到"集成应用"页面顶部的"设置 \>  \> ""集成应用""加载项 **"** 链接。</span><span class="sxs-lookup"><span data-stu-id="757ca-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="757ca-227">选择 **页面顶部的"** 部署外接程序"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理中心中的"服务和外接程序"页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="757ca-229">在出现的 **"部署新的外接程序"** 飞出中，查看信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="757ca-230">下一页上，单击 **从应用商店中选择**。</span><span class="sxs-lookup"><span data-stu-id="757ca-230">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的外接程序页面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="757ca-232">在出现的 **"选择外接程序"** 页中，单击"搜索"框中，输入"**报告网络钓鱼"，** 然后单击"**搜索搜索"** ![ 图标 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="757ca-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="757ca-233">在结果列表中，找到"**报告网络钓鱼"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="757ca-234">在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="757ca-235">在 **出现的"配置外接程序"** 页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="757ca-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="757ca-236">**已分配用户**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="757ca-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="757ca-237">**每个人都** (默认) </span><span class="sxs-lookup"><span data-stu-id="757ca-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="757ca-238">**特定用户/组**</span><span class="sxs-lookup"><span data-stu-id="757ca-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="757ca-239">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="757ca-239">**Just me**</span></span>

   - <span data-ttu-id="757ca-240">**部署方法**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="757ca-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="757ca-241">**修复 (默认) ：** 加载项会自动部署到指定用户，且无法删除。</span><span class="sxs-lookup"><span data-stu-id="757ca-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="757ca-242">**可用**：用户可以在"主页""获取加载项 \> **""管理员管理**" \> **中安装加载项**。</span><span class="sxs-lookup"><span data-stu-id="757ca-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="757ca-243">**可选**：外接程序将自动部署到指定用户，但他们可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="757ca-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="757ca-244">完成后，单击"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="757ca-245">在 **出现的"部署** 报告网络钓鱼"页中，你将看到一个进度报告，然后确认外接程序已部署。</span><span class="sxs-lookup"><span data-stu-id="757ca-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="757ca-246">阅读信息后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="757ca-247">在出现的 **"宣布外接程序"** 页上，查看信息，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="757ca-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="757ca-248">查看或编辑报告网络钓鱼外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="757ca-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="757ca-249">在 Microsoft 365 管理中心中，转到 "设置" \> **"加载项"** 页面，位于 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="757ca-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="757ca-250">如果看不到"加载项 **"页面，** 请转到"集成应用"页面顶部的"设置 \>  \> ""集成应用""加载项 **"** 链接。</span><span class="sxs-lookup"><span data-stu-id="757ca-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="757ca-251">查找并选择报告 **网络钓鱼** 外接程序。</span><span class="sxs-lookup"><span data-stu-id="757ca-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="757ca-252">在出现的 **"编辑报告** 钓鱼"飞出控件中，查看和编辑适合你的组织的设置。</span><span class="sxs-lookup"><span data-stu-id="757ca-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="757ca-253">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="757ca-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="757ca-254">查看和查看报告的邮件</span><span class="sxs-lookup"><span data-stu-id="757ca-254">View and review reported messages</span></span>

<span data-ttu-id="757ca-255">若要查看用户报告给 Microsoft 的邮件，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="757ca-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="757ca-256">使用管理员提交门户。</span><span class="sxs-lookup"><span data-stu-id="757ca-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="757ca-257">有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="757ca-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="757ca-258">创建邮件流规则 (也称为传输规则) 传输规则，以发送报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="757ca-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="757ca-259">有关说明，请参阅 [使用邮件流规则查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="757ca-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>