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
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>使用安装向导安装 Microsoft 365 Business

完成步骤 1-4 下面。
  
### <a name="set-up-microsoft-365-business"></a>设置 Microsoft 365 商业版

观看有关如何设置 Microsoft 365 企业版时您无需在本地 Active Directory 的视频：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
设置步骤包括包括本地 Active Directory 的设置的信息。如果您想要继续访问加入域的设备，阅读以下文章的两个不同的启用，方式，并在运行安装向导之前完成的步骤：
  
- [启用加入域的 Windows 10 设备，由 Microsoft 365 企业版](manage-windows-devices.md)
    
    -这是建议的方式。
    
- [访问本地资源从 Microsoft 365 企业版中的 Azure AD 加入设备](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>步骤 1： 个性化登录

1. 使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.microsoft.com)。选择" **管理**"图块，进入管理中心。 
    
2. 在管理中心内，选择" **开始设置**"（可能会看到" **继续设置**"，具体取决于所处的状态），启动向导。 
    
3. 输入要使用的域名（如 contoso.com）。
    
    继续操作，并输入您的域，即使时使用 Azure AD 连接，例如验证。如果您使用 Azure AD 连接验证您的域，以下两个步骤执行操作不适用于您。
    
4. 按照向导中的步骤验证您拥有域中的[Office 365 任何 DNS 宿主提供商处创建 DNS 记录](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。 
    
    您可以查看的示例视频[视频： 安装 Office 365 中新的 Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。请注意，此视频不包括 Microsoft 365 业务数据保护步骤。
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>步骤 2： 添加用户并分配许可证

1. 可通过此步骤添加用户，或稍后在管理中心[添加用户](add-users-m365b.md)。 
    
    添加的所有用户都会自动获得 Microsoft 365 商业版 许可。
    
2. 如果你的 Microsoft 365 商业版 订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。
    
3. 还将显示与添加的新用户共享凭据的选项。可以选择打印、通过电子邮件发送或下载凭据。
    
4. 跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。 
    
    如果您要从另一个电子邮件提供商移动，并且想要将数据复制更高版本，则可以[迁移电子邮件和到 Office 365 的联系人](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>步骤 3： 连接您的域

> [!NOTE]
> 如果选择使用.onmicrosoft 域，或使用 Azure AD 连接时，将不会看到此步骤。 
  
必须更新 DNS 主机或域注册机构的一些记录才能设置服务。
  
1. 通常，安装向导检测您注册器，并为您提供了一个链接到更新在注册网站 NS 记录的分步说明。如果没有，[更改名称服务器设置的任何域注册 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。
    
2. 将为你设置电子邮件和其他服务
    
### <a name="step-4-manage-devices-and-work-files"></a>步骤 4： 管理设备和处理文件

1. 对**您的移动设备上的保护工作文件**页设置**保护工作文件时丢失或被盗设备**和**管理用户访问移动设备上的 Office 文件的方式**设置为**上**。您还可以访问每个子设置通过单击每个设置旁边的箭头。
  
  所有许可的用户工作文件现在保护 iOS 和 Android 设备，只要他们[安装 Office 应用程序](set-up-mobile-devices.md)（和通过其 Microsoft 365 业务凭据进行身份验证）。 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. 在**设置 Windows 10 设备配置**页上设置为**上**的**安全 Windows 10 设备**设置。
  
   您还可以访问每个子设置通过单击它旁边的 v 形。
  
3. 将**Windows 10 设备上安装 Office**设置为**是**如果您的所有用户有 Windows 10 台计算机，并任一没有现有 Office 安装，或单击即点即用 Office 安装。如果这不是这样，设置此选项为**否**。您可以从管理中心更高版本的[自动安装 Office](auto-install-or-uninstall-office.md)后您已经准备好用户计算机。有关说明，请参阅[准备 Office 客户端安装](prepare-for-office-client-deployment.md)。
  
    将为他们提供投影 Windows 10 设备上的授权的用户工作文件对 Microsoft 365 业务 Azure AD 域或时同时加入 Microsoft 365[安装的新计算机上的 Windows 10](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)的[联接其 Windows 10 设备](set-up-windows-devices.md)业务 Azure AD 域。 
  
4. 单击**下一步**和安装程序使用完。 
  
    请提供反馈我们在此步骤，以帮助我们改善体验。
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>其他安全设置

除了安全性和安装向导中的合规性设置中，您还可以设置以下附加设置：
  
- 设置防范不安全的附件。**高级威胁保护**(ATP) 标识恶意内容，然后阻止传递不安全的附件，帮助您防御网络钓鱼方案和勒索软件病毒感染。若要激活附件保护，请参阅[Office 365 ATP 安全附件策略设置](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)。
    
- 当用户单击恶意链接保护您的环境。在用户单击它们的时间，ATP 检查电子邮件中的链接。如果不安全的链接，用户警告不以访问网站，或通知网站已被阻止。这有助于防止网络钓鱼方案。[设置 Office 365 ATP 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[Office 365 ATP 安全链接策略设置](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
- 您可以保留所有邮箱内容，包括通过将用户的整个邮箱置于**诉讼保留**已删除的项目。有关说明，请参阅 
- [与 Exchange Online Archiving 的电子邮件保留设置](security-features.md#set-up-email-retention-with-exchange-online-archiving)。
    
- 设置自定义**保留策略**，例如，若要保留特定时间段的或在保留期结束永久删除内容。您可以启用中证券和合规性中心，转到**数据管理**的自定义的保留策略\>**保留**，然后按照向导中的步骤进行操作。若要了解详细信息，请参阅[Overview of 保留策略](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
    
## <a name="next-steps"></a>后续步骤

对于具有许可证的用户，下一步是设置设备。<br/> 请参阅[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)和[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。 <br/>有关如何设置设备和应用保护策略以及如何从用户设备中删除数据的主题链接，请参阅[管理 Microsoft 365 商业版](manage.md)。 
  


