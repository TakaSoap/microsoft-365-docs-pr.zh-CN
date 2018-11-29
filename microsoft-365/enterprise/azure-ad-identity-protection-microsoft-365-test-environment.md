---
title: 为 Microsoft 365 企业版的 azure AD 身份保护测试环境
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
description: 配置 Azure AD 身份保护并分析 Microsoft 365 企业版测试环境中的当前帐户。
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865483"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>为 Microsoft 365 企业版的 azure AD 身份保护测试环境

Azure AD 身份保护可以检测潜在安全漏洞影响组织的标识、 配置自动的答复，并调查事件。本文介绍如何启用 Azure AD 身份保护并查看分析的测试环境帐户。

有两个阶段设置 Microsoft 365 企业版测试环境中的 Azure AD 身份保护：

1. 创建 Microsoft 365 企业版测试环境。
2. 启用并使用 Azure AD 身份保护。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第 1 阶段： 构建 Microsoft 365 企业版测试环境

如果您只想要测试的最低硬件要求与轻型方式 Azure AD 身份保护，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。
  
如果您想要测试模拟企业中的 Azure AD 身份保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。
  
> [!NOTE]
> 测试 Azure AD 身份保护不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试 Azure AD 身份保护并与之试验环境值，该值代表典型组织中。 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>第 2 阶段： 启用并使用 Azure AD 身份保护

1. 打开浏览器的专用实例并登录到 Azure 门户在[https://portal.azure.com](https://portal.azure.com)与 Microsoft 365 企业版测试环境的全局管理员帐户。
2. 在 Azure 门户中，单击**所有服务 > 市场**。
3. 键入**Azure AD 身份保护**，然后单击它。
4. **Getting Started**刀片上,**设置**下单击**Onboard** ，单击**固定至仪表板**，，然后单击**创建**。
5. 在 Azure 门户中，单击仪表板上的**Azure AD 身份防护**。 

   您应看到**Azure AD 身份保护-概述**刀片仪表板。在下，**安全漏洞**，请注意，它决定不多因素身份验证注册的用户帐户数。此号码将因以前 Microsoft 365 Enterprise 测试实验室指南，您已完成。

6. 单击通过**调查**以查看是否有任何用户或已检测到的事件类别。

进一步测试和实验，请参阅[模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。

在标识阶段的信息和链接以部署生产环境中的 Azure AD 身份保护，请参阅[Protect 针对凭据损害](identity-azure-ad-identity-protection.md)步骤。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：标识](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
