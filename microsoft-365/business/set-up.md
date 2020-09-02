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
ms.openlocfilehash: cc20637d7a78bd34ecb61a4ed46eb06d564d63df
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324488"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>在安装向导中设置 Microsoft 365 商业高级版

观看此视频，了解 Microsoft 365 商业高级版安装程序的概述。<br><br>

## <a name="add-your-domain-users-and-set-up-policies"></a>添加你的域、用户并设置策略

在购买 Microsoft 365 商业高级版时，您可以选择使用自己的域，也可以在 [注册](sign-up.md)过程中购买一个域。

- 如果你在注册时购买了新域，则域已全部设置好，你可以继续[添加用户并分配许可证](#add-users-and-assign-licenses)。

### <a name="add-your-domain-to-personalize-sign-in"></a>添加你的域以个性化设置登录名

1. 使用全局管理员凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。 

2. 选择“**转到设置**”以启动向导。

    ![选择 "转到安装程序"。](../media/gotosetupinadmincenter.png)

3. 在“**安装 Office 应用**”页面上，可选择在自己的计算机上安装应用。
    
4. 在“**添加域**”步骤中，输入要使用的域名（如 contoso.com）。

    > [!IMPORTANT]
    > 如果你在注册期间购买了域，则此处不会看到“**添加域**”步骤。 转到“[添加用户](#add-users-and-assign-licenses)”。

    ![自定义登录页的屏幕截图。](../media/adddomain.png)

    
4. 按照向导中的步骤在 [Microsoft 365 的任何 DNS 托管提供程序中创建 dns 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) ，以验证您是否拥有该域。 如果你知道域主机，另请参阅[主机特定说明](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。

    如果你的托管服务提供商是 GoDaddy 或启用了 [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) 的其他主机，则此过程很简单，系统会自动要求你登录并让 Microsoft 代表你进行身份验证。

    ![在 GoDaddy“确认访问”页面上，选择“授权”。](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>添加用户并分配许可证

你可以在向导中添加用户，但你也可以[以后在管理中心添加用户](add-users-m365b.md)。 此外，如果你具有本地域控制器，则可以使用 [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) 添加用户。

#### <a name="add-users-in-the-wizard"></a>在向导中添加用户

在向导中添加的任何用户都会自动分配 Microsoft 365 商业高级版许可证。

![向导中的 "添加新用户" 页的屏幕截图](../media/addnewuserspage.png)

1. 如果你的 Microsoft 365 商业高级订阅具有现有用户 (例如，如果你使用的是 Azure AD Connect) ，你将获得一个选项，用于立即向其分配许可证。 继续操作，并为这些用户添加许可证。

2. 在你添加用户后，还将显示与添加的新用户共享凭据的选项。 可以选择打印、通过电子邮件发送或下载凭据。

### <a name="connect-your-domain"></a>连接你的域

> [!NOTE]
> 如果你选择使用 .onmicrosoft 域或使用 Azure AD Connect 设置用户，将不会看到此步骤。
  
必须更新 DNS 主机或域注册机构的一些记录才能设置服务。
  
1. 安装向导通常将检测你的注册机构，并提供更新注册机构网站上 NS 记录分步说明的链接。 如果不是，则 [将名称服务器更改为使用任何域注册机构设置 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)。 

    - 如果你有现有的 DNS 记录（例如现有网站），但你的 DNS 主机已启用 [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)，请选择“**为我添加记录**”。 在“**选择联机服务**”页面上，接受所有默认设置，选择“**下一步**”，然后在DNS 主机页面上选择“**授权**”。
    - 如果你具有用于其他 DNS 主机的现有 DNS 记录（未启用 domain connect），则需要管理自己的 DNS 记录以确保现有服务保持连接状态。 有关详细信息，请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。

        !["激活记录" 页。](../media/activaterecords.png)

2. 请按照向导中的步骤进行操作，然后将为你设置电子邮件和其他服务。

### <a name="protect-your-organization"></a>保护你的组织 

在向导中设置的策略将自动应用于名为 "*所有用户*" 的[安全组](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。 您还可以在管理中心中创建其他组来分配策略。

1. 在 " **加强对高级网络威胁的保护**" 中，建议您接受默认值以允许 [Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 扫描 office 应用中的文件和链接。

    ![增强保护页面的屏幕截图。](../media/increasetreatprotection.png)


2. 在 " **防止泄漏敏感数据** " 页上，接受默认设置以打开 Office 365 数据丢失防护 (DLP) 以跟踪 office 应用程序中的敏感数据，并防止在组织外部的意外共享这些数据。

3. 在 " **保护在移动 Office 中的数据** " 页面中，将移动应用管理保留在上，展开 "设置" 并查看它们，然后选择 " **创建移动应用管理策略**"。

    ![Office for mobile 页面中保护数据的屏幕截图。](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>保护 Windows 10 电脑

在左侧导航中，选择 " **设置** "，然后在 " **登录和安全**" 下，选择 " **保护 Windows 10 计算机**"。 选择 " **查看** " 即可开始。 有关完整说明，请参阅 [保护 Windows 10 计算机安全](secure-win-10-pcs.md) 。

## <a name="deploy-office-365-client-apps"></a>部署 Office 365 客户端应用程序

如果你选择在安装过程中自动安装 Office 应用，则在用户使用其工作凭据从 Windows 设备登录到 Azure AD 之后，应用将在 Windows 10 设备上安装。

若要在移动 iOS 或 Android 设备上安装 Office，请参阅 [为 Microsoft 365 商业高级版用户设置移动设备](set-up-mobile-devices.md)。

您也可以单独安装 Office。 有关说明，请参阅 [在电脑或 Mac 上安装 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 。

## <a name="see-also"></a>另请参阅

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
