---
title: 保护 Microsoft 365 企业版测试环境中的全局管理员帐户
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
description: 使用以下步骤来保护 Microsoft 365 企业版测试环境中的全局管理员帐户。
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865422"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>保护 Microsoft 365 企业版测试环境中的全局管理员帐户

您可以确保您的管理员帐户尽可能安全以阻止对您的组织的数字攻击。本文介绍如何使用 Office 365 云应用程序安全性和 Azure AD 条件访问策略来保护全局管理员帐户。

有两个阶段保护 Microsoft 365 企业版测试环境中的全局管理员帐户：

1.  创建 Microsoft 365 企业版测试环境。
2.  保护您的专用的全局管理员帐户。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要测试的最低硬件要求与轻型方式的全局管理员帐户保护，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要测试模拟企业中的全局管理员帐户保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试全局管理员帐户保护不需要模拟的企业测试环境，其中包括模拟的 intranet 连接到 Internet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试全局管理员帐户保护并与之试验环境值，该值代表典型组织中。 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>第 2 阶段： 配置云应用程序安全性和条件的访问策略

首先，创建 Office 365 云应用程序安全性策略监视全局管理员帐户活动并将通知发送给您的全局管理员帐户的电子邮件地址。 

1. 登录到 Office 365 门户[http://portal.office.com](http://portal.office.com)使用全局管理员帐户。
2. 单击**管理员**图块。在**Office Admin center**选项卡上单击**管理中心 > 安全和合规性**。
3. 在左侧的导航窗格中，单击**通知 > 管理高级通知**。
4. 在**高级通知的管理**页上，单击**打开 Office 365 云应用程序安全性**，然后单击**转到 Office 365 云应用程序安全性**。
5. 在新的**仪表板**选项卡，单击**控件 > 策略**。
6. 在**策略**页上，单击**创建策略**，，然后单击**活动策略**。
7. 在**策略名称**框中，键入**管理活动**。
8. 在“**策略严重性**”中，单击“**高**”。
9. 在**类别**中，单击**特权的帐户**。
10. 在**创建筛选器策略**，在**以下所有条件匹配的活动**中，单击**管理活动**。
11. 在“**警报**”中，单击“**作为电子邮件发送警报**”。在“**收件人**”中，键入你的全局管理员帐户的电子邮件地址。
12. 在页面底部，单击“**创建**”。
13. 关闭**仪表板**选项卡。
    
接下来，创建新的用户帐户作为专用的全局管理员。

1. 在**Office Admin center**选项卡上，在**活动用户**下单击**添加用户**。
2. 在**新建用户**页上，在**名字**、**显示名称**和**用户名**中键入**DedicatedAdmin** 。
3. 单击**密码**，单击**让我创建密码**，，，然后键入强密码。在安全位置记录此新帐户的密码。
4. 清除**进行此更改其密码它们首次登录时的用户**。
5. 单击**角色**，然后单击**全局管理员**。
6. 单击**产品许可证**，，然后打开的**企业移动 + 安全 E5**和**Office 365 企业 E5 许可证**。
7. 单击" **添加**"。
8. 在**用户已添加页上**，清除**发送电子邮件中的密码**，，然后单击**关闭**。

接下来，创建一个名为 GlobalAdmins 的新组并向其添加 DedicatedAdmin 帐户。

1. 在**Office Admin center**选项卡中，单击左侧导航窗格中，在组图标，然后单击**组**。
2. 单击**添加组**。
3. 在**新建组**页中，键入**GlobalAdmins**。
4. 单击您的全局管理员帐户的**选择所有者**单击，然后单击**添加 > 关闭**。
5. 在组列表中，单击**GlobalAdmins**组。
6. 在**GlobalAdmins**页上，单击**编辑的成员**，然后单击**添加成员**。
7. 在列表中，单击**DedicatedAdmin**帐户，然后单击**保存 > 关闭 > 关闭 > Admin center**。

接下来，创建条件访问策略需要多因素身份验证的全局管理员帐户和拒绝身份验证登录风险时中型或更高。

此第一个策略要求所有全局管理员帐户使用 MFA。

1. 在浏览器的新建选项卡上，转到[https://portal.azure.com](https://portal.azure.com)。
2. 单击**Azure Active Directory > 条件访问**。
3. 在**条件访问 – 策略**刀片中，单击**基准策略： 对于管理员 （预览） 需要 MFA**。
4. 在**比较基准策略...** 刀片中，单击**立即使用策略 > 保存**。

此第二个策略阻止对访问登录助手风险时中型或更高的全局管理员帐户身份验证。

1. 在**条件访问 – 策略**刀片中，单击**新建策略**。
2. 在**新建**刀片，在**名称**中键入**全局管理员**。
3. 在**分配**部分中，单击**用户和组**。
4. 在**用户和组**刀片**包含**选项卡上，单击**选择用户和组 > 用户和组 > 选择**。
5. 在**选择**刀片中，单击**GlobalAdmins > 选择 > 完成**。
6. 在**分配**部分中，单击**条件**。
7. **条件**刀片上, 单击**登录风险**，单击**是****配置**，单击**高**和**Medium**，然后单击**选择**并**完成**。
8. 在**新建**刀片**访问控制**部分中，单击**授予**。
9. **授予**刀片上, 单击**阻止访问**，然后单击**选择**。
10. **新建**刀片上**的**启用策略**，单击**，然后单击**创建**。
11. 关闭**Azure 门户**和**Office 管理中心**选项卡。

若要测试的第一个策略，请先注销，然后使用 DedicatedAdmin 帐户登录。您应提示用户帐户配置 MFA。此示例演示应用的第一个策略。

有关信息和链接以保护您的全局管理员帐户在生产中的标识阶段，请参阅[Protect 全局管理员帐户](identity-designate-protect-admin-accounts.md)步骤。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：标识](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
