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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解如何设置 Microsoft 365 业务通过完成以下四个步骤。
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865405"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="2f475-103">使用安装向导安装 Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="2f475-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="2f475-104">完成步骤 1-4 下面。</span><span class="sxs-lookup"><span data-stu-id="2f475-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="2f475-105">设置 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="2f475-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="2f475-106">观看有关如何设置 Microsoft 365 企业版时您无需在本地 Active Directory 的视频：</span><span class="sxs-lookup"><span data-stu-id="2f475-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="2f475-p101">设置步骤包括包括本地 Active Directory 的设置的信息。如果您想要继续访问加入域的设备，阅读以下文章的两个不同的启用，方式，并在运行安装向导之前完成的步骤：</span><span class="sxs-lookup"><span data-stu-id="2f475-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="2f475-109">启用加入域的 Windows 10 设备，由 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="2f475-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="2f475-110">-这是建议的方式。</span><span class="sxs-lookup"><span data-stu-id="2f475-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="2f475-111">访问本地资源从 Microsoft 365 企业版中的 Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="2f475-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="2f475-112">步骤 1： 个性化登录</span><span class="sxs-lookup"><span data-stu-id="2f475-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="2f475-p102">使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.microsoft.com)。选择" **管理**"图块，进入管理中心。</span><span class="sxs-lookup"><span data-stu-id="2f475-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="2f475-115">在管理中心内，选择" **开始设置**"（可能会看到" **继续设置**"，具体取决于所处的状态），启动向导。</span><span class="sxs-lookup"><span data-stu-id="2f475-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="2f475-116">输入要使用的域名（如 contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="2f475-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="2f475-p103">继续操作，并输入您的域，即使时使用 Azure AD 连接，例如验证。如果您使用 Azure AD 连接验证您的域，以下两个步骤执行操作不适用于您。</span><span class="sxs-lookup"><span data-stu-id="2f475-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="2f475-119">按照向导中的步骤验证您拥有域中的[Office 365 任何 DNS 宿主提供商处创建 DNS 记录](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="2f475-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="2f475-p104">您可以查看的示例视频[视频： 安装 Office 365 中新的 Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。请注意，此视频不包括 Microsoft 365 业务数据保护步骤。</span><span class="sxs-lookup"><span data-stu-id="2f475-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="2f475-123">步骤 2： 添加用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="2f475-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="2f475-124">可通过此步骤添加用户，或稍后在管理中心[添加用户](add-users-m365b.md)。</span><span class="sxs-lookup"><span data-stu-id="2f475-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="2f475-125">添加的所有用户都会自动获得 Microsoft 365 商业版 许可。</span><span class="sxs-lookup"><span data-stu-id="2f475-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="2f475-p105">如果你的 Microsoft 365 商业版 订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。</span><span class="sxs-lookup"><span data-stu-id="2f475-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="2f475-p106">还将显示与添加的新用户共享凭据的选项。可以选择打印、通过电子邮件发送或下载凭据。</span><span class="sxs-lookup"><span data-stu-id="2f475-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="2f475-130">跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2f475-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="2f475-131">如果您要从另一个电子邮件提供商移动，并且想要将数据复制更高版本，则可以[迁移电子邮件和到 Office 365 的联系人](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。</span><span class="sxs-lookup"><span data-stu-id="2f475-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="2f475-133">步骤 3： 连接您的域</span><span class="sxs-lookup"><span data-stu-id="2f475-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="2f475-134">如果选择使用.onmicrosoft 域，或使用 Azure AD 连接时，将不会看到此步骤。</span><span class="sxs-lookup"><span data-stu-id="2f475-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="2f475-135">必须更新 DNS 主机或域注册机构的一些记录才能设置服务。</span><span class="sxs-lookup"><span data-stu-id="2f475-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="2f475-p107">通常，安装向导检测您注册器，并为您提供了一个链接到更新在注册网站 NS 记录的分步说明。如果没有，[更改名称服务器设置的任何域注册 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。</span><span class="sxs-lookup"><span data-stu-id="2f475-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="2f475-138">将为你设置电子邮件和其他服务</span><span class="sxs-lookup"><span data-stu-id="2f475-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="2f475-139">步骤 4： 管理设备和处理文件</span><span class="sxs-lookup"><span data-stu-id="2f475-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="2f475-p108">对**您的移动设备上的保护工作文件**页设置**保护工作文件时丢失或被盗设备**和**管理用户访问移动设备上的 Office 文件的方式**设置为**上**。您还可以访问每个子设置通过单击每个设置旁边的箭头。</span><span class="sxs-lookup"><span data-stu-id="2f475-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="2f475-142">所有许可的用户工作文件现在保护 iOS 和 Android 设备，只要他们[安装 Office 应用程序](set-up-mobile-devices.md)（和通过其 Microsoft 365 业务凭据进行身份验证）。</span><span class="sxs-lookup"><span data-stu-id="2f475-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="2f475-144">在**设置 Windows 10 设备配置**页上设置为**上**的**安全 Windows 10 设备**设置。</span><span class="sxs-lookup"><span data-stu-id="2f475-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="2f475-145">您还可以访问每个子设置通过单击它旁边的 v 形。</span><span class="sxs-lookup"><span data-stu-id="2f475-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="2f475-p109">将**Windows 10 设备上安装 Office**设置为**是**如果您的所有用户有 Windows 10 台计算机，并任一没有现有 Office 安装，或单击即点即用 Office 安装。如果这不是这样，设置此选项为**否**。您可以从管理中心更高版本的[自动安装 Office](auto-install-or-uninstall-office.md)后您已经准备好用户计算机。有关说明，请参阅[准备 Office 客户端安装](prepare-for-office-client-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="2f475-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="2f475-150">将为他们提供投影 Windows 10 设备上的授权的用户工作文件对 Microsoft 365 业务 Azure AD 域或时同时加入 Microsoft 365[安装的新计算机上的 Windows 10](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)的[联接其 Windows 10 设备](set-up-windows-devices.md)业务 Azure AD 域。</span><span class="sxs-lookup"><span data-stu-id="2f475-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="2f475-151">单击**下一步**和安装程序使用完。</span><span class="sxs-lookup"><span data-stu-id="2f475-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="2f475-152">请提供反馈我们在此步骤，以帮助我们改善体验。</span><span class="sxs-lookup"><span data-stu-id="2f475-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="2f475-154">其他安全设置</span><span class="sxs-lookup"><span data-stu-id="2f475-154">Additional security settings</span></span>

<span data-ttu-id="2f475-155">除了安全性和安装向导中的合规性设置中，您还可以设置以下附加设置：</span><span class="sxs-lookup"><span data-stu-id="2f475-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="2f475-p110">设置防范不安全的附件。**高级威胁保护**(ATP) 标识恶意内容，然后阻止传递不安全的附件，帮助您防御网络钓鱼方案和勒索软件病毒感染。若要激活附件保护，请参阅[Office 365 ATP 安全附件策略设置](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2f475-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="2f475-p111">当用户单击恶意链接保护您的环境。在用户单击它们的时间，ATP 检查电子邮件中的链接。如果不安全的链接，用户警告不以访问网站，或通知网站已被阻止。这有助于防止网络钓鱼方案。[设置 Office 365 ATP 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[Office 365 ATP 安全链接策略设置](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。</span><span class="sxs-lookup"><span data-stu-id="2f475-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="2f475-p112">您可以保留所有邮箱内容，包括通过将用户的整个邮箱置于**诉讼保留**已删除的项目。有关说明，请参阅</span><span class="sxs-lookup"><span data-stu-id="2f475-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="2f475-166">[与 Exchange Online Archiving 的电子邮件保留设置](security-features.md#set-up-email-retention-with-exchange-online-archiving)。</span><span class="sxs-lookup"><span data-stu-id="2f475-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="2f475-p113">设置自定义**保留策略**，例如，若要保留特定时间段的或在保留期结束永久删除内容。您可以启用中证券和合规性中心，转到**数据管理**的自定义的保留策略\>**保留**，然后按照向导中的步骤进行操作。若要了解详细信息，请参阅[Overview of 保留策略](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="2f475-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="2f475-170">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2f475-170">Next steps</span></span>

<span data-ttu-id="2f475-171">对于具有许可证的用户，下一步是设置设备。</span><span class="sxs-lookup"><span data-stu-id="2f475-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="2f475-172">请参阅[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)和[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="2f475-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="2f475-173">有关如何设置设备和应用保护策略以及如何从用户设备中删除数据的主题链接，请参阅[管理 Microsoft 365 商业版](manage.md)。</span><span class="sxs-lookup"><span data-stu-id="2f475-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


