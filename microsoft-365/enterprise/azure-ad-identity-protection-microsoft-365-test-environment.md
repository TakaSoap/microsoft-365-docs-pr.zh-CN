---
title: 适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 配置 Azure AD 标识保护并分析 Microsoft 365 企业版测试环境中的当前帐户。
ms.openlocfilehash: 97530dcec9c32882bbe3b66eb53eaa6d4668a838
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071711"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护

通过 Azure AD 标识保护，可以检测影响组织标识、配置自动响应和调查事件的潜在漏洞。 本文介绍如何启用 Azure AD Identity Protection 并查看测试环境帐户的分析。

在 Microsoft 365 企业版测试环境中设置 Azure AD 标识保护有两个阶段：

1. 创建 Microsoft 365 企业版测试环境。
2. 启用和使用 Azure AD Identity Protection。

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>第1阶段：构建 Microsoft 365 企业版测试环境

如果只想使用最低要求以轻型方式测试 Azure AD 标识保护，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。
  
如果要在模拟的企业中测试 Azure AD 标识保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。
  
> [!NOTE]
> 测试 Azure AD Identity Protection 不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。 此处提供它作为选项，以便您可以在代表典型组织的环境中测试 Azure AD 标识保护并对其进行实验。 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>第2阶段：启用和使用 Azure AD 标识保护

1. 打开浏览器的私有实例，并[https://portal.azure.com](https://portal.azure.com)使用 Microsoft 365 企业版测试环境的全局管理员帐户登录到 Azure 门户。
2. 在 Azure 门户中，单击 "**所有服务 > Marketplace**"。
3. 键入**AZURE AD Identity Protection** ，然后单击它。
4. 在 "**入门" 边栏选项**卡上的 **"设置** **" 下，单击 "** **固定到仪表板**"，然后单击 "**创建**"。
5. 在 Azure 门户中，单击仪表板上的 " **AZURE AD 标识保护**"。 

   您应该会看到一个带有仪表板的**AZURE AD 标识保护-概述**刀片。 在 "**漏洞**" 下，请注意，它确定了没有多重身份验证注册的用户帐户数。 此数字取决于您已完成的以前的 Microsoft 365 企业测试实验室指南。

6. 依次单击要进行**调查**的类别，以查看是否有任何用户或事件已检测到。

有关进一步的测试和实验，请参阅[模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。

若要了解如何在生产环境中部署 Azure AD 标识保护的信息和链接，请参阅 Identity 阶段中的防止[凭据泄露](identity-secure-user-sign-ins.md#identity-ident-prot)步骤。

## <a name="next-step"></a>后续步骤

在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。

## <a name="see-also"></a>另请参阅

[阶段 2：标识](identity-infrastructure.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版部署](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
