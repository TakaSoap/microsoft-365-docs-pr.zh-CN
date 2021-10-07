---
title: 适用于企业测试环境Microsoft 365 Azure AD Identity Protection
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
description: 配置 Azure AD Identity Protection 并分析企业测试Microsoft 365中的当前帐户。
ms.openlocfilehash: bba9567b8257d112f71875fc39a93f2bea90e6ef
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208345"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于企业测试环境Microsoft 365 Azure AD Identity Protection

*本测试实验室指南只能用于Microsoft 365测试环境。*

可以使用 Azure AD Azure Active Directory (Identity Protection) 检测影响组织标识的潜在漏洞，配置自动响应并调查事件。 本文介绍如何使用 Azure AD Identity Protection 查看测试环境帐户的分析。

在企业测试环境中Microsoft 365 Azure AD Identity Protection 包括两个阶段：

- [第 1 阶段：构建Microsoft 365测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [阶段 2：使用 Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365 [for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第 1 阶段：构建Microsoft 365测试环境

如果你希望仅测试具有最低要求的轻型 Azure AD Identity Protection，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
如果要在模拟的企业中测试 Azure AD Identity Protection，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> 测试 Azure AD Identity Protection 不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 它在此处作为一个选项提供，以便你可以测试 Azure AD Identity Protection，在代表典型组织的环境中试验它。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>阶段 2：使用 Azure AD Identity Protection

1. 打开浏览器的专用实例，然后使用适用于企业测试环境的 Microsoft 365 的全局管理员帐户 [https://portal.azure.com](https://portal.azure.com) 登录到 Azure 门户。
2. 在 Azure 门户中， **在搜索框中** 键入标识保护，然后选择 **Azure AD Identity Protection**。
3. 在 **"Identity Protection - 概述"** 边栏选项卡中，选择每个报告以查看报告内容。
4. 在 **"通知"** 下 **，选择"处于风险中检测到警报的用户"。**
5. 在"**存在风险的用户检测到警报"窗格中**，选择"中等 **"。**
6. For **Emails are sent to the following users，** select **Included** and verify that your global admin account is in the list of selected members.
7. 选择“**保存**”。

在 **"保护**"下，选择各种策略以查看如何配置策略。 如果创建并激活策略，请确保它不会阻止所有用户的访问，否则可能无法登录。 若要阻止这种情况发生，请排除特定用户帐户，例如全局管理员。

有关进一步测试和实验，请参阅 [模拟风险事件](/azure/active-directory/active-directory-identityprotection-playbook)。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)