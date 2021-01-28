---
title: 启用报告钓鱼加载项
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: 了解如何为单个用户或整个组织启用 Outlook 和 Web 上的 Outlook 报告网络钓鱼外接程序。
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029134"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="66c6a-103">启用“报告网络钓鱼”加载项</span><span class="sxs-lookup"><span data-stu-id="66c6a-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="66c6a-104">如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议您使用安全与合规中心中的&门户。</span><span class="sxs-lookup"><span data-stu-id="66c6a-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="66c6a-105">有关详细信息，请参阅"使用管理员提交"将可疑的垃圾邮件、网络钓鱼[、URL 和文件提交到 Microsoft。](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="66c6a-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="66c6a-106">Outlook 和 Web 上的 Outlook 的"报告邮件"和"报告钓鱼"外接程序 (以前称为 Outlook Web App) ，使用户能够轻松地将标记为错误) 或误报 (的误报电子邮件或漏报 (错误电子邮件允许) 向 Microsoft 及其关联公司进行分析。</span><span class="sxs-lookup"><span data-stu-id="66c6a-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="66c6a-107">Microsoft 使用这些提交来提高电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="66c6a-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="66c6a-108">例如，假设用户使用"报告网络钓鱼"外接程序报告许多邮件。</span><span class="sxs-lookup"><span data-stu-id="66c6a-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="66c6a-109">此信息在安全仪表板 [和其他](security-dashboard.md) 报告中显示。</span><span class="sxs-lookup"><span data-stu-id="66c6a-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="66c6a-110">组织的安全团队可以使用此信息来指示可能需要更新防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="66c6a-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="66c6a-111">可以安装"报告邮件"或"报告钓鱼"加载项。</span><span class="sxs-lookup"><span data-stu-id="66c6a-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="66c6a-112">如果希望用户同时报告垃圾邮件和网络钓鱼邮件，请在你的组织中部署报告邮件外接程序。</span><span class="sxs-lookup"><span data-stu-id="66c6a-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="66c6a-113">有关详细信息，请参阅 ["启用报告邮件"加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="66c6a-114">报告网络钓鱼外接程序提供仅报告网络钓鱼邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="66c6a-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="66c6a-115">管理员可以为组织启用报告网络钓鱼外接程序，并且单个用户可以自行安装它。</span><span class="sxs-lookup"><span data-stu-id="66c6a-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="66c6a-116">如果您是单个用户，您可以为自己启用报告网络钓鱼 [外接程序](#get-the-report-phishing-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="66c6a-117">如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，您可以为组织启用报告网络钓鱼 [外接程序](#get-and-enable-the-report-phishing-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="66c6a-118">报告网络钓鱼Add-In现在可以通过集中 [部署获得](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="66c6a-119">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="66c6a-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="66c6a-120">报告网络钓鱼外接程序适用于大多数 Microsoft 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="66c6a-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="66c6a-121">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="66c6a-121">Outlook on the web</span></span>
  - <span data-ttu-id="66c6a-122">Outlook 2013 SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="66c6a-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="66c6a-123">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="66c6a-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="66c6a-124">Microsoft 365 企业应用版中包含的 Outlook</span><span class="sxs-lookup"><span data-stu-id="66c6a-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="66c6a-125">报告网络钓鱼外接程序对内部部署 Exchange 组织的邮箱不可用。</span><span class="sxs-lookup"><span data-stu-id="66c6a-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="66c6a-126">可以将报告的邮件配置为复制或重定向到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="66c6a-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="66c6a-127">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="66c6a-128">现有的 Web 浏览器应该与报告网络钓鱼外接程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="66c6a-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="66c6a-129">但是，如果发现加载项不可用或无法正常使用，请尝试其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="66c6a-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="66c6a-130">对于组织安装，组织需要配置为使用 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="66c6a-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="66c6a-131">有关详细信息，请参阅"确定外接程序的集中部署[是否适用于你的组织"。](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="66c6a-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="66c6a-132">管理员需为全局管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="66c6a-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="66c6a-133">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="66c6a-134">为自己获取报告网络钓鱼外接程序</span><span class="sxs-lookup"><span data-stu-id="66c6a-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="66c6a-135">转到 Microsoft AppSource， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告钓鱼"加载项。</span><span class="sxs-lookup"><span data-stu-id="66c6a-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="66c6a-136">单击 **"立即获取"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="66c6a-137">在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="66c6a-138">使用工作或学校帐户登录 (商业) 或 Microsoft 帐户 (个人使用) 。</span><span class="sxs-lookup"><span data-stu-id="66c6a-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="66c6a-139">安装并启用加载项后，你将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="66c6a-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="66c6a-140">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c6a-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的"报告钓鱼外接程序"图标](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="66c6a-142">在 Outlook 网页 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c6a-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告网络钓鱼外接程序图标](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="66c6a-144">获取并启用组织的"报告钓鱼"外接程序</span><span class="sxs-lookup"><span data-stu-id="66c6a-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="66c6a-145">外接程序最多可能需要 12 小时才能显示在组织中。</span><span class="sxs-lookup"><span data-stu-id="66c6a-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="66c6a-146">在 Microsoft 365 管理中心中，转到"设置加载项"页面，如果看不到外接程序页面，请转到"集成应用"页面顶部的"设置集成应用外接程序" \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  \>  \> 链接。</span><span class="sxs-lookup"><span data-stu-id="66c6a-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="66c6a-147">选择 **页面顶部的**"部署外接程序"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理中心中的"服务和加载项"页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="66c6a-149">在 **出现的"部署新的外接程序"** 飞出中，查看信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="66c6a-150">下一页上，单击 **"从应用商店中选择"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-150">On the next page, click **Choose from the Store**.</span></span>

   ![部署新外接程序页面](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="66c6a-152">在 **出现的"选择外接程序"** 页中，在"搜索"框中单击，输入"报告钓鱼 **"，** 然后单击 **"搜索搜索"** ![ 图标 ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="66c6a-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="66c6a-153">在结果列表中，找到 **"报告钓鱼"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="66c6a-154">在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="66c6a-155">在 **出现的"配置外接程序"** 页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="66c6a-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="66c6a-156">**已分配用户**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="66c6a-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="66c6a-157">**每个** (默认) </span><span class="sxs-lookup"><span data-stu-id="66c6a-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="66c6a-158">**特定用户/组**</span><span class="sxs-lookup"><span data-stu-id="66c6a-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="66c6a-159">**就我自己**</span><span class="sxs-lookup"><span data-stu-id="66c6a-159">**Just me**</span></span>

   - <span data-ttu-id="66c6a-160">**部署方法**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="66c6a-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="66c6a-161">**修复 (默认) ：** 外接程序会自动部署到指定用户，并且他们无法删除它。</span><span class="sxs-lookup"><span data-stu-id="66c6a-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="66c6a-162">**可用**： 用户可以在家庭获取外接程序管理员管理的 \>  \> **安装外接程序**。</span><span class="sxs-lookup"><span data-stu-id="66c6a-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="66c6a-163">**可选**：加载项会自动部署到指定用户，但他们可以选择将其删除。</span><span class="sxs-lookup"><span data-stu-id="66c6a-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="66c6a-164">完成后，单击"部署 **"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="66c6a-165">在 **出现的"** 部署报告钓鱼"页中，你将看到一个进度报告，然后确认外接程序已部署。</span><span class="sxs-lookup"><span data-stu-id="66c6a-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="66c6a-166">阅读信息后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="66c6a-167">在出现的 **"宣布外接程序"** 页上，查看信息，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="66c6a-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="66c6a-168">了解如何使用报告网络钓鱼外接程序</span><span class="sxs-lookup"><span data-stu-id="66c6a-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="66c6a-169">分配了外接程序的人将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="66c6a-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="66c6a-170">在 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c6a-170">In Outlook, the icon looks like this:</span></span>

  ![Outlook 的"报告钓鱼外接程序"图标](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="66c6a-172">在 Outlook 网页 Outlook 中，图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="66c6a-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook 网页报告钓鱼外接程序图标](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="66c6a-174">查看或编辑报告网络钓鱼外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="66c6a-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="66c6a-175">在 Microsoft 365 管理中心中，转到"设置加载项"页面，如果看不到外接程序页面，请转到"集成应用"页面顶部的"设置集成应用外接程序" \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>  \>  \> 链接。</span><span class="sxs-lookup"><span data-stu-id="66c6a-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="66c6a-176">查找并选择 **"报告钓鱼** "加载项。</span><span class="sxs-lookup"><span data-stu-id="66c6a-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="66c6a-177">在 **"编辑报告钓鱼"** 飞出控件中，根据组织需要显示、查看和编辑设置。</span><span class="sxs-lookup"><span data-stu-id="66c6a-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="66c6a-178">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="66c6a-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="66c6a-179">查看和查看报告的邮件</span><span class="sxs-lookup"><span data-stu-id="66c6a-179">View and review reported messages</span></span>

<span data-ttu-id="66c6a-180">若要查看用户向 Microsoft 报告的邮件，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="66c6a-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="66c6a-181">使用管理员提交门户。</span><span class="sxs-lookup"><span data-stu-id="66c6a-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="66c6a-182">有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="66c6a-183">创建邮件流规则 (传输规则) 报告的邮件副本。</span><span class="sxs-lookup"><span data-stu-id="66c6a-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="66c6a-184">有关说明， [请参阅"使用邮件流规则"查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="66c6a-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>