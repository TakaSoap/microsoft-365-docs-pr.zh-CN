---
title: Microsoft 365 测试环境的密码重置
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的密码重置。
ms.openlocfilehash: 30ce8517d1b0eb8967bd7cb26abba780d81eb8b0
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353149"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的密码重置

借助 Azure Active Directory (Azure AD) 自助服务密码重置 (SSPR)，用户可重置或解锁其密码或帐户。 

本文介绍如何分三个阶段在 Microsoft 365 测试环境中配置和测试密码重置：

1.  创建 Microsoft 365 企业版测试环境。
2.  启用密码写回。
3.  为用户 2 帐户配置和测试密码重置。
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

首先，按照[密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括： 
  
- Office 365 E5 和 EMS E5 试用订阅或付费订阅。
- 连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。 
- 在 APP1 上运行的 Azure AD Connect，它用于将 TESTLAB Active Directory 域服务 (AD DS) 同步到 Office 365 和 EMS E5 订阅的 Azure AD 租户。


## <a name="phase-2-enable-password-writeback"></a>阶段 2：启用密码写回

接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。

必须启用密码写回才能使用密码重置。
  
## <a name="phase-3-configure-and-test-password-reset"></a>第 3 阶段：配置和测试密码重置

在这一阶段，通过组成员身份在 Azure AD 租户中配置密码重置，然后验证它是否能够正常工作。

首先，为特定 Azure AD 组中的帐户启用密码重置。

1. 在浏览器的专用实例中，打开 [https://portal.azure.com](https://portal.azure.com)，然后使用全局管理员帐户的凭据登录。
2. 在 Azure 门户中，单击“Azure Active Directory”>“组”>“新组”****。
3. 将“组类型”**** 设置为“安全”****，将“组名称”**** 设置为“PWReset”****，将“成员身份类型”**** 设置为“分配”****。单击“创建”****。
5. 单击列表中的“PWReset”**** 组，然后单击“成员”****。
6. 依次单击“添加成员”****、“用户 2”****，再单击“选择”****。关闭“PWReset”**** 和“组”**** 页。
7. 在 Azure Active Directory 页上，单击“密码重置”****。
8. 在“属性”**** 页的“自助服务密码重置已启用”**** 选项下，选择“已选择”****。
9. 从“选择组”**** 中选择“PWReset”****，然后单击“保存”****。
10. 关闭专用浏览器实例。

接下来，为用户 2 帐户测试密码重置。

1. 打开新的专用浏览器实例并浏览到 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。
2. 使用用户 2 帐户凭据登录。
3. 在“不丢失对帐户的访问权限”**** 中，将身份验证电话设置为你的手机号码，并将身份验证电子邮件设置为你的工作或个人电子邮件帐户。
4. 对这两项进行验证后，单击“良好”****，然后关闭浏览器的专用实例。
5. 打开新的专用浏览器实例并转到 [https://aka.ms/sspr](https://aka.ms/sspr)
6. 使用用户 2 帐户凭据登录，键入 CAPTCHA 中的字符，然后单击“下一步”****。
8. 对于“验证步骤 1”****，单击“以电子邮件形式发送备用电子邮件”****，然后单击“电子邮件”****。在收到电子邮件时，键入验证码，然后单击“下一步”****。
9. 在“返回到帐户”**** 中，键入用户 2 帐户的新密码，然后单击“完成”****。记录用户 2 帐户更改后的密码，然后将其存储在一个安全的位置。
10. 在同一浏览器的独立选项卡中，转到 [https://portal.office.com](https://portal.office.com)，然后使用用户 2 帐户名及其新密码登录。 此时应会看到“**Microsoft Office 主页**”页面。

有关在生产中配置密码重置的信息和相关链接，请参阅“标识”阶段中的[简化密码重置](identity-password-reset.md#identity-pw-reset)步骤。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
