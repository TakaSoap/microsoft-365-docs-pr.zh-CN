---
title: 设置 Microsoft 365 商业版
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解如何设置 Microsoft 365 商业版。
ms.openlocfilehash: ac9c8b828ff131a15bf057fa8bdc0bf56dd00987
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772559"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="fc462-103">在安装向导中设置 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="fc462-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="fc462-104">添加你的域、用户并设置策略</span><span class="sxs-lookup"><span data-stu-id="fc462-104">Add your domain, users, and set up policies</span></span>

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

<span data-ttu-id="fc462-106">在购买 Microsoft 365 商业版时, 您可以选择使用自己的域, 也可以在[注册](sign-up.md)过程中购买一个域。</span><span class="sxs-lookup"><span data-stu-id="fc462-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="fc462-107">如果你在注册时购买了一个新域, 你的域将全部设置, 并且你可以移动以[添加用户并分配许可证](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="fc462-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="fc462-108">添加你的域以个性化登录</span><span class="sxs-lookup"><span data-stu-id="fc462-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="fc462-109">使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="fc462-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="fc462-110">选择 "**添加域**" 或 "**添加用户**" 启动向导。</span><span class="sxs-lookup"><span data-stu-id="fc462-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="fc462-111">如果你在注册过程中购买了一个域, 你将不会在此处看到 "**添加域**" 步骤。</span><span class="sxs-lookup"><span data-stu-id="fc462-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="fc462-112">改为转到 "[添加用户](#add-users-and-assign-licenses)"。</span><span class="sxs-lookup"><span data-stu-id="fc462-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![选择 "添加域"。](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="fc462-114">在向导中, 输入要使用的域名 (如 contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="fc462-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![自定义登录页的屏幕截图。](media/personalizesignin.png)

    
4. <span data-ttu-id="fc462-116">按照向导中的步骤在[适用于 Office 365 的任何 dns 托管提供程序中创建 dns 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), 以验证您是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="fc462-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="fc462-117">如果你知道你的域主机, 请参阅[特定主机说明](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="fc462-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="fc462-118">如果您的托管提供商为 GoDaddy, 则该过程非常简单, 您将自动要求您登录并让 Microsoft 代表你进行身份验证:</span><span class="sxs-lookup"><span data-stu-id="fc462-118">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![在 GoDaddy "确认访问" 页上, 选择 "授权"。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="fc462-120">添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="fc462-120">Add users and assign licenses</span></span>

<span data-ttu-id="fc462-121">你可以在向导中添加用户, 但你也可以[稍后在管理中心添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="fc462-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="fc462-122">此外, 如果您有一个本地域控制器, 则可以使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)添加用户。</span><span class="sxs-lookup"><span data-stu-id="fc462-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="fc462-123">在向导中添加用户</span><span class="sxs-lookup"><span data-stu-id="fc462-123">Add users in the wizard</span></span>

<span data-ttu-id="fc462-124">在向导中添加的任何用户都会自动分配 Microsoft 365 商业版许可证。</span><span class="sxs-lookup"><span data-stu-id="fc462-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![向导中的 "添加新用户" 页的屏幕截图](media/addnewuserspage.png)

1. <span data-ttu-id="fc462-126">如果你的 Microsoft 365 业务订阅具有现有用户 (例如, 如果你使用的是 Azure AD Connect), 你将获得一个选项, 用于立即向其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="fc462-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="fc462-127">继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="fc462-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="fc462-128">添加用户后, 您还将获得一个选项, 用于与添加的新用户共享凭据。</span><span class="sxs-lookup"><span data-stu-id="fc462-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="fc462-129">可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="fc462-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="fc462-130">跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fc462-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="fc462-131">如果要从另一个电子邮件提供商处进行移动, 并在以后复制数据, 则可以将[电子邮件和联系人迁移到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。</span><span class="sxs-lookup"><span data-stu-id="fc462-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="fc462-132">连接你的域</span><span class="sxs-lookup"><span data-stu-id="fc462-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="fc462-133">如果选择使用 .onmicrosoft 域或使用的 Azure AD Connect 设置用户, 则不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="fc462-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="fc462-134">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="fc462-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="fc462-135">设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="fc462-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="fc462-136">如果不是, 请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。</span><span class="sxs-lookup"><span data-stu-id="fc462-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="fc462-137">如果您有现有的 DNS 记录 (例如现有网站), 您需要管理自己的 DNS 记录, 以确保现有服务保持连接。</span><span class="sxs-lookup"><span data-stu-id="fc462-137">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="fc462-138">有关详细信息, 请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="fc462-138">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![连接域页面, 我将管理自己的 DNS 记录。](media/connectyourdomainpage.png)

2. <span data-ttu-id="fc462-140">按照向导中的步骤进行操作, 将为你设置电子邮件和其他服务。</span><span class="sxs-lookup"><span data-stu-id="fc462-140">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="fc462-141">设置安全策略和设备配置</span><span class="sxs-lookup"><span data-stu-id="fc462-141">Set up security policies and device configurations</span></span> 

<span data-ttu-id="fc462-142">在向导中设置的策略将自动应用于名为 "*所有用户*" 的[安全组](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。</span><span class="sxs-lookup"><span data-stu-id="fc462-142">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="fc462-143">您还可以在管理中心中创建其他组来分配策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-143">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="fc462-144">在**移动设备上保护你的工作文件**。默认情况下, 选择 "在**设备丢失或被盗时保护工作文件**" 选项。</span><span class="sxs-lookup"><span data-stu-id="fc462-144">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="fc462-145">你可以选择启用 "**管理用户如何在移动设备上访问 Office 文件**", 并建议这样做。</span><span class="sxs-lookup"><span data-stu-id="fc462-145">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    !["移动设备上的保护工作文件" 页的屏幕截图。](media/protectworkfilesondevices.png)

     - <span data-ttu-id="fc462-147">**当设备丢失或被盗时, 展开保护工作文件**以显示[默认值](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="fc462-147">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![用于保护丢失设备上的文件的默认值的屏幕截图。](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="fc462-149">选择 "**管理用户如何访问移动设备上的 Office 文件**并展开" 以显示[默认值](manage-user-access-on-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="fc462-149">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="fc462-150">建议您在安装过程中接受默认值, 以创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-150">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="fc462-151">在设置完成后，可以创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-151">You can create more policies after setup completes.</span></span>

        ![移动时 Office 文件的保护设置的屏幕截图。](media/useraccessonmobile.png)

2. <span data-ttu-id="fc462-153">"保护数据和设备" 的最后一步是, 设置策略以保护 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="fc462-153">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="fc462-154">当用户的 Windows 10 连接到您的组织时, 这些设置会自动应用。</span><span class="sxs-lookup"><span data-stu-id="fc462-154">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="fc462-155">您可以展开**安全 Windows 10 设备**, 以查看和修改[默认值](secure-windows-10-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="fc462-155">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="fc462-156">你也可以选择在 Windows 10 设备上[自动安装 Office](install-office-on-windows-10-during-setup.md) 。</span><span class="sxs-lookup"><span data-stu-id="fc462-156">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    !["设置 Windows 10 设备配置" 页的屏幕截图。](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="fc462-158">部署 Office 365 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fc462-158">Deploy Office 365 client apps</span></span>

<span data-ttu-id="fc462-159">如果你选择在设置过程中自动安装 Office 应用, 则在用户使用其工作凭据从 Windows 设备登录到 Azure AD 之后, 应用将在 Windows 10 设备上安装。</span><span class="sxs-lookup"><span data-stu-id="fc462-159">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="fc462-160">若要在移动 iOS 或 Android 设备上安装 Office, 请参阅[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="fc462-160">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="fc462-161">您也可以单独安装 Office。</span><span class="sxs-lookup"><span data-stu-id="fc462-161">You can also install Office individually.</span></span> <span data-ttu-id="fc462-162">有关说明, 请参阅[在电脑或 Mac 上安装 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) 。</span><span class="sxs-lookup"><span data-stu-id="fc462-162">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
