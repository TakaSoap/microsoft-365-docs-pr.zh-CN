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
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>使用安装向导安装 Microsoft 365 Business

完成下面的步骤1-4。
  
### <a name="set-up-microsoft-365-business"></a>设置 Microsoft 365 商业版

如果你没有本地 Active Directory, 请观看有关如何设置 Microsoft 365 商业版的视频:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
设置步骤包括包含本地 Active Directory 的设置的信息。 如果要继续访问加入域的设备, 请阅读以下文章以两种不同的方式启用该命令, 并在运行安装向导之前完成这些步骤:
  
- [启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备](manage-windows-devices.md)
    
    -建议采用此方法。
    
- [从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>步骤 1: 个性化登录

1. 使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.microsoft.com)。选择" **管理**"图块，进入管理中心。 
    
2. 在管理中心内，选择" **开始设置**"（可能会看到" **继续设置**"，具体取决于所处的状态），启动向导。 
    
3. 输入要使用的域名（如 contoso.com）。
    
    继续进行操作并输入你的域（即使在使用 Azure AD Connect（举例）时已验证过）。 如果您使用 Azure AD Connect 验证您的域, 则以下两个步骤不适用于您。
    
4. 按照向导中的步骤在[适用于 Office 365 的任何 dns 托管提供程序中创建 dns 记录](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166), 以验证您是否拥有该域。 
    
    您可以查看视频的示例视频[: 在新管理中心中设置 Office 365](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。 请注意，此视频不包括 Microsoft 365 商业版 的数据保护步骤。
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>步骤 2: 添加用户并分配许可证

1. 可通过此步骤添加用户，或稍后在管理中心[添加用户](add-users-m365b.md)。 
    
    添加的所有用户都会自动获得 Microsoft 365 商业版 许可。
    
2. 如果你的 Microsoft 365 商业版 订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。
    
3. 还将显示与添加的新用户共享凭据的选项。可以选择打印、通过电子邮件发送或下载凭据。
    
4. 跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。 
    
    如果要从另一个电子邮件提供商处进行移动, 并在以后复制数据, 则可以将[电子邮件和联系人迁移到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>步骤 3: 连接域

> [!NOTE]
> 如果您选择使用 .onmicrosoft 域或使用的 Azure AD Connect, 则不会看到此步骤。 
  
必须更新 DNS 主机或域注册机构的一些记录才能设置服务。
  
1. 设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。 如果不是, 请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。
    
2. 将为你设置电子邮件和其他服务
    
### <a name="step-4-manage-devices-and-work-files"></a>步骤 4: 管理设备和工作文件

1. 还可以通过单击每个设置旁边的箭头访问每个子设置。 您还可以通过单击每个设置旁边的燕尾形来访问每个子设置。
  
  所有许可用户的工作文件现在都在 iOS 和 Android 设备上受到保护, 只要他们安装了[Office 应用程序](set-up-mobile-devices.md)(并通过其 Microsoft 365 商业版凭据进行身份验证)。 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. 在 "**设置 windows 10 设备配置**" 页上, 将 "**安全 windows 10 设备**" 设置设置为 **"开"**。
  
   您还可以通过单击每个子设置旁边的燕尾形来访问它。
  
3. 将 "**在 windows 10 设备上安装 Office** " 设置为 **"是"** , 如果所有用户都有 Windows 10 计算机, 并且没有现有 office 安装, 或者即点即用 office 安装。 如果不是这种情况, 请将此选项设置为 "**否**"。 在准备好用户计算机后, 您可以在以后自动从管理中心[安装 Office](auto-install-or-uninstall-office.md) 。 有关说明, 请参阅[prepare for Office client 安装](prepare-for-office-client-deployment.md)。
  
    在 windows 10 设备上, 许可用户的工作文件将在其[windows 10 设备加入](set-up-windows-devices.md)microsoft 365 商业 Azure AD 域或在[新计算机上安装 windows 10](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)后立即进行规划, 同时加入 Microsoft 365Business Azure AD 域。 
  
4. 单击 "**下一步**", 你已完成设置。 
  
    请在此步骤中留下反馈, 以帮助我们改进体验。
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>其他安全设置

除了 "安装向导" 中的 "安全性和合规性" 设置之外, 您还可以设置以下附加设置:
  
- 设置针对不安全附件的保护。 **高级威胁防护**(ATP) 标识恶意内容, 然后阻止提供不安全附件, 从而帮助您抵御网络钓鱼骗术和勒索软件感染。 若要激活附件保护, 请参阅[设置 Office 365 ATP 安全附件策略](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)。
    
- 当用户单击恶意链接时, 保护您的环境。 ATP 在用户单击时检查电子邮件中的链接。 如果链接不安全, 则会警告用户不会访问网站, 或通知用户网站已被阻止。 这有助于防止仿冒骗术。 [设置 office 365 atp 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)或[设置 office 365 atp 安全链接策略](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)。
    
- 通过将用户的整个邮箱置于**诉讼保留**中, 可以保留所有邮箱内容 (包括已删除项目)。 有关说明, 请参阅 
- [使用 Exchange Online 存档设置电子邮件保留](security-features.md#set-up-email-retention-with-exchange-online-archiving)。
    
- 设置自定义**保留策略**, 例如, 在保留期结束时保留特定时间段或永久删除内容。 您可以在 "证券和合规中心" 中启用自定义保留策略, 转到 "**数据调控** \> **保留**", 然后按照向导中的步骤操作。 若要了解详细信息, 请参阅[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)。
    
## <a name="next-steps"></a>后续步骤

对于具有许可证的用户，下一步是设置设备。<br/> 请参阅[为 Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)和[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。 <br/>有关如何设置设备和应用保护策略以及如何从用户设备中删除数据的主题链接，请参阅[管理 Microsoft 365 商业版](manage.md)。 
  


