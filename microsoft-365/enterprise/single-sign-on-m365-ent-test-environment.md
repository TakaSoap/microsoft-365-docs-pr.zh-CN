---
title: 适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录。
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487596"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录

*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*

Azure AD 无缝单一 Sign-On (无缝 SSO) 当用户位于连接到其组织网络的 Pc 或设备上时，会自动登录用户。Azure AD 无缝 SSO 为用户提供了对基于云的应用程序的轻松访问，而无需任何其他本地组件。

本文介绍如何为 Azure AD 无缝 SSO 配置 Microsoft 365 测试环境。

设置 Azure AD 无缝 SSO 包含两个阶段：
- [阶段 1：为 Microsoft 365 测试环境配置密码哈希同步](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

按照 [针对 Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明进行操作。 

生成的配置如下所示：
  
![使用密码哈希同步测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。
- Azure AD Connect 在 APP1 上运行，以定期将 TESTLAB Active Directory 域服务 (AD DS) 域同步到 Microsoft 365 订阅的 Azure AD 租户。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO

在此阶段，在 APP1 上为 Azure ad 无缝 SSO 配置 Azure AD Connect，然后验证它是否正常工作。

### <a name="configure-azure-ad-connect-on-app1"></a>在 APP1 上配置 Azure AD Connect

1. 在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。

2. 在 APP1 桌面中，运行 Azure AD Connect。

3. 在 " **欢迎" 页**上，选择 " **配置**"。

4. 在 " **其他任务** " 页上，选择 " **更改用户登录**"，然后选择 " **下一步**"。

5. 在 " **连接到 AZURE AD** " 页上，输入全局管理员帐户凭据，然后选择 " **下一步**"。

6. 在 " **用户登录** " 页上，选择 " **启用单一登录**"，然后选择 " **下一步**"。

7. 在 " **启用单一登录** " 页上，选择 " **输入凭据**"。

8. 在 " **Windows 安全性** " 对话框中，输入 **user1** 和 user1 帐户的密码，选择 **"确定**"，然后选择 " **下一步**"。

9. 在 " **准备配置** " 页上，选择 " **配置**"。

10. 在 " **配置完成** " 页上，选择 " **退出**"。

11. 从 Azure 门户的左侧窗格中，选择 " **azure Active Directory**  >  **azure AD Connect**"。 验证 **无缝单一登录** 功能是否显示为 " **已启用**"。

接下来，测试使用 user1@testlab 登录订阅的功能 <strong>。</strong>\<*your public domain*> 测试能否登录订阅。

1. 在 APP1 上的 Internet Explorer 中，选择 "设置" 图标，然后选择 " **Internet 选项**"。
 
2. 在 " **Internet 选项**" 中，选择 " **安全** " 选项卡。

3. 选择 " **本地 intranet**"，然后选择 " **网站**"。

4. 在 " **本地 intranet**" 中，选择 " **高级**"。

5. 在 "**将该网站添加到区域**中" 中，输入**https：<span>//</span>autologon.microsoftazuread-sso.com**，选择 "**添加**  >  **关闭**  >  **"** 确定  >  **"确定"**。

6. 注销，再重新登录，这次指定不同的帐户。

7. 当系统提示您登录时，请指定 <strong>user1@testlab。</strong>\<*your public domain*> 名称，然后选择 " **下一步**"。 应能够以 User1 身份成功登录，且不会看到密码输入提示。 这就证明无缝 SSO 能正常运行。

请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是 Azure AD 全局管理员。 因此，不会看到作为一个选项的**管理员**图标。

下面是生成的配置：

![使用传递身份验证测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

此配置包括：

- 使用 DNS 域 testlab 的 Microsoft 365 E5 试用版或付费订阅。\<*your domain name*> 。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。
- 在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Microsoft 365 订阅同步到 TESTLAB AD DS 域。
- 启用了 Azure AD 无缝 SSO，以便模拟的 intranet 上的计算机可以登录到 Microsoft 365 云资源，而无需指定用户帐户密码。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
