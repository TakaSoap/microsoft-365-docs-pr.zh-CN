---
title: 使用新域或现有域设置 Microsoft 365 商业标准版
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- BEA160
description: 购买 Microsoft 365 商业标准版时，你可以选择使用自己拥有的域，也可以在注册期间购买一个域。
ms.openlocfilehash: 3144c61b0aa6f329fa4f0159cedbad21c2038169
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169343"
---
# <a name="set-up-microsoft-365-business-standard-with-a-new-or-existing-domain"></a>使用新域或现有域设置 Microsoft 365 商业标准版

购买 Microsoft 365 商业标准版时，你可以选择添加自己拥有的域，也可以购买一个域。 查看 [注册 Microsoft 365 商业标准版订阅](../simplified-signup/signup-business-standard.md)。

在本文中，我们将引导你完成添加已拥有的现有域或购买新域的步骤。 如果你在注册时购买了新域，则域已全部设置好，你可以继续[添加用户并分配许可证](#add-users-and-assign-licenses)。

## <a name="before-you-begin"></a>开始之前

要添加、修改或删除域，你必须是全局管理员。 有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md)。

> [!IMPORTANT]
> 注册 Microsoft 365 商业版的人员（通常是业务所有者）自动成为组织的技术管理员。 如果希望帮助管理 Microsoft 365 服务，可以将其他人添加为管理员。 有关详细信息，请查看 [添加管理员](../../business-video/add-admin.md)。

## <a name="watch-add-an-existing-domain-to-your-microsoft-365-business-standard-subscription"></a>观看：将现有域添加到 Microsoft 365 商业标准版订阅

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu]

## <a name="steps-add-an-existing-domain-to-your-microsoft-365-business-standard-subscription"></a>步骤：将现有域添加到 Microsoft 365 商业标准版订阅

1. 从 Microsoft 365 商业标准版注册的 **如何登录** 页面中，选择“**创建新的业务电子邮件帐户（高级）**”。

2. 在“**安装 Office 应用**”页面上，可选择在自己的计算机上安装应用。

