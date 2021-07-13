---
title: 设置 Microsoft 365 商业标准版
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: 购买 Microsoft 365 商业标准版时，可以选择使用自有的域，也可以在注册期间购买一个域。
ms.openlocfilehash: 861a9e38f10f0cd654e2b10c1879811cd668bc1f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393807"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="ed95c-103">设置 Microsoft 商业标准版</span><span class="sxs-lookup"><span data-stu-id="ed95c-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="ed95c-104">添加你的域以个性化设置登录名</span><span class="sxs-lookup"><span data-stu-id="ed95c-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="ed95c-105">购买 Microsoft 365 商业标准版时，你可以选择使用自己拥有的域，也可以在注册期间购买一个域。</span><span class="sxs-lookup"><span data-stu-id="ed95c-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="ed95c-106">如果你在注册时购买了新域，则域已全部设置好，你可以继续[添加用户并分配许可证](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="ed95c-107">使用全局管理员凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="ed95c-108">选择“**转到设置**”以启动向导。</span><span class="sxs-lookup"><span data-stu-id="ed95c-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="ed95c-109">在“**安装 Office 应用**”页面上，可选择在自己的计算机上安装应用。</span><span class="sxs-lookup"><span data-stu-id="ed95c-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="ed95c-110">在“**添加域**”步骤中，输入要使用的域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ed95c-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ed95c-p101">如果您在注册期间购买了域，您将不会在此处看到 **添加域** 步骤。 转至 [添加用户](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-p101">If you purchased a domain during the sign-up, you will not see **Add a domain** step here. Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="ed95c-113">按照向导[在任何 DNS 托管提供商处为 Office 365 创建 DNS 记录](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)中的步骤验证你是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="ed95c-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="ed95c-114">如果你知道域主机，另请参阅[向Microsoft 365](/microsoft-365/admin/setup/add-domain)添加域。</span><span class="sxs-lookup"><span data-stu-id="ed95c-114">If you know your domain host, see also [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).</span></span>

    <span data-ttu-id="ed95c-115">如果你的托管服务提供商是 GoDaddy 或启用了 [domain connect](/office365/admin/get-help-with-domains/domain-connect) 的其他主机，则此过程很简单，系统会自动要求你登录并让 Microsoft 代表你进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ed95c-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy“确认访问”页面上，选择“授权”。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="ed95c-117">添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="ed95c-117">Add users and assign licenses</span></span>

<span data-ttu-id="ed95c-118">你可以在向导中添加用户，但你也可以[以后在管理中心添加用户](../add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="ed95c-119">此外，如果你具有本地域控制器，则可以使用 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) 添加用户。</span><span class="sxs-lookup"><span data-stu-id="ed95c-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="ed95c-120">在向导中添加用户</span><span class="sxs-lookup"><span data-stu-id="ed95c-120">Add users in the wizard</span></span>

<span data-ttu-id="ed95c-121">你在向导中添加的所有用户都将自动分配一个 Microsoft 365 商业标准版许可证。</span><span class="sxs-lookup"><span data-stu-id="ed95c-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="ed95c-p104">如果你的 Microsoft 365 商业标准版订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="ed95c-p104">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="ed95c-p105">添加用户之后，还将显示与添加的新用户共享凭据的选项。可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="ed95c-p105">After you've added the users, you'll also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="ed95c-126">连接你的域</span><span class="sxs-lookup"><span data-stu-id="ed95c-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="ed95c-127">如果你选择使用 .onmicrosoft 域或使用 Azure AD Connect 设置用户，将不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="ed95c-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="ed95c-128">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="ed95c-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="ed95c-129">安装向导通常将检测你的注册机构，并提供更新注册机构网站上 NS 记录分步说明的链接。</span><span class="sxs-lookup"><span data-stu-id="ed95c-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="ed95c-130">如果没有，请[将名称服务器更改为使用任意域名注册机构设置 Office 365](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="ed95c-131">如果你有现有的 DNS 记录（例如现有网站），但你的 DNS 主机已启用 [domain connect](/office365/admin/get-help-with-domains/domain-connect)，请选择“**为我添加记录**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="ed95c-132">在“**选择联机服务**”页面上，接受所有默认设置，选择“**下一步**”，然后在DNS 主机页面上选择“**授权**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="ed95c-p108">如果具有具有其他 DNS 主机的现有 DNS 记录（未对域连接启用），需要管理自己的 DNS 记录以确保现有服务保持连接。有关详细信息，请参阅[域基础知识](/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-p108">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected. See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="ed95c-135">请按照向导中的步骤进行操作，然后将为你设置电子邮件和其他服务。</span><span class="sxs-lookup"><span data-stu-id="ed95c-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="ed95c-136">注册过程完成后，你将转到管理中心，按照向导安装 Office 应用、添加域、添加用户和分配许可证。</span><span class="sxs-lookup"><span data-stu-id="ed95c-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="ed95c-137">完成初始设置后，可使用管理中心中的“**设置**”页面，继续设置和配置订阅附带的服务。</span><span class="sxs-lookup"><span data-stu-id="ed95c-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="ed95c-138">有关设置向导和管理中心“**设置**”页面的详细信息，请参阅 [设置向导和设置页面之间的区别](o365-setup-wizard-and-setup-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="ed95c-139">完成设置</span><span class="sxs-lookup"><span data-stu-id="ed95c-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="ed95c-140">设置 Outlook，使用电子邮件功能</span><span class="sxs-lookup"><span data-stu-id="ed95c-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="ed95c-141">在 Windows“开始”菜单上，搜索并选择“Outlook”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="ed95c-142">（如果使用的是 Mac，请从工具栏打开 Outlook 或使用 Finder 进行查找。）</span><span class="sxs-lookup"><span data-stu-id="ed95c-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="ed95c-143">如果刚刚安装了 Outlook，请在欢迎页面上选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="ed95c-144">选择“**文件**”\>“**信息**”\>“**添加帐户**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="ed95c-145">输入你的 Microsoft 电子邮件地址并选择“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-145">Enter your Microsoft email address and select **Connect**.</span></span>

## <a name="watch-set-up-outlook-for-email"></a><span data-ttu-id="ed95c-146">观看：设置 Outlook，以使用电子邮件功能</span><span class="sxs-lookup"><span data-stu-id="ed95c-146">Watch: Set up Outlook for email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="ed95c-147">请参阅[设置 Outlook，使用电子邮件功能](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)，了解有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed95c-147">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="ed95c-148">使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="ed95c-148">Import email</span></span>

<span data-ttu-id="ed95c-149">如果通过另一电子邮件帐户使用 Outlook，可将之前的电子邮件、日历和联系人导入新的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="ed95c-149">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="ed95c-150">**导出旧的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="ed95c-150">**Export your old email**</span></span>

    <span data-ttu-id="ed95c-151">在 Outlook 中，选择“**文件**”\>“**打开并导出**”\>“**导入/导出**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-151">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="ed95c-152">选择“**导出到文件**”，然后按照以下步骤导出 Outlook 数据文件 (.pst) 和任何子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ed95c-152">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="ed95c-153">**导入旧的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="ed95c-153">**Import your old email**</span></span>

    <span data-ttu-id="ed95c-154">在 Outlook 中，再次选择“**文件**”\>“**打开并导出**”\>>“**导入/导出**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-154">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="ed95c-155">这一次，选择“**从另一程序或文件导入**”并按照以下步骤导入“导出旧的电子邮件”时创建的备份文件。</span><span class="sxs-lookup"><span data-stu-id="ed95c-155">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

## <a name="watch-import-and-redirect-email"></a><span data-ttu-id="ed95c-156">观看：导入和重定向电子邮件</span><span class="sxs-lookup"><span data-stu-id="ed95c-156">Watch: Import and redirect email</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="ed95c-157">请参阅[使用 Outlook 导入电子邮件](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)，了解有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed95c-157">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="ed95c-158">还可以使用 Exchange 管理中心导入每个人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed95c-158">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="ed95c-159">有关详细信息，请参阅[迁移多个电子邮件帐户](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="ed95c-159">For more information, see [migrate multiple email accounts](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="ed95c-160">使用公共网站</span><span class="sxs-lookup"><span data-stu-id="ed95c-160">Use a public website</span></span>

<span data-ttu-id="ed95c-161">Microsoft 365 不提供适用于公司的公共网站。</span><span class="sxs-lookup"><span data-stu-id="ed95c-161">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="ed95c-162">如需设置一个公共网站，请考虑使用 GoDaddy 或 WIX 等 Microsoft 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="ed95c-162">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="ed95c-163">从管理中心，转到“**资源**”，然后选择“**公共网站**”。</span><span class="sxs-lookup"><span data-stu-id="ed95c-163">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="ed95c-164">在其中一个选项下选择“**了解详细信息**”，然后注册网站合作伙伴，并使用其工具设置和设计你的网站。</span><span class="sxs-lookup"><span data-stu-id="ed95c-164">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

## <a name="watch-create-your-business-website"></a><span data-ttu-id="ed95c-165">观看：创建企业网站</span><span class="sxs-lookup"><span data-stu-id="ed95c-165">Watch: Create your business website</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a><span data-ttu-id="ed95c-166">相关内容</span><span class="sxs-lookup"><span data-stu-id="ed95c-166">Related content</span></span>

<span data-ttu-id="ed95c-167">[创建网站](../../business-video/create-web-site.md)（视频）</span><span class="sxs-lookup"><span data-stu-id="ed95c-167">[Create a website](../../business-video/create-web-site.md) (video)</span></span>\
<span data-ttu-id="ed95c-168">[适用于你的企业的 Microsoft 365](../../business-video/index.yml)（链接页面）</span><span class="sxs-lookup"><span data-stu-id="ed95c-168">[Microsoft 365 for your business](../../business-video/index.yml) (link page)</span></span>
