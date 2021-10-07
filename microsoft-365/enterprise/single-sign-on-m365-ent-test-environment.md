---
title: 适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录。
ms.openlocfilehash: 4a420da5251ecef900f2efe9573db1d51a6bd597
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202819"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录

*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*

Azure AD 无缝Sign-On (无缝 SSO) 当用户位于连接到其组织网络的 PC 或设备上时，可自动登录用户。 Azure AD 无缝 SSO 使用户能够轻松访问基于云的应用程序，而无需任何其他本地组件。

本文介绍如何为 Azure AD 无缝 SSO Microsoft 365测试环境。

设置 Azure AD 无缝 SSO 涉及两个阶段：
- [阶段 1：为 Microsoft 365 测试环境配置密码哈希同步](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

按照密码哈希[同步中的说明操作Microsoft 365。](password-hash-sync-m365-ent-test-environment.md) 

生成的配置如下所示：
  
![密码哈希同步测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。
- Azure AD 连接 APP1 上运行，以定期将 TESTLAB Active Directory 域服务 (AD DS) 域同步到 Microsoft 365 订阅的 Azure AD 租户。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO

在此阶段中，在 APP1 连接 Azure AD 无缝 SSO 配置 Azure AD 策略，然后验证其是否正常工作。

### <a name="configure-azure-ad-connect-on-app1"></a>在 APP1 上配置 Azure AD Connect

1. 在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。

2. 从 APP1 桌面运行 Azure AD 连接。

3. 在"**欢迎"页上，** 选择"**配置"。**

4. 在"**其他任务"** 页上，选择 **"更改用户登录"，** 然后选择"下一 **步"。**

5. 在 **"连接 Azure AD"** 页上，输入全局管理员帐户凭据，然后选择"下一 **步"。**

6. 在"**用户登录"页上**，选择 **"启用单一登录"，** 然后选择"下一 **步"。**

7. 在"**启用单一登录"页上**，选择 **"输入凭据"。**

8. 在 **"Windows 安全中心"** 对话框中，输入 **user1** 和 user1 帐户的密码，选择"**确定**"，然后选择"下一 **步"。**

9. 在"**准备配置"页上，** 选择"配置 **"。**

10. 在"**配置完成"页上**，选择"退出 **"。**

11. 从 Azure 门户的左侧窗格中，选择"Azure Active Directory   >  **Azure AD 连接"。** 验证无缝 **单一登录** 功能是否显示为 **已启用**。

接下来，测试能否使用 user1@testlab <strong>登录订阅。</strong>\<*your public domain*> 测试能否登录订阅。

1. From Internet Explorer on APP1， select the settings icon， and then select **Internet Options**.
 
2. 在 **"Internet 选项"** 中，选择 **"安全"** 选项卡。

3. 选择 **"本地 Intranet"，** 然后选择"**网站"。**

4. 在本地 **Intranet 中**，选择"**高级"。**

5. 在 **"将此网站添加到区域"中**，输入 **https <span>：//</span>autologon.microsoftazuread-sso.com**，选择 **"添加**  >  **关闭**  >  **确定**  >  **"。**

6. 注销，再重新登录，这次指定不同的帐户。

7. 当系统提示登录时，指定 <strong>user1@testlab。</strong>\<*your public domain*> name，然后选择"下一 **步"。** 应能够以 User1 身份成功登录，且不会看到密码输入提示。 这就证明无缝 SSO 能正常运行。

请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是 Azure AD 全局管理员。 因此，不会看到作为一个选项的 **管理员** 图标。

下面是生成的配置：

![具有传递身份验证测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

此配置包括：

- 使用Microsoft 365 E5测试标签试用或付费订阅。\<*your domain name*> 。
- 连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。
- 在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Microsoft 365 订阅同步到 TESTLAB AD DS 域。
- Azure AD 无缝 SSO 已启用，以便模拟 Intranet 上的计算机无需指定用户帐户密码Microsoft 365登录到云资源。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)