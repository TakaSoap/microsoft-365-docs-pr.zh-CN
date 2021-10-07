---
title: Microsoft 365 测试环境的传递身份验证
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置 Microsoft 365 测试环境的传递身份验证。
ms.openlocfilehash: dcc23662683ffaf65a0ec5fa3698f729dc215af7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163356"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的传递身份验证

*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*

想要直接使用本地 Active Directory 域服务 (AD DS) 基础结构来进行对 Microsoft 云服务的身份验证的组织可以使用直通身份验证。 本文介绍了如何为直通身份验证配置 Microsoft 365 测试环境，生成的配置如下：
  
![具有传递身份验证测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
此测试环境的设置分为以下两个阶段：

1.    通过密码哈希同步创建 Microsoft 365 模拟企业测试环境。
2.    在 APP1 上对 Azure AD Connect 进行传递身份验证配置。
    
![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](../downloads/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

按照 [Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。
  
![密码哈希同步测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括： 
  
- Microsoft 365 E5试用版或付费订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。 在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域定期同步到 Microsoft 365 订阅的 Azure AD 租户。

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>阶段 2：在 APP1 上对 Azure AD Connect 进行传递身份验证配置

在该阶段，需在 APP1 上将 Azure AD Connect 配置为使用传递身份验证，然后验证该功能能否正常工作。

### <a name="configure-azure-ad-connect-on-app1"></a>在 APP1 上配置 Azure AD Connect

1.    在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。

2.    在 APP1 的桌面上，运行 Azure AD Connect。

3.    在“**欢迎页**”上，单击“**配置**”。

4.    在“其他任务”页面上，依次单击“**更改用户登录**”和“**下一步**”。

5.    在“**连接到 Azure AD**”页面上，键入全局管理员帐户凭据，然后单击“**下一步**”。

6.    在“**用户登录**”页面上，单击“**传递身份验证**”，然后单击“**下一步**”。

7.    在“**准备配置**”页面上，单击“**配置**”。

8.    在“**配置完成**”页面上，单击“**退出**”。

9.    在 Azure 门户的左窗格中，单击“**Azure Active Directory > Azure AD Connect**”。请验证 **传递身份验证** 功能的状态为“**已启用**”。

10.    单击“**传递身份验证**”。“**传递身份验证**”窗格中会列出身份验证代理所安装到的服务器。APP1 应该会出现在该列表中。关闭“**传递身份验证**”窗格。

接下来，测试能否使用 user1@testlab <strong>登录订阅。</strong>\<your public domain> 测试能否登录订阅。

1. 在 APP1 中，注销，再重新登录，这次指定不同的帐户。

2. 当系统提示输入用户名和密码时，指定 <strong>user1@testlab.</strong>\<your public domain> 和 User1 密码。 你应该能以 User1 身份成功登录。

请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是全局管理员。 因此，不会看到作为一个选项的 **管理员** 图标。

下面是生成的配置：

![具有传递身份验证测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
此配置包括：

- 使用Microsoft 365 E5测试标签试用或付费订阅。\<your domain name> 。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。身份验证代理在 APP1 上运行，以处理 Microsoft 365 订阅的 Azure AD 租户发出的直通身份验证请求。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)