---
title: 适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录。
ms.openlocfilehash: a32dca8c37d9e6788aef801e9f99a90b724e86b1
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757669"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录

*此测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*

Azure AD 无缝单一登录 (SSO) 自动将连接到组织网络的 PC 或设备上的用户登入。借助 Azure AD 无缝 SSO，用户无需使用其他任何本地组件，即可轻松访问基于云的应用程序。

本文介绍了如何为 Microsoft 365 测试环境配置 Azure AD 无缝 SSO。

此设置包含两个阶段：

1.  创建采用密码哈希同步的 Microsoft 365 模拟企业测试环境。
2.  为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO。
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

按照 [Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括： 
  
- Microsoft 365 E5 或 Office 365 E5 试用版或付费版订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。 
- 在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Active Directory 域服务 (AD DS) 定期同步到 Microsoft 365 或 Office 365 订阅的 Azure AD 租户。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO

在这一阶段，为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO，再验证此功能是否正常运行。

### <a name="configure-azure-ad-connect-on-app1"></a>配置 APP1 上的 Azure AD Connect

1. 在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。

2. 在 APP1 的桌面上，运行 Azure AD Connect。

3. 在“**欢迎页**”上，单击“**配置**”。

4. 在“其他任务”页上，依次单击“更改用户登录”和“下一步”。************

5. 在“**连接到 Azure AD**”页面上，键入全局管理员帐户凭据，然后单击“**下一步**”。

6. 在“用户登录”**** 页上，选择“启用单一登录”****，再单击“下一步”****。

7. 在“启用单一登录”**** 页上，单击“输入凭据”****。

8. 在“Windows 安全中心”**** 对话框中，键入“user1”**** 和 user1 帐户的密码，再依次单击“确定”**** 和“下一步”****。

9. 在“准备配置”**** 页上，单击“配置”****。

10. 在“配置完成”**** 页上，单击“退出”****。

11. 在 Azure 门户内的左侧窗格中，依次单击“Azure Active Directory”和“Azure AD Connect”****。验证“无缝单一登录”**** 功能的状态是否为“已启用”****。

接下来，测试能否使用 User1 帐户的用户名 <strong>user1@testlab.</strong>\<公共域名> 登录 Office 365 订阅。

1. 在 APP1 上，依次单击 Internet Explorer 中的设置图标和“Internet 选项”****。
 
2. 单击“Internet 选项”**** 中的“安全”**** 选项卡。

3. 依次单击“本地 Intranet”**** 和“网站”****。

4. 单击“本地 Intranet”**** 中的“高级”****。

5. 在“将此网站添加到区域”**** 中，键入“https**<span>://autologon.microsoftazuread-sso.com</span>**”，再依次单击“添加”、“关闭”、“确定”和“确定”****。

6. 注销 Office 365，再重新登录，这次指定不同的帐户。

7. 当出现登录提示时，指定用户名 <strong>user1@testlab.</strong>\<公共域> 名称，再单击“下一步”****。 应能够以 User1 身份成功登录，且不会看到密码输入提示。 这就证明无缝 SSO 能正常运行。

请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是  Azure AD 和 Office 365 全局管理员。 因此，不会看到作为一个选项的**管理员**图标。

下面是生成的配置：

![使用传递身份验证测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
此配置包括：

- 包含已注册 DNS 域 testlab.\<你的域名> 的 Microsoft 365 E5 或 Office 365 E5 试用订阅或付费订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。 
- 在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Microsoft 365 或 Office 365 订阅同步到 TESTLAB AD DS 域。 
- 已启用的 Azure AD 无缝 SSO，这样模拟 Intranet 上的计算机无需指定用户帐户密码，即可登录 Microsoft 365 云资源。

若要了解如何在生产中配置 Azure AD 无缝 SSO 和相关链接，请参阅“标识”阶段中的[简化用户登录](identity-secure-your-passwords.md#identity-sso)步骤。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)


