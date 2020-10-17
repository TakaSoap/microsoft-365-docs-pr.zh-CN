---
title: 适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 配置 Azure AD 标识保护并分析 Microsoft 365 for 企业测试环境中的当前帐户。
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487704"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

您可以使用 Azure Active Directory (Azure AD) 标识保护，以检测影响组织的身份、配置自动响应和调查事件的潜在漏洞。 本文介绍如何使用 Azure AD Identity Protection 查看测试环境帐户的分析。

在 Microsoft 365 for 企业测试环境中设置 Azure AD 标识保护包括两个阶段：

- [第1阶段：构建您的 Microsoft 365 企业版测试环境](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [第2阶段：使用 Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>第1阶段：构建您的 Microsoft 365 企业版测试环境

如果你希望仅使用最低要求以轻型方式测试 Azure AD Identity Protection，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试 Azure AD 标识保护，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试 Azure AD 标识保护不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。 此处提供它作为选项，以便您可以在代表典型组织的环境中测试 Azure AD 标识保护并对其进行实验。
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>第2阶段：使用 Azure AD Identity Protection

1. 打开浏览器的私有实例，并 [https://portal.azure.com](https://portal.azure.com) 使用 Microsoft 365 for 企业版测试环境的全局管理员帐户登录 Azure 门户。
2. 在 Azure 门户中，在搜索框中键入 **identity protection** ，然后选择 " **Azure AD identity protection**"。
3. 在 " **身份保护-概述** " 刀片中，选择每个报告以查看报告的内容。
4. 在 " **通知**" 下，选择 "用户" " **风险检测警报**"。
5. 在 " **检测到风险的用户警报** " 窗格中，选择 " **中**"。
6. 对于 **向以下用户发送电子邮件**，请选择 " **包含** "，并验证全局管理员帐户是否在所选成员列表中。
7. 选择“**保存**”。

在 " **保护**" 下，选择各种策略以查看如何配置它们。 如果您创建并激活策略，请确保它不会阻止对所有用户的访问，否则您可能无法登录。 若要防止出现这种情况，请排除特定用户帐户，如全局管理员。

有关进一步的测试和实验，请参阅 [模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