3. 在“**添加域**”步骤中，输入要使用的域名（如 contoso.com）。

    > [!IMPORTANT]
    > 如果您在注册期间购买了域，您将不会在此处看到 **添加域** 步骤。 转至 [添加用户](#add-users-and-assign-licenses)。

4. 按照步骤 [在任何 Office 365 DNS 托管提供商处创建 DNS 记录](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，以验证你是否拥有该域。 如果你知道域主机，另请参阅[向Microsoft 365](/microsoft-365/admin/setup/add-domain)添加域。

    如果你的托管服务提供商是 GoDaddy 或启用了 [domain connect](/office365/admin/get-help-with-domains/domain-connect) 的其他主机，则此过程很简单，系统会自动要求你登录并让 Microsoft 代表你进行身份验证。

    ![在 GoDaddy“确认访问”页面上，选择“授权”。](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>添加用户并分配许可证

你可以现在添加用户，但也可以稍后在管理中心中 [添加用户](../add-users/add-users.md)。

你添加的所有用户都将自动分配一个 Microsoft 365 商业标准版许可证。

1. 如果你的 Microsoft 365 商业标准版订阅具有现有用户，则可以选择现在即向其分配许可证。继续操作，并为这些用户添加许可证。

2. 添加用户之后，还将显示与添加的新用户共享凭据的选项。可以选择打印、通过电子邮件发送或下载凭据。

## <a name="connect-your-domain"></a>连接你的域
  
必须更新 DNS 主机或域注册机构的记录才能设置服务。
  
1. 安装向导通常将检测你的注册机构，并提供更新注册机构网站上 NS 记录分步说明的链接。 如果没有，请[将名称服务器更改为使用任意域名注册机构设置 Office 365](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)。

    - 如果你有现有的 DNS 记录（例如现有网站），但你的 DNS 主机已启用 [domain connect](/office365/admin/get-help-with-domains/domain-connect)，请选择“**为我添加记录**”。 在“**选择联机服务**”页面上，接受所有默认设置，选择“**下一步**”，然后在DNS 主机页面上选择“**授权**”。
    - 如果具有具有其他 DNS 主机的现有 DNS 记录（未对域连接启用），需要管理自己的 DNS 记录以确保现有服务保持连接。有关详细信息，请参阅[域基础知识](/office365/admin/get-help-with-domains/dns-basics)。

2. 请按照向导中的步骤进行操作，然后将为你设置电子邮件和其他服务。

    注册过程完成后，你将转到管理中心，按照向导安装 Office 应用、添加域、添加用户和分配许可证。 完成初始设置后，可使用管理中心中的“**设置**”页面，继续设置和配置订阅附带的服务。

    有关设置向导和管理中心“**设置**”页面的详细信息，请参阅 [设置向导和设置页面之间的区别](o365-setup-wizard-and-setup-page.md)。

## <a name="watch-set-up-business-email-with-a-new-domain"></a>观看：使用新域设置业务电子邮件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA]

## <a name="steps-set-up-business-email-with-a-new-domain"></a>步骤：使用新域设置业务电子邮件

1. 从 Microsoft 365 商业标准版注册的 **如何登录** 页面中，选择“**创建新的业务电子邮件帐户（高级）**”。

2. 按照步骤购买新域并输入要使用的域名（如 contoso.com）。 完成购买域后，可以 [添加用户和许可证](../add-users/add-users.md) 并在管理中心内安装 Office 应用。

## <a name="finish-setting-up"></a>完成设置

按照以下步骤设置 Outlook、Teams、OneDrive 和网站。

### <a name="step-set-up-outlook-for-email"></a>观看：设置 Outlook，以使用电子邮件功能

1. 在 Windows“开始”菜单上，搜索并选择“Outlook”。

    （如果使用的是 Mac，请从工具栏打开 Outlook 或使用 Finder 进行查找。）

    如果刚刚安装了 Outlook，请在欢迎页面上选择“**下一步**”。

2. 选择“**文件**”\>“**信息**”\>“**添加帐户**”。

3. 输入你的 Microsoft 电子邮件地址并选择“**连接**”。

## <a name="watch-set-up-outlook-for-email"></a>观看：设置 Outlook，以使用电子邮件功能

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

## <a name="watch-import-and-redirect-email"></a>观看：导入和重定向电子邮件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
请参阅[使用 Outlook 导入电子邮件](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)，了解有关详细信息。

还可以使用 Exchange 管理中心导入每个人的电子邮件。 有关详细信息，请参阅[迁移多个电子邮件帐户](/Exchange/mailbox-migration/mailbox-migration)。

## <a name="set-up-microsoft-teams-and-onedrive-for-business"></a>设置 Microsoft Teams 和 OneDrive for Business

从任务栏中选择 OneDrive 云图标，然后按照步骤将文件移动到新的 OneDrive for Business 文件夹。选择“**下一步**”以设置 Microsoft Teams。

1. 打开 Microsoft Teams，选择个人资料图标，然后 **添加工作或学校帐户**。 按照步骤将新帐户添加到 Teams。

## <a name="use-a-public-website"></a>使用公共网站

Microsoft 365 不提供适用于公司的公共网站。 如需设置一个公共网站，请考虑使用 GoDaddy 或 WIX 等 Microsoft 合作伙伴。
  
1. 从管理中心，转到“**资源**”，然后选择“**公共网站**”。

2. 在其中一个选项下选择“**了解详细信息**”，然后注册网站合作伙伴，并使用其工具设置和设计你的网站。

## <a name="watch-create-your-business-website"></a>观看：创建企业网站

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a>相关内容

[将数据迁移到 Microsoft 365 商业标准版订阅](../simplified-signup/migrate-data-business-standard.md)

[注册 Microsoft 365 商业标准版订阅](../simplified-signup/signup-business-standard.md)

[接受对 Microsoft 365 商业标准版订阅（用户）的邀请](../simplified-signup/user-invite-business-standard.md)
