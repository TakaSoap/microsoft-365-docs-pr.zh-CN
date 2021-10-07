---
title: 在企业测试环境中Microsoft 365全局管理员帐户
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用这些步骤来保护企业测试环境中Microsoft 365管理员帐户。
ms.openlocfilehash: e529304b9f897e4cac7a0cec5f32821b88cd297d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195313"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>在企业测试环境中Microsoft 365全局管理员帐户

*本测试实验室指南只能用于Microsoft 365测试环境。*

您可以通过确保管理员帐户尽可能安全来防止对组织的数字攻击。 

本文介绍如何使用 Azure AD Azure Active Directory (条件访问) 保护全局管理员帐户。

在企业测试Microsoft 365中保护全局管理员帐户包括两个阶段：
- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：配置条件访问策略](#phase-2-configure-conditional-access-policies)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果要使用最低要求的轻型方式测试全局管理员帐户保护，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中测试全局管理员帐户保护，请按照传递 [身份验证 中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试全局管理员帐户保护不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 。 它在此处作为一个选项提供，以便你可以测试全局管理员帐户保护，在代表典型组织的环境中试验它。 
  
## <a name="phase-2-configure-conditional-access-policies"></a>阶段 2：配置条件访问策略

首先，创建一个新的用户帐户作为专用全局管理员。

1. 在单独的选项卡上[，打开Microsoft 365 管理中心](https://admin.microsoft.com/)。
2. 选择 **"用户**  >  **""** 活动用户"，然后选择"**添加用户"。**
3. 在"**添加用户"** 窗格中，在"名字"、"显示名称"和"用户名"框中输入 **DedicatedAdmin。** 
4. 选择 **"密码****"，选择"允许我创建密码**"，然后输入强密码。 在安全位置记录此新帐户的密码。
5. 选择“**下一步**”。
6. 在"**分配产品许可证**"窗格中，选择 **"Microsoft 365 E5"，** 然后选择"下一 **步"。**
7. 在"**可选设置"窗格中**，选择"**角色**  >  **""管理中心""访问**  >  **全局管理员""下一**  >  **步"。**
8. 在"**你已完成"窗格中**，选择"**完成添加"，** 然后选择"关闭 **"。**

接下来，创建一个名为 GlobalAdmins 的新组，并添加 DedicatedAdmin 帐户。

1. 在 **"Microsoft 365 管理中心"** 选项卡上，选择左侧导航中的"组"，然后选择"组 **"。**
2. 选择 **"添加组"。**
3. 在"**选择组类型"窗格中**，选择"**安全性"，** 然后选择"下一 **步"。**
4. 在"**设置基础知识"窗格中**，选择"**创建组**"，然后选择"关闭 **"。**
5. 在"**查看并完成添加组"窗格中**，输入 **GlobalAdmins，** 然后选择"下一 **步"。**
7. 在组列表中，选择 **GlobalAdmins** 组。
8. 在"**全局管理"窗格中**，选择"成员 **"，** 然后选择"**查看所有和管理成员"。**
9. 在 **"全局管理员"窗格中**，选择"**添加** 成员"，选择 **"DedicatedAdmin"** 帐户和全局管理员帐户，然后选择"**保存**  >  **""关闭""**  >  **关闭"。**

接下来，创建条件访问策略，要求对全局管理员帐户进行多重身份验证，如果登录风险为中或高，则拒绝身份验证。

此第一个策略要求所有全局管理员帐户都使用 MFA。

1. 在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。
2. 单击 **Azure Active Directory**  >    >  **安全条件访问"。**
3. 在"**条件访问 – 策略"** 窗格中，选择"**基线策略： 要求管理员使用 MFA (预览) "。**
4. 在基线 **策略窗格中**，选择立即 **使用策略>保存。**

当登录风险为中或高时，第二个策略将阻止访问全局管理员帐户身份验证。

1. 在"**条件访问 – 策略"** 窗格中，选择"**新建策略"。**
2. 在"**新建"** 窗格中，在"**名称"中输入"** 全局 **管理员"。**
3. 在"**分配"** 部分，选择"**用户和组"。**
4. 在"**用户和** 组"**窗格** 的"包含"选项卡上，选择 **"选择用户和组**  >  **用户和组**  >  **"选择**。
5. 在"**选择**"窗格中，选择 **"GlobalAdmins"** 组，然后选择"**选择完成**  >  **"。**
6. 在"**分配"** 部分，选择"条件 **"。**
7. 在"**条件"** 窗格中，选择"**登录风险**"，为"配置"选择"是"，选择"高"和"中等"，然后选择"**选择** 并 **完成"。** 
8. 在"**新建"窗格** 的"访问控制"**部分**，选择"授予 **"。**
9. 在"**授予"窗格中**，选择 **"阻止访问**"，然后选择"选择 **"。**
10. 在"**新建"** 窗格中，为"启用策略"选择 **"打开****"，** 然后选择"创建 **"。**
11. 关闭 **Azure 门户，** 然后 **Microsoft 365 管理中心** 选项卡。

若要测试第一个策略，请注销，然后使用 DedicatedAdmin 帐户登录。 系统将提示你配置 MFA。 这演示了正在应用第一个策略。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)