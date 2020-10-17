---
title: Microsoft 365 测试环境的密码写回
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 摘要：配置 Microsoft 365 测试环境的密码写回。
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487124"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的密码写回

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

用户可以使用密码写回通过 Azure Active Directory (Azure AD) （然后将其复制到本地 Active Directory 域服务 (AD DS) ）更新其密码。通过密码写回，用户无需通过内部部署 AD DS （其中存储其原始用户帐户）来更新其密码。这有助于不具有到本地网络的远程访问连接的漫游或远程用户。

本文介绍如何为您的 Microsoft 365 测试环境配置密码写回。

配置密码写回的测试环境包括两个阶段：
- [阶段 1：为 Microsoft 365 测试环境配置密码哈希同步](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [阶段 2：为 TESTLAB AD DS 域启用密码写回](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

首先，按照 " [密码哈希同步](password-hash-sync-m365-ent-test-environment.md)" 中的说明操作。生成的配置如下所示：
  
![使用密码哈希同步测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。
- 在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域同步到 Microsoft 365 订阅的 Azure AD 租户。

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>阶段 2：为 TESTLAB AD DS 域启用密码写回

首先，使用全局管理员角色配置用户 1 帐户。

1. 通过 [Microsoft 365 管理中心](https://portal.microsoft.com)使用全局管理员帐户进行登录。

2. 选择 " **活动用户**"。
 
3. 在 " **活动用户** " 页上，选择 **user1** 帐户，

4. 在 " **user1** " 窗格中，选择 "**角色**" 旁边的 "**编辑**"。

5. 在用户1的 " **编辑用户角色** " 窗格中，选择 " **全局管理员**"，选择 " **保存**"，然后选择 " **关闭**"。

接下来，使用允许用户 1 代表 TESTLAB AD DS 域中的其他用户更改密码的安全设置来配置用户 1 帐户。

1. 在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。

2. 在 APP1 的桌面上，选择 " **开始**"，输入 " **活动**"，然后选择 " **active Directory 用户和计算机**"。

3. 在菜单栏上，选择 " **查看**"。 如果未启用 **高级功能** ，请选择该功能以启用它。

4. 在树窗格中，选择并按住 (或右键单击) 您的域，选择 " **属性**"，然后选择 " **安全** " 选项卡。

5. 选择“高级”****。

6. 在 " **权限** " 选项卡上，选择 " **添加**"。

7. 选择 " **选择主体**"，输入 **User1**，然后选择 **"确定"**。

8. 在“**适用于**”中，选择“**后代用户对象**”。

9. 在“**权限**”下，选择以下内容：

    - **更改密码**
    - **重置密码**

10. 在“**属性**”下，选择以下内容：
    - **写入 lockoutTime**
    - **写入 pwdLastSet**

11. 选择 **"确定"** 三次，以保存更改。

12. 关闭 **Active Directory 用户和计算机**。

接下来，在 APP1 上对 Azure AD Connect 进行密码写回配置。

1. 如果需要，使用 TESTLAB \ User1 帐户连接到 APP1。

2. 在 APP1 的桌面上，双击“**Azure AD Connect**”。

3. 在 " **欢迎" 页**上，选择 " **配置**"。

4. 在 " **其他任务** " 页上，选择 " **自定义同步选项**"，然后选择 " **下一步**"。

5. 在 " **连接到 AZURE AD** " 页上，输入全局管理员帐户凭据，然后选择 " **下一步**"。

6. 在 " **连接目录** 和 **域/OU 筛选** " 页上，选择 " **下一步**"。

7. 在 " **可选功能** " 页上，选择 " **密码写回**"，然后选择 " **下一步**"。

8. 在 " **准备配置** " 页上，选择 " **配置** 并等待该过程完成"。

9. 当您看到配置完成时，选择 " **退出**"。

现在，您可以为未连接到模拟 intranet 的虚拟网络的计算机上的用户测试密码写回。

生成的配置如下所示：

![使用传递身份验证测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

此配置包括：

- 使用 DNS 域 TESTLAB 的 Microsoft 365 E5 试用版或付费订阅。\<*your domain name*> 。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。
- 在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Microsoft 365 订阅同步到 TESTLAB AD DS 域。
- 已启用密码写回，因此用户可以通过 Azure AD 更改其密码，而无需连接到简化的 Intranet。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)


