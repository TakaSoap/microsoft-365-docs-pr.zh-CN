---
title: Microsoft 365 测试环境的密码哈希同步
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 摘要：配置和展示 Microsoft 365 测试环境的密码哈希同步和登录。
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487454"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的密码哈希同步

*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*

许多组织使用 Azure AD Connect 和密码哈希同步来同步他们内部部署的 Active Directory 域服务 (AD DS) 林帐户集与 Microsoft 365 订阅的 Azure AD 租户帐户集。 

本文介绍如何将密码哈希同步添加到 Microsoft 365 测试环境中，这将导致此配置：
  
![使用密码哈希同步测试环境的模拟企业配置](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
设置此测试环境涉及三个阶段：
- [第 1 阶段：创建 Microsoft 365 模拟企业测试环境](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [第 2 阶段：创建和注册 testlab 域](#phase-2-create-and-register-the-testlab-domain)
- [第 3 阶段：在 APP1 上安装 Azure AD Connect](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>第 1 阶段：创建 Microsoft 365 模拟企业测试环境

按照 [模拟企业基本配置中有关 Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md)的说明进行操作。 生成的配置如下所示：
  
![模拟企业基础配置](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络中的 DC1、APP1 和 CLIENT1 虚拟机组成。 DC1 是 testlab 的域控制器。 <*公共域名*> AD DS 域。

## <a name="phase-2-create-and-register-the-testlab-domain"></a>第 2 阶段：创建和注册 testlab 域

在此阶段中，添加一个公共 DNS 域，然后将其添加到你的订阅。

首先，使用您的公共 DNS 注册提供程序创建基于您的当前域名的新的公共 DNS 域名，然后将其添加到订阅中。 建议使用名称**testlab <*公共域* > **。 例如，如果您的公用域名是** <span>contoso</span>.com**，请添加公共域名： ** <span>testlab</span>. contoso.com**。
  
接下来，通过域注册过程将 **<testlab*公共域* > **域添加到 Microsoft 365 试用版或付费订阅。 这包括向 testlab 添加其他 DNS 记录 **。 <*公共域* > **域。 有关详细信息，请参阅 [将域添加到 Microsoft 365](../admin/setup/add-domain.md)。

生成的配置如下所示：
  
![注册 testlab 域名](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
此配置包括：

- 带有 DNS 域 testlab 的 Microsoft 365 E5 试用版或付费订阅。> 注册 *公共域名* <。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。

请注意，<您的 *公共域名*> 现在是：

- 受公共 DNS 记录支持。
- 已在 Microsoft 365 订阅中注册。
- 是模拟 Intranet 上的 AD DS 域。
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>第 3 阶段：在 APP1 上安装 Azure AD Connect

在此阶段，在 APP1 上安装并配置 Azure AD Connect 工具，然后验证它是否正常工作。
  
首先，在 APP1 上安装和配置 Azure AD Connect。

1. 在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，再使用 TESTLAB\\User1 帐户连接到 APP1。
    
2. 在 APP1 的桌面中，打开管理员级 Windows PowerShell 命令提示符，然后运行下面这些命令来禁用 Internet Explorer 增强安全：
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. 在任务栏中，选择 " **Internet Explorer** "，然后转到 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。
    
4. 在 "Microsoft Azure Active Directory Connect" 页上，选择 " **下载**"，然后选择 " **运行**"。
    
5. 在 " **欢迎使用 AZURE AD Connect** " 页上，选择 " **我同意**"，然后选择 " **继续**"。
    
6. 在 " **快速设置** " 页上，选择 " **使用快速设置**"。
    
7. 在 " **连接到 AZURE AD** " 页上，在 **"用户名"** 中输入全局管理员帐户名称，在 " **密码**" 中输入密码，然后选择 " **下一步**"。
    
8. 在 "**连接到 AD DS** " 页上，在 **"用户名"** 中输入**TESTLAB \\ User1** ，在 "**密码**" 中输入密码，然后选择 "**下一步**"。
    
9. 在 " **准备配置** " 页上，选择 " **安装**"。
    
10. 在 " **配置完成** " 页上，选择 " **退出**"。
    
11. 在 Internet Explorer 中，转到 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))。
    
12. 在左侧导航窗格中，选择 " **用户 > 活动用户**"。
    
    请注意，该帐户名为**用户 1**。 此帐户来自 TESTLAB AD DS 域，证明目录同步已正常工作。
    
13. 选择 **User1** 帐户，然后选择 " **许可证和应用**"。
    
14. 在 " **产品许可证**" 中，选择您的位置 (如果需要) ，请禁用 **Office 365 e5** 许可证，然后启用 **Microsoft 365 e5** 许可证。 

15. 选择页面底部的 " **保存** "，然后选择 " **关闭**"。
    
接下来，测试使用 user1@testlab 登录订阅的功能 **。 <*您的域名* > **用户名的 user1 帐户：

1. 在 APP1 中，注销，再重新登录，这次指定不同的帐户。

2. 当系统提示输入用户名和密码时，请指定**user1@testlab。 <*你的域名* > **和 user1 密码。 你应该能以 User1 身份成功登录。
 
请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是全局管理员。 因此，不会看到作为一个选项的**管理员**图标。 

生成的配置如下所示：

![使用密码哈希同步测试环境的模拟企业配置](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

此配置包括： 
  
- Microsoft 365 E5 或 Office 365 E5 试用版或带 DNS 域 TESTLAB 的付费订阅。> 注册 <*您的域名* 。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。 Azure AD Connect 在 APP1 上运行，以定期将 TESTLAB AD DS 域同步到 Microsoft 365 订阅的 Azure AD 租户。
- TESTLAB  AD DS 域中的 User1 帐户已与 Azure AD 租户同步。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
