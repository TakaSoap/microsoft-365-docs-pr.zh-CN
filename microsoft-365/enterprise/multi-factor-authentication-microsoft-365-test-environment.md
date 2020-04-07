---
title: Microsoft 365 企业版测试环境的多重身份验证
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 使用发送到 Microsoft 365 企业版测试环境中的智能手机的短信配置多重身份验证。
ms.openlocfilehash: b17c6b3b39bebaff2737ea5e9bb198beef00844c
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153876"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企业版测试环境的多重身份验证

*此测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*

若要使用其他级别的安全来登录 Microsoft 365 或使用 Azure AD 租户订阅订阅的任何服务或应用程序，您可以启用 Azure 多重身份验证，它需要的用户和密码不只需要用户名和密码即可验证帐户。 

使用多重身份验证时，用户需要确认电话呼叫、在短信中键入验证代码，或者在正确输入密码后在智能手机上指定应用密码。 仅在满足第二个身份验证因素时才能登录。 
  
本文介绍如何为特定用户帐户启用和测试基于短信的身份验证。
  
为 Microsoft 365 企业版测试环境中的帐户设置多重身份验证有两个阶段：
  
1. 创建 Microsoft 365 企业版测试环境。
    
2. 为 User 2 帐户启用并测试多重身份验证。

3. 使用条件访问策略启用和测试多重身份验证（可选）。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>阶段 1：构建 Microsoft 365 企业版测试环境。

如果只想使用最低要求以轻型方式测试多重身份验证，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试多重身份验证，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试多重身份验证不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。 它在此处作为一个选项提供，以便你可以测试多重身份验证，并在代表典型组织的环境中对其进行试验。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>阶段 2：启用和测试 User 2 帐户的多重身份验证

通过以下步骤为 User 2 帐户启用多重身份验证：
  
1. 打开浏览器的单独私有实例，转到 Microsoft 365 管理中心（[https://portal.microsoft.com](https://portal.microsoft.com)），然后使用全局管理员帐户登录。
    
2. 在左侧导航窗格中，单击“**用户 > 活动用户**”。
    
3. 在 "活动用户" 窗格中，单击 "**多因素身份验证**"。
    
4. 在列表中，选择 "**用户 2** " 帐户。
    
5. 在“User 2”**** 部分的“快速步骤”**** 下，单击“启用”****。
    
6. 在“关于启用多重身份验证”**** 对话框中，单击“启用多重身份验证”****。
    
7. 在 "**更新成功**" 对话框中，单击 "**关闭**"。
    
8. 在 " **Microsoft 365 管理中心**" 选项卡上，单击右上角的 "用户帐户" 图标，然后单击 **"注销"。**
    
9. 关闭浏览器实例。
   
完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：
  
1. 打开浏览器的新的私有实例。
    
2. 转到 Office 365 门户（[https://portal.office.com](https://portal.office.com)），并使用用户2帐户名称和密码登录。
    
3. 登录后，系统会提示您设置帐户以获取详细信息。 单击“**下一步**”。
    
4. 在“其他安全性验证”**** 页上： 
    
   - 选择你所在的国家或地区。
    
   - 键入接收短信的智能手机的电话号码。
    
   - 在**方法**中，单击 "**通过短信向我发送代码**"。
    
5. 单击“**下一步**”。
    
6. 输入智能手机收到的短信中的验证码，然后单击“验证”****。
    
7. 在“第 3 步: 保留现有应用程序”**** 页上，将显示的 User 2 帐户的应用密码记录在安全位置，然后单击“完成”****。
    
8. 如果这是你第一次使用 User 2 帐户登录，那么系统将提示你更改密码。键入原始密码和新密码两次，然后单击“更新密码并登录”****。将新密码记录在安全位置。
    
    您应在浏览器的 " **Microsoft Office 主页**" 选项卡上看到 "用户 2" 的 Office 门户。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>第3阶段：使用条件访问策略启用和测试多重身份验证

*此阶段仅可用于 Microsoft 365 企业版测试环境。*

在此阶段中，将使用组和条件访问策略为用户3帐户启用多重身份验证。

接下来，创建一个名为 "MFAUsers" 的新组，并向其添加用户3帐户。

1. 在 " **Microsoft 365 管理中心**" 选项卡上，单击左侧导航栏中的 "**组**"，然后单击 "**组**"。
2. 单击 "**添加组**"。
3. 在 "**选择组类型**" 窗格中，选择 "**安全性**"，然后单击 "**下一步**"。
4. 在 "**设置基础知识"** 窗格中，单击 "**创建组**"，然后单击 "**关闭**"。
5. 在 "**查看并完成添加组**窗格" 中，键入**MFAUsers**，然后单击 "**下一步**"。
6. 在组列表中，单击 " **MFAUsers** " 组。
7. 在 " **MFAUsers** " 窗格中，单击 "**成员**"，然后单击 "**查看所有和管理成员**"。
8. 在 " **MFAUsers** " 窗格中，单击 "**添加成员**"，选择**用户 3**帐户，然后单击 "**保存" > 关闭 > "关闭**"。

接下来，创建一个条件访问策略，以要求对 MFAUsers 组成员进行多重身份验证。

1. 在浏览器的新选项卡中，转[https://portal.azure.com](https://portal.azure.com)到。
2. 单击 " **Azure Active Directory > Security > 条件访问**。
3. 在 "**条件访问–策略**" 窗格中，单击 "**新建策略**"。
4. 在 "**新建**" 窗格中，为 "**名称**" 中**的用户帐户键入 MFA** 。
5. 在 "**工作分配**" 部分，单击 "**用户和组**"。
6. 在 "**用户和组**" 窗格的 "**包含**" 选项卡上，单击 "选择用户和组" **> 用户和组**"。 >" 选择 "。
7. 在**选择**窗格中，单击 " **MFAUsers** " 组，然后单击 "**选择 > 完成**"。
8. 在**新**窗格的 "**访问控制**" 部分，单击 "**授予**"。
9. 在 "**授予**" 窗格中，单击 "**要求多重身份验证**"，然后单击 "**选择**"。
10. 在 "**新建**" 窗格中，单击 **"** **启用策略**"，然后单击 "**创建**"。
11. 关闭 " **Azure 门户**" 和 " **Microsoft 365 管理中心**" 选项卡。

若要测试此策略，请注销并使用用户3帐户登录。 系统会提示您配置 MFA。 这说明正在应用 MFAUsers 策略。

若要了解如何在生产环境中部署多重身份验证的信息和链接，请参阅 Identity 阶段中的[设置多重身份验证](identity-secure-user-sign-ins.md#identity-mfa)步骤。
    
## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：标识](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
