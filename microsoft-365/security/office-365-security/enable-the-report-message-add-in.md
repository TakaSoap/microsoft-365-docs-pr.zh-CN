---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
ms.openlocfilehash: 22ce1c8e8084cb0bcbcb2f9fa4c0c80e1a59bf9c
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939471"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="6ab27-103">启用报表消息加载项</span><span class="sxs-lookup"><span data-stu-id="6ab27-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="6ab27-104">如果您是具有 Exchange Online 邮箱的组织中的管理员，我们建议您在安全 & 合规性中心中使用提交门户。</span><span class="sxs-lookup"><span data-stu-id="6ab27-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6ab27-105">有关详细信息，请参阅[使用管理员提交将可疑的垃圾邮件、网络钓鱼、url 和文件提交给 Microsoft](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="6ab27-106">Outlook 和 web 上的 Outlook （以前称为 "Outlook Web App"）的报告邮件外接程序使用户能够轻松地将误报（电子邮件被标记为 "坏"）或 "漏报（允许错误电子邮件"）报告给 Microsoft 及其子公司进行分析。</span><span class="sxs-lookup"><span data-stu-id="6ab27-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="6ab27-107">Microsoft 使用这些提交改进电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="6ab27-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="6ab27-108">例如，假设有人将大量邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="6ab27-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="6ab27-109">[安全仪表板](security-dashboard.md)和其他报告中的此信息图面。</span><span class="sxs-lookup"><span data-stu-id="6ab27-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="6ab27-110">组织的安全团队可以使用此信息指示可能需要更新的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="6ab27-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="6ab27-111">或者，如果用户使用报告邮件外接程序报告大量被标记为垃圾邮件的邮件，则组织的安全团队可能需要调整[反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6ab27-112">此外，如果您的组织使用的是[Office 365 高级威胁防护计划 1](office-365-atp.md)或[计划 2](office-365-ti.md)，则报告消息外接程序会为您组织的安全团队提供可用于查看和更新安全策略的有用信息。</span><span class="sxs-lookup"><span data-stu-id="6ab27-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="6ab27-113">管理员可以为组织启用报告邮件外接程序，单个用户可以自行安装。</span><span class="sxs-lookup"><span data-stu-id="6ab27-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="6ab27-114">如果您是单个用户，则可以[为自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="6ab27-115">如果您是全局管理员或 Exchange Online 管理员，并且将 Exchange 配置为使用 OAuth 身份验证，则可以[为您的组织启用报告消息外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="6ab27-116">现在，可以通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)使用报告消息加载项。</span><span class="sxs-lookup"><span data-stu-id="6ab27-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6ab27-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="6ab27-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6ab27-118">报告邮件加载项适用于大多数 Microsoft 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="6ab27-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="6ab27-119">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="6ab27-119">Outlook on the web</span></span>
  - <span data-ttu-id="6ab27-120">Outlook 2013 SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="6ab27-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="6ab27-121">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="6ab27-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="6ab27-122">Outlook 包含在适用于企业的 Microsoft 365 应用程序中</span><span class="sxs-lookup"><span data-stu-id="6ab27-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="6ab27-123">报告邮件外接程序目前不可用于：</span><span class="sxs-lookup"><span data-stu-id="6ab27-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="6ab27-124">内部部署 Exchange 组织中的邮箱</span><span class="sxs-lookup"><span data-stu-id="6ab27-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="6ab27-125">GCC、GCC 高或 DoD 订阅</span><span class="sxs-lookup"><span data-stu-id="6ab27-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="6ab27-126">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ab27-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6ab27-127">有关详细信息，请参阅[在 Office 365 中指定用户提交垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="6ab27-128">您的现有 web 浏览器应与报告邮件外接程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="6ab27-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="6ab27-129">但是，如果您注意到加载项不可用或无法按预期工作，请尝试使用不同的浏览器。</span><span class="sxs-lookup"><span data-stu-id="6ab27-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="6ab27-130">对于组织安装，需要将组织配置为使用 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ab27-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="6ab27-131">有关详细信息，请参阅[确定加载项的集中部署是否适用于你的组织](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="6ab27-132">管理员需要是全局管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="6ab27-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="6ab27-133">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="6ab27-134">获取自己的报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="6ab27-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="6ab27-135">转到 Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> ，并搜索报告邮件外接程序。</span><span class="sxs-lookup"><span data-stu-id="6ab27-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="6ab27-136">若要直接转到报告邮件加载项，请转到<https://appsource.microsoft.com/product/office/wa104381180>。</span><span class="sxs-lookup"><span data-stu-id="6ab27-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="6ab27-137">单击 "**立即获取**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-137">Click **GET IT NOW**.</span></span>

   ![报告消息-立即获取](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="6ab27-139">在显示的对话框中，查看使用条款和隐私策略，然后单击 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="6ab27-140">使用你的工作或学校帐户（用于商业用途）或你的 Microsoft 帐户（供个人使用）登录。</span><span class="sxs-lookup"><span data-stu-id="6ab27-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="6ab27-141">安装并启用加载项后，您将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="6ab27-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="6ab27-142">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ab27-142">In Outlook, the icon looks like this:</span></span>

  ![报告邮件外接程序图标（适用于 Outlook）](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="6ab27-144">在 web 上的 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ab27-144">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="6ab27-146">若要了解如何使用加载项，请参阅[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="6ab27-147">为您的组织获取并启用报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="6ab27-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="6ab27-148">最长可能需要12个小时，外接程序才会显示在您的组织中。</span><span class="sxs-lookup"><span data-stu-id="6ab27-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="6ab27-149">在 Microsoft 365 管理中心，转到 "服务" **& "外接程序**" 页<https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>，然后单击 "**部署外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 管理中心中的 "服务和外接程序" 页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="6ab27-151">在 "**部署新的外接程序**" 弹出对话框中，查看信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="6ab27-152">在下一页上，单击 **"从存储区中选择"**。</span><span class="sxs-lookup"><span data-stu-id="6ab27-152">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的加载项页面](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="6ab27-154">在出现的 "**选择外接程序**" 页中，单击 "**搜索**" 框，输入**报告消息**，然后单击 "**搜索** ![搜索" 图标](../../media/search-icon.png)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="6ab27-155">在结果列表中，找到 "**报告消息**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![选择加载项搜索结果](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="6ab27-157">在出现的对话框中，查看许可和隐私信息，然后单击 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="6ab27-158">在出现的 "**配置外接程序**" 页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6ab27-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6ab27-159">**分配的用户**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6ab27-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="6ab27-160">**所有人**（默认）</span><span class="sxs-lookup"><span data-stu-id="6ab27-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="6ab27-161">**特定用户/组**</span><span class="sxs-lookup"><span data-stu-id="6ab27-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="6ab27-162">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="6ab27-162">**Just me**</span></span>

   - <span data-ttu-id="6ab27-163">**部署方法**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6ab27-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="6ab27-164">**固定（默认值）**：加载项将自动部署到指定的用户，并且无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="6ab27-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="6ab27-165">**可用**：用户可以在**家庭** \> **Get add-ins** \>版中安装外接程序**管理员管理**。</span><span class="sxs-lookup"><span data-stu-id="6ab27-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="6ab27-166">**可选**：将加载项自动部署到指定的用户，但可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="6ab27-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![配置加载项页面](../../media/configure-add-in.png)

   <span data-ttu-id="6ab27-168">完成后，请单击 "**部署**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="6ab27-169">在出现的 "**部署报告邮件**" 页中，您将看到一个进度报告，随后将会看到已部署加载项的确认信息。</span><span class="sxs-lookup"><span data-stu-id="6ab27-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="6ab27-170">阅读信息后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-170">After you read the information, click **Next**.</span></span>

   !["部署报告邮件" 页](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="6ab27-172">在出现的 "**通知外接程序**" 页上，查看信息，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="6ab27-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![通知加载项页面](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="6ab27-174">了解如何使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="6ab27-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="6ab27-175">为其分配了加载项的人员将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="6ab27-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="6ab27-176">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ab27-176">In Outlook, the icon looks like this:</span></span>

  ![报告邮件外接程序图标（适用于 Outlook）](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="6ab27-178">在 web 上的 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ab27-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="6ab27-180">当您通知用户有关报告邮件加载项时，请包含[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。</span><span class="sxs-lookup"><span data-stu-id="6ab27-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="6ab27-181">查看或编辑报告邮件外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="6ab27-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="6ab27-182">在 Microsoft 365 管理中心，转到上<https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>的 "**服务" & "外接程序**" 页。</span><span class="sxs-lookup"><span data-stu-id="6ab27-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="6ab27-184">查找并选择**报告邮件**加载项。</span><span class="sxs-lookup"><span data-stu-id="6ab27-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="6ab27-185">在显示的 "**编辑报告消息**" 浮出控件中，查看并编辑组织的相应设置。</span><span class="sxs-lookup"><span data-stu-id="6ab27-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="6ab27-186">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="6ab27-186">When you're finished, click **Save**.</span></span>

   ![报告邮件外接程序的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="6ab27-188">查看和查看报告的邮件</span><span class="sxs-lookup"><span data-stu-id="6ab27-188">View and review reported messages</span></span>

<span data-ttu-id="6ab27-189">若要查看用户向 Microsoft 报告的邮件，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="6ab27-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="6ab27-190">使用管理提交门户。</span><span class="sxs-lookup"><span data-stu-id="6ab27-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="6ab27-191">有关详细信息，请参阅[View user 报送 To Microsoft](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="6ab27-192">创建邮件流规则（也称为传输规则），以发送报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="6ab27-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="6ab27-193">有关说明，请参阅[使用邮件流规则查看用户报告给 Microsoft 的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab27-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
