---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或整个组织启用 Outlook 和 Outlook 网页版的报告邮件加载项。
ms.openlocfilehash: 45f67e4c88d311254a0d922baed66178c3f672a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826633"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="573aa-103">启用报表消息加载项</span><span class="sxs-lookup"><span data-stu-id="573aa-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="573aa-104">如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议你在安全与自动安全与合规中心内使用&门户。</span><span class="sxs-lookup"><span data-stu-id="573aa-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="573aa-105">有关详细信息，请参阅["使用管理员提交"将可取的垃圾邮件、网络钓鱼邮件、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="573aa-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="573aa-106">用于 Outlook 和 Web 上的 Outlook 网页版的报告消息加载项 (Outlook Web App) 用户可以轻松地报告误报邮件 (标记为错误的) 或漏报电子邮件 (允许) Microsoft 及其关联来进行分析。</span><span class="sxs-lookup"><span data-stu-id="573aa-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="573aa-107">Microsoft 使用这些提交来提高电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="573aa-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="573aa-108">例如，假定用户要将大量邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="573aa-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="573aa-109">此信息会出现在 [安全仪表板](security-dashboard.md) 和其他报告中。</span><span class="sxs-lookup"><span data-stu-id="573aa-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="573aa-110">组织的安全团队可以将此信息用作反网络钓鱼策略可能需要更新的指示。</span><span class="sxs-lookup"><span data-stu-id="573aa-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="573aa-111">或者，如果用户要报告大量使用"报告邮件"外接程序标记为"非垃圾邮件"的邮件，则您组织的安全团队可能需要调整 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="573aa-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="573aa-112">此外，如果组织使用的是 [Office 365 高级威胁防护计划 1](office-365-atp.md) 或计划 [2，](office-365-ti.md)则报告邮件加载项还会为组织的安全团队提供有用的信息，可用于审查和更新安全策略。</span><span class="sxs-lookup"><span data-stu-id="573aa-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="573aa-113">管理员可以为组织启用报告消息加载项，且单个用户可以为自己安装报告消息加载项。</span><span class="sxs-lookup"><span data-stu-id="573aa-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="573aa-114">如果你是单个用户，可以 [自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="573aa-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="573aa-115">如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 被配置为使用 OAuth 身份验证，则可 [为组织启用报告邮件加载项](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="573aa-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="573aa-116">现在可以通过集中部署提供" [报告消息"加载项](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="573aa-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="573aa-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="573aa-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="573aa-118">报告消息加载项适用于大多数 Microsoft 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="573aa-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="573aa-119">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="573aa-119">Outlook on the web</span></span>
  - <span data-ttu-id="573aa-120">Outlook 2013 SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="573aa-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="573aa-121">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="573aa-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="573aa-122">Microsoft 365 企业版应用版中包含 Outlook</span><span class="sxs-lookup"><span data-stu-id="573aa-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="573aa-123">报告邮件外接程序不适用于本地 Exchange 组织的邮箱。</span><span class="sxs-lookup"><span data-stu-id="573aa-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="573aa-124">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="573aa-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="573aa-125">有关详细信息，请参阅 [在 Exchange Online 中指定提交用户收集垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="573aa-125">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="573aa-126">现有 Web 浏览器应与报告邮件加载项一起使用。</span><span class="sxs-lookup"><span data-stu-id="573aa-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="573aa-127">但是，如果你注意到外接程序不可用或无法按预期正常运行，请尝试使用其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="573aa-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="573aa-128">对于组织安装，需要将组织配置为使用 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="573aa-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="573aa-129">有关详细信息，请参阅"[确定加载项集中部署是否适用于贵组织。](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="573aa-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="573aa-130">管理员必须是全局管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="573aa-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="573aa-131">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="573aa-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="573aa-132">为自己获取报告消息加载项</span><span class="sxs-lookup"><span data-stu-id="573aa-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="573aa-133">转到 Microsoft <https://appsource.microsoft.com/marketplace/apps> AppSource，并搜索报告邮件加载项。</span><span class="sxs-lookup"><span data-stu-id="573aa-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="573aa-134">若要直接转到报告消息加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="573aa-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="573aa-135">单击 **"立即获取"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-135">Click **GET IT NOW**.</span></span>

   ![报告消息 - 立即获取](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="573aa-137">在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="573aa-138">使用你的工作或学校帐户 (以使用) 或 Microsoft 帐户管理员 (个人使用数据) 。</span><span class="sxs-lookup"><span data-stu-id="573aa-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="573aa-139">安装并启用加载项后，将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="573aa-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="573aa-140">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="573aa-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的报告邮件外接程序图标](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="573aa-142">在 Outlook 网页版中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="573aa-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页版报告邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="573aa-144">若要了解如何使用外接程序，请参阅 ["报告邮件"加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="573aa-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="573aa-145">为组织获取并启用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="573aa-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="573aa-146">最长可能需要 12 小时，外接程序才能显示在组织中。</span><span class="sxs-lookup"><span data-stu-id="573aa-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="573aa-147">在 Microsoft 365 管理中心，转到**上"服务 &"** 加载项 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 页面，然后单击"**部署加载项"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 管理中心的"服务和加载项"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="573aa-149">在随**即显示的新外接程序浮**出控件中，查看信息，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="573aa-150">在下一页上，单击 **"应用商店"中的"选择"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-150">On the next page, click **Choose from the Store**.</span></span>

   ![部署新的外接程序页面](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="573aa-152">在出现 **的"选择外接程序** 页面中单击"框，在'搜索' **框中** 单击，输入 **'报告消息'，** 然后单击' **搜索搜索** ![ '图标 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="573aa-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="573aa-153">在结果列表中，找到"**报告邮件"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![选择加载项搜索结果](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="573aa-155">在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="573aa-156">在 **显示的"配置** 加载项"页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="573aa-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="573aa-157">**已分配用户**：选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="573aa-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="573aa-158">\*\*默认情况下， (") \*\*</span><span class="sxs-lookup"><span data-stu-id="573aa-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="573aa-159">**特定用户/组**</span><span class="sxs-lookup"><span data-stu-id="573aa-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="573aa-160">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="573aa-160">**Just me**</span></span>

   - <span data-ttu-id="573aa-161">**部署方法**：选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="573aa-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="573aa-162">\*\*修复 (默认) ： \*\*加载项自动部署到指定用户，且不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="573aa-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="573aa-163">**可用**：用户可以在"家庭获取" **外接程序** \> **上安装管理员** \> **管理的加载项**。</span><span class="sxs-lookup"><span data-stu-id="573aa-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="573aa-164">**可选**：外接程序将自动部署到指定的用户，但可以选择删除它。</span><span class="sxs-lookup"><span data-stu-id="573aa-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![配置加载项页面](../../media/configure-add-in.png)

   <span data-ttu-id="573aa-166">完成后，请单击"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="573aa-167">在 **随即显示的** "部署报告邮件"页中，您将看到进度报告，后跟一个确认已部署外接程序的确认。</span><span class="sxs-lookup"><span data-stu-id="573aa-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="573aa-168">阅读这些信息后，单击"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-168">After you read the information, click **Next**.</span></span>

   !["部署报告消息"页面](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="573aa-170">在**出现的"通知外接程序"页上**，查看信息，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="573aa-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![通知外接程序页面](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="573aa-172">了解如何使用报告消息加载项</span><span class="sxs-lookup"><span data-stu-id="573aa-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="573aa-173">为其分配有加载项的用户将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="573aa-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="573aa-174">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="573aa-174">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的报告邮件外接程序图标](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="573aa-176">在 Outlook 网页版中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="573aa-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页版报表邮件加载项图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="573aa-178">如果你向用户通知报告邮件加载项，请加入一个指向 [使用报告邮件加载项的链接](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="573aa-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="573aa-179">查看或编辑报告消息加载项的设置</span><span class="sxs-lookup"><span data-stu-id="573aa-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="573aa-180">在 Microsoft 365 管理中心，转到 **"服务"&页面** <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 。</span><span class="sxs-lookup"><span data-stu-id="573aa-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![新版 Microsoft 365 管理中心的"服务和加载项"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="573aa-182">查找并选择 **"报告** 消息"加载项。</span><span class="sxs-lookup"><span data-stu-id="573aa-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="573aa-183">在随 **后显示的** "编辑报告消息"浮出控件中，根据你的组织查看和编辑设置。</span><span class="sxs-lookup"><span data-stu-id="573aa-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="573aa-184">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="573aa-184">When you're finished, click **Save**.</span></span>

   ![报告消息加载项的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="573aa-186">查看和审阅报告的邮件</span><span class="sxs-lookup"><span data-stu-id="573aa-186">View and review reported messages</span></span>

<span data-ttu-id="573aa-187">若要查看用户报告给 Microsoft 的邮件，你可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="573aa-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="573aa-188">使用管理提交门户。</span><span class="sxs-lookup"><span data-stu-id="573aa-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="573aa-189">有关详细信息，请参阅"[查看用户提交至 Microsoft"。](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="573aa-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="573aa-190">创建邮件流规则类型 (也称为传输规则，) 发送已报告邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="573aa-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="573aa-191">有关说明，请参阅 ["邮件流规则"来查看用户向 Microsoft 报告的内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="573aa-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
