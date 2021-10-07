---
title: Microsoft 365 测试环境的密码重置
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/13/2019
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
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的密码重置。
ms.openlocfilehash: 9aa55f42ca295577bf3b1c81ee54b1160adf3d27
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198369"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的密码重置

*本测试实验室指南只能用于Microsoft 365测试环境。*

借助 Azure Active Directory (Azure AD) 自助服务密码重置 (SSPR)，用户可重置或解锁其密码或帐户。

本文介绍如何在测试环境中配置和测试密码Microsoft 365重置。

设置 SSPR 包括三个阶段：
- [阶段 1：为 Microsoft 365 测试环境配置密码哈希同步](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [阶段 2：启用密码写回](#phase-2-enable-password-writeback)
- [第 3 阶段：配置和测试密码重置](#phase-3-configure-and-test-password-reset)
    
![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

首先，按照密码哈希 [同步 中的说明操作](password-hash-sync-m365-ent-test-environment.md)。 

生成的配置如下所示：
  
![密码哈希同步测试环境的模拟企业。](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。
- 在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Active Directory 域服务 (AD DS) 域同步到 Microsoft 365 订阅的 Azure AD 租户。

## <a name="phase-2-enable-password-writeback"></a>阶段 2：启用密码写回

接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。

必须启用密码写回才能使用密码重置。
  
## <a name="phase-3-configure-and-test-password-reset"></a>第 3 阶段：配置和测试密码重置

在此阶段，通过组成员身份在 Azure AD 租户中配置密码重置，然后验证其是否正常工作。

首先，为特定 Azure AD 组中的帐户启用密码重置。

1. 在浏览器的专用实例中，打开 [https://portal.azure.com](https://portal.azure.com)，然后使用全局管理员帐户的凭据登录。
2. 在 Azure 门户中，选择 **"Azure Active Directory**  >  **组**  >  **""新建组"。**
3. 将“**组类型**”设置为“**安全**”，将“**组名称**”设置为“**PWReset**”，将“**成员身份类型**”设置为“**已分配**”。
4. 选择 **"成员**"，查找并选择 **"用户 3"，** 选择 **"选择**"，然后选择"创建 **"。**
5. 关闭“**组**”窗格。
6. 在"Azure Active Directory窗格中，选择左侧 **导航栏中的"** 密码重置"。
7. 在“**密码重置属性**”窗格的“**已启用自助式密码重置**”选项下，选中“**已选择**”。
8. 选择 **"选择组"，** 选择 **"PWReset"** 组，然后选择"**保存**  >  **"。**
9. 关闭专用浏览器实例。

接下来，为用户 3 帐户测试密码重置。

1. 打开新的专用浏览器实例并浏览到 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。
1. 使用用户 3 帐户凭据登录。
1. 在 **"需要更多信息"中**，选择"下 **一步"。** 
1. 在“不丢失对帐户的访问权限”中，将身份验证电话设置为你的移动电话号码，并将身份验证电子邮件地址设置为你的工作或个人电子邮件帐户。
1. 验证两者后，选择" **外观良好**"，然后关闭浏览器的专用实例。
1. 在新的专用浏览器实例中，转到 [https://aka.ms/sspr](https://aka.ms/sspr) 。
1. 输入用户 3 帐户名，输入 CAPTCHA 中的字符，然后选择"下一步 **"。**
1. 对于 **验证步骤 1，** 选择 **"通过电子邮件发送我的备用电子邮件**"，然后选择"**电子邮件"。** 收到电子邮件时，输入验证码，然后选择"下一 **步"。**
1. 在 **"返回到你的帐户"中**，输入用户 3 帐户的新密码，然后选择"完成 **"。** 记下已更改的用户 3 帐户密码并将其存储在安全的位置。
1. 在同一浏览器的独立选项卡中，转到 [https://admin.microsoft.com](https://admin.microsoft.com)，然后使用用户 3 帐户名及其新密码登录。 应该会看到“Microsoft Office 主页”页面。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)