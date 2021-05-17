---
title: 从 Google Workspace 迁移业务电子邮件和日历
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何将电子邮件、联系人和日历从 Google Workspace 迁移到 Microsoft 365 for business。
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913618"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="a3687-103">从 Google Workspace 迁移业务电子邮件和日历</span><span class="sxs-lookup"><span data-stu-id="a3687-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="a3687-104">可以使用管理员运行迁移从 Google 工作区Exchange Online迁移。</span><span class="sxs-lookup"><span data-stu-id="a3687-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="a3687-105">您可以一次迁移所有邮件，也可以分步迁移邮件。</span><span class="sxs-lookup"><span data-stu-id="a3687-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="a3687-106">以下步骤显示如何一次迁移电子邮件数据。</span><span class="sxs-lookup"><span data-stu-id="a3687-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="a3687-107">有关详细信息，请参阅执行 [G 套件迁移](/exchange/mailbox-migration/perform-g-suite-migration)。</span><span class="sxs-lookup"><span data-stu-id="a3687-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="a3687-108">迁移过程需要几个步骤，可能需要几个小时到几天的时间，具体取决于要迁移的数据量。</span><span class="sxs-lookup"><span data-stu-id="a3687-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="a3687-109">试一试！</span><span class="sxs-lookup"><span data-stu-id="a3687-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="a3687-110">创建 Google 服务帐户</span><span class="sxs-lookup"><span data-stu-id="a3687-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="a3687-111">使用 Chrome 浏览器，登录到 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="a3687-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="a3687-112">In a new tab or window， navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span><span class="sxs-lookup"><span data-stu-id="a3687-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="a3687-113">选择 **"创建项目"，** 将项目命名，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="a3687-114">选择 **"创建服务帐户**"，输入名称，选择 **"创建"，** 然后选择"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="a3687-115">打开" **操作"** 菜单， **选择"编辑"，** 然后记下唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a3687-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="a3687-116">此过程稍后将需要此 ID。</span><span class="sxs-lookup"><span data-stu-id="a3687-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="a3687-117">打开" **显示域范围的委派"** 部分。</span><span class="sxs-lookup"><span data-stu-id="a3687-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="a3687-118">选择 **"启用 G Suite 域范围委派"，** 输入许可屏幕的产品名称，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="a3687-119">迁移过程不会使用产品名称，但需要将其保存在对话框中。</span><span class="sxs-lookup"><span data-stu-id="a3687-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="a3687-120">再次打开 **"操作**"菜单，然后选择"**创建密钥"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="a3687-121">选择 **"JSON"，** 然后选择"**创建"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="a3687-122">私钥将保存到你的设备的下载文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a3687-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="a3687-123">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="a3687-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="a3687-124">为项目启用 API 用法</span><span class="sxs-lookup"><span data-stu-id="a3687-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="a3687-125">导航到 [API 页面](https://console.developers.google.com/apis/library)。</span><span class="sxs-lookup"><span data-stu-id="a3687-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="a3687-126">在搜索栏中，输入 **Gmail API**。</span><span class="sxs-lookup"><span data-stu-id="a3687-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="a3687-127">选择它， **然后选择启用**。</span><span class="sxs-lookup"><span data-stu-id="a3687-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="a3687-128">对 Google 日历 API 和联系人 API 重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a3687-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="a3687-129">授予对服务帐户的访问权限</span><span class="sxs-lookup"><span data-stu-id="a3687-129">Grant access to the service account</span></span>

