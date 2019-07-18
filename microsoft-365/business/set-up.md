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
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>在安装向导中设置 Microsoft 365 商业版

## <a name="add-your-domain-users-and-set-up-policies"></a>添加你的域、用户并设置策略

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

在购买 Microsoft 365 商业版时, 您可以选择使用自己的域, 也可以在[注册](sign-up.md)过程中购买一个域。

- 如果你在注册时购买了一个新域, 你的域将全部设置, 并且你可以移动以[添加用户并分配许可证](#add-users-and-assign-licenses)。

### <a name="add-your-domain-to-personalize-sign-in"></a>添加你的域以个性化登录

1. 使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。 

2. 选择 "**添加域**" 或 "**添加用户**" 启动向导。
    > [!IMPORTANT]
    > 如果你在注册过程中购买了一个域, 你将不会在此处看到 "**添加域**" 步骤。 改为转到 "[添加用户](#add-users-and-assign-licenses)"。

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

![向导中的 "添加新用户" 页的屏幕截图](media/addnewuserspage.png)

1. 如果你的 Microsoft 365 业务订阅具有现有用户 (例如, 如果你使用的是 Azure AD Connect), 你将获得一个选项, 用于立即向其分配许可证。 继续操作，并为这些用户添加许可证。

3. 添加用户后, 您还将获得一个选项, 用于与添加的新用户共享凭据。 可以选择打印、通过电子邮件发送或下载凭据。

4. 跳过迁移电子邮件，然后在" **迁移电子邮件**"页面上选择" **下一步**"。 

    如果要从另一个电子邮件提供商处进行移动, 并在以后复制数据, 则可以将[电子邮件和联系人迁移到 Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)。


### <a name="connect-your-domain"></a>连接你的域

> [!NOTE]
> 如果选择使用 .onmicrosoft 域或使用的 Azure AD Connect 设置用户, 则不会看到此步骤。
  
必须更新 DNS 主机或域注册机构的一些记录才能设置服务。
  
1. 设置向导通常可检测到你的注册机构并提供一个链接，该链接指向在注册机构网站更新 NS 记录的分步说明。 如果不是, 请[将名称服务器更改为使用任何域注册机构设置 Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)。 

    - 如果您有现有的 DNS 记录 (例如现有网站), 您需要管理自己的 DNS 记录, 以确保现有服务保持连接。 有关详细信息, 请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。

        ![连接域页面, 我将管理自己的 DNS 记录。](media/connectyourdomainpage.png)

2. 按照向导中的步骤进行操作, 将为你设置电子邮件和其他服务。

### <a name="set-up-security-policies-and-device-configurations"></a>设置安全策略和设备配置 

在向导中设置的策略将自动应用于名为 "*所有用户*" 的[安全组](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups)。 您还可以在管理中心中创建其他组来分配策略。

1. 在**移动设备上保护你的工作文件**。默认情况下, 选择 "在**设备丢失或被盗时保护工作文件**" 选项。 你可以选择启用 "**管理用户如何在移动设备上访问 Office 文件**", 并建议这样做。

    !["移动设备上的保护工作文件" 页的屏幕截图。](media/protectworkfilesondevices.png)

     - **当设备丢失或被盗时, 展开保护工作文件**以显示[默认值](protect-work-files-on-lost-or-stolen-device.md):

        ![用于保护丢失设备上的文件的默认值的屏幕截图。](media/protectworkfilesondevicesdefault.png)

    - 选择 "**管理用户如何访问移动设备上的 Office 文件**并展开" 以显示[默认值](manage-user-access-on-mobile-devices.md)。 建议您在安装过程中接受默认值, 以创建适用于所有用户的 Android、iOS 和 Windows 10 应用程序策略。 在设置完成后，可以创建多个策略。

        ![移动时 Office 文件的保护设置的屏幕截图。](media/useraccessonmobile.png)

2. "保护数据和设备" 的最后一步是, 设置策略以保护 Windows 10 设备。 当用户的 Windows 10 连接到您的组织时, 这些设置会自动应用。 您可以展开**安全 Windows 10 设备**, 以查看和修改[默认值](secure-windows-10-devices.md)。
3. 你也可以选择在 Windows 10 设备上[自动安装 Office](install-office-on-windows-10-during-setup.md) 。

    !["设置 Windows 10 设备配置" 页的屏幕截图。](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>部署 Office 365 客户端应用程序

如果你选择在设置过程中自动安装 Office 应用, 则在用户使用其工作凭据从 Windows 设备登录到 Azure AD 之后, 应用将在 Windows 10 设备上安装。
若要在移动 iOS 或 Android 设备上安装 Office, 请参阅[为 Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。

您也可以单独安装 Office。 有关说明, 请参阅[在电脑或 Mac 上安装 Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) 。
