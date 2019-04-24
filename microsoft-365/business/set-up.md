---
title: 使用安装向导安装 Microsoft 365 Business
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
description: 了解如何通过完成四个步骤来设置 Microsoft 365 商业版。
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283871"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="373da-103">使用安装向导安装 Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="373da-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="373da-104">完成下面的步骤1-4。</span><span class="sxs-lookup"><span data-stu-id="373da-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="373da-105">设置 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="373da-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="373da-106">如果你没有本地 Active Directory, 请观看有关如何设置 Microsoft 365 商业版的视频:</span><span class="sxs-lookup"><span data-stu-id="373da-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="373da-107">设置步骤包括包含本地 Active Directory 的设置的信息。</span><span class="sxs-lookup"><span data-stu-id="373da-107">The set-up steps include information for setups that include local Active Directory.</span></span> <span data-ttu-id="373da-108">如果要继续访问加入域的设备, 请阅读以下文章以两种不同的方式启用该命令, 并在运行安装向导之前完成这些步骤:</span><span class="sxs-lookup"><span data-stu-id="373da-108">If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="373da-109">启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="373da-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="373da-110">-建议采用此方法。</span><span class="sxs-lookup"><span data-stu-id="373da-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="373da-111">从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源</span><span class="sxs-lookup"><span data-stu-id="373da-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="373da-112">步骤 1: 个性化登录</span><span class="sxs-lookup"><span data-stu-id="373da-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="373da-p102">使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.microsoft.com)。选择" **管理**"图块，进入管理中心。</span><span class="sxs-lookup"><span data-stu-id="373da-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="373da-115">在管理中心内，选择" **开始设置**"（可能会看到" **继续设置**"，具体取决于所处的状态），启动向导。</span><span class="sxs-lookup"><span data-stu-id="373da-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="373da-116">输入要使用的域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="373da-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="373da-117">继续进行操作并输入你的域（即使在使用 Azure AD Connect（举例）时已验证过）。</span><span class="sxs-lookup"><span data-stu-id="373da-117">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example.</span></span> <span data-ttu-id="373da-118">如果您使用 Azure AD Connect 验证您的域, 则以下两个步骤不适用于您。</span><span class="sxs-lookup"><span data-stu-id="373da-118">The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="373da-119">按照向导中的步骤在[适用于 Office 365 的任何 dns 托管提供程序中创建 dns 记录](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166), 以验证您是否拥有该域。</span><span class="sxs-lookup"><span data-stu-id="373da-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="373da-120">您可以查看视频的示例视频[: 在新管理中心中设置 Office 365](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。</span><span class="sxs-lookup"><span data-stu-id="373da-120">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8).</span></span> <span data-ttu-id="373da-121">请注意，此视频不包括 Microsoft 365 商业版 的数据保护步骤。</span><span class="sxs-lookup"><span data-stu-id="373da-121">Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="373da-123">步骤 2: 添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="373da-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="373da-124">可通过此步骤添加用户，或稍后在管理中心[添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="373da-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="373da-125">添加的所有用户都会自动获得 Microsoft 365 商业版 许可。</span><span class="sxs-lookup"><span data-stu-id="373da-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="373da-p105">如果你的 Microsoft 365 商业版 订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="373da-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="373da-p106">还将显示与添加的新用户共享凭据的选项。可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="373da-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="373da-130">跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="373da-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="373da-131">如果要从另一个电子邮件提供商处进行移动, 并在以后复制数据, 则可以将[电子邮件和联系人迁移到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。</span><span class="sxs-lookup"><span data-stu-id="373da-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="373da-133">步骤 3: 连接域</span><span class="sxs-lookup"><span data-stu-id="373da-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="373da-134">如果您选择使用 .onmicrosoft 域或使用的 Azure AD Connect, 则不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="373da-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="373da-135">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="373da-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="373da-136">设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。</span><span class="sxs-lookup"><span data-stu-id="373da-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="373da-137">如果不是, 请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。</span><span class="sxs-lookup"><span data-stu-id="373da-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="373da-138">将为你设置电子邮件和其他服务</span><span class="sxs-lookup"><span data-stu-id="373da-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="373da-139">步骤 4: 管理设备和工作文件</span><span class="sxs-lookup"><span data-stu-id="373da-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="373da-140">还可以通过单击每个设置旁边的箭头访问每个子设置。</span><span class="sxs-lookup"><span data-stu-id="373da-140">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**.</span></span> <span data-ttu-id="373da-141">您还可以通过单击每个设置旁边的燕尾形来访问每个子设置。</span><span class="sxs-lookup"><span data-stu-id="373da-141">You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="373da-142">所有许可用户的工作文件现在都在 iOS 和 Android 设备上受到保护, 只要他们安装了[Office 应用程序](set-up-mobile-devices.md)(并通过其 Microsoft 365 商业版凭据进行身份验证)。</span><span class="sxs-lookup"><span data-stu-id="373da-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="373da-144">在 "**设置 windows 10 设备配置**" 页上, 将 "**安全 windows 10 设备**" 设置设置为 **"开"**。</span><span class="sxs-lookup"><span data-stu-id="373da-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="373da-145">您还可以通过单击每个子设置旁边的燕尾形来访问它。</span><span class="sxs-lookup"><span data-stu-id="373da-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="373da-146">将 "**在 windows 10 设备上安装 Office** " 设置为 **"是"** , 如果所有用户都有 Windows 10 计算机, 并且没有现有 office 安装, 或者即点即用 office 安装。</span><span class="sxs-lookup"><span data-stu-id="373da-146">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs.</span></span> <span data-ttu-id="373da-147">如果不是这种情况, 请将此选项设置为 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="373da-147">If this is not the case, set this option to **No**.</span></span> <span data-ttu-id="373da-148">在准备好用户计算机后, 您可以在以后自动从管理中心[安装 Office](auto-install-or-uninstall-office.md) 。</span><span class="sxs-lookup"><span data-stu-id="373da-148">You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers.</span></span> <span data-ttu-id="373da-149">有关说明, 请参阅[prepare for Office client 安装](prepare-for-office-client-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="373da-149">For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="373da-150">在 windows 10 设备上, 许可用户的工作文件将在其[windows 10 设备加入](set-up-windows-devices.md)microsoft 365 商业 Azure AD 域或在[新计算机上安装 windows 10](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)后立即进行规划, 同时加入 Microsoft 365Business Azure AD 域。</span><span class="sxs-lookup"><span data-stu-id="373da-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="373da-151">单击 "**下一步**", 你已完成设置。</span><span class="sxs-lookup"><span data-stu-id="373da-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="373da-152">请在此步骤中留下反馈, 以帮助我们改进体验。</span><span class="sxs-lookup"><span data-stu-id="373da-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="373da-154">其他安全设置</span><span class="sxs-lookup"><span data-stu-id="373da-154">Additional security settings</span></span>

<span data-ttu-id="373da-155">除了 "安装向导" 中的 "安全性和合规性" 设置之外, 您还可以设置以下附加设置:</span><span class="sxs-lookup"><span data-stu-id="373da-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="373da-156">设置针对不安全附件的保护。</span><span class="sxs-lookup"><span data-stu-id="373da-156">Set up protection against unsafe attachments.</span></span> <span data-ttu-id="373da-157">**高级威胁防护**(ATP) 标识恶意内容, 然后阻止提供不安全附件, 从而帮助您抵御网络钓鱼骗术和勒索软件感染。</span><span class="sxs-lookup"><span data-stu-id="373da-157">**Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections.</span></span> <span data-ttu-id="373da-158">若要激活附件保护, 请参阅[设置 Office 365 ATP 安全附件策略](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)。</span><span class="sxs-lookup"><span data-stu-id="373da-158">To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="373da-159">当用户单击恶意链接时, 保护您的环境。</span><span class="sxs-lookup"><span data-stu-id="373da-159">Protect your environment when users click malicious links.</span></span> <span data-ttu-id="373da-160">ATP 在用户单击时检查电子邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="373da-160">ATP examines links in email at the time a user clicks them.</span></span> <span data-ttu-id="373da-161">如果链接不安全, 则会警告用户不会访问网站, 或通知用户网站已被阻止。</span><span class="sxs-lookup"><span data-stu-id="373da-161">If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked.</span></span> <span data-ttu-id="373da-162">这有助于防止仿冒骗术。</span><span class="sxs-lookup"><span data-stu-id="373da-162">This helps protect against phishing schemes.</span></span> <span data-ttu-id="373da-163">[设置 office 365 atp 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[设置 office 365 atp 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。</span><span class="sxs-lookup"><span data-stu-id="373da-163">[Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="373da-164">通过将用户的整个邮箱置于**诉讼保留**中, 可以保留所有邮箱内容 (包括已删除项目)。</span><span class="sxs-lookup"><span data-stu-id="373da-164">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**.</span></span> <span data-ttu-id="373da-165">有关说明, 请参阅</span><span class="sxs-lookup"><span data-stu-id="373da-165">For instructions, see</span></span> 
- <span data-ttu-id="373da-166">[使用 Exchange Online 存档设置电子邮件保留](security-features.md#set-up-email-retention-with-exchange-online-archiving)。</span><span class="sxs-lookup"><span data-stu-id="373da-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="373da-167">设置自定义**保留策略**, 例如, 在保留期结束时保留特定时间段或永久删除内容。</span><span class="sxs-lookup"><span data-stu-id="373da-167">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="373da-168">您可以在 "证券和合规中心" 中启用自定义保留策略, 转到 "**数据调控** \> **保留**", 然后按照向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="373da-168">You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard.</span></span> <span data-ttu-id="373da-169">若要了解详细信息, 请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="373da-169">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="373da-170">后续步骤</span><span class="sxs-lookup"><span data-stu-id="373da-170">Next steps</span></span>

<span data-ttu-id="373da-171">对于具有许可证的用户，下一步是设置设备。</span><span class="sxs-lookup"><span data-stu-id="373da-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="373da-172">请参阅[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)和[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="373da-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="373da-173">有关如何设置设备和应用保护策略以及如何从用户设备中删除数据的主题链接，请参阅[管理 Microsoft 365 商业版](manage.md)。</span><span class="sxs-lookup"><span data-stu-id="373da-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


