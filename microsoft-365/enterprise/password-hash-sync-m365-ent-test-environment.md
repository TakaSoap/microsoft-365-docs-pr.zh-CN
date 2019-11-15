---
title: Microsoft 365 测试环境的密码哈希同步
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置和展示 Microsoft 365 测试环境的密码哈希同步和登录。
ms.openlocfilehash: ad48a11684903c65fb6d8e07a4e7a3c2523a153f
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639812"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的密码哈希同步

许多组织使用 Azure AD Connect 和密码哈希同步来同步他们内部部署的 Active Directory 域服务 (AD DS) 林账户集与 Office 365 和 EMS E5 订阅的 Azure AD 租户账户集。 本文介绍了如何添加密码哈希同步至 Microsoft 365 测试环境，从而生成以下配置：
  
![使用密码哈希同步测试环境的模拟企业配置](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
此测试环境的设置分为以下两个阶段：
  
1. 创建 Microsoft 365 模拟企业测试环境。
2. 在 APP1 上安装和配置 Azure AD Connect。
    
> [!TIP]
> 单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>第 1 阶段：创建 Microsoft 365 模拟企业测试环境

请按照[适用于 Microsoft 365 的模拟企业基础配置](simulated-ent-base-configuration-microsoft-365-enterprise.md)中的说明操作。生成的配置如下。
  
![模拟企业基础配置](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
此配置包括： 
  
- Office 365 E5 和 EMS E5 试用订阅或付费订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络中的 DC1、APP1 和 CLIENT1 虚拟机。 DC1 是 testlab.\<你的公共域名 > AD DS 域的域控制器。

## <a name="phase-2-create-and-register-the-testlab-domain"></a>第 2 阶段：创建和注册 testlab 域

在这一阶段，将公共 DNS 域添加到订阅中。

首先，使用公共 DNS 注册提供程序，根据当前域名新建一个公共 DNS 域名，并将它添加到 Office 365 订阅中。建议命名为 **testlab.**\<公共域名>。例如，如果公共域名是 <span>**contoso</span>.com**，请添加公共域名 **<span>testlab</span>.contoso.com**。
  
接下来，通过域注册过程添加**testlab.**\<公共域 > 域到 Office 365 试用版或付费订阅。 这包括添加其他 DNS 记录到**testlab.**\<公共域 > 域。 有关详细信息，请参阅[添加用户和域到 Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。 

下面是生成的配置。
  
![注册 testlab 域名](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
此配置包括：

- 包含已注册 DNS 域 testlab.\<你的公共域名> 的 Office 365 E5 和 EMS E5 试用订阅或付费订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。

请注意，现在 testlab.\<你的公共域名>：

- 受公共 DNS 记录支持。
- 在 Office 365 和 EMS 订阅中进行了注册。
- 是模拟 Intranet 上的 AD DS 域。
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>第 3 阶段：在 APP1 上安装 Azure AD Connect

在这一阶段，在 APP1 上安装和配置 Azure AD Connect 工具，并验证它能否正常工作。
  
首先，在 APP1 上安装和配置 Azure AD Connect。

1. 在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，再使用 TESTLAB\\User1 帐户连接到 APP1。
    
2. 在 APP1 的桌面中，打开管理员级 Windows PowerShell 命令提示符，然后运行下面这些命令：
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. 从任务栏中单击 **Internet Explorer**，然后转到 [https://aka.ms/aadconnect](https://aka.ms/aadconnect)。
    
4. 在“Microsoft Azure Active Directory Connect”页上，单击“下载”****，然后单击“运行”****。
    
5. 在“欢迎使用 Azure AD Connect”**** 页上，单击“我同意”****，然后单击“继续”****。
    
6. 在“快速设置”**** 页上，单击“使用快速设置”****。
    
7. 在“连接到 Azure AD”**** 页上，在“用户名”**** 中键入 Office 365 全局管理员帐户名，在“密码”**** 中键入密码，再单击“下一步”****。
    
8. 在“连接到 AD DS”**** 页上，在“用户名”**** 中键入“TESTLAB\\User1”****，在“密码”**** 中键入密码，再单击“下一步”****。
    
9. 单击“配置就绪”**** 页上的“安装”****。
    
10. 在“配置完成”**** 页上，单击“退出”****。
    
11. 在 Internet Explorer 中，转到 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))。
    
12. 在左侧导航窗格中，单击“**用户 > 活动用户**”。
    
    请注意，该帐户名为**用户 1**。 此帐户来自 TESTLAB AD DS 域，证明目录同步已正常工作。
    
13. 单击 **User1** 帐户。对于产品许可证，请单击“编辑”****。
    
14. 在“产品许可证”**** 中，选择所在的国家/地区，再单击“Office 365 企业版 E5”**** 的“关”**** 控件（将它切换为“开”****）。对“企业移动性 + 安全性 E5”**** 许可证执行相同的操作。 

15. 依次单击页面底部的“**保存**”和“**关闭**”。
    
接下来，使用 User1 帐户的用户名“<strong>user1@testlab.</strong>\<域名>”，测试能否登录 Office 365 订阅。

1. 在 APP1 中，注销 Office 365，再重新登录，这次指定不同的帐户。

2. 当系统提示输入用户名和密码时，指定 <strong>user1@testlab.</strong>\<你的公共域名> 和 User1 密码。应该能以 User1 身份成功登录。 
 
请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是 Office 365 全局管理员。 因此，不会看到作为一个选项的**管理员**图标。 

下面是生成的配置。

![使用密码哈希同步的测试环境的模拟企业配置](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

此配置包括： 
  
- 包含已注册 DNS 域 TESTLAB.\<域名> 的 Office 365 E5 和 EMS E5 试用订阅或付费订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。 在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域周期性同步到 Office 365 和 EMS E5 订阅的 Azure AD 租户。
- TESTLAB  AD DS 域中的 User1 帐户已与 Azure AD 租户同步。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)


