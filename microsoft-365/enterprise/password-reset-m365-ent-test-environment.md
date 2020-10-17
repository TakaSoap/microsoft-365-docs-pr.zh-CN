---
title: Microsoft 365 测试环境的密码重置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
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
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的密码重置。
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487420"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Microsoft 365 测试环境的密码重置

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

借助 Azure Active Directory (Azure AD) 自助服务密码重置 (SSPR)，用户可重置或解锁其密码或帐户。

本文介绍如何在 Microsoft 365 测试环境中配置和测试密码重置。

设置 SSPR 包括三个阶段：
- [阶段 1：为 Microsoft 365 测试环境配置密码哈希同步](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [阶段 2：启用密码写回](#phase-2-enable-password-writeback)
- [第 3 阶段：配置和测试密码重置](#phase-3-configure-and-test-password-reset)
    
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

首先，按照 " [密码哈希同步](password-hash-sync-m365-ent-test-environment.md)" 中的说明操作。 

生成的配置如下所示：
  
![使用密码哈希同步测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。
- 在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Active Directory 域服务 (AD DS) 域同步到 Microsoft 365 订阅的 Azure AD 租户。

## <a name="phase-2-enable-password-writeback"></a>阶段 2：启用密码写回

接下来，按照[“密码写回”测试实验室指南的阶段 2](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) 中的说明进行操作。

必须启用密码写回才能使用密码重置。
  
## <a name="phase-3-configure-and-test-password-reset"></a>第 3 阶段：配置和测试密码重置

在此阶段中，通过组成员身份在 Azure AD 租户中配置密码重置，然后验证它是否正常工作。

首先，为特定 Azure AD 组中的帐户启用密码重置。

1. 在浏览器的专用实例中，打开 [https://portal.azure.com](https://portal.azure.com)，然后使用全局管理员帐户的凭据登录。
2. 在 azure 门户中，选择 " **azure Active Directory**  >  **组**  >  **新组**"。
3. 将“**组类型**”设置为“**安全**”，将“**组名称**”设置为“**PWReset**”，将“**成员身份类型**”设置为“**已分配**”。
4. 选择 " **成员**"，查找并选择 " **用户 3**"，选择 " **选择**"，然后选择 " **创建**"。
5. 关闭“**组**”窗格。
6. 在 "Azure Active Directory" 窗格中，选择左侧导航栏中的 " **密码重置** "。
7. 在“**密码重置属性**”窗格的“**已启用自助式密码重置**”选项下，选中“**已选择**”。
8. 选择 "**选择组**"，选择 " **PWReset** " 组，然后选择 "**选择**  >  **保存**"。
9. 关闭专用浏览器实例。

接下来，为用户3帐户测试密码重置。

1. 打开新的专用浏览器实例并浏览到 [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup)。
1. 使用用户 3 帐户凭据登录。
1. 在 " **需要详细信息**" 中，选择 " **下一步**"。 
1. 在“不丢失对帐户的访问权限”**** 中，将身份验证电话设置为你的移动电话号码，并将身份验证电子邮件地址设置为你的工作或个人电子邮件帐户。
1. 经过验证后，选择 " **外观**"，然后关闭浏览器的专用实例。
1. 在新的专用浏览器实例中，转到 [https://aka.ms/sspr](https://aka.ms/sspr) 。
1. 输入用户3帐户名称，输入 CAPTCHA 中的字符，然后选择 " **下一步**"。
1. 对于 **验证步骤 1**，请选择 **"电子邮件-我的备用电子邮件**"，然后选择 " **电子邮件**"。 当您收到电子邮件时，请输入验证代码，然后选择 " **下一步**"。
1. 在 " **返回到帐户**" 中，为用户3帐户输入一个新密码，然后选择 " **完成**"。 记下已更改的用户 3 帐户密码并将其存储在安全的位置。
1. 在同一浏览器的独立选项卡中，转到 [https://portal.office.com](https://portal.office.com)，然后使用用户 3 帐户名及其新密码登录。 应该会看到“Microsoft Office 主页”页面。****

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
