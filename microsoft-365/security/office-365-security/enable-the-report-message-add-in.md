---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或您的整个组织启用 Outlook 和 web 上的 outlook 和 Outlook 网页版报告消息外接程序。
ms.openlocfilehash: 94dbe7d9dcd5cf3dc8bd5874550880d813f879f5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086308"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="c6abf-103">启用报表消息加载项</span><span class="sxs-lookup"><span data-stu-id="c6abf-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="c6abf-104">Outlook 和 web 上的 Outlook 的报告邮件外接程序与[Outlook 垃圾邮件筛选器](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)并不完全相同，但这两者都可用于将电子邮件标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="c6abf-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="c6abf-105">不同之处在于，Outlook 和 web 上的 Outlook 的报告邮件外接程序会通知 Microsoft misclassified 电子邮件，而 Outlook 垃圾邮件筛选器用于组织用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c6abf-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="c6abf-106">概述</span><span class="sxs-lookup"><span data-stu-id="c6abf-106">Overview</span></span>

<span data-ttu-id="c6abf-107">Outlook 和 web 上的 Outlook 的报告邮件外接程序（以前称为 Outlook Web App）使用户能够轻松地向 Microsoft 及其子公司报告 misclassified 电子邮件（无论是安全还是恶意）。</span><span class="sxs-lookup"><span data-stu-id="c6abf-107">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="c6abf-108">Microsoft 使用这些提交改进电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="c6abf-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c6abf-109">此外，如果您的组织使用的是[Office 365 高级威胁防护计划 1](office-365-atp.md)或[计划 2](office-365-ti.md)，则报告消息外接程序会为您组织的安全团队提供可用于查看和更新安全策略的有用信息。</span><span class="sxs-lookup"><span data-stu-id="c6abf-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="c6abf-110">例如，假设有人将大量邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="c6abf-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="c6abf-111">[安全仪表板](security-dashboard.md)和其他报告中的此信息图面。</span><span class="sxs-lookup"><span data-stu-id="c6abf-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c6abf-112">组织的安全团队可以使用此信息指示可能需要更新的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="c6abf-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="c6abf-113">或者，如果用户使用报告邮件外接程序报告大量被标记为垃圾邮件的邮件，则组织的安全团队可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

<span data-ttu-id="c6abf-114">报告邮件加载项适用于大多数 Office 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="c6abf-114">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

 - <span data-ttu-id="c6abf-115">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="c6abf-115">Outlook on the web</span></span>
 - <span data-ttu-id="c6abf-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="c6abf-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="c6abf-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6abf-117">Outlook 2016</span></span>
 - <span data-ttu-id="c6abf-118">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="c6abf-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="c6abf-119">Outlook 包含在 Office 365 专业增强版中</span><span class="sxs-lookup"><span data-stu-id="c6abf-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="c6abf-120">报告邮件外接程序目前不可用于：</span><span class="sxs-lookup"><span data-stu-id="c6abf-120">The Report Message add-in is currently not available for:</span></span>

 - <span data-ttu-id="c6abf-121">内部部署 Exchange 组织中的邮箱</span><span class="sxs-lookup"><span data-stu-id="c6abf-121">Mailboxes in on-premises Exchange organizations</span></span>
 - <span data-ttu-id="c6abf-122">GCC、GCC 高或 DoD 订阅</span><span class="sxs-lookup"><span data-stu-id="c6abf-122">GCC, GCC HIGH, or DoD subscriptions</span></span>

