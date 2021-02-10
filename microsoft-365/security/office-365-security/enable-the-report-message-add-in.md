---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或整个组织启用 Outlook 和 Outlook 网页邮件外接程序。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe47bcb4db42514f3a5252a567421ad792967cd1
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167571"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="3cb28-103">启用报表消息加载项</span><span class="sxs-lookup"><span data-stu-id="3cb28-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3cb28-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="3cb28-104">**Applies to**</span></span>
- [<span data-ttu-id="3cb28-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3cb28-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3cb28-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="3cb28-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3cb28-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cb28-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> <span data-ttu-id="3cb28-108">如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议你使用安全与合规中心&门户。</span><span class="sxs-lookup"><span data-stu-id="3cb28-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3cb28-109">有关详细信息，请参阅"使用管理员提交"将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3cb28-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="3cb28-110">Outlook 和 Web 上的 Outlook 的"报告邮件"和"报告钓鱼"外接程序 (以前称为 Outlook Web App) ，它使用户能够轻松地将标记为错误 (的误报或误报) 或漏报 (错误电子邮件允许) 向 Microsoft 及其关联公司进行分析。</span><span class="sxs-lookup"><span data-stu-id="3cb28-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="3cb28-111">Microsoft 使用这些提交来提高电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="3cb28-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="3cb28-112">例如，如果用户报告大量使用报告邮件外接程序标记为"非垃圾邮件"的邮件，则组织的安全团队可能需要调整反垃圾邮件 [策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3cb28-113">可以安装"报告邮件"或"报告钓鱼"加载项。</span><span class="sxs-lookup"><span data-stu-id="3cb28-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="3cb28-114">如果希望用户仅报告网络钓鱼邮件，请在你的组织中部署报告网络钓鱼外接程序。</span><span class="sxs-lookup"><span data-stu-id="3cb28-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="3cb28-115">有关详细信息，请参阅"[启用报告钓鱼外接程序"。](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="3cb28-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="3cb28-116">报告邮件外接程序提供了报告垃圾邮件和网络钓鱼邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="3cb28-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="3cb28-117">管理员可以为组织启用"报告消息"外接程序，并且单个用户可以自行安装它。</span><span class="sxs-lookup"><span data-stu-id="3cb28-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="3cb28-118">如果你是单个用户，你可以为自己启用报告 [消息外接程序](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="3cb28-119">如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，您可以为组织启用报告邮件 [外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="3cb28-120">报告消息Add-In现在可以通过集中 [部署获得](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-120">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3cb28-121">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3cb28-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3cb28-122">报告邮件外接程序适用于大多数 Microsoft 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="3cb28-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="3cb28-123">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="3cb28-123">Outlook on the web</span></span>
  - <span data-ttu-id="3cb28-124">Outlook 2013 SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3cb28-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="3cb28-125">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="3cb28-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="3cb28-126">Microsoft 365 企业应用版中包含的 Outlook</span><span class="sxs-lookup"><span data-stu-id="3cb28-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="3cb28-127">适用于 iOS 和 Android 的 Outlook 应用</span><span class="sxs-lookup"><span data-stu-id="3cb28-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="3cb28-128">报告邮件外接程序对内部部署 Exchange 组织的邮箱不可用。</span><span class="sxs-lookup"><span data-stu-id="3cb28-128">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="3cb28-129">可以将报告的邮件配置为复制或重定向到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3cb28-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="3cb28-130">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="3cb28-131">现有的 Web 浏览器应该与报告消息外接程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="3cb28-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="3cb28-132">但是，如果发现加载项不可用或无法正常使用，请尝试其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="3cb28-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="3cb28-133">对于组织安装，组织需要配置为使用 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="3cb28-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="3cb28-134">有关详细信息，请参阅"确定加载项集中部署[是否适用于你的组织"。](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="3cb28-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="3cb28-135">管理员需是全局管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="3cb28-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="3cb28-136">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="3cb28-137">为自己获取"报告邮件"加载项</span><span class="sxs-lookup"><span data-stu-id="3cb28-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="3cb28-138">转到 Microsoft AppSource， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告消息"加载项。</span><span class="sxs-lookup"><span data-stu-id="3cb28-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="3cb28-139">若要直接转到"报告邮件"加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="3cb28-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="3cb28-140">单击 **"立即获取"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-140">Click **GET IT NOW**.</span></span>

   ![报告消息 - 现在获取](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="3cb28-142">在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="3cb28-143">使用工作或学校帐户登录 (商业) 或 Microsoft 帐户 (个人使用) 。</span><span class="sxs-lookup"><span data-stu-id="3cb28-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="3cb28-144">安装并启用加载项后，你将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="3cb28-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="3cb28-145">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="3cb28-145">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的"报告邮件"加载项图标](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="3cb28-147">在 Outlook 网页 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="3cb28-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告邮件外接程序图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="3cb28-149">若要了解如何使用外接程序，请参阅"使用 [报告消息"加载项](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="3cb28-150">获取并启用组织的"报告邮件"加载项</span><span class="sxs-lookup"><span data-stu-id="3cb28-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="3cb28-151">外接程序最多可能需要 12 小时才能显示在组织中。</span><span class="sxs-lookup"><span data-stu-id="3cb28-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="3cb28-152">在 Microsoft 365 管理中心中，转到"设置加载项"页面，如果看不到外接程序页面，请转到"集成应用"页面顶部的"设置集成应用外接程序" \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  \>  \> 链接。</span><span class="sxs-lookup"><span data-stu-id="3cb28-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="3cb28-153">选择 **页面顶部的**"部署外接程序"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理中心中的"服务和加载项"页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="3cb28-155">在 **出现的"部署新的外接程序"** 飞出中，查看信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="3cb28-156">下一页上，单击 **"从应用商店中选择"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-156">On the next page, click **Choose from the Store**.</span></span>

   ![部署新外接程序页面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="3cb28-158">在 **出现的"选择外接程序"** 页中，在"搜索"框中单击，输入 **"报告** 消息"，然后单击 **"搜索搜索"** ![ 图标 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="3cb28-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="3cb28-159">在结果列表中，找到 **"报告消息**"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![选择外接程序搜索结果](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="3cb28-161">在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="3cb28-162">在 **出现的"配置外接程序"** 页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3cb28-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3cb28-163">**已分配用户**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3cb28-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="3cb28-164">**每个** (默认) </span><span class="sxs-lookup"><span data-stu-id="3cb28-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="3cb28-165">**特定用户/组**</span><span class="sxs-lookup"><span data-stu-id="3cb28-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="3cb28-166">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="3cb28-166">**Just me**</span></span>

   - <span data-ttu-id="3cb28-167">**部署方法**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="3cb28-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="3cb28-168">**修复 (默认) ：** 外接程序会自动部署到指定用户，并且他们无法删除它。</span><span class="sxs-lookup"><span data-stu-id="3cb28-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="3cb28-169">**可用**：用户可以在家庭获取外接程序管理员管理的 \>  \> **安装外接程序**。</span><span class="sxs-lookup"><span data-stu-id="3cb28-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="3cb28-170">**可选**：加载项会自动部署到指定用户，但他们可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="3cb28-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![配置外接程序页面](../../media/configure-add-in.png)

   <span data-ttu-id="3cb28-172">完成后，单击"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="3cb28-173">在 **出现的"** 部署报告消息"页中，你将看到一个进度报告，后跟一条确认加载项已部署的确认。</span><span class="sxs-lookup"><span data-stu-id="3cb28-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="3cb28-174">阅读信息后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-174">After you read the information, click **Next**.</span></span>

   !["部署报告消息"页](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="3cb28-176">在出现的 **"宣布外接程序"** 页上，查看信息，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="3cb28-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   !["宣布外接程序"页](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="3cb28-178">了解如何使用"报告邮件"加载项</span><span class="sxs-lookup"><span data-stu-id="3cb28-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="3cb28-179">分配了外接程序的人将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="3cb28-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="3cb28-180">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="3cb28-180">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的"报告邮件外接程序"图标](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="3cb28-182">在 Outlook 网页 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="3cb28-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告邮件外接程序图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="3cb28-184">当通知用户有关报告邮件外接程序时，请包含一个指向"使用报告邮件 ["加载项的链接](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="3cb28-185">查看或编辑报告邮件外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="3cb28-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="3cb28-186">在 Microsoft 365 管理中心中，转到"设置加载项"页面，如果看不到外接程序页面，请转到"集成应用"页面顶部的"设置集成应用外接程序" \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  \>  \> 链接。</span><span class="sxs-lookup"><span data-stu-id="3cb28-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![新Add-Ins Microsoft 365 管理中心中的"服务和服务"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="3cb28-188">查找并选择 **"报告邮件** "加载项。</span><span class="sxs-lookup"><span data-stu-id="3cb28-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="3cb28-189">在 **出现的"编辑报告消息** "飞出中，根据组织情况查看和编辑设置。</span><span class="sxs-lookup"><span data-stu-id="3cb28-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="3cb28-190">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3cb28-190">When you're finished, click **Save**.</span></span>

   ![报告邮件加载项的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="3cb28-192">查看和查看报告的邮件</span><span class="sxs-lookup"><span data-stu-id="3cb28-192">View and review reported messages</span></span>

<span data-ttu-id="3cb28-193">若要查看用户向 Microsoft 报告的邮件，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="3cb28-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="3cb28-194">使用管理员提交门户。</span><span class="sxs-lookup"><span data-stu-id="3cb28-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="3cb28-195">有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="3cb28-196">创建邮件流规则 (传输规则) 报告的邮件副本。</span><span class="sxs-lookup"><span data-stu-id="3cb28-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="3cb28-197">有关说明， [请参阅"使用邮件流规则"查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
