---
title: 设置 Microsoft 365 商业标准版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: 了解如何设置 Microsoft 365 商业标准版订阅。
ms.openlocfilehash: e69a3c75d77a8b4721558e72526a068df643f284
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644551"
---
# <a name="set-up-microsoft-business-standard"></a>设置 Microsoft 商业标准版

观看有关设置 Microsoft 365 商业标准版的简短视频。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ELKR]

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。
  
 *这些步骤适用于具有 **[Microsoft 365 商业标准版计划](https://go.microsoft.com/fwlink/p/?LinkId=627220)** 的企业和[非营利组织](https://go.microsoft.com/fwlink/p/?LinkId=627221)_

观看有关设置 Microsoft 365 商业标准版（以前称为 Microsoft 365 商业高级版）的简短视频。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

如果你觉得这段视频有用，请查看[适用于小型企业和 Microsoft 365 新手的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="add-your-domain-to-personalize-sign-in"></a>添加你的域以个性化设置登录名

购买 Microsoft 365 商业标准版时，你可以选择使用自己拥有的域，也可以在注册期间购买一个域。

- 如果你在注册时购买了新域，则域已全部设置好，你可以继续[添加用户并分配许可证](#add-users-and-assign-licenses)。

1. 使用全局管理员凭据登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。 

2. 选择“*转到设置*”来启动向导。

3. 在“**安装 Office 应用**”页面上，可选择在自己的计算机上安装应用。
    
4. 在“**添加域**”步骤中，输入要使用的域名（如 contoso.com）。

    > [!IMPORTANT]
    > 如果你在注册期间购买了域，则此处不会看到“**添加域**”步骤。 转到“[添加用户](#add-users-and-assign-licenses)”。

    
4. 按照向导[在任何 DNS 托管提供商处为 Office 365 创建 DNS 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)中的步骤验证你是否拥有该域。 如果你知道域主机，另请参阅[主机特定说明](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)。

    如果你的托管服务提供商是 GoDaddy 或启用了 [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) 的其他主机，则此过程很简单，系统会自动要求你登录并让 Microsoft 代表你进行身份验证。

    ![在 GoDaddy“确认访问”页面上，选择“授权”。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>添加用户并分配许可证

你可以在向导中添加用户，但你也可以[以后在管理中心添加用户](../add-users/add-users.md)。 此外，如果你具有本地域控制器，则可以使用 [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) 添加用户。

## <a name="add-users-in-the-wizard"></a>在向导中添加用户

你在向导中添加的所有用户都将自动分配一个 Microsoft 365 商业标准版许可证。

1. 如果你的 Microsoft 365 商业标准版订阅中存在现有用户（例如，如果使用了 Azure AD Connect），将显示现在为其分配许可证的选项。 继续操作，并为这些用户添加许可证。

2. 在你添加用户后，还将显示与添加的新用户共享凭据的选项。 可以选择打印、通过电子邮件发送或下载凭据。

## <a name="connect-your-domain"></a>连接你的域

> [!NOTE]
> 如果你选择使用 .onmicrosoft 域或使用 Azure AD Connect 设置用户，将不会看到此步骤。
  
必须更新 DNS 主机或域注册机构的一些记录才能设置服务。
  
1. 安装向导通常将检测你的注册机构，并提供更新注册机构网站上 NS 记录分步说明的链接。 如果没有，请[将名称服务器更改为使用任意域名注册机构设置 Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar)。 

    - 如果你有现有的 DNS 记录（例如现有网站），但你的 DNS 主机已启用 [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)，请选择“**为我添加记录**”。 在“**选择联机服务**”页面上，接受所有默认设置，选择“**下一步**”，然后在DNS 主机页面上选择“**授权**”。
    - 如果你具有用于其他 DNS 主机的现有 DNS 记录（未启用 domain connect），则需要管理自己的 DNS 记录以确保现有服务保持连接状态。 有关详细信息，请参阅[域基础知识](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics)。

2. 请按照向导中的步骤进行操作，然后将为你设置电子邮件和其他服务。

    注册过程完成后，你将转到管理中心，按照向导安装 Office 应用、添加域、添加用户和分配许可证。 完成初始设置后，可使用管理中心中的“**设置**”页面，继续设置和配置订阅附带的服务。

    有关设置向导和管理中心“**设置**”页面的详细信息，请参阅[设置向导和设置页面之间的区别](o365-setup-wizard-and-setup-page.md)。

## <a name="finish-setting-up"></a>完成设置

### <a name="set-up-outlook-for-email"></a>设置 Outlook，使用电子邮件功能

1. 在 Windows“开始”菜单上，搜索并选择“Outlook”。

    （如果使用的是 Mac，请从工具栏打开 Outlook 或使用 Finder 进行查找。）

    如果刚刚安装了 Outlook，请在欢迎页面上选择“**下一步**”。

2. 选择“**文件**”\>“**信息**”\>“**添加帐户**”。

3. 输入你的 Microsoft 电子邮件地址并选择“**连接**”。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
请参阅[设置 Outlook，使用电子邮件功能](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)，了解有关详细信息。
  
### <a name="import-email"></a>使用 Outlook

如果通过另一电子邮件帐户使用 Outlook，可将之前的电子邮件、日历和联系人导入新的 Microsoft 帐户。
  
1. **导出旧的电子邮件**

    在 Outlook 中，选择“**文件**”\>“**打开并导出**”\>“**导入/导出**”。

    选择“**导出到文件**”，然后按照以下步骤导出 Outlook 数据文件 (.pst) 和任何子文件夹。

2. **导入旧的电子邮件**

    在 Outlook 中，再次选择“**文件**”\>“**打开并导出**”\>>“**导入/导出**”。

    这一次，选择“**从另一程序或文件导入**”并按照以下步骤导入“导出旧的电子邮件”时创建的备份文件。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
请参阅[使用 Outlook 导入电子邮件](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)，了解有关详细信息。

还可以使用 Exchange 管理中心导入每个人的电子邮件。 有关详细信息，请参阅[迁移多个电子邮件帐户](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。
  
### <a name="use-a-public-website"></a>使用公共网站

Microsoft 365 不提供适用于公司的公共网站。 如需设置一个公共网站，请考虑使用 GoDaddy 或 WIX 等 Microsoft 合作伙伴。
  
1. 从管理中心，转到“**资源**”，然后选择“**公共网站**”。

2. 在其中一个选项下选择“**了解详细信息**”，然后注册网站合作伙伴，并使用其工具设置和设计你的网站。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

请参阅[使用公共网站](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)，了解有关详细信息。