<span data-ttu-id="c6abf-123">您的现有 web 浏览器应该能够满足报告消息外接程序的需要。但是，如果您注意到加载项不可用或无法按预期工作，请尝试使用不同的浏览器。</span><span class="sxs-lookup"><span data-stu-id="c6abf-123">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="c6abf-124">如果您是单个用户，则可以[为自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-124">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="c6abf-125">如果您是 Office 365 全局管理员或 Exchange Online 管理员，并且将 Exchange 配置为使用 OAuth 身份验证，则可以[为您的组织启用报告消息外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-125">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="c6abf-126">现在，可以通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)使用报告消息加载项。</span><span class="sxs-lookup"><span data-stu-id="c6abf-126">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="c6abf-127">获取自己的报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="c6abf-127">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="c6abf-128">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)中，搜索[报告邮件外接程序](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-128">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="c6abf-129">选择 "**立即获取**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-129">Choose **GET IT NOW**.</span></span>

   ![报告消息-立即获取](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="c6abf-131">查看使用条款和隐私策略。</span><span class="sxs-lookup"><span data-stu-id="c6abf-131">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="c6abf-132">然后选择" **继续**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-132">Then choose **Continue**.</span></span>

4. <span data-ttu-id="c6abf-133">使用你的工作或学校帐户（用于商业用途）或你的 Microsoft 帐户（供个人使用）登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c6abf-133">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c6abf-134">安装并启用加载项后，您将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="c6abf-134">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c6abf-135">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6abf-135">In Outlook, the icon looks like this:</span></span>

  ![报告邮件外接程序图标（适用于 Outlook）](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="c6abf-137">在 web 上的 Outlook （以前称为 Outlook Web App）中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6abf-137">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![Outlook 网页报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="c6abf-139">作为下一步，了解如何[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-139">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="c6abf-140">为您的组织获取并启用报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="c6abf-140">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6abf-141">若要完成此任务，您必须是 Office 365 全局管理员或 Exchange Online 管理员。</span><span class="sxs-lookup"><span data-stu-id="c6abf-141">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="c6abf-142">此外，必须将 Exchange 配置为使用 OAuth 身份验证以了解详细信息，请参阅[exchange 要求（加载项的集中部署）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-142">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="c6abf-143">转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-143">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="c6abf-145">选择 " **+ 部署外接端"**。</span><span class="sxs-lookup"><span data-stu-id="c6abf-145">Choose **+ Deploy Add-in**.</span></span>

   ![选择 "部署加载项"](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="c6abf-147">在 "**新建外接端**" 屏幕中，查看信息，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-147">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![新加载项详细信息](../../media/NewAddInScreen1.png)

4. <span data-ttu-id="c6abf-149">选择 **"我想从 Office 应用商店添加外接程序**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-149">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![我想要添加新的外接程序](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c6abf-151">搜索**报告消息**，并在结果列表中的**报告邮件外接程序**旁边，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-151">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![搜索报告消息，然后选择 "添加"](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="c6abf-153">在 "**报告邮件**" 屏幕上，查看信息，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-153">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![报告消息详细信息](../../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="c6abf-155">指定 Outlook 的用户默认设置，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-155">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![为 Outlook 报告邮件的默认设置](../../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="c6abf-157">指定要获取报告邮件加载项的收件人，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-157">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![谁可以获取报告邮件加载项](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="c6abf-159">建议[设置一个规则，以获取用户报告的电子](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="c6abf-159">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="c6abf-160">根据您在设置加载项时选择的内容（上面的步骤7-8），贵组织中的人员将会看到[报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-160">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="c6abf-161">你组织中的人员将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="c6abf-161">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="c6abf-162">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6abf-162">In Outlook, the icon looks like this:</span></span>

  ![报告邮件外接程序图标（适用于 Outlook）](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="c6abf-164">在 web 上的 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6abf-164">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="c6abf-166">当您通知用户有关报告邮件加载项时，请包含[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。</span><span class="sxs-lookup"><span data-stu-id="c6abf-166">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="c6abf-167">设置一个规则，以获取用户报告的电子邮件的副本</span><span class="sxs-lookup"><span data-stu-id="c6abf-167">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6abf-168">您必须是 Exchange Online 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="c6abf-168">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="c6abf-169">您可以设置一个规则，以获取由组织中的用户报告的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="c6abf-169">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="c6abf-170">为组织下载并启用报告邮件外接程序后，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c6abf-170">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="c6abf-171">在 Exchange 管理中心中，选择 "**邮件流** \> **规则**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-171">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="c6abf-172">选择**+** \> "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-172">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="c6abf-173">在 "**名称**" 框中，键入一个名称，如 "提交"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-173">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="c6abf-174">在 "在**以下情况应用此规则**" 列表中，选择**收件人地址包括 ...**。</span><span class="sxs-lookup"><span data-stu-id="c6abf-174">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="c6abf-175">在 "**指定字词或短语**" 屏幕中`junk@office365.microsoft.com` ， `phish@office365.microsoft.com`添加和，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c6abf-175">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![指定规则的垃圾邮件和网络钓鱼电子邮件地址](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="c6abf-177">在 "**执行以下操作 ...** " 列表中，选择 **"将邮件密件抄送给 ...**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-177">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="c6abf-178">添加全局管理员、安全管理员和/或安全阅读者，这些读者应收到用户报告给 Microsoft 的每封电子邮件的副本，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c6abf-178">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![添加全局或安全管理员以接收每个报告的邮件的副本](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="c6abf-180">选择 "**使用严重性级别审核此规则**"，然后选择 "**中**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-180">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="c6abf-181">在 "**为此规则选择模式**" 下，选择 "**强制**"。</span><span class="sxs-lookup"><span data-stu-id="c6abf-181">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![设置一个规则以获取每个报告的邮件的副本](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="c6abf-183">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c6abf-183">Choose **Save**.</span></span>

<span data-ttu-id="c6abf-184">在适当的情况下，当组织中的某人使用报告邮件加载项报告电子邮件时，全局管理员、安全管理员和/或安全读者将收到该邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="c6abf-184">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="c6abf-185">此信息可以让你设置或调整策略，如[Office 365 ATP 安全链接](atp-safe-links.md)策略或[反垃圾邮件](anti-spam-protection.md)设置。</span><span class="sxs-lookup"><span data-stu-id="c6abf-185">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="c6abf-186">了解如何使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="c6abf-186">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="c6abf-187">请参阅[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-187">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="c6abf-188">查看或编辑报告邮件外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="c6abf-188">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="c6abf-189">您可以在 "[服务" & "外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上查看和编辑报告邮件外接程序的默认设置。</span><span class="sxs-lookup"><span data-stu-id="c6abf-189">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6abf-190">若要完成此任务，您必须是 Office 365 全局管理员或 Exchange Online 管理员。</span><span class="sxs-lookup"><span data-stu-id="c6abf-190">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="c6abf-191">转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="c6abf-191">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="c6abf-193">查找并选择报告邮件加载项。</span><span class="sxs-lookup"><span data-stu-id="c6abf-193">Find and select the Report Message add-in.</span></span>

   ![查找并选择报告邮件加载项](../../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="c6abf-195">在 "报告邮件" 屏幕上，查看并编辑适用于您的组织的设置。</span><span class="sxs-lookup"><span data-stu-id="c6abf-195">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![报告邮件外接程序的设置](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="c6abf-197">相关主题</span><span class="sxs-lookup"><span data-stu-id="c6abf-197">Related topics</span></span>

[<span data-ttu-id="c6abf-198">使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="c6abf-198">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="c6abf-199">查看安全&amp;合规性中心中的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="c6abf-199">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="c6abf-200">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="c6abf-200">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="c6abf-201">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="c6abf-201">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)
