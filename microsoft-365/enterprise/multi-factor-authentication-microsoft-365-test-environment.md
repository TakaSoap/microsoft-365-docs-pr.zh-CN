---
title: Microsoft 365企业测试环境的多重身份验证
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
- seo-marvel-apr2020
- admindeeplinkMAC
description: 使用发送到适用于企业测试环境的 Microsoft 365 智能手机的短信配置多重身份验证。
ms.openlocfilehash: 283504812466568c4254febe57c3f2886dd3098e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154994"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于企业测试环境Microsoft 365多重身份验证

*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*

若要为登录 Microsoft 365 或任何将 Azure AD 租户用于订阅的服务或应用程序提供额外的安全级别，可以启用 Azure AD 多重身份验证，该身份验证不仅需要用户名和密码来验证帐户。

使用多重身份验证，用户必须确认电话呼叫、键入短信发送的验证码，或在正确输入密码后验证智能手机上的应用是否进行身份验证。 只有在满足第二个身份验证因素后，他们才能登录。
  
本文介绍如何为特定用户帐户启用和测试基于短信的身份验证。
  
在企业测试环境中为 Microsoft 365设置多重身份验证包括两个阶段和第三个可选阶段：
- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：启用和测试 User 2 帐户的多重身份验证](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [阶段 3：使用条件访问策略启用和测试多重身份验证](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果只需要测试具有最低要求的轻型多重身份验证，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中测试多重身份验证，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试多重身份验证不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 同步。 它在此处作为一个选项提供，以便你可以测试多重身份验证，并在代表典型组织的环境中对其进行试验。
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>阶段 2：启用和测试 User 2 帐户的多重身份验证

通过以下步骤为 User 2 帐户启用多重身份验证：
  
1. 打开浏览器的单独专用实例，转到 Microsoft 365 管理中心 () ，然后使用全局管理员 [https://portal.microsoft.com](https://portal.microsoft.com) 帐户登录。
    
2. 在左侧导航栏中，选择"**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**""活动用户"。**</a>
    
3. 在"活动用户"窗格中，选择 **"多重身份验证"。**
    
4. 在列表中，选择 **"用户 2"** 帐户。
    
5. 在"**用户 2"** 部分中的"**快速步骤"下**，选择"**启用"。**
    
6. 在 **"关于启用多重** 身份验证"对话框中，选择"**启用多重身份验证"。**
    
7. 在"**更新成功"** 对话框中，选择"关闭 **"。**
    
8. 在 **"Microsoft 365 管理中心"** 选项卡上，选择右上角的用户帐户图标，然后选择"**注销"。**
    
9. 关闭浏览器实例。
   
完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：
  
1. 打开浏览器的新专用实例。
    
2. 转到["Microsoft 365 管理中心"，](https://admin.microsoft.com)然后使用 User 2 帐户名称和密码登录。
    
3. 登录后，系统将提示你设置帐户，了解详细信息。 选择“**下一步**”。
    
4. 在“其他安全性验证”页上： 
    
   - 选择你所在的国家或地区。
    
   - 输入将接收短信的智能手机的电话号码。
    
   - 在 **"方法**"中 **，选择"通过短信向我发送代码"。**
    
5. 选择“**下一步**”。
    
6. 输入智能手机上收到的短信中的验证码，然后选择"验证 **"。**
    
7. 在"**步骤 3： 保留现有应用程序"页上**，选择"完成 **"。**
    
8. 如果这是你第一次使用 User 2 帐户登录，那么系统将提示你更改密码。 输入原始密码和新密码两次，然后选择更新 **密码并登录**。 将新密码记录在安全位置。
    
    你应该在浏览器Office主页"选项卡上看到用户 2  Microsoft Office门户。

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>阶段 3：使用条件访问策略启用和测试多重身份验证

*此阶段只能用于企业Microsoft 365测试环境。*

在此阶段，使用组和条件访问策略为用户 3 帐户启用多重身份验证。

接下来，创建一个名为 MFAUsers 的新组，并添加 User 3 帐户。

1. 在 **"Microsoft 365 管理中心"** 选项卡上，选择左侧导航中的"组"，然后选择"组 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**"。**</a>
2. 选择 **"添加组"。**
3. 在"**选择组类型"窗格中**，选择"**安全性"，** 然后选择"下一 **步"。**
4. 在"**设置基础知识"窗格中**，选择"**创建组**"，然后选择"关闭 **"。**
5. 在"**查看并完成添加组"窗格中**，输入 **"MFAUsers"，** 然后选择"下一 **步"。**
6. 在组列表中，选择 **MFAUsers** 组。
7. 在 **"MFAUsers"** 窗格中，选择"**成员"，** 然后选择"**查看所有和管理成员"。**
8. 在 **"MFAUsers"** 窗格中，选择"**添加** 成员"，选择 **"用户 3"** 帐户，然后选择"**保存**  >  **关闭**  >  **关闭"。**

接下来，创建条件访问策略，要求 MFAUsers 组的成员进行多重身份验证。

1. 在浏览器的新选项卡中，转到 [https://portal.azure.com](https://portal.azure.com) 。
2. 选择 **Azure Active Directory**  >    >  **安全条件访问"。**
3. 在"**条件访问 – 策略"** 窗格中，选择"**新建策略"。**
4. 在"**新建**"窗格中，在"名称"**框中输入用户帐户的 MFA。** 
5. 在"**分配"** 部分，选择"**用户和组"。**
6. 在"**用户和** 组"**窗格** 的"包含"选项卡上，选择 **"选择用户和组**  >  **用户和组**  >  **"选择**。
7. 在"**选择**"窗格中，选择 **"MFAUsers"** 组，然后选择"**选择完成**  >  **"。**
8. 在"**新建"窗格** 的"访问控制"**部分**，选择"授予 **"。**
9. 在"**授予"** 窗格中，选择 **"需要多重身份验证"，** 然后选择"选择 **"。**
10. 在"**新建"** 窗格中，为"启用策略"选择 **"打开****"，** 然后选择"创建 **"。**
11. 关闭 **Azure 门户并****Microsoft 365 管理中心选项卡**。

若要测试此策略，请注销，然后使用 User 3 帐户登录。 系统将提示你配置 MFA。 这演示了正在应用 MFAUsers 策略。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)