---
title: 设置 Microsoft 365 商业高级版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 发现 Microsoft 365 商业高级版的设置步骤，包括添加域和用户、设置安全策略等。
ms.openlocfilehash: 89186fbd00e47385f0320c45f7fc44c258742aa3
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785696"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="add11-103">在安装向导中设置 Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="add11-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="add11-104">观看此视频，了解 Microsoft 365 商业高级版安装程序的概述。</span><span class="sxs-lookup"><span data-stu-id="add11-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="add11-105">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="add11-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="add11-106">添加你的域、用户并设置策略</span><span class="sxs-lookup"><span data-stu-id="add11-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="add11-107">在购买 Microsoft 365 商业高级版时，您可以选择使用自己的域，也可以在[注册](sign-up.md)过程中购买一个域。</span><span class="sxs-lookup"><span data-stu-id="add11-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="add11-108">如果你在注册时购买了一个新域，你的域将全部设置，并且你可以移动以[添加用户并分配许可证](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="add11-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="add11-109">添加你的域以个性化登录</span><span class="sxs-lookup"><span data-stu-id="add11-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="add11-110">使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="add11-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="add11-111">选择 "**转到安装程序**" 以启动向导。</span><span class="sxs-lookup"><span data-stu-id="add11-111">Choose **Go to setup** to start the wizard.</span></span>

    ![选择 "转到安装程序"。](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="add11-113">在 "**安装 Office 应用程序**" 页上，您可以选择在自己的计算机上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="add11-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="add11-114">在 "**添加域**" 步骤中，输入要使用的域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="add11-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="add11-115">如果你在注册过程中购买了一个域，你将不会在此处看到 "**添加域**" 步骤。</span><span class="sxs-lookup"><span data-stu-id="add11-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="add11-116">改为转到 "[添加用户](#add-users-and-assign-licenses)"。</span><span class="sxs-lookup"><span data-stu-id="add11-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![自定义登录页的屏幕截图。](../media/adddomain.png)

    
4. <span data-ttu-id="add11-118">按照向导中的步骤在[适用于 Office 365 的任何 dns 托管提供程序中创建 dns 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，以验证您是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="add11-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="add11-119">如果你知道你的域主机，请参阅[特定主机说明](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="add11-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="add11-120">如果您的托管提供商是 GoDaddy 或另一台使用[域连接](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)启用的主机，则此过程非常简单，您将自动要求您登录并让 Microsoft 代表你进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="add11-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![在 GoDaddy "确认访问" 页上，选择 "授权"。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="add11-122">添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="add11-122">Add users and assign licenses</span></span>

<span data-ttu-id="add11-123">你可以在向导中添加用户，但你也可以[稍后在管理中心添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="add11-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="add11-124">此外，如果您有一个本地域控制器，则可以使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)添加用户。</span><span class="sxs-lookup"><span data-stu-id="add11-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="add11-125">在向导中添加用户</span><span class="sxs-lookup"><span data-stu-id="add11-125">Add users in the wizard</span></span>

<span data-ttu-id="add11-126">在向导中添加的任何用户都会自动分配 Microsoft 365 商业高级版许可证。</span><span class="sxs-lookup"><span data-stu-id="add11-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![向导中的 "添加新用户" 页的屏幕截图](../media/addnewuserspage.png)

1. <span data-ttu-id="add11-128">如果你的 Microsoft 365 商业高级订阅具有现有用户（例如，如果你使用的是 Azure AD Connect），你将获得一个选项，用于立即向其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="add11-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="add11-129">继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="add11-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="add11-130">添加用户后，您还将获得一个选项，用于与添加的新用户共享凭据。</span><span class="sxs-lookup"><span data-stu-id="add11-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="add11-131">可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="add11-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="add11-132">连接你的域</span><span class="sxs-lookup"><span data-stu-id="add11-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="add11-133">如果选择使用 .onmicrosoft 域或使用的 Azure AD Connect 设置用户，则不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="add11-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="add11-134">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="add11-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="add11-135">设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="add11-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="add11-136">如果不是，请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)。</span><span class="sxs-lookup"><span data-stu-id="add11-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="add11-137">如果您有现有的 DNS 记录（例如现有网站），但 DNS 主机启用了[域连接](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)，请选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="add11-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="add11-138">在 "**选择您的在线服务**" 页面上，接受所有默认设置，然后选择 "**下一步**"，然后在 DNS 主机的页面上选择 "**授权**"。</span><span class="sxs-lookup"><span data-stu-id="add11-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="add11-139">如果已有其他 DNS 主机的现有 DNS 记录（未启用域连接），则需要管理自己的 DNS 记录，以确保现有服务保持连接。</span><span class="sxs-lookup"><span data-stu-id="add11-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="add11-140">有关详细信息，请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="add11-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        !["激活记录" 页。](../media/activaterecords.png)

2. <span data-ttu-id="add11-142">按照向导中的步骤进行操作，将为你设置电子邮件和其他服务。</span><span class="sxs-lookup"><span data-stu-id="add11-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="add11-143">保护你的组织</span><span class="sxs-lookup"><span data-stu-id="add11-143">Protect your organization</span></span> 

<span data-ttu-id="add11-144">在向导中设置的策略将自动应用于名为 "*所有用户*" 的[安全组](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。</span><span class="sxs-lookup"><span data-stu-id="add11-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="add11-145">您还可以在管理中心中创建其他组来分配策略。</span><span class="sxs-lookup"><span data-stu-id="add11-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="add11-146">在 "**加强对高级网络威胁的保护**" 中，建议您接受默认值以允许[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)扫描 office 应用中的文件和链接。</span><span class="sxs-lookup"><span data-stu-id="add11-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![增强保护页面的屏幕截图。](../media/increasetreatprotection.png)


2. <span data-ttu-id="add11-148">在 "**防止泄漏敏感数据**" 页上，接受默认设置以启用 Office 365 数据丢失防护（DLP）以跟踪 office 应用程序中的敏感数据，并防止在组织外部的意外共享这些数据。</span><span class="sxs-lookup"><span data-stu-id="add11-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="add11-149">在 "**保护在移动 Office 中的数据**" 页面中，将移动应用管理保留在上，展开 "设置" 并查看它们，然后选择 "**创建移动应用管理策略**"。</span><span class="sxs-lookup"><span data-stu-id="add11-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Office for mobile 页面中保护数据的屏幕截图。](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="add11-151">保护 Windows 10 电脑</span><span class="sxs-lookup"><span data-stu-id="add11-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="add11-152">在左侧导航中，选择 "**设置**"，然后在 "**登录和安全**" 下，选择 "**保护 Windows 10 计算机**"。</span><span class="sxs-lookup"><span data-stu-id="add11-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="add11-153">选择 "**查看**" 即可开始。</span><span class="sxs-lookup"><span data-stu-id="add11-153">Choose **View** to get started.</span></span> <span data-ttu-id="add11-154">有关完整说明，请参阅[保护 Windows 10 计算机安全](secure-win-10-pcs.md)。</span><span class="sxs-lookup"><span data-stu-id="add11-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="add11-155">部署 Office 365 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="add11-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="add11-156">如果你选择在安装过程中自动安装 Office 应用，则在用户使用其工作凭据从 Windows 设备登录到 Azure AD 之后，应用将在 Windows 10 设备上安装。</span><span class="sxs-lookup"><span data-stu-id="add11-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="add11-157">若要在移动 iOS 或 Android 设备上安装 Office，请参阅[为 Microsoft 365 商业高级版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="add11-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="add11-158">您也可以单独安装 Office。</span><span class="sxs-lookup"><span data-stu-id="add11-158">You can also install Office individually.</span></span> <span data-ttu-id="add11-159">有关说明，请参阅[在电脑或 Mac 上安装 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 。</span><span class="sxs-lookup"><span data-stu-id="add11-159">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="add11-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="add11-160">See also</span></span>

[<span data-ttu-id="add11-161">Microsoft 365 商业版培训视频</span><span class="sxs-lookup"><span data-stu-id="add11-161">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
