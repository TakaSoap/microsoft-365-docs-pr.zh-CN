---
title: 设置 Microsoft 365 商业版
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660721"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="9419c-103">设置 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="9419c-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="9419c-104">在开始之前, 请参阅[获取 Microsoft 365 商业](get-microsoft-365-business.md)版以获取注册详细信息。</span><span class="sxs-lookup"><span data-stu-id="9419c-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="9419c-105">观看有关如何使用设置向导以及当你没有本地 Active Directory 时[如何设置 Microsoft 365 商业版的简短视频](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1)</span><span class="sxs-lookup"><span data-stu-id="9419c-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="9419c-106">概述</span><span class="sxs-lookup"><span data-stu-id="9419c-106">Overview</span></span>

<span data-ttu-id="9419c-107">大部分设置步骤可以在安装向导中完成, 但也会列出其他选项。</span><span class="sxs-lookup"><span data-stu-id="9419c-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="9419c-108">[添加你的域](#add-your-domain-to-personalize-sign-in)(如果你在[注册](sign-up.md)期间购买了你的域, 则此步骤已完成。)</span><span class="sxs-lookup"><span data-stu-id="9419c-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="9419c-109">添加用户。</span><span class="sxs-lookup"><span data-stu-id="9419c-109">Add users.</span></span> <span data-ttu-id="9419c-110">可以通过以下三种方式之一执行此操作:</span><span class="sxs-lookup"><span data-stu-id="9419c-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="9419c-111">在[安装向导](#add-users-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="9419c-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="9419c-112">如果你有本地 Active directory, 请使用目录同步来[使用 AZURE AD Connect 添加用户](#add-users-by-using-azure-ad-connect)。</span><span class="sxs-lookup"><span data-stu-id="9419c-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="9419c-113">您还可以在随后的管理中心[添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="9419c-114">设置安全策略和配置设备。</span><span class="sxs-lookup"><span data-stu-id="9419c-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="9419c-115">可以通过以下三种方式之一执行此操作:</span><span class="sxs-lookup"><span data-stu-id="9419c-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="9419c-116">在[安装向导](#set-up-policies-in-the-wizard)中。</span><span class="sxs-lookup"><span data-stu-id="9419c-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="9419c-117">在[管理中心](#modify-or-add-policies-in-the-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="9419c-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="9419c-118">在[Intune 管理中心](https://docs.microsoft.com/intune/what-is-device-management)中。</span><span class="sxs-lookup"><span data-stu-id="9419c-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="9419c-119">设置和管理 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="9419c-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="9419c-120">将 WIndows 10 设备加入 Azure AD 时, 所有策略都将应用于它。</span><span class="sxs-lookup"><span data-stu-id="9419c-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="9419c-121">在[安装向导](#set-up-policies-in-the-wizard)中设置 Windows 10 设备配置。</span><span class="sxs-lookup"><span data-stu-id="9419c-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="9419c-122">将[新的 Windows 10 设备](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device)加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9419c-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="9419c-123">将[现有 Windows 10 设备](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro)加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9419c-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="9419c-124">安装 Office 365 商业版。</span><span class="sxs-lookup"><span data-stu-id="9419c-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="9419c-125">您可以使用[安装向导](#set-up-policies-in-the-wizard)在 Windows 设备中自动安装 Office。</span><span class="sxs-lookup"><span data-stu-id="9419c-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="9419c-126">从管理中心自动[安装 Office](auto-install-or-uninstall-office.md) 。</span><span class="sxs-lookup"><span data-stu-id="9419c-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="9419c-127">允许用户安装适用于 Windows 和设备的[Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications)。</span><span class="sxs-lookup"><span data-stu-id="9419c-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="9419c-128">设置其他安全性。</span><span class="sxs-lookup"><span data-stu-id="9419c-128">Set up additional security.</span></span>
    - <span data-ttu-id="9419c-129">安装向导添加策略以保护设备, 但您也可以利用[其他安全](#additional-security-settings)功能来帮助保护您的数据、帐户和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9419c-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="9419c-130">添加你的域、用户并设置策略</span><span class="sxs-lookup"><span data-stu-id="9419c-130">Add your domain, users and set up policies</span></span>

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

<span data-ttu-id="9419c-132">在购买 Microsoft 365 商业版时, 您可以选择使用自己的域, 也可以在[注册](sign-up.md)过程中购买一个域。</span><span class="sxs-lookup"><span data-stu-id="9419c-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="9419c-133">如果你在注册时购买了一个新域, 你的域将全部设置, 并且你可以移动以[添加用户并分配许可证](#add-users-and-assign-licenses)。</span><span class="sxs-lookup"><span data-stu-id="9419c-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="9419c-134">添加你的域以个性化登录</span><span class="sxs-lookup"><span data-stu-id="9419c-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="9419c-135">使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="9419c-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="9419c-136">选择 "**添加域**" 以启动向导。</span><span class="sxs-lookup"><span data-stu-id="9419c-136">Choose **Add a domain** to start the wizard.</span></span>

    ![选择 "添加域"。](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="9419c-138">在向导中, 输入要使用的域名 (如 contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="9419c-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![自定义登录页的屏幕截图。](media/personalizesignin.png)

    
4. <span data-ttu-id="9419c-140">按照向导中的步骤在[适用于 Office 365 的任何 dns 托管提供程序中创建 dns 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), 以验证您是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="9419c-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="9419c-141">如果你知道你的域主机, 请参阅[特定主机说明](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。</span><span class="sxs-lookup"><span data-stu-id="9419c-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="9419c-142">如果您的托管提供商为 GoDaddy, 则该过程非常简单, 您将自动要求您登录并让 Microsoft 代表你进行身份验证:</span><span class="sxs-lookup"><span data-stu-id="9419c-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![在 GoDaddy "确认访问" 页上, 选择 "授权"。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="9419c-144">添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="9419c-144">Add users and assign licenses</span></span>

<span data-ttu-id="9419c-145">你可以在向导中添加用户, 但你也可以[稍后在管理中心添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="9419c-146">此外, 如果您有一个本地域控制器, 则可以使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)添加用户。</span><span class="sxs-lookup"><span data-stu-id="9419c-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="9419c-147">在向导中添加用户</span><span class="sxs-lookup"><span data-stu-id="9419c-147">Add users in the wizard</span></span>

<span data-ttu-id="9419c-148">在向导中添加的任何用户都会自动分配 Microsoft 365 商业版许可证。</span><span class="sxs-lookup"><span data-stu-id="9419c-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="9419c-149">如果你有一个本地域控制器, 并且正在使用 Active Directory, 请参阅 how [to ddd users by Using AZURE AD Connect](#add-users-by-using-azure-ad-connect)。</span><span class="sxs-lookup"><span data-stu-id="9419c-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![向导中的 "添加新用户" 页的屏幕截图](media/addnewuserspage.png)

1. <span data-ttu-id="9419c-p106">如果你的 Microsoft 365 商业版 订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="9419c-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="9419c-153">添加用户后, 您还将获得一个选项, 用于与添加的新用户共享凭据。</span><span class="sxs-lookup"><span data-stu-id="9419c-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="9419c-154">可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="9419c-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="9419c-155">跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9419c-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="9419c-156">如果要从另一个电子邮件提供商处进行移动, 并在以后复制数据, 则可以将[电子邮件和联系人迁移到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。</span><span class="sxs-lookup"><span data-stu-id="9419c-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="9419c-157">使用 Azure AD Connect 添加用户</span><span class="sxs-lookup"><span data-stu-id="9419c-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="9419c-158">如果您有一个包含 Active Directory 的本地域控制器, 则使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)将用户与 Microsoft 365 业务同步。</span><span class="sxs-lookup"><span data-stu-id="9419c-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="9419c-159">完成此过程后, 再启动安装向导。</span><span class="sxs-lookup"><span data-stu-id="9419c-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="9419c-160">您可以在管理中心下载:</span><span class="sxs-lookup"><span data-stu-id="9419c-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="9419c-161">转到 "**用户** \> **活动用户**", 选择页面顶部的省略号, 然后选择 "**目录同步**" 以下载 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="9419c-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![在 "活动用户" 页上, 选择省略号 > Directory snchronization。](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="9419c-163">如果以这种方式创建用户, 则仍必须在管理中心将许可证分配给这些用户。</span><span class="sxs-lookup"><span data-stu-id="9419c-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="9419c-164">继续访问加入域的应用和设备</span><span class="sxs-lookup"><span data-stu-id="9419c-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="9419c-165">如果要继续访问加入域的应用和设备, 请阅读以下文章以两种不同的方式启用:</span><span class="sxs-lookup"><span data-stu-id="9419c-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="9419c-166">启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="9419c-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="9419c-167">建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="9419c-167">This is the recommended way.</span></span>

- [<span data-ttu-id="9419c-168">从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源</span><span class="sxs-lookup"><span data-stu-id="9419c-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="9419c-169">连接你的域</span><span class="sxs-lookup"><span data-stu-id="9419c-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="9419c-170">如果选择使用 .onmicrosoft 域或使用的 Azure AD Connect 设置用户, 则不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="9419c-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="9419c-171">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="9419c-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="9419c-172">设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="9419c-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="9419c-173">如果不是, 请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。</span><span class="sxs-lookup"><span data-stu-id="9419c-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="9419c-174">如果您有现有的 DNS 记录 (例如现有网站), 您需要管理自己的 DNS 记录, 以确保现有服务保持连接。</span><span class="sxs-lookup"><span data-stu-id="9419c-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="9419c-175">有关详细信息, 请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。</span><span class="sxs-lookup"><span data-stu-id="9419c-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![连接域页面, 我将管理自己的 DNS 记录。](media/connectyourdomainpage.png)

2. <span data-ttu-id="9419c-177">按照向导中的步骤进行操作, 将为你设置电子邮件和其他服务。</span><span class="sxs-lookup"><span data-stu-id="9419c-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="9419c-178">设置安全策略和设备配置</span><span class="sxs-lookup"><span data-stu-id="9419c-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="9419c-179">如果您决定向一组用户分配不同的策略, 则这些策略适用于您向其授予许可证的每个用户或向一组用户。</span><span class="sxs-lookup"><span data-stu-id="9419c-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="9419c-180">在向导中设置策略</span><span class="sxs-lookup"><span data-stu-id="9419c-180">Set up policies in the wizard</span></span>

<span data-ttu-id="9419c-181">在向导中设置的策略将自动应用于名为 "*所有用户*" 的[安全组](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。</span><span class="sxs-lookup"><span data-stu-id="9419c-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="9419c-182">在**移动设备上保护你的工作文件**。默认情况下, 选择 "在**设备丢失或被盗时保护工作文件**" 选项。</span><span class="sxs-lookup"><span data-stu-id="9419c-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="9419c-183">你可以选择启用 "**管理用户如何在移动设备上访问 Office 文件**", 并建议这样做。</span><span class="sxs-lookup"><span data-stu-id="9419c-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    !["移动设备上的保护工作文件" 页的屏幕截图。](media/protectworkfilesondevices.png)

     - <span data-ttu-id="9419c-185">如果在**设备丢失或被盗时扩展了保护工作文件**, 则将预先选择[默认值](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="9419c-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![用于保护丢失设备上的文件的默认值的屏幕截图。](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="9419c-187">如果选择 "**管理用户如何在移动设备上访问 Office 文件**并展开", 将显示[默认值](manage-user-access-on-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="9419c-188">建议在设置过程中接受默认值，创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="9419c-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="9419c-189">在设置完成后，可以创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="9419c-189">You can create more policies after setup completes.</span></span>

        ![移动时 Office 文件的保护设置的屏幕截图。](media/useraccessonmobile.png)

2. <span data-ttu-id="9419c-191">"保护数据和设备" 的最后一步是, 设置策略以保护 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="9419c-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="9419c-192">当用户的 Windows 10 连接到您的组织时, 这些设置会自动应用。</span><span class="sxs-lookup"><span data-stu-id="9419c-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="9419c-193">您可以展开**安全 Windows 10 设备**, 以查看和修改[默认值](secure-windows-10-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="9419c-194">你也可以选择在 Windows 10 设备上[自动安装 Office](install-office-on-windows-10-during-setup.md) 。</span><span class="sxs-lookup"><span data-stu-id="9419c-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    !["设置 Windows 10 设备配置" 页的屏幕截图。](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="9419c-196">在管理中心中修改或添加策略</span><span class="sxs-lookup"><span data-stu-id="9419c-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="9419c-197">请参阅[管理 Microsoft 365 商业](manage.md)版, 了解有关如何查看和修改设备和应用保护策略以及如何从或重置用户设备中删除数据的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="9419c-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="9419c-198">部署和管理 Windows 10</span><span class="sxs-lookup"><span data-stu-id="9419c-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="9419c-199">请参阅为[Microsoft 365 商业用户设置 Windows 设备](set-up-windows-devices.md)以在安装新计算机的过程中手动连接到 Azure AD, 或更改现有计算机的登录配置文件。</span><span class="sxs-lookup"><span data-stu-id="9419c-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="9419c-200">使用 Autopilot 设置新设备</span><span class="sxs-lookup"><span data-stu-id="9419c-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="9419c-201">可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置**新**的 Windows 10 设备, 但更易于获取可为您执行此操作的[合作伙伴](https://www.microsoft.com/solution-providers/search)。</span><span class="sxs-lookup"><span data-stu-id="9419c-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="9419c-202">你也可以转到[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)并咨询云技术专家, 以设置你购买的新设备。</span><span class="sxs-lookup"><span data-stu-id="9419c-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="9419c-203">访问本地资源</span><span class="sxs-lookup"><span data-stu-id="9419c-203">Access on-premises resources</span></span>

<span data-ttu-id="9419c-204">如果您的组织使用的是本地 Windows Server Active Directory, 则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备, 同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9419c-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="9419c-205">按照 Microsoft 365 商业版中的 "[启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作, 以便对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="9419c-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="9419c-206">这是此状态的首选方法, 称为混合 Azure AD 加入的设备。</span><span class="sxs-lookup"><span data-stu-id="9419c-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="9419c-207">如果你的企业有包含某些本地资源 (如文件共享和打印机) 的本地 Active Directory, 则可以执行以下步骤, 为 Azure AD 联接的设备提供对这些资源的访问权限:[从访问本地资源Microsoft 365 商业版中的 Azure AD 加入设备](access-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="9419c-208">部署 Office 365 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="9419c-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="9419c-209">如果你选择在设置过程中自动安装 Office 应用, 则在用户使用其工作凭据从 Windows 设备登录到 Azure AD 之后, 应用将在 Windows 10 设备上安装。</span><span class="sxs-lookup"><span data-stu-id="9419c-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="9419c-210">若要在移动 iOS 或 Android 设备上安装 Office, 请参阅[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="9419c-211">您也可以单独安装 Office。</span><span class="sxs-lookup"><span data-stu-id="9419c-211">You can also install Office individually.</span></span> <span data-ttu-id="9419c-212">有关说明, 请参阅[在电脑或 Mac 上安装 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) 。</span><span class="sxs-lookup"><span data-stu-id="9419c-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="9419c-213">其他安全设置</span><span class="sxs-lookup"><span data-stu-id="9419c-213">Additional security settings</span></span>

<span data-ttu-id="9419c-214">除了 "安装向导" 中的 "安全性和合规性" 设置之外, 您还可以设置以下附加设置:</span><span class="sxs-lookup"><span data-stu-id="9419c-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="9419c-215">**电子邮件恶意软件保护**</span><span class="sxs-lookup"><span data-stu-id="9419c-215">**Email malware protection**</span></span>
- <span data-ttu-id="9419c-216">**高级威胁防护 (ATP) 安全附件**</span><span class="sxs-lookup"><span data-stu-id="9419c-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="9419c-217">**ATP 安全链接**</span><span class="sxs-lookup"><span data-stu-id="9419c-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="9419c-218">**APT. 反网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="9419c-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="9419c-219">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="9419c-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="9419c-220">**数据丢失防护 (DLP)**</span><span class="sxs-lookup"><span data-stu-id="9419c-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="9419c-221">**Azure 信息保护**(计划 1)</span><span class="sxs-lookup"><span data-stu-id="9419c-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="9419c-222">**Intune 门户可用性**</span><span class="sxs-lookup"><span data-stu-id="9419c-222">**Intune portal availability**</span></span>

<span data-ttu-id="9419c-223">若要开始, 请[设置高级安全策略](set-up-advanced-security.md)。</span><span class="sxs-lookup"><span data-stu-id="9419c-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="9419c-224">请参阅[保护 Microsoft 365 业务的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), 以获得最佳安全实践的路线图。</span><span class="sxs-lookup"><span data-stu-id="9419c-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>