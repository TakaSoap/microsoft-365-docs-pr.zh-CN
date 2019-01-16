---
title: Microsoft 365 企业版的多因素身份验证测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 配置多重身份验证使用发送到 Microsoft 365 企业版测试环境中智能电话的短信。
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865401"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企业版的多因素身份验证测试环境

登录到 Office 365 或任何服务或为您的组织使用 Azure AD 租户的应用程序的安全性的其他级别，可以启用 Azure 多因素身份验证，这要求远不止用户名和密码验证帐户。使用多因素身份验证，用户所需确认电话呼叫，键入验证代码发送文本消息，或在其智能手机上正确输入自己的密码之后指定应用程序密码。在此第二个身份验证因素已得到满足之后，才可以登录状态。 
  
本文介绍如何启用和测试文本为特定帐户的基于消息的身份验证。
  
有两个阶段设置多因素身份验证 Microsoft 365 企业版测试环境中的帐户：
  
1. 创建 Microsoft 365 企业版测试环境。
    
2. 为 User 2 帐户启用并测试多重身份验证。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要测试的最低硬件要求与轻型方式中的多因素身份验证，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要测试模拟企业中的多因素身份验证，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试多因素身份验证不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试多因素身份验证并代表典型组织的环境中试验它。 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>阶段 2：启用和测试 User 2 帐户的多重身份验证

通过以下步骤为 User 2 帐户启用多重身份验证：
  
1. 打开单独的专用的浏览器实例，请转到 Office 门户 ([https://office.com](https://office.com))，然后使用您的全局管理员帐户登录。
    
2. 在主门户页上，单击“管理员”****。
    
3. 在左侧导航栏中，依次单击“用户”和“活动用户”****。
    
4. 在活动用户窗格中，单击**更多 > 多因素身份验证设置**。
    
5. 在列表中，选择的**用户 2**帐户。
    
6. 在**用户 2**部分中，单击**快速步骤**下的**启用**。
    
7. 在**有关启用多重身份验证**对话框中，单击**启用多重身份验证**。
    
8. 在**更新成功**对话框中，单击**关闭**。
    
9. 在**Microsoft Office Home**选项卡上，单击右上方中的用户帐户图标，然后单击**注销**。
    
10. 关闭浏览器实例。
   
完成 User 2 帐户的配置，通过以下步骤，使用短信对其进行验证和测试：
  
1. 打开浏览器的专用的新实例。
    
2. 转到 Office 门户 ([https://office.com](https://office.com)) 和使用用户 2 帐户的登录 (user2 @\<组织名称 >。 onmicrosoft.com) 和密码。
    
3. 在登录后被提示设置的详细信息的帐户。单击**下一步**。
    
4. 在**其他安全验证**页上：
    
   - 选择你所在的国家或地区。
    
   - 键入接收短信的智能手机的电话号码。
    
   - 在**方法**中，单击**给我发送的短信代码**。
    
5. 单击"下一步"。
    
6. 输入介于智能手机上收到的文本消息验证代码，然后单击**验证**。
    
7. 在**步骤 3： 保留现有的应用程序**页上，在安全的位置，记录用户 2 帐户的显示应用程序密码，然后单击**完成**。
    
8. 如果这是首次您使用登录用户 2 帐户后，在系统提示您要更改的密码。两次，键入原始密码和新密码，然后单击**更新密码和登录**。记录在安全位置的新密码。
    
    在浏览器的**Microsoft Office Home**选项卡上，您应用户 2 看到 Office 门户。


在标识阶段的信息和链接以部署生产环境中的多因素身份验证，请参阅[设置多因素身份验证](identity-multi-factor-authentication.md)步骤。
    
## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：身份](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
