---
title: Azure AD企业测试环境Microsoft 365标识保护
f1.keywords:
  - NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
  - TLG
  - Ent_TLGs
description: 配置Azure AD Identity Protection 并分析企业测试Microsoft 365中的当前帐户。
---

# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD企业测试环境Microsoft 365标识保护

*本测试实验室指南只能用于Microsoft 365测试环境。*

可以使用 Azure Active Directory (Azure AD) Identity Protection 检测影响组织标识的潜在漏洞，配置自动响应并调查事件。 本文介绍如何使用 Azure AD Identity Protection 查看测试环境帐户的分析。

在Azure AD测试环境中设置 Microsoft 365 Identity Protection 包括两个阶段：

- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：使用Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你希望仅按照最低Azure AD轻型方式测试 Identity Protection，请按照轻型基本配置[中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟企业中Azure AD Identity Protection，请按照传递身份验证[中的说明进行操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试 Azure AD Identity Protection 不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 的目录同步。 它在此处作为一个选项提供，以便你可以Azure AD Identity Protection，在代表典型组织的环境中试验它。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>阶段 2：使用Azure AD Identity Protection

1. 打开浏览器的专用[https://portal.azure.com](https://portal.azure.com)实例，然后使用适用于企业测试环境Microsoft 365全局管理员帐户登录到 Azure 门户。
2. 在 Azure 门户中，**在搜索框中** 键入标识保护，然后选择"Azure AD **Identity Protection"**。
3. 在 **"Identity Protection - 概述"** 边栏选项卡中，选择每个报告以查看报告内容。
4. 在 **"通知**"下 **，选择"存在风险的用户检测到的警报"**。
5. 在" **存在风险的用户检测到警报"窗格中** ，选择"中等 **"**。
6. 对于 **"将电子邮件发送给以下用户"，** 选择"已包含"并验证全局管理员帐户是否位于选定成员列表中。
7. 选择“保存”。

在 **"** 保护"下，选择各种策略以查看如何配置策略。 如果创建并激活策略，请确保它不会阻止所有用户的访问，否则可能无法登录。 若要阻止这种情况发生，请排除特定用户帐户，例如全局管理员。

有关进一步测试和试验，请参阅 [模拟风险事件](/azure/active-directory/active-directory-identityprotection-playbook)。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[部署标识](deploy-identity-solution-overview.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)