1. <span data-ttu-id="a3687-130">返回到 Google Workspace 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a3687-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="a3687-131">选择 **"安全性**"，向下滚动并打开 **API 控件**。</span><span class="sxs-lookup"><span data-stu-id="a3687-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="a3687-132">向下滚动并选择"**管理域范围的委派"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="a3687-133">选择 **"添加新** "，然后输入之前记下的客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="a3687-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="a3687-134">然后输入 Google API 的 OAuth 范围。</span><span class="sxs-lookup"><span data-stu-id="a3687-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="a3687-135">可在步骤 5 [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) 以下产品：：</span><span class="sxs-lookup"><span data-stu-id="a3687-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="a3687-136">选择 **"授权"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="a3687-137">为要发送到邮箱的邮件创建Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3687-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="a3687-138">返回到 **Google Workspace 管理** 控制台。</span><span class="sxs-lookup"><span data-stu-id="a3687-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="a3687-139">选择 **"域\*\*\*\*"，"管理** 域"，然后选择"**添加域别名"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="a3687-140">输入类似 的域别名 `m365.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="a3687-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="a3687-141">然后选择" **继续"并验证域所有权**。</span><span class="sxs-lookup"><span data-stu-id="a3687-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="a3687-142">域验证通常只需几分钟，但最多可能需要 48 小时。</span><span class="sxs-lookup"><span data-stu-id="a3687-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="a3687-143">转到管理[Microsoft 365中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a3687-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="a3687-144">In the **Microsoft 365 admin center**， in the left nav， select Show **all**，**设置**， **Domains**， and then **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="a3687-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="a3687-145">输入之前创建的子域，然后选择"**使用此域"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="a3687-146">若要连接域，请选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="a3687-147">向下滚动并记下 MX 记录、CNAME 记录和 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="a3687-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="a3687-148">返回到 **Google 管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="a3687-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="a3687-149">选择 **"域**"，**选择"管理域\*\*\*\*"，"验证详细信息**"，然后选择"**管理域"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="a3687-150">在左侧导航中，选择 **"DNS"** 并向下滚动到"**自定义资源记录"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="a3687-151">打开"记录类型"下拉列表，选择 **"MX"，** 输入或复制并粘贴之前记录的 MX 记录信息，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="a3687-152">对 CNAME 记录和 TXT 记录重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a3687-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="a3687-153">可能需要一些时间，这些更改生效。</span><span class="sxs-lookup"><span data-stu-id="a3687-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="a3687-154">返回到你离开管理 **中心Microsoft 365，\*\*\*\*然后选择继续。**</span><span class="sxs-lookup"><span data-stu-id="a3687-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="a3687-155">您的域现已设置。</span><span class="sxs-lookup"><span data-stu-id="a3687-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="a3687-156">在电子邮件中创建Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3687-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="a3687-157">在开始迁移之前，您需要使用新的子域为用户创建电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="a3687-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="a3687-158">若要开始下一步，请在管理中心的"添加域"Microsoft 365，选择"转到活动 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="a3687-159">选择用户，然后管理 **用户名和电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="a3687-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="a3687-160">从 **"域** "下拉列表中，选择之前创建的子域。</span><span class="sxs-lookup"><span data-stu-id="a3687-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="a3687-161">输入用户名，选择"**添加\*\*\*\*"，"保存更改**"，然后关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="a3687-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="a3687-162">对每个用户重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a3687-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="a3687-163">开始迁移过程</span><span class="sxs-lookup"><span data-stu-id="a3687-163">Start the migration process</span></span>

<span data-ttu-id="a3687-164">完成后，即可进行迁移。</span><span class="sxs-lookup"><span data-stu-id="a3687-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="a3687-165">在管理中心的左侧导航 **Microsoft 365，向下滚动** 到"管理中心 **"，然后选择"Exchange"。** </span><span class="sxs-lookup"><span data-stu-id="a3687-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="a3687-166">在 **"收件人"** 下，选择 **"迁移**"，选择"**新建\*\*\*\*"，Exchange Online"** 迁移"，选择 **"G Suite 迁移**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="a3687-167">创建包含要迁移的邮箱列表的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="a3687-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="a3687-168">确保文件遵循以下格式：</span><span class="sxs-lookup"><span data-stu-id="a3687-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="a3687-169">有关详细信息，请参阅[aka.ms/GoogleWorkspaceMigration。](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="a3687-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="a3687-170">选择 **"选择文件**"，导航到 CSV 文件，选择它，选择"**打开**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="a3687-171">验证要用于测试的管理员电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a3687-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="a3687-172">选择 **"文件**"，导航到之前创建的 JSON 文件 (通常位于计算机上"下载"文件夹中) ，选择"打开"，然后选择"下一 **步"。** </span><span class="sxs-lookup"><span data-stu-id="a3687-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="a3687-173">在"新建迁移批处理 **名称"字段中输入名称**。</span><span class="sxs-lookup"><span data-stu-id="a3687-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="a3687-174">在"目标传递域"字段中输入创建的 **子域，** 选择"下一步 **"，然后选择**"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="a3687-175">保存信息后，选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="a3687-176">现在可以查看迁移的状态。</span><span class="sxs-lookup"><span data-stu-id="a3687-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="a3687-177">经过一段时间后，根据要迁移的用户数，选择"刷新 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="a3687-178">在状态更改为"已同步 **"** 后，选择 **"完成此迁移批处理**"，然后选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="a3687-179">该过程完成后，状态将更改为"**已完成"。**</span><span class="sxs-lookup"><span data-stu-id="a3687-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="a3687-180">如果需要，可以选择" **查看详细信息** "，了解有关迁移的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3687-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="a3687-181">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="a3687-181">Select **Close**.</span></span> 
1. <span data-ttu-id="a3687-182">打开Outlook验证来自 Google Workspace 的所有电子邮件已成功迁移。</span><span class="sxs-lookup"><span data-stu-id="a3687-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="a3687-183">也可以对日历项目和联系人重复此操作。</span><span class="sxs-lookup"><span data-stu-id="a3687-183">You can repeat this for calendar items and contacts as well.</span></span>