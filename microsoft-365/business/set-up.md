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
# <a name="set-up-microsoft-365-business"></a>设置 Microsoft 365 商业版

在开始之前, 请参阅[获取 Microsoft 365 商业](get-microsoft-365-business.md)版以获取注册详细信息。

观看有关如何使用设置向导以及当你没有本地 Active Directory 时[如何设置 Microsoft 365 商业版的简短视频](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1)
  

## <a name="overview"></a>概述

大部分设置步骤可以在安装向导中完成, 但也会列出其他选项。

1. [添加你的域](#add-your-domain-to-personalize-sign-in)(如果你在[注册](sign-up.md)期间购买了你的域, 则此步骤已完成。)
2. 添加用户。 可以通过以下三种方式之一执行此操作:
    - 在[安装向导](#add-users-in-the-wizard)中。
    - 如果你有本地 Active directory, 请使用目录同步来[使用 AZURE AD Connect 添加用户](#add-users-by-using-azure-ad-connect)。
    - 您还可以在随后的管理中心[添加用户](add-users-m365b.md)。
3. 设置安全策略和配置设备。 可以通过以下三种方式之一执行此操作:
    - 在[安装向导](#set-up-policies-in-the-wizard)中。  
    - 在[管理中心](#modify-or-add-policies-in-the-admin-center)。
    - 在[Intune 管理中心](https://docs.microsoft.com/intune/what-is-device-management)中。
4. 设置和管理 Windows 10 设备。

    将 WIndows 10 设备加入 Azure AD 时, 所有策略都将应用于它。
    - 在[安装向导](#set-up-policies-in-the-wizard)中设置 Windows 10 设备配置。
    - 将[新的 Windows 10 设备](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device)加入 Azure AD。
    - 将[现有 Windows 10 设备](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro)加入 Azure AD。
1. 安装 Office 365 商业版。
    - 您可以使用[安装向导](#set-up-policies-in-the-wizard)在 Windows 设备中自动安装 Office。
    - 从管理中心自动[安装 Office](auto-install-or-uninstall-office.md) 。
    - 允许用户安装适用于 Windows 和设备的[Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications)。
     
1. 设置其他安全性。
    - 安装向导添加策略以保护设备, 但您也可以利用[其他安全](#additional-security-settings)功能来帮助保护您的数据、帐户和电子邮件。 

## <a name="add-your-domain-users-and-set-up-policies"></a>添加你的域、用户并设置策略

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

在购买 Microsoft 365 商业版时, 您可以选择使用自己的域, 也可以在[注册](sign-up.md)过程中购买一个域。

- 如果你在注册时购买了一个新域, 你的域将全部设置, 并且你可以移动以[添加用户并分配许可证](#add-users-and-assign-licenses)。

### <a name="add-your-domain-to-personalize-sign-in"></a>添加你的域以个性化登录

1. 使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。 

2. 选择 "**添加域**" 以启动向导。

    ![选择 "添加域"。](media/addadomainadmincenter.png)
    
3. 在向导中, 输入要使用的域名 (如 contoso.com)。


    ![自定义登录页的屏幕截图。](media/personalizesignin.png)

    
4. 按照向导中的步骤在[适用于 Office 365 的任何 dns 托管提供程序中创建 dns 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), 以验证您是否拥有该域。 如果你知道你的域主机, 请参阅[特定主机说明](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。

    如果您的托管提供商为 GoDaddy, 则该过程非常简单, 您将自动要求您登录并让 Microsoft 代表你进行身份验证:

    ![在 GoDaddy "确认访问" 页上, 选择 "授权"。](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>添加用户并分配许可证

你可以在向导中添加用户, 但你也可以[稍后在管理中心添加用户](add-users-m365b.md)。 此外, 如果您有一个本地域控制器, 则可以使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)添加用户。

#### <a name="add-users-in-the-wizard"></a>在向导中添加用户

在向导中添加的任何用户都会自动分配 Microsoft 365 商业版许可证。
如果你有一个本地域控制器, 并且正在使用 Active Directory, 请参阅 how [to ddd users by Using AZURE AD Connect](#add-users-by-using-azure-ad-connect)。

![向导中的 "添加新用户" 页的屏幕截图](media/addnewuserspage.png)

1. 如果你的 Microsoft 365 商业版 订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。继续操作，并为这些用户添加许可证。

3. 添加用户后, 您还将获得一个选项, 用于与添加的新用户共享凭据。 可以选择打印、通过电子邮件发送或下载凭据。

4. 跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。 

    如果要从另一个电子邮件提供商处进行移动, 并在以后复制数据, 则可以将[电子邮件和联系人迁移到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。

#### <a name="add-users-by-using-azure-ad-connect"></a>使用 Azure AD Connect 添加用户

 如果您有一个包含 Active Directory 的本地域控制器, 则使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)将用户与 Microsoft 365 业务同步。 完成此过程后, 再启动安装向导。 您可以在管理中心下载:

- 转到 "**用户** \> **活动用户**", 选择页面顶部的省略号, 然后选择 "**目录同步**" 以下载 Azure AD Connect。

    ![在 "活动用户" 页上, 选择省略号 > Directory snchronization。](media/setupdirsync.png)

    > [!IMPORTANT]
    > 如果以这种方式创建用户, 则仍必须在管理中心将许可证分配给这些用户。

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>继续访问加入域的应用和设备

如果要继续访问加入域的应用和设备, 请阅读以下文章以两种不同的方式启用:
  
- [启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备](manage-windows-devices.md)
    - 建议使用此方法。

- [从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源](access-resources.md)

### <a name="connect-your-domain"></a>连接你的域

> [!NOTE]
> 如果选择使用 .onmicrosoft 域或使用的 Azure AD Connect 设置用户, 则不会看到此步骤。
  
必须更新 DNS 主机或域注册机构的一些记录才能设置服务。
  
1. 设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。 如果不是, 请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。 

    - 如果您有现有的 DNS 记录 (例如现有网站), 您需要管理自己的 DNS 记录, 以确保现有服务保持连接。 有关详细信息, 请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。

        ![连接域页面, 我将管理自己的 DNS 记录。](media/connectyourdomainpage.png)

2. 按照向导中的步骤进行操作, 将为你设置电子邮件和其他服务。

### <a name="set-up-security-policies-and-device-configurations"></a>设置安全策略和设备配置 

如果您决定向一组用户分配不同的策略, 则这些策略适用于您向其授予许可证的每个用户或向一组用户。

#### <a name="set-up-policies-in-the-wizard"></a>在向导中设置策略

在向导中设置的策略将自动应用于名为 "*所有用户*" 的[安全组](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。

1. 在**移动设备上保护你的工作文件**。默认情况下, 选择 "在**设备丢失或被盗时保护工作文件**" 选项。 你可以选择启用 "**管理用户如何在移动设备上访问 Office 文件**", 并建议这样做。

    !["移动设备上的保护工作文件" 页的屏幕截图。](media/protectworkfilesondevices.png)

     - 如果在**设备丢失或被盗时扩展了保护工作文件**, 则将预先选择[默认值](protect-work-files-on-lost-or-stolen-device.md):

        ![用于保护丢失设备上的文件的默认值的屏幕截图。](media/protectworkfilesondevicesdefault.png)

    - 如果选择 "**管理用户如何在移动设备上访问 Office 文件**并展开", 将显示[默认值](manage-user-access-on-mobile-devices.md)。 建议在设置过程中接受默认值，创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。 在设置完成后，可以创建多个策略。

        ![移动时 Office 文件的保护设置的屏幕截图。](media/useraccessonmobile.png)

2. "保护数据和设备" 的最后一步是, 设置策略以保护 Windows 10 设备。 当用户的 Windows 10 连接到您的组织时, 这些设置会自动应用。 您可以展开**安全 Windows 10 设备**, 以查看和修改[默认值](secure-windows-10-devices.md)。
3. 你也可以选择在 Windows 10 设备上[自动安装 Office](install-office-on-windows-10-during-setup.md) 。

    !["设置 Windows 10 设备配置" 页的屏幕截图。](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>在管理中心中修改或添加策略

请参阅[管理 Microsoft 365 商业](manage.md)版, 了解有关如何查看和修改设备和应用保护策略以及如何从或重置用户设备中删除数据的主题的链接。

## <a name="deploy-and-manage-windows-10"></a>部署和管理 Windows 10
请参阅为[Microsoft 365 商业用户设置 Windows 设备](set-up-windows-devices.md)以在安装新计算机的过程中手动连接到 Azure AD, 或更改现有计算机的登录配置文件。 

### <a name="use-autopilot-to-set-up-new-devices"></a>使用 Autopilot 设置新设备

可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置**新**的 Windows 10 设备, 但更易于获取可为您执行此操作的[合作伙伴](https://www.microsoft.com/solution-providers/search)。 你也可以转到[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)并咨询云技术专家, 以设置你购买的新设备。

### <a name="access-on-premises-resources"></a>访问本地资源

如果您的组织使用的是本地 Windows Server Active Directory, 则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备, 同时仍保持对需要本地身份验证的本地资源的访问权限。 按照 Microsoft 365 商业版中的 "[启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作, 以便对此进行设置。 这是此状态的首选方法, 称为混合 Azure AD 加入的设备。

如果你的企业有包含某些本地资源 (如文件共享和打印机) 的本地 Active Directory, 则可以执行以下步骤, 为 Azure AD 联接的设备提供对这些资源的访问权限:[从访问本地资源Microsoft 365 商业版中的 Azure AD 加入设备](access-resources.md)。

## <a name="deploy-office-365-client-apps"></a>部署 Office 365 客户端应用程序

如果你选择在设置过程中自动安装 Office 应用, 则在用户使用其工作凭据从 Windows 设备登录到 Azure AD 之后, 应用将在 Windows 10 设备上安装。
若要在移动 iOS 或 Android 设备上安装 Office, 请参阅[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。

您也可以单独安装 Office。 有关说明, 请参阅[在电脑或 Mac 上安装 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) 。

## <a name="additional-security-settings"></a>其他安全设置

除了 "安装向导" 中的 "安全性和合规性" 设置之外, 您还可以设置以下附加设置:
  
- **电子邮件恶意软件保护**
- **高级威胁防护 (ATP) 安全附件**
- **ATP 安全链接**
- **APT. 反网络钓鱼**
- **Exchange Online Archiving**
- **数据丢失防护 (DLP)**
- **Azure 信息保护**(计划 1)
- **Intune 门户可用性**

若要开始, 请[设置高级安全策略](set-up-advanced-security.md)。

请参阅[保护 Microsoft 365 业务的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), 以获得最佳安全实践的路线图。