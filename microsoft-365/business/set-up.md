---
title: 设置 Microsoft 365 商业高级版
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解适用于用户Microsoft 365 商业高级版步骤，包括添加域和用户、设置安全策略等。
ms.openlocfilehash: 37607b483686fc12ac6253ae9f693ec86c073c4e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245036"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="f839b-103">在Microsoft 365 商业高级版向导中设置网站</span><span class="sxs-lookup"><span data-stu-id="f839b-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="f839b-104">观看此视频，大致了解Microsoft 365 商业高级版设置。</span><span class="sxs-lookup"><span data-stu-id="f839b-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="f839b-105">添加域、用户和设置策略</span><span class="sxs-lookup"><span data-stu-id="f839b-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="f839b-106">购买Microsoft 365 商业高级版时，可以选择使用你拥有的域，或在注册期间购买[一个](sign-up.md)域。</span><span class="sxs-lookup"><span data-stu-id="f839b-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="f839b-107">如果你在注册时购买了新域，则域已全部设置好，你可以继续[添加用户并分配许可证](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f839b-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="f839b-108">添加你的域以个性化设置登录名</span><span class="sxs-lookup"><span data-stu-id="f839b-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="f839b-109">使用全局管理员凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f839b-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="f839b-110">选择“**转到设置**”以启动向导。</span><span class="sxs-lookup"><span data-stu-id="f839b-110">Choose **Go to setup** to start the wizard.</span></span>

    ![选择"转到设置"。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="f839b-112">在“**安装 Office 应用**”页面上，可选择在自己的计算机上安装应用。</span><span class="sxs-lookup"><span data-stu-id="f839b-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="f839b-113">在“**添加域**”步骤中，输入要使用的域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="f839b-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f839b-114">如果你在注册期间购买了域，则此处不会看到“**添加域**”步骤。</span><span class="sxs-lookup"><span data-stu-id="f839b-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="f839b-115">转到“[添加用户](#add-users-and-assign-licenses)”。</span><span class="sxs-lookup"><span data-stu-id="f839b-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    !["个性化您的登录"页面的屏幕截图。](../media/adddomain.png)

    
4. <span data-ttu-id="f839b-117">按照向导中的步骤，在验证您是否拥有该域的任何 DNS Microsoft 365创建[DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)记录。</span><span class="sxs-lookup"><span data-stu-id="f839b-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="f839b-118">如果你知道域主机，另请参阅[主机特定说明](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="f839b-118">If you know your domain host, see also the [host specific instructions](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="f839b-119">如果你的托管服务提供商是 GoDaddy 或启用了 [domain connect](/office365/admin/get-help-with-domains/domain-connect) 的其他主机，则此过程很简单，系统会自动要求你登录并让 Microsoft 代表你进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f839b-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy“确认访问”页面上，选择“授权”。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="f839b-121">添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="f839b-121">Add users and assign licenses</span></span>

<span data-ttu-id="f839b-122">你可以在向导中添加用户，但你也可以[以后在管理中心添加用户](../admin/add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="f839b-122">You can add users in the wizard, but you can also [add users later](../admin/add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="f839b-123">此外，如果你具有本地域控制器，则可以使用 [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express) 添加用户。</span><span class="sxs-lookup"><span data-stu-id="f839b-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="f839b-124">在向导中添加用户</span><span class="sxs-lookup"><span data-stu-id="f839b-124">Add users in the wizard</span></span>

<span data-ttu-id="f839b-125">在向导中添加的任何用户都会自动获得Microsoft 365 商业高级版许可证。</span><span class="sxs-lookup"><span data-stu-id="f839b-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![向导中"添加新用户"页面的屏幕截图](../media/addnewuserspage.png)

1. <span data-ttu-id="f839b-127">如果你Microsoft 365 商业高级版订阅的现有用户 (，例如，如果你已使用 Azure AD 连接) ，则你现在可以选择为其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="f839b-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="f839b-128">继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="f839b-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="f839b-129">在你添加用户后，还将显示与添加的新用户共享凭据的选项。</span><span class="sxs-lookup"><span data-stu-id="f839b-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="f839b-130">可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="f839b-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="f839b-131">连接你的域</span><span class="sxs-lookup"><span data-stu-id="f839b-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="f839b-132">如果你选择使用 .onmicrosoft 域或使用 Azure AD Connect 设置用户，将不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="f839b-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="f839b-133">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="f839b-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="f839b-134">安装向导通常将检测你的注册机构，并提供更新注册机构网站上 NS 记录分步说明的链接。</span><span class="sxs-lookup"><span data-stu-id="f839b-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="f839b-135">如果没有，请更改[名称服务器以设置Microsoft 365注册机构的名称](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。</span><span class="sxs-lookup"><span data-stu-id="f839b-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md).</span></span> 

    - <span data-ttu-id="f839b-136">如果你有现有的 DNS 记录（例如现有网站），但你的 DNS 主机已启用 [domain connect](/office365/admin/get-help-with-domains/domain-connect)，请选择“**为我添加记录**”。</span><span class="sxs-lookup"><span data-stu-id="f839b-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="f839b-137">在“**选择联机服务**”页面上，接受所有默认设置，选择“**下一步**”，然后在DNS 主机页面上选择“**授权**”。</span><span class="sxs-lookup"><span data-stu-id="f839b-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="f839b-138">如果你具有用于其他 DNS 主机的现有 DNS 记录（未启用 domain connect），则需要管理自己的 DNS 记录以确保现有服务保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="f839b-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="f839b-139">有关详细信息，请参阅[域基础知识](/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="f839b-139">See [domain basics](/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        !["激活记录"页。](../media/activaterecords.png)

2. <span data-ttu-id="f839b-141">请按照向导中的步骤进行操作，然后将为你设置电子邮件和其他服务。</span><span class="sxs-lookup"><span data-stu-id="f839b-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="f839b-142">保护组织</span><span class="sxs-lookup"><span data-stu-id="f839b-142">Protect your organization</span></span> 

<span data-ttu-id="f839b-143">在向导中设置的策略将自动应用于名为 ["](/office365/admin/create-groups/compare-groups#security-groups) 所有用户" *的安全组*。</span><span class="sxs-lookup"><span data-stu-id="f839b-143">The policies you set up in the wizard are applied automatically to a [Security group](/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="f839b-144">还可以创建其他组，以在管理中心向分配策略。</span><span class="sxs-lookup"><span data-stu-id="f839b-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="f839b-145">在 **"增强对高级** 网络威胁的保护"上，建议你接受默认设置，Office 365 [高级](../security/office-365-security/defender-for-office-365.md)威胁防护扫描应用中的文件和Office链接。</span><span class="sxs-lookup"><span data-stu-id="f839b-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](../security/office-365-security/defender-for-office-365.md) scan files and links in Office apps.</span></span>

    !["增强保护"页面的屏幕截图。](../media/increasetreatprotection.png)


2. <span data-ttu-id="f839b-147">在"防止泄露敏感数据"页上，接受默认设置以启用 Office 365 数据丢失防护 (DLP) ，以跟踪 Office 应用中的敏感数据并防止在组织外部意外共享这些数据。</span><span class="sxs-lookup"><span data-stu-id="f839b-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="f839b-148">On the **Protect data in Office for mobile** page， leave mobile app management on， expand the settings and review them， and then select Create mobile app management **policy**.</span><span class="sxs-lookup"><span data-stu-id="f839b-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Screenshot of Protect data in Office for mobile page.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="f839b-150">保护 Windows 10 电脑</span><span class="sxs-lookup"><span data-stu-id="f839b-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="f839b-151">在左侧导航上，选择"**设置**"，然后在"登录和安全"下，选择"保护 **Windows 10计算机"。**</span><span class="sxs-lookup"><span data-stu-id="f839b-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="f839b-152">选择 **"视图** "开始。</span><span class="sxs-lookup"><span data-stu-id="f839b-152">Choose **View** to get started.</span></span> <span data-ttu-id="f839b-153">请参阅[保护Windows 10](secure-win-10-pcs.md)计算机，了解完整说明。</span><span class="sxs-lookup"><span data-stu-id="f839b-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="f839b-154">部署Office 365客户端应用</span><span class="sxs-lookup"><span data-stu-id="f839b-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="f839b-155">如果选择在安装过程中自动安装 Office 应用，则当用户使用工作凭据从 Windows 设备登录 Azure AD 后，这些应用将安装在 Windows 10 设备上。</span><span class="sxs-lookup"><span data-stu-id="f839b-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="f839b-156">若要在Office iOS 或 Android 设备上安装设备，请参阅为用户[Microsoft 365 商业高级版移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="f839b-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="f839b-157">也可以单独安装Office安装。</span><span class="sxs-lookup"><span data-stu-id="f839b-157">You can also install Office individually.</span></span> <span data-ttu-id="f839b-158">有关[说明Office，请参阅在电脑或 Mac 上](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)安装设备。</span><span class="sxs-lookup"><span data-stu-id="f839b-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f839b-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f839b-159">See also</span></span>

[<span data-ttu-id="f839b-160">Microsoft 365 商业版培训视频</span><span class="sxs-lookup"><span data-stu-id="f839b-160">Microsoft 365 for business training videos</span></span>](../business-video/index.yml)
